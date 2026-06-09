# std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>::~unique_ptr<FilterAgent,std::default_delete<FilterAgent>>(void)

- ea: `0x18000dbe0`
- end: `0x18000dc05`
- name: `??1?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(FilterAgent **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180022921`

## callees

- `0x18000dbe0`
- `0x18000ef28`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000dbf9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dbf9`

## pseudocode

```c
void __fastcall std::unique_ptr<FilterAgent>::~unique_ptr<FilterAgent>(FilterAgent **a1)
{
  FilterAgent *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    FilterAgent::~FilterAgent(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000dbe0  push    rbx
0x18000dbe2  sub     rsp, 20h
0x18000dbe6  mov     rbx, [rcx]
0x18000dbe9  test    rbx, rbx
0x18000dbec  jz      short loc_18000DBFF
0x18000dbee  mov     rcx, rbx; this
0x18000dbf1  call    ??1FilterAgent@@QEAA@XZ; FilterAgent::~FilterAgent(void)
0x18000dbf6  mov     rcx, rbx
0x18000dbf9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000dbff  add     rsp, 20h
0x18000dc03  pop     rbx
0x18000dc04  retn
```
