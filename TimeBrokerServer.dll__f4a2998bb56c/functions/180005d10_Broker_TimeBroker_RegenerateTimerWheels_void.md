# Broker::TimeBroker::RegenerateTimerWheels(void)

- ea: `0x180005d10`
- end: `0x180006061`
- name: `?RegenerateTimerWheels@TimeBroker@Broker@@AEAAXXZ`
- size: `849`
- prototype: `void __fastcall(Broker::TimeBroker *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180001c14`
- `0x180005400`
- `0x180005760`

## callees

- `0x180003800`
- `0x1800050d0`
- `0x180005c50`
- `0x180005d10`
- `0x1800061e0`
- `0x18000b990`
- `0x180013978`
- `0x18001c010`

## import_xrefs

- `BrokerLib!BrBufferFree` at `0x180005f75`
- `BrokerLib!BrBufferFree` at `0x180005f75`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180005e6d`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180005e6d`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x180005e1c`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x180005e1c`

## pseudocode

```c
void __fastcall Broker::TimeBroker::RegenerateTimerWheels(Broker::TimeBroker *this)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rbx
  _QWORD *v4; // rbx
  _QWORD *v5; // rbx
  _QWORD *v6; // rbx
  unsigned int v7; // eax
  unsigned int v8; // ebx
  unsigned int i; // edi
  unsigned int BrokeredEventInfo2; // eax
  __int64 v11; // r8
  unsigned int v12; // ebx
  __int64 v13; // rbx
  __int64 v14; // rax
  _DWORD *v15; // rsi
  volatile signed __int32 *v16; // rbx
  int v17; // ecx
  _QWORD *v18; // rax
  __int128 v19; // [rsp+30h] [rbp-D8h] BYREF
  __int128 v20; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B8h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v23; // [rsp+68h] [rbp-A0h]
  int v24; // [rsp+78h] [rbp-90h]
  unsigned int v25; // [rsp+80h] [rbp-88h]
  void **v26; // [rsp+88h] [rbp-80h] BYREF
  __int128 v27; // [rsp+90h] [rbp-78h]
  int v28; // [rsp+A0h] [rbp-68h]
  unsigned int v29; // [rsp+A8h] [rbp-60h]
  void **v30; // [rsp+B0h] [rbp-58h] BYREF
  _DWORD v31[20]; // [rsp+B8h] [rbp-50h] BYREF
  unsigned int v32; // [rsp+110h] [rbp+8h] BYREF
  __int64 v33; // [rsp+118h] [rbp+10h] BYREF
  __int64 v34; // [rsp+120h] [rbp+18h] BYREF

  v2 = *(_QWORD **)this;
  std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(
    (__int64)this,
    (__int64)this,
    *(_QWORD *)(*(_QWORD *)this + 8LL));
  v2[1] = v2;
  *v2 = v2;
  v2[2] = v2;
  *((_QWORD *)this + 1) = 0;
  v3 = (_QWORD *)*((_QWORD *)this + 4);
  std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(
    (__int64)this + 32,
    (__int64)this + 32,
    v3[1]);
  v3[1] = v3;
  *v3 = v3;
  v3[2] = v3;
  *((_QWORD *)this + 5) = 0;
  v4 = (_QWORD *)*((_QWORD *)this + 2);
  std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(
    (__int64)this + 16,
    (__int64)this + 16,
    v4[1]);
  v4[1] = v4;
  *v4 = v4;
  v4[2] = v4;
  *((_QWORD *)this + 3) = 0;
  v5 = (_QWORD *)*((_QWORD *)this + 6);
  std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(
    (__int64)this + 48,
    (__int64)this + 48,
    v5[1]);
  v5[1] = v5;
  *v5 = v5;
  v5[2] = v5;
  *((_QWORD *)this + 7) = 0;
  v6 = (_QWORD *)*((_QWORD *)this + 8);
  std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(
    (__int64)this + 64,
    (__int64)this + 64,
    v6[1]);
  v6[1] = v6;
  *v6 = v6;
  v6[2] = v6;
  *((_QWORD *)this + 9) = 0;
  if ( *((_QWORD *)this + 24) )
  {
    v32 = 0;
    v33 = 0;
    v7 = BrQueryBrokeredEvents2(*((_QWORD *)this + 24), 0, 0, 0xFFFFFFFFLL, &v32, &v33);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v8 = v7;
      if ( v7 )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v7);
        v23 = 0;
        v24 = 1;
        pExceptionObject = &Broker::Win32Error::`vftable';
        v25 = v8;
        throw (Broker::Win32Error *)&pExceptionObject;
      }
      for ( i = 0; i < v32; ++i )
      {
        v34 = 0;
        BrokeredEventInfo2 = BrGetBrokeredEventInfo2(*((_QWORD *)this + 24), *(_QWORD *)(v33 + 8LL * i), 0, 0, &v34);
        v12 = BrokeredEventInfo2;
        if ( BrokeredEventInfo2 )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51,
              &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
              BrokeredEventInfo2);
          v27 = 0;
          v28 = 1;
          v26 = &Broker::Win32Error::`vftable';
          v29 = v12;
          throw (Broker::Win32Error *)&v26;
        }
        v13 = v34;
        v14 = *(_QWORD *)(v34 + 8);
        if ( v14 )
          _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
        v15 = *(_DWORD **)v13;
        *(_QWORD *)&v19 = v15;
        v16 = *(volatile signed __int32 **)(v13 + 8);
        *((_QWORD *)&v19 + 1) = v16;
        v17 = v15[22];
        if ( ((v17 - 2) & 0xFFFFFFFC) == 0 && v17 != 3 )
        {
          (*(void (__fastcall **)(_DWORD *, _QWORD))(*(_QWORD *)v15 + 16LL))(v15, *((_QWORD *)this + 25));
          if ( v15[18] == 3 )
          {
            v18 = std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(&v21, &v19);
            Broker::TimeBroker::AlignKeepAliveTimers((__int64)this, v18);
          }
        }
        v20 = 0;
        if ( v16 )
          _InterlockedIncrement(v16 + 2);
        v20 = v19;
        Broker::TimeBroker::InsertIntoTimerWheelIfNecessary(this, &v20, v11);
        if ( v16 && _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
          if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        }
      }
      if ( v33 )
        BrBufferFree();
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &Broker::Win32Error `RTTI Type Descriptor', (Broker::Win32Error *)&v30) )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v31[6]);
        if ( v33 )
          BrBufferFree();
        v30 = &std::exception::`vftable';
        o___std_exception_destroy_0(v31);
        __eh34_try_continuation(0, &Broker::Win32Error `RTTI Type Descriptor', &loc_18000605C);
      }
    }
  }
}

