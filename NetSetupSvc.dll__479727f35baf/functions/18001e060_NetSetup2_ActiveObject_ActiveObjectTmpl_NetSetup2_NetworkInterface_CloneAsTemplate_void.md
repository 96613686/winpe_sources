# NetSetup2::ActiveObject::ActiveObjectTmpl<NetSetup2::NetworkInterface>::CloneAsTemplate(void)

- ea: `0x18001e060`
- end: `0x18001e126`
- name: `?CloneAsTemplate@?$ActiveObjectTmpl@VNetworkInterface@NetSetup2@@@ActiveObject@NetSetup2@@QEAA?AVNetworkInterfaceTemplate@3@XZ`
- size: `198`
- prototype: `NetSetup2::NetworkInterfaceTemplate *__fastcall(__int64, NetSetup2::NetworkInterfaceTemplate *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180020384`

## callees

- `0x1800027c0`
- `0x18000d974`
- `0x180019ab4`
- `0x18001d258`
- `0x18001e060`
- `0x18002c728`
- `0x18002c94c`
- `0x18002d560`

## pseudocode

```c
NetSetup2::NetworkInterfaceTemplate *__fastcall NetSetup2::ActiveObject::ActiveObjectTmpl<NetSetup2::NetworkInterface>::CloneAsTemplate(
        __int64 a1,
        NetSetup2::NetworkInterfaceTemplate *a2)
{
  __int64 v3; // rdx
  NetSetup2::ActiveObject *v4; // rsi
  __int64 v5; // rdi
  __int64 v6; // rbp
  struct Property v7; // rax
  _BYTE v9[24]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v10[24]; // [rsp+48h] [rbp-50h] BYREF
  _QWORD v11[3]; // [rsp+60h] [rbp-38h] BYREF

  NetSetup2::NetworkInterfaceTemplate::NetworkInterfaceTemplate(a2);
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
0x18001e060  mov     [rsp+arg_10], rbx
0x18001e065  push    rbp
0x18001e066  push    rsi
0x18001e067  push    rdi
0x18001e068  sub     rsp, 80h
0x18001e06f  mov     rax, cs:__security_cookie
0x18001e076  xor     rax, rsp
0x18001e079  mov     [rsp+98h+var_20], rax
0x18001e07e  mov     rbx, rdx
0x18001e081  mov     rdx, rcx
0x18001e084  mov     [rsp+98h+var_70], rbx
0x18001e089  mov     [rsp+98h+var_78], 0
0x18001e091  mov     rcx, rbx; this
0x18001e094  call    ??0NetworkInterfaceTemplate@NetSetup2@@QEAA@XZ; NetSetup2::NetworkInterfaceTemplate::NetworkInterfaceTemplate(void)
0x18001e099  mov     [rsp+98h+var_78], 1
0x18001e0a1  lea     rax, [rdx-28h]
0x18001e0a5  neg     rdx
0x18001e0a8  sbb     rsi, rsi
0x18001e0ab  and     rsi, rax
0x18001e0ae  lea     rdx, [rsp+98h+var_38]
0x18001e0b3  mov     rcx, rsi
0x18001e0b6  call    ?GetPropertyKeys@ActiveObject@NetSetup2@@QEBA?AV?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@XZ; NetSetup2::ActiveObject::GetPropertyKeys(void)
0x18001e0bb  nop
0x18001e0bc  mov     rdi, [rsp+98h+var_38]
0x18001e0c1  mov     rbp, [rsp+98h+var_30]
0x18001e0c6  jmp     short loc_18001E0F3
0x18001e0c8  mov     r8, rdi
0x18001e0cb  lea     rdx, [rsp+98h+var_68]; struct _NETSETUPPROPKEY *
0x18001e0d0  mov     rcx, rsi; this
0x18001e0d3  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x18001e0d8  nop
0x18001e0d9  mov     rdx, rax
0x18001e0dc  mov     rcx, rbx
0x18001e0df  call    ?SetProperty@ObjectCreationTemplate@NetSetup2@@QEAAX$$QEAVProperty@2@@Z; NetSetup2::ObjectCreationTemplate::SetProperty(NetSetup2::Property &&)
0x18001e0e4  nop
0x18001e0e5  lea     rcx, [rsp+98h+var_50]
0x18001e0ea  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001e0ef  add     rdi, 14h
0x18001e0f3  cmp     rdi, rbp
0x18001e0f6  jnz     short loc_18001E0C8
0x18001e0f8  lea     rcx, [rsp+98h+var_38]
0x18001e0fd  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@AEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18001e102  mov     rax, rbx
0x18001e105  mov     rcx, [rsp+98h+var_20]
0x18001e10a  xor     rcx, rsp; StackCookie
0x18001e10d  call    __security_check_cookie
0x18001e112  mov     rbx, [rsp+98h+arg_10]
0x18001e11a  add     rsp, 80h
0x18001e121  pop     rdi
0x18001e122  pop     rsi
0x18001e123  pop     rbp
0x18001e124  retn
```
