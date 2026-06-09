# CExecResizeConsole

- ea: `0x14000eed0`
- end: `0x14000effd`
- name: `CExecResizeConsole`
- size: `301`
- prototype: `__int64 __fastcall(__int64, __int64, __int16, __int16)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002310`
- `0x140006684`
- `0x140007960`
- `0x14000becc`
- `0x14000eed0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x14000ef2d`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x14000ef2d`

## string_xrefs

- `0x14000ef5b`: `onecore\vm\compute\service\cexec\service\cexecrequestserver.cpp`

## pseudocode

```c
__int64 __fastcall CExecResizeConsole(__int64 a1, __int64 a2, __int16 a3, __int16 a4)
{
  int v4; // eax
  unsigned int v5; // edi
  unsigned int v6; // ebx
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-19h] BYREF
  unsigned __int16 v9[4]; // [rsp+48h] [rbp-9h] BYREF
  const char *v10; // [rsp+50h] [rbp-1h]
  __int64 v11; // [rsp+58h] [rbp+7h]
  __int16 v12; // [rsp+60h] [rbp+Fh]
  _QWORD v13[4]; // [rsp+68h] [rbp+17h] BYREF
  _UNKNOWN *retaddr; // [rsp+B0h] [rbp+5Fh]
  int v15; // [rsp+C0h] [rbp+6Fh] BYREF
  __int16 v16; // [rsp+C8h] [rbp+77h] BYREF
  __int16 v17; // [rsp+D0h] [rbp+7Fh] BYREF

  v17 = a4;
  v16 = a3;
  v15 = a2;
  if ( g_VmlEtwTrace )
  {
    *(_QWORD *)&UserData.Size = 4;
    UserData.Ptr = (ULONGLONG)&v15;
    EventWrite(*((_QWORD *)g_VmlEtwTrace + 2), &MSCEXEC_RESIZE_CONSOLE, 1u, &UserData);
  }
  v13[0] = &v15;
  v13[1] = &v16;
  v13[2] = &v17;
  *(_QWORD *)v9 = retaddr;
  v10 = "onecore\\vm\\compute\\service\\cexec\\service\\cexecrequestserver.cpp";
  v12 = 141;
  UserData.Ptr = (ULONGLONG)&wil::details::functor_wrapper_void<_lambda_6a5b27d922d464155885d682f87c2665_>::`vftable';
  *(_QWORD *)&UserData.Size = v13;
  v11 = 0;
  v4 = wil::details::ResultFromException(v9, a2, &UserData);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = v4 & 0xEFFFFFFF;
    _snwprintf_s<16>(v13, 16, L"%%%%%u", v4 & 0xEFFFFFFF);
    _snwprintf_s<16>(v9, 16, L"0x%08X", v6);
    VmEventWrite<unsigned short (&)[16],unsigned short (&)[16]>(&MSCEXEC_RESIZE_CONSOLE_FAILED, v9);
  }
  return v5;
}

```

## disassembly

