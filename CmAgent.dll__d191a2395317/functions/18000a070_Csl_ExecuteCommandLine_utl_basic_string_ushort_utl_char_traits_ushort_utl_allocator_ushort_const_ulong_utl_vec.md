# Csl::ExecuteCommandLine(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,ulong &,utl::vector<uchar,utl::allocator<uchar>> *,ulong)

- ea: `0x18000a070`
- end: `0x18000a55c`
- name: `?ExecuteCommandLine@Csl@@YAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAKPEAV?$vector@EV?$allocator@E@utl@@@3@K@Z`
- size: `1260`
- prototype: `__int64 __fastcall(WCHAR **, DWORD *, __int64, DWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009f8c`
- `0x18001edfc`

## callees

- `0x180002534`
- `0x180002c48`
- `0x1800045e4`
- `0x180007b2c`
- `0x180009eb8`
- `0x180009f24`
- `0x18000a070`
- `0x18000a6e0`
- `0x18000b004`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18000a2f2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18000a2f2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000a1f8`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000a1f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a25d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a25d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a33d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a33d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a35c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a35c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a145`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a160`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a238`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a34e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a45e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a479`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a516`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a531`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a145`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a160`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a238`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a34e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a45e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a479`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a516`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a531`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18000a17e`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18000a17e`
- `ntdll!NtTerminateProcess` at `0x18000a27c`
- `ntdll!NtTerminateProcess` at `0x18000a27c`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000a378`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000a378`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000a405`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000a405`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x18000a10f`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x18000a10f`

## pseudocode

```c
__int64 __fastcall Csl::ExecuteCommandLine(WCHAR **a1, DWORD *a2, __int64 a3, DWORD a4)
{
  void **v8; // rbx
  void **v9; // rax
  const char *v10; // r9
  __int64 v11; // rdx
  unsigned int LastError; // eax
  HANDLE v13; // rcx
  unsigned int v14; // ebx
  bool v15; // cc
  HANDLE v16; // rcx
  bool v17; // cc
  WCHAR *v19; // rdx
  const char *v20; // r9
  __int64 v21; // rdx
  struct _PROCESS_INFORMATION *v22; // rdx
  unsigned int v23; // eax
  struct _PROCESS_INFORMATION *v24; // rdx
  struct _PROCESS_INFORMATION *v25; // rdx
  HANDLE v26; // rsi
  DWORD v27; // ebx
  DWORD FileSize; // eax
  size_t v29; // r14
  __int64 v30; // r15
  void *v31; // rbx
  LPVOID lpSecurityDescriptor; // rsi
  const char *v33; // r9
  struct _PROCESS_INFORMATION *v34; // rdx
  unsigned int v35; // edi
  void *v36; // rcx
  int bInheritHandles; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-A8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-A0h] BYREF
  _SECURITY_ATTRIBUTES PipeAttributes; // [rsp+78h] [rbp-88h] BYREF
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp-70h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]
  DWORD ExitCode; // [rsp+150h] [rbp+50h] BYREF

  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  hFile = 0;
  hObject = 0;
  if ( a3 )
  {
    *(_QWORD *)&PipeAttributes.nLength = 24;
    *(_QWORD *)&PipeAttributes.bInheritHandle = 1;
    PipeAttributes.lpSecurityDescriptor = 0;
    v8 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
    v9 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hFile);
    if ( !CreatePipe(v9, v8, &PipeAttributes, 0) )
    {
      v11 = 1374;
LABEL_4:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v11,
                    (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
                    v10);
      v13 = hObject;
      v14 = LastError;
      v15 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_5:
      if ( v15 )
        CloseHandle(v13);
      v16 = hFile;
      v17 = (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_8:
      if ( v17 )
        CloseHandle(v16);
      return v14;
    }
    if ( !SetHandleInformation(hFile, 1u, 0) )
    {
      v11 = 1378;
      goto LABEL_4;
    }
    StartupInfo.dwFlags |= 0x100u;
    StartupInfo.hStdError = hObject;
    StartupInfo.hStdOutput = hObject;
  }
  v19 = *a1;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CreateProcessW(0, v19, 0, 0, a3 != 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    v21 = 1395;
LABEL_16:
    v14 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v21,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
            v20);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v22);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v16 = hFile;
    v17 = (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    goto LABEL_8;
  }
  if ( WaitForSingleObject(ProcessInformation.hProcess, a4) == 258 )
  {
    v14 = -2147023436;
    v23 = NtTerminateProcess(ProcessInformation.hProcess, -2147023436);
    if ( (int)(v23 + 0x80000000) >= 0 && v23 != -1073741558 )
      wil::details::in1diag3::Log_NtStatus(
        retaddr,
        (void *)0x582,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
        (const char *)v23,
        bInheritHandles);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x585,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
      (const char *)0x800705B4LL,
      bInheritHandles);
