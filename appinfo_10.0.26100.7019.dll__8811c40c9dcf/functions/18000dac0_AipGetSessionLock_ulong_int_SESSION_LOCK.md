# AipGetSessionLock(ulong,int,_SESSION_LOCK * *)

- ea: `0x18000dac0`
- end: `0x18000dd5f`
- name: `?AipGetSessionLock@@YAKKHPEAPEAU_SESSION_LOCK@@@Z`
- size: `671`
- prototype: `unsigned int __fastcall(unsigned int, int, struct _SESSION_LOCK **)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d9a0`
- `0x1800263a8`
- `0x180026790`
- `0x180026820`
- `0x180026ba0`

## callees

- `0x18000dac0`
- `0x180042912`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000db8e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000dccf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000db8e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000dccf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000dd11`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000dd11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dd3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dd3d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db0c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db0c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db6e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000dc7f`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000dc7f`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000dc9f`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000dc9f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000db2f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000dcb7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000db2f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000dcb7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dc64`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dcf3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dc64`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dcf3`

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
0x18000dac0  mov     [rsp+arg_8], rbx
0x18000dac5  mov     [rsp+arg_10], rbp
0x18000daca  push    rsi
0x18000dacb  push    rdi
0x18000dacc  push    r14
0x18000dace  sub     rsp, 20h
0x18000dad2  xor     edi, edi
0x18000dad4  mov     ebx, ecx
0x18000dad6  xor     ebp, ebp
0x18000dad8  mov     [r8], rdi
0x18000dadb  mov     rsi, r8
0x18000dade  mov     r14d, edx
0x18000dae1  test    ecx, ecx
0x18000dae3  jnz     short loc_18000DAEF
0x18000dae5  mov     ebp, 5B3h
0x18000daea  jmp     loc_18000DD3A
0x18000daef  cmp     ebx, cs:?g_dwSessions@@3KA; ulong g_dwSessions
0x18000daf5  mov     [rsp+38h+arg_0], r15
0x18000dafa  jbe     loc_18000DC75
0x18000db00  mov     rdx, rbx
0x18000db03  mov     ecx, 40h ; '@'; uFlags
0x18000db08  shl     rdx, 3; uBytes
0x18000db0c  call    cs:__imp_LocalAlloc
0x18000db13  nop     dword ptr [rax+rax+00h]
0x18000db18  mov     rdi, rax
0x18000db1b  test    rax, rax
0x18000db1e  jnz     short loc_18000DB28
0x18000db20  lea     ebp, [rax+8]
0x18000db23  jmp     loc_18000DD35
0x18000db28  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000db2f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000db36  nop     dword ptr [rax+rax+00h]
0x18000db3b  mov     r15d, cs:?g_dwSessions@@3KA; ulong g_dwSessions
0x18000db42  cmp     ebx, r15d
0x18000db45  jbe     loc_18000DC50
0x18000db4b  mov     rdx, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; Src
0x18000db52  mov     r8d, r15d
0x18000db55  shl     r8, 3; Size
0x18000db59  mov     rcx, rdi; void *
0x18000db5c  call    memcpy_0
0x18000db61  cmp     r15d, ebx
0x18000db64  jnb     short loc_18000DBD5
0x18000db66  mov     edx, 20h ; ' '; uBytes
0x18000db6b  lea     ecx, [rdx+20h]; uFlags
0x18000db6e  call    cs:__imp_LocalAlloc
0x18000db75  nop     dword ptr [rax+rax+00h]
0x18000db7a  mov     [rdi+r15*8], rax
0x18000db7e  lea     rbp, [rdi+r15*8]
0x18000db82  test    rax, rax
0x18000db85  jz      short loc_18000DBCE
0x18000db87  xor     r8d, r8d; lpName
0x18000db8a  xor     edx, edx; bInitialOwner
0x18000db8c  xor     ecx, ecx; lpMutexAttributes
0x18000db8e  call    cs:__imp_CreateMutexW
0x18000db95  nop     dword ptr [rax+rax+00h]
0x18000db9a  mov     rcx, rax
0x18000db9d  mov     rax, [rbp+0]
0x18000dba1  mov     [rax], rcx
0x18000dba4  mov     rax, [rbp+0]
0x18000dba8  cmp     qword ptr [rax], 0
0x18000dbac  jz      short loc_18000DBBE
0x18000dbae  add     rax, 10h
0x18000dbb2  inc     r15d
0x18000dbb5  mov     [rax+8], rax
0x18000dbb9  mov     [rax], rax
0x18000dbbc  jmp     short loc_18000DB61
0x18000dbbe  call    cs:__imp_GetLastError
0x18000dbc5  nop     dword ptr [rax+rax+00h]
0x18000dbca  mov     ebp, eax
0x18000dbcc  jmp     short loc_18000DBDC
0x18000dbce  mov     ebp, 8
0x18000dbd3  jmp     short loc_18000DBDC
0x18000dbd5  xor     ebp, ebp
0x18000dbd7  cmp     r15d, ebx
0x18000dbda  jz      short loc_18000DC29
0x18000dbdc  mov     ebx, cs:?g_dwSessions@@3KA; ulong g_dwSessions
0x18000dbe2  cmp     ebx, r15d
0x18000dbe5  ja      loc_18000DD35
0x18000dbeb  mov     eax, ebx
0x18000dbed  mov     rcx, [rdi+rax*8]
0x18000dbf1  lea     rsi, [rdi+rax*8]
0x18000dbf5  test    rcx, rcx
0x18000dbf8  jz      short loc_18000DC1D
0x18000dbfa  mov     rcx, [rcx]; hObject
0x18000dbfd  test    rcx, rcx
0x18000dc00  jz      short loc_18000DC0E
0x18000dc02  call    cs:__imp_CloseHandle
0x18000dc09  nop     dword ptr [rax+rax+00h]
0x18000dc0e  mov     rcx, [rsi]; hMem
0x18000dc11  call    cs:__imp_LocalFree
0x18000dc18  nop     dword ptr [rax+rax+00h]
0x18000dc1d  inc     ebx
0x18000dc1f  cmp     ebx, r15d
0x18000dc22  jbe     short loc_18000DBEB
0x18000dc24  jmp     loc_18000DD35
0x18000dc29  mov     rcx, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; hMem
0x18000dc30  call    cs:__imp_LocalFree
0x18000dc37  nop     dword ptr [rax+rax+00h]
0x18000dc3c  mov     rcx, rdi
0x18000dc3f  mov     cs:?g_dwSessions@@3KA, ebx; ulong g_dwSessions
0x18000dc45  mov     cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA, rcx; _SESSION_LOCK * * g_SessionLocks
0x18000dc4c  xor     edi, edi
0x18000dc4e  jmp     short loc_18000DC57
0x18000dc50  mov     rcx, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; _SESSION_LOCK * * g_SessionLocks
0x18000dc57  dec     ebx
0x18000dc59  mov     rbx, [rcx+rbx*8]
0x18000dc5d  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000dc64  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000dc6b  nop     dword ptr [rax+rax+00h]
0x18000dc70  jmp     loc_18000DD04
0x18000dc75  lfence
0x18000dc78  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000dc7f  call    cs:__imp_RtlAcquireSRWLockShared
0x18000dc86  nop     dword ptr [rax+rax+00h]
0x18000dc8b  mov     rax, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; _SESSION_LOCK * * g_SessionLocks
0x18000dc92  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000dc99  dec     ebx
0x18000dc9b  mov     rbx, [rax+rbx*8]
0x18000dc9f  call    cs:__imp_RtlReleaseSRWLockShared
0x18000dca6  nop     dword ptr [rax+rax+00h]
0x18000dcab  cmp     [rbx], rdi
0x18000dcae  jnz     short loc_18000DD04
0x18000dcb0  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000dcb7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000dcbe  nop     dword ptr [rax+rax+00h]
0x18000dcc3  cmp     [rbx], rdi
0x18000dcc6  jnz     short loc_18000DCEC
0x18000dcc8  xor     r8d, r8d; lpName
0x18000dccb  xor     edx, edx; bInitialOwner
0x18000dccd  xor     ecx, ecx; lpMutexAttributes
0x18000dccf  call    cs:__imp_CreateMutexW
0x18000dcd6  nop     dword ptr [rax+rax+00h]
0x18000dcdb  mov     [rbx], rax
0x18000dcde  lea     rax, [rbx+10h]
0x18000dce2  mov     [rax+8], rax
0x18000dce6  mov     [rax], rax
0x18000dce9  mov     [rbx+8], edi
0x18000dcec  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x18000dcf3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000dcfa  nop     dword ptr [rax+rax+00h]
0x18000dcff  cmp     [rbx], rdi
0x18000dd02  jz      short loc_18000DD22
0x18000dd04  test    r14d, r14d
0x18000dd07  jz      short loc_18000DD32
0x18000dd09  mov     rcx, [rbx]; hHandle
0x18000dd0c  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000dd11  call    cs:__imp_WaitForSingleObject
0x18000dd18  nop     dword ptr [rax+rax+00h]
0x18000dd1d  cmp     eax, 0FFFFFFFFh
0x18000dd20  jnz     short loc_18000DD32
0x18000dd22  call    cs:__imp_GetLastError
0x18000dd29  nop     dword ptr [rax+rax+00h]
0x18000dd2e  mov     ebp, eax
0x18000dd30  jmp     short loc_18000DD35
0x18000dd32  mov     [rsi], rbx
0x18000dd35  mov     r15, [rsp+38h+arg_0]
0x18000dd3a  mov     rcx, rdi; hMem
0x18000dd3d  call    cs:__imp_LocalFree
0x18000dd44  nop     dword ptr [rax+rax+00h]
0x18000dd49  mov     rbx, [rsp+38h+arg_8]
0x18000dd4e  mov     eax, ebp
0x18000dd50  mov     rbp, [rsp+38h+arg_10]
0x18000dd55  add     rsp, 20h
0x18000dd59  pop     r14
0x18000dd5b  pop     rdi
0x18000dd5c  pop     rsi
0x18000dd5d  retn
```
