# WaasMedic::CSandboxRpcWrapper::CreateSandbox(void)

- ea: `0x18001e83c`
- end: `0x18001eb54`
- name: `?CreateSandbox@CSandboxRpcWrapper@WaasMedic@@QEAAJXZ`
- size: `792`
- prototype: `__int64 __fastcall(WaasMedic::CSandboxRpcWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180018d3c`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x1800098f0`
- `0x180009cd0`
- `0x18001e83c`
- `0x18001f23c`
- `0x1800261c8`
- `0x180026a98`
- `0x1800285a0`
- `0x180028b9c`
- `0x18002a87c`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001eaac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001eaac`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001e99b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001e99b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e9c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e9c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea29`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001eac1`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001eac1`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001ea1f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001ea1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e9b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e9b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb1b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001e8e3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001e8e3`

## string_xrefs

- `0x18001ea91`: `Service found out worker will wait %d second(s). Adjusting waiting for sandbox process start to that amount.`
- `0x18001e902`: `Failed to expand WaaSMedicAgent command line.  Nothing copied! hr = 0x%08x`
- `0x18001e914`: `Failed to expand WaaSMedicAgent command line! hr = 0x%08x`
- `0x18001e9d8`: `CreateMutex failed. Error code: 0x%08x`
- `0x18001ea3a`: `CreateProcessW failed. hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::CSandboxRpcWrapper::CreateSandbox(const WCHAR **this)
{
  const WCHAR *v2; // rcx
  unsigned int v3; // edi
  const unsigned __int16 *v4; // rdx
  DWORD v5; // eax
  signed int LastError; // eax
  const WCHAR *v7; // rdx
  __int64 v8; // r8
  int Sha256HashOfString; // eax
  const WCHAR *v10; // r8
  const WCHAR *MutexW; // rsi
  WCHAR *v12; // rcx
  signed int v13; // eax
  unsigned int v14; // edx
  signed int v15; // eax
  DWORD v16; // ebx
  WaasMedic *v17; // rcx
  unsigned __int16 *v18; // rdx
  unsigned __int16 *v19; // r9
  __int64 v20; // rcx
  unsigned int DwordValueWithDefault; // ebx
  unsigned int *bInheritHandles; // [rsp+20h] [rbp-E0h]
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v26; // [rsp+70h] [rbp-90h] BYREF
  __int64 v27; // [rsp+80h] [rbp-80h]
  __int64 v28; // [rsp+88h] [rbp-78h]
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpName[2]; // [rsp+100h] [rbp+0h] BYREF
  __m128i si128; // [rsp+110h] [rbp+10h]
  WCHAR Dst[264]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v33[132]; // [rsp+330h] [rbp+230h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  *(_OWORD *)lpName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpName[0]) = 0;
  WaasMedic::CSandboxRpcWrapper::SandBoxShutdown((WaasMedic::CSandboxRpcWrapper *)this);
  v2 = this[2];
  if ( !v2 )
  {
    v3 = -2147467261;
    v4 = L"Sandbox is not initialized! hr = 0x%08x";
LABEL_3:
    LogLevelW(2u, v4, v3);
    goto LABEL_38;
  }
  v5 = ExpandEnvironmentStringsW(v2, Dst, 0x104u);
  if ( !v5 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v4 = L"Failed to expand WaaSMedicAgent command line.  Nothing copied! hr = 0x%08x";
    goto LABEL_3;
  }
  if ( v5 > 0x104 )
  {
    v3 = -2147024774;
    v4 = L"Failed to expand WaaSMedicAgent command line! hr = 0x%08x";
    goto LABEL_3;
  }
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v7 = this[1];
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v8 = -1;
  do
    ++v8;
  while ( v7[v8] );
  std::wstring::_Construct<1,unsigned short const *>(&v26, v7);
  Sha256HashOfString = WaasMedic::GetSha256HashOfString(&v26);
  v3 = Sha256HashOfString;
  if ( Sha256HashOfString >= 0 )
  {
    v10 = (const WCHAR *)lpName;
    if ( si128.m128i_i64[1] > 7uLL )
      v10 = lpName[0];
    MutexW = (const WCHAR *)CreateMutexW(0, 1, v10);
    v12 = (WCHAR *)this[4];
    if ( (unsigned __int64)v12 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v12);
    this[4] = MutexW;
    if ( !MutexW )
    {
      v13 = GetLastError();
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      LogLevelW(3u, L"CreateMutex failed. Error code: 0x%08x", (unsigned int)v13);
    }
    if ( !CreateProcessW(0, Dst, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      v15 = GetLastError();
      v3 = v15;
      if ( v15 > 0 )
        v3 = (unsigned __int16)v15 | 0x80070000;
      v4 = L"CreateProcessW failed. hr = 0x%08x";
      goto LABEL_3;
    }
    v16 = 1000;
    if ( WaasMedic::MiscUtil::IsTestKeyEnabled((const unsigned __int16 *)&stru_1800787F8, v14)
      && WaasMedic::IsTestSigningEnabled(v17)
      && WaasMedic::RegGetPersistedSubkeyPath((WaasMedic *)L"Test", v18, (unsigned int)v33, v19, bInheritHandles) >= 0 )
    {
      DwordValueWithDefault = WaasMedic::RegQueryDwordValueWithDefault(v20, v33);
      LogLevelW(
        4u,
        L"Service found out worker will wait %d second(s). Adjusting waiting for sandbox process start to that amount.",
        DwordValueWithDefault);
      v16 = 1000 * DwordValueWithDefault;
    }
    WaitForSingleObject(ProcessInformation.hProcess, v16);
    ExitCode = 0;
    if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
    {
      LogLevelW(4u, L"Exit code of sandbox: %d!", ExitCode);
      if ( ExitCode != 259 )
      {
        if ( (int)ExitCode > 0 )
          v3 = (unsigned __int16)ExitCode | 0x80010000;
        else
          v3 = ExitCode;
        LogLevelW(2u, L"Sandbox process died.");
      }
    }
    CloseHandle(ProcessInformation.hProcess);
    CloseHandle(ProcessInformation.hThread);
  }
  else
  {
    LogLevelW(2u, L"Failed to determine mutex name. hr = 0x%08x.", (unsigned int)Sha256HashOfString);
  }
LABEL_38:
  std::wstring::~wstring(lpName);
  return v3;
}

```

