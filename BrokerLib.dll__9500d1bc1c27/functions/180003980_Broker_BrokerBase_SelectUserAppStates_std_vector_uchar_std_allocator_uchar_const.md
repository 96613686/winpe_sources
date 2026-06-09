# Broker::BrokerBase::SelectUserAppStates(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x180003980`
- end: `0x180003a4c`
- name: `?SelectUserAppStates@BrokerBase@Broker@@AEAA?AV?$vector@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@V?$allocator@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@4@@Z`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800026b4`
- `0x18000c970`

## callees

- `0x180003920`
- `0x180003980`
- `0x180004700`
- `0x180005b50`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Broker::BrokerBase::SelectUserAppStates(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // r9
  __int64 v8; // r9
  __int64 v10; // r9
  _QWORD v11[7]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12; // [rsp+70h] [rbp+8h] BYREF
  _QWORD *v13; // [rsp+78h] [rbp+10h]

  v13 = a2;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v10 = 0;
    if ( *(_QWORD *)(a1 + 8) )
      v10 = *(_QWORD *)(a1 + 8);
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids, v10);
  }
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v11[0] = a1;
  v11[1] = a3;
  v11[2] = a2;
  v6 = *(_QWORD *)(a1 + 272);
  v7 = **(_QWORD **)(v6 + 32);
  v12 = v7;
  while ( v7 != *(_QWORD *)(v6 + 32) )
  {
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>,std::_Iterator_base0>::operator++(
      &v12,
      a2,
      a3,
      v7);
    lambda_4d723a70409c971b782fbfb79ff852a6_::operator()((__int64)v11, (PSID **)(v8 + 120));
    v7 = v12;
  }
  return a2;
}

```

## disassembly

```asm
0x180003980  mov     [rsp+arg_10], rbx
0x180003985  mov     [rsp+arg_8], rdx
0x18000398a  push    rbp
0x18000398b  push    rsi
0x18000398c  push    rdi
0x18000398d  sub     rsp, 50h
0x180003991  mov     rsi, r8
0x180003994  mov     rdi, rdx
0x180003997  mov     rbx, rcx
0x18000399a  xor     ebp, ebp
0x18000399c  mov     [rsp+68h+var_48], ebp
0x1800039a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039a7  test    dword ptr [rcx+1Ch], 800h
0x1800039ae  jnz     short loc_180003A1D
0x1800039b0  mov     [rdi], rbp
0x1800039b3  mov     [rdi+8], rbp
0x1800039b7  mov     [rdi+10h], rbp
0x1800039bb  mov     [rsp+68h+var_48], 1
0x1800039c3  mov     [rsp+68h+var_38], rbx
0x1800039c8  mov     [rsp+68h+var_30], rsi
0x1800039cd  mov     [rsp+68h+var_28], rdi
0x1800039d2  mov     rbx, [rbx+110h]
0x1800039d9  mov     r9, [rbx+20h]
0x1800039dd  mov     r9, [r9]
0x1800039e0  mov     [rsp+68h+arg_0], r9
0x1800039e5  cmp     r9, [rbx+20h]
0x1800039e9  jz      short loc_180003A0A
0x1800039eb  lea     rcx, [rsp+68h+arg_0]
0x1800039f0  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>,std::_Iterator_base0>::operator++(void)
0x1800039f5  lea     rdx, [r9+78h]
0x1800039f9  lea     rcx, [rsp+68h+var_38]
0x1800039fe  call    _lambda_4d723a70409c971b782fbfb79ff852a6___operator__
0x180003a03  mov     r9, [rsp+68h+arg_0]
0x180003a08  jmp     short loc_1800039E5
0x180003a0a  mov     rax, rdi
0x180003a0d  mov     rbx, [rsp+68h+arg_10]
0x180003a15  add     rsp, 50h
0x180003a19  pop     rdi
0x180003a1a  pop     rsi
0x180003a1b  pop     rbp
0x180003a1c  retn
0x180003a1d  cmp     byte ptr [rcx+19h], 5
0x180003a21  jb      short loc_1800039B0
0x180003a23  mov     rax, [rbx+8]
0x180003a27  mov     r9, rbp
0x180003a2a  test    rax, rax
0x180003a2d  cmovnz  r9, rax
0x180003a31  mov     edx, 2Ah ; '*'
0x180003a36  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180003a3d  mov     rcx, [rcx+10h]
0x180003a41  call    WPP_SF__guid_
0x180003a46  jmp     loc_1800039B0
```
