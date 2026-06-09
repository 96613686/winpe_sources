# std::pair<FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>>::~pair<FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>>(void)

- ea: `0x180010440`
- end: `0x180010466`
- name: `??1?$pair@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180022945`

## callees

- `0x18000dc0c`
- `0x180010440`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001045a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001045a`

## pseudocode

```c
void __fastcall std::pair<enum FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>::~pair<enum FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>(
        __int64 a1)
{
  void *v1; // rbx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
  {
    std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(*(_QWORD *)(a1 + 8));
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x180010440  push    rbx
0x180010442  sub     rsp, 20h
0x180010446  mov     rbx, [rcx+8]
0x18001044a  test    rbx, rbx
0x18001044d  jz      short loc_180010460
0x18001044f  mov     rcx, rbx
0x180010452  call    ??1?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(void)
0x180010457  mov     rcx, rbx
0x18001045a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010460  add     rsp, 20h
0x180010464  pop     rbx
0x180010465  retn
```
