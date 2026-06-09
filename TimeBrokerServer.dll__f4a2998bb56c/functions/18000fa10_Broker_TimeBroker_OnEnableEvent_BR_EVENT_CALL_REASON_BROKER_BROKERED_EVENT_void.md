# Broker::TimeBroker::OnEnableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)

- ea: `0x18000fa10`
- end: `0x18000fe63`
- name: `?OnEnableEvent@TimeBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z`
- size: `1107`
- prototype: `__int64 __fastcall(__int16, __int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180003800`
- `0x180003840`
- `0x1800061e0`
- `0x180009710`
- `0x180009f10`
- `0x18000c500`
- `0x18000d034`
- `0x18000fa10`
- `0x180012dd0`
- `0x180014098`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000faa8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000faa8`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::OnEnableEvent(__int16 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  volatile signed __int32 *v8; // rax
  Broker::TimeBroker *v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // r9d
  unsigned int v13; // edi
  __int64 v14; // rax
  __int64 v15; // rbx
  volatile signed __int32 *v16; // rsi
  __int64 v17; // rdi
  _QWORD *v18; // rcx
  __int64 v19; // rax
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  Broker::TimeBroker *v23; // rcx
  volatile signed __int32 *v24; // rsi
  __int64 v26; // rax
  __int64 v27; // r8
  __int64 v28; // rax
  __int64 v29; // r8
  ULONG v30; // [rsp+50h] [rbp-E8h] BYREF
  int v31; // [rsp+58h] [rbp-E0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-D8h] BYREF
  __int64 v33; // [rsp+68h] [rbp-D0h] BYREF
  __int128 v34; // [rsp+70h] [rbp-C8h] BYREF
  Broker::TimeBroker *v35; // [rsp+80h] [rbp-B8h]
  volatile signed __int32 *v36; // [rsp+88h] [rbp-B0h]
  __int64 v37; // [rsp+90h] [rbp-A8h] BYREF
  __int128 v38; // [rsp+A0h] [rbp-98h]
  Broker::BILayer::Failure *v39; // [rsp+B0h] [rbp-88h] BYREF
  Broker::Win32Error *v40; // [rsp+B8h] [rbp-80h] BYREF
  Broker::EventInternalError *v41; // [rsp+C0h] [rbp-78h] BYREF
  Broker::BrokerCommonException *v42; // [rsp+C8h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v43; // [rsp+D0h] [rbp-68h] BYREF
  __int64 v44; // [rsp+E0h] [rbp-58h]
  __int64 v45; // [rsp+E8h] [rbp-50h]
  ULONG *v46; // [rsp+F0h] [rbp-48h]
  __int64 v47; // [rsp+F8h] [rbp-40h]
  int *v48; // [rsp+100h] [rbp-38h]
  __int64 v49; // [rsp+108h] [rbp-30h]

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
  v8 = (volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1);
  if ( *(&Broker::TimeBroker::Instance + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1) + 2);
    v8 = (volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1);
  }
  v9 = Broker::TimeBroker::Instance;
  v35 = Broker::TimeBroker::Instance;
  v36 = v8;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *((struct _FILETIME *)v9 + 25) = SystemTimeAsFileTime;
  if ( a2 && a3 && a4 )
  {
    if ( v9 )
    {
      if ( *((_QWORD *)v9 + 24) == a2 )
      {
        v14 = a4[1];
        if ( v14 )
          _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
        v15 = *a4;
        *(_QWORD *)&v38 = *a4;
        v16 = (volatile signed __int32 *)a4[1];
        *((_QWORD *)&v38 + 1) = v16;
        v17 = *((_QWORD *)v9 + 25);
        v18 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v11, *(_QWORD *)(v15 + 248));
          v18 = WPP_GLOBAL_Control;
        }
        try
        {
          if ( !*(_DWORD *)(v15 + 88) )
          {
            if ( (*((_BYTE *)v18 + 28) & 0x40) != 0 && *((_BYTE *)v18 + 25) >= 4u )
              WPP_SF__guid_ll(v18[2], v10, v11, *(_QWORD *)(v15 + 248), 0, 4);
            LOBYTE(SystemTimeAsFileTime.dwLowDateTime) = Microsoft_Windows_TimeBrokerEnableBits & 1;
            if ( (Microsoft_Windows_TimeBrokerEnableBits & 1) != 0 )
            {
              v31 = 4;
              v30 = *(_DWORD *)(v15 + 88);
              v44 = *(_QWORD *)(v15 + 248);
              v45 = 16;
              v46 = &v30;
              v47 = 4;
              v48 = &v31;
              v49 = 4;
              McGenEventWrite_EventWriteTransfer((int)v18, (int)&EventStateChange, v11, v12, &v43);
            }
            *(_DWORD *)(v15 + 88) = 4;
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 72LL))(v15, v17);
          }
          v34 = 0;
          if ( v16 )
            _InterlockedIncrement(v16 + 2);
          v34 = v38;
          Broker::TimeBroker::InsertIntoTimerWheelIfNecessary(v35, &v34);
          if ( !*(_DWORD *)(v15 + 72) && *(_QWORD *)(v15 + 48) != 25920000000000LL )
          {
            v19 = *(_QWORD *)(v15 + 32);
            v33 = v19;
            if ( (unsigned int)dword_180026058 > 5
              && (qword_180026068 & 0x400000000000LL) != 0
              && (qword_180026070 & 0x400000000000LL) == qword_180026070 )
            {
              LOWORD(v30) = a1;
              v31 = Broker::TimeEvent::GetOnLockScreen((Broker::TimeEvent *)v15);
              SystemTimeAsFileTime.dwLowDateTime = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v15 + 48LL))(v15);
              v37 = v33;
              v33 = *(_QWORD *)(a3 + 24);
              *(_QWORD *)&v34 = a3;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(
                v20,
                (unsigned int)byte_180020705,
                v21,
                v22,
                (__int64)&v34,
                (__int64)&v33,
                (__int64)&v37,
                (__int64)&SystemTimeAsFileTime,
                (__int64)&v31,
                (__int64)&v30);
            }
          }
          v13 = 0;
          if ( v16 )
          {
            if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
              if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
            }
          }
        }
        catch ( std::bad_alloc )
        {
          v30 = 14;
          v13 = 14;
        }
        catch ( Broker::NotFound )
        {
          v30 = 2;
          v13 = 2;
        }
        catch ( Broker::AccessDenied )
        {
          v30 = 5;
          v13 = 5;
        }
        catch ( Broker::BILayer::Failure *v39 )
        {
          v30 = RtlNtStatusToDosError(*((_DWORD *)v39 + 8));
          v13 = v30;
        }
        catch ( Broker::Win32Error *v40 )
        {
          v30 = *((_DWORD *)v40 + 8);
          v13 = v30;
        }
        catch ( Broker::EventInternalError *v41 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v26 = (*(__int64 (__fastcall **)(Broker::EventInternalError *))(*(_QWORD *)v41 + 8LL))(v41);
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, v27, v26);
          }
          v30 = 1359;
          v13 = 1359;
        }
        catch ( Broker::BrokerCommonException *v42 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v28 = (*(__int64 (__fastcall **)(Broker::BrokerCommonException *))(*(_QWORD *)v42 + 8LL))(v42);
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, v29, v28);
          }
          v30 = 1359;
          v13 = 1359;
        }
        catch ( ... )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
          v30 = 1359;
          v13 = 1359;
        }
      }
      else
      {
        v13 = 5;
      }
    }
    else
    {
      v13 = 21;
    }
  }
  else
  {
    v13 = 87;
  }
  v23 = v35;
  *((_QWORD *)v35 + 26) = *((_QWORD *)v35 + 25);
  *((_QWORD *)v23 + 25) = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v13);
  v24 = v36;
  if ( v36 )
  {
    if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
      if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x18000fa10  mov     [rsp+arg_0], rbx
0x18000fa15  mov     [rsp+arg_8], rsi
0x18000fa1a  push    rdi
0x18000fa1b  push    r14
0x18000fa1d  push    r15
0x18000fa1f  sub     rsp, 120h
0x18000fa26  mov     rax, cs:__security_cookie
0x18000fa2d  xor     rax, rsp
0x18000fa30  mov     [rsp+138h+var_28], rax
0x18000fa38  mov     rsi, r9
0x18000fa3b  mov     r14, r8
0x18000fa3e  mov     rbx, rdx
0x18000fa41  mov     r15d, ecx
0x18000fa44  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa4b  test    byte ptr [rcx+1Ch], 1
0x18000fa4f  jz      short loc_18000FA6C
0x18000fa51  cmp     byte ptr [rcx+19h], 4
0x18000fa55  jb      short loc_18000FA6C
0x18000fa57  mov     edx, 6Fh ; 'o'
0x18000fa5c  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18000fa63  mov     rcx, [rcx+10h]
0x18000fa67  call    WPP_SF_
0x18000fa6c  mov     rax, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000fa73  test    rax, rax
0x18000fa76  jz      short loc_18000FA83
0x18000fa78  lock inc dword ptr [rax+8]
0x18000fa7c  mov     rax, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000fa83  mov     rdi, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000fa8a  mov     [rsp+138h+var_B8], rdi
0x18000fa92  mov     [rsp+138h+var_B0], rax
0x18000fa9a  mov     qword ptr [rsp+138h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000faa3  lea     rcx, [rsp+138h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000faa8  call    cs:__imp_GetSystemTimeAsFileTime
0x18000faae  mov     rax, qword ptr [rsp+138h+SystemTimeAsFileTime.dwLowDateTime]
0x18000fab3  mov     [rdi+0C8h], rax
0x18000faba  test    rbx, rbx
0x18000fabd  jz      loc_18000FDA1
0x18000fac3  test    r14, r14
0x18000fac6  jz      loc_18000FDA1
0x18000facc  test    rsi, rsi
0x18000facf  jz      loc_18000FDA1
0x18000fad5  test    rdi, rdi
0x18000fad8  jnz     short loc_18000FAE4
0x18000fada  mov     edi, 15h
0x18000fadf  jmp     loc_18000FDA6
0x18000fae4  cmp     [rdi+0C0h], rbx
0x18000faeb  jz      short loc_18000FAF7
0x18000faed  mov     edi, 5
0x18000faf2  jmp     loc_18000FDA6
0x18000faf7  mov     rax, [rsi+8]
0x18000fafb  test    rax, rax
0x18000fafe  jz      short loc_18000FB04
0x18000fb00  lock inc dword ptr [rax+8]
0x18000fb04  mov     rbx, [rsi]
0x18000fb07  mov     qword ptr [rsp+138h+var_98], rbx
0x18000fb0f  mov     rsi, [rsi+8]
0x18000fb13  mov     qword ptr [rsp+138h+var_98+8], rsi
0x18000fb1b  mov     rdi, [rdi+0C8h]
0x18000fb22  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb29  test    byte ptr [rcx+1Ch], 40h
0x18000fb2d  jz      short loc_18000FB51
0x18000fb2f  cmp     byte ptr [rcx+19h], 5
0x18000fb33  jb      short loc_18000FB51
0x18000fb35  mov     edx, 0Ch
0x18000fb3a  mov     r9, [rbx+0F8h]
0x18000fb41  mov     rcx, [rcx+10h]
0x18000fb45  call    WPP_SF__guid_
0x18000fb4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb51  cmp     dword ptr [rbx+58h], 0
0x18000fb55  jnz     loc_18000FC24
0x18000fb5b  test    byte ptr [rcx+1Ch], 40h
0x18000fb5f  jz      short loc_18000FB87
0x18000fb61  cmp     byte ptr [rcx+19h], 4
0x18000fb65  jb      short loc_18000FB87
0x18000fb67  mov     dword ptr [rsp+138h+var_110], 4
0x18000fb6f  mov     dword ptr [rsp+138h+var_118], 0
0x18000fb77  mov     r9, [rbx+0F8h]
0x18000fb7e  mov     rcx, [rcx+10h]
0x18000fb82  call    WPP_SF__guid_ll
0x18000fb87  movzx   eax, cs:Microsoft_Windows_TimeBrokerEnableBits
0x18000fb8e  and     al, 1
0x18000fb90  mov     byte ptr [rsp+138h+SystemTimeAsFileTime.dwLowDateTime], al
0x18000fb94  jz      short loc_18000FC0B
0x18000fb96  mov     [rsp+138h+var_E0], 4
0x18000fb9e  mov     eax, [rbx+58h]
0x18000fba1  mov     [rsp+138h+var_E8], eax
0x18000fba5  mov     rax, [rbx+0F8h]
0x18000fbac  mov     [rsp+138h+var_58], rax
0x18000fbb4  mov     [rsp+138h+var_50], 10h
0x18000fbc0  lea     rax, [rsp+138h+var_E8]
0x18000fbc5  mov     [rsp+138h+var_48], rax
0x18000fbcd  mov     [rsp+138h+var_40], 4
0x18000fbd9  lea     rax, [rsp+138h+var_E0]
0x18000fbde  mov     [rsp+138h+var_38], rax
0x18000fbe6  mov     [rsp+138h+var_30], 4
0x18000fbf2  lea     rax, [rsp+138h+var_68]
0x18000fbfa  mov     [rsp+138h+var_118], rax; PEVENT_DATA_DESCRIPTOR
0x18000fbff  lea     rdx, EventStateChange; int
0x18000fc06  call    McGenEventWrite_EventWriteTransfer
0x18000fc0b  mov     dword ptr [rbx+58h], 4
0x18000fc12  mov     rax, [rbx]
0x18000fc15  mov     rdx, rdi
0x18000fc18  mov     rcx, rbx
0x18000fc1b  mov     rax, [rax+48h]
0x18000fc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc24  xorps   xmm0, xmm0
0x18000fc27  movdqa  [rsp+138h+var_C8], xmm0
0x18000fc2d  test    rsi, rsi
0x18000fc30  jz      short loc_18000FC36
0x18000fc32  lock inc dword ptr [rsi+8]
0x18000fc36  movaps  xmm0, [rsp+138h+var_98]
0x18000fc3e  movdqa  [rsp+138h+var_C8], xmm0
0x18000fc44  lea     rdx, [rsp+138h+var_C8]
0x18000fc49  mov     rcx, [rsp+138h+var_B8]
0x18000fc51  call    ?InsertIntoTimerWheelIfNecessary@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z; Broker::TimeBroker::InsertIntoTimerWheelIfNecessary(std::shared_ptr<Broker::TimeEvent>)
0x18000fc56  cmp     dword ptr [rbx+48h], 0
0x18000fc5a  jnz     loc_18000FD57
0x18000fc60  mov     rax, 1792F8648000h
0x18000fc6a  cmp     [rbx+30h], rax
0x18000fc6e  jz      loc_18000FD57
0x18000fc74  mov     rax, [rbx+20h]
0x18000fc78  mov     rcx, rax
0x18000fc7b  shr     rcx, 20h
0x18000fc7f  mov     dword ptr [rsp+138h+var_D0+4], ecx
0x18000fc83  mov     dword ptr [rsp+138h+var_D0], eax
0x18000fc87  mov     eax, cs:dword_180026058
0x18000fc8d  cmp     eax, 5
0x18000fc90  jbe     loc_18000FD57
0x18000fc96  mov     rcx, cs:qword_180026070
0x18000fc9d  mov     rax, cs:qword_180026068
0x18000fca4  mov     rdx, 400000000000h
0x18000fcae  test    rdx, rax
0x18000fcb1  jz      loc_18000FD57
0x18000fcb7  mov     rax, rcx
0x18000fcba  and     rax, rdx
0x18000fcbd  cmp     rax, rcx
0x18000fcc0  jnz     loc_18000FD57
0x18000fcc6  mov     word ptr [rsp+138h+var_E8], r15w
0x18000fccc  mov     rcx, rbx; this
0x18000fccf  call    ?GetOnLockScreen@TimeEvent@Broker@@QEAA_NXZ; Broker::TimeEvent::GetOnLockScreen(void)
0x18000fcd4  movzx   eax, al
0x18000fcd7  mov     [rsp+138h+var_E0], eax
0x18000fcdb  mov     rax, [rbx]
0x18000fcde  mov     rcx, rbx
0x18000fce1  mov     rax, [rax+30h]
0x18000fce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcea  movzx   eax, al
0x18000fced  mov     [rsp+138h+SystemTimeAsFileTime.dwLowDateTime], eax
0x18000fcf1  mov     rax, [rsp+138h+var_D0]
0x18000fcf6  mov     [rsp+138h+var_A8], rax
0x18000fcfe  mov     rax, [r14+18h]
0x18000fd02  mov     [rsp+138h+var_D0], rax
0x18000fd07  mov     qword ptr [rsp+138h+var_C8], r14
0x18000fd0c  lea     rax, [rsp+138h+var_E8]
0x18000fd11  mov     [rsp+138h+var_F0], rax
0x18000fd16  lea     rax, [rsp+138h+var_E0]
0x18000fd1b  mov     [rsp+138h+var_F8], rax
0x18000fd20  lea     rax, [rsp+138h+SystemTimeAsFileTime]
0x18000fd25  mov     [rsp+138h+var_100], rax
0x18000fd2a  lea     rax, [rsp+138h+var_A8]
0x18000fd32  mov     [rsp+138h+var_108], rax
0x18000fd37  lea     rax, [rsp+138h+var_D0]
0x18000fd3c  mov     [rsp+138h+var_110], rax
0x18000fd41  lea     rax, [rsp+138h+var_C8]
0x18000fd46  mov     [rsp+138h+var_118], rax
0x18000fd4b  lea     rdx, byte_180020705
0x18000fd52  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &)
0x18000fd57  xor     edi, edi
0x18000fd59  mov     ebx, 0FFFFFFFFh
0x18000fd5e  test    rsi, rsi
0x18000fd61  jz      short loc_18000FD99
0x18000fd63  mov     eax, ebx
0x18000fd65  lock xadd [rsi+8], eax
0x18000fd6a  cmp     eax, 1
0x18000fd6d  jnz     short loc_18000FD99
0x18000fd6f  mov     rax, [rsi]
0x18000fd72  mov     rcx, rsi
0x18000fd75  mov     rax, [rax]
0x18000fd78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd7d  mov     eax, ebx
0x18000fd7f  lock xadd [rsi+0Ch], eax
0x18000fd84  cmp     eax, 1
0x18000fd87  jnz     short loc_18000FD99
0x18000fd89  mov     rax, [rsi]
0x18000fd8c  mov     rcx, rsi
0x18000fd8f  mov     rax, [rax+8]
0x18000fd93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd98  nop
0x18000fd99  jmp     short loc_18000FDAB
0x18000fd9b  mov     edi, [rsp+138h+var_E8]
0x18000fd9f  jmp     short loc_18000FDA6
0x18000fda1  mov     edi, 57h ; 'W'
0x18000fda6  mov     ebx, 0FFFFFFFFh
0x18000fdab  mov     rcx, [rsp+138h+var_B8]
0x18000fdb3  mov     rax, [rcx+0C8h]
0x18000fdba  mov     [rcx+0D0h], rax
0x18000fdc1  mov     qword ptr [rcx+0C8h], 0
0x18000fdcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fdd3  test    byte ptr [rcx+1Ch], 1
0x18000fdd7  jz      short loc_18000FDF8
0x18000fdd9  cmp     byte ptr [rcx+19h], 4
0x18000fddd  jb      short loc_18000FDF8
0x18000fddf  mov     edx, 73h ; 's'
0x18000fde4  mov     r9d, edi
0x18000fde7  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18000fdee  mov     rcx, [rcx+10h]
0x18000fdf2  call    WPP_SF_d
0x18000fdf7  nop
0x18000fdf8  mov     rsi, [rsp+138h+var_B0]
0x18000fe00  test    rsi, rsi
0x18000fe03  jz      short loc_18000FE38
0x18000fe05  mov     eax, ebx
0x18000fe07  lock xadd [rsi+8], eax
0x18000fe0c  cmp     eax, 1
0x18000fe0f  jnz     short loc_18000FE38
0x18000fe11  mov     rax, [rsi]
0x18000fe14  mov     rcx, rsi
0x18000fe17  mov     rax, [rax]
0x18000fe1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe1f  lock xadd [rsi+0Ch], ebx
0x18000fe24  cmp     ebx, 1
0x18000fe27  jnz     short loc_18000FE38
0x18000fe29  mov     rdx, [rsi]
0x18000fe2c  mov     rcx, rsi
0x18000fe2f  mov     rax, [rdx+8]
0x18000fe33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe38  mov     eax, edi
0x18000fe3a  mov     rcx, [rsp+138h+var_28]
0x18000fe42  xor     rcx, rsp; StackCookie
0x18000fe45  call    __security_check_cookie
0x18000fe4a  lea     r11, [rsp+138h+var_18]
0x18000fe52  mov     rbx, [r11+20h]
0x18000fe56  mov     rsi, [r11+28h]
0x18000fe5a  mov     rsp, r11
0x18000fe5d  pop     r15
0x18000fe5f  pop     r14
0x18000fe61  pop     rdi
0x18000fe62  retn
```
