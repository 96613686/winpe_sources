# std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>,void *>>>(void)

- ea: `0x1400115e8`
- end: `0x140011633`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140015a5c`

## callees

- `0x1400115e8`
- `0x14001382c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140011607`
- `KERNEL32!CloseHandle` at `0x140011607`

## pseudocode

```c
void __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rbx
  void *v3; // rcx
  void *v4; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    v3 = *(void **)(v1 + 48);
    if ( v3 )
    {
      CloseHandle(v3);
      *(_QWORD *)(v1 + 48) = 0;
    }
  }
  v4 = *(void **)(a1 + 8);
  if ( v4 )
    operator delete(v4);
}

```

## disassembly

```asm
0x1400115e8  mov     [rsp+arg_8], rbx
0x1400115ed  push    rdi
0x1400115ee  sub     rsp, 20h
0x1400115f2  mov     rbx, [rcx+8]
0x1400115f6  mov     rdi, rcx
0x1400115f9  test    rbx, rbx
0x1400115fc  jz      short loc_140011615
0x1400115fe  mov     rcx, [rbx+30h]; hObject
0x140011602  test    rcx, rcx
0x140011605  jz      short loc_140011615
0x140011607  call    cs:__imp_CloseHandle
0x14001160d  mov     qword ptr [rbx+30h], 0
0x140011615  mov     rcx, [rdi+8]; Block
0x140011619  test    rcx, rcx
0x14001161c  jz      short loc_140011628
0x14001161e  mov     edx, 40h ; '@'
0x140011623  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011628  mov     rbx, [rsp+28h+arg_8]
0x14001162d  add     rsp, 20h
0x140011631  pop     rdi
0x140011632  retn
```
