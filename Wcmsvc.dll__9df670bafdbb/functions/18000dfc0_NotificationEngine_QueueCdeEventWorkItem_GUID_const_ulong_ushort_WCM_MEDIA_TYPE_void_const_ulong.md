# NotificationEngine::QueueCdeEventWorkItem(_GUID const &,ulong,ushort,_WCM_MEDIA_TYPE,void const *,ulong)

- ea: `0x18000dfc0`
- end: `0x18000e67c`
- name: `?QueueCdeEventWorkItem@NotificationEngine@@SAXAEBU_GUID@@KGW4_WCM_MEDIA_TYPE@@PEBXK@Z`
- size: `1724`
- prototype: ``
- caller_count: `12`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000b128`
- `0x18000ded0`
- `0x18004acb0`
- `0x1800590c0`
- `0x18005e85c`
- `0x18006ef00`
- `0x1800729dc`
- `0x18008d1e0`
- `0x18009f4b0`
- `0x1800a0dc4`
- `0x1800c3ba0`
- `0x1800c3c10`

## callees

- `0x18000d3a0`
- `0x18000dfc0`
- `0x18000e720`
- `0x180010080`
- `0x180019434`
- `0x18002b440`
- `0x18008e64c`
- `0x18008e688`
- `0x18008f140`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e0ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e0ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e0e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e346`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e0e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e346`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000e0fd`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000e0fd`

## string_xrefs

- `0x18000e226`: `wcm_notification_cde_link_speed_change`
- `0x18000e495`: `wcm_notification_cde_set_radio_state_complete`
- `0x18000e4c5`: `wcm_notification_cde_ondemand_token_applied`
- `0x18000e4dd`: `wcm_notification_cde_l2_available_connection_delete`
- `0x18000e501`: `wcm_notification_cde_link_degraded`
- `0x18000e50d`: `wcm_notification_cde_link_improved`
- `0x18000e525`: `wcm_notification_cde_profile_route_policy_delete`
- `0x18000e531`: `wcm_notification_cde_route_selection_policy_update`
- `0x18000e549`: `wcm_notification_cde_ondemand_connection_complete`
- `0x18000e555`: `wcm_notification_cde_ondemand_disconnection_complete`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall NotificationEngine::QueueCdeEventWorkItem(
        __int64 a1,
        unsigned int a2,
        unsigned __int16 a3,
        int a4,
        void *Src,
        int a6)
{
  unsigned int v6; // esi
  void *v9; // r8
  __m128i v10; // xmm6
  __int64 v11; // rdx
  signed __int32 v12; // eax
  signed __int32 v13; // ett
  int v14; // r8d
  __int16 *v15; // rdx
  volatile signed __int32 *v16; // rbx
  volatile signed __int32 *v17; // xmm6_8
  void *v18; // rdx
  volatile signed __int32 *v19; // xmm6_8
  const wchar_t *v20; // r9
  std::_Ref_count_base *v21; // rcx
  unsigned int WCMNotificationCodeString; // eax
  __int64 v23; // r11
  int v24; // edx
  int v25; // r8d
  char v26; // r10
  SIZE_T dwBytes; // [rsp+28h] [rbp-80h]
  std::_Ref_count_base *v28[2]; // [rsp+40h] [rbp-68h] BYREF
  std::_Ref_count_base *v29[2]; // [rsp+50h] [rbp-58h] BYREF
  __int128 v30; // [rsp+60h] [rbp-48h]
  __int64 v31; // [rsp+70h] [rbp-38h]

  v6 = a3;
  v9 = Src;
  v10 = 0;
  v30 = 0;
  v11 = *((_QWORD *)&xmmword_18013FCC0 + 1);
  if ( *((_QWORD *)&xmmword_18013FCC0 + 1) )
  {
    v12 = *(_DWORD *)(*((_QWORD *)&xmmword_18013FCC0 + 1) + 8LL);
    while ( v12 )
    {
      v13 = v12;
      v12 = _InterlockedCompareExchange((volatile signed __int32 *)(v11 + 8), v12 + 1, v12);
      if ( v13 == v12 )
      {
        v10 = (__m128i)xmmword_18013FCC0;
        v30 = xmmword_18013FCC0;
        break;
      }
    }
  }
  if ( v10.m128i_i64[0] )
  {
    *(_OWORD *)v28 = 0;
    LODWORD(dwBytes) = a6;
    if ( (unsigned int)NotificationEngine::CreateNotification(
                         a1,
                         a2,
                         (unsigned __int16)v6,
                         a4,
                         Src,
                         dwBytes,
                         (__int64)v28) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WCMNotificationCodeString = (unsigned int)GetWCMNotificationCodeString(v6, a2);
        WPP_SF_SDDD(*(_QWORD *)(v23 + 16), v24, v25, WCMNotificationCodeString, a2, v6, v26);
      }
      if ( v28[1] )
        std::_Ref_count_base::_Decref(v28[1]);
      v21 = (std::_Ref_count_base *)_mm_srli_si128(v10, 8).m128i_u64[0];
      if ( v21 )
        std::_Ref_count_base::_Decref(v21);
    }
    else
    {
      v15 = (__int16 *)&WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        if ( (_WORD)v6 == 256 )
        {
          if ( a2 == 65538 )
          {
            v20 = L"wcm_notification_cm_private_power_change";
          }
          else if ( a2 == 65537 )
          {
            v20 = L"wcm_notification_cm_private_nla";
          }
          else
          {
            v15 = &_ImageBase;
            switch ( a2 )
            {
              case 0x10000u:
                v20 = L"wcm_notification_cm_private_begin";
                break;
              case 0x10003u:
                v20 = L"wcm_notification_cm_private_session_change";
                break;
              case 0x10004u:
                v20 = L"wcm_notification_cm_private_csp_state";
                break;
              case 0x10005u:
                v20 = L"wcm_notification_cm_private_grouppolicy_change";
                break;
              case 0x10006u:
                v20 = L"wcm_notification_cm_private_register_state_changed";
                break;
              case 0x10007u:
                v20 = L"wcm_notification_cm_private_system_time_changed";
                break;
              case 0x10008u:
                v20 = L"wcm_notification_cm_private_connected_standby_enter";
                break;
              case 0x10009u:
                v20 = L"wcm_notification_cm_private_connected_standby_exit";
                break;
              case 0x1000Au:
                v20 = L"wcm_notification_cm_private_network_quiet_mode_enter";
                break;
              case 0x1000Bu:
                v20 = L"wcm_notification_cm_private_network_quiet_mode_exit";
                break;
              case 0x1000Cu:
                v20 = L"wcm_notification_cm_private_wifi_limited_connectivity_override";
                break;
              case 0x1000Du:
                v20 = L"wcm_notification_cm_private_power_override";
                break;
              default:
                LODWORD(v15) = (unsigned int)&WPP_GLOBAL_Control;
LABEL_104:
                v20 = L"WCMUnknownNotificationCode";
                break;
            }
          }
        }
        else if ( a2 == 131102 )
        {
          v20 = L"wcm_notification_cde_link_speed_change";
        }
        else if ( a2 == 131090 )
        {
          v20 = L"wcm_notification_cde_signal_strength_change";
        }
        else
        {
          v15 = &_ImageBase;
          switch ( a2 )
          {
            case 0x20000u:
              v20 = L"wcm_notification_cde_private_begin";
              break;
            case 0x20001u:
              v20 = L"wcm_notification_cde_l2_adapter_arrival";
              break;
            case 0x20003u:
              v20 = L"wcm_notification_cde_l2_adapter_removal";
              break;
            case 0x20005u:
              v20 = L"wcm_notification_cde_connection_available";
              break;
            case 0x20006u:
              v20 = L"wcm_notification_cde_connection_unavailable";
              break;
            case 0x20007u:
              v20 = L"wcm_notification_cde_disconnected";
              break;
            case 0x20008u:
              v20 = L"wcm_notification_cde_connected";
              break;
            case 0x20009u:
              v20 = L"wcm_notification_cde_connection_failed";
              break;
            case 0x2000Au:
              v20 = L"wcm_notification_cde_connecting";
              break;
            case 0x2000Bu:
              v20 = L"wcm_notification_cde_disconnecting";
              break;
            case 0x2000Cu:
              v20 = L"wcm_notification_cde_profile_change";
              break;
            case 0x2000Du:
              v20 = L"wcm_notification_cde_connected_standby_entry";
              break;
            case 0x2000Eu:
              v20 = L"wcm_notification_cde_connected_standby_exit";
              break;
            case 0x2000Fu:
              v20 = L"wcm_notification_cde_registered";
              break;
            case 0x20010u:
              v20 = L"wcm_notification_cde_set_radio_state_complete";
              break;
            case 0x20011u:
              v20 = L"wcm_notification_cde_set_radio_state_failed";
              break;
            case 0x20013u:
              v20 = L"wcm_notification_cde_ondemand_adapter_arrival";
              break;
            case 0x20014u:
              v20 = L"wcm_notification_cde_ondemand_adapter_removal";
              break;
            case 0x20015u:
              v20 = L"wcm_notification_cde_ondemand_token_applied";
              break;
            case 0x20016u:
              v20 = L"wcm_notification_cde_l2_available_connection_add";
              break;
            case 0x20017u:
              v20 = L"wcm_notification_cde_l2_available_connection_delete";
              break;
            case 0x20018u:
              v20 = L"wcm_notification_cde_l2_available_connection_property_change";
              break;
            case 0x20019u:
              v20 = L"wcm_notification_cde_l2_uicc_bindings_change";
              break;
            case 0x2001Au:
              v20 = L"wcm_notification_cde_link_degraded";
              break;
            case 0x2001Bu:
              v20 = L"wcm_notification_cde_link_improved";
              break;
            case 0x2001Cu:
              v20 = L"wcm_notification_cde_wifi_roaming_start";
              break;
            case 0x2001Du:
              v20 = L"wcm_notification_cde_wifi_roaming_end";
              break;
            case 0x2001Fu:
              v20 = L"wcm_notification_cde_profile_route_policy_add";
              break;
            case 0x20020u:
              v20 = L"wcm_notification_cde_profile_route_policy_delete";
              break;
            case 0x20021u:
              v20 = L"wcm_notification_cde_route_selection_policy_update";
              break;
            case 0x20022u:
              v20 = L"wcm_notification_cde_terminate_ondemand_connections";
              break;
            case 0x20023u:
              v20 = L"wcm_notification_cde_ondemand_connection_complete";
              break;
            case 0x20024u:
              v20 = L"wcm_notification_cde_ondemand_disconnection_complete";
              break;
            default:
              LODWORD(v15) = (unsigned int)&WPP_GLOBAL_Control;
              goto LABEL_104;
          }
        }
        WPP_SF_SDD_guid_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), (_DWORD)v15, v14, (_DWORD)v20, a2, v6, a1);
      }
      v16 = (volatile signed __int32 *)v28[1];
      if ( v28[1] )
        _InterlockedIncrement((volatile signed __int32 *)v28[1] + 2);
      *(_OWORD *)v29 = *(_OWORD *)v28;
      EnterCriticalSection((LPCRITICAL_SECTION)(v10.m128i_i64[0] + 288));
      v31 = v10.m128i_i64[0] + 288;
      if ( *(_BYTE *)(v10.m128i_i64[0] + 552) )
      {
        if ( v10.m128i_i64[0] != -288 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v10.m128i_i64[0] + 288));
      }
      else
      {
        if ( *(_DWORD *)(v10.m128i_i64[0] + 280) == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__NotificationEngine::QueueCdeEventWorkItem_::_3_::_lambda_1___(
            v10.m128i_i64[0] + 432,
            v29);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__NotificationEngine::QueueCdeEventWorkItem_::_3_::_lambda_1___(
            v10.m128i_i64[0] + 512,
            v29);
        if ( v10.m128i_i64[0] != -288 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v10.m128i_i64[0] + 288));
        _InterlockedIncrement64((volatile signed __int64 *)(v10.m128i_i64[0] + 416));
        SubmitThreadpoolWork(*(PTP_WORK *)(v10.m128i_i64[0] + 408));
      }
      if ( v29[1] )
        std::_Ref_count_base::_Decref(v29[1]);
      if ( v16 )
      {
        if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
          if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        }
      }
      v17 = (volatile signed __int32 *)_mm_srli_si128(v10, 8).m128i_u64[0];
      if ( v17 && _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
  }
  else
  {
    v18 = &WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_bd6cec6e73c931b0798be97f1945a788_Traceguids);
    }
    v19 = (volatile signed __int32 *)_mm_srli_si128(v10, 8).m128i_u64[0];
    if ( v19 )
    {
      if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *, void *, void *))v19)(v19, v18, v9);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
  }
}

```

