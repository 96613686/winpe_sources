# CBrowserBrokerInstance::RunExtExportToGenerateQihoo360SEFavoritesTempFile(ushort const *,_GUID)

- ea: `0x18000c640`
- end: `0x18000c8a7`
- name: `?RunExtExportToGenerateQihoo360SEFavoritesTempFile@CBrowserBrokerInstance@@UEAAJPEBGU_GUID@@@Z`
- size: `615`
- prototype: `__int64 __fastcall(CBrowserBrokerInstance *__hidden this, const unsigned __int16 *, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x18000c640`
- `0x18000d1c0`
- `0x18000e428`
- `0x18001ed58`
- `0x18001ef24`
- `0x1800245ec`
- `0x18002b4e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c85b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c866`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c85b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c866`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c712`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c712`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c81d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c81d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c83a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c86e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c83a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c86e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000c809`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000c809`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000c6c3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000c6c3`

## string_xrefs

- `0x18000c718`: `"%s" "%s" "%s" "%s" JSON 360SE "%s"`

## pseudocode

```c
__int64 __fastcall CBrowserBrokerInstance::RunExtExportToGenerateQihoo360SEFavoritesTempFile(
        CBrowserBrokerInstance *this,
        const unsigned __int16 *a2,
        struct _GUID *a3)
{
  __int64 v5; // rdx
  int PIC; // ebx
  DWORD v7; // eax
  signed int LastError; // eax
  signed int v9; // eax
  unsigned int v11; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v14[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v15; // [rsp+F0h] [rbp-10h]
  __int128 v16; // [rsp+100h] [rbp+0h]
  __int128 v17; // [rsp+110h] [rbp+10h]
  __int64 v18; // [rsp+120h] [rbp+20h]
  OLECHAR sz[128]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR pszPath[264]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v21[264]; // [rsp+440h] [rbp+340h] BYREF
  WCHAR v22[264]; // [rsp+650h] [rbp+550h] BYREF
  WCHAR CommandLine[1336]; // [rsp+860h] [rbp+760h] BYREF

  v11 = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, &v11);
  if ( PIC >= 0 )
  {
    if ( !GetIEPathFromCsidlW(pszPath, v5, 42, 0) )
      goto LABEL_16;
    PIC = PathCchAppend(pszPath, 0x104u, L"ExtExport.exe");
    if ( PIC < 0 )
      return (unsigned int)PIC;
    PIC = GetQihoo360SESqliteDllPath(v22);
    if ( PIC < 0 )
      return (unsigned int)PIC;
    PIC = GetQihoo360SEBookmarksFilePath(v21);
    if ( PIC < 0 )
      return (unsigned int)PIC;
    sz[0] = 0;
    StringFromGUID2(a3, sz, 128);
    *(_OWORD *)v14 = *(_OWORD *)L"\"%s\" \"%s\" \"%s\" \"%s\" JSON 360SE \"%s\"";
    v16 = *(_OWORD *)L"%s\" JSON 360SE \"%s\"";
    v15 = *(_OWORD *)L"\" \"%s\" \"%s\" JSON 360SE \"%s\"";
    v18 = *(_QWORD *)L"%s\"";
    v17 = *(_OWORD *)L" 360SE \"%s\"";
    PIC = StringCchPrintfW(CommandLine, 0x538u, v14, pszPath, v22, v21, a2, sz);
    if ( PIC < 0 )
      return (unsigned int)PIC;
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( CreateProcessW(0, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      v7 = WaitForSingleObject(ProcessInformation.hProcess, 0x3A98u);
      if ( v7 )
      {
        if ( v7 == 258 )
        {
          PIC = -2147418113;
        }
        else if ( v7 == -1 )
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
LABEL_16:
      v9 = GetLastError();
      PIC = v9;
      if ( v9 > 0 )
        return (unsigned __int16)v9 | 0x80070000;
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x18000c640  mov     [rsp-8+arg_0], rbx
0x18000c645  push    rbp
0x18000c646  push    rsi
0x18000c647  push    rdi
0x18000c648  lea     rbp, [rsp-11E0h]
0x18000c650  mov     eax, 12E0h
0x18000c655  call    _alloca_probe
0x18000c65a  sub     rsp, rax
0x18000c65d  mov     rax, cs:__security_cookie
0x18000c664  xor     rax, rsp
0x18000c667  mov     [rbp+11F0h+var_20], rax
0x18000c66e  mov     rdi, rdx
0x18000c671  mov     [rsp+12F0h+var_12A0], 0
0x18000c679  lea     rdx, [rsp+12F0h+var_12A0]; unsigned int *
0x18000c67e  mov     ecx, 1; unsigned int
0x18000c683  mov     rsi, r8
0x18000c686  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x18000c68b  mov     ebx, eax
0x18000c68d  test    eax, eax
0x18000c68f  js      loc_18000C883
0x18000c695  xor     r9d, r9d; bool
0x18000c698  lea     rcx, [rbp+11F0h+pszPath]; unsigned __int16 *
0x18000c69f  lea     r8d, [r9+2Ah]; unsigned int
0x18000c6a3  call    ?GetIEPathFromCsidlW@@YA_NPEAGKK_N@Z; GetIEPathFromCsidlW(ushort *,ulong,ulong,bool)
0x18000c6a8  test    al, al
0x18000c6aa  jz      loc_18000C86E
0x18000c6b0  lea     r8, pszMore; "ExtExport.exe"
0x18000c6b7  mov     edx, 104h; cchPath
0x18000c6bc  lea     rcx, [rbp+11F0h+pszPath]; pszPath
0x18000c6c3  call    cs:__imp_PathCchAppend
0x18000c6c9  mov     ebx, eax
0x18000c6cb  test    eax, eax
0x18000c6cd  js      loc_18000C883
0x18000c6d3  lea     rcx, [rbp+11F0h+var_CA0]; pszPath
0x18000c6da  call    ?GetQihoo360SESqliteDllPath@@YAJPEAGK@Z; GetQihoo360SESqliteDllPath(ushort *,ulong)
0x18000c6df  mov     ebx, eax
0x18000c6e1  test    eax, eax
0x18000c6e3  js      loc_18000C883
0x18000c6e9  lea     rcx, [rbp+11F0h+var_EB0]; unsigned __int16 *
0x18000c6f0  call    ?GetQihoo360SEBookmarksFilePath@@YAJPEAGK@Z; GetQihoo360SEBookmarksFilePath(ushort *,ulong)
0x18000c6f5  mov     ebx, eax
0x18000c6f7  test    eax, eax
0x18000c6f9  js      loc_18000C883
0x18000c6ff  xor     eax, eax
0x18000c701  lea     rdx, [rbp+11F0h+sz]; lpsz
0x18000c705  mov     r8d, 80h; cchMax
0x18000c70b  mov     [rbp+11F0h+sz], ax
0x18000c70f  mov     rcx, rsi; rguid
0x18000c712  call    cs:__imp_StringFromGUID2
0x18000c718  movaps  xmm0, xmmword ptr cs:aSSSSJson360seS; "\"%s\" \"%s\" \"%s\" \"%s\" JSON 360SE "...
0x18000c71f  lea     rax, [rbp+11F0h+sz]
0x18000c723  movaps  xmm1, xmmword ptr cs:aSSSSJson360seS+10h; "\" \"%s\" \"%s\" JSON 360SE \"%s\""
0x18000c72a  lea     r9, [rbp+11F0h+pszPath]
0x18000c731  mov     [rsp+12F0h+lpCurrentDirectory], rax
0x18000c736  lea     r8, [rbp+11F0h+var_1210]; unsigned __int16 *
0x18000c73a  movaps  xmmword ptr [rbp+11F0h+var_1210], xmm0
0x18000c73e  lea     rax, [rbp+11F0h+var_EB0]
0x18000c745  movaps  xmm0, xmmword ptr cs:aSSSSJson360seS+20h; "%s\" JSON 360SE \"%s\""
0x18000c74c  lea     rcx, [rbp+11F0h+CommandLine]; unsigned __int16 *
0x18000c753  mov     [rsp+12F0h+lpEnvironment], rdi
0x18000c758  mov     edx, 538h; unsigned __int64
0x18000c75d  mov     qword ptr [rsp+12F0h+dwCreationFlags], rax
0x18000c762  lea     rax, [rbp+11F0h+var_CA0]
0x18000c769  movaps  [rbp+11F0h+var_11F0], xmm0
0x18000c76d  movsd   xmm0, qword ptr cs:aSSSSJson360seS+40h; "%s\""
0x18000c775  movaps  [rbp+11F0h+var_1200], xmm1
0x18000c779  movaps  xmm1, xmmword ptr cs:aSSSSJson360seS+30h; " 360SE \"%s\""
0x18000c780  movsd   [rbp+11F0h+var_11D0], xmm0
0x18000c785  mov     qword ptr [rsp+12F0h+bInheritHandles], rax
0x18000c78a  movaps  [rbp+11F0h+var_11E0], xmm1
0x18000c78e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c793  mov     ebx, eax
0x18000c795  test    eax, eax
0x18000c797  js      loc_18000C883
0x18000c79d  xor     edx, edx; Val
0x18000c79f  lea     rcx, [rsp+12F0h+StartupInfo+4]; void *
0x18000c7a4  lea     r8d, [rdx+64h]; Size
0x18000c7a8  call    memset_0
0x18000c7ad  xor     eax, eax
0x18000c7af  mov     [rsp+12F0h+StartupInfo.cb], 68h ; 'h'
0x18000c7b7  mov     qword ptr [rsp+12F0h+ProcessInformation.dwProcessId], rax
0x18000c7bc  lea     rdx, [rbp+11F0h+CommandLine]; lpCommandLine
0x18000c7c3  lea     rax, [rsp+12F0h+ProcessInformation]
0x18000c7c8  xorps   xmm0, xmm0
0x18000c7cb  mov     [rsp+12F0h+lpProcessInformation], rax; lpProcessInformation
0x18000c7d0  xor     r9d, r9d; lpThreadAttributes
0x18000c7d3  lea     rax, [rsp+12F0h+StartupInfo]
0x18000c7d8  xor     r8d, r8d; lpProcessAttributes
0x18000c7db  mov     [rsp+12F0h+lpStartupInfo], rax; lpStartupInfo
0x18000c7e0  xor     ecx, ecx; lpApplicationName
0x18000c7e2  mov     [rsp+12F0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18000c7eb  mov     [rsp+12F0h+lpEnvironment], 0; lpEnvironment
0x18000c7f4  mov     [rsp+12F0h+dwCreationFlags], 0; dwCreationFlags
0x18000c7fc  mov     [rsp+12F0h+bInheritHandles], 0; bInheritHandles
0x18000c804  movups  xmmword ptr [rsp+12F0h+ProcessInformation.hProcess], xmm0
0x18000c809  call    cs:__imp_CreateProcessW
0x18000c80f  test    eax, eax
0x18000c811  jz      short loc_18000C86E
0x18000c813  mov     rcx, [rsp+12F0h+ProcessInformation.hProcess]; hHandle
0x18000c818  mov     edx, 3A98h; dwMilliseconds
0x18000c81d  call    cs:__imp_WaitForSingleObject
0x18000c823  test    eax, eax
0x18000c825  jz      short loc_18000C856
0x18000c827  cmp     eax, 102h
0x18000c82c  jnz     short loc_18000C835
0x18000c82e  mov     ebx, 8000FFFFh
0x18000c833  jmp     short loc_18000C856
0x18000c835  cmp     eax, 0FFFFFFFFh
0x18000c838  jnz     short loc_18000C851
0x18000c83a  call    cs:__imp_GetLastError
0x18000c840  mov     ebx, eax
0x18000c842  test    eax, eax
0x18000c844  jle     short loc_18000C856
0x18000c846  movzx   ebx, ax
0x18000c849  or      ebx, 80070000h
0x18000c84f  jmp     short loc_18000C856
0x18000c851  mov     ebx, 80004005h
0x18000c856  mov     rcx, [rsp+12F0h+ProcessInformation.hProcess]; hObject
0x18000c85b  call    cs:__imp_CloseHandle
0x18000c861  mov     rcx, [rsp+12F0h+ProcessInformation.hThread]; hObject
0x18000c866  call    cs:__imp_CloseHandle
0x18000c86c  jmp     short loc_18000C883
0x18000c86e  call    cs:__imp_GetLastError
0x18000c874  mov     ebx, eax
0x18000c876  test    eax, eax
0x18000c878  jle     short loc_18000C883
0x18000c87a  movzx   ebx, ax
0x18000c87d  or      ebx, 80070000h
0x18000c883  mov     eax, ebx
0x18000c885  mov     rcx, [rbp+11F0h+var_20]
0x18000c88c  xor     rcx, rsp; StackCookie
0x18000c88f  call    __security_check_cookie
0x18000c894  mov     rbx, [rsp+12F0h+arg_0]
0x18000c89c  add     rsp, 12E0h
0x18000c8a3  pop     rdi
0x18000c8a4  pop     rsi
0x18000c8a5  pop     rbp
0x18000c8a6  retn
```
