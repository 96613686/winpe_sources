# NotificationHelper::ShowNotification(NotificationMetadata *)

- ea: `0x180104c94`
- end: `0x180104fdd`
- name: `?ShowNotification@NotificationHelper@@QEAAJPEAUNotificationMetadata@@@Z`
- size: `841`
- prototype: `int(NotificationHelper *__hidden this, struct NotificationMetadata *)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800668c4`
- `0x1801b37a4`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001c844`
- `0x1800252e8`
- `0x180103174`
- `0x180104c94`
- `0x180104fe4`
- `0x1801050b4`
- `0x1801051e0`
- `0x1801349ac`
- `0x180134b04`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180104ce0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180104ce0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180104f99`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180104f99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104e48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104e56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104ed8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104ee6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104e48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104e56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104ed8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104ee6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180104d30`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180104d30`

## string_xrefs

- `0x180104e80`: `_spNotificationCreator->CreateNotificationUpdateData(pData, notificationUpdateData.GetAddressOf(), notificationGroup.GetAddressOf(), notificationTag.GetAddressOf())`
- `0x180104dfc`: `onecoreuap\enduser\winstore\installservice\lib\notificationhelper.cpp`
- `0x180104de6`: `_UpdateNotificationHistory(spTNMForUser, pData, &dwToastDisplayFlags, &cNotificationCount)`
- `0x180104ebb`: `_UpdateNotification(spTNMForUser.Get(), notificationUpdateData.Get(), notificationGroup.Get(), notificationTag.Get())`
- `0x180104f45`: `_spNotificationCreator->CreateNotification( spTNMStatics.Get(), pData, !!(dwToastDisplayFlags & FLAG_GROUPED), !!(dwToastDisplayFlags & FLAG_GHOST), cNotificationCount, notification.GetAddressOf())`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall NotificationHelper::ShowNotification(HANDLE *this, struct NotificationMetadata *a2)
{
  __int64 v4; // rbx
  int ActivationFactory; // ebx
  struct Windows::UI::Notifications::IToastNotificationManagerStatics *v6; // rbx
  __int64 (__fastcall *v7)(struct Windows::UI::Notifications::IToastNotificationManagerStatics *, GUID *, HSTRING *); // rdi
  HSTRING v8; // rdi
  __int64 (__fastcall *v9)(HSTRING, _QWORD, struct Windows::UI::Notifications::IToastNotificationManagerForUser **); // rbx
  int updated; // eax
  NotificationCreator *v11; // rbx
  int v12; // eax
  NotificationHelper *v13; // rcx
  int v14; // eax
  struct Windows::UI::Notifications::IToastNotification *v15; // rcx
  int v16; // eax
  NotificationHelper *v17; // rcx
  int v18; // eax
  unsigned int v20; // [rsp+28h] [rbp-41h]
  unsigned int v21; // [rsp+28h] [rbp-41h]
  unsigned int v22; // [rsp+28h] [rbp-41h]
  unsigned int v23; // [rsp+28h] [rbp-41h]
  unsigned int v24; // [rsp+28h] [rbp-41h]
  struct Windows::UI::Notifications::IToastNotification *v25; // [rsp+40h] [rbp-29h] BYREF
  HSTRING newString; // [rsp+48h] [rbp-21h] BYREF
  HSTRING string; // [rsp+50h] [rbp-19h] BYREF
  struct Windows::UI::Notifications::IToastNotificationManagerForUser *v28; // [rsp+58h] [rbp-11h] BYREF
  int v29; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v30; // [rsp+64h] [rbp-5h] BYREF
  struct Windows::UI::Notifications::IToastNotificationManagerStatics *v31; // [rsp+68h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  __int64 v33; // [rsp+88h] [rbp+1Fh]

  if ( (unsigned int)(*((_DWORD *)a2 + 2) - 4) <= 1 )
    GetPackageDetails(a2);
  WaitForSingleObject(this[11], 0xFFFFFFFF);
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v28 = 0;
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.UI.Notifications.ToastNotificationManager",
    0x32u,
    0x31u);
  v4 = v33;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v31);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4, &v31);
  if ( ActivationFactory >= 0 )
  {
    newString = 0;
    v6 = v31;
    v7 = **(__int64 (__fastcall ***)(struct Windows::UI::Notifications::IToastNotificationManagerStatics *, GUID *, HSTRING *))v31;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&newString);
    ActivationFactory = v7(v6, &GUID_8f993fd3_e516_45fb_8130_398e93fa52c3, &newString);
    if ( ActivationFactory >= 0 )
    {
      v8 = newString;
      v9 = *(__int64 (__fastcall **)(HSTRING, _QWORD, struct Windows::UI::Notifications::IToastNotificationManagerForUser **))(*(_QWORD *)newString + 48LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v28);
      ActivationFactory = v9(v8, *(_QWORD *)a2, &v28);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&newString);
    if ( ActivationFactory >= 0 )
    {
      v25 = v28;
      if ( v28 )
        (*(void (__fastcall **)(struct Windows::UI::Notifications::IToastNotificationManagerForUser *))(*(_QWORD *)v28 + 8LL))(v28);
      updated = NotificationHelper::_UpdateNotificationHistory(
                  (__int64)this,
                  (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v25,
                  (__int64)a2,
                  &v29,
                  &v30);
      ActivationFactory = TraceHR(
                            "onecoreuap\\enduser\\winstore\\installservice\\lib\\notificationhelper.cpp",
                            0x5Cu,
                            "NotificationHelper::ShowNotification",
                            "_UpdateNotificationHistory(spTNMForUser, pData, &dwToastDisplayFlags, &cNotificationCount)",
                            updated,
                            v20);
      if ( ActivationFactory >= 0 && v29 && *((_BYTE *)a2 + 93) )
      {
        v11 = (NotificationCreator *)this[9];
        v25 = 0;
        if ( (v29 & 8) != 0 )
        {
          string = 0;
          newString = 0;
          WindowsDeleteString(0);
          newString = 0;
          WindowsDeleteString(string);
          string = 0;
          v12 = NotificationCreator::CreateNotificationUpdateData(v11, a2, &v25, &string, &newString);
          ActivationFactory = TraceHR(
                                "onecoreuap\\enduser\\winstore\\installservice\\lib\\notificationhelper.cpp",
                                0x66u,
                                "NotificationHelper::ShowNotification",
                                "_spNotificationCreator->CreateNotificationUpdateData(pData, notificationUpdateData.GetAd"
                                "dressOf(), notificationGroup.GetAddressOf(), notificationTag.GetAddressOf())",
                                v12,
                                v21);
          if ( ActivationFactory >= 0 )
          {
            v14 = NotificationHelper::_UpdateNotification(v13, v28, v25, string, newString);
            ActivationFactory = TraceHR(
                                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\notificationhelper.cpp",
                                  0x67u,
                                  "NotificationHelper::ShowNotification",
                                  "_UpdateNotification(spTNMForUser.Get(), notificationUpdateData.Get(), notificationGrou"
                                  "p.Get(), notificationTag.Get())",
                                  v14,
                                  v22);
          }
          WindowsDeleteString(newString);
          newString = 0;
          WindowsDeleteString(string);
          string = 0;
          v15 = v25;
          if ( v25 )
          {
            v25 = 0;
            (*(void (__fastcall **)(struct Windows::UI::Notifications::IToastNotification *))(*(_QWORD *)v15 + 16LL))(v15);
          }
        }
        else
        {
          v16 = NotificationCreator::CreateNotification(v11, v31, a2, (v29 & 2) != 0, (v29 & 4) != 0, v30, &v25);
          ActivationFactory = TraceHR(
                                "onecoreuap\\enduser\\winstore\\installservice\\lib\\notificationhelper.cpp",
                                0x72u,
                                "NotificationHelper::ShowNotification",
                                "_spNotificationCreator->CreateNotification( spTNMStatics.Get(), pData, !!(dwToastDisplay"
                                "Flags & FLAG_GROUPED), !!(dwToastDisplayFlags & FLAG_GHOST), cNotificationCount, notific"
                                "ation.GetAddressOf())",
                                v16,
                                v23);
          if ( ActivationFactory >= 0 )
          {
            v18 = NotificationHelper::_DisplayNotification(v17, v28, v25);
            ActivationFactory = TraceHR(
                                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\notificationhelper.cpp",
                                  0x74u,
                                  "NotificationHelper::ShowNotification",
                                  "_DisplayNotification(spTNMForUser.Get(), notification.Get())",
                                  v18,
                                  v24);
          }
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v25);
        }
      }
    }
  }
  ReleaseMutex(this[11]);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v31);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180104c94  mov     [rsp-8+arg_10], rbx
