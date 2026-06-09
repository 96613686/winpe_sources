# Broker::TimeBroker::Dump(unsigned __int64)

- ea: `0x180010f0c`
- end: `0x1800111af`
- name: `?Dump@TimeBroker@Broker@@QEAAX_K@Z`
- size: `675`
- prototype: `void __fastcall(Broker::TimeBroker *this, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180010e88`

## callees

- `0x180002400`
- `0x180003800`
- `0x180003840`
- `0x180005b30`
- `0x180005b90`
- `0x180009fc0`
- `0x18000b990`
- `0x180010f0c`
- `0x180013978`
- `0x180016914`
- `0x18001c010`

## import_xrefs

- `BrokerLib!BrBufferFree` at `0x18001116e`
- `BrokerLib!BrBufferFree` at `0x18001116e`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x1800110b3`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x1800110b3`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x18001100d`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x18001100d`

## pseudocode

```c
void __fastcall Broker::TimeBroker::Dump(Broker::TimeBroker *this, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v4; // r9
  __int64 v5; // r9
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // eax
  unsigned int v9; // esi
  __int64 i; // rsi
  unsigned int BrokeredEventInfo2; // eax
  unsigned int v12; // r15d
  _QWORD *v13; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v14; // [rsp+38h] [rbp-B0h] BYREF
  std::_Ref_count_base *v15; // [rsp+40h] [rbp-A8h]
  void **pExceptionObject; // [rsp+48h] [rbp-A0h] BYREF
  __int128 v17; // [rsp+50h] [rbp-98h]
  int v18; // [rsp+60h] [rbp-88h]
  unsigned int v19; // [rsp+68h] [rbp-80h]
  void **v20; // [rsp+70h] [rbp-78h] BYREF
  __int128 v21; // [rsp+78h] [rbp-70h]
  int v22; // [rsp+88h] [rbp-60h]
  unsigned int v23; // [rsp+90h] [rbp-58h]
  void **v24; // [rsp+98h] [rbp-50h] BYREF
  _DWORD v25[18]; // [rsp+A0h] [rbp-48h] BYREF
  unsigned int v26; // [rsp+F0h] [rbp+8h] BYREF
  __int64 v27; // [rsp+F8h] [rbp+10h]
  char v28; // [rsp+100h] [rbp+18h] BYREF
  __int64 v29; // [rsp+108h] [rbp+20h] BYREF

  v27 = a2;
  v2 = a2;
  v26 = 0;
  v29 = 0;
  if ( *((_QWORD *)this + 24) )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      Broker::TimeBroker::BrokerLock::BrokerLock((Broker::TimeBroker::BrokerLock *)&v28, 1);
      WPP_SF_(v2, 38, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
      v4 = *(_QWORD *)(*((_QWORD *)this + 10) + 16LL);
      if ( v4 )
        WPP_SF_i(v2, 39, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v4);
      else
        WPP_SF_(v2, 40, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
      v5 = *(_QWORD *)(*((_QWORD *)this + 12) + 16LL);
      if ( v5 )
        WPP_SF_i(v2, 41, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v5);
      else
        WPP_SF_(v2, 42, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
      WPP_SF_l(v2, v6, v7, *((unsigned int *)this + 42));
      v8 = BrQueryBrokeredEvents2(*((_QWORD *)this + 24), 0, 0, 0xFFFFFFFFLL, &v26, &v29);
      v9 = v8;
      if ( v8 )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v8);
        v17 = 0;
        v18 = 1;
        pExceptionObject = &Broker::Win32Error::`vftable';
        v19 = v9;
        throw (Broker::Win32Error *)&pExceptionObject;
      }
      for ( i = 0; (unsigned int)i < v26; i = (unsigned int)(i + 1) )
      {
        v13 = 0;
        BrokeredEventInfo2 = BrGetBrokeredEventInfo2(*((_QWORD *)this + 24), *(_QWORD *)(v29 + 8 * i), 0, 0, &v13);
        v12 = BrokeredEventInfo2;
        if ( BrokeredEventInfo2 )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              45,
              &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
              BrokeredEventInfo2);
          v21 = 0;
          v22 = 1;
          v20 = &Broker::Win32Error::`vftable';
          v23 = v12;
          throw (Broker::Win32Error *)&v20;
        }
        std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(&v14, v13);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 8LL))(v14, v2);
        if ( v15 )
          std::_Ref_count_base::_Decref(v15);
      }
      if ( v29 )
        BrBufferFree();
      Broker::TimeBroker::BrokerLock::~BrokerLock((Broker::TimeBroker::BrokerLock *)&v28);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &Broker::Win32Error `RTTI Type Descriptor', (Broker::Win32Error *)&v24) )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v25[6]);
        if ( v29 )
          BrBufferFree();
        v24 = &std::exception::`vftable';
        o___std_exception_destroy_0(v25);
        v2 = v27;
        __eh34_try_continuation(0, &Broker::Win32Error `RTTI Type Descriptor', &loc_180011185);
      }
    }
  }
  WPP_SF_(v2, 47, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
}

