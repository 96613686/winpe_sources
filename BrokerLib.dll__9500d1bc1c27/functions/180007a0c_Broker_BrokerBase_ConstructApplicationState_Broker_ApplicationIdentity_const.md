# Broker::BrokerBase::ConstructApplicationState(Broker::ApplicationIdentity const &)

- ea: `0x180007a0c`
- end: `0x180007afc`
- name: `?ConstructApplicationState@BrokerBase@Broker@@AEAA?AV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@AEBUApplicationIdentity@2@@Z`
- size: `240`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180008554`
- `0x180008668`
- `0x1800178fc`
- `0x18001849c`
- `0x1800185f4`

## callees

- `0x180002e88`
- `0x180003760`
- `0x180007a0c`
- `0x180007b10`
- `0x180007be0`
- `0x180008604`
- `0x180013a60`
- `0x1800156f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall Broker::BrokerBase::ConstructApplicationState(__int64 a1, __int64 *a2, __int64 *a3)
{
  __int64 v6; // rbp
  __int64 v7; // r12
  __int64 v8; // r13
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // r8
  __int64 v12; // rax
  _BYTE v14[16]; // [rsp+28h] [rbp-60h] BYREF
  __int64 v15; // [rsp+38h] [rbp-50h]

  Broker::ApplicationStateTable::CreateApplicationState(*(_QWORD *)(a1 + 272), a2, (__int64)a3);
  std::_Tree<std::_Tmap_traits<std::vector<unsigned char>,std::set<std::pair<unsigned __int64,unsigned long>>,std::less<std::vector<unsigned char>>,std::allocator<std::pair<std::vector<unsigned char> const,std::set<std::pair<unsigned __int64,unsigned long>>>>,0>>::_Find_lower_bound<std::vector<unsigned char>>(
    a1 + 256,
    v14,
    a3);
  v6 = v15;
  if ( *(_BYTE *)(v15 + 25) )
    goto LABEL_15;
  v7 = *a3;
  v8 = *(_QWORD *)(v15 + 32);
  v9 = a3[1] - *a3;
  v10 = *(_QWORD *)(v15 + 40) - v8;
  v11 = v10;
  if ( v10 >= v9 )
    v11 = v9;
  if ( (v12 = _std_mismatch_1(v7, *(_QWORD *)(v15 + 32), v11), v12 != v10)
    && (v12 == v9 || *(_BYTE *)(v7 + v12) < *(_BYTE *)(v12 + v8))
    || v6 == *(_QWORD *)(a1 + 256) )
  {
LABEL_15:
    if ( Broker::ApplicationStateTable::State::OnUserLogoff((Broker::ApplicationStateTable::State *)*a2) )
      Broker::BrokerBase::OnAppDisable(a1, 6, *a2);
  }
  else if ( Broker::ApplicationStateTable::State::OnUserLogon((Broker::ApplicationStateTable::State *)*a2) )
  {
    Broker::BrokerBase::OnAppEnable(a1, 6u, (_QWORD *)*a2);
  }
  return a2;
}

