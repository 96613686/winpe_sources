# Broker::TimeBroker::RemoveFromTimerWheel(std::shared_ptr<Broker::TimeEvent>)

- ea: `0x1800074c0`
- end: `0x180007826`
- name: `?RemoveFromTimerWheel@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z`
- size: `870`
- prototype: `void __fastcall(Broker::TimeBroker *this, __int64 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000215c`
- `0x180003868`
- `0x18000874c`
- `0x18000f6f0`

## callees

- `0x1800074c0`
- `0x180007830`
- `0x180007c60`
- `0x1800131e4`
- `0x18001c010`

## pseudocode

```c
void __fastcall Broker::TimeBroker::RemoveFromTimerWheel(Broker::TimeBroker *this, __int64 *a2)
{
  __int64 *v2; // rdi
  Broker::TimeBroker *v3; // rsi
  __int64 **v4; // r14
  __int64 **v5; // r12
  __int64 v6; // rax
  __int64 v7; // rbp
  volatile signed __int32 *v8; // r15
  __int64 *v9; // rbx
  __int64 *v10; // rdx
  __int64 i; // rax
  __int64 v12; // rcx
  __int64 **v13; // rsi
  volatile signed __int32 *v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rbp
  volatile signed __int32 *v17; // r14
  __int64 *v18; // rbx
  __int64 *v19; // rdx
  _BYTE *v20; // rcx
  __int64 v21; // rax
  __int64 **v22; // rsi
  volatile signed __int32 *v23; // rdi
  volatile signed __int32 *v24; // rbx
  __int64 j; // rax

  v2 = a2;
  v3 = this;
  v4 = *(__int64 ***)(*a2 + 224);
  v5 = *(__int64 ***)(*a2 + 232);
  if ( !v4 )
    goto LABEL_16;
  v6 = a2[1];
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  v7 = *a2;
  v8 = (volatile signed __int32 *)a2[1];
  v9 = (__int64 *)**v4;
  while ( v9 != *v4 )
  {
    v10 = v9;
    i = v9[2];
    if ( *(_BYTE *)(i + 25) )
    {
      for ( i = v9[1]; !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
      {
        if ( v9 != *(__int64 **)(i + 16) )
          break;
        v9 = (__int64 *)i;
      }
    }
    else
    {
      v12 = *(_QWORD *)i;
      if ( !*(_BYTE *)(*(_QWORD *)i + 25LL) )
      {
        do
        {
          v9 = (__int64 *)v12;
          v12 = *(_QWORD *)v12;
        }
        while ( !*(_BYTE *)(v12 + 25) );
        goto LABEL_9;
      }
    }
    v9 = (__int64 *)i;
LABEL_9:
    if ( v10[5] == v7 )
    {
      v13 = std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Extract(
              v4,
              (__int64 **)v10);
      v14 = (volatile signed __int32 *)v13[6];
      if ( v14 && _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
      operator delete(v13);
    }
  }
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  v2 = a2;
  *(_QWORD *)(*a2 + 224) = 0;
  v3 = this;
LABEL_16:
  if ( v5 )
  {
    v15 = v2[1];
    if ( v15 )
      _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
    v16 = *v2;
    v17 = (volatile signed __int32 *)v2[1];
    v18 = (__int64 *)**v5;
    while ( v18 != *v5 )
    {
      v19 = v18;
      v20 = (_BYTE *)v18[2];
      if ( v20[25] )
      {
        for ( j = v18[1]; !*(_BYTE *)(j + 25); j = *(_QWORD *)(j + 8) )
        {
          if ( v18 != *(__int64 **)(j + 16) )
            break;
          v18 = (__int64 *)j;
        }
        v18 = (__int64 *)j;
      }
      else
      {
        v21 = *(_QWORD *)v20;
        if ( *(_BYTE *)(*(_QWORD *)v20 + 25LL) )
        {
          v18 = (__int64 *)v18[2];
        }
        else
        {
          do
          {
            v18 = (__int64 *)v21;
            v21 = *(_QWORD *)v21;
          }
          while ( !*(_BYTE *)(v21 + 25) );
        }
      }
      if ( v19[5] == v16 )
      {
        v22 = std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Extract(
                v5,
                (__int64 **)v19);
        v23 = (volatile signed __int32 *)v22[6];
        if ( v23 )
        {
          if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
            if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
          }
        }
        operator delete(v22);
      }
    }
    if ( v17 )
    {
      if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    v2 = a2;
    *(_QWORD *)(*a2 + 232) = 0;
    v3 = this;
  }
  Broker::TimeBroker::SetSytemTimer(v3);
  v24 = (volatile signed __int32 *)v2[1];
  if ( v24 )
  {
    if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
      if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    }
  }
}

```

