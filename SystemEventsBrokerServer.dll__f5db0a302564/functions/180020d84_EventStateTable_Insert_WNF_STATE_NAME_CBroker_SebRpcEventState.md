# EventStateTable::Insert(_WNF_STATE_NAME,CBroker::SebRpcEventState *)

- ea: `0x180020d84`
- end: `0x180020e16`
- name: `?Insert@EventStateTable@@QEAAKU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(EventStateTable *this, struct _WNF_STATE_NAME, struct CBroker::SebRpcEventState *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180020cd0`

## callees

- `0x180013820`
- `0x180013920`
- `0x18001cf50`
- `0x180020a6c`
- `0x180020d84`

## pseudocode

```c
__int64 __fastcall EventStateTable::Insert(
        EventStateTable *this,
        struct _WNF_STATE_NAME a2,
        struct CBroker::SebRpcEventState *a3)
{
  __int64 v5; // rcx
  unsigned int v6; // edi
  _BYTE v8[16]; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v9[16]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v10[2]; // [rsp+48h] [rbp-20h] BYREF

  Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)v9, &stru_180036E10, 1);
  try
  {
    v6 = 0;
    v10[0] = (__int64)a2;
    v10[1] = (__int64)a3;
    std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,CBroker::SebRpcEventState *,std::less<_WNF_STATE_NAME>,std::allocator<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>,0>>::_Emplace<std::pair<_WNF_STATE_NAME,CBroker::SebRpcEventState *>>(
      v5,
      (__int64)v8,
      v10);
    if ( !v8[8] )
      v6 = 1359;
  }
  catch ( ... )
  {
    v6 = 1359;
  }
  Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)v9);
  return v6;
}

```

## disassembly

```asm
0x180020d84  mov     [rsp+arg_0], rbx
0x180020d89  mov     [rsp+arg_10], rsi
0x180020d8e  push    rdi
0x180020d8f  sub     rsp, 60h
0x180020d93  mov     rax, cs:__security_cookie
0x180020d9a  xor     rax, rsp
0x180020d9d  mov     [rsp+68h+var_10], rax
0x180020da2  mov     rsi, r8
0x180020da5  mov     rbx, rdx
0x180020da8  mov     r8b, 1; bool
0x180020dab  lea     rdx, stru_180036E10; struct _RTL_SRWLOCK *
0x180020db2  lea     rcx, [rsp+68h+var_30]; this
0x180020db7  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x180020dbc  nop
0x180020dbd  xor     edi, edi
0x180020dbf  mov     [rsp+68h+var_20], rbx
0x180020dc4  mov     [rsp+68h+var_18], rsi
0x180020dc9  lea     r8, [rsp+68h+var_20]
0x180020dce  lea     rdx, [rsp+68h+var_40]
0x180020dd3  call    ??$_Emplace@U?$pair@U_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@@?$_Tree@V?$_Tmap_traits@U_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@U?$less@U_WNF_STATE_NAME@@@std@@V?$allocator@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@U_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@1@@Z; std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,CBroker::SebRpcEventState *,std::less<_WNF_STATE_NAME>,std::allocator<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>,0>>::_Emplace<std::pair<_WNF_STATE_NAME,CBroker::SebRpcEventState *>>(std::pair<_WNF_STATE_NAME,CBroker::SebRpcEventState *> &&)
0x180020dd8  mov     eax, 54Fh
0x180020ddd  cmp     [rsp+68h+var_38], dil
0x180020de2  cmovz   edi, eax
0x180020de5  jmp     short loc_180020DEB
0x180020de7  mov     edi, [rsp+68h+var_48]
0x180020deb  lea     rcx, [rsp+68h+var_30]; this
0x180020df0  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x180020df5  mov     eax, edi
0x180020df7  mov     rcx, [rsp+68h+var_10]
0x180020dfc  xor     rcx, rsp; StackCookie
0x180020dff  call    __security_check_cookie
0x180020e04  lea     r11, [rsp+68h+var_8]
0x180020e09  mov     rbx, [r11+10h]
0x180020e0d  mov     rsi, [r11+20h]
0x180020e11  mov     rsp, r11
0x180020e14  pop     rdi
0x180020e15  retn
```
