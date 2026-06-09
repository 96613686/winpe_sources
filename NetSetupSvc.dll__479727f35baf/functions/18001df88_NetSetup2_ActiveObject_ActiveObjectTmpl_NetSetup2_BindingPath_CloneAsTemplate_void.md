# NetSetup2::ActiveObject::ActiveObjectTmpl<NetSetup2::BindingPath>::CloneAsTemplate(void)

- ea: `0x18001df88`
- end: `0x18001e05a`
- name: `?CloneAsTemplate@?$ActiveObjectTmpl@VBindingPath@NetSetup2@@@ActiveObject@NetSetup2@@QEAA?AVBindingPathTemplate@3@XZ`
- size: `210`
- prototype: `NetSetup2::ObjectCreationTemplate *__fastcall(__int64, NetSetup2::ObjectCreationTemplate *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180020384`

## callees

- `0x1800027c0`
- `0x18000d974`
- `0x180019ab4`
- `0x18001d27c`
- `0x18001df88`
- `0x18002c728`
- `0x18002c94c`
- `0x18002d560`

## pseudocode

```c
NetSetup2::ObjectCreationTemplate *__fastcall NetSetup2::ActiveObject::ActiveObjectTmpl<NetSetup2::BindingPath>::CloneAsTemplate(
        __int64 a1,
        NetSetup2::ObjectCreationTemplate *a2)
{
  __int64 v3; // rdx
  NetSetup2::ActiveObject *v4; // rsi
  __int64 v5; // rdi
  __int64 v6; // rbp
  struct Property v7; // rax
  _BYTE v9[24]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v10[24]; // [rsp+48h] [rbp-50h] BYREF
  _QWORD v11[3]; // [rsp+60h] [rbp-38h] BYREF

  *(_OWORD *)a2 = 0;
  *((_QWORD *)a2 + 2) = 0;
  NetSetup2::ObjectCreationTemplate::ObjectCreationTemplate(a2);
  v4 = (NetSetup2::ActiveObject *)((v3 - 40) & -(__int64)(v3 != 0));
  NetSetup2::ActiveObject::GetPropertyKeys(v4, v11);
  v5 = v11[0];
  v6 = v11[1];
  while ( v5 != v6 )
  {
    v7.lpVtbl = NetSetup2::ActiveObject::GetProperty(v4, (const struct _NETSETUPPROPKEY *)v9).lpVtbl;
    NetSetup2::ObjectCreationTemplate::SetProperty(a2, v7.lpVtbl);
    std::vector<unsigned char>::_Tidy((__int64)v10);
    v5 += 20;
  }
  std::vector<_NETSETUPPROPKEY>::_Tidy(v11);
  return a2;
}

```

## disassembly

```asm
0x18001df88  mov     [rsp+arg_10], rbx
0x18001df8d  push    rbp
0x18001df8e  push    rsi
0x18001df8f  push    rdi
0x18001df90  sub     rsp, 80h
0x18001df97  mov     rax, cs:__security_cookie
0x18001df9e  xor     rax, rsp
0x18001dfa1  mov     [rsp+98h+var_20], rax
0x18001dfa6  mov     rbx, rdx
0x18001dfa9  mov     rdx, rcx
0x18001dfac  mov     [rsp+98h+var_70], rbx
0x18001dfb1  mov     [rsp+98h+var_78], 0
0x18001dfb9  xorps   xmm0, xmm0
0x18001dfbc  xor     eax, eax
0x18001dfbe  movups  xmmword ptr [rbx], xmm0
0x18001dfc1  mov     [rbx+10h], rax
0x18001dfc5  mov     rcx, rbx; this
0x18001dfc8  call    ??0ObjectCreationTemplate@NetSetup2@@QEAA@XZ; NetSetup2::ObjectCreationTemplate::ObjectCreationTemplate(void)
0x18001dfcd  mov     [rsp+98h+var_78], 1
0x18001dfd5  lea     rax, [rdx-28h]
0x18001dfd9  neg     rdx
0x18001dfdc  sbb     rsi, rsi
0x18001dfdf  and     rsi, rax
0x18001dfe2  lea     rdx, [rsp+98h+var_38]
0x18001dfe7  mov     rcx, rsi
0x18001dfea  call    ?GetPropertyKeys@ActiveObject@NetSetup2@@QEBA?AV?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@XZ; NetSetup2::ActiveObject::GetPropertyKeys(void)
0x18001dfef  nop
0x18001dff0  mov     rdi, [rsp+98h+var_38]
0x18001dff5  mov     rbp, [rsp+98h+var_30]
0x18001dffa  jmp     short loc_18001E027
0x18001dffc  mov     r8, rdi
0x18001dfff  lea     rdx, [rsp+98h+var_68]; struct _NETSETUPPROPKEY *
0x18001e004  mov     rcx, rsi; this
0x18001e007  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x18001e00c  nop
0x18001e00d  mov     rdx, rax
0x18001e010  mov     rcx, rbx
0x18001e013  call    ?SetProperty@ObjectCreationTemplate@NetSetup2@@QEAAX$$QEAVProperty@2@@Z; NetSetup2::ObjectCreationTemplate::SetProperty(NetSetup2::Property &&)
0x18001e018  nop
0x18001e019  lea     rcx, [rsp+98h+var_50]
0x18001e01e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001e023  add     rdi, 14h
0x18001e027  cmp     rdi, rbp
0x18001e02a  jnz     short loc_18001DFFC
0x18001e02c  lea     rcx, [rsp+98h+var_38]
0x18001e031  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@AEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18001e036  mov     rax, rbx
0x18001e039  mov     rcx, [rsp+98h+var_20]
0x18001e03e  xor     rcx, rsp; StackCookie
0x18001e041  call    __security_check_cookie
0x18001e046  mov     rbx, [rsp+98h+arg_10]
0x18001e04e  add     rsp, 80h
0x18001e055  pop     rdi
0x18001e056  pop     rsi
0x18001e057  pop     rbp
0x18001e058  retn
```
