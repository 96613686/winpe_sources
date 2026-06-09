# ScheduledTileManager::Initialize(NotificationPlatform *)

- ea: `0x18007dbb8`
- end: `0x18007df19`
- name: `?Initialize@ScheduledTileManager@@QEAAJPEAVNotificationPlatform@@@Z`
- size: `865`
- prototype: `__int64 __fastcall(ScheduledTileManager *__hidden this, struct NotificationPlatform *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180035508`

## callees

- `0x180004e38`
- `0x180011618`
- `0x180020f48`
- `0x180024640`
- `0x1800299c0`
- `0x18002e5d0`
- `0x18002ee38`
- `0x1800317e4`
- `0x18003fe5c`
- `0x18007dbb8`
- `0x1800a61dc`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800b9a20`
- `0x1800e22e0`
- `0x180118010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18007dd5b`
- `ntdll!RtlNtStatusToDosError` at `0x18007dd5b`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x18007dec2`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x18007dec2`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtEnumerateBrokeredEvents` at `0x18007dd4b`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtEnumerateBrokeredEvents` at `0x18007dd4b`

## string_xrefs

- `0x18007dcb0`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18007de74`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18007dc4e`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18007ddc4`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18007dc47`: `ScheduledTileManager::Initialize`
- `0x18007ddbd`: `ScheduledTileManager::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ScheduledTileManager::Initialize(ScheduledTileManager *this, struct NotificationPlatform *a2)
{
  struct ExpiredScheduledTileWork *v4; // rbx
  __int64 v5; // rdx
  int UserSid; // edi
  unsigned int v7; // ecx
  int v8; // r9d
  TimerBrokerHelper *v9; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  struct ExpiredScheduledTileWork *v12; // rax
  struct ExpiredScheduledTileWork *v13; // rsi
  NTSTATUS v14; // eax
  signed int v15; // eax
  int v16; // ecx
  int PersistentEvents; // eax
  ThreadPool *v18; // rcx
  int v20; // [rsp+20h] [rbp-89h]
  unsigned int v21; // [rsp+40h] [rbp-69h] BYREF
  struct _GUID *v22; // [rsp+48h] [rbp-61h] BYREF
  ThreadPool *v23; // [rsp+50h] [rbp-59h] BYREF
  struct ExpiredScheduledTileWork *v24; // [rsp+58h] [rbp-51h]
  TimerBrokerHelper *v25; // [rsp+60h] [rbp-49h]
  _BYTE v26[80]; // [rsp+70h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v21 = 0;
  v22 = 0;
  v4 = 0;
  v24 = 0;
  v23 = 0;
  *((_QWORD *)this + 16) = a2;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<IGlobalInterfaceTable>::InternalAddRef((char *)a2 + 48, v5);
  v23 = (ThreadPool *)*((_QWORD *)a2 + 6);
  if ( !v23 )
  {
    UserSid = -2143420155;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x400,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)0x803E0105LL,
      v20);
    v8 = 411;