LABEL_24:
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v24);
    v13 = hObject;
    v15 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    goto LABEL_5;
  }
  ExitCode = 0;
  if ( !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
  {
    v21 = 1420;
    goto LABEL_16;
  }
  if ( a3 )
  {
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v25);
    v26 = hObject;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v27 = GetLastError();
      CloseHandle(v26);
      SetLastError(v27);
    }
    hObject = 0;
    FileSize = GetFileSize(hFile, 0);
    v29 = FileSize;
    if ( FileSize == -1 )
    {
      v21 = 1430;
      goto LABEL_16;
    }
    v30 = -1;
    NumberOfBytesRead = 0;
    *(_QWORD *)&PipeAttributes.bInheritHandle = -1;
    *(__m128i *)&PipeAttributes.nLength = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    if ( FileSize )
    {
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                               &PipeAttributes,
                               FileSize) )
      {
        v14 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x59D,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
          (const char *)0x8007000ELL,
          bInheritHandles);
        if ( *(_QWORD *)&PipeAttributes.nLength != -1 )
          operator delete(*(void **)&PipeAttributes.nLength, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_24;
      }
      memset_0(PipeAttributes.lpSecurityDescriptor, 0, v29);
      v31 = *(void **)&PipeAttributes.nLength;
      v30 = *(_QWORD *)&PipeAttributes.bInheritHandle;
      lpSecurityDescriptor = (LPVOID)(*(_QWORD *)&PipeAttributes.nLength + v29);
      if ( !ReadFile(hFile, *(LPVOID *)&PipeAttributes.nLength, v29, &NumberOfBytesRead, 0) )
      {
        v35 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x5A4,
                (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
                v33);
        if ( v31 != (void *)-1LL )
          operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
        wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v34);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hFile);
        return v35;
      }
    }
    else
    {
      lpSecurityDescriptor = PipeAttributes.lpSecurityDescriptor;
      v31 = *(void **)&PipeAttributes.nLength;
    }
    v36 = *(void **)a3;
    if ( *(_QWORD *)a3 != -1 )
    {
      *(_QWORD *)(a3 + 8) = v36;
      operator delete(v36, (const struct std::nothrow_t *)&std::nothrow);
    }
    *(_QWORD *)a3 = v31;
    *(_QWORD *)(a3 + 8) = lpSecurityDescriptor;
    *(_QWORD *)(a3 + 16) = v30;
  }
  *a2 = ExitCode;
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v25);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hFile);
  return 0;
}