```

## disassembly

```asm
0x180010f0c  mov     rax, rsp
0x180010f0f  mov     [rax+10h], rdx
0x180010f13  push    rsi
0x180010f14  push    rdi
0x180010f15  push    r14
0x180010f17  push    r15
0x180010f19  sub     rsp, 0C8h
0x180010f20  mov     rdi, rdx
0x180010f23  mov     r14, rcx
0x180010f26  mov     dword ptr [rax+8], 0
0x180010f2d  mov     qword ptr [rax+20h], 0
0x180010f35  cmp     qword ptr [rcx+0C0h], 0
0x180010f3d  jz      loc_18001118D
0x180010f43  mov     edx, 1; int
0x180010f48  lea     rcx, [rax+18h]; this
0x180010f4c  call    ??0BrokerLock@TimeBroker@Broker@@QEAA@H@Z; Broker::TimeBroker::BrokerLock::BrokerLock(int)
0x180010f51  nop
0x180010f52  mov     edx, 26h ; '&'
0x180010f57  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180010f5e  mov     rcx, rdi
0x180010f61  call    WPP_SF_
0x180010f66  mov     rax, [r14+50h]
0x180010f6a  mov     r9, [rax+10h]
0x180010f6e  test    r9, r9
0x180010f71  jz      short loc_180010F89
0x180010f73  mov     edx, 27h ; '''
0x180010f78  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180010f7f  mov     rcx, rdi
0x180010f82  call    WPP_SF_i
0x180010f87  jmp     short loc_180010F9D
0x180010f89  mov     edx, 28h ; '('
0x180010f8e  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180010f95  mov     rcx, rdi
0x180010f98  call    WPP_SF_
0x180010f9d  mov     rax, [r14+60h]
0x180010fa1  mov     r9, [rax+10h]
0x180010fa5  test    r9, r9
0x180010fa8  jz      short loc_180010FC0
0x180010faa  mov     edx, 29h ; ')'
0x180010faf  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180010fb6  mov     rcx, rdi
0x180010fb9  call    WPP_SF_i
0x180010fbe  jmp     short loc_180010FD4
0x180010fc0  mov     edx, 2Ah ; '*'
0x180010fc5  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180010fcc  mov     rcx, rdi
0x180010fcf  call    WPP_SF_
0x180010fd4  mov     r9d, [r14+0A8h]
0x180010fdb  mov     rcx, rdi
0x180010fde  call    WPP_SF_l
0x180010fe3  lea     rax, [rsp+0E8h+arg_18]
0x180010feb  mov     [rsp+0E8h+var_C0], rax
0x180010ff0  lea     rax, [rsp+0E8h+arg_0]
0x180010ff8  mov     [rsp+0E8h+var_C8], rax
0x180010ffd  or      r9d, 0FFFFFFFFh
0x180011001  xor     r8d, r8d
0x180011004  xor     edx, edx
0x180011006  mov     rcx, [r14+0C0h]
0x18001100d  call    cs:__imp_BrQueryBrokeredEvents2
0x180011013  mov     esi, eax
0x180011015  test    eax, eax
0x180011017  jz      short loc_180011078
0x180011019  mov     rcx, cs:WPP_GLOBAL_Control
0x180011020  test    dword ptr [rcx+1Ch], 100h
0x180011027  jz      short loc_180011047
0x180011029  cmp     byte ptr [rcx+19h], 2
0x18001102d  jb      short loc_180011047
0x18001102f  mov     edx, 2Ch ; ','
0x180011034  mov     r9d, eax
0x180011037  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18001103e  mov     rcx, [rcx+10h]
0x180011042  call    WPP_SF_d
0x180011047  xorps   xmm0, xmm0
0x18001104a  movups  [rsp+0E8h+var_98], xmm0
0x18001104f  mov     [rsp+0E8h+var_88], 1
0x180011057  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18001105e  mov     [rsp+0E8h+pExceptionObject], rax
0x180011063  mov     [rsp+0E8h+var_80], esi
0x180011067  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001106e  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180011073  call    _CxxThrowException_0
0x180011078  xor     esi, esi
0x18001107a  cmp     esi, [rsp+0E8h+arg_0]
0x180011081  jnb     loc_180011161
0x180011087  mov     [rsp+0E8h+var_B8], 0
0x180011090  lea     rcx, [rsp+0E8h+var_B8]
0x180011095  mov     [rsp+0E8h+var_C8], rcx
0x18001109a  xor     r9d, r9d
0x18001109d  xor     r8d, r8d
0x1800110a0  mov     rdx, [rsp+0E8h+arg_18]
0x1800110a8  mov     rdx, [rdx+rsi*8]
0x1800110ac  mov     rcx, [r14+0C0h]
0x1800110b3  call    cs:__imp_BrGetBrokeredEventInfo2
0x1800110b9  mov     r15d, eax
0x1800110bc  test    eax, eax
0x1800110be  jz      short loc_180011126
0x1800110c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110c7  test    dword ptr [rcx+1Ch], 100h
0x1800110ce  jz      short loc_1800110EE
0x1800110d0  cmp     byte ptr [rcx+19h], 2
0x1800110d4  jb      short loc_1800110EE
0x1800110d6  mov     edx, 2Dh ; '-'
0x1800110db  mov     r9d, eax
0x1800110de  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x1800110e5  mov     rcx, [rcx+10h]
0x1800110e9  call    WPP_SF_d
0x1800110ee  xorps   xmm0, xmm0
0x1800110f1  movups  [rsp+0E8h+var_70], xmm0
0x1800110f6  mov     [rsp+0E8h+var_60], 1
0x180011101  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180011108  mov     [rsp+0E8h+var_78], rax
0x18001110d  mov     [rsp+0E8h+var_58], r15d
0x180011115  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001111c  lea     rcx, [rsp+0E8h+var_78]; pExceptionObject
0x180011121  call    _CxxThrowException_0
0x180011126  mov     rdx, [rsp+0E8h+var_B8]
0x18001112b  lea     rcx, [rsp+0E8h+var_B0]
0x180011130  call    ??0?$shared_ptr@VTimeEvent@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(std::shared_ptr<Broker::TimeEvent> const &)
0x180011135  nop
0x180011136  mov     rcx, [rsp+0E8h+var_B0]
0x18001113b  mov     rax, [rcx]
0x18001113e  mov     rdx, rdi
0x180011141  mov     rax, [rax+8]
0x180011145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001114a  nop
0x18001114b  mov     rcx, [rsp+0E8h+var_A8]; this
0x180011150  test    rcx, rcx
0x180011153  jz      short loc_18001115A
0x180011155  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001115a  inc     esi
0x18001115c  jmp     loc_18001107A
0x180011161  mov     rcx, [rsp+0E8h+arg_18]
0x180011169  test    rcx, rcx
0x18001116c  jz      short loc_180011175
0x18001116e  call    cs:__imp_BrBufferFree
0x180011174  nop
0x180011175  lea     rcx, [rsp+0E8h+arg_10]; this
0x18001117d  call    ??1BrokerLock@TimeBroker@Broker@@QEAA@XZ; Broker::TimeBroker::BrokerLock::~BrokerLock(void)
0x180011182  nop
0x180011183  jmp     short loc_18001118D
0x180011185  mov     rdi, [rsp+0E8h+arg_8]
0x18001118d  mov     edx, 2Fh ; '/'
0x180011192  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180011199  mov     rcx, rdi
0x18001119c  call    WPP_SF_
0x1800111a1  add     rsp, 0C8h
0x1800111a8  pop     r15
0x1800111aa  pop     r14
0x1800111ac  pop     rdi
0x1800111ad  pop     rsi
0x1800111ae  retn
```