## disassembly

```asm
0x1800074c0  mov     [rsp+arg_18], rbx
0x1800074c5  mov     [rsp+arg_8], rdx
0x1800074ca  mov     [rsp+arg_0], rcx
0x1800074cf  push    rbp
0x1800074d0  push    rsi
0x1800074d1  push    rdi
0x1800074d2  push    r12
0x1800074d4  push    r13
0x1800074d6  push    r14
0x1800074d8  push    r15
0x1800074da  sub     rsp, 30h
0x1800074de  mov     rdi, rdx
0x1800074e1  mov     rsi, rcx
0x1800074e4  mov     rax, [rdx]
0x1800074e7  mov     r14, [rax+0E0h]
0x1800074ee  mov     r12, [rax+0E8h]
0x1800074f5  mov     r13d, 0FFFFFFFFh
0x1800074fb  test    r14, r14
0x1800074fe  jz      loc_1800075C8
0x180007504  mov     rax, [rdx+8]
0x180007508  test    rax, rax
0x18000750b  jz      short loc_180007511
0x18000750d  lock inc dword ptr [rax+8]
0x180007511  mov     rbp, [rdx]
0x180007514  mov     r15, [rdx+8]
0x180007518  mov     rbx, [r14]
0x18000751b  mov     rbx, [rbx]
0x18000751e  xchg    ax, ax
0x180007520  cmp     rbx, [r14]
0x180007523  jz      short loc_180007599
0x180007525  mov     rdx, rbx
0x180007528  mov     r8, rbx
0x18000752b  mov     rax, [rbx+10h]
0x18000752f  cmp     byte ptr [rax+19h], 0
0x180007533  jnz     loc_1800076D3
0x180007539  mov     rcx, [rax]
0x18000753c  cmp     byte ptr [rcx+19h], 0
0x180007540  jnz     loc_1800076F0
0x180007546  nop     word ptr [rax+rax+00000000h]
0x180007550  mov     rbx, rcx
0x180007553  mov     rax, [rcx]
0x180007556  mov     rcx, rax
0x180007559  cmp     byte ptr [rax+19h], 0
0x18000755d  jz      short loc_180007550
0x18000755f  cmp     [rdx+28h], rbp
0x180007563  jnz     short loc_180007520
0x180007565  mov     rcx, r14
0x180007568  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>,std::_Iterator_base0>)
0x18000756d  mov     rsi, rax
0x180007570  mov     rdi, [rax+30h]
0x180007574  test    rdi, rdi
0x180007577  jz      short loc_18000758A
0x180007579  mov     ecx, r13d
0x18000757c  lock xadd [rdi+8], ecx
0x180007581  cmp     ecx, 1
0x180007584  jz      loc_18000771D
0x18000758a  mov     edx, 38h ; '8'; unsigned __int64
0x18000758f  mov     rcx, rsi; void *
0x180007592  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007597  jmp     short loc_180007520
0x180007599  test    r15, r15
0x18000759c  jz      short loc_1800075B0
0x18000759e  mov     eax, r13d
0x1800075a1  lock xadd [r15+8], eax
0x1800075a7  cmp     eax, 1
0x1800075aa  jz      loc_1800077B5
0x1800075b0  mov     rdi, [rsp+68h+arg_8]
0x1800075b5  mov     rax, [rdi]
0x1800075b8  mov     qword ptr [rax+0E0h], 0
0x1800075c3  mov     rsi, [rsp+68h+arg_0]
0x1800075c8  test    r12, r12
0x1800075cb  jz      loc_180007698
0x1800075d1  mov     rax, [rdi+8]
0x1800075d5  test    rax, rax
0x1800075d8  jz      short loc_1800075DE
0x1800075da  lock inc dword ptr [rax+8]
0x1800075de  mov     rbp, [rdi]
0x1800075e1  mov     r14, [rdi+8]
0x1800075e5  mov     rbx, [r12]
0x1800075e9  mov     rbx, [rbx]
0x1800075ec  nop     dword ptr [rax+00h]
0x1800075f0  cmp     rbx, [r12]
0x1800075f4  jz      short loc_180007669
0x1800075f6  mov     rdx, rbx
0x1800075f9  mov     r8, rbx
0x1800075fc  mov     rcx, [rbx+10h]
0x180007600  cmp     byte ptr [rcx+19h], 0
0x180007604  jnz     loc_1800076F8
0x18000760a  mov     rax, [rcx]
0x18000760d  cmp     byte ptr [rax+19h], 0
0x180007611  jnz     loc_18000781D
0x180007617  nop     word ptr [rax+rax+00000000h]
0x180007620  mov     rbx, rax
0x180007623  mov     rcx, [rax]
0x180007626  mov     rax, rcx
0x180007629  cmp     byte ptr [rcx+19h], 0
0x18000762d  jz      short loc_180007620
0x18000762f  cmp     [rdx+28h], rbp
0x180007633  jnz     short loc_1800075F0
0x180007635  mov     rcx, r12
0x180007638  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>,std::_Iterator_base0>)
0x18000763d  mov     rsi, rax
0x180007640  mov     rdi, [rax+30h]
0x180007644  test    rdi, rdi
0x180007647  jz      short loc_18000765A
0x180007649  mov     ecx, r13d
0x18000764c  lock xadd [rdi+8], ecx
0x180007651  cmp     ecx, 1
0x180007654  jz      loc_180007750
0x18000765a  mov     edx, 38h ; '8'; unsigned __int64
0x18000765f  mov     rcx, rsi; void *
0x180007662  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007667  jmp     short loc_1800075F0
0x180007669  test    r14, r14
0x18000766c  jz      short loc_180007680
0x18000766e  mov     eax, r13d
0x180007671  lock xadd [r14+8], eax
0x180007677  cmp     eax, 1
0x18000767a  jz      loc_1800077E9
0x180007680  mov     rdi, [rsp+68h+arg_8]
0x180007685  mov     rax, [rdi]
0x180007688  mov     qword ptr [rax+0E8h], 0
0x180007693  mov     rsi, [rsp+68h+arg_0]
0x180007698  mov     rcx, rsi; this
0x18000769b  call    ?SetSytemTimer@TimeBroker@Broker@@AEAAXXZ; Broker::TimeBroker::SetSytemTimer(void)
0x1800076a0  nop
0x1800076a1  mov     rbx, [rdi+8]
0x1800076a5  test    rbx, rbx
0x1800076a8  jz      short loc_1800076BB
0x1800076aa  mov     eax, r13d
0x1800076ad  lock xadd [rbx+8], eax
0x1800076b2  cmp     eax, 1
0x1800076b5  jz      loc_180007783
0x1800076bb  mov     rbx, [rsp+68h+arg_18]
0x1800076c3  add     rsp, 30h
0x1800076c7  pop     r15
0x1800076c9  pop     r14
0x1800076cb  pop     r13
0x1800076cd  pop     r12
0x1800076cf  pop     rdi
0x1800076d0  pop     rsi
0x1800076d1  pop     rbp
0x1800076d2  retn
0x1800076d3  mov     rax, [rbx+8]
0x1800076d7  cmp     byte ptr [rax+19h], 0
0x1800076db  jnz     short loc_1800076F0
0x1800076dd  cmp     rbx, [rax+10h]
0x1800076e1  jnz     short loc_1800076F0
0x1800076e3  mov     rbx, rax
0x1800076e6  mov     rax, [rax+8]
0x1800076ea  cmp     byte ptr [rax+19h], 0
0x1800076ee  jz      short loc_1800076DD
0x1800076f0  mov     rbx, rax
0x1800076f3  jmp     loc_18000755F
0x1800076f8  mov     rax, [rbx+8]
0x1800076fc  cmp     byte ptr [rax+19h], 0
0x180007700  jnz     short loc_180007715
0x180007702  cmp     rbx, [rax+10h]
0x180007706  jnz     short loc_180007715
0x180007708  mov     rbx, rax
0x18000770b  mov     rax, [rax+8]
0x18000770f  cmp     byte ptr [rax+19h], 0
0x180007713  jz      short loc_180007702
0x180007715  mov     rbx, rax
0x180007718  jmp     loc_18000762F
0x18000771d  mov     rdx, [rdi]
0x180007720  mov     rcx, rdi
0x180007723  mov     rax, [rdx]
0x180007726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000772b  mov     eax, r13d
0x18000772e  lock xadd [rdi+0Ch], eax
0x180007733  cmp     eax, 1
0x180007736  jnz     loc_18000758A
0x18000773c  mov     rax, [rdi]
0x18000773f  mov     rcx, rdi
0x180007742  mov     rax, [rax+8]
0x180007746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000774b  jmp     loc_18000758A
0x180007750  mov     rdx, [rdi]
0x180007753  mov     rcx, rdi
0x180007756  mov     rax, [rdx]
0x180007759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000775e  mov     eax, r13d
0x180007761  lock xadd [rdi+0Ch], eax
0x180007766  cmp     eax, 1
0x180007769  jnz     loc_18000765A
0x18000776f  mov     rax, [rdi]
0x180007772  mov     rcx, rdi
0x180007775  mov     rax, [rax+8]
0x180007779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000777e  jmp     loc_18000765A
0x180007783  mov     rax, [rbx]
0x180007786  mov     rcx, rbx
0x180007789  mov     rax, [rax]
0x18000778c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007791  lock xadd [rbx+0Ch], r13d
0x180007797  cmp     r13d, 1
0x18000779b  jnz     loc_1800076BB
0x1800077a1  mov     rax, [rbx]
0x1800077a4  mov     rcx, rbx
0x1800077a7  mov     rax, [rax+8]
0x1800077ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077b0  jmp     loc_1800076BB
0x1800077b5  mov     rax, [r15]
0x1800077b8  mov     rcx, r15
0x1800077bb  mov     rax, [rax]
0x1800077be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077c3  mov     eax, r13d
0x1800077c6  lock xadd [r15+0Ch], eax
0x1800077cc  cmp     eax, 1
0x1800077cf  jnz     loc_1800075B0
0x1800077d5  mov     rax, [r15]
0x1800077d8  mov     rcx, r15
0x1800077db  mov     rax, [rax+8]
0x1800077df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077e4  jmp     loc_1800075B0
0x1800077e9  mov     rax, [r14]
0x1800077ec  mov     rcx, r14
0x1800077ef  mov     rax, [rax]
0x1800077f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077f7  mov     eax, r13d
0x1800077fa  lock xadd [r14+0Ch], eax
0x180007800  cmp     eax, 1
0x180007803  jnz     loc_180007680
0x180007809  mov     rax, [r14]
0x18000780c  mov     rcx, r14
0x18000780f  mov     rax, [rax+8]
0x180007813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007818  jmp     loc_180007680
0x18000781d  mov     rbx, rcx
0x180007820  jmp     loc_18000762F
```
