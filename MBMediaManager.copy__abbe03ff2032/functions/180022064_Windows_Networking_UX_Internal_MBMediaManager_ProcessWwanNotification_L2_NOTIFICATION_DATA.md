# Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification(_L2_NOTIFICATION_DATA *)

- ea: `0x180022064`
- end: `0x1800227eb`
- name: `?_ProcessWwanNotification@MBMediaManager@Internal@UX@Networking@Windows@@AEAAXPEAU_L2_NOTIFICATION_DATA@@@Z`
- size: `1927`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::MBMediaManager *__hidden this, struct _L2_NOTIFICATION_DATA *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180033030`

## callees

- `0x180002150`
- `0x180003e48`
- `0x180008c84`
- `0x180009150`
- `0x18000ad20`
- `0x18000bde0`
- `0x180022064`
- `0x180022a1c`
- `0x180022e9c`
- `0x18002cd20`
- `0x180033070`
- `0x1800331c8`
- `0x180059010`

## string_xrefs

- `0x1800225ff`: `WwanMsmEventTypeProfileIStreamDeleted`
- `0x1800223c1`: `WwanMsmEventTypeProfileIStreamCreated`
- `0x1800224ae`: `WwanMsmEventTypeProfileIStreamUpdated`
- `0x180022252`: `WwanMsmEventTypeGetPinInfoComplete`
- `0x18002235c`: `WwanMsmEventTypeGetPinListComplete`
- `0x180022483`: `WwanMsmEventTypePinActionComplete`
- `0x1800225f1`: `WwanMsmEventTypeConnectionIStreamCreated`
- `0x1800225c9`: `WwanMsmEventTypeConnectionIStreamUpdated`
- `0x18002243f`: `WwanMsmEventTypeSetRadioStateComplete`
- `0x18002234e`: `WwanMsmEventTypeScanCompleted`
- `0x18002259e`: `WwanMsmEventTypeDMConfigProfileUpdate`
- `0x1800222d0`: `WwanMsmEventTypeConnectComplete`
- `0x18002269a`: `WwanMsmEventTypeProtectIMSIChanged`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification(
        Windows::Networking::UX::Internal::MBMediaManager *this,
        struct _L2_NOTIFICATION_DATA *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rdx
  int MBCategory; // edi
  __int64 v8; // rax
  __int64 v9; // rax
  DWORD NotificationCode; // r9d
  __int64 v11; // [rsp+30h] [rbp-29h] BYREF
  char v12; // [rsp+38h] [rbp-21h]
  _BYTE v13[8]; // [rsp+40h] [rbp-19h] BYREF
  char v14[40]; // [rsp+48h] [rbp-11h] BYREF
  __int128 v15; // [rsp+70h] [rbp+17h] BYREF
  _BYTE v16[19]; // [rsp+80h] [rbp+27h]

  wil::EnterCriticalSection(v13, (char *)this + 104);
  if ( a2->NotificationCode != 1 )
  {
    if ( !a2->NotificationCode )
    {
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
        404,
        "WwanPnpEventTypeInterfaceArrival");
      LOBYTE(v5) = v12;
      Windows::Networking::UX::Internal::MBMediaManager::_ProcessInterfaceArrival(this, v5, a2);
      goto LABEL_86;
    }
    v11 = 0;
    if ( *((_QWORD *)this + 19) == -1 )
    {
      MBSettingUXLogging::Warn(
        "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
        415,
        "_hWwanNotificationHandle found null while trying to process WWAN RPC");
LABEL_85:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
      goto LABEL_86;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
    MBCategory = Windows::Networking::UX::Internal::MBMediaManager::_GetMBCategory(this, v6, &a2->InterfaceGuid, &v11);
    if ( MBCategory == -2147023728 )
    {
      v8 = MbLoggingHelperGuidToString(v14);
      v15 = *(_OWORD *)v8;
      *(_OWORD *)v16 = *(_OWORD *)(v8 + 16);
      *(_DWORD *)&v16[15] = *(_DWORD *)(v8 + 31);
      MBSettingUXLogging::Warn(
        "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
        429,
        "Notification for unrecognized interface. Ignoring notification. NotificationCode=%d, pNotification->InterfaceGuid=%hs",
        a2->NotificationCode,
        (const char *)&v15);
      goto LABEL_85;
    }
    if ( MBCategory < 0 )
    {
      v9 = MbLoggingHelperGuidToString(v14);
      v15 = *(_OWORD *)v9;
      *(_OWORD *)v16 = *(_OWORD *)(v9 + 16);
      *(_DWORD *)&v16[15] = *(_DWORD *)(v9 + 31);
      MBSettingUXLogging::Error(
        "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
        0x1B7u,
        "_GetMBCategory failed. NotificationCode=%d, pNotification->InterfaceGuid=%hs, HRESULT=0x%x",
        a2->NotificationCode,
        (const char *)&v15,
        MBCategory);
      goto LABEL_85;
    }
    NotificationCode = a2->NotificationCode;
    if ( NotificationCode > 0x2E )
    {
      if ( NotificationCode > 0x55 )
      {
        switch ( NotificationCode )
        {
          case 'V':
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
              532,
              "WwanMsmEventTypeEnterpriseAPNParams");
            (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 56LL))(v11, a2);
            goto LABEL_85;
          case 'Y':
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
              520,
              "WwanMsmEventTypeDisallowAutoConnectChanged");
            (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 136LL))(v11, a2);
            goto LABEL_85;
          case 'Z':
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
              561,
              "WwanMsmEventTypeManualConnectSessionStateChanged");
            (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 184LL))(v11, a2);
            goto LABEL_85;
          case '[':
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
              540,
              "WwanMsmEventTypeProvisioningStateChanged");
            (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 144LL))(v11, a2);
            goto LABEL_85;
          case '_':
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
              544,
              "WwanMsmEventTypeMultiSIMInfo");
            (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 96LL))(v11, a2);
            goto LABEL_85;
          case '`':
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
              548,
              "WwanMsmEventTypeMultiSIMSlotMapping");
            (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 104LL))(v11, a2);
            goto LABEL_85;
          case 'x':
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
              573,
              "WwanMsmEventTypeProtectIMSIChanged");
            (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 240LL))(v11, a2);
            goto LABEL_85;
        }
        goto LABEL_77;
      }
      switch ( NotificationCode )
      {
        case 'U':
          MBSettingUXLogging::Info(
            "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
            528,
            "WwanMsmEventTypeHighestConnCategory");
          goto LABEL_85;
        case '/':
          MBSettingUXLogging::Info(
            "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
            454,
            "WwanMsmEventTypeProfileIStreamDeleted");
          (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 168LL))(v11, a2);
          goto LABEL_85;
        case '0':
          MBSettingUXLogging::Info(
            "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
            488,
            "WwanMsmEventTypeConnectionIStreamCreated");
          break;
        case '1':
          MBSettingUXLogging::Info(
            "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
            492,
            "WwanMsmEventTypeConnectionIStreamUpdated");
          break;
        case ';':
          MBSettingUXLogging::Info(
            "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
            552,
            "WwanMsmEventTypeDMConfigProfileUpdate");
          (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 176LL))(v11, a2);
          goto LABEL_85;
        case 'C':
          MBSettingUXLogging::Info(
            "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
            558,
            "WwanMsmEventTypeUiccBindingsChanged - Ignore notification, RIL only");
          goto LABEL_85;
        case 'H':
          MBSettingUXLogging::Info(
            "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
            516,
            "WwanMsmEventTypeDataEnablementChange");
          (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 128LL))(v11, a2);
          goto LABEL_85;
        case 'I':
          MBSettingUXLogging::Info(
            "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
            524,
            "WwanMsmEventTypeRoamingPolicyChange");
          (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 120LL))(v11, a2);
          goto LABEL_85;
        case 'N':
          MBSettingUXLogging::Info(
            "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
            536,
            "WwanMsmEventTypeNetworkLTEAttachInfo");
          (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 64LL))(v11, a2);
          goto LABEL_85;
        default:
          goto LABEL_77;
      }
      (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 88LL))(v11, a2);
      goto LABEL_85;
    }
    if ( NotificationCode != 46 )
    {
      if ( NotificationCode <= 0x15 )
      {
        switch ( NotificationCode )
        {
          case 0x15u:
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
              480,
              "WwanMsmEventTypeGetPinListComplete");
            (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 224LL))(v11, a2);
            goto LABEL_85;
          case 2u:
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
              508,
              "WwanMsmEventTypeScanCompleted");
            break;
          case 3u:
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
              512,
              "WwanMsmEventTypeScanFailed");
            break;
          case 6u:
          case 7u:
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
              472,
              "WwanMsmEventTypeRegistered/WwanMsmEventTypeDeregistered");
            (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 112LL))(v11, a2);
            goto LABEL_85;
          case 0xEu:
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
              565,
              "WwanMsmEventTypeConnectComplete");
            (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 192LL))(v11, a2);
            goto LABEL_85;
          case 0xFu:
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
              569,
              "WwanMsmEventTypeConnectFailed");
            (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 200LL))(v11, a2);
            goto LABEL_85;
          case 0x12u:
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
              466,
              "WwanMsmEventTypeSubscriberInfo");
            (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 48LL))(v11, a2);
            goto LABEL_85;
          case 0x13u:
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
              476,
              "WwanMsmEventTypeGetPinInfoComplete");
            (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 216LL))(v11, a2);
            goto LABEL_85;
          default:
