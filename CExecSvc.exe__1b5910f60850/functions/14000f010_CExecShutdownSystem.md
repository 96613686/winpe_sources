# CExecShutdownSystem

- ea: `0x14000f010`
- end: `0x14000f116`
- name: `CExecShutdownSystem`
- size: `262`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002310`
- `0x140006684`
- `0x140007960`
- `0x14000becc`
- `0x14000f010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x14000f050`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x14000f050`

## string_xrefs

- `0x14000f066`: `onecore\vm\compute\service\cexec\service\cexecrequestserver.cpp`

## pseudocode

```c
__int64 __fastcall CExecShutdownSystem(__int64 a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // edi
  unsigned int v4; // ebx
  char v6; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int16 v7[4]; // [rsp+38h] [rbp-48h] BYREF
  const char *v8; // [rsp+40h] [rbp-40h]
  __int64 v9; // [rsp+48h] [rbp-38h]
  __int16 v10; // [rsp+50h] [rbp-30h]
  _QWORD v11[4]; // [rsp+58h] [rbp-28h] BYREF
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+8h]

  if ( g_VmlEtwTrace )
    EventWrite(*((_QWORD *)g_VmlEtwTrace + 2), &MSCEXEC_SHUTDOWN, 0, 0);
  *(_QWORD *)v7 = retaddr;
  v6 = 0;
  v8 = "onecore\\vm\\compute\\service\\cexec\\service\\cexecrequestserver.cpp";
  v10 = 193;
  v11[0] = &wil::details::functor_wrapper_void<_lambda_ce3718dc83b7418c8c606f4b3eec2356_>::`vftable';
  v11[1] = &v6;
  v9 = 0;
  v2 = wil::details::ResultFromException(v7, a2, v11);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = v2 & 0xEFFFFFFF;
    _snwprintf_s<16>(v11, 16, L"%%%%%u", v2 & 0xEFFFFFFF);
    _snwprintf_s<16>(v7, 16, L"0x%08X", v4);
    VmEventWrite<unsigned short (&)[16],unsigned short (&)[16]>(&MSCEXEC_RUN_COMMAND_FAILED, v7);
  }
  return v3;
}

```

## disassembly

```asm
0x14000f010  mov     [rsp-8+arg_0], rbx
0x14000f015  mov     [rsp-8+arg_8], rdi
0x14000f01a  push    rbp
0x14000f01b  mov     rbp, rsp
0x14000f01e  sub     rsp, 80h
0x14000f025  mov     rax, cs:__security_cookie
0x14000f02c  xor     rax, rsp
0x14000f02f  mov     [rbp+var_8], rax
0x14000f033  mov     rcx, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x14000f03a  test    rcx, rcx
0x14000f03d  jz      short loc_14000F056
0x14000f03f  mov     rcx, [rcx+10h]; RegHandle
0x14000f043  lea     rdx, MSCEXEC_SHUTDOWN; EventDescriptor
0x14000f04a  xor     r9d, r9d; UserData
0x14000f04d  xor     r8d, r8d; UserDataCount
0x14000f050  call    cs:__imp_EventWrite
0x14000f056  mov     rax, [rbp+8]
0x14000f05a  lea     r8, [rbp+var_28]
0x14000f05e  mov     qword ptr [rbp+var_48], rax
0x14000f062  lea     rcx, [rbp+var_48]
0x14000f066  lea     rax, aOnecoreVmCompu_0; "onecore\\vm\\compute\\service\\cexec\\s"...
0x14000f06d  mov     [rbp+var_50], 0
0x14000f071  mov     [rbp+var_40], rax
0x14000f075  mov     eax, 0C1h
0x14000f07a  mov     [rbp+var_30], ax
0x14000f07e  lea     rax, ??_7?$functor_wrapper_void@V_lambda_ce3718dc83b7418c8c606f4b3eec2356_@@@details@wil@@6B@; const wil::details::functor_wrapper_void<_lambda_ce3718dc83b7418c8c606f4b3eec2356_>::`vftable'
0x14000f085  mov     [rbp+var_28], rax
0x14000f089  lea     rax, [rbp+var_50]
0x14000f08d  mov     [rbp+var_20], rax
0x14000f091  mov     [rbp+var_38], 0
0x14000f099  call    ?ResultFromException@details@wil@@YAJAEBUDiagnosticsInfo@2@W4SupportedExceptions@2@AEAUIFunctor@12@@Z; wil::details::ResultFromException(wil::DiagnosticsInfo const &,wil::SupportedExceptions,wil::details::IFunctor &)
0x14000f09e  mov     edi, eax
0x14000f0a0  test    eax, eax
0x14000f0a2  jns     short loc_14000F0F3
0x14000f0a4  mov     ebx, eax
0x14000f0a6  lea     r8, aU; "%%%%%u"
0x14000f0ad  btr     ebx, 1Ch
0x14000f0b1  lea     rcx, [rbp+var_28]
0x14000f0b5  mov     r9d, ebx
0x14000f0b8  mov     edx, 10h
0x14000f0bd  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x14000f0c2  mov     r9d, ebx
0x14000f0c5  lea     r8, a0x08x; "0x%08X"
0x14000f0cc  mov     edx, 10h
0x14000f0d1  lea     rcx, [rbp+var_48]
0x14000f0d5  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x14000f0da  lea     rax, [rbp+var_48]
0x14000f0de  lea     r9, [rbp+var_28]
0x14000f0e2  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x14000f0e7  lea     rcx, MSCEXEC_RUN_COMMAND_FAILED; EventDescriptor
0x14000f0ee  call    ??$VmEventWrite@AEAY0BA@GAEAY0BA@G@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@AEAY0BA@G2@Z; VmEventWrite<ushort (&)[16],ushort (&)[16]>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort (&)[16],ushort (&)[16])
0x14000f0f3  mov     eax, edi
0x14000f0f5  mov     rcx, [rbp+var_8]
0x14000f0f9  xor     rcx, rsp; StackCookie
0x14000f0fc  call    __security_check_cookie
0x14000f101  lea     r11, [rsp+80h+var_s0]
0x14000f109  mov     rbx, [r11+10h]
0x14000f10d  mov     rdi, [r11+18h]
0x14000f111  mov     rsp, r11
0x14000f114  pop     rbp
0x14000f115  retn
```
