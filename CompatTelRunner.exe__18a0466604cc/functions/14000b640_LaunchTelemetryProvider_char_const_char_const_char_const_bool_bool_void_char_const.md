# LaunchTelemetryProvider(char const *,char const *,char const *,bool,bool,void *,char const *)

- ea: `0x14000b640`
- end: `0x14000bb41`
- name: `?LaunchTelemetryProvider@@YAJPEBD00_N1PEAX0@Z`
- size: `1281`
- prototype: `__int64 __fastcall(LPCSTR lpLibFileName, CHAR *lpProcName, const char *, __int64, bool, void *, char *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x14000c2f8`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x1400093e8`
- `0x14000b640`
- `0x14000bbf4`
- `0x14000c200`
- `0x1400151b0`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x14000b804`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x14000b804`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b8ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b904`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b919`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b92a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b8ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b904`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b919`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b92a`
- `api-ms-win-core-libraryloader-l1-2-0!SetDefaultDllDirectories` at `0x14000b720`
- `api-ms-win-core-libraryloader-l1-2-0!SetDefaultDllDirectories` at `0x14000b720`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000baca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000baca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b72a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bafa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b72a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bafa`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000b79d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000b79d`

## string_xrefs

- `0x14000b730`: `SetDefaultDllDirectories failed [%d]`
- `0x14000b748`: `%%windir%%\system32\%hs`
- `0x14000b818`: `LoadLibraryExA failed [%d]`

## pseudocode

