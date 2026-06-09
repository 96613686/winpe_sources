# std::_Hash<std::_Umap_traits<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::clear(void)

- ea: `0x140011854`
- end: `0x14001191f`
- name: `?clear@?$_Hash@V?$_Umap_traits@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@5@$0A@@std@@@std@@QEAAXXZ`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140010d8c`

## callees

- `0x140011854`
- `0x14001193c`
- `0x14001382c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400118b1`
- `KERNEL32!CloseHandle` at `0x1400118b1`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::clear(
        _QWORD *a1)
{
  _QWORD **v2; // rdi
  _QWORD *v3; // rdi
  void *v4; // rcx
  _QWORD *v5; // rsi
  void *v6; // rdi
  unsigned __int64 v7; // rcx

  if ( a1[2] )
  {
    v2 = (_QWORD **)a1[1];
    if ( a1[7] >> 3 <= a1[2] )
    {
      *v2[1] = 0;
      v3 = *v2;
      if ( v3 )
      {
        do
        {
          v4 = (void *)v3[6];
          v5 = (_QWORD *)*v3;
          if ( v4 )
          {
            CloseHandle(v4);
            v3[6] = 0;
          }
          operator delete(v3);
          v3 = v5;
        }
        while ( v5 );
      }
      *(_QWORD *)a1[1] = a1[1];
      *(_QWORD *)(a1[1] + 8LL) = a1[1];
      a1[2] = 0;
      v6 = (void *)a1[3];
      v7 = (unsigned __int64)(a1[4] - (_QWORD)v6 + 7LL) >> 3;
      if ( (unsigned __int64)v6 > a1[4] )
        v7 = 0;
      if ( v7 )
        memset64(v6, a1[1], v7);
    }
    else
    {
      std::_Hash<std::_Umap_traits<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::_Unchecked_erase(
        a1,
        *v2,
        (_QWORD *)a1[1]);
    }
  }
}

```

## disassembly

```asm
0x140011854  mov     [rsp+arg_8], rbx
0x140011859  mov     [rsp+arg_10], rbp
0x14001185e  mov     [rsp+arg_18], rsi
0x140011863  push    rdi
0x140011864  sub     rsp, 20h
0x140011868  xor     ebp, ebp
0x14001186a  mov     rbx, rcx
0x14001186d  cmp     [rcx+10h], rbp
0x140011871  jz      loc_14001190A
0x140011877  mov     rax, [rcx+38h]
0x14001187b  mov     rdi, [rcx+8]
0x14001187f  shr     rax, 3
0x140011883  cmp     rax, [rcx+10h]
0x140011887  jbe     short loc_140011896
0x140011889  mov     rdx, [rdi]
0x14001188c  mov     r8, rdi
0x14001188f  call    ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@5@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Umap_traits<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::_Unchecked_erase(std::_List_node<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>,void *> *,std::_List_node<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>,void *> * const)
0x140011894  jmp     short loc_14001190A
0x140011896  mov     rax, [rdi+8]
0x14001189a  mov     [rax], rbp
0x14001189d  mov     rdi, [rdi]
0x1400118a0  test    rdi, rdi
0x1400118a3  jz      short loc_1400118D0
0x1400118a5  mov     rcx, [rdi+30h]; hObject
0x1400118a9  mov     rsi, [rdi]
0x1400118ac  test    rcx, rcx
0x1400118af  jz      short loc_1400118BB
0x1400118b1  call    cs:__imp_CloseHandle
0x1400118b7  mov     [rdi+30h], rbp
0x1400118bb  mov     edx, 40h ; '@'
0x1400118c0  mov     rcx, rdi; Block
0x1400118c3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400118c8  mov     rdi, rsi
0x1400118cb  test    rsi, rsi
0x1400118ce  jnz     short loc_1400118A5
0x1400118d0  mov     rax, [rbx+8]
0x1400118d4  mov     [rax], rax
0x1400118d7  mov     rax, [rbx+8]
0x1400118db  mov     [rax+8], rax
0x1400118df  mov     [rbx+10h], rbp
0x1400118e3  mov     rdi, [rbx+18h]
0x1400118e7  mov     rcx, [rbx+20h]
0x1400118eb  sub     rcx, rdi
0x1400118ee  add     rcx, 7
0x1400118f2  shr     rcx, 3
0x1400118f6  cmp     rdi, [rbx+20h]
0x1400118fa  cmova   rcx, rbp
0x1400118fe  test    rcx, rcx
0x140011901  jz      short loc_14001190A
0x140011903  mov     rax, [rbx+8]
0x140011907  rep stosq
0x14001190a  mov     rbx, [rsp+28h+arg_8]
0x14001190f  mov     rbp, [rsp+28h+arg_10]
0x140011914  mov     rsi, [rsp+28h+arg_18]
0x140011919  add     rsp, 20h
0x14001191d  pop     rdi
0x14001191e  retn
```
