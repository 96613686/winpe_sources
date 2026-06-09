# std::list<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>>,std::allocator<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>>>>::~list<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>>,std::allocator<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>>>>(void)

- ea: `0x18000db40`
- end: `0x18000dbac`
- name: `??1?$list@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@V?$allocator@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x18000dc78`
- `0x180022288`

## callees

- `0x18000db40`
- `0x18000dc0c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000db83`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000db8c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000db83`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000db8c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dba5`

## pseudocode

```c
void __fastcall std::list<std::pair<enum FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>::~list<std::pair<enum FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>(
        __int64 a1)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rcx
  void *v4; // rsi
  _QWORD *v5; // rbp

  v2 = **(_QWORD ***)a1;
  **(_QWORD **)a1 = *(_QWORD *)a1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = *(_QWORD *)a1;
  *(_QWORD *)(a1 + 8) = 0;
  v3 = *(_QWORD **)a1;
  if ( v2 != v3 )
  {
    do
    {
      v4 = (void *)v2[3];
      v5 = (_QWORD *)*v2;
      if ( v4 )
      {
        std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(v2[3]);
        operator delete(v4);
      }
      operator delete(v2);
      v3 = *(_QWORD **)a1;
      v2 = v5;
    }
    while ( v5 != *(_QWORD **)a1 );
  }
  operator delete(v3);
}

```

## disassembly

```asm
0x18000db40  push    rbx
0x18000db42  push    rbp
0x18000db43  push    rsi
0x18000db44  push    rdi
0x18000db45  sub     rsp, 28h
0x18000db49  mov     rax, [rcx]
0x18000db4c  mov     rdi, rcx
0x18000db4f  mov     rbx, [rax]
0x18000db52  mov     [rax], rax
0x18000db55  mov     rax, [rcx]
0x18000db58  mov     [rax+8], rax
0x18000db5c  mov     qword ptr [rcx+8], 0
0x18000db64  mov     rcx, [rcx]
0x18000db67  cmp     rbx, rcx
0x18000db6a  jz      short loc_18000DB9D
0x18000db6c  mov     rsi, [rbx+18h]
0x18000db70  mov     rbp, [rbx]
0x18000db73  test    rsi, rsi
0x18000db76  jz      short loc_18000DB89
0x18000db78  mov     rcx, rsi
0x18000db7b  call    ??1?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(void)
0x18000db80  mov     rcx, rsi
0x18000db83  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000db89  mov     rcx, rbx
0x18000db8c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000db92  mov     rcx, [rdi]
0x18000db95  mov     rbx, rbp
0x18000db98  cmp     rbp, rcx
0x18000db9b  jnz     short loc_18000DB6C
0x18000db9d  add     rsp, 28h
0x18000dba1  pop     rdi
0x18000dba2  pop     rsi
0x18000dba3  pop     rbp
0x18000dba4  pop     rbx
0x18000dba5  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
