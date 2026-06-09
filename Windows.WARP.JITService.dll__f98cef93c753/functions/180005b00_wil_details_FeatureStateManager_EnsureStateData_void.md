# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180005b00`
- end: `0x180005f0c`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `1036`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180006050`
- `0x180006410`
- `0x180007030`

## callees

- `0x180001364`
- `0x1800017fc`
- `0x180001e80`
- `0x180002de0`
- `0x180002e24`
- `0x180002e40`
- `0x180003280`
- `0x180003490`
- `0x18000531c`
- `0x180005b00`
- `0x180008a80`
- `0x18000941c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005be2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005be2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e1e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e36`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005c36`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005d3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005dd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005c36`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005d3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005dd6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180005daf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180005daf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005ba1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005ba1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005b62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005b62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ce9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005df0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ce9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005df0`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(RTL_SRWLOCK *this)
{
  DWORD LastError; // r13d
  __int64 v3; // rbx
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v6; // rcx
  void *v7; // rbx
  HANDLE v8; // r15
  int LastErrorFailHr; // r14d
  DWORD v10; // eax
  void *v11; // rdx
  unsigned int v12; // r8d
  const char *v13; // r9
  void *v14; // rsi
  int Pointer; // eax
  unsigned __int64 v16; // r8
  __int64 v17; // r8
  const char *v18; // r9
  __int64 v19; // r8
  const char *v20; // r9
  char *v21; // rax
  unsigned int v22; // r8d
  char *v23; // r12
  unsigned int v24; // r8d
  int v25; // eax
  unsigned int v26; // r8d
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
  const char *v40; // r9
  int v42; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( this[3].Ptr )
    return this[3].Ptr != 0;
  LastError = GetLastError();
  if ( !this[3].Ptr )
  {
    if ( this[2].Ptr )
      goto LABEL_39;
    CurrentProcessId = GetCurrentProcessId();
    StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
    Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
    v7 = Mutex;
    if ( !Mutex )
    {
      v8 = 0;
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v6);
      goto LABEL_7;
    }
    v10 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
    if ( v10 == 258 )
    {
      v14 = 0;
    }
    else
    {
      if ( (v10 & 0xFFFFFF7F) != 0 )
        wil::details::in1diag3::FailFast_Unexpected(retaddr, v11, v12, v13);
      v14 = v7;
    }
    hObject[0] = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, hObject);
    if ( Pointer < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v16, (const char *)(unsigned int)Pointer, 304);
      if ( v14 && !ReleaseMutex(v14) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v17, v18);
      if ( !CloseHandle(v7) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v19, v20);
      goto LABEL_39;
    }
    v8 = hObject[0];
    if ( hObject[0] )
    {
      ++*(_DWORD *)hObject[0];
      goto LABEL_34;
    }
    v8 = 0;
    v21 = (char *)wil::details::ProcessHeapAlloc(8u, 0x130u, v16);
    v23 = v21;
    if ( v21 )
    {
      *(_OWORD *)hObject = 0;
      v25 = wil::details_abi::SemaphoreValue::CreateFromPointer(
              (wil::details_abi::SemaphoreValue *)hObject,
              Name,
              (unsigned __int64)v21);
      LastErrorFailHr = v25;
      if ( v25 >= 0 )
      {
        v36 = *(_OWORD *)hObject;
        *(_DWORD *)v23 = 1;
        *((_QWORD *)v23 + 1) = v7;
        *((_OWORD *)v23 + 1) = v36;
        memset_0(v23 + 40, 0, 0x108u);
        *((_QWORD *)v23 + 4) = 0;
        wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v23 + 40));
        InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v23 + 232), 0, 0);
        v8 = v23;
        *((_QWORD *)v23 + 34) = 0;
        *((_QWORD *)v23 + 35) = 0;
        *((_QWORD *)v23 + 36) = 0;
        *((_QWORD *)v23 + 37) = 0;
        v7 = 0;
