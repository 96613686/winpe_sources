# std::list<std::unique_ptr<ProcessWatcherDesc,std::default_delete<ProcessWatcherDesc>>,std::allocator<std::unique_ptr<ProcessWatcherDesc,std::default_delete<ProcessWatcherDesc>>>>::~list<std::unique_ptr<ProcessWatcherDesc,std::default_delete<ProcessWatcherDesc>>,std::allocator<std::unique_ptr<ProcessWatcherDesc,std::default_delete<ProcessWatcherDesc>>>>(void)

- ea: `0x1800046f4`
- end: `0x180004760`
- name: `??1?$list@V?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@std@@V?$allocator@V?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004608`
- `0x180004e34`

## callees

- `0x1800046f4`
- `0x180004f20`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004737`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004740`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004737`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004740`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004759`

## pseudocode

```c
void __fastcall std::list<std::unique_ptr<ProcessWatcherDesc>>::~list<std::unique_ptr<ProcessWatcherDesc>>(
        __int64 a1,
        __int64 a2)
{
  void **v3; // rbx
  void **v4; // rcx
  void *v5; // rsi
  void **v6; // rbp

  v3 = **(void ****)a1;
  **(_QWORD **)a1 = *(_QWORD *)a1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = *(_QWORD *)a1;
  *(_QWORD *)(a1 + 8) = 0;
  v4 = *(void ***)a1;
  if ( v3 != v4 )
  {
    do
    {
      v5 = v3[2];
      v6 = (void **)*v3;
      if ( v5 )
      {
        ProcessWatcherDesc::~ProcessWatcherDesc((ProcessWatcherDesc *)v3[2], a2);
        operator delete(v5);
      }
      operator delete(v3);
      v4 = *(void ***)a1;
      v3 = v6;
    }
    while ( v6 != *(void ***)a1 );
  }
  operator delete(v4);
}

```

## disassembly

```asm
0x1800046f4  push    rbx
0x1800046f6  push    rbp
0x1800046f7  push    rsi
0x1800046f8  push    rdi
0x1800046f9  sub     rsp, 28h
0x1800046fd  mov     rax, [rcx]
0x180004700  mov     rdi, rcx
0x180004703  mov     rbx, [rax]
0x180004706  mov     [rax], rax
0x180004709  mov     rax, [rcx]
0x18000470c  mov     [rax+8], rax
0x180004710  mov     qword ptr [rcx+8], 0
0x180004718  mov     rcx, [rcx]
0x18000471b  cmp     rbx, rcx
0x18000471e  jz      short loc_180004751
0x180004720  mov     rsi, [rbx+10h]
0x180004724  mov     rbp, [rbx]
0x180004727  test    rsi, rsi
0x18000472a  jz      short loc_18000473D
0x18000472c  mov     rcx, rsi; this
0x18000472f  call    ??1ProcessWatcherDesc@@QEAA@XZ; ProcessWatcherDesc::~ProcessWatcherDesc(void)
0x180004734  mov     rcx, rsi
0x180004737  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000473d  mov     rcx, rbx
0x180004740  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004746  mov     rcx, [rdi]
0x180004749  mov     rbx, rbp
0x18000474c  cmp     rbp, rcx
0x18000474f  jnz     short loc_180004720
0x180004751  add     rsp, 28h
0x180004755  pop     rdi
0x180004756  pop     rsi
0x180004757  pop     rbp
0x180004758  pop     rbx
0x180004759  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