```c
__int64 __fastcall LaunchTelemetryProvider(
        LPCSTR lpLibFileName,
        CHAR *lpProcName,
        const char *a3,
        __int64 a4,
        bool a5,
        void *a6,
        char *a7)
{
  char v9; // r13
  unsigned int v10; // esi
  DWORD LastError; // eax
  const char *v12; // r9
  __int64 v13; // r8
  int v14; // eax
  int v15; // ebx
  unsigned int v16; // eax
  HMODULE Library; // r14
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r8
  FARPROC v21; // r13
  unsigned int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  unsigned __int16 *v25; // r8
  signed int v26; // eax
  FARPROC ProcAddress; // [rsp+50h] [rbp-B0h]
  FARPROC v30; // [rsp+60h] [rbp-A0h]
  FARPROC v31; // [rsp+68h] [rbp-98h]
  _QWORD v32[3]; // [rsp+70h] [rbp-90h] BYREF
  bool v33; // [rsp+88h] [rbp-78h]
  int v34; // [rsp+89h] [rbp-77h]
  __int16 v35; // [rsp+8Dh] [rbp-73h]
  char v36; // [rsp+8Fh] [rbp-71h]
  void *v37; // [rsp+90h] [rbp-70h]
  CHAR ProcName; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v39[271]; // [rsp+A1h] [rbp-5Fh] BYREF
  CHAR v40; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v41[271]; // [rsp+1B1h] [rbp+B1h] BYREF
  CHAR v42; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v43[271]; // [rsp+2C1h] [rbp+1C1h] BYREF
  unsigned __int16 v44[128]; // [rsp+3D0h] [rbp+2D0h] BYREF
  WCHAR Src; // [rsp+4D0h] [rbp+3D0h] BYREF
  _BYTE v46[526]; // [rsp+4D2h] [rbp+3D2h] BYREF
  WCHAR Dst; // [rsp+6E0h] [rbp+5E0h] BYREF
  _BYTE v48[526]; // [rsp+6E2h] [rbp+5E2h] BYREF

  v9 = 0;
  v42 = 0;
  v10 = -2147467259;
  memset_0(v43, 0, 0x103u);
  v40 = 0;
  memset_0(v41, 0, 0x103u);
  ProcName = 0;
  memset_0(v39, 0, 0x103u);
  Src = 0;
  memset_0(v46, 0, 0x206u);
  Dst = 0;
  memset_0(v48, 0, 0x206u);
  if ( SetDefaultDllDirectories(0x800u) )
  {
    v14 = StringCchPrintfW(&Src, 0x104u, L"%%windir%%\\system32\\%hs", lpLibFileName);
    v15 = v14;
    if ( v14 < 0 )
    {
      AslLogCallPrintf(1, "LaunchTelemetryProvider", 268, "StringCchPrintfW failed [%#x]", v14);
      goto LABEL_42;
    }
    if ( ExpandEnvironmentStringsW(&Src, &Dst, 0x104u) - 1 > 0x103 )
    {
      LastError = GetLastError();
      v12 = "ExpandEnvironmentStringsW failed [%d]";
      v13 = 275;
      goto LABEL_39;
    }
    v16 = VerifyEmbeddedSignature(&Dst);
    v15 = v16;
    if ( v16 )
    {
      AslLogCallPrintf(
        1,
        "LaunchTelemetryProvider",
        283,
        "VerifyEmbeddedSignature(%hs) failed: [%d]",
        lpLibFileName,
        v16);
      if ( v15 <= 0 )
        goto LABEL_42;
      v15 = (unsigned __int16)v15;
      goto LABEL_41;
    }
    Library = LoadLibraryExA(lpLibFileName, 0, 0x800u);
    if ( !Library )
    {
      LastError = GetLastError();
      v12 = "LoadLibraryExA failed [%d]";
      v13 = 292;
      goto LABEL_39;
    }
    v18 = StringCchPrintfA(&ProcName, 0x104u, "%hs%hs", lpProcName, "TCEx");
    v15 = v18;
    if ( v18 < 0 )
    {
      v19 = 301;
LABEL_13:
      AslLogCallPrintf(1, "LaunchTelemetryProvider", v19, "StringCchPrintfA failed [%#x]", v18);
LABEL_37:
      FreeLibrary(Library);
      goto LABEL_42;
    }
    v18 = StringCchPrintfA(&v40, 0x104u, "%hs%hs", lpProcName, "TC2");
    v15 = v18;
    if ( v18 < 0 )
    {
      v19 = 308;
      goto LABEL_13;
    }
    v18 = StringCchPrintfA(&v42, 0x104u, "%hs%hs", lpProcName, "TC");
    v15 = v18;
    if ( v18 < 0 )
    {
      v19 = 315;
      goto LABEL_13;
    }
    ProcAddress = GetProcAddress(Library, &ProcName);
    v30 = GetProcAddress(Library, &v40);
    v31 = GetProcAddress(Library, &v42);
    v21 = GetProcAddress(Library, lpProcName);
    if ( ProcAddress )
    {
      lpProcName = &ProcName;
      v33 = a5;
      v34 = 0;
      v35 = 0;
      v36 = 0;
      v37 = a6;
      v32[1] = a3;
      v32[0] = 1;
      v32[2] = a7;
      v22 = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v32);
LABEL_24:
      v10 = v22;
LABEL_34:
      v9 = 1;
      AslLogCallPrintf(
        3,
        "LaunchTelemetryProvider",
        379,
        "Called export %hs!%hs returned %#x",
        lpLibFileName,
        lpProcName,
        v10);
      goto LABEL_37;
    }
    if ( v30 )
    {
      LOBYTE(v20) = a5;
      lpProcName = &v40;
      v22 = ((__int64 (__fastcall *)(const char *, _QWORD, __int64, char *))v30)(a3, 0, v20, a7);
      goto LABEL_24;
    }
    if ( v31 )
    {
      lpProcName = &v42;
      v22 = ((__int64 (__fastcall *)(const char *, _QWORD, char *))v31)(a3, 0, a7);
      goto LABEL_24;
    }
    if ( v21 )
    {
      v23 = -1;
      do
        ++v23;
      while ( lpProcName[v23] );
      if ( lpProcName[v23 - 1] == 87 )
      {
        memset_0(v44, 0, sizeof(v44));
        v24 = StringCchPrintfW(v44, 0x80u, L"%hs", a7);
        v15 = v24;
        if ( v24 < 0 )
        {
          AslLogCallPrintf(1, "LaunchTelemetryProvider", 358, "StringCchPrintfW failed [%#x]", v24);
LABEL_36:
          v9 = 0;
          goto LABEL_37;
        }
        v25 = v44;
      }
      else
      {
        v25 = (unsigned __int16 *)a7;
      }
      ((void (__fastcall *)(_QWORD, _QWORD, unsigned __int16 *, _QWORD))v21)(0, 0, v25, 0);
      v10 = 0;
      goto LABEL_34;
    }
    AslLogCallPrintf(
      1,
      "LaunchTelemetryProvider",
      372,
      "Function %hs is not exported by %hs",
      lpProcName,
      lpLibFileName);
    v15 = -2147467259;
    goto LABEL_36;
  }
  LastError = GetLastError();
  v12 = "SetDefaultDllDirectories failed [%d]";
  v13 = 253;
LABEL_39:
  AslLogCallPrintf(1, "LaunchTelemetryProvider", v13, v12, LastError);
  v26 = GetLastError();
  v15 = v26;
  if ( v26 <= 0 )
    goto LABEL_42;
  v15 = (unsigned __int16)v26;
LABEL_41:
  v15 |= 0x80070000;
LABEL_42:
  if ( !v9 )
    return (unsigned int)v15;
  return v10;
}

```

