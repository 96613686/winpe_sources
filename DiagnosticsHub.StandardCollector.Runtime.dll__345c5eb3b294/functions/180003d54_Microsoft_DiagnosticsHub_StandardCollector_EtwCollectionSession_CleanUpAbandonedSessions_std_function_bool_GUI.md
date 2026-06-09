# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSession::CleanUpAbandonedSessions(std::function<bool (_GUID const &)>)

- ea: `0x180003d54`
- end: `0x180004263`
- name: `?CleanUpAbandonedSessions@EtwCollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@SAXV?$function@$$A6A_NAEBU_GUID@@@Z@std@@@Z`
- size: `1295`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180032470`

## callees

- `0x180003d54`
- `0x18002da4c`
- `0x18003d864`
- `0x180049b50`
- `0x180049bac`
- `0x180049c18`
- `0x18004a024`
- `0x18004a080`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memset` at `0x180003e2a`
- `VCRUNTIME140!memset` at `0x180003e2a`
- `KERNEL32!SetFileInformationByHandle` at `0x180004198`
- `KERNEL32!SetFileInformationByHandle` at `0x180004198`
- `KERNEL32!CompareStringOrdinal` at `0x180004130`
- `KERNEL32!CompareStringOrdinal` at `0x180004130`
- `KERNEL32!CreateFileW` at `0x1800040eb`
- `KERNEL32!CreateFileW` at `0x1800040eb`
- `KERNEL32!TryEnterCriticalSection` at `0x180003d99`
- `KERNEL32!TryEnterCriticalSection` at `0x180003d99`
- `KERNEL32!LeaveCriticalSection` at `0x180004208`
- `KERNEL32!LeaveCriticalSection` at `0x180004208`
- `KERNEL32!CloseHandle` at `0x18000417d`
- `KERNEL32!CloseHandle` at `0x18000417d`
- `KERNEL32!GetLastError` at `0x1800041a9`
- `KERNEL32!GetLastError` at `0x1800041a9`
- `ole32!CLSIDFromString` at `0x180004013`
- `ole32!CLSIDFromString` at `0x180004013`
- `SHLWAPI!PathFindExtensionW` at `0x180004108`
- `SHLWAPI!PathFindExtensionW` at `0x180004108`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x18000425c`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x18000425c`
- `ADVAPI32!QueryAllTracesW` at `0x180003e88`
- `ADVAPI32!QueryAllTracesW` at `0x180003e88`
- `ADVAPI32!ControlTraceW` at `0x180004065`
- `ADVAPI32!ControlTraceW` at `0x180004065`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x180003f8f`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x180003f8f`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180003ef3`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180003fa5`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800040b2`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180003ef3`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180003fa5`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800040b2`

## string_xrefs

