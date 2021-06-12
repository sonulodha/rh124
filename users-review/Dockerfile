#Docker image for Managing Local Users and Groups
FROM centos:8
RUN yum install -y vim sudo passwd  openssh-clients  openssh-server && yum clean all
RUN useradd student 
RUN echo student | passwd --stdin student
RUN echo "student ALL=(ALL) ALL" > /etc/sudoers.d/student
RUN ssh-keygen -A
EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
RUN rm -rf /var/run/nologin