0x180104c99  mov     [rsp-8+arg_18], rsi
0x180104c9e  push    rbp
0x180104c9f  push    rdi
0x180104ca0  push    r12
0x180104ca2  push    r14
0x180104ca4  push    r15
0x180104ca6  lea     rbp, [rsp-37h]
0x180104cab  sub     rsp, 0A0h
0x180104cb2  mov     rax, cs:__security_cookie
0x180104cb9  xor     rax, rsp
0x180104cbc  mov     [rbp+57h+var_30], rax
0x180104cc0  mov     rsi, rdx
0x180104cc3  mov     r14, rcx
0x180104cc6  mov     eax, [rdx+8]
0x180104cc9  sub     eax, 4
0x180104ccc  cmp     eax, 1
0x180104ccf  ja      short loc_180104CD9
0x180104cd1  mov     rcx, rdx; struct NotificationMetadata *
0x180104cd4  call    ?GetPackageDetails@@YAJPEAUNotificationMetadata@@@Z; GetPackageDetails(NotificationMetadata *)
0x180104cd9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180104cdc  mov     rcx, [r14+58h]; hHandle
0x180104ce0  call    cs:__imp_WaitForSingleObject
0x180104ce6  xor     r15d, r15d
0x180104ce9  mov     [rbp+57h+var_60], r15d
0x180104ced  mov     [rbp+57h+var_5C], r15d
0x180104cf1  mov     [rbp+57h+var_58], r15
0x180104cf5  mov     [rbp+57h+var_68], r15
0x180104cf9  mov     [rbp+57h+var_38], r15
0x180104cfd  lea     r9d, [r15+31h]; unsigned int
0x180104d01  lea     r8d, [r15+32h]; unsigned int
0x180104d05  lea     rdx, ?RuntimeClass_Windows_UI_Notifications_ToastNotificationManager@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x180104d0c  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180104d10  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180104d15  mov     rbx, [rbp+57h+var_38]
0x180104d19  lea     rcx, [rbp+57h+var_58]
0x180104d1d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180104d22  lea     r8, [rbp+57h+var_58]
0x180104d26  lea     rdx, _GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4
0x180104d2d  mov     rcx, rbx
0x180104d30  call    cs:__imp_RoGetActivationFactory
0x180104d36  mov     ebx, eax
0x180104d38  test    eax, eax
0x180104d3a  js      loc_180104F95
0x180104d40  mov     [rbp+57h+newString], r15
0x180104d44  mov     rbx, [rbp+57h+var_58]
0x180104d48  mov     rax, [rbx]
0x180104d4b  mov     rdi, [rax]
0x180104d4e  lea     rcx, [rbp+57h+newString]
0x180104d52  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180104d57  lea     r8, [rbp+57h+newString]
0x180104d5b  lea     rdx, _GUID_8f993fd3_e516_45fb_8130_398e93fa52c3
0x180104d62  mov     rcx, rbx
0x180104d65  mov     rax, rdi
0x180104d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104d6d  mov     ebx, eax
0x180104d6f  test    eax, eax
0x180104d71  js      short loc_180104D9B
0x180104d73  mov     rdi, [rbp+57h+newString]
0x180104d77  mov     rax, [rdi]
0x180104d7a  mov     rbx, [rax+30h]
0x180104d7e  lea     rcx, [rbp+57h+var_68]
0x180104d82  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180104d87  lea     r8, [rbp+57h+var_68]
0x180104d8b  mov     rdx, [rsi]
0x180104d8e  mov     rcx, rdi
0x180104d91  mov     rax, rbx
0x180104d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104d99  mov     ebx, eax
0x180104d9b  lea     rcx, [rbp+57h+newString]
0x180104d9f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180104da4  test    ebx, ebx
0x180104da6  js      loc_180104F95
0x180104dac  mov     rcx, [rbp+57h+var_68]
0x180104db0  mov     [rbp+57h+var_80], rcx
0x180104db4  test    rcx, rcx
0x180104db7  jz      short loc_180104DC6
0x180104db9  mov     rax, [rcx]
0x180104dbc  mov     rax, [rax+8]
0x180104dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104dc5  nop
0x180104dc6  lea     rax, [rbp+57h+var_5C]
0x180104dca  mov     [rsp+0C0h+var_A0], rax
0x180104dcf  lea     r9, [rbp+57h+var_60]
0x180104dd3  mov     r8, rsi
0x180104dd6  lea     rdx, [rbp+57h+var_80]
0x180104dda  mov     rcx, r14
0x180104ddd  call    ?_UpdateNotificationHistory@NotificationHelper@@AEAAJV?$ComPtr@UIToastNotificationManagerForUser@Notifications@UI@Windows@@@WRL@Microsoft@@PEAUNotificationMetadata@@PEAKPEAI@Z; NotificationHelper::_UpdateNotificationHistory(Microsoft::WRL::ComPtr<Windows::UI::Notifications::IToastNotificationManagerForUser>,NotificationMetadata *,ulong *,uint *)
0x180104de2  mov     dword ptr [rsp+0C0h+var_A0], eax; int
0x180104de6  lea     r9, aUpdatenotifica; "_UpdateNotificationHistory(spTNMForUser"...
0x180104ded  lea     rdi, aNotificationhe_3; "NotificationHelper::ShowNotification"
0x180104df4  mov     r8, rdi; char *
0x180104df7  mov     edx, 5Ch ; '\'; unsigned int
0x180104dfc  lea     r12, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\installs"...
0x180104e03  mov     rcx, r12; char *
0x180104e06  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180104e0b  mov     ebx, eax
0x180104e0d  test    eax, eax
0x180104e0f  js      loc_180104F95
0x180104e15  mov     r9d, [rbp+57h+var_60]
0x180104e19  test    r9d, r9d
0x180104e1c  jz      loc_180104F95
0x180104e22  cmp     [rsi+5Dh], r15b
0x180104e26  jz      loc_180104F95
0x180104e2c  mov     rbx, [r14+48h]
0x180104e30  mov     [rbp+57h+var_80], r15
0x180104e34  test    r9b, 8
0x180104e38  jz      loc_180104F0F
0x180104e3e  mov     [rbp+57h+string], r15
0x180104e42  mov     [rbp+57h+newString], r15
0x180104e46  xor     ecx, ecx; string
0x180104e48  call    cs:__imp_WindowsDeleteString
0x180104e4e  mov     [rbp+57h+newString], r15
0x180104e52  mov     rcx, [rbp+57h+string]; string
0x180104e56  call    cs:__imp_WindowsDeleteString
0x180104e5c  mov     [rbp+57h+string], r15
0x180104e60  lea     rax, [rbp+57h+newString]
0x180104e64  mov     [rsp+0C0h+var_A0], rax; newString
0x180104e69  lea     r9, [rbp+57h+string]; HSTRING *
0x180104e6d  lea     r8, [rbp+57h+var_80]; struct Windows::UI::Notifications::INotificationData **
0x180104e71  mov     rdx, rsi; struct NotificationMetadata *
0x180104e74  mov     rcx, rbx; this
0x180104e77  call    ?CreateNotificationUpdateData@NotificationCreator@@QEAAJPEAUNotificationMetadata@@PEAPEAUINotificationData@Notifications@UI@Windows@@PEAPEAUHSTRING__@@2@Z; NotificationCreator::CreateNotificationUpdateData(NotificationMetadata *,Windows::UI::Notifications::INotificationData * *,HSTRING__ * *,HSTRING__ * *)
0x180104e7c  mov     dword ptr [rsp+0C0h+var_A0], eax; int
0x180104e80  lea     r9, aSpnotification; "_spNotificationCreator->CreateNotificat"...
0x180104e87  mov     r8, rdi; char *
0x180104e8a  mov     edx, 66h ; 'f'; unsigned int
0x180104e8f  mov     rcx, r12; char *
0x180104e92  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180104e97  mov     ebx, eax
0x180104e99  test    eax, eax
0x180104e9b  js      short loc_180104ED4
0x180104e9d  mov     rax, [rbp+57h+newString]
0x180104ea1  mov     [rsp+0C0h+var_A0], rax; HSTRING
0x180104ea6  mov     r9, [rbp+57h+string]; HSTRING
0x180104eaa  mov     r8, [rbp+57h+var_80]; struct Windows::UI::Notifications::INotificationData *
0x180104eae  mov     rdx, [rbp+57h+var_68]; struct Windows::UI::Notifications::IToastNotificationManagerForUser *
0x180104eb2  call    ?_UpdateNotification@NotificationHelper@@AEAAJPEAUIToastNotificationManagerForUser@Notifications@UI@Windows@@PEAUINotificationData@345@PEAUHSTRING__@@2@Z; NotificationHelper::_UpdateNotification(Windows::UI::Notifications::IToastNotificationManagerForUser *,Windows::UI::Notifications::INotificationData *,HSTRING__ *,HSTRING__ *)
0x180104eb7  mov     dword ptr [rsp+0C0h+var_A0], eax; int
0x180104ebb  lea     r9, aUpdatenotifica_0; "_UpdateNotification(spTNMForUser.Get(),"...
0x180104ec2  mov     r8, rdi; char *
0x180104ec5  mov     edx, 67h ; 'g'; unsigned int
0x180104eca  mov     rcx, r12; char *
0x180104ecd  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180104ed2  mov     ebx, eax
0x180104ed4  mov     rcx, [rbp+57h+newString]; string
0x180104ed8  call    cs:__imp_WindowsDeleteString
0x180104ede  mov     [rbp+57h+newString], r15
0x180104ee2  mov     rcx, [rbp+57h+string]; string
0x180104ee6  call    cs:__imp_WindowsDeleteString
0x180104eec  mov     [rbp+57h+string], r15
0x180104ef0  mov     rcx, [rbp+57h+var_80]
0x180104ef4  test    rcx, rcx
0x180104ef7  jz      short loc_180104F0A
0x180104ef9  mov     [rbp+57h+var_80], r15
0x180104efd  mov     rax, [rcx]
0x180104f00  mov     rax, [rax+10h]
0x180104f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104f09  nop
0x180104f0a  jmp     loc_180104F95
0x180104f0f  mov     ecx, [rbp+57h+var_5C]
0x180104f12  mov     eax, r9d
0x180104f15  shr     eax, 2
0x180104f18  and     al, 1
0x180104f1a  shr     r9d, 1
0x180104f1d  and     r9b, 1; bool
0x180104f21  lea     rdx, [rbp+57h+var_80]
0x180104f25  mov     [rsp+0C0h+var_90], rdx; struct Windows::UI::Notifications::IToastNotification **
0x180104f2a  mov     [rsp+0C0h+var_98], ecx; int
0x180104f2e  mov     byte ptr [rsp+0C0h+var_A0], al; bool
0x180104f32  mov     r8, rsi; struct NotificationMetadata *
0x180104f35  mov     rdx, [rbp+57h+var_58]; struct Windows::UI::Notifications::IToastNotificationManagerStatics *
0x180104f39  mov     rcx, rbx; this
0x180104f3c  call    ?CreateNotification@NotificationCreator@@QEAAJPEAUIToastNotificationManagerStatics@Notifications@UI@Windows@@PEAUNotificationMetadata@@_N2IPEAPEAUIToastNotification@345@@Z; NotificationCreator::CreateNotification(Windows::UI::Notifications::IToastNotificationManagerStatics *,NotificationMetadata *,bool,bool,uint,Windows::UI::Notifications::IToastNotification * *)
0x180104f41  mov     dword ptr [rsp+0C0h+var_A0], eax; int
0x180104f45  lea     r9, aSpnotification_0; "_spNotificationCreator->CreateNotificat"...
0x180104f4c  mov     r8, rdi; char *
0x180104f4f  mov     edx, 72h ; 'r'; unsigned int
0x180104f54  mov     rcx, r12; char *
0x180104f57  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180104f5c  mov     ebx, eax
0x180104f5e  test    eax, eax
0x180104f60  js      short loc_180104F8C
0x180104f62  mov     r8, [rbp+57h+var_80]; struct Windows::UI::Notifications::IToastNotification *
0x180104f66  mov     rdx, [rbp+57h+var_68]; struct Windows::UI::Notifications::IToastNotificationManagerForUser *
0x180104f6a  call    ?_DisplayNotification@NotificationHelper@@AEAAJPEAUIToastNotificationManagerForUser@Notifications@UI@Windows@@PEAUIToastNotification@345@@Z; NotificationHelper::_DisplayNotification(Windows::UI::Notifications::IToastNotificationManagerForUser *,Windows::UI::Notifications::IToastNotification *)
0x180104f6f  mov     dword ptr [rsp+0C0h+var_A0], eax; int
0x180104f73  lea     r9, aDisplaynotific; "_DisplayNotification(spTNMForUser.Get()"...
0x180104f7a  mov     r8, rdi; char *
0x180104f7d  mov     edx, 74h ; 't'; unsigned int
0x180104f82  mov     rcx, r12; char *
0x180104f85  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180104f8a  mov     ebx, eax
0x180104f8c  lea     rcx, [rbp+57h+var_80]
0x180104f90  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180104f95  mov     rcx, [r14+58h]; hMutex
0x180104f99  call    cs:__imp_ReleaseMutex
0x180104f9f  nop
0x180104fa0  lea     rcx, [rbp+57h+var_68]
0x180104fa4  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180104fa9  nop
0x180104faa  lea     rcx, [rbp+57h+var_58]
0x180104fae  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180104fb3  mov     eax, ebx
0x180104fb5  mov     rcx, [rbp+57h+var_30]
0x180104fb9  xor     rcx, rsp; StackCookie
0x180104fbc  call    __security_check_cookie
0x180104fc1  lea     r11, [rsp+0C0h+var_20]
0x180104fc9  mov     rbx, [r11+40h]
0x180104fcd  mov     rsi, [r11+48h]
0x180104fd1  mov     rsp, r11
0x180104fd4  pop     r15
0x180104fd6  pop     r14
0x180104fd8  pop     r12
0x180104fda  pop     rdi
0x180104fdb  pop     rbp
0x180104fdc  retn
```
