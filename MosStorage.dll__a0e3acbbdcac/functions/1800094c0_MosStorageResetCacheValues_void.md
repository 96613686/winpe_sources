# MosStorageResetCacheValues(void)

- ea: `0x1800094c0`
- end: `0x18000950a`
- name: `?MosStorageResetCacheValues@@YAXXZ`
- size: `74`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009790`

## callees

- `0x1800094c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800094cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800094cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009503`

## pseudocode

```c
void MosStorageResetCacheValues(void)
{
  EnterCriticalSection(&CriticalSection);
  word_180018B50 = 0;
  qword_180018B48 = 0;
  if ( Src != (void *)qword_180018DD8 )
    qword_180018DD8 = (__int64)Src;
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x1800094c0  sub     rsp, 28h
0x1800094c4  lea     rcx, CriticalSection; lpCriticalSection
0x1800094cb  call    cs:__imp_EnterCriticalSection
0x1800094d1  xor     eax, eax
0x1800094d3  mov     cs:word_180018B50, ax
0x1800094da  mov     cs:qword_180018B48, rax
0x1800094e1  mov     rax, cs:Src
0x1800094e8  cmp     rax, cs:qword_180018DD8
0x1800094ef  jz      short loc_1800094F8
0x1800094f1  mov     cs:qword_180018DD8, rax
0x1800094f8  lea     rcx, CriticalSection
0x1800094ff  add     rsp, 28h
0x180009503  jmp     cs:__imp_LeaveCriticalSection
```
