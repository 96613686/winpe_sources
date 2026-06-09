# std::_Wrap_alloc<std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>::destroy<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>(std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>> *)

- ea: `0x18000db14`
- end: `0x18000db39`
- name: `??$destroy@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@std@@@std@@QEAAXPEAV?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@1@@Z`
- size: `37`
- prototype: `void __fastcall(__int64, FilterAgent **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x18002286d`

## callees

- `0x18000db14`
- `0x18000ef28`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000db2d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000db2d`

## pseudocode

```c
void __fastcall std::_Wrap_alloc<std::allocator<std::unique_ptr<FilterAgent>>>::destroy<std::unique_ptr<FilterAgent>>(
        __int64 a1,
        FilterAgent **a2)
{
  FilterAgent *v2; // rbx

  v2 = *a2;
  if ( *a2 )
  {
    FilterAgent::~FilterAgent(*a2);
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x18000db14  push    rbx
0x18000db16  sub     rsp, 20h
0x18000db1a  mov     rbx, [rdx]
0x18000db1d  test    rbx, rbx
0x18000db20  jz      short loc_18000DB33
0x18000db22  mov     rcx, rbx; this
0x18000db25  call    ??1FilterAgent@@QEAA@XZ; FilterAgent::~FilterAgent(void)
0x18000db2a  mov     rcx, rbx
0x18000db2d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000db33  add     rsp, 20h
0x18000db37  pop     rbx
0x18000db38  retn
```
