# CWinreCbsClient::Initialize(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ICbsUIHandler *)

- ea: `0x18002d1f4`
- end: `0x18002d4ac`
- name: `?Initialize@CWinreCbsClient@@QEAAJPEBG0000PEAUICbsUIHandler@@@Z`
- size: `696`
- prototype: `__int64 __fastcall(CWinreCbsClient *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct ICbsUIHandler *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180022d8c`

## callees

- `0x180023620`
- `0x18002d1f4`
- `0x18003717c`
- `0x180037344`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `ServicingCommon!CbsCreateOfflineSession` at `0x18002d2cd`
- `ServicingCommon!CbsCreateOfflineSession` at `0x18002d2cd`
- `ole32!CoGetMalloc` at `0x18002d266`
- `ole32!CoGetMalloc` at `0x18002d266`

## string_xrefs

- `0x18002d3dd`: `WinREAgent`
- `0x18002d286`: `base\diagnosis\srt\winreagent\lib\operations\src\cbsclient.cpp`
- `0x18002d2ed`: `base\diagnosis\srt\winreagent\lib\operations\src\cbsclient.cpp`
- `0x18002d380`: `base\diagnosis\srt\winreagent\lib\operations\src\cbsclient.cpp`
- `0x18002d40b`: `base\diagnosis\srt\winreagent\lib\operations\src\cbsclient.cpp`
- `0x18002d460`: `base\diagnosis\srt\winreagent\lib\operations\src\cbsclient.cpp`
- `0x18002d272`: `Failed getting COM allocator`
- `0x18002d2d9`: `Failed to create offline session`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWinreCbsClient::Initialize(
        CWinreCbsClient *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  LPMALLOC *v8; // rax
  HRESULT Malloc; // ebx
  __int64 v11; // rax
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64); // rbx
  __int64 v14; // rax
  __int64 v15; // rax
  _QWORD v16[2]; // [rsp+40h] [rbp-20h] BYREF

  v16[1] = 0;
  v16[0] = &RAII::CAutoRelease<ICbsSession *>::`vftable';
  if ( a2 && a3 && a4 )
  {
    v8 = (LPMALLOC *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 4) + 8LL))((char *)this + 32);
    Malloc = CoGetMalloc(1u, v8);
    if ( Malloc >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 2) + 8LL))((char *)this + 16);
      Malloc = CbsCreateOfflineSession(a2, v11);
      if ( Malloc >= 0 )
      {
        PushButtonReset::Logging::Trace(0, L"Loaded servicing stack for offline use only.");
        v12 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 2) + 24LL))((char *)this + 16);
        v13 = **v12;
        v14 = (*(__int64 (__fastcall **)(_QWORD *))(v16[0] + 8LL))(v16);
        Malloc = v13(v12, &GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22, v14);
        if ( Malloc >= 0 )
        {
          v15 = (*(__int64 (__fastcall **)(_QWORD *))(v16[0] + 24LL))(v16);
          Malloc = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, const unsigned __int16 *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v15 + 152LL))(
                     v15,
                     0x1000000,
                     L"WinREAgent",
                     a3,
                     a4,
                     0);
          if ( Malloc < 0 )
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)Malloc,
              "CWinreCbsClient::Initialize",
              "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\cbsclient.cpp",
              43,
              L"Failed initiating PBR session");
          v16[0] = &RAII::CAutoRelease<ICbsSession *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(v16);
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Malloc,
            "CWinreCbsClient::Initialize",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\cbsclient.cpp",
            34,
            L"Failed querying ICbsSession9 interface.");
          v16[0] = &RAII::CAutoRelease<ICbsSession *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(v16);
        }
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Malloc,
          "CWinreCbsClient::Initialize",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\cbsclient.cpp",
          29,
          L"Failed to create offline session");
        v16[0] = &RAII::CAutoRelease<ICbsSession *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v16);
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Malloc,
        "CWinreCbsClient::Initialize",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\cbsclient.cpp",
        26,
        L"Failed getting COM allocator");
      v16[0] = &RAII::CAutoRelease<ICbsSession *>::`vftable';
      RAII::CAutoRelease<IXMLDOMParseError *>::Release(v16);
    }
    return (unsigned int)Malloc;
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "CWinreCbsClient::Initialize",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\cbsclient.cpp",
      22,
      L"Invalid Parameters");
    v16[0] = &RAII::CAutoRelease<ICbsSession *>::`vftable';
    RAII::CAutoRelease<IXMLDOMParseError *>::Release(v16);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18002d1f4  push    rbp
0x18002d1f6  push    rbx
0x18002d1f7  push    rsi
0x18002d1f8  push    rdi
0x18002d1f9  push    r12
0x18002d1fb  push    r14
0x18002d1fd  push    r15
0x18002d1ff  mov     rbp, rsp
0x18002d202  sub     rsp, 60h
0x18002d206  mov     rax, cs:__security_cookie
0x18002d20d  xor     rax, rsp
0x18002d210  mov     [rbp+var_10], rax
0x18002d214  mov     r15, r9
0x18002d217  mov     r14, r8
0x18002d21a  mov     rsi, rdx
0x18002d21d  mov     rdi, rcx
0x18002d220  mov     [rbp+var_18], 0
0x18002d228  lea     r12, ??_7?$CAutoRelease@PEAUICbsSession@@@RAII@@6B@; const RAII::CAutoRelease<ICbsSession *>::`vftable'
0x18002d22f  mov     [rbp+var_20], r12
0x18002d233  test    rdx, rdx
0x18002d236  jz      loc_18002D44C
0x18002d23c  test    r8, r8
0x18002d23f  jz      loc_18002D44C
0x18002d245  test    r9, r9
0x18002d248  jz      loc_18002D44C
0x18002d24e  add     rcx, 20h ; ' '
0x18002d252  mov     rax, [rcx]
0x18002d255  mov     rax, [rax+8]
0x18002d259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d25e  mov     rdx, rax; ppMalloc
0x18002d261  mov     ecx, 1; dwMemContext
0x18002d266  call    cs:__imp_CoGetMalloc
0x18002d26c  mov     ebx, eax
0x18002d26e  test    eax, eax
0x18002d270  jns     short loc_18002D2B6
0x18002d272  lea     rax, aFailedGettingC; "Failed getting COM allocator"
0x18002d279  mov     [rsp+60h+var_38], rax
0x18002d27e  mov     dword ptr [rsp+60h+var_40], 1Ah
0x18002d286  lea     r9, aBaseDiagnosisS_19; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002d28d  lea     r8, aCwinrecbsclien_3; "CWinreCbsClient::Initialize"
0x18002d294  mov     edx, ebx
0x18002d296  mov     ecx, 2
0x18002d29b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002d2a0  nop
0x18002d2a1  mov     [rbp+var_20], r12
0x18002d2a5  lea     rcx, [rbp+var_20]
0x18002d2a9  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18002d2ae  nop
0x18002d2af  mov     eax, ebx
0x18002d2b1  jmp     loc_18002D491
0x18002d2b6  mov     rax, [rdi+10h]
0x18002d2ba  lea     rcx, [rdi+10h]
0x18002d2be  mov     rax, [rax+8]
0x18002d2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2c7  mov     rdx, rax
0x18002d2ca  mov     rcx, rsi
0x18002d2cd  call    cs:__imp_CbsCreateOfflineSession
0x18002d2d3  mov     ebx, eax
0x18002d2d5  test    eax, eax
0x18002d2d7  jns     short loc_18002D318
0x18002d2d9  lea     rax, aFailedToCreate_18; "Failed to create offline session"
0x18002d2e0  mov     [rsp+60h+var_38], rax
0x18002d2e5  mov     dword ptr [rsp+60h+var_40], 1Dh
0x18002d2ed  lea     r9, aBaseDiagnosisS_19; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002d2f4  lea     r8, aCwinrecbsclien_3; "CWinreCbsClient::Initialize"
0x18002d2fb  mov     edx, ebx
0x18002d2fd  mov     ecx, 2
0x18002d302  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002d307  nop
0x18002d308  mov     [rbp+var_20], r12
0x18002d30c  lea     rcx, [rbp+var_20]
0x18002d310  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18002d315  nop
0x18002d316  jmp     short loc_18002D2AF
0x18002d318  lea     rdx, aLoadedServicin; "Loaded servicing stack for offline use "...
0x18002d31f  xor     ecx, ecx
0x18002d321  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002d326  mov     rax, [rdi+10h]
0x18002d32a  lea     rcx, [rdi+10h]
0x18002d32e  mov     rax, [rax+18h]
0x18002d332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d337  mov     rdi, rax
0x18002d33a  mov     rcx, [rax]
0x18002d33d  mov     rbx, [rcx]
0x18002d340  mov     rcx, [rbp+var_20]
0x18002d344  mov     rax, [rcx+8]
0x18002d348  lea     rcx, [rbp+var_20]
0x18002d34c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d351  mov     r8, rax
0x18002d354  lea     rdx, _GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22
0x18002d35b  mov     rcx, rdi
0x18002d35e  mov     rax, rbx
0x18002d361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d366  mov     ebx, eax
0x18002d368  test    eax, eax
0x18002d36a  jns     short loc_18002D3AE
0x18002d36c  lea     rax, aFailedQuerying; "Failed querying ICbsSession9 interface."
0x18002d373  mov     [rsp+60h+var_38], rax
0x18002d378  mov     dword ptr [rsp+60h+var_40], 22h ; '"'
0x18002d380  lea     r9, aBaseDiagnosisS_19; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002d387  lea     r8, aCwinrecbsclien_3; "CWinreCbsClient::Initialize"
0x18002d38e  mov     edx, ebx
0x18002d390  mov     ecx, 2
0x18002d395  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002d39a  nop
0x18002d39b  mov     [rbp+var_20], r12
0x18002d39f  lea     rcx, [rbp+var_20]
0x18002d3a3  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18002d3a8  nop
0x18002d3a9  jmp     loc_18002D2AF
0x18002d3ae  mov     rax, [rbp+var_20]
0x18002d3b2  lea     rcx, [rbp+var_20]
0x18002d3b6  mov     rax, [rax+18h]
0x18002d3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3bf  mov     r10, rax
0x18002d3c2  mov     rcx, [rax]
0x18002d3c5  mov     rax, [rcx+98h]
0x18002d3cc  mov     [rsp+60h+var_38], 0
0x18002d3d5  mov     [rsp+60h+var_40], r15
0x18002d3da  mov     r9, r14
0x18002d3dd  lea     r8, aWinreagent; "WinREAgent"
0x18002d3e4  mov     edx, 1000000h
0x18002d3e9  mov     rcx, r10
0x18002d3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3f1  mov     ebx, eax
0x18002d3f3  test    eax, eax
0x18002d3f5  jns     short loc_18002D439
0x18002d3f7  lea     rax, aFailedInitiati; "Failed initiating PBR session"
0x18002d3fe  mov     [rsp+60h+var_38], rax
0x18002d403  mov     dword ptr [rsp+60h+var_40], 2Bh ; '+'
0x18002d40b  lea     r9, aBaseDiagnosisS_19; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002d412  lea     r8, aCwinrecbsclien_3; "CWinreCbsClient::Initialize"
0x18002d419  mov     edx, ebx
0x18002d41b  mov     ecx, 2
0x18002d420  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002d425  nop
0x18002d426  mov     [rbp+var_20], r12
0x18002d42a  lea     rcx, [rbp+var_20]
0x18002d42e  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18002d433  nop
0x18002d434  jmp     loc_18002D2AF
0x18002d439  mov     [rbp+var_20], r12
0x18002d43d  lea     rcx, [rbp+var_20]
0x18002d441  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18002d446  nop
0x18002d447  jmp     loc_18002D2AF
0x18002d44c  lea     rax, aInvalidParamet; "Invalid Parameters"
0x18002d453  mov     [rsp+60h+var_38], rax
0x18002d458  mov     dword ptr [rsp+60h+var_40], 16h
0x18002d460  lea     r9, aBaseDiagnosisS_19; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002d467  lea     r8, aCwinrecbsclien_3; "CWinreCbsClient::Initialize"
0x18002d46e  mov     edx, 80070057h
0x18002d473  mov     ecx, 2
0x18002d478  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002d47d  nop
0x18002d47e  mov     [rbp+var_20], r12
0x18002d482  lea     rcx, [rbp+var_20]
0x18002d486  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18002d48b  nop
0x18002d48c  mov     eax, 80070057h
0x18002d491  mov     rcx, [rbp+var_10]
0x18002d495  xor     rcx, rsp; StackCookie
0x18002d498  call    __security_check_cookie
0x18002d49d  add     rsp, 60h
0x18002d4a1  pop     r15
0x18002d4a3  pop     r14
0x18002d4a5  pop     r12
0x18002d4a7  pop     rdi
0x18002d4a8  pop     rsi
0x18002d4a9  pop     rbx
0x18002d4aa  pop     rbp
0x18002d4ab  retn
```
