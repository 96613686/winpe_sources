# AipGetSessionLock(ulong,int,_SESSION_LOCK * *)

- ea: `0x18000da00`
- end: `0x18000dc9f`
- name: `?AipGetSessionLock@@YAKKHPEAPEAU_SESSION_LOCK@@@Z`
- size: `671`
- prototype: `unsigned int __fastcall(unsigned int, int, struct _SESSION_LOCK **)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d8e0`
- `0x180024a98`
- `0x180024e9c`
- `0x180024f2c`
- `0x1800252b0`

## callees

- `0x18000da00`
- `0x1800449e2`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000dc51`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000dc51`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000dace`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000dc0f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000dace`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000dc0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dafe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dafe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc7d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000da4c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000daae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000da4c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000daae`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000da6f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000dbf7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000da6f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000dbf7`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000dbbf`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000dbbf`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000dbdf`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000dbdf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dba4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dc33`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dba4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dc33`

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
  void **v13; // rcx
  void *v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rbx

  v3 = 0;
  LastError = 0;
  *a3 = 0;
  if ( !a1 )
  {
    LastError = 1459;
    goto LABEL_33;
  }
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
        *(_QWORD *)v16 = CreateMutexW(0, 0, 0);
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
    v13 = *(void ***)&v3[8 * i];
    if ( v13 )
    {
      v14 = *v13;
      if ( v14 )
        CloseHandle(v14);
      LocalFree(*(HLOCAL *)&v3[8 * i]);
    }
  }
LABEL_33:
  LocalFree(v3);
  return LastError;
}

```

## disassembly

