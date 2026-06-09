# CredentialUpdateNotify2(_UNICODE_STRING *,void *,ulong,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void * *,ulong *)

- ea: `0x180004390`
- end: `0x180004423`
- name: `?CredentialUpdateNotify2@@YAJPEAU_UNICODE_STRING@@PEAXKK0000PEAPEAXPEAK@Z`
- size: `147`
- prototype: `int __fastcall(struct _UNICODE_STRING *, void *, unsigned int, unsigned int, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x180005978`
- `0x180009d50`

## pseudocode

```c
int __fastcall CredentialUpdateNotify2(
        struct _UNICODE_STRING *a1,
        void *a2,
        unsigned int a3,
        unsigned int a4,
        struct _UNICODE_STRING *a5,
        struct _UNICODE_STRING *a6,
        struct _UNICODE_STRING *a7,
        struct _UNICODE_STRING *a8,
        void **a9,
        unsigned int *a10)
{
  unsigned int v15[14]; // [rsp+60h] [rbp-38h] BYREF

  *(_QWORD *)v15 = 0;
  KdcPwReadRegistry((struct _KDCPW_REG *)v15);
  return KdcBuildKerbCredentialsFromPassword(a1, a2, a3, a4, a5, a6, a8, v15[0], 1, a9, a10);
}

```

## disassembly

```asm
0x180004390  push    rbx
0x180004392  push    rbp
0x180004393  push    rsi
0x180004394  push    rdi
0x180004395  sub     rsp, 78h
0x180004399  mov     rbp, rcx
0x18000439c  mov     qword ptr [rsp+98h+var_38], 0
0x1800043a5  lea     rcx, [rsp+98h+var_38]; struct _KDCPW_REG *
0x1800043aa  mov     ebx, r9d
0x1800043ad  mov     edi, r8d
0x1800043b0  mov     rsi, rdx
0x1800043b3  call    ?KdcPwReadRegistry@@YAXPEAU_KDCPW_REG@@@Z; KdcPwReadRegistry(_KDCPW_REG *)
0x1800043b8  mov     rax, [rsp+98h+arg_48]
0x1800043c0  mov     r9d, ebx; unsigned int
0x1800043c3  mov     [rsp+98h+var_48], rax; unsigned int *
0x1800043c8  mov     r8d, edi; unsigned int
0x1800043cb  mov     rax, [rsp+98h+arg_40]
0x1800043d3  mov     rdx, rsi; void *
0x1800043d6  mov     [rsp+98h+var_50], rax; void **
0x1800043db  mov     rcx, rbp; struct _UNICODE_STRING *
0x1800043de  mov     eax, [rsp+98h+var_38]
0x1800043e2  mov     [rsp+98h+var_58], 1; int
0x1800043ea  mov     [rsp+98h+var_60], eax; unsigned int
0x1800043ee  mov     rax, [rsp+98h+arg_38]
0x1800043f6  mov     [rsp+98h+var_68], rax; struct _UNICODE_STRING *
0x1800043fb  mov     rax, [rsp+98h+arg_28]
0x180004403  mov     [rsp+98h+var_70], rax; struct _UNICODE_STRING *
0x180004408  mov     rax, [rsp+98h+arg_20]
0x180004410  mov     [rsp+98h+var_78], rax; struct _UNICODE_STRING *
0x180004415  call    ?KdcBuildKerbCredentialsFromPassword@@YAJPEAU_UNICODE_STRING@@PEAXKK000KHPEAPEAXPEAK@Z; KdcBuildKerbCredentialsFromPassword(_UNICODE_STRING *,void *,ulong,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,int,void * *,ulong *)
0x18000441a  add     rsp, 78h
0x18000441e  pop     rdi
0x18000441f  pop     rsi
0x180004420  pop     rbp
0x180004421  pop     rbx
0x180004422  retn
```
