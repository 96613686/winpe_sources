# AipGetSessionLock(ulong,int,_SESSION_LOCK * *)

- ea: `0x18000ce00`
- end: `0x18000d036`
- name: `?AipGetSessionLock@@YAKKHPEAPEAU_SESSION_LOCK@@@Z`
- size: `566`
- prototype: `__int64 __fastcall(unsigned int, int, struct _SESSION_LOCK **)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ccf0`
- `0x18001e2a8`
- `0x18001e3d0`
- `0x1800277b0`
- `0x1800290b4`

## callees

- `0x18000ce00`
- `0x180046e02`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000cec0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000cfc5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000cec0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000cfc5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000cffb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000cffb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d006`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cf25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cf25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d01b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d01b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ce4c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cea6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ce4c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cea6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000ce6b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000cfb3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000ce6b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000cfb3`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000cf87`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000cf87`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000cfa1`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000cfa1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000cf75`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000cfe3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000cf75`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000cfe3`

## pseudocode

```c
__int64 __fastcall AipGetSessionLock(unsigned int a1, int a2, struct _SESSION_LOCK **a3)
{
  char *v3; // rdi
  DWORD LastError; // ebp
  __int64 v8; // r15
  HLOCAL v9; // rax
  HANDLE **v10; // rbp
  _QWORD *v11; // rax
  unsigned int i; // ebx
  HLOCAL *v13; // rsi
  HANDLE *v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rbx

  v3 = 0;
  *a3 = 0;
  if ( !a1 )
  {
    LastError = 1459;
    goto LABEL_33;
  }
  LastError = 0;
  if ( a1 <= g_dwSessions )
  {
    _mm_lfence();
    RtlAcquireSRWLockShared(&g_SessionListLock);
    v16 = *((_QWORD *)g_SessionLocks + a1 - 1);
    RtlReleaseSRWLockShared(&g_SessionListLock);
    if ( !*(_QWORD *)v16 )
    {
      RtlAcquireSRWLockExclusive(&g_SessionListLock);
      if ( !*(_QWORD *)v16 )
      {
        *(_QWORD *)v16 = CreateMutexW(0, 0, 0); // Object namespace audit: session lock mutex is unnamed; no Global/Local fixed-name squatting surface.
        *(_QWORD *)(v16 + 24) = v16 + 16;
        *(_QWORD *)(v16 + 16) = v16 + 16;
        *(_DWORD *)(v16 + 8) = 0;
      }
      RtlReleaseSRWLockExclusive(&g_SessionListLock);
      if ( !*(_QWORD *)v16 )
      {
LABEL_31:
        LastError = GetLastError();
        goto LABEL_33;
      }
    }
LABEL_29:
    if ( !a2 || WaitForSingleObject(*(HANDLE *)v16, 0xFFFFFFFF) != -1 )
    {
      *a3 = (struct _SESSION_LOCK *)v16;
      goto LABEL_33;
    }
    goto LABEL_31;
  }
  v3 = (char *)LocalAlloc(0x40u, 8LL * a1);
  if ( !v3 )
  {
    LastError = 8;
    goto LABEL_33;
  }
  RtlAcquireSRWLockExclusive(&g_SessionListLock);
  v8 = g_dwSessions;
  if ( a1 <= g_dwSessions )
  {
    v15 = g_SessionLocks;
LABEL_24:
    v16 = v15[a1 - 1];
    RtlReleaseSRWLockExclusive(&g_SessionListLock);
    goto LABEL_29;
  }
  memcpy_0(v3, g_SessionLocks, 8LL * g_dwSessions);
  while ( (unsigned int)v8 < a1 )
  {
    v9 = LocalAlloc(0x40u, 0x20u);
    *(_QWORD *)&v3[8 * v8] = v9;
    v10 = (HANDLE **)&v3[8 * v8];
    if ( !v9 )
    {
      LastError = 8;
      goto LABEL_15;
    }
    **v10 = CreateMutexW(0, 0, 0);
    if ( !**v10 )
    {
      LastError = GetLastError();
      goto LABEL_15;
    }
    v11 = *v10 + 2;
    v8 = (unsigned int)(v8 + 1);
    v11[1] = v11;
    *v11 = v11;
  }
  LastError = 0;
  if ( (_DWORD)v8 == a1 )
  {
    LocalFree(g_SessionLocks);
    v15 = v3;
    g_dwSessions = a1;
    g_SessionLocks = v3;
    v3 = 0;
    goto LABEL_24;
  }
LABEL_15:
  for ( i = g_dwSessions; i <= (unsigned int)v8; ++i )
  {
    v13 = (HLOCAL *)&v3[8 * i];
    v14 = (HANDLE *)*v13;
    if ( *v13 )
    {
      if ( *v14 )
        CloseHandle(*v14);
      LocalFree(*v13);
    }
  }
LABEL_33:
  LocalFree(v3);
  return LastError;
}

```