## disassembly

```asm
0x14000b640  mov     [rsp-8+arg_18], rbx
0x14000b645  push    rbp
0x14000b646  push    rsi
0x14000b647  push    rdi
0x14000b648  push    r12
0x14000b64a  push    r13
0x14000b64c  push    r14
0x14000b64e  push    r15
0x14000b650  lea     rbp, [rsp-800h]
0x14000b658  sub     rsp, 900h
0x14000b65f  mov     rax, cs:__security_cookie
0x14000b666  xor     rax, rsp
0x14000b669  mov     [rbp+830h+var_40], rax
0x14000b670  mov     rax, [rbp+830h+arg_28]
0x14000b677  mov     rdi, rdx
0x14000b67a  mov     r12, [rbp+830h+arg_30]
0x14000b681  mov     r15, rcx
0x14000b684  mov     [rsp+930h+var_8E8], r8
0x14000b689  lea     rcx, [rbp+830h+var_66F]; void *
0x14000b690  xor     r13b, r13b
0x14000b693  mov     [rsp+930h+var_8D8], rax
0x14000b698  mov     ebx, 103h
0x14000b69d  mov     [rsp+930h+var_8F0], r13b
0x14000b6a2  mov     r8d, ebx; Size
0x14000b6a5  mov     [rbp+830h+var_670], r13b
0x14000b6ac  xor     edx, edx; Val
0x14000b6ae  mov     esi, 80004005h
0x14000b6b3  call    memset_0
0x14000b6b8  mov     r8d, ebx; Size
0x14000b6bb  mov     [rbp+830h+var_780], r13b
0x14000b6c2  xor     edx, edx; Val
0x14000b6c4  lea     rcx, [rbp+830h+var_77F]; void *
0x14000b6cb  call    memset_0
0x14000b6d0  mov     r8d, ebx; Size
0x14000b6d3  mov     [rbp+830h+ProcName], r13b
0x14000b6d7  xor     edx, edx; Val
0x14000b6d9  lea     rcx, [rbp+830h+var_88F]; void *
0x14000b6dd  call    memset_0
0x14000b6e2  xor     eax, eax
0x14000b6e4  lea     rcx, [rbp+830h+var_45E]; void *
0x14000b6eb  mov     ebx, 206h
0x14000b6f0  mov     [rbp+830h+Src], ax
0x14000b6f7  mov     r8d, ebx; Size
0x14000b6fa  xor     edx, edx; Val
0x14000b6fc  call    memset_0
0x14000b701  xor     eax, eax
0x14000b703  lea     rcx, [rbp+830h+var_24E]; void *
0x14000b70a  mov     r8d, ebx; Size
0x14000b70d  mov     [rbp+830h+Dst], ax
0x14000b714  xor     edx, edx; Val
0x14000b716  call    memset_0
0x14000b71b  mov     ecx, 800h; DirectoryFlags
0x14000b720  call    cs:__imp_SetDefaultDllDirectories
0x14000b726  test    eax, eax
0x14000b728  jnz     short loc_14000B742
0x14000b72a  call    cs:__imp_GetLastError
0x14000b730  lea     r9, aSetdefaultdlld; "SetDefaultDllDirectories failed [%d]"
0x14000b737  mov     r8d, 0FDh
0x14000b73d  jmp     loc_14000BAE5
0x14000b742  mov     r14d, 104h
0x14000b748  lea     r8, aWindirSystem32; "%%windir%%\\system32\\%hs"
0x14000b74f  mov     edx, r14d; unsigned __int64
0x14000b752  lea     rcx, [rbp+830h+Src]; unsigned __int16 *
0x14000b759  mov     r9, r15
0x14000b75c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000b761  mov     ebx, eax
0x14000b763  test    eax, eax
0x14000b765  jns     short loc_14000B78C
0x14000b767  lea     r9, aStringcchprint_1; "StringCchPrintfW failed [%#x]"
0x14000b76e  mov     dword ptr [rsp+930h+var_910], eax
0x14000b772  lea     r8d, [r14+8]
0x14000b776  mov     ecx, 1
0x14000b77b  lea     rdx, aLaunchtelemetr; "LaunchTelemetryProvider"
0x14000b782  call    AslLogCallPrintf
0x14000b787  jmp     loc_14000BB0F
0x14000b78c  mov     r8d, r14d; nSize
0x14000b78f  lea     rdx, [rbp+830h+Dst]; lpDst
0x14000b796  lea     rcx, [rbp+830h+Src]; lpSrc
0x14000b79d  call    cs:__imp_ExpandEnvironmentStringsW
0x14000b7a3  dec     eax
0x14000b7a5  cmp     eax, 103h
0x14000b7aa  ja      loc_14000BAD2
0x14000b7b0  lea     rcx, [rbp+830h+Dst]; unsigned __int16 *
0x14000b7b7  call    ?VerifyEmbeddedSignature@@YAKPEBG@Z; VerifyEmbeddedSignature(ushort const *)
0x14000b7bc  mov     ebx, eax
0x14000b7be  test    eax, eax
0x14000b7c0  jz      short loc_14000B7F9
0x14000b7c2  mov     dword ptr [rsp+930h+var_908], eax
0x14000b7c6  lea     r9, aVerifyembedded; "VerifyEmbeddedSignature(%hs) failed: [%"...
0x14000b7cd  mov     r8d, 11Bh
0x14000b7d3  mov     [rsp+930h+var_910], r15
0x14000b7d8  lea     rdx, aLaunchtelemetr; "LaunchTelemetryProvider"
0x14000b7df  mov     ecx, 1
0x14000b7e4  call    AslLogCallPrintf
0x14000b7e9  test    ebx, ebx
0x14000b7eb  jle     loc_14000BB0F
0x14000b7f1  movzx   ebx, bx
0x14000b7f4  jmp     loc_14000BB09
0x14000b7f9  xor     edx, edx; hFile
0x14000b7fb  mov     r8d, 800h; dwFlags
0x14000b801  mov     rcx, r15; lpLibFileName
0x14000b804  call    cs:__imp_LoadLibraryExA
0x14000b80a  mov     r14, rax
0x14000b80d  test    rax, rax
0x14000b810  jnz     short loc_14000B82A
0x14000b812  call    cs:__imp_GetLastError
0x14000b818  lea     r9, aLoadlibraryexa; "LoadLibraryExA failed [%d]"
0x14000b81f  mov     r8d, 124h
0x14000b825  jmp     loc_14000BAE5
0x14000b82a  lea     rax, aTcex; "TCEx"
0x14000b831  mov     r9, rdi
0x14000b834  lea     r8, aHsHs; "%hs%hs"
0x14000b83b  mov     [rsp+930h+var_910], rax
0x14000b840  mov     edx, 104h; unsigned __int64
0x14000b845  lea     rcx, [rbp+830h+ProcName]; char *
0x14000b849  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14000b84e  mov     ebx, eax
0x14000b850  test    eax, eax
0x14000b852  jns     short loc_14000B87B
0x14000b854  mov     r8d, 12Dh
0x14000b85a  lea     r9, aStringcchprint; "StringCchPrintfA failed [%#x]"
0x14000b861  mov     dword ptr [rsp+930h+var_910], eax
0x14000b865  lea     rdx, aLaunchtelemetr; "LaunchTelemetryProvider"
0x14000b86c  mov     ecx, 1
0x14000b871  call    AslLogCallPrintf
0x14000b876  jmp     loc_14000BAC7
0x14000b87b  lea     rax, aTc2; "TC2"
0x14000b882  mov     r9, rdi
0x14000b885  lea     r8, aHsHs; "%hs%hs"
0x14000b88c  mov     [rsp+930h+var_910], rax
0x14000b891  mov     edx, 104h; unsigned __int64
0x14000b896  lea     rcx, [rbp+830h+var_780]; char *
0x14000b89d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14000b8a2  mov     ebx, eax
0x14000b8a4  test    eax, eax
0x14000b8a6  jns     short loc_14000B8B0
0x14000b8a8  mov     r8d, 134h
0x14000b8ae  jmp     short loc_14000B85A
0x14000b8b0  lea     rax, aTc; "TC"
0x14000b8b7  mov     r9, rdi
0x14000b8ba  lea     r8, aHsHs; "%hs%hs"
0x14000b8c1  mov     [rsp+930h+var_910], rax
0x14000b8c6  mov     edx, 104h; unsigned __int64
0x14000b8cb  lea     rcx, [rbp+830h+var_670]; char *
0x14000b8d2  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14000b8d7  mov     ebx, eax
0x14000b8d9  test    eax, eax
0x14000b8db  jns     short loc_14000B8E8
0x14000b8dd  mov     r8d, 13Bh
0x14000b8e3  jmp     loc_14000B85A
0x14000b8e8  lea     rdx, [rbp+830h+ProcName]; lpProcName
0x14000b8ec  mov     rcx, r14; hModule
0x14000b8ef  call    cs:__imp_GetProcAddress
0x14000b8f5  lea     rdx, [rbp+830h+var_780]; lpProcName
0x14000b8fc  mov     rcx, r14; hModule
0x14000b8ff  mov     [rsp+930h+var_8E0], rax
0x14000b904  call    cs:__imp_GetProcAddress
0x14000b90a  lea     rdx, [rbp+830h+var_670]; lpProcName
0x14000b911  mov     rcx, r14; hModule
0x14000b914  mov     [rsp+930h+var_8D0], rax
0x14000b919  call    cs:__imp_GetProcAddress
0x14000b91f  mov     rdx, rdi; lpProcName
0x14000b922  mov     rcx, r14; hModule
0x14000b925  mov     [rsp+930h+var_8C8], rax
0x14000b92a  call    cs:__imp_GetProcAddress
0x14000b930  mov     rdx, [rsp+930h+var_8E0]
0x14000b935  xor     ecx, ecx
0x14000b937  mov     r13, rax
0x14000b93a  test    rdx, rdx
0x14000b93d  jz      short loc_14000B985
0x14000b93f  mov     al, [rbp+830h+arg_20]
0x14000b945  lea     rdi, [rbp+830h+ProcName]
0x14000b949  mov     [rbp+830h+var_8A8], al
0x14000b94c  mov     rax, [rsp+930h+var_8D8]
0x14000b951  mov     [rbp+830h+var_8A7], ecx
0x14000b954  mov     [rbp+830h+var_8A3], cx
0x14000b958  mov     [rbp+830h+var_8A1], cl
0x14000b95b  mov     rcx, [rsp+930h+var_8E8]
0x14000b960  mov     [rbp+830h+var_8A0], rax
0x14000b964  mov     rax, rdx
0x14000b967  mov     [rsp+930h+var_8B8], rcx
0x14000b96c  lea     rcx, [rsp+930h+var_8C0]
0x14000b971  mov     [rsp+930h+var_8C0], 1
0x14000b97a  mov     [rbp+830h+var_8B0], r12
0x14000b97e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b983  jmp     short loc_14000B9CE
0x14000b985  mov     rax, [rsp+930h+var_8D0]
0x14000b98a  test    rax, rax
0x14000b98d  jz      short loc_14000B9AE
0x14000b98f  mov     r8b, [rbp+830h+arg_20]
0x14000b996  lea     rdi, [rbp+830h+var_780]
0x14000b99d  mov     rcx, [rsp+930h+var_8E8]
0x14000b9a2  mov     r9, r12
0x14000b9a5  xor     edx, edx
0x14000b9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b9ac  jmp     short loc_14000B9CE
0x14000b9ae  mov     rax, [rsp+930h+var_8C8]
0x14000b9b3  test    rax, rax
0x14000b9b6  jz      short loc_14000B9D5
0x14000b9b8  mov     rcx, [rsp+930h+var_8E8]
0x14000b9bd  lea     rdi, [rbp+830h+var_670]
0x14000b9c4  mov     r8, r12
0x14000b9c7  xor     edx, edx
0x14000b9c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b9ce  mov     esi, eax
0x14000b9d0  jmp     loc_14000BA67
0x14000b9d5  test    r13, r13
0x14000b9d8  jz      loc_14000BA98
0x14000b9de  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000b9e2  inc     rax
0x14000b9e5  cmp     [rdi+rax], cl
0x14000b9e8  jnz     short loc_14000B9E2
0x14000b9ea  cmp     byte ptr [rax+rdi-1], 57h ; 'W'
0x14000b9ef  jnz     short loc_14000BA55
0x14000b9f1  xor     edx, edx; Val
0x14000b9f3  lea     rcx, [rbp+830h+var_560]; void *
0x14000b9fa  mov     r8d, 100h; Size
0x14000ba00  call    memset_0
0x14000ba05  mov     r9, r12
0x14000ba08  lea     r8, aHs_3; "%hs"
0x14000ba0f  mov     edx, 80h; unsigned __int64
0x14000ba14  lea     rcx, [rbp+830h+var_560]; unsigned __int16 *
0x14000ba1b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000ba20  mov     ebx, eax
0x14000ba22  test    eax, eax
0x14000ba24  jns     short loc_14000BA4A
0x14000ba26  lea     r9, aStringcchprint_1; "StringCchPrintfW failed [%#x]"
0x14000ba2d  mov     dword ptr [rsp+930h+var_910], eax
0x14000ba31  mov     r8d, 166h
0x14000ba37  lea     rdx, aLaunchtelemetr; "LaunchTelemetryProvider"
0x14000ba3e  mov     ecx, 1
0x14000ba43  call    AslLogCallPrintf
0x14000ba48  jmp     short loc_14000BAC2
0x14000ba4a  lea     r8, [rbp+830h+var_560]
0x14000ba51  xor     ecx, ecx
0x14000ba53  jmp     short loc_14000BA58
0x14000ba55  mov     r8, r12
0x14000ba58  xor     r9d, r9d
0x14000ba5b  xor     edx, edx
0x14000ba5d  mov     rax, r13
0x14000ba60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba65  xor     esi, esi
0x14000ba67  mov     [rsp+930h+var_900], esi
0x14000ba6b  lea     r9, aCalledExportHs; "Called export %hs!%hs returned %#x"
0x14000ba72  mov     [rsp+930h+var_908], rdi
0x14000ba77  lea     rdx, aLaunchtelemetr; "LaunchTelemetryProvider"
0x14000ba7e  mov     r8d, 17Bh
0x14000ba84  mov     [rsp+930h+var_910], r15
0x14000ba89  mov     ecx, 3
0x14000ba8e  mov     r13b, 1
0x14000ba91  call    AslLogCallPrintf
0x14000ba96  jmp     short loc_14000BAC7
0x14000ba98  mov     [rsp+930h+var_908], r15
0x14000ba9d  lea     r9, aFunctionHsIsNo; "Function %hs is not exported by %hs"
0x14000baa4  mov     r8d, 174h
0x14000baaa  mov     [rsp+930h+var_910], rdi
0x14000baaf  lea     rdx, aLaunchtelemetr; "LaunchTelemetryProvider"
0x14000bab6  mov     ecx, 1
0x14000babb  call    AslLogCallPrintf
0x14000bac0  mov     ebx, esi
0x14000bac2  mov     r13b, [rsp+930h+var_8F0]
0x14000bac7  mov     rcx, r14; hLibModule
0x14000baca  call    cs:__imp_FreeLibrary
0x14000bad0  jmp     short loc_14000BB0F
0x14000bad2  call    cs:__imp_GetLastError
0x14000bad8  lea     r9, aExpandenvironm; "ExpandEnvironmentStringsW failed [%d]"
0x14000badf  mov     r8d, 113h
0x14000bae5  lea     rdx, aLaunchtelemetr; "LaunchTelemetryProvider"
0x14000baec  mov     dword ptr [rsp+930h+var_910], eax
0x14000baf0  mov     ecx, 1
0x14000baf5  call    AslLogCallPrintf
0x14000bafa  call    cs:__imp_GetLastError
0x14000bb00  mov     ebx, eax
0x14000bb02  test    eax, eax
0x14000bb04  jle     short loc_14000BB0F
0x14000bb06  movzx   ebx, ax
0x14000bb09  or      ebx, 80070000h
0x14000bb0f  test    r13b, r13b
0x14000bb12  cmovz   esi, ebx
0x14000bb15  mov     eax, esi
0x14000bb17  mov     rcx, [rbp+830h+var_40]
0x14000bb1e  xor     rcx, rsp; StackCookie
0x14000bb21  call    __security_check_cookie
0x14000bb26  mov     rbx, [rsp+930h+arg_18]
0x14000bb2e  add     rsp, 900h
0x14000bb35  pop     r15
0x14000bb37  pop     r14
0x14000bb39  pop     r13
0x14000bb3b  pop     r12
0x14000bb3d  pop     rdi
0x14000bb3e  pop     rsi
0x14000bb3f  pop     rbp
0x14000bb40  retn
```
