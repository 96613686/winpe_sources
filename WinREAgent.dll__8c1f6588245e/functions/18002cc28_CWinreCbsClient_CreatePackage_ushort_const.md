# CWinreCbsClient::CreatePackage(ushort const *)

- ea: `0x18002cc28`
- end: `0x18002cee8`
- name: `?CreatePackage@CWinreCbsClient@@AEAAJPEBG@Z`
- size: `704`
- prototype: `int(CWinreCbsClient *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002cb84`
- `0x18002d4b4`

## callees

- `0x180023620`
- `0x18002cc28`
- `0x180037344`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002cc83`
- `KERNEL32!GetLastError` at `0x18002cc9b`
- `KERNEL32!GetLastError` at `0x18002ccdd`
- `KERNEL32!GetLastError` at `0x18002cc83`
- `KERNEL32!GetLastError` at `0x18002cc9b`
- `KERNEL32!GetLastError` at `0x18002ccdd`
- `KERNEL32!GetFileAttributesW` at `0x18002cc74`
- `KERNEL32!GetFileAttributesW` at `0x18002cc74`
- `ServicingCommon!StringsAreEqualCaseInsensitive` at `0x18002cdce`
- `ServicingCommon!StringsAreEqualCaseInsensitive` at `0x18002cdce`

## string_xrefs

- `0x18002ccc3`: `base\diagnosis\srt\winreagent\lib\operations\src\cbsclient.cpp`
- `0x18002cd6c`: `base\diagnosis\srt\winreagent\lib\operations\src\cbsclient.cpp`
- `0x18002cdfb`: `base\diagnosis\srt\winreagent\lib\operations\src\cbsclient.cpp`
- `0x18002ce89`: `base\diagnosis\srt\winreagent\lib\operations\src\cbsclient.cpp`
- `0x18002ccaf`: `Invalid parameter %ws - path not found`
- `0x18002ccca`: `CWinreCbsClient::CreatePackage`
- `0x18002cd73`: `CWinreCbsClient::CreatePackage`
- `0x18002ce02`: `CWinreCbsClient::CreatePackage`
- `0x18002ce90`: `CWinreCbsClient::CreatePackage`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWinreCbsClient::CreatePackage(CWinreCbsClient *this, const unsigned __int16 *a2)
{
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  bool v6; // sf
  signed int v7; // eax
  signed int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // esi
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, _QWORD, const unsigned __int16 *, _QWORD, __int64); // rbx
  __int64 v13; // rax
  unsigned __int64 v14; // rax
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v17)(_QWORD, GUID *, __int64); // rbx
  __int64 v18; // rax
  _QWORD v19[2]; // [rsp+40h] [rbp-20h] BYREF

  v19[1] = 0;
  v19[0] = &RAII::CAutoRelease<IUnknown *>::`vftable';
  (*(void (__fastcall **)(CWinreCbsClient *))(*(_QWORD *)this + 96LL))(this);
  FileAttributesW = GetFileAttributesW(a2);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v6 = LastError < 0;
    if ( LastError > 0 )
      v6 = 1;
    if ( v6 )
    {
      v7 = GetLastError();
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v7,
        "CWinreCbsClient::CreatePackage",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\cbsclient.cpp",
        163,
        L"Invalid parameter %ws - path not found",
        a2);
      v8 = GetLastError();
      v9 = v8;
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      goto LABEL_9;
    }
    v10 = 1;
  }
  else
  {
    v10 = 1;
    if ( (FileAttributesW & 0x10) == 0 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a2[v14] );
      if ( v14 > 4 )
      {
        if ( !(unsigned __int8)StringsAreEqualCaseInsensitive(&a2[v14 - 4], L".mum") )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            2147942487LL,
            "CWinreCbsClient::CreatePackage",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\cbsclient.cpp",
            181,
            L"Invalid package location specified %ws.  Must be a '.mum'",
            a2);
          v19[0] = &RAII::CAutoRelease<IUnknown *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(v19);
          return 2147942487LL;
        }
        v10 = 4;
      }
    }
  }
  v11 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 2) + 24LL))((char *)this + 16);
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, const unsigned __int16 *, _QWORD, __int64))(*(_QWORD *)v11 + 40LL);
  v13 = (*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 8LL))(v19);
  v9 = v12(v11, 0, v10, a2, 0, v13);
  if ( (v9 & 0x80000000) != 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      v9,
      "CWinreCbsClient::CreatePackage",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\cbsclient.cpp",
      187,
      L"Failed creating package");
    v19[0] = &RAII::CAutoRelease<IUnknown *>::`vftable';
    RAII::CAutoRelease<IXMLDOMParseError *>::Release(v19);
    return v9;
  }
  v16 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))(*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 24LL))(v19);
  v17 = **v16;
  v18 = (*(__int64 (__fastcall **)(CWinreCbsClient *))(*(_QWORD *)this + 8LL))(this);
  v9 = v17(v16, &GUID_75207393_23f2_4396_85f0_8fdb879ed0ed, v18);
  if ( (v9 & 0x80000000) != 0 )
    PushButtonReset::Logging::TraceErr(
      2,
      v9,
      "CWinreCbsClient::CreatePackage",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\cbsclient.cpp",
      191,
      L"Failed to get package iid.");
LABEL_9:
  v19[0] = &RAII::CAutoRelease<IUnknown *>::`vftable';
  RAII::CAutoRelease<IXMLDOMParseError *>::Release(v19);
  return v9;
}