LABEL_34:
        if ( v14 && !ReleaseMutex(v14) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
        if ( v7 && !CloseHandle(v7) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
        goto LABEL_8;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v26, (const char *)(unsigned int)v25, 304);
      if ( hObject[1] && !CloseHandle(hObject[1]) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
      if ( hObject[0] && !CloseHandle(hObject[0]) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v23);
    }
    else
    {
      LastErrorFailHr = -2147024882;
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v22, (const char *)0x8007000ELL, 304);
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v24, (const char *)(unsigned int)LastErrorFailHr, v42);
    if ( v14 && !ReleaseMutex(v14) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
    if ( !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
LABEL_7:
    if ( LastErrorFailHr >= 0 )
    {
LABEL_8:
      if ( !this[2].Ptr )
        this[2].Ptr = v8;
    }
LABEL_39:
    v3 = ((__int64)this[2].Ptr + 32) & -(__int64)(this[2].Ptr != 0);
    goto LABEL_40;
  }
  v3 = 0;
LABEL_40:
  AcquireSRWLockExclusive(this + 4);
  if ( !this[3].Ptr )
    this[3].Ptr = (PVOID)v3;
  if ( this != (RTL_SRWLOCK *)-32LL )
    ReleaseSRWLockExclusive(this + 4);
  SetLastError(LastError);
  return this[3].Ptr != 0;
}

