# CExecCreateProcess

- ea: `0x14000ed90`
- end: `0x14000eec7`
- name: `CExecCreateProcess`
- size: `311`
- prototype: `__int64(__int64, ...)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140002310`
- `0x140006684`
- `0x140007960`
- `0x14000becc`
- `0x14000ed90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x14000ede7`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x14000ede7`

## string_xrefs

- `0x14000ee25`: `onecore\vm\compute\service\cexec\service\cexecrequestserver.cpp`

## pseudocode

```c
__int64 CExecCreateProcess(__int64 a1, ...)
{
  __int64 v1; // rdx
  struct _VML_ETW_TRACE *v2; // rcx
  int v3; // eax
  unsigned int v4; // edi
  unsigned int v5; // ebx
  _QWORD v7[5]; // [rsp+38h] [rbp-49h] BYREF
  _QWORD *v8; // [rsp+60h] [rbp-21h] BYREF
  unsigned __int16 v9[4]; // [rsp+68h] [rbp-19h] BYREF
  const char *v10; // [rsp+70h] [rbp-11h]
  __int64 v11; // [rsp+78h] [rbp-9h]
  __int16 v12; // [rsp+80h] [rbp-1h]
  _QWORD v13[4]; // [rsp+88h] [rbp+7h] BYREF
  _UNKNOWN *retaddr; // [rsp+D0h] [rbp+4Fh]
  __int64 v15; // [rsp+E0h] [rbp+5Fh] BYREF
  va_list va; // [rsp+E0h] [rbp+5Fh]
  __int64 v17; // [rsp+E8h] [rbp+67h] BYREF
  va_list va1; // [rsp+E8h] [rbp+67h]
  __int64 v19; // [rsp+F0h] [rbp+6Fh] BYREF
  va_list va2; // [rsp+F0h] [rbp+6Fh]
  __int64 v21; // [rsp+F8h] [rbp+77h] BYREF
  va_list va3; // [rsp+F8h] [rbp+77h]
  _QWORD *v23; // [rsp+100h] [rbp+7Fh]
  va_list va4; // [rsp+108h] [rbp+87h] BYREF

  va_start(va4, a1);
  va_start(va3, a1);
  va_start(va2, a1);
  va_start(va1, a1);
  va_start(va, a1);
  v15 = va_arg(va1, _QWORD);
  v1 = v15;
  va_copy(va2, va1);
  v17 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v19 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v21 = va_arg(va4, _QWORD);
  v23 = va_arg(va4, _QWORD *);
  v2 = g_VmlEtwTrace;
  v8 = v23;
  *v23 = 0;
  if ( v2 )
    EventWrite(*((_QWORD *)v2 + 2), &MSCEXEC_RUN_COMMAND_REQUEST, 0, 0);
  va_copy((va_list)v7, va);
  v7[1] = &v8;
  va_copy((va_list)&v7[2], va1);
  va_copy((va_list)&v7[3], va2);
  va_copy((va_list)&v7[4], va3);
  *(_QWORD *)v9 = retaddr;
  v10 = "onecore\\vm\\compute\\service\\cexec\\service\\cexecrequestserver.cpp";
  v12 = 111;
  v13[0] = &wil::details::functor_wrapper_void<_lambda_40039f9a0b0a5977062229195ec08814_>::`vftable';
  v13[1] = v7;
  v11 = 0;
  v3 = wil::details::ResultFromException(v9, v1, v13);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = v3 & 0xEFFFFFFF;
    _snwprintf_s<16>(v13, 16, L"%%%%%u", v3 & 0xEFFFFFFF);
    _snwprintf_s<16>(v9, 16, L"0x%08X", v5);
    VmEventWrite<unsigned short (&)[16],unsigned short (&)[16]>(&MSCEXEC_RUN_COMMAND_FAILED, v9);
  }
  return v4;
}

```

## disassembly

```asm
0x14000ed90  mov     rax, rsp
0x14000ed93  mov     [rax+20h], r9
0x14000ed97  mov     [rax+18h], r8
0x14000ed9b  mov     [rax+10h], rdx
0x14000ed9f  push    rbp
0x14000eda0  push    rbx
0x14000eda1  push    rdi
0x14000eda2  lea     rbp, [rax-4Fh]
0x14000eda6  sub     rsp, 0B0h
0x14000edad  mov     rax, cs:__security_cookie
0x14000edb4  xor     rax, rsp
0x14000edb7  mov     [rbp+47h+var_20], rax
0x14000edbb  mov     rax, [rbp+47h+arg_28]
0x14000edbf  mov     rcx, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x14000edc6  mov     [rbp+47h+var_68], rax
0x14000edca  mov     qword ptr [rax], 0
0x14000edd1  test    rcx, rcx
0x14000edd4  jz      short loc_14000EDED
0x14000edd6  mov     rcx, [rcx+10h]; RegHandle
0x14000edda  lea     rdx, MSCEXEC_RUN_COMMAND_REQUEST; EventDescriptor
0x14000ede1  xor     r9d, r9d; UserData
0x14000ede4  xor     r8d, r8d; UserDataCount
0x14000ede7  call    cs:__imp_EventWrite
0x14000eded  lea     rax, [rbp+47h+arg_8]
0x14000edf1  mov     [rbp+47h+var_90], rax
0x14000edf5  lea     r8, [rbp+47h+var_40]
0x14000edf9  lea     rax, [rbp+47h+var_68]
0x14000edfd  mov     [rbp+47h+var_88], rax
0x14000ee01  lea     rcx, [rbp+47h+var_60]
0x14000ee05  lea     rax, [rbp+47h+arg_10]
0x14000ee09  mov     [rbp+47h+var_80], rax
0x14000ee0d  lea     rax, [rbp+47h+arg_18]
0x14000ee11  mov     [rbp+47h+var_78], rax
0x14000ee15  lea     rax, [rbp+47h+arg_20]
0x14000ee19  mov     [rbp+47h+var_70], rax
0x14000ee1d  mov     rax, [rbp+4Fh]
0x14000ee21  mov     qword ptr [rbp+47h+var_60], rax
0x14000ee25  lea     rax, aOnecoreVmCompu_0; "onecore\\vm\\compute\\service\\cexec\\s"...
0x14000ee2c  mov     [rbp+47h+var_58], rax
0x14000ee30  mov     eax, 6Fh ; 'o'
0x14000ee35  mov     [rbp+47h+var_48], ax
0x14000ee39  lea     rax, ??_7?$functor_wrapper_void@V_lambda_40039f9a0b0a5977062229195ec08814_@@@details@wil@@6B@; const wil::details::functor_wrapper_void<_lambda_40039f9a0b0a5977062229195ec08814_>::`vftable'
0x14000ee40  mov     [rbp+47h+var_40], rax
0x14000ee44  lea     rax, [rbp+47h+var_90]
0x14000ee48  mov     [rbp+47h+var_38], rax
0x14000ee4c  mov     [rbp+47h+var_50], 0
0x14000ee54  call    ?ResultFromException@details@wil@@YAJAEBUDiagnosticsInfo@2@W4SupportedExceptions@2@AEAUIFunctor@12@@Z; wil::details::ResultFromException(wil::DiagnosticsInfo const &,wil::SupportedExceptions,wil::details::IFunctor &)
0x14000ee59  mov     edi, eax
0x14000ee5b  test    eax, eax
0x14000ee5d  jns     short loc_14000EEAE
0x14000ee5f  mov     ebx, eax
0x14000ee61  lea     r8, aU; "%%%%%u"
0x14000ee68  btr     ebx, 1Ch
0x14000ee6c  lea     rcx, [rbp+47h+var_40]
0x14000ee70  mov     r9d, ebx
0x14000ee73  mov     edx, 10h
0x14000ee78  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x14000ee7d  mov     r9d, ebx
0x14000ee80  lea     r8, a0x08x; "0x%08X"
0x14000ee87  mov     edx, 10h
0x14000ee8c  lea     rcx, [rbp+47h+var_60]
0x14000ee90  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x14000ee95  lea     rax, [rbp+47h+var_60]
0x14000ee99  lea     r9, [rbp+47h+var_40]
0x14000ee9d  mov     [rsp+20h], rax; unsigned __int16 *
0x14000eea2  lea     rcx, MSCEXEC_RUN_COMMAND_FAILED; EventDescriptor
0x14000eea9  call    ??$VmEventWrite@AEAY0BA@GAEAY0BA@G@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@AEAY0BA@G2@Z; VmEventWrite<ushort (&)[16],ushort (&)[16]>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort (&)[16],ushort (&)[16])
0x14000eeae  mov     eax, edi
0x14000eeb0  mov     rcx, [rbp+47h+var_20]
0x14000eeb4  xor     rcx, rsp; StackCookie
0x14000eeb7  call    __security_check_cookie
0x14000eebc  add     rsp, 0B0h
0x14000eec3  pop     rdi
0x14000eec4  pop     rbx
0x14000eec5  pop     rbp
0x14000eec6  retn
```