LABEL_3:
    WpnDebugInitTrace(
      v7,
      L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      L"ScheduledTileManager::Initialize",
      v8,
      UserSid);
    goto LABEL_31;
  }
  v9 = (TimerBrokerHelper *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
  v25 = v9;
  if ( v9 )
    v9 = TimerBrokerHelper::TimerBrokerHelper(
           v9,
           (struct ITimerBrokerCallback *)(((unsigned __int64)this + 8)
                                         & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
           a2);
  *((_QWORD *)this + 15) = v9;
  if ( v9 )
  {
    v12 = (struct ExpiredScheduledTileWork *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
    v13 = v12;
    v25 = v12;
    if ( v12 )
    {
      *(_QWORD *)v12 = &ExpiredScheduledTileWork::`vftable';
      *((_QWORD *)v12 + 5) = 0;
      *((_QWORD *)v12 + 4) = (char *)v12 + 24;
      *((_QWORD *)v12 + 3) = (char *)v12 + 24;
      v4 = v12;
      v24 = v12;
      *((_QWORD *)v12 + 5) = a2;
      v14 = BiPtEnumerateBrokeredEvents(qword_180127CB0, &v21, &v22);
      if ( v14 < 0 )
      {
        v15 = RtlNtStatusToDosError(v14);
        UserSid = v15;
        if ( v15 > 0 )
          UserSid = (unsigned __int16)v15 | 0x80070000;
      }
      else
      {
        UserSid = 0;
      }
      if ( UserSid < 0 )
      {
        v8 = 426;
        goto LABEL_3;
      }
      if ( v21 )
      {
        UserSid = WpnGetUserSid(v26);
        if ( UserSid < 0 )
        {
          if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 0x20) != 0 )
            McTemplateU0zzdqz_EventWriteTransfer(
              v16,
              (unsigned int)WPNCORE_EVENT_DEBUG_INIT,
              (unsigned int)L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
              (unsigned int)L"ScheduledTileManager::Initialize",
              175,
              UserSid,
              (__int64)&word_180124798);
          goto LABEL_31;
        }
        ScheduledTileManager::LoadPersistentEvents(this, v21, v22, v26, 1, v13);
        PersistentEvents = ScheduledTileManager::LoadPersistentEvents(this, v21, v22, v26, 0, 0);
        UserSid = 0;
        if ( PersistentEvents >= 0 )
          UserSid = PersistentEvents;
        if ( (*(int (__fastcall **)(struct ExpiredScheduledTileWork *))(*(_QWORD *)v13 + 16LL))(v13) >= 0 )
        {
          v4 = 0;
          v24 = 0;
          UserSid = ThreadPool::Submit(v23, v13);
          if ( UserSid < 0 )
            UserSid = 0;
        }
      }
      ScheduledTileManager::s_Timer = (struct TimerBrokerHelper *)*((_QWORD *)this + 15);
      goto LABEL_31;
    }
    v4 = 0;
    v24 = 0;
    UserSid = -2147024882;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1A1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)0x8007000ELL,
      v20);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v11 = 19;
      goto LABEL_30;
    }
  }
  else
  {
    UserSid = -2147024882;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)0x8007000ELL,
      v20);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v11 = 18;
LABEL_30:
      WPP_SF_d(v10[2], v11, WPP_91456f608371345bae03279a5fee97df_Traceguids, 2147942414LL);
    }
  }
LABEL_31:
  if ( v22 )
  {
    BiPtFreeMemory(v22);
    v22 = 0;
  }
  v18 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(ThreadPool *))(*(_QWORD *)v18 + 16LL))(v18);
  }
  if ( v4 )
    std::default_delete<NotificationPlatform>::operator()(v18, v4);
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x18007dbb8  push    rbp
0x18007dbba  push    rbx
0x18007dbbb  push    rsi
0x18007dbbc  push    rdi
0x18007dbbd  push    r14
0x18007dbbf  push    r15
0x18007dbc1  lea     rbp, [rsp-2Fh]
0x18007dbc6  sub     rsp, 0D8h
0x18007dbcd  mov     rax, cs:__security_cookie
0x18007dbd4  xor     rax, rsp
0x18007dbd7  mov     [rbp+57h+var_40], rax
0x18007dbdb  mov     r15, rdx
0x18007dbde  mov     r14, rcx
0x18007dbe1  mov     [rbp+57h+var_C0], 0
0x18007dbe8  mov     [rbp+57h+var_B8], 0
0x18007dbf0  xor     ebx, ebx
0x18007dbf2  mov     [rbp+57h+var_A8], rbx
0x18007dbf6  mov     [rbp+57h+var_B0], rbx
0x18007dbfa  mov     [rcx+80h], rdx
0x18007dc01  lea     rcx, [rbp+57h+var_B0]
0x18007dc05  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007dc0a  lea     rcx, [r15+30h]
0x18007dc0e  call    ?InternalAddRef@?$ComPtr@UIGlobalInterfaceTable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IGlobalInterfaceTable>::InternalAddRef(void)
0x18007dc13  mov     rax, [r15+30h]
0x18007dc17  mov     [rbp+57h+var_B0], rax
0x18007dc1b  test    rax, rax
0x18007dc1e  jnz     short loc_18007DC5F
0x18007dc20  mov     rcx, [rbp+5Fh]; this
0x18007dc24  mov     edi, 803E0105h
0x18007dc29  mov     r9d, edi; char *
0x18007dc2c  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007dc33  mov     edx, 400h; void *
0x18007dc38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007dc3d  mov     r9d, 19Bh; int
0x18007dc43  mov     [rsp+100h+var_E0], edi; int
0x18007dc47  lea     r8, aScheduledtilem; "ScheduledTileManager::Initialize"
0x18007dc4e  lea     rdx, aOnecoreuapBase_129; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007dc55  call    ?WpnDebugInitTrace@@YAXKPEBG0HJ@Z; WpnDebugInitTrace(ulong,ushort const *,ushort const *,int,long)
0x18007dc5a  jmp     loc_18007DEB9
0x18007dc5f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007dc66  mov     edi, 30h ; '0'
0x18007dc6b  mov     ecx, edi; unsigned __int64
0x18007dc6d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007dc72  mov     r9, rax
0x18007dc75  mov     [rbp+57h+var_A0], rax
0x18007dc79  test    rax, rax
0x18007dc7c  jz      short loc_18007DC9A
0x18007dc7e  mov     rax, r14
0x18007dc81  lea     rcx, [r14+8]
0x18007dc85  neg     rax
0x18007dc88  sbb     rdx, rdx
0x18007dc8b  and     rdx, rcx; struct ITimerBrokerCallback *
0x18007dc8e  mov     r8, r15; struct NotificationPlatform *
0x18007dc91  mov     rcx, r9; this
0x18007dc94  call    ??0TimerBrokerHelper@@QEAA@PEAVITimerBrokerCallback@@PEAVNotificationPlatform@@@Z; TimerBrokerHelper::TimerBrokerHelper(ITimerBrokerCallback *,NotificationPlatform *)
0x18007dc99  nop
0x18007dc9a  mov     [r14+78h], rax
0x18007dc9e  test    rax, rax
0x18007dca1  jnz     short loc_18007DCEC
0x18007dca3  mov     r9d, 8007000Eh; char *
0x18007dca9  mov     edi, r9d
0x18007dcac  mov     rcx, [rbp+5Fh]; this
0x18007dcb0  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007dcb7  mov     edx, 19Eh; void *
0x18007dcbc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007dcc1  lea     rax, WPP_GLOBAL_Control
0x18007dcc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dccf  cmp     rcx, rax
0x18007dcd2  jz      loc_18007DEB9
0x18007dcd8  test    byte ptr [rcx+1Ch], 80h
0x18007dcdc  jz      loc_18007DEB9
0x18007dce2  mov     edx, 12h
0x18007dce7  jmp     loc_18007DEA3
0x18007dcec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007dcf3  mov     rcx, rdi; unsigned __int64
0x18007dcf6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007dcfb  mov     rsi, rax
0x18007dcfe  mov     [rbp+57h+var_A0], rax
0x18007dd02  test    rax, rax
0x18007dd05  jz      loc_18007DE61
0x18007dd0b  lea     rax, ??_7ExpiredScheduledTileWork@@6B@; const ExpiredScheduledTileWork::`vftable'
0x18007dd12  mov     [rsi], rax
0x18007dd15  mov     qword ptr [rsi+28h], 0
0x18007dd1d  lea     rax, [rsi+18h]
0x18007dd21  mov     [rax+8], rax
0x18007dd25  mov     [rax], rax
0x18007dd28  mov     rbx, rsi
0x18007dd2b  mov     [rbp+57h+var_A8], rbx
0x18007dd2f  test    rsi, rsi
0x18007dd32  jz      loc_18007DE67
0x18007dd38  mov     [rsi+28h], r15
0x18007dd3c  lea     r8, [rbp+57h+var_B8]
0x18007dd40  lea     rdx, [rbp+57h+var_C0]
0x18007dd44  lea     rcx, qword_180127CB0
0x18007dd4b  call    cs:__imp_BiPtEnumerateBrokeredEvents
0x18007dd51  test    eax, eax
0x18007dd53  js      short loc_18007DD59
0x18007dd55  xor     edi, edi
0x18007dd57  jmp     short loc_18007DD70
0x18007dd59  mov     ecx, eax; Status
0x18007dd5b  call    cs:__imp_RtlNtStatusToDosError
0x18007dd61  mov     edi, eax
0x18007dd63  test    eax, eax
0x18007dd65  jle     short loc_18007DD70
0x18007dd67  movzx   edi, ax
0x18007dd6a  or      edi, 80070000h
0x18007dd70  test    edi, edi
0x18007dd72  jns     short loc_18007DD7F
0x18007dd74  mov     r9d, 1AAh
0x18007dd7a  jmp     loc_18007DC43
0x18007dd7f  cmp     [rbp+57h+var_C0], 0
0x18007dd83  jbe     loc_18007DE54
0x18007dd89  lea     rcx, [rbp+57h+var_90]; void *
0x18007dd8d  call    ?WpnGetUserSid@@YAJPEAXK@Z; WpnGetUserSid(void *,ulong)
0x18007dd92  mov     edi, eax
0x18007dd94  test    eax, eax
0x18007dd96  jns     short loc_18007DDDC
0x18007dd98  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 20h
0x18007dd9f  jz      loc_18007DEB9
0x18007dda5  lea     rax, word_180124798
0x18007ddac  mov     [rsp+100h+var_D0], rax
0x18007ddb1  mov     dword ptr [rsp+100h+var_D8], edi
0x18007ddb5  mov     [rsp+100h+var_E0], 1AFh
0x18007ddbd  lea     r9, aScheduledtilem; "ScheduledTileManager::Initialize"
0x18007ddc4  lea     r8, aOnecoreuapBase_129; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007ddcb  lea     rdx, WPNCORE_EVENT_DEBUG_INIT
0x18007ddd2  call    McTemplateU0zzdqz_EventWriteTransfer
0x18007ddd7  jmp     loc_18007DEB9
0x18007dddc  mov     [rsp+100h+var_D8], rsi; struct ExpiredScheduledTileWork *
0x18007dde1  mov     [rsp+100h+var_E0], 1; int
0x18007dde9  lea     r9, [rbp+57h+var_90]; void *
0x18007dded  mov     r8, [rbp+57h+var_B8]; struct _GUID *
0x18007ddf1  mov     edx, [rbp+57h+var_C0]; unsigned int
0x18007ddf4  mov     rcx, r14; this
0x18007ddf7  call    ?LoadPersistentEvents@ScheduledTileManager@@AEAAJKPEAU_GUID@@PEAXHPEAVExpiredScheduledTileWork@@@Z; ScheduledTileManager::LoadPersistentEvents(ulong,_GUID *,void *,int,ExpiredScheduledTileWork *)
0x18007ddfc  mov     [rsp+100h+var_D8], 0; struct ExpiredScheduledTileWork *
0x18007de05  mov     [rsp+100h+var_E0], 0; int
0x18007de0d  lea     r9, [rbp+57h+var_90]; void *
0x18007de11  mov     r8, [rbp+57h+var_B8]; struct _GUID *
0x18007de15  mov     edx, [rbp+57h+var_C0]; unsigned int
0x18007de18  mov     rcx, r14; this
0x18007de1b  call    ?LoadPersistentEvents@ScheduledTileManager@@AEAAJKPEAU_GUID@@PEAXHPEAVExpiredScheduledTileWork@@@Z; ScheduledTileManager::LoadPersistentEvents(ulong,_GUID *,void *,int,ExpiredScheduledTileWork *)
0x18007de20  xor     edi, edi
0x18007de22  test    eax, eax
0x18007de24  cmovns  edi, eax
0x18007de27  mov     rax, [rsi]
0x18007de2a  mov     rcx, rsi
0x18007de2d  mov     rax, [rax+10h]
0x18007de31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007de36  test    eax, eax
0x18007de38  js      short loc_18007DE54
0x18007de3a  xor     ebx, ebx
0x18007de3c  mov     [rbp+57h+var_A8], rbx
0x18007de40  mov     rdx, rsi; struct WorkItem *
0x18007de43  mov     rcx, [rbp+57h+var_B0]; this
0x18007de47  call    ?Submit@ThreadPool@@QEAAJPEAVWorkItem@@@Z; ThreadPool::Submit(WorkItem *)
0x18007de4c  mov     edi, eax
0x18007de4e  test    eax, eax
0x18007de50  jns     short loc_18007DE54
0x18007de52  xor     edi, edi
0x18007de54  mov     rax, [r14+78h]
0x18007de58  mov     cs:?s_Timer@ScheduledTileManager@@2PEAVTimerBrokerHelper@@EA, rax; TimerBrokerHelper * ScheduledTileManager::s_Timer
0x18007de5f  jmp     short loc_18007DEB9
0x18007de61  xor     ebx, ebx
0x18007de63  mov     [rbp+57h+var_A8], rbx
0x18007de67  mov     r9d, 8007000Eh; char *
0x18007de6d  mov     edi, r9d
0x18007de70  mov     rcx, [rbp+5Fh]; this
0x18007de74  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007de7b  mov     edx, 1A1h; void *
0x18007de80  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007de85  lea     rax, WPP_GLOBAL_Control
0x18007de8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007de93  cmp     rcx, rax
0x18007de96  jz      short loc_18007DEB9
0x18007de98  test    byte ptr [rcx+1Ch], 80h
0x18007de9c  jz      short loc_18007DEB9
0x18007de9e  mov     edx, 13h
0x18007dea3  mov     r9d, 8007000Eh
0x18007dea9  lea     r8, WPP_91456f608371345bae03279a5fee97df_Traceguids
0x18007deb0  mov     rcx, [rcx+10h]
0x18007deb4  call    WPP_SF_d
0x18007deb9  mov     rcx, [rbp+57h+var_B8]
0x18007debd  test    rcx, rcx
0x18007dec0  jz      short loc_18007DED0
0x18007dec2  call    cs:__imp_BiPtFreeMemory
0x18007dec8  mov     [rbp+57h+var_B8], 0
0x18007ded0  mov     rcx, [rbp+57h+var_B0]
0x18007ded4  test    rcx, rcx
0x18007ded7  jz      short loc_18007DEEE
0x18007ded9  mov     [rbp+57h+var_B0], 0
0x18007dee1  mov     rax, [rcx]
0x18007dee4  mov     rax, [rax+10h]
0x18007dee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007deed  nop
0x18007deee  test    rbx, rbx
0x18007def1  jz      short loc_18007DEFB
0x18007def3  mov     rdx, rbx
0x18007def6  call    ??R?$default_delete@VNotificationPlatform@@@std@@QEBAXPEAVNotificationPlatform@@@Z; std::default_delete<NotificationPlatform>::operator()(NotificationPlatform *)
0x18007defb  mov     eax, edi
0x18007defd  mov     rcx, [rbp+57h+var_40]
0x18007df01  xor     rcx, rsp; StackCookie
0x18007df04  call    __security_check_cookie
0x18007df09  add     rsp, 0D8h
0x18007df10  pop     r15
0x18007df12  pop     r14
0x18007df14  pop     rdi
0x18007df15  pop     rsi
0x18007df16  pop     rbx
0x18007df17  pop     rbp
0x18007df18  retn
```
