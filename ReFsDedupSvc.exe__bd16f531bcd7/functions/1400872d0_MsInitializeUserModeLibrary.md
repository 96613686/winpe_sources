# MsInitializeUserModeLibrary

- ea: `0x1400872d0`
- end: `0x140087608`
- name: `MsInitializeUserModeLibrary`
- size: `824`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14006f5e0`

## callees

- `0x1400830cc`
- `0x1400830f4`
- `0x140085708`
- `0x140085e30`
- `0x140086f78`
- `0x1400872d0`
- `0x140087ec0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400873a6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400873a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400873fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400873fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14008744d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140087497`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400874ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140087543`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140087599`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14008744d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140087497`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400874ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140087543`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140087599`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x14008733f`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x14008733f`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x140087327`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x140087327`

## string_xrefs

- `0x140087579`: `MinstoreCleanLockedCachedPagesTarget`
- `0x140087523`: `MinstoreCleanLockedCachedPagesThreshold`

## pseudocode

```c
__int64 __fastcall MsInitializeUserModeLibrary(char a1, char a2)
{
  LSTATUS v2; // ebx
  __int64 v4; // rdx
  int v5; // eax
  int dwCreationFlags; // [rsp+20h] [rbp-10h]
  int dwCreationFlagsa; // [rsp+20h] [rbp-10h]
  const char *lpThreadId; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  DWORD cbData; // [rsp+40h] [rbp+10h] BYREF
  unsigned int Data; // [rsp+48h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp+20h] BYREF

  LOBYTE(Data) = a2;
  LOBYTE(cbData) = a1;
  if ( byte_14021FE30 )
  {
    v2 = -1073741436;
    wil::details::in1diag3::Return_NtStatus(
      retaddr,
      (void *)0x28B,
      (unsigned int)"minkernel\\fs\\minstore\\usermodeenvironment.cpp",
      (const char *)0xC0000184LL,
      dwCreationFlags);
    return (unsigned int)v2;
  }
  UmeInitUpcaseTable();
  word_140220078 = 257;
  InitializeSListHead(&ListHead);
  ExistingCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
  if ( !ExistingCompletionPort )
  {
    v4 = 674;
LABEL_6:
    v2 = -1073741670;
    wil::details::in1diag3::Return_NtStatusMsg(
      retaddr,
      (void *)v4,
      (unsigned int)"minkernel\\fs\\minstore\\usermodeenvironment.cpp",
      (const char *)0xC000009ALL,
      (int)"STATUS_INSUFFICIENT_RESOURCES",
      lpThreadId);
LABEL_7:
    UmepCleanupCompletionThread();
    return (unsigned int)v2;
  }
  qword_14021FE28 = CreateThread(0, 0, UmeIoCompletionThreadWorker, 0, 0, 0);
  if ( !qword_14021FE28 )
  {
    v4 = 683;
    goto LABEL_6;
  }
  Data = 0;
  cbData = 0;
  phkResult = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\FileSystem", 0, 0x20019u, &phkResult);
  if ( v2 < 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    goto LABEL_7;
  }
  Data = 0;
  cbData = 4;
  if ( RegQueryValueExW(phkResult, L"MinstoreAlwaysCheckpointPageCountThreshold", 0, 0, (LPBYTE)&Data, &cbData) >= 0
    && Data )
  {
    dword_1402200C8 = Data;
  }
  Data = 0;
  cbData = 4;
  if ( RegQueryValueExW(phkResult, L"MinstoreDirtyPageThreshold", 0, 0, (LPBYTE)&Data, &cbData) < 0
    || (qword_14021FDE8 = Data) == 0 )
  {
    qword_14021FDE8 = 0x40000;
  }
  Data = 0;
  cbData = 4;
  if ( RegQueryValueExW(phkResult, L"MinstoreDirtyPageTarget", 0, 0, (LPBYTE)&Data, &cbData) < 0
    || (qword_14021FDF0 = Data) == 0 )
  {
    qword_14021FDF0 = 0x20000;
  }
  Data = 0;
  cbData = 4;
  if ( RegQueryValueExW(phkResult, L"MinstoreCleanLockedCachedPagesThreshold", 0, 0, (LPBYTE)&Data, &cbData) < 0
    || (qword_14021FDF8 = Data) == 0 )
  {
    qword_14021FDF8 = 0x40000;
  }
  Data = 0;
  cbData = 4;
  if ( RegQueryValueExW(phkResult, L"MinstoreCleanLockedCachedPagesTarget", 0, 0, (LPBYTE)&Data, &cbData) < 0
    || (qword_14021FE00 = Data) == 0 )
  {
    qword_14021FE00 = 0x20000;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  v5 = MsInitializeLibrary();
  v2 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_NtStatus(
      retaddr,
      (void *)0x318,
      (unsigned int)"minkernel\\fs\\minstore\\usermodeenvironment.cpp",
      (const char *)(unsigned int)v5,
      dwCreationFlagsa);
    goto LABEL_7;
  }
  byte_14021FE30 = 1;
  return 0;
}

```

