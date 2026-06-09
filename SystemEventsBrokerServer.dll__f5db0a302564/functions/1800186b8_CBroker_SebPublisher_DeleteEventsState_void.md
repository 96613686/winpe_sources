# CBroker::SebPublisher::DeleteEventsState(void)

- ea: `0x1800186b8`
- end: `0x18001874b`
- name: `?DeleteEventsState@SebPublisher@CBroker@@CAXXZ`
- size: `147`
- prototype: `void __fastcall(EventStateTable *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001fc60`

## callees

- `0x180013820`
- `0x180013920`
- `0x180014fec`
- `0x18001708c`
- `0x1800186b8`
- `0x1800190b0`

## pseudocode

```c
void __fastcall CBroker::SebPublisher::DeleteEventsState(EventStateTable *a1)
{
  unsigned int i; // ebx
  __int64 v2; // rax
  __int64 v3; // rdi
  __int64 v4; // rcx
  _BYTE v5[40]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF
  __int64 v7; // [rsp+58h] [rbp+10h] BYREF
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF

  for ( i = 4096; i < 0x1043; ++i )
  {
    v2 = i - 4096;
    v3 = 5 * v2;
    if ( EventStateTable::Find(a1, *(struct _WNF_STATE_NAME *)&dword_180035F54[10 * v2]) )
    {
      v6 = *(_QWORD *)&dword_180035F54[2 * v3];
      Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)v5, &stru_180036E10, 1);
      std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,CBroker::SebRpcEventState *,std::less<_WNF_STATE_NAME>,std::allocator<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>,0>>::find(
        v4,
        &v7,
        &v6);
      if ( v7 != qword_180036E00 )
        std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,CBroker::SebRpcEventState *,std::less<_WNF_STATE_NAME>,std::allocator<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>>>,0>(
          (__int64)&qword_180036E00,
          &v8,
          v7);
      Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)v5);
    }
  }
}

```

## disassembly

```asm
0x1800186b8  push    rbx
0x1800186ba  push    rsi
0x1800186bb  push    rdi
0x1800186bc  sub     rsp, 30h
0x1800186c0  mov     ebx, 1000h
0x1800186c5  lea     eax, [rbx-1000h]
0x1800186cb  lea     rdi, [rax+rax*4]
0x1800186cf  lea     rsi, dword_180035F54
0x1800186d6  mov     rdx, [rsi+rdi*8]; struct _WNF_STATE_NAME
0x1800186da  call    ?Find@EventStateTable@@QEAAPEAVSebRpcEventState@CBroker@@U_WNF_STATE_NAME@@@Z; EventStateTable::Find(_WNF_STATE_NAME)
0x1800186df  test    rax, rax
0x1800186e2  jz      short loc_180018739
0x1800186e4  mov     rax, [rsi+rdi*8]
0x1800186e8  lea     rdx, stru_180036E10; struct _RTL_SRWLOCK *
0x1800186ef  mov     r8b, 1; bool
0x1800186f2  mov     [rsp+48h+arg_0], rax
0x1800186f7  lea     rcx, [rsp+48h+var_28]; this
0x1800186fc  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x180018701  lea     r8, [rsp+48h+arg_0]
0x180018706  lea     rdx, [rsp+48h+arg_8]
0x18001870b  call    ?find@?$_Tree@V?$_Tmap_traits@U_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@U?$less@U_WNF_STATE_NAME@@@std@@V?$allocator@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@@std@@@std@@@2@AEBU_WNF_STATE_NAME@@@Z; std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,CBroker::SebRpcEventState *,std::less<_WNF_STATE_NAME>,std::allocator<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>,0>>::find(_WNF_STATE_NAME const &)
0x180018710  mov     r8, [rsp+48h+arg_8]
0x180018715  cmp     r8, cs:qword_180036E00
0x18001871c  jz      short loc_18001872F
0x18001871e  lea     rdx, [rsp+48h+arg_10]
0x180018723  lea     rcx, qword_180036E00
0x18001872a  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@U_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@U?$less@U_WNF_STATE_NAME@@@std@@V?$allocator@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,CBroker::SebRpcEventState *,std::less<_WNF_STATE_NAME>,std::allocator<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>>>)
0x18001872f  lea     rcx, [rsp+48h+var_28]; this
0x180018734  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x180018739  inc     ebx
0x18001873b  cmp     ebx, 1043h
0x180018741  jb      short loc_1800186C5
0x180018743  add     rsp, 30h
0x180018747  pop     rdi
0x180018748  pop     rsi
0x180018749  pop     rbx
0x18001874a  retn
```