```

## disassembly

```asm
0x180005b00  push    rbp
0x180005b02  push    rbx
0x180005b03  push    rsi
0x180005b04  push    rdi
0x180005b05  push    r12
0x180005b07  push    r13
0x180005b09  push    r14
0x180005b0b  push    r15
0x180005b0d  lea     rbp, [rsp-168h]
0x180005b15  sub     rsp, 268h
0x180005b1c  mov     rax, cs:__security_cookie
0x180005b23  xor     rax, rsp
0x180005b26  mov     [rbp+1A0h+var_50], rax
0x180005b2d  xor     r14d, r14d
0x180005b30  mov     rdi, rcx
0x180005b33  cmp     [rcx+18h], r14
0x180005b37  jnz     loc_180005E45
0x180005b3d  call    cs:__imp_GetLastError
0x180005b43  mov     r13d, eax
0x180005b46  cmp     [rdi+18h], r14
0x180005b4a  jz      short loc_180005B54
0x180005b4c  mov     ebx, r14d
0x180005b4f  jmp     loc_180005E17
0x180005b54  cmp     [rdi+10h], r14
0x180005b58  jnz     loc_180005E06
0x180005b5e  mov     rbx, [rdi+8]
0x180005b62  call    cs:__imp_GetCurrentProcessId
0x180005b68  mov     r12d, 130h
0x180005b6e  mov     [rsp+2A0h+var_278], rbx
0x180005b73  mov     r9d, eax
0x180005b76  mov     [rsp+2A0h+var_280], r12d; int
0x180005b7b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005b82  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x180005b87  lea     edx, [r12-2Ch]; unsigned __int64
0x180005b8c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005b91  mov     r9d, 1F0001h; dwDesiredAccess
0x180005b97  lea     rdx, [rsp+2A0h+Name]; lpName
0x180005b9c  xor     r8d, r8d; dwFlags
0x180005b9f  xor     ecx, ecx; lpMutexAttributes
0x180005ba1  call    cs:__imp_CreateMutexExW
0x180005ba7  mov     rbx, rax
0x180005baa  test    rax, rax
0x180005bad  jnz     short loc_180005BD9
0x180005baf  mov     r15, r14
0x180005bb2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005bb7  mov     r14d, eax
0x180005bba  test    r14d, r14d
0x180005bbd  js      loc_180005E03
0x180005bc3  xor     r14d, r14d
0x180005bc6  cmp     [rdi+10h], r14
0x180005bca  jnz     loc_180005E06
0x180005bd0  mov     [rdi+10h], r15
0x180005bd4  jmp     loc_180005E06
0x180005bd9  xor     r8d, r8d; bAlertable
0x180005bdc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005bdf  mov     rcx, rbx; hHandle
0x180005be2  call    cs:__imp_WaitForSingleObjectEx
0x180005be8  cmp     eax, 102h
0x180005bed  jz      short loc_180005BFF
0x180005bef  test    eax, 0FFFFFF7Fh
0x180005bf4  jnz     loc_180005EB7
0x180005bfa  mov     rsi, rbx
0x180005bfd  jmp     short loc_180005C02
0x180005bff  mov     rsi, r14
0x180005c02  lea     rdx, [rsp+2A0h+hObject]; void **
0x180005c07  mov     [rsp+2A0h+hObject], r14
0x180005c0c  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x180005c11  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180005c16  test    eax, eax
0x180005c18  jns     short loc_180005C5A
0x180005c1a  mov     rcx, [rbp+1A8h]; this
0x180005c21  mov     r9d, eax; char *
0x180005c24  mov     edx, 12Eh; void *
0x180005c29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c2e  test    rsi, rsi
0x180005c31  jz      short loc_180005C44
0x180005c33  mov     rcx, rsi; hMutex
0x180005c36  call    cs:__imp_ReleaseMutex
0x180005c3c  test    eax, eax
0x180005c3e  jz      loc_180005EC4
0x180005c44  mov     rcx, rbx; hObject
0x180005c47  call    cs:__imp_CloseHandle
0x180005c4d  test    eax, eax
0x180005c4f  jz      loc_180005E81
0x180005c55  jmp     loc_180005E06
0x180005c5a  mov     r15, [rsp+2A0h+hObject]
0x180005c5f  test    r15, r15
0x180005c62  jz      short loc_180005C71
0x180005c64  mov     eax, [r15]
0x180005c67  inc     eax
0x180005c69  mov     [r15], eax
0x180005c6c  jmp     loc_180005DCE
0x180005c71  mov     rdx, r12; dwBytes
0x180005c74  mov     ecx, 8; dwFlags
0x180005c79  mov     r15, r14
0x180005c7c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005c81  mov     r12, rax
0x180005c84  test    rax, rax
0x180005c87  jnz     short loc_180005CA5
0x180005c89  mov     rcx, [rbp+1A8h]; this
0x180005c90  mov     r14d, 8007000Eh
0x180005c96  mov     r9d, r14d; char *
0x180005c99  mov     edx, 14Bh; void *
0x180005c9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005ca3  jmp     short loc_180005D23
0x180005ca5  xorps   xmm0, xmm0
0x180005ca8  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x180005cad  mov     r8, r12; void *
0x180005cb0  lea     rcx, [rsp+2A0h+hObject]; this
0x180005cb5  movdqu  xmmword ptr [rsp+2A0h+hObject], xmm0
0x180005cbb  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180005cc0  mov     r14d, eax
0x180005cc3  test    eax, eax
0x180005cc5  jns     loc_180005D63
0x180005ccb  mov     rcx, [rbp+1A8h]; this
0x180005cd2  mov     r9d, eax; char *
0x180005cd5  mov     edx, 14Eh; void *
0x180005cda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005cdf  mov     rcx, [rsp+2A0h+hObject+8]; hObject
0x180005ce4  test    rcx, rcx
0x180005ce7  jz      short loc_180005CF7
0x180005ce9  call    cs:__imp_CloseHandle
0x180005cef  test    eax, eax
0x180005cf1  jz      loc_180005ED6
0x180005cf7  mov     rcx, [rsp+2A0h+hObject]; hObject
0x180005cfc  test    rcx, rcx
0x180005cff  jz      short loc_180005D0F
0x180005d01  call    cs:__imp_CloseHandle
0x180005d07  test    eax, eax
0x180005d09  jz      loc_180005EE8
0x180005d0f  call    cs:__imp_GetProcessHeap
0x180005d15  mov     r8, r12; lpMem
0x180005d18  xor     edx, edx; dwFlags
0x180005d1a  mov     rcx, rax; hHeap
0x180005d1d  call    cs:__imp_HeapFree
0x180005d23  mov     rcx, [rbp+1A8h]; this
0x180005d2a  mov     r9d, r14d; char *
0x180005d2d  mov     edx, 137h; void *
0x180005d32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005d37  test    rsi, rsi
0x180005d3a  jz      short loc_180005D4D
0x180005d3c  mov     rcx, rsi; hMutex
0x180005d3f  call    cs:__imp_ReleaseMutex
0x180005d45  test    eax, eax
0x180005d47  jz      loc_180005EFA
0x180005d4d  mov     rcx, rbx; hObject
0x180005d50  call    cs:__imp_CloseHandle
0x180005d56  test    eax, eax
0x180005d58  jz      loc_180005E93
0x180005d5e  jmp     loc_180005BBA
0x180005d63  movups  xmm0, xmmword ptr [rsp+2A0h+hObject]
0x180005d68  lea     rcx, [r12+28h]; void *
0x180005d6d  mov     dword ptr [r12], 1
0x180005d75  xor     edx, edx; Val
0x180005d77  mov     [r12+8], rbx
0x180005d7c  mov     r8d, 108h; Size
0x180005d82  movdqu  xmmword ptr [r12+10h], xmm0
0x180005d89  call    memset_0
0x180005d8e  xor     eax, eax
0x180005d90  lea     rcx, [r12+28h]; this
0x180005d95  mov     [r12+20h], rax
0x180005d9a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180005d9f  lea     rbx, [r12+0E8h]
0x180005da7  xor     r8d, r8d; Flags
0x180005daa  mov     rcx, rbx; lpCriticalSection
0x180005dad  xor     edx, edx; dwSpinCount
0x180005daf  call    cs:__imp_InitializeCriticalSectionEx
0x180005db5  xor     r14d, r14d
0x180005db8  mov     r15, r12
0x180005dbb  mov     [rbx+28h], r14
0x180005dbf  mov     [rbx+30h], r14
0x180005dc3  mov     [rbx+38h], r14
0x180005dc7  mov     [rbx+40h], r14
0x180005dcb  mov     ebx, r14d
0x180005dce  test    rsi, rsi
0x180005dd1  jz      short loc_180005DE4
0x180005dd3  mov     rcx, rsi; hMutex
0x180005dd6  call    cs:__imp_ReleaseMutex
0x180005ddc  test    eax, eax
0x180005dde  jz      loc_180005E6F
0x180005de4  test    rbx, rbx
0x180005de7  jz      loc_180005BC6
0x180005ded  mov     rcx, rbx; hObject
0x180005df0  call    cs:__imp_CloseHandle
0x180005df6  test    eax, eax
0x180005df8  jz      loc_180005EA5
0x180005dfe  jmp     loc_180005BC6
0x180005e03  xor     r14d, r14d
0x180005e06  mov     rax, [rdi+10h]
0x180005e0a  lea     rcx, [rax+20h]
0x180005e0e  neg     rax
0x180005e11  sbb     rbx, rbx
0x180005e14  and     rbx, rcx
0x180005e17  lea     rsi, [rdi+20h]
0x180005e1b  mov     rcx, rsi; SRWLock
0x180005e1e  call    cs:__imp_AcquireSRWLockExclusive
0x180005e24  cmp     [rdi+18h], r14
0x180005e28  jnz     short loc_180005E2E
0x180005e2a  mov     [rdi+18h], rbx
0x180005e2e  test    rsi, rsi
0x180005e31  jz      short loc_180005E3C
0x180005e33  mov     rcx, rsi; SRWLock
0x180005e36  call    cs:__imp_ReleaseSRWLockExclusive
0x180005e3c  mov     ecx, r13d; dwErrCode
0x180005e3f  call    cs:__imp_SetLastError
0x180005e45  cmp     [rdi+18h], r14
0x180005e49  setnz   al
0x180005e4c  mov     rcx, [rbp+1A0h+var_50]
0x180005e53  xor     rcx, rsp; StackCookie
0x180005e56  call    __security_check_cookie
0x180005e5b  add     rsp, 268h
0x180005e62  pop     r15
0x180005e64  pop     r14
0x180005e66  pop     r13
0x180005e68  pop     r12
0x180005e6a  pop     rdi
0x180005e6b  pop     rsi
0x180005e6c  pop     rbx
0x180005e6d  pop     rbp
0x180005e6e  retn
0x180005e6f  mov     rcx, [rbp+1A8h]; this
0x180005e76  mov     edx, 0A15h; void *
0x180005e7b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e81  mov     rcx, [rbp+1A8h]; this
0x180005e88  mov     edx, 0A0Bh; void *
0x180005e8d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e93  mov     rcx, [rbp+1A8h]; this
0x180005e9a  mov     edx, 0A0Bh; void *
0x180005e9f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005ea5  mov     rcx, [rbp+1A8h]; this
0x180005eac  mov     edx, 0A0Bh; void *
0x180005eb1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005eb7  mov     rcx, [rbp+1A8h]; this
0x180005ebe  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005ec4  mov     rcx, [rbp+1A8h]; this
0x180005ecb  mov     edx, 0A15h; void *
0x180005ed0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005ed6  mov     rcx, [rbp+1A8h]; this
0x180005edd  mov     edx, 0A0Bh; void *
0x180005ee2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005ee8  mov     rcx, [rbp+1A8h]; this
0x180005eef  mov     edx, 0A0Bh; void *
0x180005ef4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005efa  mov     rcx, [rbp+1A8h]; this
0x180005f01  mov     edx, 0A15h; void *
0x180005f06  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
