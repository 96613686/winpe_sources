# std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>::~unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>(void)

- ea: `0x18000dbb4`
- end: `0x18000dbd9`
- name: `??1?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x1800228eb`
- `0x1800228fd`
- `0x18002290f`
- `0x180022933`

## callees

- `0x18000dbb4`
- `0x18000dc0c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000dbcd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dbcd`

## pseudocode

```c
void __fastcall std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>::~unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>(
        _QWORD *a1)
{
  void *v1; // rbx

  v1 = (void *)*a1;
  if ( *a1 )
  {
    std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000dbb4  push    rbx
0x18000dbb6  sub     rsp, 20h
0x18000dbba  mov     rbx, [rcx]
0x18000dbbd  test    rbx, rbx
0x18000dbc0  jz      short loc_18000DBD3
0x18000dbc2  mov     rcx, rbx
0x18000dbc5  call    ??1?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(void)
0x18000dbca  mov     rcx, rbx
0x18000dbcd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000dbd3  add     rsp, 20h
0x18000dbd7  pop     rbx
0x18000dbd8  retn
```