```

## disassembly

```asm
0x18002cc28  mov     [rsp-38h+arg_10], rbx
0x18002cc2d  push    rbp
0x18002cc2e  push    rsi
0x18002cc2f  push    rdi
0x18002cc30  push    r12
0x18002cc32  push    r13
0x18002cc34  push    r14
0x18002cc36  push    r15
0x18002cc38  mov     rbp, rsp
0x18002cc3b  sub     rsp, 60h
0x18002cc3f  mov     rax, cs:__security_cookie
0x18002cc46  xor     rax, rsp
0x18002cc49  mov     [rbp+var_10], rax
0x18002cc4d  mov     r14, rdx
0x18002cc50  mov     r15, rcx
0x18002cc53  xor     r12d, r12d
0x18002cc56  mov     [rbp+var_18], r12
0x18002cc5a  lea     r13, ??_7?$CAutoRelease@PEAUIUnknown@@@RAII@@6B@; const RAII::CAutoRelease<IUnknown *>::`vftable'
0x18002cc61  mov     [rbp+var_20], r13
0x18002cc65  mov     rax, [rcx]
0x18002cc68  mov     rax, [rax+60h]
0x18002cc6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc71  mov     rcx, r14; lpFileName
0x18002cc74  call    cs:__imp_GetFileAttributesW
0x18002cc7a  cmp     eax, 0FFFFFFFFh
0x18002cc7d  jnz     loc_18002CD9A
0x18002cc83  call    cs:__imp_GetLastError
0x18002cc89  mov     edi, 80070000h
0x18002cc8e  test    eax, eax
0x18002cc90  jle     short loc_18002CC99
0x18002cc92  movzx   eax, ax
0x18002cc95  or      eax, edi
0x18002cc97  test    eax, eax
0x18002cc99  jns     short loc_18002CD01
0x18002cc9b  call    cs:__imp_GetLastError
0x18002cca1  test    eax, eax
0x18002cca3  jle     short loc_18002CCAA
0x18002cca5  movzx   eax, ax
0x18002cca8  or      eax, edi
0x18002ccaa  mov     [rsp+60h+var_30], r14
0x18002ccaf  lea     rcx, aInvalidParamet_0; "Invalid parameter %ws - path not found"
0x18002ccb6  mov     [rsp+60h+var_38], rcx
0x18002ccbb  mov     dword ptr [rsp+60h+var_40], 0A3h
0x18002ccc3  lea     r9, aBaseDiagnosisS_19; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002ccca  lea     r8, aCwinrecbsclien_0; "CWinreCbsClient::CreatePackage"
0x18002ccd1  mov     edx, eax
0x18002ccd3  mov     ecx, 2
0x18002ccd8  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002ccdd  call    cs:__imp_GetLastError
0x18002cce3  mov     ebx, eax
0x18002cce5  test    eax, eax
0x18002cce7  jle     short loc_18002CCEE
0x18002cce9  movzx   ebx, ax
0x18002ccec  or      ebx, edi
0x18002ccee  mov     [rbp+var_20], r13
0x18002ccf2  lea     rcx, [rbp+var_20]
0x18002ccf6  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18002ccfb  nop
0x18002ccfc  jmp     loc_18002CEC2
0x18002cd01  mov     esi, 1
0x18002cd06  lea     rcx, [r15+10h]
0x18002cd0a  mov     rax, [rcx]
0x18002cd0d  mov     rax, [rax+18h]
0x18002cd11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd16  mov     rdi, rax
0x18002cd19  mov     rcx, [rax]
0x18002cd1c  mov     rbx, [rcx+28h]
0x18002cd20  mov     rcx, [rbp+var_20]
0x18002cd24  mov     rax, [rcx+8]
0x18002cd28  lea     rcx, [rbp+var_20]
0x18002cd2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd31  mov     [rsp+60h+var_38], rax
0x18002cd36  mov     [rsp+60h+var_40], r12
0x18002cd3b  mov     r9, r14
0x18002cd3e  mov     r8d, esi
0x18002cd41  xor     edx, edx
0x18002cd43  mov     rcx, rdi
0x18002cd46  mov     rax, rbx
0x18002cd49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd4e  mov     ebx, eax
0x18002cd50  test    eax, eax
0x18002cd52  jns     loc_18002CE31
0x18002cd58  lea     rax, aFailedCreating_0; "Failed creating package"
0x18002cd5f  mov     [rsp+60h+var_38], rax
0x18002cd64  mov     dword ptr [rsp+60h+var_40], 0BBh
0x18002cd6c  lea     r9, aBaseDiagnosisS_19; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002cd73  lea     r8, aCwinrecbsclien_0; "CWinreCbsClient::CreatePackage"
0x18002cd7a  mov     edx, ebx
0x18002cd7c  mov     ecx, 2
0x18002cd81  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002cd86  nop
0x18002cd87  mov     [rbp+var_20], r13
0x18002cd8b  lea     rcx, [rbp+var_20]
0x18002cd8f  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18002cd94  nop
0x18002cd95  jmp     loc_18002CEC2
0x18002cd9a  mov     esi, 1
0x18002cd9f  test    al, 10h
0x18002cda1  jnz     loc_18002CD06
0x18002cda7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002cdab  inc     rax
0x18002cdae  cmp     [r14+rax*2], r12w
0x18002cdb3  jnz     short loc_18002CDAB
0x18002cdb5  cmp     rax, 4
0x18002cdb9  jbe     loc_18002CD06
0x18002cdbf  add     rax, 0FFFFFFFFFFFFFFFCh
0x18002cdc3  lea     rcx, [r14+rax*2]
0x18002cdc7  lea     rdx, aMum; ".mum"
0x18002cdce  call    cs:__imp_StringsAreEqualCaseInsensitive
0x18002cdd4  test    al, al
0x18002cdd6  jz      short loc_18002CDE2
0x18002cdd8  mov     esi, 4
0x18002cddd  jmp     loc_18002CD06
0x18002cde2  mov     [rsp+60h+var_30], r14
0x18002cde7  lea     rax, aInvalidPackage; "Invalid package location specified %ws."...
0x18002cdee  mov     [rsp+60h+var_38], rax
0x18002cdf3  mov     dword ptr [rsp+60h+var_40], 0B5h
0x18002cdfb  lea     r9, aBaseDiagnosisS_19; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002ce02  lea     r8, aCwinrecbsclien_0; "CWinreCbsClient::CreatePackage"
0x18002ce09  mov     edx, 80070057h
0x18002ce0e  mov     ecx, 2
0x18002ce13  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002ce18  nop
0x18002ce19  mov     [rbp+var_20], r13
0x18002ce1d  lea     rcx, [rbp+var_20]
0x18002ce21  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18002ce26  nop
0x18002ce27  mov     eax, 80070057h
0x18002ce2c  jmp     loc_18002CEC4
0x18002ce31  mov     rax, [rbp+var_20]
0x18002ce35  lea     rcx, [rbp+var_20]
0x18002ce39  mov     rax, [rax+18h]
0x18002ce3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce42  mov     rdi, rax
0x18002ce45  mov     rdx, [rax]
0x18002ce48  mov     rbx, [rdx]
0x18002ce4b  mov     rdx, [r15]
0x18002ce4e  mov     rcx, r15
0x18002ce51  mov     rax, [rdx+8]
0x18002ce55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce5a  mov     r8, rax
0x18002ce5d  lea     rdx, _GUID_75207393_23f2_4396_85f0_8fdb879ed0ed
0x18002ce64  mov     rcx, rdi
0x18002ce67  mov     rax, rbx
0x18002ce6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce6f  mov     ebx, eax
0x18002ce71  test    eax, eax
0x18002ce73  jns     short loc_18002CEB4
0x18002ce75  lea     rax, aFailedToGetPac_0; "Failed to get package iid."
0x18002ce7c  mov     [rsp+60h+var_38], rax
0x18002ce81  mov     dword ptr [rsp+60h+var_40], 0BFh
0x18002ce89  lea     r9, aBaseDiagnosisS_19; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002ce90  lea     r8, aCwinrecbsclien_0; "CWinreCbsClient::CreatePackage"
0x18002ce97  mov     edx, ebx
0x18002ce99  mov     ecx, 2
0x18002ce9e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002cea3  nop
0x18002cea4  mov     [rbp+var_20], r13
0x18002cea8  lea     rcx, [rbp+var_20]
0x18002ceac  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18002ceb1  nop
0x18002ceb2  jmp     short loc_18002CEC2
0x18002ceb4  mov     [rbp+var_20], r13
0x18002ceb8  lea     rcx, [rbp+var_20]
0x18002cebc  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18002cec1  nop
0x18002cec2  mov     eax, ebx
0x18002cec4  mov     rcx, [rbp+var_10]
0x18002cec8  xor     rcx, rsp; StackCookie
0x18002cecb  call    __security_check_cookie
0x18002ced0  mov     rbx, [rsp+60h+arg_10]
0x18002ced8  add     rsp, 60h
0x18002cedc  pop     r15
0x18002cede  pop     r14
0x18002cee0  pop     r13
0x18002cee2  pop     r12
0x18002cee4  pop     rdi
0x18002cee5  pop     rsi
0x18002cee6  pop     rbp
0x18002cee7  retn
```
