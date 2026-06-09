# Broker::TimeBroker::SimulateLockScreenChange(Broker::ApplicationIdentity const &,bool)

- ea: `0x180015f3c`
- end: `0x180016188`
- name: `?SimulateLockScreenChange@TimeBroker@Broker@@QEAAXAEBUApplicationIdentity@2@_N@Z`
- size: `588`
- prototype: `void __fastcall(Broker::TimeBroker *this, const struct Broker::ApplicationIdentity *, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800147b0`

## callees

- `0x180002400`
- `0x180003800`
- `0x180003840`
- `0x180004dd4`
- `0x180005b30`
- `0x180005b90`
- `0x180013978`
- `0x180015f3c`

## import_xrefs

- `BrokerLib!BrBufferFree` at `0x180016125`
- `BrokerLib!BrBufferFree` at `0x180016125`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x1800160c8`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x1800160c8`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x180015ffc`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x180015ffc`

## pseudocode

```c
void __fastcall Broker::TimeBroker::SimulateLockScreenChange(
        Broker::TimeBroker *this,
        const struct Broker::ApplicationIdentity *a2,
        char a3)
{
  _QWORD *v6; // rcx
  _QWORD *v7; // r8
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int64 i; // rbx
  __int64 v11; // [rsp+30h] [rbp-98h] BYREF
  _QWORD *v12; // [rsp+38h] [rbp-90h] BYREF
  std::_Ref_count_base *v13[2]; // [rsp+40h] [rbp-88h] BYREF
  void **v14; // [rsp+50h] [rbp-78h] BYREF
  __int128 v15; // [rsp+58h] [rbp-70h]
  int v16; // [rsp+68h] [rbp-60h]
  void **pExceptionObject; // [rsp+70h] [rbp-58h] BYREF
  __int128 v18; // [rsp+78h] [rbp-50h]
  int v19; // [rsp+88h] [rbp-40h]
  unsigned int v20; // [rsp+90h] [rbp-38h]
  void **v21; // [rsp+98h] [rbp-30h] BYREF
  _DWORD v22[8]; // [rsp+A0h] [rbp-28h] BYREF
  unsigned int v23; // [rsp+D0h] [rbp+8h] BYREF
  char v24; // [rsp+E8h] [rbp+20h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 24) )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v12 = 0;
      v23 = 0;
      v11 = 0;
      *(_OWORD *)v13 = 0;
      Broker::TimeBroker::BrokerLock::BrokerLock((Broker::TimeBroker::BrokerLock *)&v24, 0);
      v7 = (_QWORD *)((char *)a2 + 56);
      if ( *((_QWORD *)a2 + 10) > 7u )
        v7 = (_QWORD *)*v7;
      v8 = BrQueryBrokeredEvents2(*((_QWORD *)this + 24), 0, v7, 0xFFFFFFFFLL, &v23, &v11);
      v9 = v8;
      if ( v8 )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v8);
        v18 = 0;
        v19 = 1;
        pExceptionObject = &Broker::Win32Error::`vftable';
        v20 = v9;
        throw (Broker::Win32Error *)&pExceptionObject;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v23);
      for ( i = 0; (unsigned int)i < v23; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)BrGetBrokeredEventInfo2(*((_QWORD *)this + 24), *(_QWORD *)(v11 + 8 * i), 0, 0, &v12) )
        {
          v15 = 0;
          v16 = 3;
          v14 = &Broker::NotFound::`vftable';
          throw (Broker::NotFound *)&v14;
        }
        std::shared_ptr<Broker::TimeEvent>::operator=(v13, v12);
        *((_BYTE *)v13[0] + 93) = a3;
      }
      if ( v11 )
        BrBufferFree();
      Broker::TimeBroker::BrokerLock::~BrokerLock((Broker::TimeBroker::BrokerLock *)&v24);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &Broker::Win32Error `RTTI Type Descriptor', (Broker::Win32Error *)&v21) )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v22[6]);
        if ( v11 )
          BrBufferFree();
        v21 = &std::exception::`vftable';
        o___std_exception_destroy_0(v22);
        __eh34_try_continuation(0, &Broker::Win32Error `RTTI Type Descriptor', &loc_18001613C);
      }
    }
    if ( v13[1] )
      std::_Ref_count_base::_Decref(v13[1]);
    v6 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_(v6[2], 120, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
}