## disassembly

```asm
0x1400872d0  mov     [rsp-8+arg_18], rbx
0x1400872d5  mov     byte ptr [rsp-8+Data], dl
0x1400872d9  mov     byte ptr [rsp-8+cbData], cl
0x1400872dd  push    rbp
0x1400872de  mov     rbp, rsp
0x1400872e1  sub     rsp, 30h
0x1400872e5  cmp     cs:byte_14021FE30, 0
0x1400872ec  jz      short loc_140087312
0x1400872ee  mov     rcx, [rbp+8]; this
0x1400872f2  lea     r8, aMinkernelFsMin_5; "minkernel\\fs\\minstore\\usermodeenviro"...
0x1400872f9  mov     ebx, 0C0000184h
0x1400872fe  mov     edx, 28Bh; void *
0x140087303  mov     r9d, ebx; char *
0x140087306  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14008730b  mov     eax, ebx
0x14008730d  jmp     loc_1400875FC
0x140087312  call    UmeInitUpcaseTable
0x140087317  lea     rcx, ListHead; ListHead
0x14008731e  mov     cs:word_140220078, 101h
0x140087327  call    cs:__imp_InitializeSListHead
0x14008732e  nop     dword ptr [rax+rax+00h]
0x140087333  xor     r9d, r9d; NumberOfConcurrentThreads
0x140087336  xor     r8d, r8d; CompletionKey
0x140087339  xor     edx, edx; ExistingCompletionPort
0x14008733b  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x14008733f  call    cs:__imp_CreateIoCompletionPort
0x140087346  nop     dword ptr [rax+rax+00h]
0x14008734b  mov     cs:ExistingCompletionPort, rax
0x140087352  test    rax, rax
0x140087355  jnz     short loc_140087387
0x140087357  mov     edx, 2A2h; void *
0x14008735c  mov     rcx, [rbp+8]; this
0x140087360  lea     rax, aStatusInsuffic; "STATUS_INSUFFICIENT_RESOURCES"
0x140087367  mov     ebx, 0C000009Ah
0x14008736c  mov     qword ptr [rsp+30h+dwCreationFlags], rax; int
0x140087371  mov     r9d, ebx; char *
0x140087374  lea     r8, aMinkernelFsMin_5; "minkernel\\fs\\minstore\\usermodeenviro"...
0x14008737b  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x140087380  call    UmepCleanupCompletionThread
0x140087385  jmp     short loc_14008730B
0x140087387  mov     [rsp+30h+lpThreadId], 0; lpThreadId
0x140087390  lea     r8, UmeIoCompletionThreadWorker; lpStartAddress
0x140087397  xor     r9d, r9d; lpParameter
0x14008739a  mov     [rsp+30h+dwCreationFlags], 0; dwCreationFlags
0x1400873a2  xor     edx, edx; dwStackSize
0x1400873a4  xor     ecx, ecx; lpThreadAttributes
0x1400873a6  call    cs:__imp_CreateThread
0x1400873ad  nop     dword ptr [rax+rax+00h]
0x1400873b2  mov     cs:qword_14021FE28, rax
0x1400873b9  test    rax, rax
0x1400873bc  jnz     short loc_1400873C5
0x1400873be  mov     edx, 2ABh
0x1400873c3  jmp     short loc_14008735C
0x1400873c5  lea     rax, [rbp+phkResult]
0x1400873c9  mov     [rbp+Data], 0
0x1400873d0  mov     r9d, 20019h; samDesired
0x1400873d6  mov     qword ptr [rsp+30h+dwCreationFlags], rax; phkResult
0x1400873db  xor     r8d, r8d; ulOptions
0x1400873de  mov     [rbp+cbData], 0
0x1400873e5  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Fil"...
0x1400873ec  mov     [rbp+phkResult], 0
0x1400873f4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400873fb  call    cs:__imp_RegOpenKeyExW
0x140087402  nop     dword ptr [rax+rax+00h]
0x140087407  mov     ebx, eax
0x140087409  test    eax, eax
0x14008740b  jns     short loc_14008741B
0x14008740d  lea     rcx, [rbp+phkResult]
0x140087411  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140087416  jmp     loc_140087380
0x14008741b  mov     rcx, [rbp+phkResult]; hKey
0x14008741f  lea     rax, [rbp+cbData]
0x140087423  mov     [rsp+30h+lpThreadId], rax; lpcbData
0x140087428  lea     rdx, aMinstorealways; "MinstoreAlwaysCheckpointPageCountThresh"...
0x14008742f  lea     rax, [rbp+Data]
0x140087433  mov     [rbp+Data], 0
0x14008743a  mov     ebx, 4
0x14008743f  mov     qword ptr [rsp+30h+dwCreationFlags], rax; lpData
0x140087444  xor     r9d, r9d; lpType
0x140087447  mov     [rbp+cbData], ebx
0x14008744a  xor     r8d, r8d; lpReserved
0x14008744d  call    cs:__imp_RegQueryValueExW
0x140087454  nop     dword ptr [rax+rax+00h]
0x140087459  test    eax, eax
0x14008745b  js      short loc_14008746A
0x14008745d  mov     eax, [rbp+Data]
0x140087460  test    eax, eax
0x140087462  jz      short loc_14008746A
0x140087464  mov     cs:dword_1402200C8, eax
0x14008746a  mov     rcx, [rbp+phkResult]; hKey
0x14008746e  lea     rax, [rbp+cbData]
0x140087472  mov     [rsp+30h+lpThreadId], rax; lpcbData
0x140087477  lea     rdx, aMinstoredirtyp_0; "MinstoreDirtyPageThreshold"
0x14008747e  lea     rax, [rbp+Data]
0x140087482  mov     [rbp+Data], 0
0x140087489  xor     r9d, r9d; lpType
0x14008748c  mov     qword ptr [rsp+30h+dwCreationFlags], rax; lpData
0x140087491  xor     r8d, r8d; lpReserved
0x140087494  mov     [rbp+cbData], ebx
0x140087497  call    cs:__imp_RegQueryValueExW
0x14008749e  nop     dword ptr [rax+rax+00h]
0x1400874a3  test    eax, eax
0x1400874a5  js      short loc_1400874B5
0x1400874a7  mov     eax, [rbp+Data]
0x1400874aa  mov     cs:qword_14021FDE8, rax
0x1400874b1  test    eax, eax
0x1400874b3  jnz     short loc_1400874C0
0x1400874b5  mov     cs:qword_14021FDE8, 40000h
0x1400874c0  mov     rcx, [rbp+phkResult]; hKey
0x1400874c4  lea     rax, [rbp+cbData]
0x1400874c8  mov     [rsp+30h+lpThreadId], rax; lpcbData
0x1400874cd  lea     rdx, aMinstoredirtyp; "MinstoreDirtyPageTarget"
0x1400874d4  lea     rax, [rbp+Data]
0x1400874d8  mov     [rbp+Data], 0
0x1400874df  xor     r9d, r9d; lpType
0x1400874e2  mov     qword ptr [rsp+30h+dwCreationFlags], rax; lpData
0x1400874e7  xor     r8d, r8d; lpReserved
0x1400874ea  mov     [rbp+cbData], ebx
0x1400874ed  call    cs:__imp_RegQueryValueExW
0x1400874f4  nop     dword ptr [rax+rax+00h]
0x1400874f9  test    eax, eax
0x1400874fb  js      short loc_14008750B
0x1400874fd  mov     eax, [rbp+Data]
0x140087500  mov     cs:qword_14021FDF0, rax
0x140087507  test    eax, eax
0x140087509  jnz     short loc_140087516
0x14008750b  mov     cs:qword_14021FDF0, 20000h
0x140087516  mov     rcx, [rbp+phkResult]; hKey
0x14008751a  lea     rax, [rbp+cbData]
0x14008751e  mov     [rsp+30h+lpThreadId], rax; lpcbData
0x140087523  lea     rdx, aMinstorecleanl_0; "MinstoreCleanLockedCachedPagesThreshold"
0x14008752a  lea     rax, [rbp+Data]
0x14008752e  mov     [rbp+Data], 0
0x140087535  xor     r9d, r9d; lpType
0x140087538  mov     qword ptr [rsp+30h+dwCreationFlags], rax; lpData
0x14008753d  xor     r8d, r8d; lpReserved
0x140087540  mov     [rbp+cbData], ebx
0x140087543  call    cs:__imp_RegQueryValueExW
0x14008754a  nop     dword ptr [rax+rax+00h]
0x14008754f  test    eax, eax
0x140087551  js      short loc_140087561
0x140087553  mov     eax, [rbp+Data]
0x140087556  mov     cs:qword_14021FDF8, rax
0x14008755d  test    eax, eax
0x14008755f  jnz     short loc_14008756C
0x140087561  mov     cs:qword_14021FDF8, 40000h
0x14008756c  mov     rcx, [rbp+phkResult]; hKey
0x140087570  lea     rax, [rbp+cbData]
0x140087574  mov     [rsp+30h+lpThreadId], rax; lpcbData
0x140087579  lea     rdx, aMinstorecleanl; "MinstoreCleanLockedCachedPagesTarget"
0x140087580  lea     rax, [rbp+Data]
0x140087584  mov     [rbp+Data], 0
0x14008758b  xor     r9d, r9d; lpType
0x14008758e  mov     qword ptr [rsp+30h+dwCreationFlags], rax; int
0x140087593  xor     r8d, r8d; lpReserved
0x140087596  mov     [rbp+cbData], ebx
0x140087599  call    cs:__imp_RegQueryValueExW
0x1400875a0  nop     dword ptr [rax+rax+00h]
0x1400875a5  test    eax, eax
0x1400875a7  js      short loc_1400875B7
0x1400875a9  mov     eax, [rbp+Data]
0x1400875ac  mov     cs:qword_14021FE00, rax
0x1400875b3  test    eax, eax
0x1400875b5  jnz     short loc_1400875C2
0x1400875b7  mov     cs:qword_14021FE00, 20000h
0x1400875c2  lea     rcx, [rbp+phkResult]
0x1400875c6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400875cb  call    MsInitializeLibrary
0x1400875d0  mov     ebx, eax
0x1400875d2  test    eax, eax
0x1400875d4  jns     short loc_1400875F3
0x1400875d6  mov     rcx, [rbp+8]; this
0x1400875da  lea     r8, aMinkernelFsMin_5; "minkernel\\fs\\minstore\\usermodeenviro"...
0x1400875e1  mov     r9d, eax; char *
0x1400875e4  mov     edx, 318h; void *
0x1400875e9  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1400875ee  jmp     loc_140087380
0x1400875f3  mov     cs:byte_14021FE30, 1
0x1400875fa  xor     eax, eax
0x1400875fc  mov     rbx, [rsp+30h+arg_18]
0x140087601  add     rsp, 30h
0x140087605  pop     rbp
0x140087606  retn
```
