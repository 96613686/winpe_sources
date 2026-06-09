# CProcessStateManager::_RefreshActiveUserSettings(void)

- ea: `0x1800268e0`
- end: `0x180026b19`
- name: `?_RefreshActiveUserSettings@CProcessStateManager@@AEAAXXZ`
- size: `569`
- prototype: `void __fastcall(CProcessStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000fd2c`

## callees

- `0x18000df10`
- `0x1800140c8`
- `0x180014a34`
- `0x180014ce4`
- `0x1800268e0`
- `0x180026e70`
- `0x180026ec4`
- `0x18002bc20`
- `0x18002dec4`
- `0x18002e18c`
- `0x180040a6c`
- `0x18004ae38`
- `0x18007eda4`
- `0x18009d010`

## import_xrefs

- `CredProvCommonCore!__imp_?IsFirstBoot@@YA_NXZ` at `0x1800269de`
- `CredProvCommonCore!__imp_?IsFirstBoot@@YA_NXZ` at `0x1800269de`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002696e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002696e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026acd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026acd`
- `UxTheme!__imp_GetDefaultColorPreference` at `0x18002692d`
- `UxTheme!__imp_GetDefaultColorPreference` at `0x18002692d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendNotifyMessageW` at `0x180026a3e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendNotifyMessageW` at `0x180026a3e`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180026911`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180026a05`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180026911`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180026a05`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180026a9e`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180026a9e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CProcessStateManager::_RefreshActiveUserSettings(CProcessStateManager *this)
{
  char v2; // bl
  __int64 v3; // rdi
  char IsHighContrast; // si
  __int64 v5; // rcx
  CUserSettingChangeMonitor *v6; // rcx
  const unsigned __int16 *StringRawBuffer; // rax
  CUserColorData *v8; // rcx
  int pvParam; // [rsp+20h] [rbp-10h] BYREF
  __int64 v10; // [rsp+24h] [rbp-Ch]
  int v11; // [rsp+2Ch] [rbp-4h]
  CUserColorData *v12; // [rsp+50h] [rbp+20h] BYREF
  RTL_SRWLOCK *v13; // [rsp+58h] [rbp+28h] BYREF
  PSRWLOCK SRWLock; // [rsp+60h] [rbp+30h] BYREF

  v2 = 0;
  pvParam = 16;
  v10 = 0;
  v11 = 0;
  if ( SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0) )
    v2 = v10 & 1;
  v13 = 0;
  GetDefaultColorPreference(&v13);
  v12 = 0;
  if ( *((_QWORD *)this + 53) )
  {
    IsHighContrast = 0;
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v12);
    if ( CProcessStateManager::_GetColorDataForUser(this, *((HSTRING *)this + 53), &v12) >= 0 )
    {
      v13 = *(RTL_SRWLOCK **)CUserColorData::GetColorPreference(v12, &SRWLock);
      IsHighContrast = CUserColorData::IsHighContrast(v12);
    }
    if ( v2 != IsHighContrast )
    {
      LODWORD(v10) = v10 ^ 1;
      v2 = 1;
    }
    if ( (!*((_BYTE *)this + 105) || !IsFirstBoot()) && !*((_BYTE *)this + 561) )
    {
      if ( v2 )
      {
        SystemParametersInfoW(0x43u, 0x10u, &pvParam, 0);
        v5 = *((_QWORD *)this + 26);
        if ( v5 )
        {
          CUserColorData::GetColorPreference(v5, &SRWLock);
          if ( SRWLock == v13 )
            SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0x43u, 0);
        }
      }
    }
    v6 = (CUserSettingChangeMonitor *)*((_QWORD *)this + 30);
    if ( v6 )
      CUserSettingChangeMonitor::StartListening(
        v6,
        (struct IUserSettingChangeCallback *)(((unsigned __int64)this + 40)
                                            & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
        *((HSTRING *)this + 53));
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<HSTRING__ *>>::operator=((char *)this + 208, &v12);
    CProcessStateManager::_SetPerUserColors(this);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonUINoUpdateUserInput>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_LogonUINoUpdateUserInput>::GetImpl'::`2'::impl);
    if ( *((_BYTE *)this + 537) && GetSystemMetrics(4096) != 1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 456);
      *((_QWORD *)this + 58) = -1;
      *((_QWORD *)this + 59) = -1;
      StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 53), 0);
      CLanguageProfileHelper::SetPerUserInputMethods(StringRawBuffer, (unsigned __int16 **)this + 57);
    }
    CProcessStateManager::_LoadAccessibilitySettingsForUser(this, *((HSTRING *)this + 53));
  }
  else
  {
    v3 = *((_QWORD *)this + 26);
    if ( v3 )
    {
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, v3 + 40);
      *(_BYTE *)(v3 + 48) = v2;
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      if ( v2 )
        LODWORD(v10) = v10 & 0xFFFFFFFE;
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v12);
    }
  }
  v8 = v12;
  if ( v12 )
  {
    v12 = 0;
    (*(void (__fastcall **)(CUserColorData *))(*(_QWORD *)v8 + 16LL))(v8);
  }
}