```

## disassembly

```asm
0x180015f3c  mov     [rsp+arg_8], rbx
0x180015f41  mov     [rsp+arg_10], rsi
0x180015f46  push    rdi
0x180015f47  sub     rsp, 0C0h
0x180015f4e  mov     sil, r8b
0x180015f51  mov     rbx, rdx
0x180015f54  mov     rdi, rcx
0x180015f57  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f5e  test    byte ptr [rcx+1Ch], 1
0x180015f62  jz      short loc_180015F86
0x180015f64  cmp     byte ptr [rcx+19h], 4
0x180015f68  jb      short loc_180015F86
0x180015f6a  mov     edx, 74h ; 't'
0x180015f6f  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180015f76  mov     rcx, [rcx+10h]
0x180015f7a  call    WPP_SF_
0x180015f7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f86  cmp     qword ptr [rdi+0C0h], 0
0x180015f8e  jz      loc_180016152
0x180015f94  mov     [rsp+0C8h+var_90], 0
0x180015f9d  mov     [rsp+0C8h+arg_0], 0
0x180015fa8  mov     [rsp+0C8h+var_98], 0
0x180015fb1  xorps   xmm0, xmm0
0x180015fb4  movdqu  xmmword ptr [rsp+0C8h+var_88], xmm0
0x180015fba  xor     edx, edx; int
0x180015fbc  lea     rcx, [rsp+0C8h+arg_18]; this
0x180015fc4  call    ??0BrokerLock@TimeBroker@Broker@@QEAA@H@Z; Broker::TimeBroker::BrokerLock::BrokerLock(int)
0x180015fc9  nop
0x180015fca  lea     r8, [rbx+38h]
0x180015fce  cmp     qword ptr [r8+18h], 7
0x180015fd3  jbe     short loc_180015FD8
0x180015fd5  mov     r8, [r8]
0x180015fd8  lea     rax, [rsp+0C8h+var_98]
0x180015fdd  mov     [rsp+0C8h+var_A0], rax
0x180015fe2  lea     rax, [rsp+0C8h+arg_0]
0x180015fea  mov     [rsp+0C8h+var_A8], rax
0x180015fef  or      r9d, 0FFFFFFFFh
0x180015ff3  xor     edx, edx
0x180015ff5  mov     rcx, [rdi+0C0h]
0x180015ffc  call    cs:__imp_BrQueryBrokeredEvents2
0x180016002  mov     ebx, eax
0x180016004  test    eax, eax
0x180016006  jz      short loc_18001606D
0x180016008  mov     rcx, cs:WPP_GLOBAL_Control
0x18001600f  test    dword ptr [rcx+1Ch], 100h
0x180016016  jz      short loc_180016036
0x180016018  cmp     byte ptr [rcx+19h], 2
0x18001601c  jb      short loc_180016036
0x18001601e  mov     edx, 75h ; 'u'
0x180016023  mov     r9d, eax
0x180016026  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18001602d  mov     rcx, [rcx+10h]
0x180016031  call    WPP_SF_d
0x180016036  xorps   xmm0, xmm0
0x180016039  movups  [rsp+0C8h+var_50], xmm0
0x18001603e  mov     [rsp+0C8h+var_40], 1
0x180016049  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180016050  mov     [rsp+0C8h+pExceptionObject], rax
0x180016055  mov     [rsp+0C8h+var_38], ebx
0x18001605c  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180016063  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180016068  call    _CxxThrowException_0
0x18001606d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016074  test    byte ptr [rcx+1Ch], 1
0x180016078  jz      short loc_18001609D
0x18001607a  cmp     byte ptr [rcx+19h], 4
0x18001607e  jb      short loc_18001609D
0x180016080  mov     edx, 76h ; 'v'
0x180016085  mov     r9d, [rsp+0C8h+arg_0]
0x18001608d  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180016094  mov     rcx, [rcx+10h]
0x180016098  call    WPP_SF_d
0x18001609d  xor     ebx, ebx
0x18001609f  cmp     ebx, [rsp+0C8h+arg_0]
0x1800160a6  jnb     short loc_18001611B
0x1800160a8  lea     rcx, [rsp+0C8h+var_90]
0x1800160ad  mov     [rsp+0C8h+var_A8], rcx
0x1800160b2  xor     r9d, r9d
0x1800160b5  xor     r8d, r8d
0x1800160b8  mov     rdx, [rsp+0C8h+var_98]
0x1800160bd  mov     rdx, [rdx+rbx*8]
0x1800160c1  mov     rcx, [rdi+0C0h]
0x1800160c8  call    cs:__imp_BrGetBrokeredEventInfo2
0x1800160ce  test    eax, eax
0x1800160d0  jz      short loc_1800160FF
0x1800160d2  xorps   xmm0, xmm0
0x1800160d5  movups  [rsp+0C8h+var_70], xmm0
0x1800160da  mov     [rsp+0C8h+var_60], 3
0x1800160e2  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x1800160e9  mov     [rsp+0C8h+var_78], rax
0x1800160ee  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x1800160f5  lea     rcx, [rsp+0C8h+var_78]; pExceptionObject
0x1800160fa  call    _CxxThrowException_0
0x1800160ff  mov     rdx, [rsp+0C8h+var_90]
0x180016104  lea     rcx, [rsp+0C8h+var_88]
0x180016109  call    ??4?$shared_ptr@VTimeEvent@Broker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Broker::TimeEvent>::operator=(std::shared_ptr<Broker::TimeEvent> const &)
0x18001610e  mov     rax, [rsp+0C8h+var_88]
0x180016113  mov     [rax+5Dh], sil
0x180016117  inc     ebx
0x180016119  jmp     short loc_18001609F
0x18001611b  mov     rcx, [rsp+0C8h+var_98]
0x180016120  test    rcx, rcx
0x180016123  jz      short loc_18001612C
0x180016125  call    cs:__imp_BrBufferFree
0x18001612b  nop
0x18001612c  lea     rcx, [rsp+0C8h+arg_18]; this
0x180016134  call    ??1BrokerLock@TimeBroker@Broker@@QEAA@XZ; Broker::TimeBroker::BrokerLock::~BrokerLock(void)
0x180016139  nop
0x18001613a  jmp     short $+2
0x18001613c  mov     rcx, [rsp+0C8h+var_88+8]; this
0x180016141  test    rcx, rcx
0x180016144  jz      short loc_18001614B
0x180016146  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001614b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016152  test    byte ptr [rcx+1Ch], 1
0x180016156  jz      short loc_180016173
0x180016158  cmp     byte ptr [rcx+19h], 4
0x18001615c  jb      short loc_180016173
0x18001615e  mov     edx, 78h ; 'x'
0x180016163  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18001616a  mov     rcx, [rcx+10h]
0x18001616e  call    WPP_SF_
0x180016173  lea     r11, [rsp+0C8h+var_8]
0x18001617b  mov     rbx, [r11+18h]
0x18001617f  mov     rsi, [r11+20h]
0x180016183  mov     rsp, r11
0x180016186  pop     rdi
0x180016187  retn
```
