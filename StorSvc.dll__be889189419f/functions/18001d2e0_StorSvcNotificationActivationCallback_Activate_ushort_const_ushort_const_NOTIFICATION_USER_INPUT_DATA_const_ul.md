# StorSvcNotificationActivationCallback::Activate(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x18001d2e0`
- end: `0x18001d8e3`
- name: `?Activate@StorSvcNotificationActivationCallback@@UEAAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `1539`
- prototype: `int(StorSvcNotificationActivationCallback *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180001148`
- `0x180001328`
- `0x18000d030`
- `0x180012734`
- `0x180014a00`
- `0x180017500`
- `0x18001780c`
- `0x18001784c`
- `0x180018c0c`
- `0x180018cc0`
- `0x18001ca54`
- `0x18001cb08`
- `0x18001d2e0`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d335`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d36d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d3a3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d3d2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d582`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d6d3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d7f4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d335`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d36d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d3a3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d3d2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d582`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d6d3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d7f4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d65b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d65b`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x18001d670`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x18001d670`

## string_xrefs

- `0x18001d401`: `Windows.Foundation.Uri`
- `0x18001d329`: `command:DeleteWinOld_Yes`
- `0x18001d361`: `command:DeleteWinOld_No`
- `0x18001d397`: `command:StoragePolicies_ReminderToast`
- `0x18001d3c6`: `command:LaunchStoragePolicies`
- `0x18001d6c7`: `command:CloudAgeOut_Enable`
- `0x18001d7e8`: `command:CloudAgeOut_Dismiss`
- `0x18001d576`: `command:LaunchSystemStorage`
- `0x18001d7c8`: `onecore\drivers\storage\storsvc\service\storagelowdisk.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall StorSvcNotificationActivationCallback::Activate(
        StorSvcNotificationActivationCallback *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct NOTIFICATION_USER_INPUT_DATA *a4)
{
  __int64 v5; // rcx
  HKEY v6; // rcx
  unsigned int v7; // r9d
  const unsigned __int16 *v8; // r8
  const unsigned __int16 *v9; // rdx
  int v10; // esi
  __int64 v11; // rdi
  int (__fastcall *v12)(__int64, __int64, LPVOID *); // rbx
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, LPVOID, __int64 *); // rbx
  bool v15; // sf
  char v16; // al
  HKEY v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  HKEY v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  int v23; // eax
  unsigned int v24; // ebx
  __int64 v26; // r8
  __int64 v27; // r9
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v31; // [rsp+50h] [rbp-B0h]
  unsigned int v32[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h] BYREF
  int v35[2]; // [rsp+70h] [rbp-90h] BYREF
  HSTRING_HEADER v36; // [rsp+78h] [rbp-88h] BYREF
  __int64 v37; // [rsp+90h] [rbp-70h]
  HSTRING_HEADER v38; // [rsp+98h] [rbp-68h] BYREF
  __int64 v39; // [rsp+B0h] [rbp-50h]
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v41; // [rsp+D0h] [rbp-30h]
  _OWORD v42[13]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v31 = 0;
  v29 = 0;
  if ( CompareStringOrdinal(a3, -1, L"command:DeleteWinOld_Yes", -1, 0) == 2 )
  {
    ppv = &v29;
    Windows::Internal::ComTaskPool::QueueTask<_lambda_17fcd30ddbc55d1a344c922581f42f74_>(v5, &ppv);
    return 0;
  }
  if ( CompareStringOrdinal(a3, -1, L"command:DeleteWinOld_No", -1, 0) == 2 )
  {
    v7 = 7;
    v8 = L"NumWinOldLowStorageNotify";
    v9 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\DiskSpaceChecking";
LABEL_40:
    SHRegSetDWORD(v6, v9, v8, v7);
    return 0;
  }
  if ( CompareStringOrdinal(a3, -1, L"command:StoragePolicies_ReminderToast", -1, 0) == 2 )
  {
    v7 = 1;
    v8 = L"OptOutButtonClicked";
LABEL_39:
    v9 = L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy";
    goto LABEL_40;
  }
  if ( CompareStringOrdinal(a3, -1, L"command:LaunchStoragePolicies", -1, 0) == 2 )
  {
    *(_QWORD *)v32 = 0;
    v33 = 0;
    ppv = 0;
    v34 = 0;
    v41 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
    v10 = 1;
    v31 = 1;
    v29 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
            v41,
            (__int64)&v33);
    if ( v29 < 0 )
      goto LABEL_12;
    v11 = v33;
    v12 = *(int (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v33 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
    v39 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v38, L"ms-settings:storagepolicies", 0x1Cu, 0x1Bu);
    v10 = 3;
    v31 = 3;
    if ( v12(v11, v39, &ppv) < 0 )
      goto LABEL_12;
    v37 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v36, L"Windows.System.Launcher", 0x18u, 0x17u);
    v10 = 7;
    v31 = 7;
    v29 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(
            v37,
            (__int64)v32);
    if ( v29 < 0
      || (v13 = *(_QWORD *)v32,
          v14 = *(int (__fastcall **)(__int64, LPVOID, __int64 *))(**(_QWORD **)v32 + 64LL),
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34),
          v15 = v14(v13, ppv, &v34) < 0,
          v16 = 1,
          v15) )
    {
LABEL_12:
      v16 = 0;
    }
    if ( (v10 & 4) != 0 )
    {
      v10 &= ~4u;
      v31 = v10;
      v37 = 0;
    }
    if ( (v10 & 2) != 0 )
    {
      v10 &= ~2u;
      v31 = v10;
      v39 = 0;
    }
    if ( (v10 & 1) != 0 )
    {
      v31 = v10 & 0xFFFFFFFE;
      v41 = 0;
    }
    if ( v16 )
      v29 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v32);
    return 0;
  }
  if ( CompareStringOrdinal(a3, -1, L"command:LaunchSystemStorage", -1, 0) == 2 )
  {
    ppv = 0;
    v42[0] = *(_OWORD *)L"page=SettingsPageStorageSenseStorageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
    v42[1] = *(_OWORD *)L"tingsPageStorageSenseStorageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
    v42[2] = *(_OWORD *)L"eStorageSenseStorageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
    v42[3] = *(_OWORD *)L"SenseStorageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
    v42[4] = *(_OWORD *)L"rageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
    v42[5] = *(_OWORD *)L"view&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
    v42[6] = *(_OWORD *)L"get=SystemSettings_StorageSense_SystemDrive&invoke=true";
    v42[7] = *(_OWORD *)L"emSettings_StorageSense_SystemDrive&invoke=true";
    v42[8] = *(_OWORD *)L"gs_StorageSense_SystemDrive&invoke=true";
    v42[9] = *(_OWORD *)L"geSense_SystemDrive&invoke=true";
    v42[10] = *(_OWORD *)L"SystemDrive&invoke=true";
    v42[11] = *(_OWORD *)L"ive&invoke=true";
    v42[12] = *(_OWORD *)L"ke=true";
    v32[0] = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
    if ( CoCreateInstance(&CLSID_ApplicationActivationManager, 0, 4u, &GUID_2e941141_7f97_4756_ba1d_9decde894a3d, &ppv) >= 0 )
    {
      v29 = CoAllowSetForegroundWindow((IUnknown *)ppv, 0);
      if ( v29 >= 0
        && (*(int (__fastcall **)(LPVOID, const wchar_t *, _OWORD *, _QWORD, unsigned int *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
             v42,
             0,
             v32) >= 0 )
      {
        v29 = 0;
      }
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
    return 0;
  }
  if ( CompareStringOrdinal(a3, -1, L"command:CloudAgeOut_Enable", -1, 0) != 2 )
  {
    if ( CompareStringOrdinal(a3, -1, L"command:CloudAgeOut_Dismiss", -1, 0) != 2 )
      return 0;
    v32[0] = 0;
    SHRegGetDWORD(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
      L"CloudConsentToastCount",
      v32);
    if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
    {
      LODWORD(ppv) = v32[0];
      LODWORD(v34) = 1223;
      LODWORD(v33) = 4;
      *(_QWORD *)v35 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (__int64)&word_1800A583E,
        v26,
        v27,
        (__int64)v35,
        (__int64)&v33,
        (__int64)&v34,
        (__int64)&ppv);
    }
    v7 = 3;
    v8 = L"CloudConsentToastCount";
    goto LABEL_39;
  }
  v32[0] = 0;
  SHRegGetDWORD(
    HKEY_CURRENT_USER,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
    L"CloudConsentToastCount",
    v32);
  if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
  {
    LODWORD(v33) = v32[0];
    LODWORD(v34) = 0;
    LODWORD(ppv) = 4;
    *(_QWORD *)v35 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)v17,
      (__int64)word_1800A5882,
      v18,
      v19,
      (__int64)v35,
      (__int64)&ppv,
      (__int64)&v34,
      (__int64)&v33);
  }
  SHRegSetDWORD(
    v17,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
    L"CloudConsentToastCount",
    3u);
  SHRegSetDWORD(
    v20,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
    L"CloudfilePolicyConsent",
    1u);
  v23 = Windows::Internal::ComTaskPool::QueueTask<_lambda_aaac285f1682a49811d03760bad078e8_>(v22, v21);
  v24 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D4,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagelowdisk.cpp",
      (const char *)(unsigned int)v23,
      bIgnoreCase);
    return v24;
  }
  return 0;
}

```

## disassembly

```asm
0x18001d2e0  mov     [rsp-8+arg_0], rbx
0x18001d2e5  mov     [rsp-8+arg_8], rsi
0x18001d2ea  push    rbp
0x18001d2eb  push    rdi
0x18001d2ec  push    r14
0x18001d2ee  lea     rbp, [rsp-0C0h]
0x18001d2f6  sub     rsp, 1C0h
0x18001d2fd  mov     rax, cs:__security_cookie
0x18001d304  xor     rax, rsp
0x18001d307  mov     [rbp+0D0h+var_20], rax
0x18001d30e  mov     rbx, r8
0x18001d311  xor     r14d, r14d
0x18001d314  mov     [rsp+1D0h+var_180], r14d
0x18001d319  mov     [rsp+1D0h+var_190], r14d
0x18001d31e  mov     [rsp+1D0h+bIgnoreCase], r14d; bIgnoreCase
0x18001d323  or      edi, 0FFFFFFFFh
0x18001d326  mov     r9d, edi; cchCount2
0x18001d329  lea     r8, String2; "command:DeleteWinOld_Yes"
0x18001d330  mov     edx, edi; cchCount1
0x18001d332  mov     rcx, rbx; lpString1
0x18001d335  call    cs:__imp_CompareStringOrdinal
0x18001d33b  cmp     eax, 2
0x18001d33e  jnz     short loc_18001D359
0x18001d340  lea     rax, [rsp+1D0h+var_190]
0x18001d345  mov     [rsp+1D0h+ppv], rax
0x18001d34a  lea     rdx, [rsp+1D0h+ppv]
0x18001d34f  call    ??$QueueTask@V_lambda_17fcd30ddbc55d1a344c922581f42f74_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_17fcd30ddbc55d1a344c922581f42f74_@@@Z; Windows::Internal::ComTaskPool::QueueTask<_lambda_17fcd30ddbc55d1a344c922581f42f74_>(Windows::Internal::TaskApartment,_lambda_17fcd30ddbc55d1a344c922581f42f74_ &&)
0x18001d354  jmp     loc_18001D8BA
0x18001d359  mov     [rsp+1D0h+bIgnoreCase], r14d; bIgnoreCase
0x18001d35e  mov     r9d, edi; cchCount2
0x18001d361  lea     r8, aCommandDeletew; "command:DeleteWinOld_No"
0x18001d368  mov     edx, edi; cchCount1
0x18001d36a  mov     rcx, rbx; lpString1
0x18001d36d  call    cs:__imp_CompareStringOrdinal
0x18001d373  cmp     eax, 2
0x18001d376  jnz     short loc_18001D38F
0x18001d378  lea     r9d, [rax+5]
0x18001d37c  lea     r8, aNumwinoldlowst; "NumWinOldLowStorageNotify"
0x18001d383  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001d38a  jmp     loc_18001D8B5
0x18001d38f  mov     [rsp+1D0h+bIgnoreCase], r14d; bIgnoreCase
0x18001d394  mov     r9d, edi; cchCount2
0x18001d397  lea     r8, aCommandStorage; "command:StoragePolicies_ReminderToast"
0x18001d39e  mov     edx, edi; cchCount1
0x18001d3a0  mov     rcx, rbx; lpString1
0x18001d3a3  call    cs:__imp_CompareStringOrdinal
0x18001d3a9  cmp     eax, 2
0x18001d3ac  jnz     short loc_18001D3BE
0x18001d3ae  lea     r9d, [rax-1]
0x18001d3b2  lea     r8, aOptoutbuttoncl; "OptOutButtonClicked"
0x18001d3b9  jmp     loc_18001D8AE
0x18001d3be  mov     [rsp+1D0h+bIgnoreCase], r14d; bIgnoreCase
0x18001d3c3  mov     r9d, edi; cchCount2
0x18001d3c6  lea     r8, aCommandLaunchs_0; "command:LaunchStoragePolicies"
0x18001d3cd  mov     edx, edi; cchCount1
0x18001d3cf  mov     rcx, rbx; lpString1
0x18001d3d2  call    cs:__imp_CompareStringOrdinal
0x18001d3d8  cmp     eax, 2
0x18001d3db  jnz     loc_18001D56E
0x18001d3e1  mov     qword ptr [rsp+1D0h+var_178], r14
0x18001d3e6  mov     [rsp+1D0h+var_170], r14
0x18001d3eb  mov     [rsp+1D0h+ppv], r14
0x18001d3f0  mov     [rsp+1D0h+var_168], r14
0x18001d3f5  mov     [rbp+0D0h+var_100], r14
0x18001d3f9  lea     r9d, [rax+14h]; unsigned int
0x18001d3fd  lea     r8d, [rax+15h]; unsigned int
0x18001d401  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18001d408  lea     rcx, [rbp+0D0h+hstringHeader]; hstringHeader
0x18001d40c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001d411  nop
0x18001d412  mov     esi, 1
0x18001d417  mov     [rsp+1D0h+var_180], esi
0x18001d41b  lea     rdx, [rsp+1D0h+var_170]
0x18001d420  mov     rcx, [rbp+0D0h+var_100]
0x18001d424  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18001d429  mov     [rsp+1D0h+var_190], eax
0x18001d42d  test    eax, eax
0x18001d42f  js      loc_18001D4FF
0x18001d435  mov     rdi, [rsp+1D0h+var_170]
0x18001d43a  mov     rax, [rdi]
0x18001d43d  mov     rbx, [rax+30h]
0x18001d441  lea     rcx, [rsp+1D0h+ppv]
0x18001d446  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d44b  mov     [rbp+0D0h+var_120], r14
0x18001d44f  lea     r9d, [rsi+1Ah]; unsigned int
0x18001d453  lea     r8d, [rsi+1Bh]; unsigned int
0x18001d457  lea     rdx, sourceString; "ms-settings:storagepolicies"
0x18001d45e  lea     rcx, [rbp+0D0h+var_138]; hstringHeader
0x18001d462  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001d467  nop
0x18001d468  mov     esi, 3
0x18001d46d  mov     [rsp+1D0h+var_180], esi
0x18001d471  lea     r8, [rsp+1D0h+ppv]
0x18001d476  mov     rdx, [rbp+0D0h+var_120]
0x18001d47a  mov     rcx, rdi
0x18001d47d  mov     rax, rbx
0x18001d480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d485  mov     [rsp+1D0h+var_190], eax
0x18001d489  test    eax, eax
0x18001d48b  js      short loc_18001D4FF
0x18001d48d  mov     [rbp+0D0h+var_140], r14
0x18001d491  lea     r9d, [rsi+14h]; unsigned int
0x18001d495  lea     r8d, [rsi+15h]; unsigned int
0x18001d499  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x18001d4a0  lea     rcx, [rsp+1D0h+var_158]; hstringHeader
0x18001d4a5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001d4aa  nop
0x18001d4ab  mov     esi, 7
0x18001d4b0  mov     [rsp+1D0h+var_180], esi
0x18001d4b4  lea     rdx, [rsp+1D0h+var_178]
0x18001d4b9  mov     rcx, [rbp+0D0h+var_140]
0x18001d4bd  call    ??$GetActivationFactory@V?$ComPtr@UILauncherStatics@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILauncherStatics@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>)
0x18001d4c2  mov     [rsp+1D0h+var_190], eax
0x18001d4c6  test    eax, eax
0x18001d4c8  js      short loc_18001D4FF
0x18001d4ca  mov     rdi, qword ptr [rsp+1D0h+var_178]
0x18001d4cf  mov     rax, [rdi]
0x18001d4d2  mov     rbx, [rax+40h]
0x18001d4d6  lea     rcx, [rsp+1D0h+var_168]
0x18001d4db  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d4e0  lea     r8, [rsp+1D0h+var_168]
0x18001d4e5  mov     rdx, [rsp+1D0h+ppv]
0x18001d4ea  mov     rcx, rdi
0x18001d4ed  mov     rax, rbx
0x18001d4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4f5  mov     [rsp+1D0h+var_190], eax
0x18001d4f9  test    eax, eax
0x18001d4fb  mov     al, 1
0x18001d4fd  jns     short loc_18001D502
0x18001d4ff  mov     al, r14b
0x18001d502  test    sil, 4
0x18001d506  jz      short loc_18001D513
0x18001d508  and     esi, 0FFFFFFFBh
0x18001d50b  mov     [rsp+1D0h+var_180], esi
0x18001d50f  mov     [rbp+0D0h+var_140], r14
0x18001d513  test    sil, 2
0x18001d517  jz      short loc_18001D524
0x18001d519  and     esi, 0FFFFFFFDh
0x18001d51c  mov     [rsp+1D0h+var_180], esi
0x18001d520  mov     [rbp+0D0h+var_120], r14
0x18001d524  test    sil, 1
0x18001d528  jz      short loc_18001D535
0x18001d52a  and     esi, 0FFFFFFFEh
0x18001d52d  mov     [rsp+1D0h+var_180], esi
0x18001d531  mov     [rbp+0D0h+var_100], r14
0x18001d535  test    al, al
0x18001d537  jz      short loc_18001D53E
0x18001d539  mov     [rsp+1D0h+var_190], r14d
0x18001d53e  lea     rcx, [rsp+1D0h+var_168]
0x18001d543  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d548  nop
0x18001d549  lea     rcx, [rsp+1D0h+ppv]
0x18001d54e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d553  nop
0x18001d554  lea     rcx, [rsp+1D0h+var_170]
0x18001d559  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d55e  nop
0x18001d55f  lea     rcx, [rsp+1D0h+var_178]
0x18001d564  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d569  jmp     loc_18001D8BA
0x18001d56e  mov     [rsp+1D0h+bIgnoreCase], r14d; bIgnoreCase
0x18001d573  mov     r9d, edi; cchCount2
0x18001d576  lea     r8, aCommandLaunchs; "command:LaunchSystemStorage"
0x18001d57d  mov     edx, edi; cchCount1
0x18001d57f  mov     rcx, rbx; lpString1
0x18001d582  call    cs:__imp_CompareStringOrdinal
0x18001d588  cmp     eax, 2
0x18001d58b  jnz     loc_18001D6BF
0x18001d591  mov     [rsp+1D0h+ppv], r14
0x18001d596  movaps  xmm0, xmmword ptr cs:aPageSettingspa_1; "page=SettingsPageStorageSenseStorageOve"...
0x18001d59d  movups  [rbp+0D0h+var_F0], xmm0
0x18001d5a1  movaps  xmm1, xmmword ptr cs:aPageSettingspa_1+10h; "tingsPageStorageSenseStorageOverview&ta"...
0x18001d5a8  movups  [rbp+0D0h+var_E0], xmm1
0x18001d5ac  movaps  xmm0, xmmword ptr cs:aPageSettingspa_1+20h; "eStorageSenseStorageOverview&target=Sys"...
0x18001d5b3  movups  [rbp+0D0h+var_D0], xmm0
0x18001d5b7  movaps  xmm1, xmmword ptr cs:aPageSettingspa_1+30h; "SenseStorageOverview&target=SystemSetti"...
0x18001d5be  movups  [rbp+0D0h+var_C0], xmm1
0x18001d5c2  movaps  xmm0, xmmword ptr cs:aPageSettingspa_1+40h; "rageOverview&target=SystemSettings_Stor"...
0x18001d5c9  movups  [rbp+0D0h+var_B0], xmm0
0x18001d5cd  movaps  xmm1, xmmword ptr cs:aPageSettingspa_1+50h; "view&target=SystemSettings_StorageSense"...
0x18001d5d4  movups  [rbp+0D0h+var_A0], xmm1
0x18001d5d8  movaps  xmm0, xmmword ptr cs:aPageSettingspa_1+60h; "get=SystemSettings_StorageSense_SystemD"...
0x18001d5df  movups  [rbp+0D0h+var_90], xmm0
0x18001d5e3  movaps  xmm1, xmmword ptr cs:aPageSettingspa_1+70h; "emSettings_StorageSense_SystemDrive&inv"...
0x18001d5ea  movups  [rbp+0D0h+var_80], xmm1
0x18001d5ee  movaps  xmm0, xmmword ptr cs:aPageSettingspa_1+80h; "gs_StorageSense_SystemDrive&invoke=true"
0x18001d5f5  movups  [rbp+0D0h+var_70], xmm0
0x18001d5f9  movaps  xmm1, xmmword ptr cs:aPageSettingspa_1+90h; "geSense_SystemDrive&invoke=true"
0x18001d600  movups  [rbp+0D0h+var_60], xmm1
0x18001d604  movaps  xmm0, xmmword ptr cs:aPageSettingspa_1+0A0h; "SystemDrive&invoke=true"
0x18001d60b  movups  [rbp+0D0h+var_50], xmm0
0x18001d612  movaps  xmm1, xmmword ptr cs:aPageSettingspa_1+0B0h; "ive&invoke=true"
0x18001d619  movups  [rbp+0D0h+var_40], xmm1
0x18001d620  movaps  xmm0, xmmword ptr cs:aPageSettingspa_1+0C0h; "ke=true"
0x18001d627  movups  [rbp+0D0h+var_30], xmm0
0x18001d62e  mov     [rsp+1D0h+var_178], r14d
0x18001d633  lea     rcx, [rsp+1D0h+ppv]
0x18001d638  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d63d  lea     rax, [rsp+1D0h+ppv]
0x18001d642  mov     qword ptr [rsp+1D0h+bIgnoreCase], rax; ppv
0x18001d647  lea     r9, _GUID_2e941141_7f97_4756_ba1d_9decde894a3d; riid
0x18001d64e  xor     edx, edx; pUnkOuter
0x18001d650  lea     r8d, [rdx+4]; dwClsContext
0x18001d654  lea     rcx, CLSID_ApplicationActivationManager; rclsid
0x18001d65b  call    cs:__imp_CoCreateInstance
0x18001d661  mov     [rsp+1D0h+var_190], eax
0x18001d665  test    eax, eax
0x18001d667  js      short loc_18001D6B0
0x18001d669  xor     edx, edx; lpvReserved
0x18001d66b  mov     rcx, [rsp+1D0h+ppv]; pUnk
0x18001d670  call    cs:__imp_CoAllowSetForegroundWindow
0x18001d676  mov     [rsp+1D0h+var_190], eax
0x18001d67a  test    eax, eax
0x18001d67c  js      short loc_18001D6B0
0x18001d67e  mov     rcx, [rsp+1D0h+ppv]
0x18001d683  mov     rax, [rcx]
0x18001d686  lea     rdx, [rsp+1D0h+var_178]
0x18001d68b  mov     qword ptr [rsp+1D0h+bIgnoreCase], rdx
0x18001d690  xor     r9d, r9d
0x18001d693  lea     r8, [rbp+0D0h+var_F0]
0x18001d697  lea     rdx, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x18001d69e  mov     rax, [rax+18h]
0x18001d6a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6a7  test    eax, eax
0x18001d6a9  js      short loc_18001D6B0
0x18001d6ab  mov     [rsp+1D0h+var_190], r14d
0x18001d6b0  lea     rcx, [rsp+1D0h+ppv]
0x18001d6b5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d6ba  jmp     loc_18001D8BA
0x18001d6bf  mov     [rsp+1D0h+bIgnoreCase], r14d; bIgnoreCase
0x18001d6c4  mov     r9d, edi; cchCount2
0x18001d6c7  lea     r8, aCommandCloudag_0; "command:CloudAgeOut_Enable"
0x18001d6ce  mov     edx, edi; cchCount1
0x18001d6d0  mov     rcx, rbx; lpString1
0x18001d6d3  call    cs:__imp_CompareStringOrdinal
0x18001d6d9  cmp     eax, 2
0x18001d6dc  jnz     loc_18001D7E0
0x18001d6e2  mov     [rsp+1D0h+var_178], r14d
0x18001d6e7  lea     r9, [rsp+1D0h+var_178]; unsigned int *
0x18001d6ec  lea     r8, aCloudconsentto; "CloudConsentToastCount"
0x18001d6f3  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001d6fa  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18001d701  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001d706  mov     eax, cs:dword_1800BF000
0x18001d70c  cmp     eax, 5
0x18001d70f  jbe     short loc_18001D77D
0x18001d711  mov     rdx, 400000000000h
0x18001d71b  lea     rcx, dword_1800BF000
0x18001d722  call    _tlgKeywordOn
0x18001d727  test    al, al
0x18001d729  jz      short loc_18001D77D
0x18001d72b  mov     eax, [rsp+1D0h+var_178]
0x18001d72f  mov     dword ptr [rsp+1D0h+var_170], eax
0x18001d733  mov     dword ptr [rsp+1D0h+var_168], r14d
0x18001d738  mov     dword ptr [rsp+1D0h+ppv], 4
0x18001d740  mov     qword ptr [rsp+1D0h+var_160], 1000000h
0x18001d749  lea     rax, [rsp+1D0h+var_170]
0x18001d74e  mov     [rsp+1D0h+var_198], rax
0x18001d753  lea     rax, [rsp+1D0h+var_168]
0x18001d758  mov     [rsp+1D0h+var_1A0], rax
0x18001d75d  lea     rax, [rsp+1D0h+ppv]
0x18001d762  mov     [rsp+1D0h+var_1A8], rax
0x18001d767  lea     rax, [rsp+1D0h+var_160]
0x18001d76c  mov     qword ptr [rsp+1D0h+bIgnoreCase], rax; int
0x18001d771  lea     rdx, word_1800A5882
0x18001d778  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001d77d  mov     r9d, 3; unsigned int
0x18001d783  lea     r8, aCloudconsentto; "CloudConsentToastCount"
0x18001d78a  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001d791  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18001d796  mov     r9d, 1; unsigned int
0x18001d79c  lea     r8, aCloudfilepolic; "CloudfilePolicyConsent"
0x18001d7a3  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001d7aa  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18001d7af  call    ??$QueueTask@V_lambda_aaac285f1682a49811d03760bad078e8_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_aaac285f1682a49811d03760bad078e8_@@@Z; Windows::Internal::ComTaskPool::QueueTask<_lambda_aaac285f1682a49811d03760bad078e8_>(Windows::Internal::TaskApartment,_lambda_aaac285f1682a49811d03760bad078e8_ &&)
0x18001d7b4  mov     ebx, eax
0x18001d7b6  test    eax, eax
0x18001d7b8  jns     loc_18001D8BA
0x18001d7be  mov     rcx, [rbp+0D8h]; this
0x18001d7c5  mov     r9d, eax; char *
0x18001d7c8  lea     r8, aOnecoreDrivers_7; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18001d7cf  mov     edx, 5D4h; void *
0x18001d7d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d7d9  mov     eax, ebx
0x18001d7db  jmp     loc_18001D8BC
0x18001d7e0  mov     [rsp+1D0h+bIgnoreCase], r14d; bIgnoreCase
0x18001d7e5  mov     r9d, edi; cchCount2
0x18001d7e8  lea     r8, aCommandCloudag; "command:CloudAgeOut_Dismiss"
0x18001d7ef  mov     edx, edi; cchCount1
0x18001d7f1  mov     rcx, rbx; lpString1
0x18001d7f4  call    cs:__imp_CompareStringOrdinal
0x18001d7fa  cmp     eax, 2
0x18001d7fd  jnz     loc_18001D8BA
0x18001d803  mov     [rsp+1D0h+var_178], r14d
0x18001d808  lea     r9, [rsp+1D0h+var_178]; unsigned int *
0x18001d80d  lea     r8, aCloudconsentto; "CloudConsentToastCount"
0x18001d814  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001d81b  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18001d822  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001d827  mov     eax, cs:dword_1800BF000
  ... truncated ...
```