## disassembly

```asm
0x18000dfc0  mov     [rsp+arg_18], rbx
0x18000dfc5  push    rsi
0x18000dfc6  push    rdi
0x18000dfc7  push    r14
0x18000dfc9  sub     rsp, 90h
0x18000dfd0  movaps  [rsp+0A8h+var_28], xmm6
0x18000dfd8  movzx   esi, r8w
0x18000dfdc  mov     ebx, edx
0x18000dfde  mov     r14, rcx
0x18000dfe1  mov     r8, [rsp+0A8h+arg_20]
0x18000dfe9  xorps   xmm6, xmm6
0x18000dfec  movdqu  [rsp+0A8h+var_48], xmm6
0x18000dff2  mov     rdx, qword ptr cs:xmmword_18013FCC0+8
0x18000dff9  test    rdx, rdx
0x18000dffc  jz      short loc_18000E01C
0x18000dffe  mov     eax, [rdx+8]
0x18000e001  test    eax, eax
0x18000e003  jz      short loc_18000E01C
0x18000e005  lea     ecx, [rax+1]
0x18000e008  lock cmpxchg [rdx+8], ecx
0x18000e00d  jnz     short loc_18000E001
0x18000e00f  movups  xmm6, cs:xmmword_18013FCC0
0x18000e016  movdqu  [rsp+0A8h+var_48], xmm6
0x18000e01c  movq    rdi, xmm6
0x18000e021  test    rdi, rdi
0x18000e024  jz      loc_18000E1B3
0x18000e02a  xorps   xmm1, xmm1
0x18000e02d  movdqa  xmmword ptr [rsp+0A8h+var_68], xmm1
0x18000e033  lea     rax, [rsp+0A8h+var_68]
0x18000e038  mov     [rsp+0A8h+var_78], rax; __int64
0x18000e03d  mov     eax, dword ptr [rsp+0A8h+arg_28]
0x18000e044  mov     dword ptr [rsp+0A8h+dwBytes], eax; dwBytes
0x18000e048  mov     [rsp+0A8h+Src], r8; Src
0x18000e04d  movzx   r8d, si; int
0x18000e051  mov     edx, ebx; int
0x18000e053  mov     rcx, r14; int
0x18000e056  call    ?CreateNotification@NotificationEngine@@SAKAEBU_GUID@@KGW4_WCM_MEDIA_TYPE@@PEBXKAEAV?$shared_ptr@U_WCM_NOTIFICATION_DATA@@@std@@@Z; NotificationEngine::CreateNotification(_GUID const &,ulong,ushort,_WCM_MEDIA_TYPE,void const *,ulong,std::shared_ptr<_WCM_NOTIFICATION_DATA> &)
0x18000e05b  mov     r10d, eax
0x18000e05e  test    eax, eax
0x18000e060  jnz     loc_18000E351
0x18000e066  lea     rdx, WPP_GLOBAL_Control
0x18000e06d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e074  cmp     rcx, rdx
0x18000e077  jz      short loc_18000E089
0x18000e079  cmp     byte ptr [rcx+19h], 4
0x18000e07d  jb      short loc_18000E089
0x18000e07f  test    byte ptr [rcx+1Ch], 1
0x18000e083  jnz     loc_18000E214
0x18000e089  mov     rbx, [rsp+0A8h+var_68+8]
0x18000e08e  test    rbx, rbx
0x18000e091  jz      short loc_18000E097
0x18000e093  lock inc dword ptr [rbx+8]
0x18000e097  movaps  xmm0, xmmword ptr [rsp+0A8h+var_68]
0x18000e09c  movdqa  xmmword ptr [rsp+0A8h+var_58], xmm0
0x18000e0a2  lea     rsi, [rdi+120h]
0x18000e0a9  mov     rcx, rsi; lpCriticalSection
0x18000e0ac  call    cs:__imp_EnterCriticalSection
0x18000e0b2  mov     [rsp+0A8h+var_38], rsi
0x18000e0b7  lea     rcx, [rdi+1B0h]
0x18000e0be  cmp     byte ptr [rcx+78h], 0
0x18000e0c2  jnz     loc_18000E33A
0x18000e0c8  lea     rdx, [rsp+0A8h+var_58]
0x18000e0cd  cmp     dword ptr [rdi+118h], 1
0x18000e0d4  jnz     loc_18000E56D
0x18000e0da  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__NotificationEngine__QueueCdeEventWorkItem____3____lambda_1___
0x18000e0df  nop
0x18000e0e0  test    rsi, rsi
0x18000e0e3  jz      short loc_18000E0EE
0x18000e0e5  mov     rcx, rsi; lpCriticalSection
0x18000e0e8  call    cs:__imp_LeaveCriticalSection
0x18000e0ee  lock inc qword ptr [rdi+1A0h]
0x18000e0f6  mov     rcx, [rdi+198h]; pwk
0x18000e0fd  call    cs:__imp_SubmitThreadpoolWork
0x18000e103  nop
0x18000e104  mov     rcx, [rsp+0A8h+var_58+8]; this
0x18000e109  test    rcx, rcx
0x18000e10c  jz      short loc_18000E114
0x18000e10e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000e113  nop
0x18000e114  mov     edi, 0FFFFFFFFh
0x18000e119  test    rbx, rbx
0x18000e11c  jz      short loc_18000E154
0x18000e11e  mov     eax, edi
0x18000e120  lock xadd [rbx+8], eax
0x18000e125  cmp     eax, 1
0x18000e128  jnz     short loc_18000E154
0x18000e12a  mov     rax, [rbx]
0x18000e12d  mov     rcx, rbx
0x18000e130  mov     rax, [rax]
0x18000e133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e138  mov     eax, edi
0x18000e13a  lock xadd [rbx+0Ch], eax
0x18000e13f  cmp     eax, 1
0x18000e142  jnz     short loc_18000E154
0x18000e144  mov     rax, [rbx]
0x18000e147  mov     rcx, rbx
0x18000e14a  mov     rax, [rax+8]
0x18000e14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e153  nop
0x18000e154  psrldq  xmm6, 8
0x18000e159  movq    rbx, xmm6
0x18000e15e  test    rbx, rbx
0x18000e161  jz      short loc_18000E197
0x18000e163  mov     eax, edi
0x18000e165  lock xadd [rbx+8], eax
0x18000e16a  cmp     eax, 1
0x18000e16d  jnz     short loc_18000E197
0x18000e16f  mov     rax, [rbx]
0x18000e172  mov     rcx, rbx
0x18000e175  mov     rax, [rax]
0x18000e178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e17d  lock xadd [rbx+0Ch], edi
0x18000e182  cmp     edi, 1
0x18000e185  jnz     short loc_18000E197
0x18000e187  mov     rax, [rbx]
0x18000e18a  mov     rcx, rbx
0x18000e18d  mov     rax, [rax+8]
0x18000e191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e196  nop
0x18000e197  mov     rbx, [rsp+0A8h+arg_18]
0x18000e19f  movaps  xmm6, [rsp+0A8h+var_28]
0x18000e1a7  add     rsp, 90h
0x18000e1ae  pop     r14
0x18000e1b0  pop     rdi
0x18000e1b1  pop     rsi
0x18000e1b2  retn
0x18000e1b3  lea     rdx, WPP_GLOBAL_Control
0x18000e1ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1c1  cmp     rcx, rdx
0x18000e1c4  jnz     loc_18000E57B
0x18000e1ca  psrldq  xmm6, 8
0x18000e1cf  movq    rbx, xmm6
0x18000e1d4  test    rbx, rbx
0x18000e1d7  jz      short loc_18000E212
0x18000e1d9  mov     edi, 0FFFFFFFFh
0x18000e1de  mov     eax, edi
0x18000e1e0  lock xadd [rbx+8], eax
0x18000e1e5  cmp     eax, 1
0x18000e1e8  jnz     short loc_18000E212
0x18000e1ea  mov     rax, [rbx]
0x18000e1ed  mov     rcx, rbx
0x18000e1f0  mov     rax, [rax]
0x18000e1f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1f8  lock xadd [rbx+0Ch], edi
0x18000e1fd  cmp     edi, 1
0x18000e200  jnz     short loc_18000E212
0x18000e202  mov     rax, [rbx]
0x18000e205  mov     rcx, rbx
0x18000e208  mov     rax, [rax+8]
0x18000e20c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e211  nop
0x18000e212  jmp     short loc_18000E197
0x18000e214  mov     eax, 100h
0x18000e219  cmp     si, ax
0x18000e21c  jz      short loc_18000E259
0x18000e21e  cmp     ebx, 2001Eh
0x18000e224  jnz     short loc_18000E248
0x18000e226  lea     r9, aWcmNotificatio_35; "wcm_notification_cde_link_speed_change"
0x18000e22d  mov     [rsp+0A8h+var_78], r14
0x18000e232  mov     dword ptr [rsp+0A8h+dwBytes], esi
0x18000e236  mov     dword ptr [rsp+0A8h+Src], ebx
0x18000e23a  mov     rcx, [rcx+10h]
0x18000e23e  call    WPP_SF_SDD_guid_
0x18000e243  jmp     loc_18000E089
0x18000e248  cmp     ebx, 20012h
0x18000e24e  jnz     short loc_18000E2A6
0x18000e250  lea     r9, aWcmNotificatio_9; "wcm_notification_cde_signal_strength_ch"...
0x18000e257  jmp     short loc_18000E22D
0x18000e259  cmp     ebx, 10002h
0x18000e25f  jnz     short loc_18000E26A
0x18000e261  lea     r9, aWcmNotificatio_0; "wcm_notification_cm_private_power_chang"...
0x18000e268  jmp     short loc_18000E22D
0x18000e26a  cmp     ebx, 10001h
0x18000e270  jnz     short loc_18000E27B
0x18000e272  lea     r9, aWcmNotificatio_26; "wcm_notification_cm_private_nla"
0x18000e279  jmp     short loc_18000E22D
0x18000e27b  lea     eax, [rbx-10000h]; switch 14 cases
0x18000e281  cmp     eax, 0Dh
0x18000e284  ja      def_18000E29B; jumptable 000000018000E29B default case, cases 65537,65538
0x18000e28a  lea     rdx, __ImageBase
0x18000e291  mov     eax, ds:(jpt_18000E29B - 180000000h)[rdx+rax*4]
0x18000e298  add     rax, rdx
0x18000e29b  jmp     rax; switch jump
0x18000e29d  lea     r9, aWcmNotificatio_34; jumptable 000000018000E29B case 65547
0x18000e2a4  jmp     short loc_18000E22D
0x18000e2a6  lea     eax, [rbx-20000h]; switch 37 cases
0x18000e2ac  cmp     eax, 24h
0x18000e2af  ja      def_18000E29B; jumptable 000000018000E29B default case, cases 65537,65538
0x18000e2b5  lea     rdx, __ImageBase
0x18000e2bc  mov     eax, ds:(jpt_18000E2C6 - 180000000h)[rdx+rax*4]
0x18000e2c3  add     rax, rdx
0x18000e2c6  jmp     rax; switch jump
0x18000e2c8  lea     r9, aWcmNotificatio_2; jumptable 000000018000E2C6 case 131101
0x18000e2cf  jmp     loc_18000E22D
0x18000e2d4  lea     r9, aWcmNotificatio; jumptable 000000018000E29B case 65544
0x18000e2db  jmp     loc_18000E22D
0x18000e2e0  lea     r9, aWcmNotificatio_7; jumptable 000000018000E29B case 65545
0x18000e2e7  jmp     loc_18000E22D
0x18000e2ec  lea     r9, aWcmNotificatio_31; jumptable 000000018000E2C6 case 131100
0x18000e2f3  jmp     loc_18000E22D
0x18000e2f8  lea     r9, aWcmNotificatio_18; jumptable 000000018000E2C6 case 131079
0x18000e2ff  jmp     loc_18000E22D
0x18000e304  lea     r9, aWcmNotificatio_13; jumptable 000000018000E2C6 case 131080
0x18000e30b  jmp     loc_18000E22D
0x18000e310  mov     rcx, [rsp+0A8h+var_68+8]; this
0x18000e315  test    rcx, rcx
0x18000e318  jz      short loc_18000E320
0x18000e31a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000e31f  nop
0x18000e320  psrldq  xmm6, 8
0x18000e325  movq    rcx, xmm6; this
0x18000e32a  test    rcx, rcx
0x18000e32d  jz      short loc_18000E335
0x18000e32f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000e334  nop
0x18000e335  jmp     loc_18000E197
0x18000e33a  test    rsi, rsi
0x18000e33d  jz      loc_18000E104
0x18000e343  mov     rcx, rsi; lpCriticalSection
0x18000e346  call    cs:__imp_LeaveCriticalSection
0x18000e34c  jmp     loc_18000E104
0x18000e351  lea     rdx, WPP_GLOBAL_Control
0x18000e358  mov     r11, cs:WPP_GLOBAL_Control
0x18000e35f  cmp     r11, rdx
0x18000e362  jz      short loc_18000E310
0x18000e364  cmp     byte ptr [r11+19h], 2
0x18000e369  jb      short loc_18000E310
0x18000e36b  test    byte ptr [r11+1Ch], 1
0x18000e370  jz      short loc_18000E310
0x18000e372  mov     edx, ebx; unsigned int
0x18000e374  mov     ecx, esi; unsigned int
0x18000e376  call    ?GetWCMNotificationCodeString@@YAPEBGKK@Z; GetWCMNotificationCodeString(ulong,ulong)
0x18000e37b  mov     r9, rax
0x18000e37e  mov     dword ptr [rsp+0A8h+var_78], r10d
0x18000e383  mov     dword ptr [rsp+0A8h+dwBytes], esi
0x18000e387  mov     dword ptr [rsp+0A8h+Src], ebx
0x18000e38b  mov     rcx, [r11+10h]
0x18000e38f  call    WPP_SF_SDDD
0x18000e394  jmp     loc_18000E310
0x18000e399  lea     r9, aWcmNotificatio_43; jumptable 000000018000E29B case 65536
0x18000e3a0  jmp     loc_18000E22D
0x18000e3a5  lea     r9, aWcmNotificatio_6; jumptable 000000018000E29B case 65539
0x18000e3ac  jmp     loc_18000E22D
0x18000e3b1  lea     r9, aWcmNotificatio_1; jumptable 000000018000E29B case 65540
0x18000e3b8  jmp     loc_18000E22D
0x18000e3bd  lea     r9, aWcmNotificatio_23; jumptable 000000018000E29B case 65541
0x18000e3c4  jmp     loc_18000E22D
0x18000e3c9  lea     r9, aWcmNotificatio_10; jumptable 000000018000E29B case 65542
0x18000e3d0  jmp     loc_18000E22D
0x18000e3d5  lea     r9, aWcmNotificatio_21; jumptable 000000018000E29B case 65543
0x18000e3dc  jmp     loc_18000E22D
0x18000e3e1  lea     r9, aWcmNotificatio_42; jumptable 000000018000E29B case 65546
0x18000e3e8  jmp     loc_18000E22D
0x18000e3ed  lea     r9, aWcmNotificatio_25; jumptable 000000018000E29B case 65548
0x18000e3f4  jmp     loc_18000E22D
0x18000e3f9  lea     r9, aWcmNotificatio_4; jumptable 000000018000E29B case 65549
0x18000e400  jmp     loc_18000E22D
0x18000e405  lea     r9, aWcmNotificatio_28; jumptable 000000018000E2C6 case 131072
0x18000e40c  jmp     loc_18000E22D
0x18000e411  lea     r9, aWcmNotificatio_8; jumptable 000000018000E2C6 case 131073
0x18000e418  jmp     loc_18000E22D
0x18000e41d  lea     r9, aWcmNotificatio_38; jumptable 000000018000E2C6 case 131075
0x18000e424  jmp     loc_18000E22D
0x18000e429  lea     r9, aWcmNotificatio_47; jumptable 000000018000E2C6 case 131077
0x18000e430  jmp     loc_18000E22D
0x18000e435  lea     r9, aWcmNotificatio_30; jumptable 000000018000E2C6 case 131078
0x18000e43c  jmp     loc_18000E22D
0x18000e441  lea     r9, aWcmNotificatio_27; jumptable 000000018000E2C6 case 131081
0x18000e448  jmp     loc_18000E22D
0x18000e44d  lea     r9, aWcmNotificatio_41; jumptable 000000018000E2C6 case 131082
0x18000e454  jmp     loc_18000E22D
0x18000e459  lea     r9, aWcmNotificatio_37; jumptable 000000018000E2C6 case 131083
0x18000e460  jmp     loc_18000E22D
0x18000e465  lea     r9, aWcmNotificatio_24; jumptable 000000018000E2C6 case 131084
0x18000e46c  jmp     loc_18000E22D
0x18000e471  lea     r9, aWcmNotificatio_22; jumptable 000000018000E2C6 case 131085
0x18000e478  jmp     loc_18000E22D
0x18000e47d  lea     r9, aWcmNotificatio_32; jumptable 000000018000E2C6 case 131086
0x18000e484  jmp     loc_18000E22D
0x18000e489  lea     r9, aWcmNotificatio_17; jumptable 000000018000E2C6 case 131087
0x18000e490  jmp     loc_18000E22D
0x18000e495  lea     r9, aWcmNotificatio_33; jumptable 000000018000E2C6 case 131088
0x18000e49c  jmp     loc_18000E22D
0x18000e4a1  lea     r9, aWcmNotificatio_40; jumptable 000000018000E2C6 case 131089
0x18000e4a8  jmp     loc_18000E22D
0x18000e4ad  lea     r9, aWcmNotificatio_11; jumptable 000000018000E2C6 case 131091
0x18000e4b4  jmp     loc_18000E22D
0x18000e4b9  lea     r9, aWcmNotificatio_12; jumptable 000000018000E2C6 case 131092
0x18000e4c0  jmp     loc_18000E22D
0x18000e4c5  lea     r9, aWcmNotificatio_14; jumptable 000000018000E2C6 case 131093
0x18000e4cc  jmp     loc_18000E22D
0x18000e4d1  lea     r9, aWcmNotificatio_5; jumptable 000000018000E2C6 case 131094
0x18000e4d8  jmp     loc_18000E22D
0x18000e4dd  lea     r9, aWcmNotificatio_46; jumptable 000000018000E2C6 case 131095
0x18000e4e4  jmp     loc_18000E22D
0x18000e4e9  lea     r9, aWcmNotificatio_15; jumptable 000000018000E2C6 case 131096
0x18000e4f0  jmp     loc_18000E22D
0x18000e4f5  lea     r9, aWcmNotificatio_44; jumptable 000000018000E2C6 case 131097
0x18000e4fc  jmp     loc_18000E22D
0x18000e501  lea     r9, aWcmNotificatio_39; jumptable 000000018000E2C6 case 131098
  ... truncated ...
```
