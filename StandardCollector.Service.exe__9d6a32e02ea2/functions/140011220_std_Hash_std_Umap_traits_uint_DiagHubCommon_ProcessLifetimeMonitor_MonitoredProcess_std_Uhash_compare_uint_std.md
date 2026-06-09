# std::_Hash<std::_Umap_traits<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>>>)

- ea: `0x140011220`
- end: `0x1400112f2`
- name: `??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@std@@@std@@@1@V21@@Z`
- size: `210`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140010a70`
- `0x140010ffc`

## callees

- `0x140011220`
- `0x14001382c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400112c1`
- `KERNEL32!CloseHandle` at `0x1400112c1`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>>>,0>(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rdx
  unsigned __int64 i; // r8
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdi
  void *v14; // rcx
  _QWORD *result; // rax

  v5 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
  {
    v8 = *((unsigned __int8 *)a3 + i + 16);
    v5 = 0x100000001B3LL * (v8 ^ v5);
  }
  v9 = v5 & a1[6];
  v10 = a1[3];
  v11 = 2 * v9;
  if ( *(_QWORD **)(v10 + 8 * v11 + 8) == a3 )
  {
    if ( *(_QWORD **)(v10 + 8 * v11) == a3 )
    {
      v12 = a1[1];
      *(_QWORD *)(v10 + 8 * v11) = v12;
    }
    else
    {
      v12 = a3[1];
    }
    *(_QWORD *)(v10 + 8 * v11 + 8) = v12;
  }
  else if ( *(_QWORD **)(v10 + 8 * v11) == a3 )
  {
    *(_QWORD *)(v10 + 8 * v11) = *a3;
  }
  v13 = *a3;
  --a1[2];
  *(_QWORD *)a3[1] = v13;
  *(_QWORD *)(v13 + 8) = a3[1];
  v14 = (void *)a3[6];
  if ( v14 )
  {
    CloseHandle(v14);
    a3[6] = 0;
  }
  operator delete(a3);
  result = a2;
  *a2 = v13;
  return result;
}

```

## disassembly

```asm
0x140011220  mov     [rsp+arg_10], rbx
0x140011225  mov     [rsp+arg_18], rsi
0x14001122a  push    rdi
0x14001122b  sub     rsp, 20h
0x14001122f  mov     rbx, r8
0x140011232  mov     rsi, rdx
0x140011235  mov     rdx, 0CBF29CE484222325h
0x14001123f  xor     r8d, r8d
0x140011242  mov     r9, rcx
0x140011245  movzx   eax, byte ptr [rbx+r8+10h]
0x14001124b  mov     rcx, 100000001B3h
0x140011255  xor     rdx, rax
0x140011258  inc     r8
0x14001125b  imul    rdx, rcx
0x14001125f  cmp     r8, 4
0x140011263  jb      short loc_140011245
0x140011265  mov     rcx, [r9+30h]
0x140011269  and     rcx, rdx
0x14001126c  mov     rdx, [r9+18h]
0x140011270  add     rcx, rcx
0x140011273  cmp     [rdx+rcx*8+8], rbx
0x140011278  jnz     short loc_140011295
0x14001127a  cmp     [rdx+rcx*8], rbx
0x14001127e  jnz     short loc_14001128A
0x140011280  mov     rax, [r9+8]
0x140011284  mov     [rdx+rcx*8], rax
0x140011288  jmp     short loc_14001128E
0x14001128a  mov     rax, [rbx+8]
0x14001128e  mov     [rdx+rcx*8+8], rax
0x140011293  jmp     short loc_1400112A2
0x140011295  cmp     [rdx+rcx*8], rbx
0x140011299  jnz     short loc_1400112A2
0x14001129b  mov     rax, [rbx]
0x14001129e  mov     [rdx+rcx*8], rax
0x1400112a2  mov     rdi, [rbx]
0x1400112a5  dec     qword ptr [r9+10h]
0x1400112a9  mov     rax, [rbx+8]
0x1400112ad  mov     [rax], rdi
0x1400112b0  mov     rax, [rbx+8]
0x1400112b4  mov     [rdi+8], rax
0x1400112b8  mov     rcx, [rbx+30h]; hObject
0x1400112bc  test    rcx, rcx
0x1400112bf  jz      short loc_1400112CF
0x1400112c1  call    cs:__imp_CloseHandle
0x1400112c7  mov     qword ptr [rbx+30h], 0
0x1400112cf  mov     edx, 40h ; '@'
0x1400112d4  mov     rcx, rbx; Block
0x1400112d7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400112dc  mov     rbx, [rsp+28h+arg_10]
0x1400112e1  mov     rax, rsi
0x1400112e4  mov     [rsi], rdi
0x1400112e7  mov     rsi, [rsp+28h+arg_18]
0x1400112ec  add     rsp, 20h
0x1400112f0  pop     rdi
0x1400112f1  retn
```
