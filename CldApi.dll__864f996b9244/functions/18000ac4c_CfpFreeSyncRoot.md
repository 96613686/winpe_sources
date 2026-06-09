# CfpFreeSyncRoot

- ea: `0x18000ac4c`
- end: `0x18000ad2c`
- name: `CfpFreeSyncRoot`
- size: `224`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004ac0`
- `0x18000b6c8`

## callees

- `0x18000ac4c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000acb2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000acb2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ad00`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ad00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ace4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ad06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ace4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ad06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ac85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aca2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000acf2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ac85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aca2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000acf2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ad1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac68`

## pseudocode

```c
BOOL __fastcall CfpFreeSyncRoot(_QWORD *a1)
{
  char *v2; // rcx
  void *v3; // rbx
  HANDLE ProcessHeap; // rax
  void *v5; // rbx
  HANDLE v6; // rax
  _QWORD *v7; // rdi
  __int64 v8; // rax
  _QWORD *v9; // rcx
  _QWORD *v10; // rbx
  HANDLE v11; // rax
  HANDLE v12; // rax

  v2 = (char *)a1[1];
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
  v3 = (void *)a1[2];
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
  }
  v5 = (void *)a1[4];
  if ( v5 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v5);
  }
  RtlAcquireSRWLockExclusive(a1 + 21);
  v7 = (_QWORD *)a1[19];
  while ( v7 != a1 + 19 )
  {
    v8 = *v7;
    if ( *(_QWORD **)(*v7 + 8LL) != v7 || (v9 = (_QWORD *)v7[1], (_QWORD *)*v9 != v7) )
      __fastfail(3u);
    *v9 = v8;
    v10 = v7 - 1;
    *(_QWORD *)(v8 + 8) = v9;
    v7 = (_QWORD *)*v7;
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  RtlReleaseSRWLockExclusive(a1 + 21);
  v12 = GetProcessHeap();
  return HeapFree(v12, 0, a1);
}

```

## disassembly

```asm
0x18000ac4c  push    rbx
0x18000ac4e  push    rbp
0x18000ac4f  push    rsi
0x18000ac50  push    rdi
0x18000ac51  push    r14
0x18000ac53  sub     rsp, 20h
0x18000ac57  mov     rsi, rcx
0x18000ac5a  mov     rcx, [rcx+8]; hObject
0x18000ac5e  lea     rax, [rcx-1]
0x18000ac62  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ac66  ja      short loc_18000AC6E
0x18000ac68  call    cs:__imp_CloseHandle
0x18000ac6e  mov     rbx, [rsi+10h]
0x18000ac72  test    rbx, rbx
0x18000ac75  jz      short loc_18000AC8B
0x18000ac77  call    cs:__imp_GetProcessHeap
0x18000ac7d  mov     r8, rbx; lpMem
0x18000ac80  xor     edx, edx; dwFlags
0x18000ac82  mov     rcx, rax; hHeap
0x18000ac85  call    cs:__imp_HeapFree
0x18000ac8b  mov     rbx, [rsi+20h]
0x18000ac8f  test    rbx, rbx
0x18000ac92  jz      short loc_18000ACA8
0x18000ac94  call    cs:__imp_GetProcessHeap
0x18000ac9a  mov     r8, rbx; lpMem
0x18000ac9d  xor     edx, edx; dwFlags
0x18000ac9f  mov     rcx, rax; hHeap
0x18000aca2  call    cs:__imp_HeapFree
0x18000aca8  lea     rbp, [rsi+0A8h]
0x18000acaf  mov     rcx, rbp
0x18000acb2  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000acb8  lea     r14, [rsi+98h]
0x18000acbf  mov     rdi, [r14]
0x18000acc2  jmp     short loc_18000ACF8
0x18000acc4  mov     rax, [rdi]
0x18000acc7  cmp     [rax+8], rdi
0x18000accb  jnz     short loc_18000AD25
0x18000accd  mov     rcx, [rdi+8]
0x18000acd1  cmp     [rcx], rdi
0x18000acd4  jnz     short loc_18000AD25
0x18000acd6  mov     [rcx], rax
0x18000acd9  lea     rbx, [rdi-8]
0x18000acdd  mov     [rax+8], rcx
0x18000ace1  mov     rdi, [rdi]
0x18000ace4  call    cs:__imp_GetProcessHeap
0x18000acea  mov     r8, rbx; lpMem
0x18000aced  xor     edx, edx; dwFlags
0x18000acef  mov     rcx, rax; hHeap
0x18000acf2  call    cs:__imp_HeapFree
0x18000acf8  cmp     rdi, r14
0x18000acfb  jnz     short loc_18000ACC4
0x18000acfd  mov     rcx, rbp
0x18000ad00  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000ad06  call    cs:__imp_GetProcessHeap
0x18000ad0c  mov     r8, rsi
0x18000ad0f  xor     edx, edx
0x18000ad11  mov     rcx, rax
0x18000ad14  add     rsp, 20h
0x18000ad18  pop     r14
0x18000ad1a  pop     rdi
0x18000ad1b  pop     rsi
0x18000ad1c  pop     rbp
0x18000ad1d  pop     rbx
0x18000ad1e  jmp     cs:__imp_HeapFree
0x18000ad25  mov     ecx, 3
0x18000ad2a  int     29h; Win8: RtlFailFast(ecx)
```