- `0x1800041b2`: `Failed to delete abandoned ETW log file. (ErrorCode:  %#08x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSession::CleanUpAbandonedSessions(
        __int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rsi
  __int64 v4; // r8
  unsigned __int64 i; // rdx
  _DWORD *v6; // rcx
  ULONG v7; // ebx
  ULONG v8; // eax
  ULONG j; // r12d
  struct _EVENT_TRACE_PROPERTIES *v10; // r15
  const WCHAR *v11; // rsi
  WCHAR *v12; // rbx
  WCHAR v13; // r13
  __int64 v14; // rcx
  ULONG v15; // eax
  WCHAR *v16; // rbx
  HANDLE FileW; // rsi
  const WCHAR *ExtensionW; // rax
  int v19; // eax
  DiagHubCommon::LogStream *v20; // rbx
  DWORD LastError; // eax
  __int64 v22; // rcx
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-60h]
  char FileInformation[4]; // [rsp+60h] [rbp-20h] BYREF
  ULONG LoggerCount; // [rsp+64h] [rbp-1Ch] BYREF
  CLSID pclsid; // [rsp+68h] [rbp-18h] BYREF

  if ( TryEnterCriticalSection(&CriticalSection) )
  {
    v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    if ( dword_180077188 > *(_DWORD *)(v3 + 4) )
    {
      Init_thread_header(&dword_180077188);
      if ( dword_180077188 == -1 )
      {
        qword_180077190 = 0;
        qword_180077190 = operator new[](0x107800u);
        atexit(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSession::CleanUpAbandonedSessions_::_2_::_dynamic_atexit_destructor_for__SessionPropertiesBuffer__);
        Init_thread_footer(&dword_180077188);
      }
    }
    memset(qword_180077190, 0, 0x107800u);
    v4 = 0;
    for ( i = 0; i < 0x800; i += 8LL )
    {
      v6 = (char *)qword_180077190 + v4;
      *(PEVENT_TRACE_PROPERTIES *)((char *)&PropertyArray + i) = (PEVENT_TRACE_PROPERTIES)((char *)qword_180077190 + v4);
      *v6 = 4216;
      (*(PEVENT_TRACE_PROPERTIES *)((char *)&PropertyArray + i))->LoggerNameOffset = 120;
      (*(PEVENT_TRACE_PROPERTIES *)((char *)&PropertyArray + i))->LogFileNameOffset = 2168;
      v4 += 4216;
    }
    v7 = 256;
    v8 = QueryAllTracesW(&PropertyArray, 0x100u, &LoggerCount);
    if ( !v8 || v8 == 234 )
    {
      if ( LoggerCount < 0x100 )
        v7 = LoggerCount;
      LoggerCount = v7;
      if ( dword_1800779A0 > *(_DWORD *)(v3 + 4) )
      {
        Init_thread_header(&dword_1800779A0);
        if ( dword_1800779A0 == -1 )
        {
          MaxCount = wcsnlen(L"DiagHubEtwSession.17", 0x400u);
          Init_thread_footer(&dword_1800779A0);
        }
      }
      if ( dword_1800779B0 > *(_DWORD *)(v3 + 4) )
      {
        Init_thread_header(&dword_1800779B0);
        if ( dword_1800779B0 == -1 )
        {
          qword_1800779B8 = MaxCount + 38;
          Init_thread_footer(&dword_1800779B0);
        }
      }
      for ( j = 0; j < LoggerCount; ++j )
      {
        v10 = *(&PropertyArray + j);
        if ( v10->LoggerNameOffset )
        {
          v11 = (const WCHAR *)((char *)v10 + v10->LoggerNameOffset);
          if ( !wcsncmp(v11, L"DiagHubEtwSession.17", MaxCount) && wcsnlen(v11, 0x400u) > qword_1800779B8 )
          {
            v12 = (WCHAR *)&v11[MaxCount];
            if ( *v12 == 46 && v12[37] == 46 )
            {
              *v12 = 123;
              v12[37] = 125;
              v13 = v12[38];
              v12[38] = 0;
              pclsid = GUID_NULL;
              if ( *v12 == 123 )
              {
                _mm_lfence();
                if ( CLSIDFromString(v12, &pclsid) >= 0 )
                {
                  v14 = *(_QWORD *)(a1 + 56);
                  if ( !v14 )
                  {
                    std::_Xbad_function_call();
                    JUMPOUT(0x180004263LL);
                  }
                  if ( !(*(unsigned __int8 (__fastcall **)(__int64, CLSID *))(*(_QWORD *)v14 + 16LL))(v14, &pclsid) )
                  {
                    _mm_lfence();
                    *v12 = 46;
                    v12[37] = 46;
                    v12[38] = v13;
                    v15 = ControlTraceW(0, v11, v10, 1u);
                    _mm_lfence();
                    if ( v15 )
                    {
                      LODWORD(dwCreationDisposition) = v15;
                      DiagHubCommon::LogStream::Write(
                        (DiagHubCommon::LogStream *)((char *)_logger + 112),
                        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
                        L"Failed to stop abandoned ETW session: %s (ErrorCode:  %#08x)",
                        v11,
                        dwCreationDisposition);
                    }
                    else
                    {
                      DiagHubCommon::LogStream::Write(
                        (DiagHubCommon::LogStream *)((char *)_logger + 56),
                        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
                        L"Stopped abandoned ETW session: %s",
                        v11);
                      if ( v10->LogFileNameOffset )
                      {
                        _mm_lfence();
                        v16 = (WCHAR *)((char *)v10 + v10->LogFileNameOffset);
                        if ( wcsnlen(v16, 0x800u) )
                        {
                          _mm_lfence();
                          FileW = CreateFileW(v16, 0x10000u, 1u, 0, 3u, 0x200000u, 0);
                          if ( FileW != (HANDLE)-1LL )
                          {
                            _mm_lfence();
                            ExtensionW = PathFindExtensionW(v16);
                            if ( ExtensionW && (_mm_lfence(), CompareStringOrdinal(ExtensionW, -1, L".etl", -1, 1) == 2) )
                            {
                              _mm_lfence();
                              v19 = Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::VerifySecured(
                                      FileW,
                                      v16);
                              _mm_lfence();
                              if ( v19 )
                              {
                                DiagHubCommon::LogStream::Write(
                                  (DiagHubCommon::LogStream *)((char *)_logger + 112),
                                  L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
                                  L"Abandonded ETW session with unsecured log file: %s",
                                  v16);
                              }
                              else
                              {
                                FileInformation[0] = 1;
                                if ( !SetFileInformationByHandle(FileW, FileDispositionInfo, FileInformation, 1u) )
                                {
                                  v20 = _logger;
                                  LastError = GetLastError();
                                  DiagHubCommon::LogStream::Write(
                                    (DiagHubCommon::LogStream *)((char *)v20 + 56),
                                    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
                                    L"Failed to delete abandoned ETW log file. (ErrorCode:  %#08x)",
                                    LastError);
                                }
                              }
                            }
                            else
                            {
                              _mm_lfence();
                              DiagHubCommon::LogStream::Write(
                                (DiagHubCommon::LogStream *)((char *)_logger + 112),
                                L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
                                L"Abandonded ETW session with unknown log file type: %s",
                                v16);
                            }
                            if ( FileW )
                            {
                              _mm_lfence();
                              CloseHandle(FileW);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 56),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
        L"Could not clean up potential abandoned ETW sessions. Failed to enumerate ETW sessions.");
    }
    LeaveCriticalSection(&CriticalSection);
  }
  v22 = *(_QWORD *)(a1 + 56);
  if ( v22 )
  {
    LOBYTE(v2) = v22 != a1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 32LL))(v22, v2);
    *(_QWORD *)(a1 + 56) = 0;
  }
}

```