LABEL_77:
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
              580,
              "Ignore notification. NotificationCode=%d",
              NotificationCode);
            goto LABEL_85;
        }
        (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 152LL))(v11, a2);
        goto LABEL_85;
      }
      switch ( NotificationCode )
      {
        case 0x17u:
          MBSettingUXLogging::Info(
            "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
            484,
            "WwanMsmEventTypePinActionComplete");
          (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 232LL))(v11, a2);
          goto LABEL_85;
        case 0x19u:
          MBSettingUXLogging::Info(
            "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
            446,
            "WwanMsmEventTypeSignalState");
          (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 80LL))(v11, a2);
          goto LABEL_85;
        case 0x1Cu:
          MBSettingUXLogging::Info(
            "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
            500,
            "WwanMsmEventTypeRadioState");
          break;
        case 0x1Du:
          MBSettingUXLogging::Info(
            "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
            496,
            "WwanMsmEventTypeSetRadioStateComplete");
          break;
        case 0x1Eu:
          MBSettingUXLogging::Info(
            "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
            504,
            "WwanMsmEventTypeSetRadioStateFailed");
          break;
        case 0x2Cu:
          MBSettingUXLogging::Info(
            "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
            450,
            "WwanMsmEventTypeIStreamChanged");
          (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 208LL))(v11, a2);
          goto LABEL_85;
        case 0x2Du:
          MBSettingUXLogging::Info(
            "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
            458,
            "WwanMsmEventTypeProfileIStreamCreated");
