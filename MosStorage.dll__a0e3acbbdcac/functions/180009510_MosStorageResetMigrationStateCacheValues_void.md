# MosStorageResetMigrationStateCacheValues(void)

- ea: `0x180009510`
- end: `0x180009582`
- name: `?MosStorageResetMigrationStateCacheValues@@YAXXZ`
- size: `114`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009790`
- `0x180009cc0`

## callees

- `0x180002802`
- `0x18000e7ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000951e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000951e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000957b`

## pseudocode

```c
void MosStorageResetMigrationStateCacheValues(void)
{
  _BYTE Src[1656]; // [rsp+20h] [rbp-678h] BYREF

  EnterCriticalSection(&CriticalSection);
  qword_1800184C0 = 0;
  qword_1800184C8 = 0;
  dword_1800184D0 = 0;
  xmmword_1800184B0 = 0;
  memset_0(Src, 0, 0x670u);
  memcpy_0(qword_1800184D8, Src, sizeof(qword_1800184D8));
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180009510  sub     rsp, 698h
0x180009517  lea     rcx, CriticalSection; lpCriticalSection
0x18000951e  call    cs:__imp_EnterCriticalSection
0x180009524  xor     eax, eax
0x180009526  lea     rcx, [rsp+698h+Src]; void *
0x18000952b  xorps   xmm0, xmm0
0x18000952e  mov     cs:qword_1800184C0, rax
0x180009535  xor     edx, edx; Val
0x180009537  mov     cs:qword_1800184C8, rax
0x18000953e  mov     r8d, 670h; Size
0x180009544  mov     cs:dword_1800184D0, eax
0x18000954a  movups  cs:xmmword_1800184B0, xmm0
0x180009551  call    memset_0
0x180009556  lea     rcx, qword_1800184D8; void *
0x18000955d  mov     r8d, 670h; Size
0x180009563  lea     rdx, [rsp+698h+Src]; Src
0x180009568  call    memcpy_0
0x18000956d  lea     rcx, CriticalSection
0x180009574  add     rsp, 698h
0x18000957b  jmp     cs:__imp_LeaveCriticalSection
```
