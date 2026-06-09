# Broker::TimeBroker::OnDisableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)

- ea: `0x18000f6f0`
- end: `0x18000fa06`
- name: `?OnDisableEvent@TimeBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z`
- size: `790`
- prototype: `__int64 __fastcall(__int16, __int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002400`
- `0x180003800`
- `0x180003840`
- `0x180005b90`
- `0x1800074c0`
- `0x180009670`
- `0x18000c500`
- `0x18000d034`
- `0x18000f6f0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::OnDisableEvent(__int16 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  _QWORD *v8; // rcx
  Broker::TimeBroker *v9; // rdi
  unsigned int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rbx
  volatile signed __int32 *v15; // rsi
  int *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  volatile signed __int32 *v20; // rsi
  int *v22; // [rsp+50h] [rbp-78h] BYREF
  int v23; // [rsp+58h] [rbp-70h] BYREF
  int v24; // [rsp+5Ch] [rbp-6Ch] BYREF
  _BYTE v25[16]; // [rsp+60h] [rbp-68h] BYREF
  __int128 v26; // [rsp+70h] [rbp-58h] BYREF
  int *v27; // [rsp+80h] [rbp-48h] BYREF
  __int128 v28; // [rsp+90h] [rbp-38h]
  __int128 v29; // [rsp+A0h] [rbp-28h]
  int v30; // [rsp+D8h] [rbp+10h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( *(&Broker::TimeBroker::Instance + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1) + 2);
    v8 = WPP_GLOBAL_Control;
  }
  v29 = *(_OWORD *)&Broker::TimeBroker::Instance;
  if ( a2 && a3 && a4 )
  {
    v9 = Broker::TimeBroker::Instance;
    if ( Broker::TimeBroker::Instance )
    {
      if ( *((_QWORD *)Broker::TimeBroker::Instance + 24) == a2 )
      {
        try
        {
          Broker::TimeBroker::BrokerLock::BrokerLock((Broker::TimeBroker::BrokerLock *)v25, 0);
          v13 = a4[1];
          if ( v13 )
            _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
          v14 = *a4;
          *(_QWORD *)&v28 = v14;
          v15 = (volatile signed __int32 *)a4[1];
          *((_QWORD *)&v28 + 1) = v15;
          Broker::TimeEvent::OnDisable((Broker::TimeEvent *)v14, v11, v12);
          v26 = 0;
          if ( v15 )
            _InterlockedIncrement(v15 + 2);
          v26 = v28;
          Broker::TimeBroker::RemoveFromTimerWheel(v9);
          if ( !*(_DWORD *)(v14 + 72) && *(_QWORD *)(v14 + 48) != 25920000000000LL )
          {
            v16 = *(int **)(v14 + 32);
            v22 = v16;
            if ( (unsigned int)dword_180026058 > 5
              && (qword_180026068 & 0x400000000000LL) != 0
              && (qword_180026070 & 0x400000000000LL) == qword_180026070 )
            {
              LOWORD(v30) = a1;
              v23 = (unsigned __int8)Broker::TimeEvent::GetOnLockScreen((Broker::TimeEvent *)v14);
              v24 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v14 + 48LL))(v14);
              v27 = v22;
              v22 = *(int **)(a3 + 24);
              *(_QWORD *)&v26 = a3;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(
                v17,
                (unsigned __int8 *)&dword_1800208FC,
                v18,
                v19,
                (__int64 *)&v26,
                &v22,
                (__int64)&v27,
                (__int64)&v24,
                (__int64)&v23,
                (__int64)&v30);
            }
          }
          v10 = 0;
          if ( v15 )
          {
            if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
              if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
            }
          }
          Broker::TimeBroker::BrokerLock::~BrokerLock((Broker::TimeBroker::BrokerLock *)v25);
          v8 = WPP_GLOBAL_Control;
        }
        catch ( ... )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
          v30 = 1359;
          v10 = 1359;
          v8 = WPP_GLOBAL_Control;
        }
      }
      else
      {
        v10 = 5;
      }
    }
    else
    {
      v10 = 21;
    }
  }
  else
  {
    v10 = 87;
  }
  if ( (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 4u )
    WPP_SF_d(v8[2], 110, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v10);
  v20 = (volatile signed __int32 *)*((_QWORD *)&v29 + 1);
  if ( *((_QWORD *)&v29 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v29 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18000f6f0  mov     [rsp+arg_0], rbx
0x18000f6f5  mov     [rsp+arg_10], rsi
0x18000f6fa  push    rdi
0x18000f6fb  push    r14
0x18000f6fd  push    r15
0x18000f6ff  sub     rsp, 0B0h
0x18000f706  mov     rsi, r9
0x18000f709  mov     r14, r8
0x18000f70c  mov     rbx, rdx
0x18000f70f  mov     r15d, ecx
0x18000f712  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f719  test    byte ptr [rcx+1Ch], 1
0x18000f71d  jz      short loc_18000F741
0x18000f71f  cmp     byte ptr [rcx+19h], 4
0x18000f723  jb      short loc_18000F741
0x18000f725  mov     edx, 6Ch ; 'l'
0x18000f72a  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18000f731  mov     rcx, [rcx+10h]
0x18000f735  call    WPP_SF_
0x18000f73a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f741  mov     rax, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000f748  test    rax, rax
0x18000f74b  jz      short loc_18000F758
0x18000f74d  lock inc dword ptr [rax+8]
0x18000f751  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f758  movups  xmm0, cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000f75f  movups  [rsp+0C8h+var_28], xmm0
0x18000f767  test    rbx, rbx
0x18000f76a  jz      loc_18000F97C
0x18000f770  test    r14, r14
0x18000f773  jz      loc_18000F97C
0x18000f779  test    rsi, rsi
0x18000f77c  jz      loc_18000F97C
0x18000f782  movq    rdi, xmm0
0x18000f787  test    rdi, rdi
0x18000f78a  jnz     short loc_18000F796
0x18000f78c  mov     edi, 15h
0x18000f791  jmp     loc_18000F981
0x18000f796  cmp     [rdi+0C0h], rbx
0x18000f79d  jz      short loc_18000F7A9
0x18000f79f  mov     edi, 5
0x18000f7a4  jmp     loc_18000F981
0x18000f7a9  xor     edx, edx; int
0x18000f7ab  lea     rcx, [rsp+0C8h+var_68]; this
0x18000f7b0  call    ??0BrokerLock@TimeBroker@Broker@@QEAA@H@Z; Broker::TimeBroker::BrokerLock::BrokerLock(int)
0x18000f7b5  nop
0x18000f7b6  mov     rax, [rsi+8]
0x18000f7ba  test    rax, rax
0x18000f7bd  jz      short loc_18000F7C3
0x18000f7bf  lock inc dword ptr [rax+8]
0x18000f7c3  mov     rbx, [rsi]
0x18000f7c6  mov     qword ptr [rsp+0C8h+var_38], rbx
0x18000f7ce  mov     rsi, [rsi+8]
0x18000f7d2  mov     qword ptr [rsp+0C8h+var_38+8], rsi
0x18000f7da  mov     rcx, rbx; this
0x18000f7dd  call    ?OnDisable@TimeEvent@Broker@@QEAAXXZ; Broker::TimeEvent::OnDisable(void)
0x18000f7e2  xorps   xmm0, xmm0
0x18000f7e5  movdqa  [rsp+0C8h+var_58], xmm0
0x18000f7eb  test    rsi, rsi
0x18000f7ee  jz      short loc_18000F7F4
0x18000f7f0  lock inc dword ptr [rsi+8]
0x18000f7f4  movaps  xmm0, [rsp+0C8h+var_38]
0x18000f7fc  movdqa  [rsp+0C8h+var_58], xmm0
0x18000f802  lea     rdx, [rsp+0C8h+var_58]
0x18000f807  mov     rcx, rdi; this
0x18000f80a  call    ?RemoveFromTimerWheel@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z; Broker::TimeBroker::RemoveFromTimerWheel(std::shared_ptr<Broker::TimeEvent>)
0x18000f80f  cmp     dword ptr [rbx+48h], 0
0x18000f813  jnz     loc_18000F916
0x18000f819  mov     rax, 1792F8648000h
0x18000f823  cmp     [rbx+30h], rax
0x18000f827  jz      loc_18000F916
0x18000f82d  mov     rax, [rbx+20h]
0x18000f831  mov     rcx, rax
0x18000f834  shr     rcx, 20h
0x18000f838  mov     dword ptr [rsp+0C8h+var_78+4], ecx
0x18000f83c  mov     dword ptr [rsp+0C8h+var_78], eax
0x18000f840  mov     eax, cs:dword_180026058
0x18000f846  cmp     eax, 5
0x18000f849  jbe     loc_18000F916
0x18000f84f  mov     rcx, cs:qword_180026070
0x18000f856  mov     rax, cs:qword_180026068
0x18000f85d  mov     rdx, 400000000000h
0x18000f867  test    rdx, rax
0x18000f86a  jz      loc_18000F916
0x18000f870  mov     rax, rcx
0x18000f873  and     rax, rdx
0x18000f876  cmp     rax, rcx
0x18000f879  jnz     loc_18000F916
0x18000f87f  mov     word ptr [rsp+0C8h+arg_8], r15w
0x18000f888  mov     rcx, rbx; this
0x18000f88b  call    ?GetOnLockScreen@TimeEvent@Broker@@QEAA_NXZ; Broker::TimeEvent::GetOnLockScreen(void)
0x18000f890  movzx   eax, al
0x18000f893  mov     [rsp+0C8h+var_70], eax
0x18000f897  mov     rax, [rbx]
0x18000f89a  mov     rcx, rbx
0x18000f89d  mov     rax, [rax+30h]
0x18000f8a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8a6  movzx   eax, al
0x18000f8a9  mov     [rsp+0C8h+var_6C], eax
0x18000f8ad  mov     rax, [rsp+0C8h+var_78]
0x18000f8b2  mov     [rsp+0C8h+var_48], rax
0x18000f8ba  mov     rax, [r14+18h]
0x18000f8be  mov     [rsp+0C8h+var_78], rax
0x18000f8c3  mov     qword ptr [rsp+0C8h+var_58], r14
0x18000f8c8  lea     rax, [rsp+0C8h+arg_8]
0x18000f8d0  mov     [rsp+0C8h+var_80], rax
0x18000f8d5  lea     rax, [rsp+0C8h+var_70]
0x18000f8da  mov     [rsp+0C8h+var_88], rax
0x18000f8df  lea     rax, [rsp+0C8h+var_6C]
0x18000f8e4  mov     [rsp+0C8h+var_90], rax
0x18000f8e9  lea     rax, [rsp+0C8h+var_48]
0x18000f8f1  mov     [rsp+0C8h+var_98], rax
0x18000f8f6  lea     rax, [rsp+0C8h+var_78]
0x18000f8fb  mov     [rsp+0C8h+var_A0], rax
0x18000f900  lea     rax, [rsp+0C8h+var_58]
0x18000f905  mov     [rsp+0C8h+var_A8], rax
0x18000f90a  lea     rdx, dword_1800208FC
0x18000f911  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &)
0x18000f916  xor     edi, edi
0x18000f918  mov     ebx, 0FFFFFFFFh
0x18000f91d  test    rsi, rsi
0x18000f920  jz      short loc_18000F958
0x18000f922  mov     eax, ebx
0x18000f924  lock xadd [rsi+8], eax
0x18000f929  cmp     eax, 1
0x18000f92c  jnz     short loc_18000F958
0x18000f92e  mov     rax, [rsi]
0x18000f931  mov     rcx, rsi
0x18000f934  mov     rax, [rax]
0x18000f937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f93c  mov     eax, ebx
0x18000f93e  lock xadd [rsi+0Ch], eax
0x18000f943  cmp     eax, 1
0x18000f946  jnz     short loc_18000F958
0x18000f948  mov     rax, [rsi]
0x18000f94b  mov     rcx, rsi
0x18000f94e  mov     rax, [rax+8]
0x18000f952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f957  nop
0x18000f958  lea     rcx, [rsp+0C8h+var_68]; this
0x18000f95d  call    ??1BrokerLock@TimeBroker@Broker@@QEAA@XZ; Broker::TimeBroker::BrokerLock::~BrokerLock(void)
0x18000f962  nop
0x18000f963  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f96a  jmp     short loc_18000F986
0x18000f96c  mov     edi, [rsp+0C8h+arg_8]
0x18000f973  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f97a  jmp     short loc_18000F981
0x18000f97c  mov     edi, 57h ; 'W'
0x18000f981  mov     ebx, 0FFFFFFFFh
0x18000f986  test    byte ptr [rcx+1Ch], 1
0x18000f98a  jz      short loc_18000F9AB
0x18000f98c  cmp     byte ptr [rcx+19h], 4
0x18000f990  jb      short loc_18000F9AB
0x18000f992  mov     edx, 6Eh ; 'n'
0x18000f997  mov     r9d, edi
0x18000f99a  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18000f9a1  mov     rcx, [rcx+10h]
0x18000f9a5  call    WPP_SF_d
0x18000f9aa  nop
0x18000f9ab  mov     rsi, qword ptr [rsp+0C8h+var_28+8]
0x18000f9b3  test    rsi, rsi
0x18000f9b6  jz      short loc_18000F9EB
0x18000f9b8  mov     eax, ebx
0x18000f9ba  lock xadd [rsi+8], eax
0x18000f9bf  cmp     eax, 1
0x18000f9c2  jnz     short loc_18000F9EB
0x18000f9c4  mov     rax, [rsi]
0x18000f9c7  mov     rcx, rsi
0x18000f9ca  mov     rax, [rax]
0x18000f9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9d2  lock xadd [rsi+0Ch], ebx
0x18000f9d7  cmp     ebx, 1
0x18000f9da  jnz     short loc_18000F9EB
0x18000f9dc  mov     rdx, [rsi]
0x18000f9df  mov     rcx, rsi
0x18000f9e2  mov     rax, [rdx+8]
0x18000f9e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9eb  mov     eax, edi
0x18000f9ed  lea     r11, [rsp+0C8h+var_18]
0x18000f9f5  mov     rbx, [r11+20h]
0x18000f9f9  mov     rsi, [r11+30h]
0x18000f9fd  mov     rsp, r11
0x18000fa00  pop     r15
0x18000fa02  pop     r14
0x18000fa04  pop     rdi
0x18000fa05  retn
```
