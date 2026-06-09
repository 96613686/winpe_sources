# PeriodicUpdateManager::Initialize(NotificationPlatform *)

- ea: `0x180032b54`
- end: `0x180032ecb`
- name: `?Initialize@PeriodicUpdateManager@@QEAAJPEAVNotificationPlatform@@@Z`
- size: `887`
- prototype: `int(PeriodicUpdateManager *__hidden this, struct NotificationPlatform *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180035508`

## callees

- `0x180024640`
- `0x18002e5d0`
- `0x18002ee38`
- `0x180032b54`
- `0x180032ed4`
- `0x1800330f0`
- `0x1800a61dc`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800b9a20`
- `0x1800d7f04`
- `0x1800e22e0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032d0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032e11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032d0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032e11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032d18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032e1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032d18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032e1f`
- `ntdll!RtlNtStatusToDosError` at `0x180032c75`
- `ntdll!RtlNtStatusToDosError` at `0x180032c75`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x180032e9c`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x180032e9c`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtEnumerateBrokeredEvents` at `0x180032c65`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtEnumerateBrokeredEvents` at `0x180032c65`

## string_xrefs

- `0x180032c00`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x180032cd8`: `PeriodicUpdateManager::Initialize`
- `0x180032e79`: `PeriodicUpdateManager::Initialize`
- `0x180032cdf`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x180032e80`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PeriodicUpdateManager::Initialize(PeriodicUpdateManager *this, struct NotificationPlatform *a2)
{
  struct _PERSISTED_PERIODIC_UPDATE *v4; // rdi
  __int64 (__fastcall ***v5)(_QWORD, char *, int *); // r13
  TimerBrokerHelper *v6; // rax
  signed int v7; // ebx
  NTSTATUS v8; // eax
  int v9; // ecx
  signed int v10; // eax
  unsigned int v11; // eax
  int UserSid; // eax
  unsigned int v13; // ecx
  unsigned int v14; // r15d
  HANDLE v15; // rax
  __int64 v16; // r12
  int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  HANDLE ProcessHeap; // rax
  int v22; // [rsp+20h] [rbp-89h]
  unsigned int v23; // [rsp+40h] [rbp-69h] BYREF
  int v24; // [rsp+44h] [rbp-65h] BYREF
  __int64 v25; // [rsp+48h] [rbp-61h] BYREF
  int v26; // [rsp+50h] [rbp-59h] BYREF
  struct _PERSISTED_PERIODIC_UPDATE *v27; // [rsp+58h] [rbp-51h] BYREF
  struct _GUID v28; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v29[80]; // [rsp+70h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v24 = 0;
  v23 = 0;
  v26 = 0;
  v25 = 0;
  v4 = 0;
  v27 = 0;
  v5 = (__int64 (__fastcall ***)(_QWORD, char *, int *))*((_QWORD *)a2 + 23);
  if ( v5 )
  {
    v6 = (TimerBrokerHelper *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
    *(_QWORD *)&v28.Data1 = v6;
    if ( v6 )
      v6 = TimerBrokerHelper::TimerBrokerHelper(
             v6,
             (struct ITimerBrokerCallback *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
             a2);
    *((_QWORD *)this + 3) = v6;
    if ( !v6 )
    {
      v7 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x126,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)0x8007000ELL,
        v22);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids, 2147942414LL);
      goto LABEL_42;
    }
    *((_QWORD *)this + 4) = a2;
    v8 = BiPtEnumerateBrokeredEvents(qword_1801252B0, &v23, &v25);
    if ( v8 < 0 )
    {
      v10 = RtlNtStatusToDosError(v8);
      v7 = v10;
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
    }
    else
    {
      v7 = 0;
    }
    if ( v7 < 0 )
    {
      if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 0x20) != 0 )
        McTemplateU0zzdqz_EventWriteTransfer(
          v9,
          (unsigned int)WPNCORE_EVENT_DEBUG_INIT,
          (unsigned int)L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
          (unsigned int)L"PeriodicUpdateManager::Initialize",
          50,
          v7,
          (__int64)&word_180124798);
      goto LABEL_42;
    }
    v11 = v23;
    if ( v23 )
    {
      UserSid = WpnGetUserSid(v29);
      v7 = UserSid;
      if ( UserSid < 0 )
      {
        WpnDebugInitTrace(
          v13,
          L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
          L"PeriodicUpdateManager::Initialize",
          310,
          UserSid);
        goto LABEL_42;
      }
      v11 = v23;
    }
    v14 = 0;
    if ( !v11 )
    {
LABEL_34:
      PeriodicUpdateManager::s_Timer = (struct TimerBrokerHelper *)*((_QWORD *)this + 3);
      if ( v4 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v4);
      }
      goto LABEL_42;
    }
    while ( 1 )
    {
      if ( v4 )
      {
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v4);
        v27 = 0;
      }
      v16 = 16LL * v14;
      v28 = *(struct _GUID *)(v16 + v25);
      v17 = PeriodicUpdateManager::UnpackPersistedEvent(&v28, v29, &v27, &v24);
      v7 = v17;
      v4 = v27;
      if ( v17 < 0 )
        break;
      if ( !v24 )
        goto LABEL_33;
      v17 = (**v5)(v5, (char *)v27 + 80, &v26);
      if ( v17 == -2147023728 )
      {
        v28 = *(struct _GUID *)(v16 + v25);
        PeriodicUpdateManager::CleanupTimer(this, &v28, v4);
LABEL_31:
        v7 = TimerBrokerHelper::AddToList(
               *((TimerBrokerHelper **)this + 3),
               v4,
               (const struct _GUID *)(v16 + v25),
               0,
               0);
        if ( v7 < 0 )
          v7 = 0;
        goto LABEL_33;
      }
      if ( v17 >= 0 )
        goto LABEL_31;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v19 = 20;
LABEL_26:
        WPP_SF_d(v18[2], v19, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids, (unsigned int)v17);
      }
LABEL_27:
      v7 = 0;
LABEL_33:
      if ( ++v14 >= v23 )
        goto LABEL_34;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_27;
    v19 = 18;
    goto LABEL_26;
  }
  v7 = -2143420155;
  if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 0x20) == 0 )
    return (unsigned int)v7;
  McTemplateU0zzdqz_EventWriteTransfer(
    (_DWORD)this,
    (unsigned int)WPNCORE_EVENT_DEBUG_INIT,
    (unsigned int)L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
    (unsigned int)L"PeriodicUpdateManager::Initialize",
    35,
    5,
    (__int64)&word_180124798);
LABEL_42:
  if ( v25 )
    BiPtFreeMemory(v25);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180032b54  mov     [rsp-8+arg_10], rbx
0x180032b59  push    rbp
0x180032b5a  push    rsi
0x180032b5b  push    rdi
0x180032b5c  push    r12
0x180032b5e  push    r13
0x180032b60  push    r14
0x180032b62  push    r15
0x180032b64  lea     rbp, [rsp-27h]
0x180032b69  sub     rsp, 0D0h
0x180032b70  mov     rax, cs:__security_cookie
0x180032b77  xor     rax, rsp
0x180032b7a  mov     [rbp+57h+var_40], rax
0x180032b7e  mov     rbx, rdx
0x180032b81  mov     rsi, rcx
0x180032b84  mov     [rbp+57h+var_BC], 0
0x180032b8b  mov     [rbp+57h+var_C0], 0
0x180032b92  mov     [rbp+57h+var_B0], 0
0x180032b99  mov     [rbp+57h+var_B8], 0
0x180032ba1  xor     edi, edi
0x180032ba3  mov     [rbp+57h+var_A8], rdi
0x180032ba7  mov     r13, [rdx+0B8h]
0x180032bae  test    r13, r13
0x180032bb1  jz      loc_180032E4F
0x180032bb7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180032bbe  lea     ecx, [rdi+30h]; unsigned __int64
0x180032bc1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180032bc6  mov     qword ptr [rbp+57h+var_A0.Data1], rax
0x180032bca  test    rax, rax
0x180032bcd  jz      short loc_180032BEB
0x180032bcf  mov     rcx, rsi
0x180032bd2  lea     r8, [rsi+8]
0x180032bd6  neg     rcx
0x180032bd9  sbb     rdx, rdx
0x180032bdc  and     rdx, r8; struct ITimerBrokerCallback *
0x180032bdf  mov     r8, rbx; struct NotificationPlatform *
0x180032be2  mov     rcx, rax; this
0x180032be5  call    ??0TimerBrokerHelper@@QEAA@PEAVITimerBrokerCallback@@PEAVNotificationPlatform@@@Z; TimerBrokerHelper::TimerBrokerHelper(ITimerBrokerCallback *,NotificationPlatform *)
0x180032bea  nop
0x180032beb  mov     [rsi+18h], rax
0x180032bef  test    rax, rax
0x180032bf2  jnz     short loc_180032C52
0x180032bf4  mov     ebx, 8007000Eh
0x180032bf9  mov     rcx, [rbp+5Fh]; this
0x180032bfd  mov     r9d, ebx; char *
0x180032c00  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180032c07  mov     edx, 126h; void *
0x180032c0c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180032c11  lea     r14, WPP_GLOBAL_Control
0x180032c18  mov     rcx, cs:WPP_GLOBAL_Control
0x180032c1f  cmp     rcx, r14
0x180032c22  jz      loc_180032E93
0x180032c28  test    byte ptr [rcx+1Ch], 80h
0x180032c2c  jz      loc_180032E93
0x180032c32  mov     edx, 0Fh
0x180032c37  mov     r9d, 8007000Eh
0x180032c3d  lea     r8, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids
0x180032c44  mov     rcx, [rcx+10h]
0x180032c48  call    WPP_SF_d
0x180032c4d  jmp     loc_180032E93
0x180032c52  mov     [rsi+20h], rbx
0x180032c56  lea     r8, [rbp+57h+var_B8]
0x180032c5a  lea     rdx, [rbp+57h+var_C0]
0x180032c5e  lea     rcx, qword_1801252B0
0x180032c65  call    cs:__imp_BiPtEnumerateBrokeredEvents
0x180032c6b  test    eax, eax
0x180032c6d  js      short loc_180032C73
0x180032c6f  xor     ebx, ebx
0x180032c71  jmp     short loc_180032C8A
0x180032c73  mov     ecx, eax; Status
0x180032c75  call    cs:__imp_RtlNtStatusToDosError
0x180032c7b  mov     ebx, eax
0x180032c7d  test    eax, eax
0x180032c7f  jle     short loc_180032C8A
0x180032c81  movzx   ebx, ax
0x180032c84  or      ebx, 80070000h
0x180032c8a  test    ebx, ebx
0x180032c8c  jns     short loc_180032CB8
0x180032c8e  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 20h
0x180032c95  jz      loc_180032E93
0x180032c9b  lea     rax, word_180124798
0x180032ca2  mov     [rsp+100h+var_D0], rax
0x180032ca7  mov     [rsp+100h+var_D8], ebx
0x180032cab  mov     [rsp+100h+var_E0], 132h
0x180032cb3  jmp     loc_180032E79
0x180032cb8  mov     eax, [rbp+57h+var_C0]
0x180032cbb  test    eax, eax
0x180032cbd  jz      short loc_180032CF3
0x180032cbf  lea     rcx, [rbp+57h+var_90]; void *
0x180032cc3  call    ?WpnGetUserSid@@YAJPEAXK@Z; WpnGetUserSid(void *,ulong)
0x180032cc8  mov     ebx, eax
0x180032cca  test    eax, eax
0x180032ccc  jns     short loc_180032CF0
0x180032cce  mov     [rsp+100h+var_E0], eax; int
0x180032cd2  mov     r9d, 136h; int
0x180032cd8  lea     r8, aPeriodicupdate; "PeriodicUpdateManager::Initialize"
0x180032cdf  lea     rdx, aOnecoreuapBase_156; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180032ce6  call    ?WpnDebugInitTrace@@YAXKPEBG0HJ@Z; WpnDebugInitTrace(ulong,ushort const *,ushort const *,int,long)
0x180032ceb  jmp     loc_180032E93
0x180032cf0  mov     eax, [rbp+57h+var_C0]
0x180032cf3  xor     r15d, r15d
0x180032cf6  test    eax, eax
0x180032cf8  jz      loc_180032DFD
0x180032cfe  lea     r14, WPP_GLOBAL_Control
0x180032d05  test    rdi, rdi
0x180032d08  jz      short loc_180032D26
0x180032d0a  call    cs:__imp_GetProcessHeap
0x180032d10  mov     r8, rdi; lpMem
0x180032d13  xor     edx, edx; dwFlags
0x180032d15  mov     rcx, rax; hHeap
0x180032d18  call    cs:__imp_HeapFree
0x180032d1e  mov     [rbp+57h+var_A8], 0
0x180032d26  mov     r12d, r15d
0x180032d29  shl     r12, 4
0x180032d2d  mov     rax, [rbp+57h+var_B8]
0x180032d31  movups  xmm0, xmmword ptr [r12+rax]
0x180032d36  movdqu  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x180032d3b  lea     r9, [rbp+57h+var_BC]; int *
0x180032d3f  lea     r8, [rbp+57h+var_A8]; struct _PERSISTED_PERIODIC_UPDATE **
0x180032d43  lea     rdx, [rbp+57h+var_90]; void *
0x180032d47  lea     rcx, [rbp+57h+var_A0]; struct _GUID
0x180032d4b  call    ?UnpackPersistedEvent@PeriodicUpdateManager@@CAJU_GUID@@PEAXPEAPEAU_PERSISTED_PERIODIC_UPDATE@@PEAH@Z; PeriodicUpdateManager::UnpackPersistedEvent(_GUID,void *,_PERSISTED_PERIODIC_UPDATE * *,int *)
0x180032d50  mov     ebx, eax
0x180032d52  mov     rdi, [rbp+57h+var_A8]
0x180032d56  test    eax, eax
0x180032d58  jns     short loc_180032D88
0x180032d5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032d61  cmp     rcx, r14
0x180032d64  jz      short loc_180032D84
0x180032d66  test    byte ptr [rcx+1Ch], 80h
0x180032d6a  jz      short loc_180032D84
0x180032d6c  mov     edx, 12h
0x180032d71  mov     r9d, eax
0x180032d74  lea     r8, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids
0x180032d7b  mov     rcx, [rcx+10h]
0x180032d7f  call    WPP_SF_d
0x180032d84  xor     ebx, ebx
0x180032d86  jmp     short loc_180032DF0
0x180032d88  cmp     [rbp+57h+var_BC], 0
0x180032d8c  jz      short loc_180032DF0
0x180032d8e  mov     rax, [r13+0]
0x180032d92  lea     rdx, [rdi+50h]
0x180032d96  lea     r8, [rbp+57h+var_B0]
0x180032d9a  mov     rcx, r13
0x180032d9d  mov     rax, [rax]
0x180032da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032da5  cmp     eax, 80070490h
0x180032daa  jnz     short loc_180032E27
0x180032dac  mov     rax, [rbp+57h+var_B8]
0x180032db0  movups  xmm0, xmmword ptr [r12+rax]
0x180032db5  movdqu  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x180032dba  mov     r8, rdi; struct _WPN_TIMER_PERSISTENCE *
0x180032dbd  lea     rdx, [rbp+57h+var_A0]; struct _GUID
0x180032dc1  mov     rcx, rsi; this
0x180032dc4  call    ?CleanupTimer@PeriodicUpdateManager@@AEAAXU_GUID@@PEAU_WPN_TIMER_PERSISTENCE@@@Z; PeriodicUpdateManager::CleanupTimer(_GUID,_WPN_TIMER_PERSISTENCE *)
0x180032dc9  mov     r8, [rbp+57h+var_B8]
0x180032dcd  add     r8, r12; struct _GUID *
0x180032dd0  mov     [rsp+100h+var_E0], 0; int
0x180032dd8  xor     r9d, r9d; unsigned __int64
0x180032ddb  mov     rdx, rdi; struct _WPN_TIMER_PERSISTENCE *
0x180032dde  mov     rcx, [rsi+18h]; this
0x180032de2  call    ?AddToList@TimerBrokerHelper@@QEAAJPEAU_WPN_TIMER_PERSISTENCE@@PEBU_GUID@@_KH@Z; TimerBrokerHelper::AddToList(_WPN_TIMER_PERSISTENCE *,_GUID const *,unsigned __int64,int)
0x180032de7  mov     ebx, eax
0x180032de9  xor     eax, eax
0x180032deb  test    ebx, ebx
0x180032ded  cmovs   ebx, eax
0x180032df0  inc     r15d
0x180032df3  cmp     r15d, [rbp+57h+var_C0]
0x180032df7  jb      loc_180032D05
0x180032dfd  mov     rax, [rsi+18h]
0x180032e01  mov     cs:?s_Timer@PeriodicUpdateManager@@2PEAVTimerBrokerHelper@@EA, rax; TimerBrokerHelper * PeriodicUpdateManager::s_Timer
0x180032e08  test    rdi, rdi
0x180032e0b  jz      loc_180032E93
0x180032e11  call    cs:__imp_GetProcessHeap
0x180032e17  mov     r8, rdi; lpMem
0x180032e1a  xor     edx, edx; dwFlags
0x180032e1c  mov     rcx, rax; hHeap
0x180032e1f  call    cs:__imp_HeapFree
0x180032e25  jmp     short loc_180032E93
0x180032e27  test    eax, eax
0x180032e29  jns     short loc_180032DC9
0x180032e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e32  cmp     rcx, r14
0x180032e35  jz      loc_180032D84
0x180032e3b  test    byte ptr [rcx+1Ch], 80h
0x180032e3f  jz      loc_180032D84
0x180032e45  mov     edx, 14h
0x180032e4a  jmp     loc_180032D71
0x180032e4f  mov     ebx, 803E0105h
0x180032e54  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 20h
0x180032e5b  jz      short loc_180032EA2
0x180032e5d  lea     rax, word_180124798
0x180032e64  mov     [rsp+100h+var_D0], rax
0x180032e69  mov     [rsp+100h+var_D8], 803E0105h
0x180032e71  mov     [rsp+100h+var_E0], 123h
0x180032e79  lea     r9, aPeriodicupdate; "PeriodicUpdateManager::Initialize"
0x180032e80  lea     r8, aOnecoreuapBase_156; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180032e87  lea     rdx, WPNCORE_EVENT_DEBUG_INIT
0x180032e8e  call    McTemplateU0zzdqz_EventWriteTransfer
0x180032e93  mov     rcx, [rbp+57h+var_B8]
0x180032e97  test    rcx, rcx
0x180032e9a  jz      short loc_180032EA2
0x180032e9c  call    cs:__imp_BiPtFreeMemory
0x180032ea2  mov     eax, ebx
0x180032ea4  mov     rcx, [rbp+57h+var_40]
0x180032ea8  xor     rcx, rsp; StackCookie
0x180032eab  call    __security_check_cookie
0x180032eb0  mov     rbx, [rsp+100h+arg_10]
0x180032eb8  add     rsp, 0D0h
0x180032ebf  pop     r15
0x180032ec1  pop     r14
0x180032ec3  pop     r13
0x180032ec5  pop     r12
0x180032ec7  pop     rdi
0x180032ec8  pop     rsi
0x180032ec9  pop     rbp
0x180032eca  retn
```