```

## disassembly

```asm
0x18000a070  mov     [rsp-8+arg_0], rbx
0x18000a075  mov     [rsp-8+arg_8], rsi
0x18000a07a  push    rbp
0x18000a07b  push    rdi
0x18000a07c  push    r12
0x18000a07e  push    r14
0x18000a080  push    r15
0x18000a082  lea     rbp, [rsp-10h]
0x18000a087  sub     rsp, 110h
0x18000a08e  mov     r12, rdx
0x18000a091  mov     rdi, r8
0x18000a094  xor     edx, edx; Val
0x18000a096  mov     r14, rcx
0x18000a099  lea     rcx, [rbp+30h+StartupInfo+4]; void *
0x18000a09d  mov     esi, r9d
0x18000a0a0  lea     r8d, [rdx+64h]; Size
0x18000a0a4  call    memset_0
0x18000a0a9  mov     [rbp+30h+StartupInfo.cb], 68h ; 'h'
0x18000a0b0  mov     [rsp+130h+hFile], 0
0x18000a0b9  mov     [rsp+130h+hObject], 0
0x18000a0c2  test    rdi, rdi
0x18000a0c5  jz      loc_18000A1A7
0x18000a0cb  lea     rcx, [rsp+130h+hObject]
0x18000a0d0  mov     qword ptr [rsp+130h+PipeAttributes.nLength], 18h
0x18000a0d9  mov     qword ptr [rbp+30h+PipeAttributes.bInheritHandle], 1
0x18000a0e1  mov     r15d, 1
0x18000a0e7  mov     [rbp+30h+PipeAttributes.lpSecurityDescriptor], 0
0x18000a0ef  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18000a0f4  lea     rcx, [rsp+130h+hFile]
0x18000a0f9  mov     rbx, rax
0x18000a0fc  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18000a101  xor     r9d, r9d; nSize
0x18000a104  lea     r8, [rsp+130h+PipeAttributes]; lpPipeAttributes
0x18000a109  mov     rdx, rbx; hWritePipe
0x18000a10c  mov     rcx, rax; hReadPipe
0x18000a10f  call    cs:__imp_CreatePipe
0x18000a116  nop     dword ptr [rax+rax+00h]
0x18000a11b  test    eax, eax
0x18000a11d  jnz     short loc_18000A173
0x18000a11f  mov     edx, 55Eh; void *
0x18000a124  mov     rcx, [rbp+38h]; this
0x18000a128  lea     r8, aOnecoreBaseGen_14; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000a12f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a134  mov     rcx, [rsp+130h+hObject]; hObject
0x18000a139  mov     ebx, eax
0x18000a13b  lea     rdx, [rcx-1]
0x18000a13f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000a143  ja      short loc_18000A151
0x18000a145  call    cs:__imp_CloseHandle
0x18000a14c  nop     dword ptr [rax+rax+00h]
0x18000a151  mov     rcx, [rsp+130h+hFile]; hObject
0x18000a156  lea     rdx, [rcx-1]
0x18000a15a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000a15e  ja      short loc_18000A16C
0x18000a160  call    cs:__imp_CloseHandle
0x18000a167  nop     dword ptr [rax+rax+00h]
0x18000a16c  mov     eax, ebx
0x18000a16e  jmp     loc_18000A53F
0x18000a173  mov     rcx, [rsp+130h+hFile]; hObject
0x18000a178  xor     r8d, r8d; dwFlags
0x18000a17b  mov     edx, r15d; dwMask
0x18000a17e  call    cs:__imp_SetHandleInformation
0x18000a185  nop     dword ptr [rax+rax+00h]
0x18000a18a  test    eax, eax
0x18000a18c  jnz     short loc_18000A195
0x18000a18e  mov     edx, 562h
0x18000a193  jmp     short loc_18000A124
0x18000a195  mov     rax, [rsp+130h+hObject]
0x18000a19a  bts     [rbp+30h+StartupInfo.dwFlags], 8
0x18000a19f  mov     [rbp+30h+StartupInfo.hStdError], rax
0x18000a1a3  mov     [rbp+30h+StartupInfo.hStdOutput], rax
0x18000a1a7  mov     rdx, [r14]; lpCommandLine
0x18000a1aa  lea     rcx, [rsp+130h+ProcessInformation]
0x18000a1af  mov     [rsp+130h+lpProcessInformation], rcx; lpProcessInformation
0x18000a1b4  xor     eax, eax
0x18000a1b6  lea     rcx, [rbp+30h+StartupInfo]
0x18000a1ba  mov     qword ptr [rsp+130h+ProcessInformation.dwProcessId], rax
0x18000a1bf  mov     [rsp+130h+lpStartupInfo], rcx; lpStartupInfo
0x18000a1c4  xorps   xmm0, xmm0
0x18000a1c7  mov     [rsp+130h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18000a1d0  test    rdi, rdi
0x18000a1d3  mov     [rsp+130h+lpEnvironment], 0; lpEnvironment
0x18000a1dc  setnz   al
0x18000a1df  mov     [rsp+130h+dwCreationFlags], 8000000h; dwCreationFlags
0x18000a1e7  xor     r9d, r9d; lpThreadAttributes
0x18000a1ea  mov     [rsp+130h+bInheritHandles], eax; int
0x18000a1ee  xor     r8d, r8d; lpProcessAttributes
0x18000a1f1  xor     ecx, ecx; lpApplicationName
0x18000a1f3  movups  xmmword ptr [rsp+130h+ProcessInformation.hProcess], xmm0
0x18000a1f8  call    cs:__imp_CreateProcessW
0x18000a1ff  nop     dword ptr [rax+rax+00h]
0x18000a204  test    eax, eax
0x18000a206  jnz     short loc_18000A256
0x18000a208  mov     edx, 573h; void *
0x18000a20d  mov     rcx, [rbp+38h]; this
0x18000a211  lea     r8, aOnecoreBaseGen_14; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000a218  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a21d  lea     rcx, [rsp+130h+ProcessInformation]; this
0x18000a222  mov     ebx, eax
0x18000a224  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x18000a229  mov     rcx, [rsp+130h+hObject]; hObject
0x18000a22e  lea     rdx, [rcx-1]
0x18000a232  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000a236  ja      short loc_18000A244
0x18000a238  call    cs:__imp_CloseHandle
0x18000a23f  nop     dword ptr [rax+rax+00h]
0x18000a244  mov     rcx, [rsp+130h+hFile]
0x18000a249  lea     rax, [rcx-1]
0x18000a24d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a251  jmp     loc_18000A15E
0x18000a256  mov     rcx, [rsp+130h+ProcessInformation.hProcess]; hHandle
0x18000a25b  mov     edx, esi; dwMilliseconds
0x18000a25d  call    cs:__imp_WaitForSingleObject
0x18000a264  nop     dword ptr [rax+rax+00h]
0x18000a269  mov     rcx, [rsp+130h+ProcessInformation.hProcess]; hProcess
0x18000a26e  cmp     eax, 102h
0x18000a273  jnz     short loc_18000A2E7
0x18000a275  mov     ebx, 800705B4h
0x18000a27a  mov     edx, ebx; ExitStatus
0x18000a27c  call    cs:__imp_NtTerminateProcess
0x18000a283  nop     dword ptr [rax+rax+00h]
0x18000a288  mov     edx, 80000000h
0x18000a28d  lea     ecx, [rax+rdx]
0x18000a290  test    edx, ecx
0x18000a292  jnz     short loc_18000A2B3
0x18000a294  cmp     eax, 0C000010Ah
0x18000a299  jz      short loc_18000A2B3
0x18000a29b  mov     rcx, [rbp+38h]; this
0x18000a29f  lea     r8, aOnecoreBaseGen_14; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000a2a6  mov     r9d, eax; char *
0x18000a2a9  mov     edx, 582h; void *
0x18000a2ae  call    ?Log_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_NtStatus(void *,uint,char const *,long)
0x18000a2b3  mov     rcx, [rbp+38h]; this
0x18000a2b7  lea     r8, aOnecoreBaseGen_14; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000a2be  mov     r9d, ebx; char *
0x18000a2c1  mov     edx, 585h; void *
0x18000a2c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a2cb  lea     rcx, [rsp+130h+ProcessInformation]; this
0x18000a2d0  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x18000a2d5  mov     rcx, [rsp+130h+hObject]
0x18000a2da  lea     rax, [rcx-1]
0x18000a2de  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a2e2  jmp     loc_18000A143
0x18000a2e7  lea     rdx, [rbp+30h+ExitCode]; lpExitCode
0x18000a2eb  mov     [rbp+30h+ExitCode], 0
0x18000a2f2  call    cs:__imp_GetExitCodeProcess
0x18000a2f9  nop     dword ptr [rax+rax+00h]
0x18000a2fe  test    eax, eax
0x18000a300  jnz     short loc_18000A30C
0x18000a302  mov     edx, 58Ch
0x18000a307  jmp     loc_18000A20D
0x18000a30c  test    rdi, rdi
0x18000a30f  jz      loc_18000A4F6
0x18000a315  lea     rcx, [rsp+130h+ProcessInformation]; this
0x18000a31a  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x18000a31f  mov     rsi, [rsp+130h+hObject]
0x18000a324  xor     eax, eax
0x18000a326  mov     qword ptr [rsp+130h+ProcessInformation.dwProcessId], rax
0x18000a32b  xorps   xmm0, xmm0
0x18000a32e  movups  xmmword ptr [rsp+130h+ProcessInformation.hProcess], xmm0
0x18000a333  lea     rax, [rsi-1]
0x18000a337  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a33b  ja      short loc_18000A368
0x18000a33d  call    cs:__imp_GetLastError
0x18000a344  nop     dword ptr [rax+rax+00h]
0x18000a349  mov     rcx, rsi; hObject
0x18000a34c  mov     ebx, eax
0x18000a34e  call    cs:__imp_CloseHandle
0x18000a355  nop     dword ptr [rax+rax+00h]
0x18000a35a  mov     ecx, ebx; dwErrCode
0x18000a35c  call    cs:__imp_SetLastError
0x18000a363  nop     dword ptr [rax+rax+00h]
0x18000a368  mov     rcx, [rsp+130h+hFile]; hFile
0x18000a36d  xor     edx, edx; lpFileSizeHigh
0x18000a36f  mov     [rsp+130h+hObject], 0
0x18000a378  call    cs:__imp_GetFileSize
0x18000a37f  nop     dword ptr [rax+rax+00h]
0x18000a384  mov     r14d, eax
0x18000a387  cmp     eax, 0FFFFFFFFh
0x18000a38a  jnz     short loc_18000A396
0x18000a38c  mov     edx, 596h
0x18000a391  jmp     loc_18000A20D
0x18000a396  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000a39e  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000a3a2  mov     [rbp+30h+NumberOfBytesRead], 0
0x18000a3a9  mov     qword ptr [rbp+30h+PipeAttributes.bInheritHandle], r15
0x18000a3ad  movdqu  xmmword ptr [rsp+130h+PipeAttributes.nLength], xmm0
0x18000a3b3  test    eax, eax
0x18000a3b5  jz      loc_18000A4C9
0x18000a3bb  mov     rdx, r14
0x18000a3be  lea     rcx, [rsp+130h+PipeAttributes]
0x18000a3c3  mov     rsi, r14
0x18000a3c6  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x18000a3cb  test    al, al
0x18000a3cd  jz      loc_18000A48C
0x18000a3d3  mov     rcx, [rbp+30h+PipeAttributes.lpSecurityDescriptor]; void *
0x18000a3d7  mov     r8, r14; Size
0x18000a3da  xor     edx, edx; Val
0x18000a3dc  call    memset_0
0x18000a3e1  mov     rbx, qword ptr [rsp+130h+PipeAttributes.nLength]
0x18000a3e6  lea     r9, [rbp+30h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000a3ea  mov     rcx, [rsp+130h+hFile]; hFile
0x18000a3ef  mov     rdx, rbx; lpBuffer
0x18000a3f2  mov     r15, qword ptr [rbp+30h+PipeAttributes.bInheritHandle]
0x18000a3f6  mov     r8d, r14d; nNumberOfBytesToRead
0x18000a3f9  add     rsi, rbx
0x18000a3fc  mov     qword ptr [rsp+130h+bInheritHandles], 0; lpOverlapped
0x18000a405  call    cs:__imp_ReadFile
0x18000a40c  nop     dword ptr [rax+rax+00h]
0x18000a411  test    eax, eax
0x18000a413  jnz     loc_18000A4D2
0x18000a419  mov     rcx, [rbp+38h]; this
0x18000a41d  lea     r8, aOnecoreBaseGen_14; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000a424  mov     edx, 5A4h; void *
0x18000a429  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a42e  mov     edi, eax
0x18000a430  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a434  jz      short loc_18000A445
0x18000a436  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a43d  mov     rcx, rbx; void *
0x18000a440  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a445  lea     rcx, [rsp+130h+ProcessInformation]; this
0x18000a44a  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x18000a44f  mov     rcx, [rsp+130h+hObject]; hObject
0x18000a454  lea     rdx, [rcx-1]
0x18000a458  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000a45c  ja      short loc_18000A46A
0x18000a45e  call    cs:__imp_CloseHandle
0x18000a465  nop     dword ptr [rax+rax+00h]
0x18000a46a  mov     rcx, [rsp+130h+hFile]; hObject
0x18000a46f  lea     rax, [rcx-1]
0x18000a473  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a477  ja      short loc_18000A485
0x18000a479  call    cs:__imp_CloseHandle
0x18000a480  nop     dword ptr [rax+rax+00h]
0x18000a485  mov     eax, edi
0x18000a487  jmp     loc_18000A53F
0x18000a48c  mov     rcx, [rbp+38h]; this
0x18000a490  lea     r8, aOnecoreBaseGen_14; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000a497  mov     ebx, 8007000Eh
0x18000a49c  mov     edx, 59Dh; void *
0x18000a4a1  mov     r9d, ebx; char *
0x18000a4a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a4a9  mov     rcx, qword ptr [rsp+130h+PipeAttributes.nLength]; void *
0x18000a4ae  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a4b2  jz      loc_18000A2CB
0x18000a4b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a4bf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a4c4  jmp     loc_18000A2CB
0x18000a4c9  mov     rsi, [rbp+30h+PipeAttributes.lpSecurityDescriptor]
0x18000a4cd  mov     rbx, qword ptr [rsp+130h+PipeAttributes.nLength]
0x18000a4d2  mov     rcx, [rdi]; void *
0x18000a4d5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a4d9  jz      short loc_18000A4EB
0x18000a4db  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a4e2  mov     [rdi+8], rcx
0x18000a4e6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a4eb  mov     [rdi], rbx
0x18000a4ee  mov     [rdi+8], rsi
0x18000a4f2  mov     [rdi+10h], r15
0x18000a4f6  mov     eax, [rbp+30h+ExitCode]
0x18000a4f9  lea     rcx, [rsp+130h+ProcessInformation]; this
0x18000a4fe  mov     [r12], eax
0x18000a502  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x18000a507  mov     rcx, [rsp+130h+hObject]; hObject
0x18000a50c  lea     rax, [rcx-1]
0x18000a510  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a514  ja      short loc_18000A522
0x18000a516  call    cs:__imp_CloseHandle
0x18000a51d  nop     dword ptr [rax+rax+00h]
0x18000a522  mov     rcx, [rsp+130h+hFile]; hObject
0x18000a527  lea     rax, [rcx-1]
0x18000a52b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a52f  ja      short loc_18000A53D
0x18000a531  call    cs:__imp_CloseHandle
0x18000a538  nop     dword ptr [rax+rax+00h]
0x18000a53d  xor     eax, eax
0x18000a53f  lea     r11, [rsp+130h+var_20]
0x18000a547  mov     rbx, [r11+30h]
0x18000a54b  mov     rsi, [r11+38h]
0x18000a54f  mov     rsp, r11
0x18000a552  pop     r15
0x18000a554  pop     r14
0x18000a556  pop     r12
0x18000a558  pop     rdi
0x18000a559  pop     rbp
0x18000a55a  retn
```