```

## disassembly

```asm
0x180007a0c  mov     [rsp+arg_8], rdx
0x180007a11  push    rbx
0x180007a12  push    rbp
0x180007a13  push    rsi
0x180007a14  push    rdi
0x180007a15  push    r12
0x180007a17  push    r13
0x180007a19  push    r14
0x180007a1b  push    r15
0x180007a1d  sub     rsp, 48h
0x180007a21  mov     rbx, r8
0x180007a24  mov     rdi, rdx
0x180007a27  mov     rsi, rcx
0x180007a2a  mov     [rsp+88h+var_68], 0
0x180007a32  mov     rcx, [rcx+110h]
0x180007a39  call    ?CreateApplicationState@ApplicationStateTable@Broker@@QEAA?AV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@AEBUApplicationIdentity@2@@Z; Broker::ApplicationStateTable::CreateApplicationState(Broker::ApplicationIdentity const &)
0x180007a3e  mov     [rsp+88h+var_68], 1
0x180007a46  lea     r15, [rsi+100h]
0x180007a4d  mov     r8, rbx
0x180007a50  lea     rdx, [rsp+88h+var_60]
0x180007a55  mov     rcx, r15
0x180007a58  call    ??$_Find_lower_bound@V?$vector@EV?$allocator@E@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@U?$less@V?$vector@EV?$allocator@E@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@PEAX@std@@@1@AEBV?$vector@EV?$allocator@E@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::vector<uchar>,std::set<std::pair<unsigned __int64,ulong>>,std::less<std::vector<uchar>>,std::allocator<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>>,0>>::_Find_lower_bound<std::vector<uchar>>(std::vector<uchar> const &)
0x180007a5d  mov     rbp, [rsp+88h+var_50]
0x180007a62  cmp     byte ptr [rbp+19h], 0
0x180007a66  jnz     short loc_180007A9C
0x180007a68  mov     r12, [rbx]
0x180007a6b  mov     r13, [rbp+20h]
0x180007a6f  mov     r14, [rbx+8]
0x180007a73  sub     r14, r12
0x180007a76  mov     rbx, [rbp+28h]
0x180007a7a  sub     rbx, r13
0x180007a7d  mov     r8, rbx
0x180007a80  cmp     rbx, r14
0x180007a83  cmovnb  r8, r14
0x180007a87  mov     rdx, r13
0x180007a8a  mov     rcx, r12
0x180007a8d  call    __std_mismatch_1
0x180007a92  cmp     rax, rbx
0x180007a95  jz      short loc_180007AC6
0x180007a97  cmp     rax, r14
0x180007a9a  jnz     short loc_180007ABC
0x180007a9c  mov     rcx, [rdi]; this
0x180007a9f  call    ?OnUserLogoff@State@ApplicationStateTable@Broker@@QEAA_NXZ; Broker::ApplicationStateTable::State::OnUserLogoff(void)
0x180007aa4  test    al, al
0x180007aa6  jnz     short loc_180007AE9
0x180007aa8  mov     rax, rdi
0x180007aab  add     rsp, 48h
0x180007aaf  pop     r15
0x180007ab1  pop     r14
0x180007ab3  pop     r13
0x180007ab5  pop     r12
0x180007ab7  pop     rdi
0x180007ab8  pop     rsi
0x180007ab9  pop     rbp
0x180007aba  pop     rbx
0x180007abb  retn
0x180007abc  mov     cl, [rax+r13]
0x180007ac0  cmp     [r12+rax], cl
0x180007ac4  jb      short loc_180007A9C
0x180007ac6  cmp     rbp, [r15]
0x180007ac9  jz      short loc_180007A9C
0x180007acb  mov     rcx, [rdi]; this
0x180007ace  call    ?OnUserLogon@State@ApplicationStateTable@Broker@@QEAA_NXZ; Broker::ApplicationStateTable::State::OnUserLogon(void)
0x180007ad3  test    al, al
0x180007ad5  jz      short loc_180007AA8
0x180007ad7  mov     r8, [rdi]
0x180007ada  mov     edx, 6
0x180007adf  mov     rcx, rsi
0x180007ae2  call    ?OnAppEnable@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBUApplicationIdentity@2@@Z; Broker::BrokerBase::OnAppEnable(_BR_EVENT_CALL_REASON,Broker::ApplicationIdentity const &)
0x180007ae7  jmp     short loc_180007AA8
0x180007ae9  mov     r8, [rdi]
0x180007aec  mov     edx, 6
0x180007af1  mov     rcx, rsi
0x180007af4  call    ?OnAppDisable@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBUApplicationIdentity@2@@Z; Broker::BrokerBase::OnAppDisable(_BR_EVENT_CALL_REASON,Broker::ApplicationIdentity const &)
0x180007af9  jmp     short loc_180007AA8
```
