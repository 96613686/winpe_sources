# RouteManagement::BadConnectionState::BadStateTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18005b590`
- end: `0x18005b8a2`
- name: `?BadStateTimerCallback@BadConnectionState@RouteManagement@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `786`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x1800137a0`
- `0x18001eb54`
- `0x180027630`
- `0x180033d00`
- `0x180036c30`
- `0x18003730c`
- `0x1800495b0`
- `0x18005b590`
- `0x180084f50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b87a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b87a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005b5eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005b5eb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005b6e0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005b6e0`

## string_xrefs

- `0x18005b620`: `onecoreuap\net\wcm\service\base\routemanager\routemanagerbadconnectionstate.cpp`
- `0x18005b750`: `onecoreuap\net\wcm\service\base\routemanager\routemanagerbadconnectionstate.cpp`
- `0x18005b7f0`: `onecoreuap\net\wcm\service\base\routemanager\routemanagerbadconnectionstate.cpp`

## pseudocode

```c
void __fastcall RouteManagement::BadConnectionState::BadStateTimerCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_TIMER Timer)
{
  int v4; // ecx
  int v5; // ecx
  int v6; // ebx
  unsigned int v7; // r14d
  unsigned int *v8; // rsi
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rax
  __int64 v13; // rdx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rax
  __int64 v18; // r10
  int v19; // edx
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // [rsp+40h] [rbp-30h] BYREF
  const char *v24; // [rsp+48h] [rbp-28h] BYREF
  const char *v25; // [rsp+50h] [rbp-20h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-18h] BYREF
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp-10h] BYREF

  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, Context + 16);
  v4 = *((_DWORD *)Context + 14);
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      if ( v5 == 1 )
      {
        v6 = *((_DWORD *)Context + 16);
        v7 = GetTickCount64() - v6;
        v8 = (unsigned int *)(Context + 60);
        if ( (unsigned int)dword_18013A120 > 5 )
        {
          v23 = EnumToString(*v8);
          v24 = Context;
          v25 = "BadConnectionState::BadStateTimerCallback : currently BadConnectivity";
          pftDueTime = (struct _FILETIME)"onecoreuap\\net\\wcm\\service\\base\\routemanager\\routemanagerbadconnectionstate.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
            v9,
            (unsigned int)byte_18011B70B,
            v10,
            v11,
            (__int64)&pftDueTime,
            (__int64)&v25,
            (__int64)&v24,
            (__int64)&v23);
        }
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v12 = EnumToString(*v8);
          WPP_SF__guid_sDD(*(_QWORD *)(v13 + 16), v12, v7, *((_DWORD *)Context + 19));
        }
        PublishWnfStateTimeIfEnabled(Context, *v8, *((unsigned int *)Context + 14), *((unsigned int *)Context + 19), v7);
        if ( v7 < 0x1D4C0 )
        {
          v23 = -20000000;
          pftDueTime = (struct _FILETIME)-20000000LL;
          SetThreadpoolTimer(*((PTP_TIMER *)Context + 13), &pftDueTime, 0, 0);
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, &WPP_b117651525d03ae6d39c613c7f962000_Traceguids, 2000);
          }
        }
      }
      goto LABEL_28;
    }
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      pftDueTime = (struct _FILETIME)EnumToString(*((unsigned int *)Context + 15));
      v25 = Context;
      v24 = "BadConnectionState::BadStateTimerCallback : currently GoodConnectivity";
      v23 = (__int64)"onecoreuap\\net\\wcm\\service\\base\\routemanager\\routemanagerbadconnectionstate.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        v14,
        (unsigned int)&byte_18011B6BF,
        v15,
        v16,
        (__int64)&v23,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&pftDueTime);
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v17 = EnumToString(*((unsigned int *)Context + 15));
      v19 = 20;
LABEL_27:
      WPP_SF__guid_s(
        *(_QWORD *)(v18 + 16),
        v19,
        (unsigned int)&WPP_b117651525d03ae6d39c613c7f962000_Traceguids,
        (_DWORD)Context,
        v17);
    }
  }
  else
  {
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      pftDueTime = (struct _FILETIME)EnumToString(*((unsigned int *)Context + 15));
      v25 = Context;
      v24 = "BadConnectionState::BadStateTimerCallback : currently Disconnected";
      v23 = (__int64)"onecoreuap\\net\\wcm\\service\\base\\routemanager\\routemanagerbadconnectionstate.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        v20,
        (unsigned int)byte_18011B673,
        v21,
        v22,
        (__int64)&v23,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&pftDueTime);
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v17 = EnumToString(*((unsigned int *)Context + 15));
      v19 = 19;
      goto LABEL_27;
    }
  }
LABEL_28:
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18005b590  mov     [rsp-18h+arg_0], rbx
0x18005b595  mov     [rsp-18h+arg_10], rsi
0x18005b59a  push    rbp
0x18005b59b  push    rdi
0x18005b59c  push    r14
0x18005b59e  mov     rbp, rsp
0x18005b5a1  sub     rsp, 70h
0x18005b5a5  mov     rax, cs:__security_cookie
0x18005b5ac  xor     rax, rsp
0x18005b5af  mov     [rbp+var_8], rax
0x18005b5b3  mov     rdi, rdx
0x18005b5b6  mov     [rbp+lpCriticalSection], 0
0x18005b5be  add     rdx, 10h
0x18005b5c2  lea     rcx, [rbp+lpCriticalSection]
0x18005b5c6  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18005b5cb  mov     ecx, [rdi+38h]
0x18005b5ce  test    ecx, ecx
0x18005b5d0  jz      loc_18005B7CA
0x18005b5d6  sub     ecx, 1
0x18005b5d9  jz      loc_18005B72A
0x18005b5df  cmp     ecx, 1
0x18005b5e2  jnz     loc_18005B871
0x18005b5e8  mov     ebx, [rdi+40h]
0x18005b5eb  call    cs:__imp_GetTickCount64
0x18005b5f1  mov     r14, rax
0x18005b5f4  sub     r14d, ebx
0x18005b5f7  mov     ecx, cs:dword_18013A120
0x18005b5fd  lea     rsi, [rdi+3Ch]
0x18005b601  cmp     ecx, 5
0x18005b604  jbe     short loc_18005B65B
0x18005b606  mov     ecx, [rsi]
0x18005b608  call    ?EnumToString@@YAPEBDW4_WCM_MEDIA_TYPE@@@Z; EnumToString(_WCM_MEDIA_TYPE)
0x18005b60d  mov     [rbp+var_30], rax
0x18005b611  mov     [rbp+var_28], rdi
0x18005b615  lea     rax, aBadconnections; "BadConnectionState::BadStateTimerCallba"...
0x18005b61c  mov     [rbp+var_20], rax
0x18005b620  lea     rax, aOnecoreuapNetW_16; "onecoreuap\\net\\wcm\\service\\base\\ro"...
0x18005b627  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x18005b62b  lea     rax, [rbp+var_30]
0x18005b62f  mov     [rsp+70h+var_38], rax
0x18005b634  lea     rax, [rbp+var_28]
0x18005b638  mov     qword ptr [rsp+70h+var_40], rax
0x18005b63d  lea     rax, [rbp+var_20]
0x18005b641  mov     qword ptr [rsp+70h+var_48], rax
0x18005b646  lea     rax, [rbp+pftDueTime]
0x18005b64a  mov     [rsp+70h+var_50], rax
0x18005b64f  lea     rdx, byte_18011B70B
0x18005b656  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x18005b65b  lea     rbx, WPP_GLOBAL_Control
0x18005b662  mov     rdx, cs:WPP_GLOBAL_Control
0x18005b669  cmp     rdx, rbx
0x18005b66c  jz      short loc_18005B69E
0x18005b66e  cmp     byte ptr [rdx+19h], 4
0x18005b672  jb      short loc_18005B69E
0x18005b674  test    byte ptr [rdx+1Ch], 1
0x18005b678  jz      short loc_18005B69E
0x18005b67a  mov     ecx, [rsi]
0x18005b67c  call    ?EnumToString@@YAPEBDW4_WCM_MEDIA_TYPE@@@Z; EnumToString(_WCM_MEDIA_TYPE)
0x18005b681  mov     ecx, [rdi+4Ch]
0x18005b684  mov     dword ptr [rsp+70h+var_40], ecx; char
0x18005b688  mov     dword ptr [rsp+70h+var_48], r14d; char
0x18005b68d  mov     [rsp+70h+var_50], rax; __int64
0x18005b692  mov     r9, rdi
0x18005b695  mov     rcx, [rdx+10h]; LoggerHandle
0x18005b699  call    WPP_SF__guid_sDD
0x18005b69e  mov     dword ptr [rsp+70h+var_50], r14d
0x18005b6a3  mov     r9d, [rdi+4Ch]
0x18005b6a7  mov     r8d, [rdi+38h]
0x18005b6ab  mov     edx, [rsi]
0x18005b6ad  mov     rcx, rdi
0x18005b6b0  call    ?PublishWnfStateTimeIfEnabled@@YAXAEBU_GUID@@W4_WCM_MEDIA_TYPE@@W4ConnectionQualityState@RouteManagement@@KK@Z; PublishWnfStateTimeIfEnabled(_GUID const &,_WCM_MEDIA_TYPE,RouteManagement::ConnectionQualityState,ulong,ulong)
0x18005b6b5  cmp     r14d, 1D4C0h
0x18005b6bc  jnb     loc_18005B871
0x18005b6c2  mov     [rbp+var_30], 0FFFFFFFFFECED300h
0x18005b6ca  mov     rax, [rbp+var_30]
0x18005b6ce  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x18005b6d2  xor     r9d, r9d; msWindowLength
0x18005b6d5  xor     r8d, r8d; msPeriod
0x18005b6d8  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x18005b6dc  mov     rcx, [rdi+68h]; pti
0x18005b6e0  call    cs:__imp_SetThreadpoolTimer
0x18005b6e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b6ed  cmp     rcx, rbx
0x18005b6f0  jz      loc_18005B871
0x18005b6f6  cmp     byte ptr [rcx+19h], 4
0x18005b6fa  jb      loc_18005B871
0x18005b700  test    byte ptr [rcx+1Ch], 1
0x18005b704  jz      loc_18005B871
0x18005b70a  mov     edx, 16h
0x18005b70f  mov     r9d, 7D0h
0x18005b715  lea     r8, WPP_b117651525d03ae6d39c613c7f962000_Traceguids
0x18005b71c  mov     rcx, [rcx+10h]
0x18005b720  call    WPP_SF_d
0x18005b725  jmp     loc_18005B871
0x18005b72a  mov     eax, cs:dword_18013A120
0x18005b730  cmp     eax, 5
0x18005b733  jbe     short loc_18005B78B
0x18005b735  mov     ecx, [rdi+3Ch]
0x18005b738  call    ?EnumToString@@YAPEBDW4_WCM_MEDIA_TYPE@@@Z; EnumToString(_WCM_MEDIA_TYPE)
0x18005b73d  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x18005b741  mov     [rbp+var_20], rdi
0x18005b745  lea     rax, aBadconnections_10; "BadConnectionState::BadStateTimerCallba"...
0x18005b74c  mov     [rbp+var_28], rax
0x18005b750  lea     rax, aOnecoreuapNetW_16; "onecoreuap\\net\\wcm\\service\\base\\ro"...
0x18005b757  mov     [rbp+var_30], rax
0x18005b75b  lea     rax, [rbp+pftDueTime]
0x18005b75f  mov     [rsp+70h+var_38], rax
0x18005b764  lea     rax, [rbp+var_20]
0x18005b768  mov     qword ptr [rsp+70h+var_40], rax
0x18005b76d  lea     rax, [rbp+var_28]
0x18005b771  mov     qword ptr [rsp+70h+var_48], rax
0x18005b776  lea     rax, [rbp+var_30]
0x18005b77a  mov     [rsp+70h+var_50], rax
0x18005b77f  lea     rdx, byte_18011B6BF
0x18005b786  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x18005b78b  lea     rbx, WPP_GLOBAL_Control
0x18005b792  mov     r10, cs:WPP_GLOBAL_Control
0x18005b799  cmp     r10, rbx
0x18005b79c  jz      loc_18005B871
0x18005b7a2  cmp     byte ptr [r10+19h], 4
0x18005b7a7  jb      loc_18005B871
0x18005b7ad  test    byte ptr [r10+1Ch], 1
0x18005b7b2  jz      loc_18005B871
0x18005b7b8  mov     ecx, [rdi+3Ch]
0x18005b7bb  call    ?EnumToString@@YAPEBDW4_WCM_MEDIA_TYPE@@@Z; EnumToString(_WCM_MEDIA_TYPE)
0x18005b7c0  mov     edx, 14h
0x18005b7c5  jmp     loc_18005B859
0x18005b7ca  mov     eax, cs:dword_18013A120
0x18005b7d0  cmp     eax, 5
0x18005b7d3  jbe     short loc_18005B82B
0x18005b7d5  mov     ecx, [rdi+3Ch]
0x18005b7d8  call    ?EnumToString@@YAPEBDW4_WCM_MEDIA_TYPE@@@Z; EnumToString(_WCM_MEDIA_TYPE)
0x18005b7dd  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x18005b7e1  mov     [rbp+var_20], rdi
0x18005b7e5  lea     rax, aBadconnections_3; "BadConnectionState::BadStateTimerCallba"...
0x18005b7ec  mov     [rbp+var_28], rax
0x18005b7f0  lea     rax, aOnecoreuapNetW_16; "onecoreuap\\net\\wcm\\service\\base\\ro"...
0x18005b7f7  mov     [rbp+var_30], rax
0x18005b7fb  lea     rax, [rbp+pftDueTime]
0x18005b7ff  mov     [rsp+70h+var_38], rax
0x18005b804  lea     rax, [rbp+var_20]
0x18005b808  mov     qword ptr [rsp+70h+var_40], rax
0x18005b80d  lea     rax, [rbp+var_28]
0x18005b811  mov     qword ptr [rsp+70h+var_48], rax
0x18005b816  lea     rax, [rbp+var_30]
0x18005b81a  mov     [rsp+70h+var_50], rax
0x18005b81f  lea     rdx, byte_18011B673
0x18005b826  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x18005b82b  lea     rbx, WPP_GLOBAL_Control
0x18005b832  mov     r10, cs:WPP_GLOBAL_Control
0x18005b839  cmp     r10, rbx
0x18005b83c  jz      short loc_18005B871
0x18005b83e  cmp     byte ptr [r10+19h], 4
0x18005b843  jb      short loc_18005B871
0x18005b845  test    byte ptr [r10+1Ch], 1
0x18005b84a  jz      short loc_18005B871
0x18005b84c  mov     ecx, [rdi+3Ch]
0x18005b84f  call    ?EnumToString@@YAPEBDW4_WCM_MEDIA_TYPE@@@Z; EnumToString(_WCM_MEDIA_TYPE)
0x18005b854  mov     edx, 13h
0x18005b859  mov     [rsp+70h+var_50], rax
0x18005b85e  mov     r9, rdi
0x18005b861  lea     r8, WPP_b117651525d03ae6d39c613c7f962000_Traceguids
0x18005b868  mov     rcx, [r10+10h]
0x18005b86c  call    WPP_SF__guid_s
0x18005b871  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18005b875  test    rcx, rcx
0x18005b878  jz      short loc_18005B881
0x18005b87a  call    cs:__imp_LeaveCriticalSection
0x18005b880  nop
0x18005b881  mov     rcx, [rbp+var_8]
0x18005b885  xor     rcx, rsp; StackCookie
0x18005b888  call    __security_check_cookie
0x18005b88d  lea     r11, [rsp+70h+var_s0]
0x18005b892  mov     rbx, [r11+20h]
0x18005b896  mov     rsi, [r11+30h]
0x18005b89a  mov     rsp, r11
0x18005b89d  pop     r14
0x18005b89f  pop     rdi
0x18005b8a0  pop     rbp
0x18005b8a1  retn
```