## disassembly

```asm
0x18001e83c  mov     [rsp-8+arg_8], rbx
0x18001e841  mov     [rsp-8+arg_10], rsi
0x18001e846  push    rbp
0x18001e847  push    rdi
0x18001e848  push    r14
0x18001e84a  lea     rbp, [rsp-450h]
0x18001e852  sub     rsp, 550h
0x18001e859  mov     rax, cs:__security_cookie
0x18001e860  xor     rax, rsp
0x18001e863  mov     [rbp+460h+var_20], rax
0x18001e86a  mov     rbx, rcx
0x18001e86d  mov     esi, 68h ; 'h'
0x18001e872  mov     r8d, esi; Size
0x18001e875  xor     edx, edx; Val
0x18001e877  lea     rcx, [rbp+460h+StartupInfo]; void *
0x18001e87b  call    memset_0
0x18001e880  xorps   xmm0, xmm0
0x18001e883  xor     eax, eax
0x18001e885  movups  xmmword ptr [rsp+560h+ProcessInformation.hProcess], xmm0
0x18001e88a  mov     qword ptr [rsp+560h+ProcessInformation.dwProcessId], rax
0x18001e88f  movups  xmmword ptr [rbp+460h+lpName], xmm0
0x18001e893  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001e89b  movdqu  [rbp+460h+var_450], xmm1
0x18001e8a0  xor     r14d, r14d
0x18001e8a3  mov     word ptr [rbp+460h+lpName], r14w
0x18001e8a8  mov     rcx, rbx; this
0x18001e8ab  call    ?SandBoxShutdown@CSandboxRpcWrapper@WaasMedic@@QEAAJXZ; WaasMedic::CSandboxRpcWrapper::SandBoxShutdown(void)
0x18001e8b0  mov     rcx, [rbx+10h]; lpSrc
0x18001e8b4  test    rcx, rcx
0x18001e8b7  jnz     short loc_18001E8D7
0x18001e8b9  mov     edi, 80004003h
0x18001e8be  lea     rdx, aSandboxIsNotIn; "Sandbox is not initialized! hr = 0x%08x"
0x18001e8c5  mov     r8d, edi
0x18001e8c8  mov     ecx, 2; unsigned __int8
0x18001e8cd  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001e8d2  jmp     loc_18001EB22
0x18001e8d7  mov     edi, 104h
0x18001e8dc  mov     r8d, edi; nSize
0x18001e8df  lea     rdx, [rbp+460h+Dst]; lpDst
0x18001e8e3  call    cs:__imp_ExpandEnvironmentStringsW
0x18001e8e9  test    eax, eax
0x18001e8eb  jnz     short loc_18001E90B
0x18001e8ed  call    cs:__imp_GetLastError
0x18001e8f3  mov     edi, eax
0x18001e8f5  test    eax, eax
0x18001e8f7  jle     short loc_18001E902
0x18001e8f9  movzx   edi, ax
0x18001e8fc  or      edi, 80070000h
0x18001e902  lea     rdx, aFailedToExpand_3; "Failed to expand WaaSMedicAgent command"...
0x18001e909  jmp     short loc_18001E8C5
0x18001e90b  cmp     eax, edi
0x18001e90d  jbe     short loc_18001E91D
0x18001e90f  mov     edi, 8007007Ah
0x18001e914  lea     rdx, aFailedToExpand_0; "Failed to expand WaaSMedicAgent command"...
0x18001e91b  jmp     short loc_18001E8C5
0x18001e91d  mov     r8, rsi; Size
0x18001e920  xor     edx, edx; Val
0x18001e922  lea     rcx, [rbp+460h+StartupInfo]; void *
0x18001e926  call    memset_0
0x18001e92b  xorps   xmm0, xmm0
0x18001e92e  xor     eax, eax
0x18001e930  movups  xmmword ptr [rsp+560h+ProcessInformation.hProcess], xmm0
0x18001e935  mov     qword ptr [rsp+560h+ProcessInformation.dwProcessId], rax
0x18001e93a  mov     rdx, [rbx+8]
0x18001e93e  movups  [rsp+560h+var_4F0], xmm0
0x18001e943  mov     [rbp+460h+var_4E0], r14
0x18001e947  mov     [rbp+460h+var_4D8], r14
0x18001e94b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001e94f  inc     r8
0x18001e952  cmp     [rdx+r8*2], r14w
0x18001e957  jnz     short loc_18001E94F
0x18001e959  lea     rcx, [rsp+560h+var_4F0]
0x18001e95e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001e963  lea     rdx, [rbp+460h+lpName]
0x18001e967  lea     rcx, [rsp+560h+var_4F0]; void *
0x18001e96c  call    ?GetSha256HashOfString@WaasMedic@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; WaasMedic::GetSha256HashOfString(std::wstring,std::wstring &)
0x18001e971  mov     edi, eax
0x18001e973  test    eax, eax
0x18001e975  jns     short loc_18001E986
0x18001e977  mov     r8d, eax
0x18001e97a  lea     rdx, aFailedToDeterm_2; "Failed to determine mutex name. hr = 0x"...
0x18001e981  jmp     loc_18001E8C8
0x18001e986  lea     r8, [rbp+460h+lpName]
0x18001e98a  cmp     qword ptr [rbp+460h+var_450+8], 7
0x18001e98f  cmova   r8, [rbp+460h+lpName]; lpName
0x18001e994  mov     edx, 1; bInitialOwner
0x18001e999  xor     ecx, ecx; lpMutexAttributes
0x18001e99b  call    cs:__imp_CreateMutexW
0x18001e9a1  mov     rsi, rax
0x18001e9a4  mov     rcx, [rbx+20h]; hObject
0x18001e9a8  lea     rdx, [rcx-1]
0x18001e9ac  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001e9b0  ja      short loc_18001E9B8
0x18001e9b2  call    cs:__imp_CloseHandle
0x18001e9b8  mov     [rbx+20h], rsi
0x18001e9bc  mov     ebx, 80070000h
0x18001e9c1  test    rsi, rsi
0x18001e9c4  jnz     short loc_18001E9E9
0x18001e9c6  call    cs:__imp_GetLastError
0x18001e9cc  test    eax, eax
0x18001e9ce  jle     short loc_18001E9D5
0x18001e9d0  movzx   eax, ax
0x18001e9d3  or      eax, ebx
0x18001e9d5  mov     r8d, eax
0x18001e9d8  lea     rdx, aCreatemutexFai; "CreateMutex failed. Error code: 0x%08x"
0x18001e9df  mov     ecx, 3; unsigned __int8
0x18001e9e4  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001e9e9  lea     rax, [rsp+560h+ProcessInformation]
0x18001e9ee  mov     [rsp+560h+lpProcessInformation], rax; lpProcessInformation
0x18001e9f3  lea     rax, [rbp+460h+StartupInfo]
0x18001e9f7  mov     [rsp+560h+lpStartupInfo], rax; lpStartupInfo
0x18001e9fc  mov     [rsp+560h+lpCurrentDirectory], r14; lpCurrentDirectory
0x18001ea01  mov     [rsp+560h+lpEnvironment], r14; lpEnvironment
0x18001ea06  mov     [rsp+560h+dwCreationFlags], 8000000h; dwCreationFlags
0x18001ea0e  mov     dword ptr [rsp+560h+bInheritHandles], r14d; unsigned int *
0x18001ea13  xor     r9d, r9d; lpThreadAttributes
0x18001ea16  xor     r8d, r8d; lpProcessAttributes
0x18001ea19  lea     rdx, [rbp+460h+Dst]; lpCommandLine
0x18001ea1d  xor     ecx, ecx; lpApplicationName
0x18001ea1f  call    cs:__imp_CreateProcessW
0x18001ea25  test    eax, eax
0x18001ea27  jnz     short loc_18001EA46
0x18001ea29  call    cs:__imp_GetLastError
0x18001ea2f  mov     edi, eax
0x18001ea31  test    eax, eax
0x18001ea33  jle     short loc_18001EA3A
0x18001ea35  movzx   edi, ax
0x18001ea38  or      edi, ebx
0x18001ea3a  lea     rdx, aCreateprocessw; "CreateProcessW failed. hr = 0x%08x"
0x18001ea41  jmp     loc_18001E8C5
0x18001ea46  mov     ebx, 3E8h
0x18001ea4b  lea     rcx, stru_1800787F8; unsigned __int16 *
0x18001ea52  call    ?IsTestKeyEnabled@MiscUtil@WaasMedic@@SA_NPEBGK@Z; WaasMedic::MiscUtil::IsTestKeyEnabled(ushort const *,ulong)
0x18001ea57  mov     esi, 4
0x18001ea5c  test    al, al
0x18001ea5e  jz      short loc_18001EAA5
0x18001ea60  call    ?IsTestSigningEnabled@WaasMedic@@YA_NXZ; WaasMedic::IsTestSigningEnabled(void)
0x18001ea65  test    al, al
0x18001ea67  jz      short loc_18001EAA5
0x18001ea69  lea     r8, [rbp+460h+var_230]; unsigned int
0x18001ea70  lea     rcx, aTest; "Test"
0x18001ea77  call    ?RegGetPersistedSubkeyPath@WaasMedic@@YAJPEAGK0PEAK@Z; WaasMedic::RegGetPersistedSubkeyPath(ushort *,ulong,ushort *,ulong *)
0x18001ea7c  test    eax, eax
0x18001ea7e  js      short loc_18001EAA5
0x18001ea80  lea     rdx, [rbp+460h+var_230]
0x18001ea87  call    ?RegQueryDwordValueWithDefault@WaasMedic@@YAKPEAUHKEY__@@PEBG1KW4RegistryHiveType@1@@Z; WaasMedic::RegQueryDwordValueWithDefault(HKEY__ *,ushort const *,ushort const *,ulong,WaasMedic::RegistryHiveType)
0x18001ea8c  mov     ebx, eax
0x18001ea8e  mov     r8d, eax
0x18001ea91  lea     rdx, aServiceFoundOu; "Service found out worker will wait %d s"...
0x18001ea98  mov     ecx, esi; unsigned __int8
0x18001ea9a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001ea9f  imul    ebx, 3E8h
0x18001eaa5  mov     edx, ebx; dwMilliseconds
0x18001eaa7  mov     rcx, [rsp+560h+ProcessInformation.hProcess]; hHandle
0x18001eaac  call    cs:__imp_WaitForSingleObject
0x18001eab2  mov     [rsp+560h+ExitCode], r14d
0x18001eab7  lea     rdx, [rsp+560h+ExitCode]; lpExitCode
0x18001eabc  mov     rcx, [rsp+560h+ProcessInformation.hProcess]; hProcess
0x18001eac1  call    cs:__imp_GetExitCodeProcess
0x18001eac7  test    eax, eax
0x18001eac9  jz      short loc_18001EB0B
0x18001eacb  mov     r8d, [rsp+560h+ExitCode]
0x18001ead0  lea     rdx, aExitCodeOfSand; "Exit code of sandbox: %d!"
0x18001ead7  mov     ecx, esi; unsigned __int8
0x18001ead9  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001eade  mov     eax, [rsp+560h+ExitCode]
0x18001eae2  cmp     eax, 103h
0x18001eae7  jz      short loc_18001EB0B
0x18001eae9  test    eax, eax
0x18001eaeb  jg      short loc_18001EAF1
0x18001eaed  mov     edi, eax
0x18001eaef  jmp     short loc_18001EAFA
0x18001eaf1  movzx   edi, ax
0x18001eaf4  or      edi, 80010000h
0x18001eafa  lea     rdx, aSandboxProcess; "Sandbox process died."
0x18001eb01  mov     ecx, 2; unsigned __int8
0x18001eb06  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001eb0b  mov     rcx, [rsp+560h+ProcessInformation.hProcess]; hObject
0x18001eb10  call    cs:__imp_CloseHandle
0x18001eb16  mov     rcx, [rsp+560h+ProcessInformation.hThread]; hObject
0x18001eb1b  call    cs:__imp_CloseHandle
0x18001eb21  nop
0x18001eb22  lea     rcx, [rbp+460h+lpName]; void *
0x18001eb26  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001eb2b  mov     eax, edi
0x18001eb2d  mov     rcx, [rbp+460h+var_20]
0x18001eb34  xor     rcx, rsp; StackCookie
0x18001eb37  call    __security_check_cookie
0x18001eb3c  lea     r11, [rsp+560h+var_10]
0x18001eb44  mov     rbx, [r11+28h]
0x18001eb48  mov     rsi, [r11+30h]
0x18001eb4c  mov     rsp, r11
0x18001eb4f  pop     r14
0x18001eb51  pop     rdi
0x18001eb52  pop     rbp
0x18001eb53  retn
```
