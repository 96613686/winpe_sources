# std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<DiagHubCommon::LogLevel const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<DiagHubCommon::LogLevel const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *>>>(void)

- ea: `0x14000dc64`
- end: `0x14000dc98`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400156da`

## callees

- `0x140003010`
- `0x14000dc64`
- `0x14001382c`

## pseudocode

```c
void __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx
  void *v3; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    std::wstring::~wstring(v2 + 24);
  v3 = *(void **)(a1 + 8);
  if ( v3 )
    operator delete(v3);
}

```

## disassembly

```asm
0x14000dc64  push    rbx
0x14000dc66  sub     rsp, 20h
0x14000dc6a  mov     rbx, rcx
0x14000dc6d  mov     rcx, [rcx+8]
0x14000dc71  test    rcx, rcx
0x14000dc74  jz      short loc_14000DC7F
0x14000dc76  add     rcx, 18h
0x14000dc7a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000dc7f  mov     rcx, [rbx+8]; Block
0x14000dc83  test    rcx, rcx
0x14000dc86  jz      short loc_14000DC92
0x14000dc88  mov     edx, 38h ; '8'
0x14000dc8d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000dc92  add     rsp, 20h
0x14000dc96  pop     rbx
0x14000dc97  retn
```