```asm
0x14000eed0  mov     rax, rsp
0x14000eed3  mov     [rax+20h], r9w
0x14000eed8  mov     [rax+18h], r8w
0x14000eedd  mov     [rax+10h], edx
0x14000eee0  push    rbp
0x14000eee1  push    rbx
0x14000eee2  push    rdi
0x14000eee3  lea     rbp, [rax-5Fh]
0x14000eee7  sub     rsp, 90h
0x14000eeee  mov     rax, cs:__security_cookie
0x14000eef5  xor     rax, rsp
0x14000eef8  mov     [rbp+57h+var_20], rax
0x14000eefc  mov     rcx, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x14000ef03  test    rcx, rcx
0x14000ef06  jz      short loc_14000EF33
0x14000ef08  lea     rax, [rbp+57h+arg_8]
0x14000ef0c  mov     qword ptr [rbp+57h+UserData.Size], 4
0x14000ef14  mov     [rbp+57h+UserData.Ptr], rax
0x14000ef18  lea     r9, [rbp+57h+UserData]; UserData
0x14000ef1c  mov     rcx, [rcx+10h]; RegHandle
0x14000ef20  lea     rdx, MSCEXEC_RESIZE_CONSOLE; EventDescriptor
0x14000ef27  mov     r8d, 1; UserDataCount
0x14000ef2d  call    cs:__imp_EventWrite
0x14000ef33  lea     rax, [rbp+57h+arg_8]
0x14000ef37  mov     [rbp+57h+var_40], rax
0x14000ef3b  lea     r8, [rbp+57h+UserData]
0x14000ef3f  lea     rax, [rbp+57h+arg_10]
0x14000ef43  mov     [rbp+57h+var_38], rax
0x14000ef47  lea     rcx, [rbp+57h+var_60]
0x14000ef4b  lea     rax, [rbp+57h+arg_18]
0x14000ef4f  mov     [rbp+57h+var_30], rax
0x14000ef53  mov     rax, [rbp+5Fh]
0x14000ef57  mov     qword ptr [rbp+57h+var_60], rax
0x14000ef5b  lea     rax, aOnecoreVmCompu_0; "onecore\\vm\\compute\\service\\cexec\\s"...
0x14000ef62  mov     [rbp+57h+var_58], rax
0x14000ef66  mov     eax, 8Dh
0x14000ef6b  mov     [rbp+57h+var_48], ax
0x14000ef6f  lea     rax, ??_7?$functor_wrapper_void@V_lambda_6a5b27d922d464155885d682f87c2665_@@@details@wil@@6B@; const wil::details::functor_wrapper_void<_lambda_6a5b27d922d464155885d682f87c2665_>::`vftable'
0x14000ef76  mov     [rbp+57h+UserData.Ptr], rax
0x14000ef7a  lea     rax, [rbp+57h+var_40]
0x14000ef7e  mov     qword ptr [rbp+57h+UserData.Size], rax
0x14000ef82  mov     [rbp+57h+var_50], 0
0x14000ef8a  call    ?ResultFromException@details@wil@@YAJAEBUDiagnosticsInfo@2@W4SupportedExceptions@2@AEAUIFunctor@12@@Z; wil::details::ResultFromException(wil::DiagnosticsInfo const &,wil::SupportedExceptions,wil::details::IFunctor &)
0x14000ef8f  mov     edi, eax
0x14000ef91  test    eax, eax
0x14000ef93  jns     short loc_14000EFE4
0x14000ef95  mov     ebx, eax
0x14000ef97  lea     r8, aU; "%%%%%u"
0x14000ef9e  btr     ebx, 1Ch
0x14000efa2  lea     rcx, [rbp+57h+var_40]
0x14000efa6  mov     r9d, ebx
0x14000efa9  mov     edx, 10h
0x14000efae  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x14000efb3  mov     r9d, ebx
0x14000efb6  lea     r8, a0x08x; "0x%08X"
0x14000efbd  mov     edx, 10h
0x14000efc2  lea     rcx, [rbp+57h+var_60]
0x14000efc6  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x14000efcb  lea     rax, [rbp+57h+var_60]
0x14000efcf  lea     r9, [rbp+57h+var_40]
0x14000efd3  mov     [rsp+20h], rax; unsigned __int16 *
0x14000efd8  lea     rcx, MSCEXEC_RESIZE_CONSOLE_FAILED; EventDescriptor
0x14000efdf  call    ??$VmEventWrite@AEAY0BA@GAEAY0BA@G@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@AEAY0BA@G2@Z; VmEventWrite<ushort (&)[16],ushort (&)[16]>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort (&)[16],ushort (&)[16])
0x14000efe4  mov     eax, edi
0x14000efe6  mov     rcx, [rbp+57h+var_20]
0x14000efea  xor     rcx, rsp; StackCookie
0x14000efed  call    __security_check_cookie
0x14000eff2  add     rsp, 90h
0x14000eff9  pop     rdi
0x14000effa  pop     rbx
0x14000effb  pop     rbp
0x14000effc  retn
```