```

## disassembly

```asm
0x1800268e0  mov     [rsp-18h+arg_18], rbx
0x1800268e5  push    rbp
0x1800268e6  push    rsi
0x1800268e7  push    rdi
0x1800268e8  mov     rbp, rsp
0x1800268eb  sub     rsp, 30h
0x1800268ef  mov     rdi, rcx
0x1800268f2  xor     bl, bl
0x1800268f4  mov     [rbp+pvParam], 10h
0x1800268fb  xor     eax, eax
0x1800268fd  mov     [rbp+var_C], rax
0x180026901  mov     [rbp+var_4], eax
0x180026904  xor     r9d, r9d; fWinIni
0x180026907  lea     r8, [rbp+pvParam]; pvParam
0x18002690b  lea     edx, [rax+10h]; uiParam
0x18002690e  lea     ecx, [rax+42h]; uiAction
0x180026911  call    cs:__imp_SystemParametersInfoW
0x180026917  test    eax, eax
0x180026919  jz      short loc_180026921
0x18002691b  mov     bl, byte ptr [rbp+var_C]
0x18002691e  and     bl, 1
0x180026921  mov     [rbp+arg_8], 0
0x180026929  lea     rcx, [rbp+arg_8]
0x18002692d  call    cs:__imp_GetDefaultColorPreference
0x180026933  mov     [rbp+arg_0], 0
0x18002693b  cmp     qword ptr [rdi+1A8h], 0
0x180026943  jnz     short loc_18002698A
0x180026945  mov     rdi, [rdi+0D0h]
0x18002694c  test    rdi, rdi
0x18002694f  jz      loc_180026AEE
0x180026955  lea     rdx, [rdi+28h]
0x180026959  lea     rcx, [rbp+SRWLock]
0x18002695d  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180026962  mov     [rdi+30h], bl
0x180026965  mov     rcx, [rbp+SRWLock]; SRWLock
0x180026969  test    rcx, rcx
0x18002696c  jz      short loc_180026974
0x18002696e  call    cs:__imp_ReleaseSRWLockExclusive
0x180026974  test    bl, bl
0x180026976  jz      short loc_18002697C
0x180026978  and     dword ptr [rbp+var_C], 0FFFFFFFEh
0x18002697c  lea     rcx, [rbp+arg_0]
0x180026980  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180026985  jmp     loc_180026AEE
0x18002698a  xor     sil, sil
0x18002698d  lea     rcx, [rbp+arg_0]
0x180026991  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180026996  lea     r8, [rbp+arg_0]; struct CUserColorData **
0x18002699a  mov     rdx, [rdi+1A8h]; HSTRING
0x1800269a1  mov     rcx, rdi; this
0x1800269a4  call    ?_GetColorDataForUser@CProcessStateManager@@AEAAJPEAUHSTRING__@@PEAPEAVCUserColorData@@@Z; CProcessStateManager::_GetColorDataForUser(HSTRING__ *,CUserColorData * *)
0x1800269a9  test    eax, eax
0x1800269ab  js      short loc_1800269CD
0x1800269ad  lea     rdx, [rbp+SRWLock]
0x1800269b1  mov     rcx, [rbp+arg_0]
0x1800269b5  call    ?GetColorPreference@CUserColorData@@QEAA?AUIMMERSIVE_COLOR_PREFERENCE@@XZ; CUserColorData::GetColorPreference(void)
0x1800269ba  mov     rcx, [rax]
0x1800269bd  mov     [rbp+arg_8], rcx
0x1800269c1  mov     rcx, [rbp+arg_0]; this
0x1800269c5  call    ?IsHighContrast@CUserColorData@@QEAA_NXZ; CUserColorData::IsHighContrast(void)
0x1800269ca  mov     sil, al
0x1800269cd  cmp     bl, sil
0x1800269d0  jz      short loc_1800269D8
0x1800269d2  xor     dword ptr [rbp+var_C], 1
0x1800269d6  mov     bl, 1
0x1800269d8  cmp     byte ptr [rdi+69h], 0
0x1800269dc  jz      short loc_1800269E8
0x1800269de  call    cs:__imp_?IsFirstBoot@@YA_NXZ; IsFirstBoot(void)
0x1800269e4  test    al, al
0x1800269e6  jnz     short loc_180026A44
0x1800269e8  cmp     byte ptr [rdi+231h], 0
0x1800269ef  jnz     short loc_180026A44
0x1800269f1  test    bl, bl
0x1800269f3  jz      short loc_180026A44
0x1800269f5  xor     r9d, r9d; fWinIni
0x1800269f8  lea     r8, [rbp+pvParam]; pvParam
0x1800269fc  lea     edx, [r9+10h]; uiParam
0x180026a00  lea     ebx, [rdx+33h]
0x180026a03  mov     ecx, ebx; uiAction
0x180026a05  call    cs:__imp_SystemParametersInfoW
0x180026a0b  mov     rcx, [rdi+0D0h]
0x180026a12  test    rcx, rcx
0x180026a15  jz      short loc_180026A44
0x180026a17  lea     rdx, [rbp+SRWLock]
0x180026a1b  call    ?GetColorPreference@CUserColorData@@QEAA?AUIMMERSIVE_COLOR_PREFERENCE@@XZ; CUserColorData::GetColorPreference(void)
0x180026a20  mov     eax, dword ptr [rbp+arg_8]
0x180026a23  cmp     dword ptr [rbp+SRWLock], eax
0x180026a26  jnz     short loc_180026A44
0x180026a28  mov     eax, dword ptr [rbp+arg_8+4]
0x180026a2b  cmp     dword ptr [rbp+SRWLock+4], eax
0x180026a2e  jnz     short loc_180026A44
0x180026a30  xor     r9d, r9d; lParam
0x180026a33  mov     r8d, ebx; wParam
0x180026a36  lea     edx, [rbx-29h]; Msg
0x180026a39  mov     ecx, 0FFFFh; hWnd
0x180026a3e  call    cs:__imp_SendNotifyMessageW
0x180026a44  mov     rcx, [rdi+0F0h]; this
0x180026a4b  test    rcx, rcx
0x180026a4e  jz      short loc_180026A6C
0x180026a50  mov     rax, rdi
0x180026a53  lea     r8, [rdi+28h]
0x180026a57  neg     rax
0x180026a5a  sbb     rdx, rdx
0x180026a5d  and     rdx, r8; struct IUserSettingChangeCallback *
0x180026a60  mov     r8, [rdi+1A8h]; HSTRING
0x180026a67  call    ?StartListening@CUserSettingChangeMonitor@@QEAAXPEAUIUserSettingChangeCallback@@PEAUHSTRING__@@@Z; CUserSettingChangeMonitor::StartListening(IUserSettingChangeCallback *,HSTRING__ *)
0x180026a6c  lea     rcx, [rdi+0D0h]
0x180026a73  lea     rdx, [rbp+arg_0]
0x180026a77  call    ??4?$ComPtr@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<HSTRING__ *>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<HSTRING__ *>> const &)
0x180026a7c  mov     rcx, rdi; this
0x180026a7f  call    ?_SetPerUserColors@CProcessStateManager@@AEAAXXZ; CProcessStateManager::_SetPerUserColors(void)
0x180026a84  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LogonUINoUpdateUserInput@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LogonUINoUpdateUserInput@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonUINoUpdateUserInput> `wil::Feature<__WilFeatureTraits_Feature_LogonUINoUpdateUserInput>::GetImpl(void)'::`2'::impl
0x180026a8b  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_LogonUINoUpdateUserInput@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonUINoUpdateUserInput>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180026a90  cmp     byte ptr [rdi+219h], 0
0x180026a97  jz      short loc_180026ADE
0x180026a99  mov     ecx, 1000h; nIndex
0x180026a9e  call    cs:__imp_GetSystemMetrics
0x180026aa4  cmp     eax, 1
0x180026aa7  jz      short loc_180026ADE
0x180026aa9  lea     rbx, [rdi+1C8h]
0x180026ab0  mov     rcx, rbx
0x180026ab3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180026ab8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026abc  mov     [rbx+8], rax
0x180026ac0  mov     [rbx+10h], rax
0x180026ac4  xor     edx, edx; length
0x180026ac6  mov     rcx, [rdi+1A8h]; string
0x180026acd  call    cs:__imp_WindowsGetStringRawBuffer
0x180026ad3  mov     rdx, rbx; unsigned __int16 **
0x180026ad6  mov     rcx, rax; unsigned __int16 *
0x180026ad9  call    ?SetPerUserInputMethods@CLanguageProfileHelper@@SAXPEBGPEAPEAG@Z; CLanguageProfileHelper::SetPerUserInputMethods(ushort const *,ushort * *)
0x180026ade  mov     rdx, [rdi+1A8h]; HSTRING
0x180026ae5  mov     rcx, rdi; this
0x180026ae8  call    ?_LoadAccessibilitySettingsForUser@CProcessStateManager@@AEAAXPEAUHSTRING__@@@Z; CProcessStateManager::_LoadAccessibilitySettingsForUser(HSTRING__ *)
0x180026aed  nop
0x180026aee  mov     rcx, [rbp+arg_0]
0x180026af2  test    rcx, rcx
0x180026af5  jz      short loc_180026B0C
0x180026af7  mov     [rbp+arg_0], 0
0x180026aff  mov     rax, [rcx]
0x180026b02  mov     rax, [rax+10h]
0x180026b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b0b  nop
0x180026b0c  mov     rbx, [rsp+30h+arg_18]
0x180026b11  add     rsp, 30h
0x180026b15  pop     rdi
0x180026b16  pop     rsi
0x180026b17  pop     rbp
0x180026b18  retn
```