LABEL_40:
          (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 160LL))(v11, a2);
          goto LABEL_85;
        default:
          goto LABEL_77;
      }
      (*(void (__fastcall **)(__int64, struct _L2_NOTIFICATION_DATA *))(*(_QWORD *)v11 + 72LL))(v11, a2);
      goto LABEL_85;
    }
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
      462,
      "WwanMsmEventTypeProfileIStreamUpdated");
    goto LABEL_40;
  }
  MBSettingUXLogging::Info(
    "Windows::Networking::UX::Internal::MBMediaManager::_ProcessWwanNotification",
    397,
    "WwanPnpEventTypeInterfaceRemoval");
  Windows::Networking::UX::Internal::MBMediaManager::_ProcessInterfaceRemoval(this, v4, a2);
LABEL_86:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v13);
}

```

## disassembly

```asm
0x180022064  mov     [rsp-8+arg_10], rbx
0x180022069  push    rbp
0x18002206a  push    rsi
0x18002206b  push    rdi
0x18002206c  lea     rbp, [rsp-47h]
0x180022071  sub     rsp, 0A0h
0x180022078  mov     rax, cs:__security_cookie
0x18002207f  xor     rax, rsp
0x180022082  mov     [rbp+57h+var_18], rax
0x180022086  mov     rbx, rdx
0x180022089  mov     rdi, rcx
0x18002208c  lea     rdx, [rcx+68h]
0x180022090  lea     rcx, [rbp+57h+var_70]
0x180022094  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180022099  nop
0x18002209a  cmp     dword ptr [rbx+4], 1
0x18002209e  jnz     short loc_1800220C8
0x1800220a0  lea     r8, aWwanpnpeventty; "WwanPnpEventTypeInterfaceRemoval"
0x1800220a7  mov     edx, 18Dh; unsigned int
0x1800220ac  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x1800220b3  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800220b8  mov     r8, rbx
0x1800220bb  mov     rcx, rdi
0x1800220be  call    ?_ProcessInterfaceRemoval@MBMediaManager@Internal@UX@Networking@Windows@@AEAAXUwrite_lock_required@wil@@PEAU_L2_NOTIFICATION_DATA@@@Z; Windows::Networking::UX::Internal::MBMediaManager::_ProcessInterfaceRemoval(wil::write_lock_required,_L2_NOTIFICATION_DATA *)
0x1800220c3  jmp     loc_1800227C3
0x1800220c8  cmp     dword ptr [rbx+4], 0
0x1800220cc  jnz     short loc_1800220F9
0x1800220ce  lea     r8, aWwanpnpeventty_0; "WwanPnpEventTypeInterfaceArrival"
0x1800220d5  mov     edx, 194h; unsigned int
0x1800220da  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x1800220e1  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800220e6  mov     r8, rbx
0x1800220e9  mov     dl, [rbp+57h+var_78]
0x1800220ec  mov     rcx, rdi
0x1800220ef  call    ?_ProcessInterfaceArrival@MBMediaManager@Internal@UX@Networking@Windows@@AEAAXUwrite_lock_required@wil@@PEAU_L2_NOTIFICATION_DATA@@@Z; Windows::Networking::UX::Internal::MBMediaManager::_ProcessInterfaceArrival(wil::write_lock_required,_L2_NOTIFICATION_DATA *)
0x1800220f4  jmp     loc_1800227C3
0x1800220f9  mov     [rbp+57h+var_80], 0
0x180022101  cmp     qword ptr [rdi+98h], 0FFFFFFFFFFFFFFFFh
0x180022109  jnz     short loc_180022128
0x18002210b  lea     r8, aHwwannotificat; "_hWwanNotificationHandle found null whi"...
0x180022112  mov     edx, 19Fh; unsigned int
0x180022117  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x18002211e  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x180022123  jmp     loc_1800227B9
0x180022128  lea     rcx, [rbp+57h+var_80]
0x18002212c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022131  lea     rsi, [rbx+8]
0x180022135  lea     r9, [rbp+57h+var_80]
0x180022139  mov     r8, rsi
0x18002213c  mov     rcx, rdi
0x18002213f  call    ?_GetMBCategory@MBMediaManager@Internal@UX@Networking@Windows@@AEAAJUread_lock_required@wil@@AEBU_GUID@@PEAPEAUIMBCategory@2345@@Z; Windows::Networking::UX::Internal::MBMediaManager::_GetMBCategory(wil::read_lock_required,_GUID const &,Windows::Networking::UX::Internal::IMBCategory * *)
0x180022144  mov     edi, eax
0x180022146  cmp     eax, 80070490h
0x18002214b  jnz     short loc_180022198
0x18002214d  mov     rdx, rsi
0x180022150  lea     rcx, [rbp+57h+var_68]; char *
0x180022154  call    ?MbLoggingHelperGuidToString@@YA?AV?$array@D$0CD@@std@@AEBU_GUID@@@Z; MbLoggingHelperGuidToString(_GUID const &)
0x180022159  movups  xmm0, xmmword ptr [rax]
0x18002215c  movups  [rbp+57h+var_40], xmm0
0x180022160  movups  xmm1, xmmword ptr [rax+10h]
0x180022164  movups  xmmword ptr [rbp+57h+var_30], xmm1
0x180022168  mov     eax, [rax+1Fh]
0x18002216b  mov     dword ptr [rbp+57h+var_30+0Fh], eax
0x18002216e  lea     rax, [rbp+57h+var_40]
0x180022172  mov     [rsp+0B0h+var_90], rax
0x180022177  mov     r9d, [rbx+4]
0x18002217b  lea     r8, aNotificationFo; "Notification for unrecognized interface"...
0x180022182  mov     edx, 1ADh; unsigned int
0x180022187  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x18002218e  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x180022193  jmp     loc_1800227B9
0x180022198  test    edi, edi
0x18002219a  jns     short loc_1800221EB
0x18002219c  mov     rdx, rsi
0x18002219f  lea     rcx, [rbp+57h+var_68]; char *
0x1800221a3  call    ?MbLoggingHelperGuidToString@@YA?AV?$array@D$0CD@@std@@AEBU_GUID@@@Z; MbLoggingHelperGuidToString(_GUID const &)
0x1800221a8  movups  xmm0, xmmword ptr [rax]
0x1800221ab  movups  [rbp+57h+var_40], xmm0
0x1800221af  movups  xmm1, xmmword ptr [rax+10h]
0x1800221b3  movups  xmmword ptr [rbp+57h+var_30], xmm1
0x1800221b7  mov     eax, [rax+1Fh]
0x1800221ba  mov     dword ptr [rbp+57h+var_30+0Fh], eax
0x1800221bd  mov     [rsp+0B0h+var_88], edi
0x1800221c1  lea     rax, [rbp+57h+var_40]
0x1800221c5  mov     [rsp+0B0h+var_90], rax
0x1800221ca  mov     r9d, [rbx+4]
0x1800221ce  lea     r8, aGetmbcategoryF; "_GetMBCategory failed. NotificationCode"...
0x1800221d5  mov     edx, 1B7h; unsigned int
0x1800221da  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x1800221e1  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x1800221e6  jmp     loc_1800227B9
0x1800221eb  mov     r9d, [rbx+4]
0x1800221ef  cmp     r9d, 2Eh ; '.'
0x1800221f3  ja      loc_1800224BF
0x1800221f9  jz      loc_1800224AE
0x1800221ff  cmp     r9d, 15h
0x180022203  ja      loc_180022387
0x180022209  jz      loc_18002235C
0x18002220f  mov     eax, r9d
0x180022212  sub     eax, 2
0x180022215  jz      loc_18002234E
0x18002221b  sub     eax, 1
0x18002221e  jz      loc_180022323
0x180022224  sub     eax, 3
0x180022227  jz      loc_1800222FB
0x18002222d  sub     eax, 1
0x180022230  jz      loc_1800222FB
0x180022236  sub     eax, 7
0x180022239  jz      loc_1800222D0
0x18002223f  sub     eax, 1
0x180022242  jz      short loc_1800222A5
0x180022244  sub     eax, 3
0x180022247  jz      short loc_18002227D
0x180022249  cmp     eax, 1
0x18002224c  jnz     loc_18002267D
0x180022252  lea     r8, aWwanmsmeventty_19; "WwanMsmEventTypeGetPinInfoComplete"
0x180022259  mov     edx, 1DCh; unsigned int
0x18002225e  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x180022265  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18002226a  mov     rcx, [rbp+57h+var_80]
0x18002226e  mov     rax, [rcx]
0x180022271  mov     rax, [rax+0D8h]
0x180022278  jmp     loc_1800227B0
0x18002227d  lea     r8, aWwanmsmeventty_22; "WwanMsmEventTypeSubscriberInfo"
0x180022284  mov     edx, 1D2h; unsigned int
0x180022289  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x180022290  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180022295  mov     rcx, [rbp+57h+var_80]
0x180022299  mov     rax, [rcx]
0x18002229c  mov     rax, [rax+30h]
0x1800222a0  jmp     loc_1800227B0
0x1800222a5  lea     r8, aWwanmsmeventty_6; "WwanMsmEventTypeConnectFailed"
0x1800222ac  mov     edx, 239h; unsigned int
0x1800222b1  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x1800222b8  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800222bd  mov     rcx, [rbp+57h+var_80]
0x1800222c1  mov     rax, [rcx]
0x1800222c4  mov     rax, [rax+0C8h]
0x1800222cb  jmp     loc_1800227B0
0x1800222d0  lea     r8, aWwanmsmeventty_23; "WwanMsmEventTypeConnectComplete"
0x1800222d7  mov     edx, 235h; unsigned int
0x1800222dc  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x1800222e3  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800222e8  mov     rcx, [rbp+57h+var_80]
0x1800222ec  mov     rax, [rcx]
0x1800222ef  mov     rax, [rax+0C0h]
0x1800222f6  jmp     loc_1800227B0
0x1800222fb  lea     r8, aWwanmsmeventty_28; "WwanMsmEventTypeRegistered/WwanMsmEvent"...
0x180022302  mov     edx, 1D8h; unsigned int
0x180022307  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x18002230e  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180022313  mov     rcx, [rbp+57h+var_80]
0x180022317  mov     rax, [rcx]
0x18002231a  mov     rax, [rax+70h]
0x18002231e  jmp     loc_1800227B0
0x180022323  lea     r8, aWwanmsmeventty_0; "WwanMsmEventTypeScanFailed"
0x18002232a  mov     edx, 200h; unsigned int
0x18002232f  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x180022336  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18002233b  mov     rcx, [rbp+57h+var_80]
0x18002233f  mov     rax, [rcx]
0x180022342  mov     rax, [rax+98h]
0x180022349  jmp     loc_1800227B0
0x18002234e  lea     r8, aWwanmsmeventty_12; "WwanMsmEventTypeScanCompleted"
0x180022355  mov     edx, 1FCh
0x18002235a  jmp     short loc_18002232F
0x18002235c  lea     r8, aWwanmsmeventty_11; "WwanMsmEventTypeGetPinListComplete"
0x180022363  mov     edx, 1E0h; unsigned int
0x180022368  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x18002236f  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180022374  mov     rcx, [rbp+57h+var_80]
0x180022378  mov     rax, [rcx]
0x18002237b  mov     rax, [rax+0E0h]
0x180022382  jmp     loc_1800227B0
0x180022387  mov     eax, r9d
0x18002238a  sub     eax, 17h
0x18002238d  jz      loc_180022483
0x180022393  sub     eax, 2
0x180022396  jz      loc_18002245B
0x18002239c  sub     eax, 3
0x18002239f  jz      loc_18002244D
0x1800223a5  sub     eax, 1
0x1800223a8  jz      loc_18002243F
0x1800223ae  sub     eax, 1
0x1800223b1  jz      short loc_180022417
0x1800223b3  sub     eax, 0Eh
0x1800223b6  jz      short loc_1800223EC
0x1800223b8  cmp     eax, 1
0x1800223bb  jnz     loc_18002267D
0x1800223c1  lea     r8, aWwanmsmeventty_32; "WwanMsmEventTypeProfileIStreamCreated"
0x1800223c8  mov     edx, 1CAh; unsigned int
0x1800223cd  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x1800223d4  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800223d9  mov     rcx, [rbp+57h+var_80]
0x1800223dd  mov     rax, [rcx]
0x1800223e0  mov     rax, [rax+0A0h]
0x1800223e7  jmp     loc_1800227B0
0x1800223ec  lea     r8, aWwanmsmeventty_1; "WwanMsmEventTypeIStreamChanged"
0x1800223f3  mov     edx, 1C2h; unsigned int
0x1800223f8  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x1800223ff  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180022404  mov     rcx, [rbp+57h+var_80]
0x180022408  mov     rax, [rcx]
0x18002240b  mov     rax, [rax+0D0h]
0x180022412  jmp     loc_1800227B0
0x180022417  lea     r8, aWwanmsmeventty_10; "WwanMsmEventTypeSetRadioStateFailed"
0x18002241e  mov     edx, 1F8h; unsigned int
0x180022423  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x18002242a  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18002242f  mov     rcx, [rbp+57h+var_80]
0x180022433  mov     rax, [rcx]
0x180022436  mov     rax, [rax+48h]
0x18002243a  jmp     loc_1800227B0
0x18002243f  lea     r8, aWwanmsmeventty_16; "WwanMsmEventTypeSetRadioStateComplete"
0x180022446  mov     edx, 1F0h
0x18002244b  jmp     short loc_180022423
0x18002244d  lea     r8, aWwanmsmeventty_21; "WwanMsmEventTypeRadioState"
0x180022454  mov     edx, 1F4h
0x180022459  jmp     short loc_180022423
0x18002245b  lea     r8, aWwanmsmeventty_3; "WwanMsmEventTypeSignalState"
0x180022462  mov     edx, 1BEh; unsigned int
0x180022467  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x18002246e  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180022473  mov     rcx, [rbp+57h+var_80]
0x180022477  mov     rax, [rcx]
0x18002247a  mov     rax, [rax+50h]
0x18002247e  jmp     loc_1800227B0
0x180022483  lea     r8, aWwanmsmeventty_2; "WwanMsmEventTypePinActionComplete"
0x18002248a  mov     edx, 1E4h; unsigned int
0x18002248f  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x180022496  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18002249b  mov     rcx, [rbp+57h+var_80]
0x18002249f  mov     rax, [rcx]
0x1800224a2  mov     rax, [rax+0E8h]
0x1800224a9  jmp     loc_1800227B0
0x1800224ae  lea     r8, aWwanmsmeventty_18; "WwanMsmEventTypeProfileIStreamUpdated"
0x1800224b5  mov     edx, 1CEh
0x1800224ba  jmp     loc_1800223CD
0x1800224bf  cmp     r9d, 55h ; 'U'
0x1800224c3  ja      loc_180022647
0x1800224c9  jz      loc_18002262A
0x1800224cf  mov     eax, r9d
0x1800224d2  sub     eax, 2Fh ; '/'
0x1800224d5  jz      loc_1800225FF
0x1800224db  sub     eax, 1
0x1800224de  jz      loc_1800225F1
0x1800224e4  sub     eax, 1
0x1800224e7  jz      loc_1800225C9
0x1800224ed  sub     eax, 0Ah
0x1800224f0  jz      loc_18002259E
0x1800224f6  sub     eax, 8
0x1800224f9  jz      loc_18002258D
0x1800224ff  sub     eax, 5
0x180022502  jz      short loc_180022562
0x180022504  sub     eax, 1
0x180022507  jz      short loc_18002253A
0x180022509  cmp     eax, 5
0x18002250c  jnz     loc_18002267D
0x180022512  lea     r8, aWwanmsmeventty_14; "WwanMsmEventTypeNetworkLTEAttachInfo"
0x180022519  mov     edx, 218h; unsigned int
0x18002251e  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x180022525  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18002252a  mov     rcx, [rbp+57h+var_80]
0x18002252e  mov     rax, [rcx]
0x180022531  mov     rax, [rax+40h]
0x180022535  jmp     loc_1800227B0
0x18002253a  lea     r8, aWwanmsmeventty_33; "WwanMsmEventTypeRoamingPolicyChange"
0x180022541  mov     edx, 20Ch; unsigned int
0x180022546  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x18002254d  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180022552  mov     rcx, [rbp+57h+var_80]
0x180022556  mov     rax, [rcx]
0x180022559  mov     rax, [rax+78h]
0x18002255d  jmp     loc_1800227B0
0x180022562  lea     r8, aWwanmsmeventty_8; "WwanMsmEventTypeDataEnablementChange"
0x180022569  mov     edx, 204h; unsigned int
0x18002256e  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x180022575  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18002257a  mov     rcx, [rbp+57h+var_80]
0x18002257e  mov     rax, [rcx]
0x180022581  mov     rax, [rax+80h]
0x180022588  jmp     loc_1800227B0
0x18002258d  lea     r8, aWwanmsmeventty_13; "WwanMsmEventTypeUiccBindingsChanged - I"...
0x180022594  mov     edx, 22Eh
0x180022599  jmp     loc_180022636
0x18002259e  lea     r8, aWwanmsmeventty_17; "WwanMsmEventTypeDMConfigProfileUpdate"
0x1800225a5  mov     edx, 228h; unsigned int
0x1800225aa  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x1800225b1  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800225b6  mov     rcx, [rbp+57h+var_80]
0x1800225ba  mov     rax, [rcx]
0x1800225bd  mov     rax, [rax+0B0h]
0x1800225c4  jmp     loc_1800227B0
0x1800225c9  lea     r8, aWwanmsmeventty; "WwanMsmEventTypeConnectionIStreamUpdate"...
0x1800225d0  mov     edx, 1ECh; unsigned int
0x1800225d5  lea     rcx, aWindowsNetwork_263; "Windows::Networking::UX::Internal::MBMe"...
0x1800225dc  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800225e1  mov     rcx, [rbp+57h+var_80]
0x1800225e5  mov     rax, [rcx]
0x1800225e8  mov     rax, [rax+58h]
  ... truncated ...
```
