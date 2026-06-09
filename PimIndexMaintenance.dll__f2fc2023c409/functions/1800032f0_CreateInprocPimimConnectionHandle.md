# CreateInprocPimimConnectionHandle

- ea: `0x1800032f0`
- end: `0x180003460`
- name: `CreateInprocPimimConnectionHandle`
- size: `368`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180002d20`
- `0x180002da8`
- `0x180002df4`
- `0x1800032c8`
- `0x1800032f0`
- `0x180021240`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x1800033c8`
- `RPCRT4!RpcBindingCreateW` at `0x1800033c8`
- `RPCRT4!RpcBindingBind` at `0x1800033f4`
- `RPCRT4!RpcBindingBind` at `0x1800033f4`

## string_xrefs

- `0x18000334e`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\rpcsetup.cpp`
- `0x180003411`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\rpcsetup.cpp`
- `0x180003315`: `UnitTestPimimService`

## pseudocode

```c
__int64 __fastcall CreateInprocPimimConnectionHandle(RPC_BINDING_HANDLE *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // r9
  RPC_STATUS v4; // eax
  __int64 v5; // r9
  RPC_STATUS v6; // eax
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-29h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+38h] [rbp-21h] BYREF
  wchar_t pszSrc[24]; // [rsp+70h] [rbp+17h] BYREF

  wcscpy(pszSrc, L"UnitTestPiService");
  v2 = RpcSetup(pszSrc);
  if ( (v2 & 0x80000000) == 0 )
  {
    v2 = EnsureInProcServiceInitialized();
    if ( (v2 & 0x80000000) != 0 )
    {
      v3 = 31;
      goto LABEL_3;
    }
    *(_QWORD *)&Template.Version = 1;
    Template.StringEndpoint = pszSrc;
    *(_QWORD *)&Template.ProtocolSequence = 3;
    Binding = 0;
    Template.NetworkAddress = 0;
    memset(&Template.u1, 0, 24);
    tlx::auto_xxx<void *,void (*)(void *),&void _CloseBinder(void *),0>::_Delete(&Binding);
    Binding = 0;
    v4 = RpcBindingCreateW(&Template, 0, 0, &Binding);
    v2 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v2 = (unsigned __int16)v4 | 0x80070000;
      v5 = 43;
    }
    else
    {
      v6 = RpcBindingBind(0, Binding, qword_1800244C0);
      v2 = v6;
      if ( !v6 )
      {
        v2 = 0;
        *a1 = Binding;
        Binding = 0;
        goto LABEL_16;
      }
      if ( v6 > 0 )
        v2 = (unsigned __int16)v6 | 0x80070000;
      v5 = 45;
    }
    Log_HREvent(
      v2,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\rpcsetup.cpp",
      v5);
LABEL_16:
    tlx::auto_xxx<void *,void (*)(void *),&void _CloseBinder(void *),0>::_Delete(&Binding);
    return v2;
  }
  v3 = 29;
LABEL_3:
  Log_HREvent(
    v2,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\rpcsetup.cpp",
    v3);
  return v2;
}

```

## disassembly