## disassembly

```asm
0x18000ce00  mov     [rsp+arg_8], rbx
0x18000ce05  mov     [rsp+arg_10], rbp
0x18000ce0a  push    rsi
0x18000ce0b  push    rdi
0x18000ce0c  push    r14
0x18000ce0e  sub     rsp, 20h
0x18000ce12  xor     edi, edi
0x18000ce14  mov     ebx, ecx
0x18000ce16  mov     [r8], rdi
0x18000ce19  mov     rsi, r8
0x18000ce1c  mov     r14d, edx
0x18000ce1f  test    ecx, ecx
0x18000ce21  jnz     short loc_18000CE2D
0x18000ce23  mov     ebp, 5B3h
0x18000ce28  jmp     loc_18000D018
0x18000ce2d  xor     ebp, ebp
0x18000ce2f  mov     [rsp+38h+arg_0], r15
0x18000ce34  cmp     ebx, cs:?g_dwSessions@@3KA; ulong g_dwSessions
0x18000ce3a  jbe     loc_18000CF7D
0x18000ce40  mov     rdx, rbx
0x18000ce43  mov     ecx, 40h ; '@'; uFlags
0x18000ce48  shl     rdx, 3; uBytes
0x18000ce4c  call    cs:__imp_LocalAlloc
0x18000ce52  mov     rdi, rax
0x18000ce55  test    rax, rax
0x18000ce58  jnz     short loc_18000CE64
0x18000ce5a  mov     ebp, 8
0x18000ce5f  jmp     loc_18000D013
0x18000ce64  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000ce6b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000ce71  mov     r15d, cs:?g_dwSessions@@3KA; ulong g_dwSessions
0x18000ce78  cmp     ebx, r15d
0x18000ce7b  jbe     loc_18000CF61
0x18000ce81  mov     rdx, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; Src
0x18000ce88  mov     r8d, r15d
0x18000ce8b  shl     r8, 3; Size
0x18000ce8f  mov     rcx, rdi; void *
0x18000ce92  call    memcpy_0
0x18000ce97  cmp     r15d, ebx
0x18000ce9a  jnb     short loc_18000CEF8
0x18000ce9c  mov     edx, 20h ; ' '; uBytes
0x18000cea1  mov     ecx, 40h ; '@'; uFlags
0x18000cea6  call    cs:__imp_LocalAlloc
0x18000ceac  mov     [rdi+r15*8], rax
0x18000ceb0  lea     rbp, [rdi+r15*8]
0x18000ceb4  test    rax, rax
0x18000ceb7  jz      short loc_18000CEF1
0x18000ceb9  xor     r8d, r8d; lpName
0x18000cebc  xor     edx, edx; bInitialOwner
0x18000cebe  xor     ecx, ecx; lpMutexAttributes
0x18000cec0  call    cs:__imp_CreateMutexW
0x18000cec6  mov     rcx, [rbp+0]
0x18000ceca  mov     [rcx], rax
0x18000cecd  mov     rax, [rbp+0]
0x18000ced1  cmp     qword ptr [rax], 0
0x18000ced5  jz      short loc_18000CEE7
0x18000ced7  add     rax, 10h
0x18000cedb  inc     r15d
0x18000cede  mov     [rax+8], rax
0x18000cee2  mov     [rax], rax
0x18000cee5  jmp     short loc_18000CE97
0x18000cee7  call    cs:__imp_GetLastError
0x18000ceed  mov     ebp, eax
0x18000ceef  jmp     short loc_18000CEFF
0x18000cef1  mov     ebp, 8
0x18000cef6  jmp     short loc_18000CEFF
0x18000cef8  xor     ebp, ebp
0x18000cefa  cmp     r15d, ebx
0x18000cefd  jz      short loc_18000CF40
0x18000ceff  mov     ebx, cs:?g_dwSessions@@3KA; ulong g_dwSessions
0x18000cf05  cmp     ebx, r15d
0x18000cf08  ja      loc_18000D013
0x18000cf0e  mov     eax, ebx
0x18000cf10  lea     rsi, [rdi+rax*8]
0x18000cf14  mov     rax, [rdi+rax*8]
0x18000cf18  test    rax, rax
0x18000cf1b  jz      short loc_18000CF34
0x18000cf1d  mov     rcx, [rax]; hObject
0x18000cf20  test    rcx, rcx
0x18000cf23  jz      short loc_18000CF2B
0x18000cf25  call    cs:__imp_CloseHandle
0x18000cf2b  mov     rcx, [rsi]; hMem
0x18000cf2e  call    cs:__imp_LocalFree
0x18000cf34  inc     ebx
0x18000cf36  cmp     ebx, r15d
0x18000cf39  jbe     short loc_18000CF0E
0x18000cf3b  jmp     loc_18000D013
0x18000cf40  mov     rcx, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; hMem
0x18000cf47  call    cs:__imp_LocalFree
0x18000cf4d  mov     rcx, rdi
0x18000cf50  mov     cs:?g_dwSessions@@3KA, ebx; ulong g_dwSessions
0x18000cf56  mov     cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA, rcx; _SESSION_LOCK * * g_SessionLocks
0x18000cf5d  xor     edi, edi
0x18000cf5f  jmp     short loc_18000CF68
0x18000cf61  mov     rcx, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; _SESSION_LOCK * * g_SessionLocks
0x18000cf68  dec     ebx
0x18000cf6a  mov     rbx, [rcx+rbx*8]
0x18000cf6e  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000cf75  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000cf7b  jmp     short loc_18000CFEE
0x18000cf7d  lfence
0x18000cf80  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000cf87  call    cs:__imp_RtlAcquireSRWLockShared
0x18000cf8d  mov     rax, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; _SESSION_LOCK * * g_SessionLocks
0x18000cf94  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000cf9b  dec     ebx
0x18000cf9d  mov     rbx, [rax+rbx*8]
0x18000cfa1  call    cs:__imp_RtlReleaseSRWLockShared
0x18000cfa7  cmp     [rbx], rdi
0x18000cfaa  jnz     short loc_18000CFEE
0x18000cfac  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000cfb3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000cfb9  cmp     [rbx], rdi
0x18000cfbc  jnz     short loc_18000CFDC
0x18000cfbe  xor     r8d, r8d; lpName
0x18000cfc1  xor     edx, edx; bInitialOwner
0x18000cfc3  xor     ecx, ecx; lpMutexAttributes
0x18000cfc5  call    cs:__imp_CreateMutexW
0x18000cfcb  mov     [rbx], rax; Object namespace audit: session lock mutex is unnamed; no Global/Local fixed-name squatting surface.
0x18000cfce  lea     rax, [rbx+10h]
0x18000cfd2  mov     [rax+8], rax
0x18000cfd6  mov     [rax], rax
0x18000cfd9  mov     [rbx+8], edi
0x18000cfdc  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000cfe3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000cfe9  cmp     [rbx], rdi
0x18000cfec  jz      short loc_18000D006
0x18000cfee  test    r14d, r14d
0x18000cff1  jz      short loc_18000D010
0x18000cff3  mov     rcx, [rbx]; hHandle
0x18000cff6  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000cffb  call    cs:__imp_WaitForSingleObject
0x18000d001  cmp     eax, 0FFFFFFFFh
0x18000d004  jnz     short loc_18000D010
0x18000d006  call    cs:__imp_GetLastError
0x18000d00c  mov     ebp, eax
0x18000d00e  jmp     short loc_18000D013
0x18000d010  mov     [rsi], rbx
0x18000d013  mov     r15, [rsp+38h+arg_0]
0x18000d018  mov     rcx, rdi; hMem
0x18000d01b  call    cs:__imp_LocalFree
0x18000d021  mov     rbx, [rsp+38h+arg_8]
0x18000d026  mov     eax, ebp
0x18000d028  mov     rbp, [rsp+38h+arg_10]
0x18000d02d  add     rsp, 20h
0x18000d031  pop     r14
0x18000d033  pop     rdi
0x18000d034  pop     rsi
0x18000d035  retn
```
