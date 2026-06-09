# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *>>>(void)

- ea: `0x1400080d0`
- end: `0x140008116`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140022d4a`

## callees

- `0x1400026b8`
- `0x1400080d0`
- `0x140008160`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rbx
  void *v3; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    std::wstring::~wstring(v1 + 64);
    std::wstring::~wstring(v1 + 32);
  }
  v3 = *(void **)(a1 + 8);
  if ( v3 )
    operator delete(v3, 0x60u);
}

```

## disassembly

```asm
0x1400080d0  mov     [rsp+arg_8], rbx
0x1400080d5  push    rdi
0x1400080d6  sub     rsp, 20h
0x1400080da  mov     rbx, [rcx+8]
0x1400080de  mov     rdi, rcx
0x1400080e1  test    rbx, rbx
0x1400080e4  jz      short loc_1400080F8
0x1400080e6  lea     rcx, [rbx+40h]
0x1400080ea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400080ef  lea     rcx, [rbx+20h]
0x1400080f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400080f8  mov     rcx, [rdi+8]; void *
0x1400080fc  test    rcx, rcx
0x1400080ff  jz      short loc_14000810B
0x140008101  mov     edx, 60h ; '`'; unsigned __int64
0x140008106  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000810b  mov     rbx, [rsp+28h+arg_8]
0x140008110  add     rsp, 20h
0x140008114  pop     rdi
0x140008115  retn
```
