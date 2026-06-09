# std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>::~vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>(void)

- ea: `0x18000dc0c`
- end: `0x18000dc71`
- name: `??1?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(__int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x18000db40`
- `0x18000dbb4`
- `0x18000e0a8`
- `0x18000f9f4`
- `0x180010440`
- `0x1800104e4`
- `0x180011198`
- `0x1800113dc`

## callees

- `0x18000dc0c`
- `0x18000ef28`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000dc39`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dc4b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dc39`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dc4b`

## pseudocode

```c
void __fastcall std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(__int64 a1)
{
  FilterAgent **v1; // rdi
  FilterAgent **v3; // rbp
  FilterAgent *v4; // rsi

  v1 = *(FilterAgent ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(FilterAgent ***)(a1 + 8);
    while ( v1 != v3 )
    {
      v4 = *v1;
      if ( *v1 )
      {
        FilterAgent::~FilterAgent(*v1);
        operator delete(v4);
      }
      ++v1;
    }
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18000dc0c  push    rbx
0x18000dc0e  push    rbp
0x18000dc0f  push    rsi
0x18000dc10  push    rdi
0x18000dc11  sub     rsp, 28h
0x18000dc15  mov     rdi, [rcx]
0x18000dc18  mov     rbx, rcx
0x18000dc1b  test    rdi, rdi
0x18000dc1e  jz      short loc_18000DC68
0x18000dc20  mov     rbp, [rcx+8]
0x18000dc24  jmp     short loc_18000DC43
0x18000dc26  mov     rsi, [rdi]
0x18000dc29  test    rsi, rsi
0x18000dc2c  jz      short loc_18000DC3F
0x18000dc2e  mov     rcx, rsi; this
0x18000dc31  call    ??1FilterAgent@@QEAA@XZ; FilterAgent::~FilterAgent(void)
0x18000dc36  mov     rcx, rsi
0x18000dc39  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000dc3f  add     rdi, 8
0x18000dc43  cmp     rdi, rbp
0x18000dc46  jnz     short loc_18000DC26
0x18000dc48  mov     rcx, [rbx]
0x18000dc4b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000dc51  mov     qword ptr [rbx], 0
0x18000dc58  mov     qword ptr [rbx+8], 0
0x18000dc60  mov     qword ptr [rbx+10h], 0
0x18000dc68  add     rsp, 28h
0x18000dc6c  pop     rdi
0x18000dc6d  pop     rsi
0x18000dc6e  pop     rbp
0x18000dc6f  pop     rbx
0x18000dc70  retn
```