## disassembly

```asm
0x180003d54  mov     [rsp-28h+arg_8], rbx
0x180003d59  mov     [rsp-28h+arg_10], rsi
0x180003d5e  mov     [rsp-28h+arg_18], rdi
0x180003d63  push    rbp
0x180003d64  push    r12
0x180003d66  push    r13
0x180003d68  push    r14
0x180003d6a  push    r15
0x180003d6c  mov     rbp, rsp
0x180003d6f  sub     rsp, 80h
0x180003d76  mov     rax, cs:__security_cookie
0x180003d7d  xor     rax, rsp
0x180003d80  mov     [rbp+var_8], rax
0x180003d84  mov     rdi, rcx
0x180003d87  mov     [rbp+var_28], rcx
0x180003d8b  lea     r15, CriticalSection
0x180003d92  mov     [rbp+var_38], r15
0x180003d96  mov     rcx, r15; lpCriticalSection
0x180003d99  call    cs:__imp_TryEnterCriticalSection
0x180003d9f  xor     r13d, r13d
0x180003da2  test    eax, eax
0x180003da4  setnz   [rbp+var_30]
0x180003da8  test    eax, eax
0x180003daa  jnz     short loc_180003DB1
0x180003dac  jmp     loc_18000420F
0x180003db1  mov     ecx, cs:_tls_index
0x180003db7  mov     rax, gs:58h
0x180003dc0  mov     r14d, 4
0x180003dc6  mov     rsi, [rax+rcx*8]
0x180003dca  mov     ebx, 107800h
0x180003dcf  mov     eax, [rsi+r14]
0x180003dd3  cmp     cs:dword_180077188, eax
0x180003dd9  jle     short loc_180003E1E
0x180003ddb  lea     rcx, dword_180077188
0x180003de2  call    _Init_thread_header
0x180003de7  cmp     cs:dword_180077188, 0FFFFFFFFh
0x180003dee  jnz     short loc_180003E1E
0x180003df0  mov     cs:qword_180077190, r13
0x180003df7  mov     ecx, ebx; unsigned __int64
0x180003df9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003dfe  mov     cs:qword_180077190, rax
0x180003e05  lea     rcx, _Microsoft__DiagnosticsHub__StandardCollector__EtwCollectionSession__CleanUpAbandonedSessions____2____dynamic_atexit_destructor_for__SessionPropertiesBuffer__; void (__cdecl *)()
0x180003e0c  call    atexit
0x180003e11  nop
0x180003e12  lea     rcx, dword_180077188
0x180003e19  call    _Init_thread_footer
0x180003e1e  mov     r8, rbx; Size
0x180003e21  xor     edx, edx; Val
0x180003e23  mov     rcx, cs:qword_180077190; void *
0x180003e2a  call    cs:__imp_memset
0x180003e30  mov     r8, r13
0x180003e33  mov     rdx, r13
0x180003e36  lea     r10, PropertyArray
0x180003e3d  mov     r9d, 1078h
0x180003e43  mov     rcx, cs:qword_180077190
0x180003e4a  add     rcx, r8
0x180003e4d  mov     [rdx+r10], rcx
0x180003e51  mov     [rcx], r9d
0x180003e54  mov     rax, [rdx+r10]
0x180003e58  mov     dword ptr [rax+74h], 78h ; 'x'
0x180003e5f  mov     rax, [rdx+r10]
0x180003e63  mov     dword ptr [rax+70h], 878h
0x180003e6a  add     rdx, 8
0x180003e6e  add     r8, r9
0x180003e71  cmp     rdx, 800h
0x180003e78  jb      short loc_180003E43
0x180003e7a  lea     r8, [rbp+LoggerCount]; LoggerCount
0x180003e7e  mov     ebx, 100h
0x180003e83  mov     edx, ebx; PropertyArrayCount
0x180003e85  mov     rcx, r10; PropertyArray
0x180003e88  call    cs:__imp_QueryAllTracesW
0x180003e8e  test    eax, eax
0x180003e90  jz      short loc_180003EBC
0x180003e92  cmp     eax, 0EAh
0x180003e97  jz      short loc_180003EBC
0x180003e99  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180003ea0  add     rcx, 38h ; '8'; this
0x180003ea4  lea     r8, aCouldNotCleanU; "Could not clean up potential abandoned "...
0x180003eab  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180003eb2  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180003eb7  jmp     loc_180004205
0x180003ebc  cmp     [rbp+LoggerCount], ebx
0x180003ebf  cmovb   ebx, [rbp+LoggerCount]
0x180003ec3  mov     [rbp+LoggerCount], ebx
0x180003ec6  mov     eax, [rsi+r14]
0x180003eca  cmp     cs:dword_1800779A0, eax
0x180003ed0  jle     short loc_180003F0C
0x180003ed2  lea     rcx, dword_1800779A0
0x180003ed9  call    _Init_thread_header
0x180003ede  cmp     cs:dword_1800779A0, 0FFFFFFFFh
0x180003ee5  jnz     short loc_180003F0C
0x180003ee7  mov     edx, 400h; MaxCount
0x180003eec  lea     rcx, aDiaghubetwsess; "DiagHubEtwSession.17"
0x180003ef3  call    cs:__imp_wcsnlen
0x180003ef9  mov     cs:MaxCount, rax
0x180003f00  lea     rcx, dword_1800779A0
0x180003f07  call    _Init_thread_footer
0x180003f0c  mov     eax, [rsi+r14]
0x180003f10  cmp     cs:dword_1800779B0, eax
0x180003f16  jle     short loc_180003F4B
0x180003f18  lea     rcx, dword_1800779B0
0x180003f1f  call    _Init_thread_header
0x180003f24  cmp     cs:dword_1800779B0, 0FFFFFFFFh
0x180003f2b  jnz     short loc_180003F4B
0x180003f2d  mov     rax, cs:MaxCount
0x180003f34  add     rax, 26h ; '&'
0x180003f38  mov     cs:qword_1800779B8, rax
0x180003f3f  lea     rcx, dword_1800779B0
0x180003f46  call    _Init_thread_footer
0x180003f4b  mov     r12d, r13d
0x180003f4e  cmp     [rbp+LoggerCount], r13d
0x180003f52  jbe     loc_180004205
0x180003f58  lea     r14, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180003f5f  lea     rcx, PropertyArray
0x180003f66  mov     eax, r12d
0x180003f69  mov     r15, [rcx+rax*8]
0x180003f6d  cmp     [r15+74h], r13d
0x180003f71  jz      loc_1800041EE
0x180003f77  mov     esi, [r15+74h]
0x180003f7b  add     rsi, r15
0x180003f7e  mov     r8, cs:MaxCount; MaxCount
0x180003f85  lea     rdx, aDiaghubetwsess; "DiagHubEtwSession.17"
0x180003f8c  mov     rcx, rsi; String1
0x180003f8f  call    cs:__imp_wcsncmp
0x180003f95  test    eax, eax
0x180003f97  jnz     loc_1800041E7
0x180003f9d  mov     edx, 400h; MaxCount
0x180003fa2  mov     rcx, rsi; Source
0x180003fa5  call    cs:__imp_wcsnlen
0x180003fab  cmp     rax, cs:qword_1800779B8
0x180003fb2  jbe     loc_1800041E7
0x180003fb8  mov     rax, cs:MaxCount
0x180003fbf  lea     rbx, [rsi+rax*2]
0x180003fc3  mov     edx, 2Eh ; '.'
0x180003fc8  cmp     [rbx], dx
0x180003fcb  jnz     loc_1800041E7
0x180003fd1  cmp     [rbx+4Ah], dx
0x180003fd5  jnz     loc_1800041E7
0x180003fdb  mov     edx, 7Bh ; '{'
0x180003fe0  mov     [rbx], dx
0x180003fe3  mov     word ptr [rbx+4Ah], 7Dh ; '}'
0x180003fe9  movzx   r13d, word ptr [rbx+4Ch]
0x180003fee  xor     ecx, ecx
0x180003ff0  mov     [rbx+4Ch], cx
0x180003ff4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180003ffb  movdqu  xmmword ptr [rbp+pclsid.Data1], xmm0
0x180004000  cmp     [rbx], dx
0x180004003  jnz     loc_1800041E7
0x180004009  lfence
0x18000400c  lea     rdx, [rbp+pclsid]; pclsid
0x180004010  mov     rcx, rbx; lpsz
0x180004013  call    cs:__imp_CLSIDFromString
0x180004019  test    eax, eax
0x18000401b  js      loc_1800041E7
0x180004021  mov     rcx, [rdi+38h]
0x180004025  test    rcx, rcx
0x180004028  jz      loc_18000425C
0x18000402e  mov     rax, [rcx]
0x180004031  lea     rdx, [rbp+pclsid]
0x180004035  mov     rax, [rax+10h]
0x180004039  call    cs:__guard_dispatch_icall_fptr
0x18000403f  xor     ecx, ecx; TraceHandle
0x180004041  test    al, al
0x180004043  jnz     loc_1800041E7
0x180004049  lfence
0x18000404c  lea     eax, [rcx+2Eh]
0x18000404f  mov     [rbx], ax
0x180004052  mov     [rbx+4Ah], ax
0x180004056  mov     [rbx+4Ch], r13w
0x18000405b  lea     r9d, [rcx+1]; ControlCode
0x18000405f  mov     r8, r15; Properties
0x180004062  mov     rdx, rsi; InstanceName
0x180004065  call    cs:__imp_ControlTraceW
0x18000406b  xor     r13d, r13d
0x18000406e  lfence
0x180004071  mov     r9, rsi
0x180004074  mov     rdx, r14; unsigned __int16 *
0x180004077  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18000407e  test    eax, eax
0x180004080  jnz     loc_1800041D3
0x180004086  add     rcx, 38h ; '8'; this
0x18000408a  lea     r8, aStoppedAbandon; "Stopped abandoned ETW session: %s"
0x180004091  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180004096  cmp     [r15+70h], r13d
0x18000409a  jz      loc_1800041E7
0x1800040a0  lfence
0x1800040a3  mov     ebx, [r15+70h]
0x1800040a7  add     rbx, r15
0x1800040aa  mov     edx, 800h; MaxCount
0x1800040af  mov     rcx, rbx; Source
0x1800040b2  call    cs:__imp_wcsnlen
0x1800040b8  test    rax, rax
0x1800040bb  jz      loc_1800041E7
0x1800040c1  lfence
0x1800040c4  mov     [rsp+80h+hTemplateFile], r13; hTemplateFile
0x1800040c9  mov     [rsp+80h+dwFlagsAndAttributes], 200000h; dwFlagsAndAttributes
0x1800040d1  mov     dword ptr [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x1800040d9  xor     r9d, r9d; lpSecurityAttributes
0x1800040dc  lea     r15d, [r13+1]
0x1800040e0  mov     r8d, r15d; dwShareMode
0x1800040e3  mov     edx, 10000h; dwDesiredAccess
0x1800040e8  mov     rcx, rbx; lpFileName
0x1800040eb  call    cs:__imp_CreateFileW
0x1800040f1  mov     rsi, rax
0x1800040f4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800040f8  jz      loc_1800041E7
0x1800040fe  lfence
0x180004101  mov     [rbp+var_40], rax
0x180004105  mov     rcx, rbx; pszPath
0x180004108  call    cs:__imp_PathFindExtensionW
0x18000410e  test    rax, rax
0x180004111  jz      loc_1800041C7
0x180004117  lfence
0x18000411a  mov     dword ptr [rsp+80h+dwCreationDisposition], r15d; bIgnoreCase
0x18000411f  or      r9d, 0FFFFFFFFh; cchCount2
0x180004123  lea     r8, aEtl; ".etl"
0x18000412a  or      edx, r9d; cchCount1
0x18000412d  mov     rcx, rax; lpString1
0x180004130  call    cs:__imp_CompareStringOrdinal
0x180004136  cmp     eax, 2
0x180004139  jnz     loc_1800041C7
0x18000413f  lfence
0x180004142  mov     rdx, rbx; String1
0x180004145  mov     rcx, rsi; hFile
0x180004148  call    ?VerifySecured@SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@SAJPEAXPEBG@Z; Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::VerifySecured(void *,ushort const *)
0x18000414d  lfence
0x180004150  test    eax, eax
0x180004152  jz      short loc_180004185
0x180004154  lea     r8, aAbandondedEtwS; "Abandonded ETW session with unsecured l"...
0x18000415b  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180004162  mov     r9, rbx
0x180004165  mov     rdx, r14; unsigned __int16 *
0x180004168  add     rcx, 70h ; 'p'; this
0x18000416c  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180004171  nop
0x180004172  test    rsi, rsi
0x180004175  jz      short loc_1800041E7
0x180004177  lfence
0x18000417a  mov     rcx, rsi; hObject
0x18000417d  call    cs:__imp_CloseHandle
0x180004183  jmp     short loc_1800041E7
0x180004185  mov     [rbp+FileInformation], r15b
0x180004189  mov     r9d, r15d; dwBufferSize
0x18000418c  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180004190  mov     edx, 4; FileInformationClass
0x180004195  mov     rcx, rsi; hFile
0x180004198  call    cs:__imp_SetFileInformationByHandle
0x18000419e  test    eax, eax
0x1800041a0  jnz     short loc_180004172
0x1800041a2  mov     rbx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800041a9  call    cs:__imp_GetLastError
0x1800041af  mov     r9d, eax
0x1800041b2  lea     r8, aFailedToDelete_0; "Failed to delete abandoned ETW log file"...
0x1800041b9  mov     rdx, r14; unsigned __int16 *
0x1800041bc  lea     rcx, [rbx+38h]; this
0x1800041c0  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800041c5  jmp     short loc_180004172
0x1800041c7  lfence
0x1800041ca  lea     r8, aAbandondedEtwS_0; "Abandonded ETW session with unknown log"...
0x1800041d1  jmp     short loc_18000415B
0x1800041d3  add     rcx, 70h ; 'p'; this
0x1800041d7  mov     dword ptr [rsp+80h+dwCreationDisposition], eax
0x1800041db  lea     r8, aFailedToStopAb; "Failed to stop abandoned ETW session: %"...
0x1800041e2  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800041e7  lea     rcx, PropertyArray
0x1800041ee  inc     r12d
0x1800041f1  xor     r13d, r13d
0x1800041f4  cmp     r12d, [rbp+LoggerCount]
0x1800041f8  jb      loc_180003F66
0x1800041fe  lea     r15, CriticalSection
0x180004205  mov     rcx, r15; lpCriticalSection
0x180004208  call    cs:__imp_LeaveCriticalSection
0x18000420e  nop
0x18000420f  mov     rcx, [rdi+38h]
0x180004213  test    rcx, rcx
0x180004216  jz      short loc_18000422F
0x180004218  cmp     rcx, rdi
0x18000421b  mov     rax, [rcx]
0x18000421e  setnz   dl
0x180004221  mov     rax, [rax+20h]
0x180004225  call    cs:__guard_dispatch_icall_fptr
0x18000422b  mov     [rdi+38h], r13
0x18000422f  mov     rcx, [rbp+var_8]
0x180004233  xor     rcx, rsp; StackCookie
0x180004236  call    __security_check_cookie
0x18000423b  lea     r11, [rsp+80h+var_s0]
0x180004243  mov     rbx, [r11+38h]
0x180004247  mov     rsi, [r11+40h]
0x18000424b  mov     rdi, [r11+48h]
0x18000424f  mov     rsp, r11
0x180004252  pop     r15
0x180004254  pop     r14
0x180004256  pop     r13
0x180004258  pop     r12
0x18000425a  pop     rbp
0x18000425b  retn
0x18000425c  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180004262  nop
```