```

## disassembly

```asm
0x180005d10  push    rbx
0x180005d12  push    rsi
0x180005d13  push    rdi
0x180005d14  push    r14
0x180005d16  push    r15
0x180005d18  sub     rsp, 0E0h
0x180005d1f  mov     r14, rcx
0x180005d22  mov     rbx, [rcx]
0x180005d25  mov     r8, [rbx+8]
0x180005d29  mov     rdx, rcx
0x180005d2c  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>> &,std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *> *)
0x180005d31  mov     [rbx+8], rbx
0x180005d35  mov     [rbx], rbx
0x180005d38  mov     [rbx+10h], rbx
0x180005d3c  xor     r15d, r15d
0x180005d3f  mov     [r14+8], r15
0x180005d43  mov     rbx, [r14+20h]
0x180005d47  mov     r8, [rbx+8]
0x180005d4b  lea     rdx, [r14+20h]
0x180005d4f  lea     rcx, [r14+20h]
0x180005d53  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>> &,std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *> *)
0x180005d58  mov     [rbx+8], rbx
0x180005d5c  mov     [rbx], rbx
0x180005d5f  mov     [rbx+10h], rbx
0x180005d63  mov     [r14+28h], r15
0x180005d67  mov     rbx, [r14+10h]
0x180005d6b  mov     r8, [rbx+8]
0x180005d6f  lea     rdx, [r14+10h]
0x180005d73  lea     rcx, [r14+10h]
0x180005d77  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>> &,std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *> *)
0x180005d7c  mov     [rbx+8], rbx
0x180005d80  mov     [rbx], rbx
0x180005d83  mov     [rbx+10h], rbx
0x180005d87  mov     [r14+18h], r15
0x180005d8b  mov     rbx, [r14+30h]
0x180005d8f  mov     r8, [rbx+8]
0x180005d93  lea     rdx, [r14+30h]
0x180005d97  lea     rcx, [r14+30h]
0x180005d9b  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>> &,std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *> *)
0x180005da0  mov     [rbx+8], rbx
0x180005da4  mov     [rbx], rbx
0x180005da7  mov     [rbx+10h], rbx
0x180005dab  mov     [r14+38h], r15
0x180005daf  mov     rbx, [r14+40h]
0x180005db3  mov     r8, [rbx+8]
0x180005db7  lea     rdx, [r14+40h]
0x180005dbb  lea     rcx, [r14+40h]
0x180005dbf  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>> &,std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *> *)
0x180005dc4  mov     [rbx+8], rbx
0x180005dc8  mov     [rbx], rbx
0x180005dcb  mov     [rbx+10h], rbx
0x180005dcf  mov     [r14+48h], r15
0x180005dd3  cmp     [r14+0C0h], r15
0x180005dda  jz      loc_180005F7C
0x180005de0  mov     [rsp+108h+arg_0], r15d
0x180005de8  mov     [rsp+108h+arg_8], r15
0x180005df0  lea     rax, [rsp+108h+arg_8]
0x180005df8  mov     [rsp+108h+var_E0], rax
0x180005dfd  lea     rax, [rsp+108h+arg_0]
0x180005e05  mov     [rsp+108h+var_E8], rax
0x180005e0a  mov     r9d, 0FFFFFFFFh
0x180005e10  xor     r8d, r8d
0x180005e13  xor     edx, edx
0x180005e15  mov     rcx, [r14+0C0h]
0x180005e1c  call    cs:__imp_BrQueryBrokeredEvents2
0x180005e22  mov     ebx, eax
0x180005e24  test    eax, eax
0x180005e26  jnz     loc_180005F8B
0x180005e2c  mov     edi, r15d
0x180005e2f  nop
0x180005e30  cmp     edi, [rsp+108h+arg_0]
0x180005e37  jnb     loc_180005F68
0x180005e3d  mov     [rsp+108h+arg_10], r15
0x180005e45  mov     eax, edi
0x180005e47  lea     rcx, [rsp+108h+arg_10]
0x180005e4f  mov     [rsp+108h+var_E8], rcx
0x180005e54  xor     r9d, r9d
0x180005e57  xor     r8d, r8d
0x180005e5a  mov     rdx, [rsp+108h+arg_8]
0x180005e62  mov     rdx, [rdx+rax*8]
0x180005e66  mov     rcx, [r14+0C0h]
0x180005e6d  call    cs:__imp_BrGetBrokeredEventInfo2
0x180005e73  mov     ebx, eax
0x180005e75  test    eax, eax
0x180005e77  jnz     loc_180005FED
0x180005e7d  mov     rbx, [rsp+108h+arg_10]
0x180005e85  mov     rax, [rbx+8]
0x180005e89  test    rax, rax
0x180005e8c  jz      short loc_180005E92
0x180005e8e  lock inc dword ptr [rax+8]
0x180005e92  mov     rsi, [rbx]
0x180005e95  mov     qword ptr [rsp+108h+var_D8], rsi
0x180005e9a  mov     rbx, [rbx+8]
0x180005e9e  mov     qword ptr [rsp+108h+var_D8+8], rbx
0x180005ea3  mov     ecx, [rsi+58h]
0x180005ea6  lea     eax, [rcx-2]
0x180005ea9  test    eax, 0FFFFFFFCh
0x180005eae  jz      short loc_180005F24
0x180005eb0  xorps   xmm0, xmm0
0x180005eb3  movdqa  [rsp+108h+var_C8], xmm0
0x180005eb9  test    rbx, rbx
0x180005ebc  jz      short loc_180005EC2
0x180005ebe  lock inc dword ptr [rbx+8]
0x180005ec2  movaps  xmm0, [rsp+108h+var_D8]
0x180005ec7  movdqa  [rsp+108h+var_C8], xmm0
0x180005ecd  lea     rdx, [rsp+108h+var_C8]
0x180005ed2  mov     rcx, r14
0x180005ed5  call    ?InsertIntoTimerWheelIfNecessary@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z; Broker::TimeBroker::InsertIntoTimerWheelIfNecessary(std::shared_ptr<Broker::TimeEvent>)
0x180005eda  nop
0x180005edb  test    rbx, rbx
0x180005ede  jz      short loc_180005EEF
0x180005ee0  mov     eax, 0FFFFFFFFh
0x180005ee5  lock xadd [rbx+8], eax
0x180005eea  cmp     eax, 1
0x180005eed  jz      short loc_180005EF6
0x180005eef  inc     edi
0x180005ef1  jmp     loc_180005E30
0x180005ef6  mov     rax, [rbx]
0x180005ef9  mov     rcx, rbx
0x180005efc  mov     rax, [rax]
0x180005eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f04  mov     eax, 0FFFFFFFFh
0x180005f09  lock xadd [rbx+0Ch], eax
0x180005f0e  cmp     eax, 1
0x180005f11  jnz     short loc_180005EEF
0x180005f13  mov     rax, [rbx]
0x180005f16  mov     rcx, rbx
0x180005f19  mov     rax, [rax+8]
0x180005f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f22  jmp     short loc_180005EEF
0x180005f24  cmp     ecx, 3
0x180005f27  jz      short loc_180005EB0
0x180005f29  mov     rax, [rsi]
0x180005f2c  mov     rdx, [r14+0C8h]
0x180005f33  mov     rcx, rsi
0x180005f36  mov     rax, [rax+10h]
0x180005f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f3f  cmp     dword ptr [rsi+48h], 3
0x180005f43  jnz     loc_180005EB0
0x180005f49  lea     rdx, [rsp+108h+var_D8]
0x180005f4e  lea     rcx, [rsp+108h+var_B8]
0x180005f53  call    ??0?$shared_ptr@VTimeEvent@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(std::shared_ptr<Broker::TimeEvent> const &)
0x180005f58  mov     rdx, rax
0x180005f5b  mov     rcx, r14
0x180005f5e  call    ?AlignKeepAliveTimers@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z; Broker::TimeBroker::AlignKeepAliveTimers(std::shared_ptr<Broker::TimeEvent>)
0x180005f63  jmp     loc_180005EB0
0x180005f68  mov     rcx, [rsp+108h+arg_8]
0x180005f70  test    rcx, rcx
0x180005f73  jz      short loc_180005F7C
0x180005f75  call    cs:__imp_BrBufferFree
0x180005f7b  nop
0x180005f7c  add     rsp, 0E0h
0x180005f83  pop     r15
0x180005f85  pop     r14
0x180005f87  pop     rdi
0x180005f88  pop     rsi
0x180005f89  pop     rbx
0x180005f8a  retn
0x180005f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f92  test    dword ptr [rcx+1Ch], 100h
0x180005f99  jz      short loc_180005FB9
0x180005f9b  cmp     byte ptr [rcx+19h], 2
0x180005f9f  jb      short loc_180005FB9
0x180005fa1  mov     edx, 32h ; '2'
0x180005fa6  mov     r9d, ebx
0x180005fa9  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180005fb0  mov     rcx, [rcx+10h]
0x180005fb4  call    WPP_SF_d
0x180005fb9  xorps   xmm0, xmm0
0x180005fbc  movups  [rsp+108h+var_A0], xmm0
0x180005fc1  mov     [rsp+108h+var_90], 1
0x180005fc9  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180005fd0  mov     [rsp+108h+pExceptionObject], rax
0x180005fd5  mov     [rsp+108h+var_88], ebx
0x180005fdc  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180005fe3  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180005fe8  call    _CxxThrowException_0
0x180005fed  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ff4  test    dword ptr [rcx+1Ch], 100h
0x180005ffb  jz      short loc_18000601B
0x180005ffd  cmp     byte ptr [rcx+19h], 2
0x180006001  jb      short loc_18000601B
0x180006003  mov     edx, 33h ; '3'
0x180006008  mov     r9d, ebx
0x18000600b  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180006012  mov     rcx, [rcx+10h]
0x180006016  call    WPP_SF_d
0x18000601b  xorps   xmm0, xmm0
0x18000601e  movups  [rsp+108h+var_78], xmm0
0x180006026  mov     [rsp+108h+var_68], 1
0x180006031  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180006038  mov     [rsp+108h+var_80], rax
0x180006040  mov     [rsp+108h+var_60], ebx
0x180006047  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000604e  lea     rcx, [rsp+108h+var_80]; pExceptionObject
0x180006056  call    _CxxThrowException_0
0x18000605c  jmp     loc_180005F7C
```
