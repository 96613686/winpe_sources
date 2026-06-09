# ImportBroker::PerformImport(ushort const *,ushort const *,ushort const *,_GUID)

- ea: `0x18002aae8`
- end: `0x18002acff`
- name: `?PerformImport@ImportBroker@@AEAAJPEBG00U_GUID@@@Z`
- size: `535`
- prototype: `__int64 __fastcall(ImportBroker *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, GUID *rguid)`
- caller_count: `4`
- callee_count: `5`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18002a9f0`
- `0x18002aa30`
- `0x18002aa70`
- `0x18002aab0`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x18000d1c0`
- `0x18000e428`
- `0x18002aae8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002acaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002acba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002acaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002acba`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002ab8c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002ab8c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002ac71`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002ac71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acc2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002ac5d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002ac5d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002ab6c`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002ab6c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002ab4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002ab4e`

## pseudocode

```c
__int64 __fastcall ImportBroker::PerformImport(
        ImportBroker *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        GUID *rguid)
{
  int PIC; // ebx
  DWORD v9; // eax
  signed int LastError; // eax
  signed int v11; // eax
  unsigned int v13; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v16[8]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v17[2]; // [rsp+F0h] [rbp-10h]
  WCHAR Buffer[264]; // [rsp+110h] [rbp+10h] BYREF
  OLECHAR sz[264]; // [rsp+320h] [rbp+220h] BYREF
  WCHAR CommandLine[1064]; // [rsp+530h] [rbp+430h] BYREF

  v13 = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, &v13);
  if ( PIC >= 0 )
  {
    if ( !GetSystemDirectoryW(Buffer, 0x104u) )
      goto LABEL_14;
    PIC = PathCchAppend(Buffer, 0x104u, L"BrowserExport.exe");
    if ( PIC < 0 )
      return (unsigned int)PIC;
    StringFromGUID2(rguid, sz, 260);
    *(_OWORD *)v16 = *(_OWORD *)L"\"%s\" %s %s \"%s\" \"%s\"";
    v17[0] = *(_OWORD *)L"%s \"%s\" \"%s\"";
    *(_OWORD *)((char *)v17 + 10) = *(_OWORD *)L"s\" \"%s\"";
    PIC = StringCchPrintfW(CommandLine, 0x425u, v16, Buffer, sz, a2, a3, a4);
    if ( PIC < 0 )
      return (unsigned int)PIC;
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( CreateProcessW(0, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      v9 = WaitForSingleObject(ProcessInformation.hProcess, 0x7D0u);
      if ( v9 )
      {
        if ( v9 == 258 )
        {
          PIC = -2147418113;
        }
        else if ( v9 == -1 )
        {
          LastError = GetLastError();
          PIC = LastError;
          if ( LastError > 0 )
            PIC = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          PIC = -2147467259;
        }
      }
      CloseHandle(ProcessInformation.hProcess);
      CloseHandle(ProcessInformation.hThread);
    }
    else
    {
LABEL_14:
      v11 = GetLastError();
      PIC = v11;
      if ( v11 > 0 )
        return (unsigned __int16)v11 | 0x80070000;
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x18002aae8  mov     [rsp-8+arg_0], rbx
0x18002aaed  push    rbp
0x18002aaee  push    rsi
0x18002aaef  push    rdi
0x18002aaf0  push    r14
0x18002aaf2  push    r15
0x18002aaf4  lea     rbp, [rsp-0C90h]
0x18002aafc  sub     rsp, 0D90h
0x18002ab03  mov     rax, cs:__security_cookie
0x18002ab0a  xor     rax, rsp
0x18002ab0d  mov     [rbp+0CB0h+var_30], rax
0x18002ab14  mov     r15, [rbp+0CB0h+rguid]
0x18002ab1b  mov     rdi, rdx
0x18002ab1e  lea     rdx, [rsp+0DB0h+var_D60]; unsigned int *
0x18002ab23  mov     [rsp+0DB0h+var_D60], 0
0x18002ab2b  mov     ecx, 1; unsigned int
0x18002ab30  mov     r14, r9
0x18002ab33  mov     rsi, r8
0x18002ab36  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x18002ab3b  mov     ebx, eax
0x18002ab3d  test    eax, eax
0x18002ab3f  js      loc_18002ACD7
0x18002ab45  mov     edx, 104h; uSize
0x18002ab4a  lea     rcx, [rbp+0CB0h+Buffer]; lpBuffer
0x18002ab4e  call    cs:__imp_GetSystemDirectoryW
0x18002ab54  test    eax, eax
0x18002ab56  jz      loc_18002ACC2
0x18002ab5c  lea     r8, aBrowserexportE; "BrowserExport.exe"
0x18002ab63  mov     edx, 104h; cchPath
0x18002ab68  lea     rcx, [rbp+0CB0h+Buffer]; pszPath
0x18002ab6c  call    cs:__imp_PathCchAppend
0x18002ab72  mov     ebx, eax
0x18002ab74  test    eax, eax
0x18002ab76  js      loc_18002ACD7
0x18002ab7c  mov     r8d, 104h; cchMax
0x18002ab82  lea     rdx, [rbp+0CB0h+sz]; lpsz
0x18002ab89  mov     rcx, r15; rguid
0x18002ab8c  call    cs:__imp_StringFromGUID2
0x18002ab92  movups  xmm0, xmmword ptr cs:aSSSSS_0; "\"%s\" %s %s \"%s\" \"%s\""
0x18002ab99  mov     [rsp+0DB0h+lpCurrentDirectory], r14
0x18002ab9e  lea     rax, [rbp+0CB0h+sz]
0x18002aba5  movups  xmm1, xmmword ptr cs:aSSSSS_0+10h; "%s \"%s\" \"%s\""
0x18002abac  mov     [rsp+0DB0h+lpEnvironment], rsi
0x18002abb1  lea     r9, [rbp+0CB0h+Buffer]
0x18002abb5  movups  xmmword ptr [rbp+0CB0h+var_CD0], xmm0
0x18002abb9  mov     qword ptr [rsp+0DB0h+dwCreationFlags], rdi
0x18002abbe  lea     r8, [rbp+0CB0h+var_CD0]; unsigned __int16 *
0x18002abc2  movups  xmm0, xmmword ptr cs:aSSSSS_0+1Ah; "s\" \"%s\""
0x18002abc9  mov     edx, 425h; unsigned __int64
0x18002abce  lea     rcx, [rbp+0CB0h+CommandLine]; unsigned __int16 *
0x18002abd5  movups  xmmword ptr [rbp+0CB0h+var_CC0], xmm1
0x18002abd9  mov     qword ptr [rsp+0DB0h+bInheritHandles], rax
0x18002abde  movups  xmmword ptr [rbp+0CB0h+var_CC0+0Ah], xmm0
0x18002abe2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002abe7  mov     ebx, eax
0x18002abe9  test    eax, eax
0x18002abeb  js      loc_18002ACD7
0x18002abf1  xor     edx, edx; Val
0x18002abf3  lea     rcx, [rsp+0DB0h+StartupInfo+4]; void *
0x18002abf8  lea     r8d, [rdx+64h]; Size
0x18002abfc  call    memset_0
0x18002ac01  xor     eax, eax
0x18002ac03  mov     [rsp+0DB0h+StartupInfo.cb], 68h ; 'h'
0x18002ac0b  mov     qword ptr [rsp+0DB0h+ProcessInformation.dwProcessId], rax
0x18002ac10  lea     rdx, [rbp+0CB0h+CommandLine]; lpCommandLine
0x18002ac17  lea     rax, [rsp+0DB0h+ProcessInformation]
0x18002ac1c  xorps   xmm0, xmm0
0x18002ac1f  mov     [rsp+0DB0h+lpProcessInformation], rax; lpProcessInformation
0x18002ac24  xor     r9d, r9d; lpThreadAttributes
0x18002ac27  lea     rax, [rsp+0DB0h+StartupInfo]
0x18002ac2c  xor     r8d, r8d; lpProcessAttributes
0x18002ac2f  mov     [rsp+0DB0h+lpStartupInfo], rax; lpStartupInfo
0x18002ac34  xor     ecx, ecx; lpApplicationName
0x18002ac36  mov     [rsp+0DB0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18002ac3f  mov     [rsp+0DB0h+lpEnvironment], 0; lpEnvironment
0x18002ac48  mov     [rsp+0DB0h+dwCreationFlags], 0; dwCreationFlags
0x18002ac50  mov     [rsp+0DB0h+bInheritHandles], 0; bInheritHandles
0x18002ac58  movups  xmmword ptr [rsp+0DB0h+ProcessInformation.hProcess], xmm0
0x18002ac5d  call    cs:__imp_CreateProcessW
0x18002ac63  test    eax, eax
0x18002ac65  jz      short loc_18002ACC2
0x18002ac67  mov     rcx, [rsp+0DB0h+ProcessInformation.hProcess]; hHandle
0x18002ac6c  mov     edx, 7D0h; dwMilliseconds
0x18002ac71  call    cs:__imp_WaitForSingleObject
0x18002ac77  test    eax, eax
0x18002ac79  jz      short loc_18002ACAA
0x18002ac7b  cmp     eax, 102h
0x18002ac80  jnz     short loc_18002AC89
0x18002ac82  mov     ebx, 8000FFFFh
0x18002ac87  jmp     short loc_18002ACAA
0x18002ac89  cmp     eax, 0FFFFFFFFh
0x18002ac8c  jnz     short loc_18002ACA5
0x18002ac8e  call    cs:__imp_GetLastError
0x18002ac94  mov     ebx, eax
0x18002ac96  test    eax, eax
0x18002ac98  jle     short loc_18002ACAA
0x18002ac9a  movzx   ebx, ax
0x18002ac9d  or      ebx, 80070000h
0x18002aca3  jmp     short loc_18002ACAA
0x18002aca5  mov     ebx, 80004005h
0x18002acaa  mov     rcx, [rsp+0DB0h+ProcessInformation.hProcess]; hObject
0x18002acaf  call    cs:__imp_CloseHandle
0x18002acb5  mov     rcx, [rsp+0DB0h+ProcessInformation.hThread]; hObject
0x18002acba  call    cs:__imp_CloseHandle
0x18002acc0  jmp     short loc_18002ACD7
0x18002acc2  call    cs:__imp_GetLastError
0x18002acc8  mov     ebx, eax
0x18002acca  test    eax, eax
0x18002accc  jle     short loc_18002ACD7
0x18002acce  movzx   ebx, ax
0x18002acd1  or      ebx, 80070000h
0x18002acd7  mov     eax, ebx
0x18002acd9  mov     rcx, [rbp+0CB0h+var_30]
0x18002ace0  xor     rcx, rsp; StackCookie
0x18002ace3  call    __security_check_cookie
0x18002ace8  mov     rbx, [rsp+0DB0h+arg_0]
0x18002acf0  add     rsp, 0D90h
0x18002acf7  pop     r15
0x18002acf9  pop     r14
0x18002acfb  pop     rdi
0x18002acfc  pop     rsi
0x18002acfd  pop     rbp
0x18002acfe  retn
```