```asm
0x18000da00  mov     [rsp+arg_8], rbx
0x18000da05  mov     [rsp+arg_10], rbp
0x18000da0a  push    rsi
0x18000da0b  push    rdi
0x18000da0c  push    r14
0x18000da0e  sub     rsp, 20h
0x18000da12  xor     edi, edi
0x18000da14  mov     ebx, ecx
0x18000da16  xor     ebp, ebp
0x18000da18  mov     [r8], rdi
0x18000da1b  mov     rsi, r8
0x18000da1e  mov     r14d, edx
0x18000da21  test    ecx, ecx
0x18000da23  jnz     short loc_18000DA2F
0x18000da25  mov     ebp, 5B3h
0x18000da2a  jmp     loc_18000DC7A
0x18000da2f  cmp     ebx, cs:?g_dwSessions@@3KA; ulong g_dwSessions
0x18000da35  mov     [rsp+38h+arg_0], r15
0x18000da3a  jbe     loc_18000DBB5
0x18000da40  mov     rdx, rbx
0x18000da43  mov     ecx, 40h ; '@'; uFlags
0x18000da48  shl     rdx, 3; uBytes
0x18000da4c  call    cs:__imp_LocalAlloc
0x18000da53  nop     dword ptr [rax+rax+00h]
0x18000da58  mov     rdi, rax
0x18000da5b  test    rax, rax
0x18000da5e  jnz     short loc_18000DA68
0x18000da60  lea     ebp, [rax+8]
0x18000da63  jmp     loc_18000DC75
0x18000da68  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000da6f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000da76  nop     dword ptr [rax+rax+00h]
0x18000da7b  mov     r15d, cs:?g_dwSessions@@3KA; ulong g_dwSessions
0x18000da82  cmp     ebx, r15d
0x18000da85  jbe     loc_18000DB90
0x18000da8b  mov     rdx, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; Src
0x18000da92  mov     r8d, r15d
0x18000da95  shl     r8, 3; Size
0x18000da99  mov     rcx, rdi; void *
0x18000da9c  call    memcpy_0
0x18000daa1  cmp     r15d, ebx
0x18000daa4  jnb     short loc_18000DB15
0x18000daa6  mov     edx, 20h ; ' '; uBytes
0x18000daab  lea     ecx, [rdx+20h]; uFlags
0x18000daae  call    cs:__imp_LocalAlloc
0x18000dab5  nop     dword ptr [rax+rax+00h]
0x18000daba  mov     [rdi+r15*8], rax
0x18000dabe  lea     rbp, [rdi+r15*8]
0x18000dac2  test    rax, rax
0x18000dac5  jz      short loc_18000DB0E
0x18000dac7  xor     r8d, r8d; lpName
0x18000daca  xor     edx, edx; bInitialOwner
0x18000dacc  xor     ecx, ecx; lpMutexAttributes
0x18000dace  call    cs:__imp_CreateMutexW
0x18000dad5  nop     dword ptr [rax+rax+00h]
0x18000dada  mov     rcx, rax
0x18000dadd  mov     rax, [rbp+0]
0x18000dae1  mov     [rax], rcx
0x18000dae4  mov     rax, [rbp+0]
0x18000dae8  cmp     qword ptr [rax], 0
0x18000daec  jz      short loc_18000DAFE
0x18000daee  add     rax, 10h
0x18000daf2  inc     r15d
0x18000daf5  mov     [rax+8], rax
0x18000daf9  mov     [rax], rax
0x18000dafc  jmp     short loc_18000DAA1
0x18000dafe  call    cs:__imp_GetLastError
0x18000db05  nop     dword ptr [rax+rax+00h]
0x18000db0a  mov     ebp, eax
0x18000db0c  jmp     short loc_18000DB1C
0x18000db0e  mov     ebp, 8
0x18000db13  jmp     short loc_18000DB1C
0x18000db15  xor     ebp, ebp
0x18000db17  cmp     r15d, ebx
0x18000db1a  jz      short loc_18000DB69
0x18000db1c  mov     ebx, cs:?g_dwSessions@@3KA; ulong g_dwSessions
0x18000db22  cmp     ebx, r15d
0x18000db25  ja      loc_18000DC75
0x18000db2b  mov     eax, ebx
0x18000db2d  mov     rcx, [rdi+rax*8]
0x18000db31  lea     rsi, [rdi+rax*8]
0x18000db35  test    rcx, rcx
0x18000db38  jz      short loc_18000DB5D
0x18000db3a  mov     rcx, [rcx]; hObject
0x18000db3d  test    rcx, rcx
0x18000db40  jz      short loc_18000DB4E
0x18000db42  call    cs:__imp_CloseHandle
0x18000db49  nop     dword ptr [rax+rax+00h]
0x18000db4e  mov     rcx, [rsi]; hMem
0x18000db51  call    cs:__imp_LocalFree
0x18000db58  nop     dword ptr [rax+rax+00h]
0x18000db5d  inc     ebx
0x18000db5f  cmp     ebx, r15d
0x18000db62  jbe     short loc_18000DB2B
0x18000db64  jmp     loc_18000DC75
0x18000db69  mov     rcx, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; hMem
0x18000db70  call    cs:__imp_LocalFree
0x18000db77  nop     dword ptr [rax+rax+00h]
0x18000db7c  mov     rcx, rdi
0x18000db7f  mov     cs:?g_dwSessions@@3KA, ebx; ulong g_dwSessions
0x18000db85  mov     cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA, rcx; _SESSION_LOCK * * g_SessionLocks
0x18000db8c  xor     edi, edi
0x18000db8e  jmp     short loc_18000DB97
0x18000db90  mov     rcx, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; _SESSION_LOCK * * g_SessionLocks
0x18000db97  dec     ebx
0x18000db99  mov     rbx, [rcx+rbx*8]
0x18000db9d  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000dba4  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000dbab  nop     dword ptr [rax+rax+00h]
0x18000dbb0  jmp     loc_18000DC44
0x18000dbb5  lfence
0x18000dbb8  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000dbbf  call    cs:__imp_RtlAcquireSRWLockShared
0x18000dbc6  nop     dword ptr [rax+rax+00h]
0x18000dbcb  mov     rax, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; _SESSION_LOCK * * g_SessionLocks
0x18000dbd2  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000dbd9  dec     ebx
0x18000dbdb  mov     rbx, [rax+rbx*8]
0x18000dbdf  call    cs:__imp_RtlReleaseSRWLockShared
0x18000dbe6  nop     dword ptr [rax+rax+00h]
0x18000dbeb  cmp     [rbx], rdi
0x18000dbee  jnz     short loc_18000DC44
0x18000dbf0  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000dbf7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000dbfe  nop     dword ptr [rax+rax+00h]
0x18000dc03  cmp     [rbx], rdi
0x18000dc06  jnz     short loc_18000DC2C
0x18000dc08  xor     r8d, r8d; lpName
0x18000dc0b  xor     edx, edx; bInitialOwner
0x18000dc0d  xor     ecx, ecx; lpMutexAttributes
0x18000dc0f  call    cs:__imp_CreateMutexW
0x18000dc16  nop     dword ptr [rax+rax+00h]
0x18000dc1b  mov     [rbx], rax
0x18000dc1e  lea     rax, [rbx+10h]
0x18000dc22  mov     [rax+8], rax
0x18000dc26  mov     [rax], rax
0x18000dc29  mov     [rbx+8], edi
0x18000dc2c  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000dc33  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000dc3a  nop     dword ptr [rax+rax+00h]
0x18000dc3f  cmp     [rbx], rdi
0x18000dc42  jz      short loc_18000DC62
0x18000dc44  test    r14d, r14d
0x18000dc47  jz      short loc_18000DC72
0x18000dc49  mov     rcx, [rbx]; hHandle
0x18000dc4c  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000dc51  call    cs:__imp_WaitForSingleObject
0x18000dc58  nop     dword ptr [rax+rax+00h]
0x18000dc5d  cmp     eax, 0FFFFFFFFh
0x18000dc60  jnz     short loc_18000DC72
0x18000dc62  call    cs:__imp_GetLastError
0x18000dc69  nop     dword ptr [rax+rax+00h]
0x18000dc6e  mov     ebp, eax
0x18000dc70  jmp     short loc_18000DC75
0x18000dc72  mov     [rsi], rbx
0x18000dc75  mov     r15, [rsp+38h+arg_0]
0x18000dc7a  mov     rcx, rdi; hMem
0x18000dc7d  call    cs:__imp_LocalFree
0x18000dc84  nop     dword ptr [rax+rax+00h]
0x18000dc89  mov     rbx, [rsp+38h+arg_8]
0x18000dc8e  mov     eax, ebp
0x18000dc90  mov     rbp, [rsp+38h+arg_10]
0x18000dc95  add     rsp, 20h
0x18000dc99  pop     r14
0x18000dc9b  pop     rdi
0x18000dc9c  pop     rsi
0x18000dc9d  retn
```
