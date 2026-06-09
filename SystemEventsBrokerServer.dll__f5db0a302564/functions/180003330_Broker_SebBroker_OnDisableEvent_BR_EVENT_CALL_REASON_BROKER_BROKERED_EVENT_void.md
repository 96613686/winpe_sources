# Broker::SebBroker::OnDisableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)

- ea: `0x180003330`
- end: `0x1800034c4`
- name: `?OnDisableEvent@SebBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z`
- size: `404`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800030e0`
- `0x180003330`
- `0x1800034d0`
- `0x180005a50`
- `0x180027010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall Broker::SebBroker::OnDisableEvent(__int64 a1, __int64 a2, __int64 a3, Broker::SebEvent **a4)
{
  _QWORD *v7; // rcx
  __int128 v8; // xmm0
  unsigned int v9; // esi

  v7 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( Broker::SebBroker::Instance && *(_BYTE *)Broker::SebBroker::Instance )
  {
    if ( *(&Broker::SebBroker::Instance + 1) )
    {
      _InterlockedIncrement((volatile signed __int32 *)*(&Broker::SebBroker::Instance + 1) + 2);
      v7 = WPP_GLOBAL_Control;
    }
    v8 = *(_OWORD *)&Broker::SebBroker::Instance;
  }
  else
  {
    v8 = 0;
  }
  if ( a2 && a3 && a4 )
  {
    if ( (_QWORD)v8 )
    {
      if ( *(_QWORD *)(v8 + 136) == a2 )
      {
        Broker::SebEvent::OnDisable(*a4);
        v9 = 0;
        v7 = WPP_GLOBAL_Control;
      }
      else
      {
        v9 = 5;
      }
    }
    else
    {
      v9 = 21;
    }
  }
  else
  {
    v9 = 87;
  }
  if ( (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 4u )
    WPP_SF_d(v7[2], 130, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v9);
  if ( *((_QWORD *)&v8 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v8 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (***((void (__fastcall ****)(_QWORD))&v8 + 1))(*((_QWORD *)&v8 + 1));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v8 + 1) + 12LL), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v8 + 1) + 8LL))(*((_QWORD *)&v8 + 1));
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180003330  mov     [rsp+arg_0], rbx
0x180003335  mov     [rsp+arg_10], rsi
0x18000333a  push    rdi
0x18000333b  sub     rsp, 30h
0x18000333f  mov     rbx, r9
0x180003342  mov     rsi, r8
0x180003345  mov     rdi, rdx
0x180003348  mov     rcx, cs:WPP_GLOBAL_Control
0x18000334f  test    byte ptr [rcx+1Ch], 1
0x180003353  jnz     loc_18000343B
0x180003359  mov     rax, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x180003360  test    rax, rax
0x180003363  jz      loc_180003466
0x180003369  cmp     byte ptr [rax], 0
0x18000336c  jz      loc_180003466
0x180003372  mov     rax, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x180003379  test    rax, rax
0x18000337c  jz      short loc_180003389
0x18000337e  lock inc dword ptr [rax+8]
0x180003382  mov     rcx, cs:WPP_GLOBAL_Control
0x180003389  movups  xmm0, cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x180003390  movdqu  [rsp+38h+var_18], xmm0
0x180003396  test    rdi, rdi
0x180003399  jz      loc_1800034B9
0x18000339f  test    rsi, rsi
0x1800033a2  jz      loc_1800034B9
0x1800033a8  test    rbx, rbx
0x1800033ab  jz      loc_1800034B9
0x1800033b1  movq    rax, xmm0
0x1800033b6  test    rax, rax
0x1800033b9  jz      loc_180003495
0x1800033bf  cmp     [rax+88h], rdi
0x1800033c6  jnz     loc_18000349F
0x1800033cc  mov     rcx, [rbx]; this
0x1800033cf  call    ?OnDisable@SebEvent@Broker@@QEAAX_N@Z; Broker::SebEvent::OnDisable(bool)
0x1800033d4  xor     esi, esi
0x1800033d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033dd  test    byte ptr [rcx+1Ch], 1
0x1800033e1  jnz     loc_18000346E
0x1800033e7  mov     rbx, qword ptr [rsp+38h+var_18+8]
0x1800033ec  test    rbx, rbx
0x1800033ef  jz      short loc_180003429
0x1800033f1  mov     edi, 0FFFFFFFFh
0x1800033f6  mov     eax, edi
0x1800033f8  lock xadd [rbx+8], eax
0x1800033fd  cmp     eax, 1
0x180003400  jnz     short loc_180003429
0x180003402  mov     rax, [rbx]
0x180003405  mov     rcx, rbx
0x180003408  mov     rax, [rax]
0x18000340b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003410  lock xadd [rbx+0Ch], edi
0x180003415  cmp     edi, 1
0x180003418  jnz     short loc_180003429
0x18000341a  mov     rcx, [rbx]
0x18000341d  mov     rax, [rcx+8]
0x180003421  mov     rcx, rbx
0x180003424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003429  mov     eax, esi
0x18000342b  mov     rbx, [rsp+38h+arg_0]
0x180003430  mov     rsi, [rsp+38h+arg_10]
0x180003435  add     rsp, 30h
0x180003439  pop     rdi
0x18000343a  retn
0x18000343b  cmp     byte ptr [rcx+19h], 4
0x18000343f  jb      loc_180003359
0x180003445  mov     edx, 80h
0x18000344a  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180003451  mov     rcx, [rcx+10h]
0x180003455  call    WPP_SF_
0x18000345a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003461  jmp     loc_180003359
0x180003466  xorps   xmm0, xmm0
0x180003469  jmp     loc_180003390
0x18000346e  cmp     byte ptr [rcx+19h], 4
0x180003472  jb      loc_1800033E7
0x180003478  mov     edx, 82h
0x18000347d  mov     r9d, esi
0x180003480  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180003487  mov     rcx, [rcx+10h]
0x18000348b  call    WPP_SF_d
0x180003490  jmp     loc_1800033E7
0x180003495  mov     esi, 15h
0x18000349a  jmp     loc_1800033DD
0x18000349f  mov     esi, 5
0x1800034a4  jmp     loc_1800033DD
0x1800034a9  mov     esi, [rsp+38h+arg_8]
0x1800034ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034b4  jmp     loc_1800033DD
0x1800034b9  mov     esi, 57h ; 'W'
0x1800034be  jmp     loc_1800033DD
```