```asm
0x1800032f0  mov     [rsp-8+arg_8], rbx
0x1800032f5  mov     [rsp-8+arg_10], rdi
0x1800032fa  push    rbp
0x1800032fb  lea     rbp, [rsp-57h]
0x180003300  sub     rsp, 0B0h
0x180003307  mov     rax, cs:__security_cookie
0x18000330e  xor     rax, rsp
0x180003311  mov     [rbp+57h+var_10], rax
0x180003315  movups  xmm0, xmmword ptr cs:aUnittestpimims; "UnitTestPimimService"
0x18000331c  mov     rdi, rcx
0x18000331f  lea     rcx, [rbp+57h+pszSrc]; pszSrc
0x180003323  movups  xmm1, xmmword ptr cs:aUnittestpimims+10h; "PimimService"
0x18000332a  movups  xmmword ptr [rbp+57h+pszSrc], xmm0
0x18000332e  movups  xmm0, xmmword ptr cs:aUnittestpimims+1Ah; "Service"
0x180003335  movups  [rbp+57h+var_30], xmm1
0x180003339  movups  [rbp+57h+var_30+0Ah], xmm0
0x18000333d  call    ?RpcSetup@@YAJPEBG@Z; RpcSetup(ushort const *)
0x180003342  mov     ebx, eax
0x180003344  test    eax, eax
0x180003346  jns     short loc_180003366
0x180003348  mov     r9d, 1Dh
0x18000334e  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180003355  mov     edx, 1
0x18000335a  mov     ecx, ebx
0x18000335c  call    Log_HREvent
0x180003361  jmp     loc_18000343D
0x180003366  call    ?EnsureInProcServiceInitialized@@YAJXZ; EnsureInProcServiceInitialized(void)
0x18000336b  mov     ebx, eax
0x18000336d  test    eax, eax
0x18000336f  jns     short loc_180003379
0x180003371  mov     r9d, 1Fh
0x180003377  jmp     short loc_18000334E
0x180003379  lea     rax, [rbp+57h+pszSrc]
0x18000337d  mov     qword ptr [rbp+57h+Template.Version], 1
0x180003385  mov     [rbp+57h+Template.StringEndpoint], rax
0x180003389  lea     rcx, [rbp+57h+Binding]
0x18000338d  xor     eax, eax
0x18000338f  mov     qword ptr [rbp+57h+Template.ProtocolSequence], 3
0x180003397  xorps   xmm0, xmm0
0x18000339a  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x18000339e  mov     [rbp+57h+Binding], rax
0x1800033a2  mov     [rbp+57h+Template.NetworkAddress], 0
0x1800033aa  movups  xmmword ptr [rbp+57h+Template.u1], xmm0
0x1800033ae  call    ?_Delete@?$auto_xxx@PEAXP6AXPEAX@Z$1?_CloseBinder@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void (*)(void *),&_CloseBinder(void *),0>::_Delete(void)
0x1800033b3  lea     r9, [rbp+57h+Binding]; Binding
0x1800033b7  mov     [rbp+57h+Binding], 0
0x1800033bf  xor     r8d, r8d; Options
0x1800033c2  lea     rcx, [rbp+57h+Template]; Template
0x1800033c6  xor     edx, edx; Security
0x1800033c8  call    cs:__imp_RpcBindingCreateW
0x1800033ce  mov     ebx, eax
0x1800033d0  test    eax, eax
0x1800033d2  jz      short loc_1800033E7
0x1800033d4  jle     short loc_1800033DF
0x1800033d6  movzx   ebx, ax
0x1800033d9  or      ebx, 80070000h
0x1800033df  mov     r9d, 2Bh ; '+'
0x1800033e5  jmp     short loc_180003411
0x1800033e7  mov     rdx, [rbp+57h+Binding]; Binding
0x1800033eb  lea     r8, qword_1800244C0; IfSpec
0x1800033f2  xor     ecx, ecx; pAsync
0x1800033f4  call    cs:__imp_RpcBindingBind
0x1800033fa  mov     ebx, eax
0x1800033fc  test    eax, eax
0x1800033fe  jz      short loc_180003423
0x180003400  jle     short loc_18000340B
0x180003402  movzx   ebx, ax
0x180003405  or      ebx, 80070000h
0x18000340b  mov     r9d, 2Dh ; '-'
0x180003411  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180003418  xor     edx, edx
0x18000341a  mov     ecx, ebx
0x18000341c  call    Log_HREvent
0x180003421  jmp     short loc_180003434
0x180003423  mov     rax, [rbp+57h+Binding]
0x180003427  xor     ebx, ebx
0x180003429  mov     [rdi], rax
0x18000342c  mov     [rbp+57h+Binding], 0
0x180003434  lea     rcx, [rbp+57h+Binding]
0x180003438  call    ?_Delete@?$auto_xxx@PEAXP6AXPEAX@Z$1?_CloseBinder@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void (*)(void *),&_CloseBinder(void *),0>::_Delete(void)
0x18000343d  mov     eax, ebx
0x18000343f  mov     rcx, [rbp+57h+var_10]
0x180003443  xor     rcx, rsp; StackCookie
0x180003446  call    __security_check_cookie
0x18000344b  lea     r11, [rsp+0B0h+var_s0]
0x180003453  mov     rbx, [r11+18h]
0x180003457  mov     rdi, [r11+20h]
0x18000345b  mov     rsp, r11
0x18000345e  pop     rbp
0x18000345f  retn
```
