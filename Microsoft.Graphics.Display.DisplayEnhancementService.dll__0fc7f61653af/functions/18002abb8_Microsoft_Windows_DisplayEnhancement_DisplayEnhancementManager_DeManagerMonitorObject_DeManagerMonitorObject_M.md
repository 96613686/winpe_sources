# Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerMonitorObject::DeManagerMonitorObject(Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerObjectLifetimeManagerImpl *,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapter> const &,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroup> const &,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinator> const &)

- ea: `0x18002abb8`
- end: `0x18002af47`
- name: `??0DeManagerMonitorObject@DisplayEnhancementManager@DisplayEnhancement@Windows@Microsoft@@QEAA@PEAVDeManagerObjectLifetimeManagerImpl@1234@AEBV?$shared_ptr@VMonitorAdapter@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$shared_ptr@VDeManagementServerSettingsGroup@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@7@AEBV?$shared_ptr@VDeRequestCoordinator@Coordinator@DisplayEnhancement@Windows@Microsoft@@@7@@Z`
- size: `911`
- prototype: `__int64 __usercall@<rax>(char@<cl>, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002d4dc`

## callees

- `0x180005860`
- `0x180009f68`
- `0x18000f778`
- `0x18000fb14`
- `0x180011fe8`
- `0x180013578`
- `0x180019cac`
- `0x18002abb8`
- `0x18002c460`
- `0x18002ea20`
- `0x180063c54`
- `0x1800847b4`
- `0x1800ed010`

## import_xrefs

- `ntdll!NtUpdateWnfStateData` at `0x18002ae50`
- `ntdll!NtUpdateWnfStateData` at `0x18002ae50`
- `ntdll!RtlAllocateWnfSerializationGroup` at `0x18002ac31`
- `ntdll!RtlAllocateWnfSerializationGroup` at `0x18002ac31`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerMonitorObject::DeManagerMonitorObject(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 *a4,
        __int64 a5)
{
  _QWORD *v9; // rbx
  _QWORD *Shared; // rax
  __int64 v11; // rdi
  void (__fastcall *v12)(__int64, void ***); // rbx
  _QWORD *BrightnessCapabilities; // rax
  _QWORD *v14; // rax
  int v15; // edi
  char v16; // bl
  __int64 *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // r10
  __int64 v24; // r9
  int v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+28h] [rbp-D8h]
  int v28; // [rsp+30h] [rbp-D0h]
  int v29; // [rsp+38h] [rbp-C8h]
  int v30; // [rsp+40h] [rbp-C0h]
  char v31[8]; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v32; // [rsp+88h] [rbp-78h] BYREF
  void **v33; // [rsp+98h] [rbp-68h] BYREF
  std::_Ref_count_base *v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  char v36[4]; // [rsp+B0h] [rbp-50h] BYREF
  char v37[4]; // [rsp+B4h] [rbp-4Ch]
  char v38[8]; // [rsp+B8h] [rbp-48h]
  _BYTE v39[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v40[32]; // [rsp+E0h] [rbp-20h] BYREF

  v35 = a1;
  *(_QWORD *)a1 = &Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerMonitorObject::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 96) = RtlAllocateWnfSerializationGroup();
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = a2;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>(
    a1 + 160,
    a4);
  v9 = (_QWORD *)(a1 + 176);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>(
    a1 + 176,
    a3);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>(
    a1 + 192,
    a5);
  *(_QWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 216) = 0;
  *(_QWORD *)(a1 + 224) = 0;
  *(_QWORD *)(a1 + 232) = 0;
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  *(_QWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 280) = 0;
  *(struct _GUID *)(a1 + 288) = *Microsoft::Windows::DisplayEnhancement::Foundation::GuidFactory::GetNextId(&v32);
  *(_BYTE *)(a1 + 304) = 0;
  (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 72LL))(*a3, a1 + 312);
  Shared = (_QWORD *)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::GetOrMakeShared(&v32);
  *(_BYTE *)(a1 + 328) = *(_BYTE *)(*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void ***))(*(_QWORD *)*Shared + 176LL))(
                                                 *Shared,
                                                 &v33)
                                  + 8LL);
  if ( v34 )
    std::_Ref_count_base::_Decref(v34);
  if ( *(_QWORD *)v32.Data4 )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v32.Data4);
  (*(void (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v9 + 16LL))(*v9, v39);
  (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v9 + 64LL))(*v9, v36);
  (**(void (__fastcall ***)(_QWORD, _BYTE *))*v9)(*v9, v40);
  v11 = *a4;
  v12 = *(void (__fastcall **)(__int64, void ***))(*(_QWORD *)*a4 + 312LL);
  BrightnessCapabilities = (_QWORD *)Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerMonitorObject::GetBrightnessCapabilities(
                                       a1,
                                       &v32);
  LOBYTE(v34) = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*BrightnessCapabilities + 8LL))(*BrightnessCapabilities) != 0;
  HIDWORD(v34) = 4;
  v33 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v12(v11, &v33);
  if ( *(_QWORD *)v32.Data4 )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v32.Data4);
  v14 = (_QWORD *)Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerMonitorObject::GetBrightnessCapabilities(
                    a1,
                    &v32);
  v15 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
  if ( *(_QWORD *)v32.Data4 )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v32.Data4);
  v16 = 1;
  if ( v15 )
  {
    v31[0] = 1;
    v28 = 0;
    v27 = 0;
    v26 = 0;
    NtUpdateWnfStateData(&WNF_PO_DYNAMIC_BRIGHTNESS_SLIDER, v31, 1);
  }
  v17 = (__int64 *)Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::GetOrMakeShared(&v32, v39);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    (_QWORD *)(a1 + 272),
    v17);
  if ( *(_QWORD *)v32.Data4 )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v32.Data4);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v16 = 0;
  }
  if ( v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40, v18, v19);
    v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39, v20, v21);
    WPP_RECORDER_AND_TRACE_SF_sLldSS_guid_q(
      *(_QWORD *)(v23 + 16),
      v26,
      v27,
      v28,
      v29,
      v30,
      v36[0],
      v37[0],
      v38[0],
      v22,
      v24,
      a1 + 288,
      a1);
  }
  std::wstring::_Tidy_deallocate(v40);
  std::wstring::_Tidy_deallocate(v39);
  return a1;
}

```

## disassembly

```asm
0x18002abb8  mov     [rsp-8+arg_8], rbx
0x18002abbd  push    rbp
0x18002abbe  push    rsi
0x18002abbf  push    rdi
0x18002abc0  push    r12
0x18002abc2  push    r13
0x18002abc4  push    r14
0x18002abc6  push    r15
0x18002abc8  lea     rbp, [rsp-10h]
0x18002abcd  sub     rsp, 110h
0x18002abd4  mov     rax, cs:__security_cookie
0x18002abdb  xor     rax, rsp
0x18002abde  mov     [rbp+40h+var_40], rax
0x18002abe2  mov     r13, r9
0x18002abe5  mov     rsi, r8
0x18002abe8  mov     rbx, rdx
0x18002abeb  mov     r14, rcx
0x18002abee  mov     [rbp+40h+var_98], rcx
0x18002abf2  mov     rdi, [rbp+40h+arg_20]
0x18002abf6  lea     rax, ??_7DeManagerMonitorObject@DisplayEnhancementManager@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerMonitorObject::`vftable'
0x18002abfd  mov     [rcx], rax
0x18002ac00  xor     r12d, r12d
0x18002ac03  mov     [rcx+8], r12
0x18002ac07  mov     [rcx+10h], r12
0x18002ac0b  xor     eax, eax
0x18002ac0d  mov     [rcx+18h], rax
0x18002ac11  mov     [rcx+20h], r12
0x18002ac15  mov     [rcx+28h], r12
0x18002ac19  mov     [rcx+30h], r12
0x18002ac1d  mov     [rcx+38h], r12
0x18002ac21  mov     [rcx+40h], r12
0x18002ac25  mov     [rcx+48h], r12
0x18002ac29  mov     [rcx+50h], r12
0x18002ac2d  mov     [rcx+58h], r12
0x18002ac31  call    cs:__imp_RtlAllocateWnfSerializationGroup
0x18002ac37  mov     [r14+60h], eax
0x18002ac3b  mov     [r14+68h], r12
0x18002ac3f  mov     [r14+70h], rbx
0x18002ac43  mov     [r14+78h], r12
0x18002ac47  mov     [r14+80h], r12
0x18002ac4e  mov     [r14+88h], r12
0x18002ac55  mov     [r14+90h], r12
0x18002ac5c  mov     [r14+98h], r12
0x18002ac63  lea     rcx, [r14+0A0h]
0x18002ac6a  mov     rdx, r13
0x18002ac6d  call    ??0?$shared_ptr@V?$OEMSetting@E@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>> const &)
0x18002ac72  nop
0x18002ac73  lea     rbx, [r14+0B0h]
0x18002ac7a  mov     rdx, rsi
0x18002ac7d  mov     rcx, rbx
0x18002ac80  call    ??0?$shared_ptr@V?$OEMSetting@E@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>> const &)
0x18002ac85  nop
0x18002ac86  lea     rcx, [r14+0C0h]
0x18002ac8d  mov     rdx, rdi
0x18002ac90  call    ??0?$shared_ptr@V?$OEMSetting@E@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>> const &)
0x18002ac95  nop
0x18002ac96  mov     [r14+0D0h], r12
0x18002ac9d  mov     [r14+0D8h], r12
0x18002aca4  mov     [r14+0E0h], r12
0x18002acab  mov     [r14+0E8h], r12
0x18002acb2  mov     [r14+0F0h], r12
0x18002acb9  mov     [r14+0F8h], r12
0x18002acc0  mov     [r14+100h], r12
0x18002acc7  mov     [r14+108h], r12
0x18002acce  lea     r15, [r14+110h]
0x18002acd5  mov     [r15], r12
0x18002acd8  mov     [r15+8], r12
0x18002acdc  lea     r12, [r14+120h]
0x18002ace3  lea     rcx, [rbp+40h+var_B8]; retstr
0x18002ace7  call    ?GetNextId@GuidFactory@Foundation@DisplayEnhancement@Windows@Microsoft@@SA?AU_GUID@@XZ; Microsoft::Windows::DisplayEnhancement::Foundation::GuidFactory::GetNextId(void)
0x18002acec  movups  xmm0, xmmword ptr [rax]
0x18002acef  movdqu  xmmword ptr [r12], xmm0
0x18002acf5  mov     byte ptr [r14+130h], 0
0x18002acfd  mov     rcx, [rsi]
0x18002ad00  mov     rax, [rcx]
0x18002ad03  lea     rdx, [r14+138h]
0x18002ad0a  mov     rax, [rax+48h]
0x18002ad0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad13  nop
0x18002ad14  lea     rcx, [rbp+40h+var_B8]
0x18002ad18  call    ?GetOrMakeShared@OEMSettingsManager@OEMSettings@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VOEMSettingsManager@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::GetOrMakeShared(void)
0x18002ad1d  nop
0x18002ad1e  mov     rcx, [rax]
0x18002ad21  mov     rax, [rcx]
0x18002ad24  lea     rdx, [rbp+40h+var_A8]
0x18002ad28  mov     rax, [rax+0B0h]
0x18002ad2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad34  mov     rcx, [rax]
0x18002ad37  mov     al, [rcx+8]
0x18002ad3a  mov     [r14+148h], al
0x18002ad41  mov     rcx, [rbp+40h+var_A0]; this
0x18002ad45  xor     esi, esi
0x18002ad47  test    rcx, rcx
0x18002ad4a  jz      short loc_18002AD52
0x18002ad4c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002ad51  nop
0x18002ad52  mov     rcx, qword ptr [rbp+40h+var_B8.Data4]; this
0x18002ad56  test    rcx, rcx
0x18002ad59  jz      short loc_18002AD60
0x18002ad5b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002ad60  mov     rcx, [rbx]
0x18002ad63  mov     rax, [rcx]
0x18002ad66  lea     rdx, [rbp+40h+var_80]
0x18002ad6a  mov     rax, [rax+10h]
0x18002ad6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad73  nop
0x18002ad74  mov     rcx, [rbx]
0x18002ad77  mov     rax, [rcx]
0x18002ad7a  lea     rdx, [rbp+40h+var_90]
0x18002ad7e  mov     rax, [rax+40h]
0x18002ad82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad87  mov     rcx, [rbx]
0x18002ad8a  mov     rax, [rcx]
0x18002ad8d  lea     rdx, [rbp+40h+var_60]
0x18002ad91  mov     rax, [rax]
0x18002ad94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad99  nop
0x18002ad9a  mov     rdi, [r13+0]
0x18002ad9e  mov     rax, [rdi]
0x18002ada1  mov     rbx, [rax+138h]
0x18002ada8  lea     rdx, [rbp+40h+var_B8]
0x18002adac  mov     rcx, r14
0x18002adaf  call    ?GetBrightnessCapabilities@DeManagerMonitorObject@DisplayEnhancementManager@DisplayEnhancement@Windows@Microsoft@@UEAA?AV?$shared_ptr@VBrightnessCapabilityWrapper@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerMonitorObject::GetBrightnessCapabilities(void)
0x18002adb4  nop
0x18002adb5  mov     rcx, [rax]
0x18002adb8  mov     rax, [rcx]
0x18002adbb  mov     rax, [rax+8]
0x18002adbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adc4  test    eax, eax
0x18002adc6  setnz   byte ptr [rbp+40h+var_A0]
0x18002adca  mov     dword ptr [rbp+40h+var_A0+4], 4
0x18002add1  lea     rax, ??_7DeManagementFloatSettingType@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable'
0x18002add8  mov     [rbp+40h+var_A8], rax
0x18002addc  lea     rdx, [rbp+40h+var_A8]
0x18002ade0  mov     rcx, rdi
0x18002ade3  mov     rax, rbx
0x18002ade6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adeb  nop
0x18002adec  mov     rcx, qword ptr [rbp+40h+var_B8.Data4]; this
0x18002adf0  test    rcx, rcx
0x18002adf3  jz      short loc_18002ADFA
0x18002adf5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002adfa  lea     rdx, [rbp+40h+var_B8]
0x18002adfe  mov     rcx, r14
0x18002ae01  call    ?GetBrightnessCapabilities@DeManagerMonitorObject@DisplayEnhancementManager@DisplayEnhancement@Windows@Microsoft@@UEAA?AV?$shared_ptr@VBrightnessCapabilityWrapper@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerMonitorObject::GetBrightnessCapabilities(void)
0x18002ae06  nop
0x18002ae07  mov     rcx, [rax]
0x18002ae0a  mov     rax, [rcx]
0x18002ae0d  mov     rax, [rax+8]
0x18002ae11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae16  mov     edi, eax
0x18002ae18  mov     rcx, qword ptr [rbp+40h+var_B8.Data4]; this
0x18002ae1c  test    rcx, rcx
0x18002ae1f  jz      short loc_18002AE26
0x18002ae21  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002ae26  mov     ebx, 1
0x18002ae2b  test    edi, edi
0x18002ae2d  jz      short loc_18002AE56
0x18002ae2f  mov     [rbp+40h+var_C0], bl
0x18002ae32  mov     [rsp+140h+var_110], esi; int
0x18002ae36  mov     [rsp+140h+var_118], esi; int
0x18002ae3a  mov     qword ptr [rsp+140h+var_120], rsi; int
0x18002ae3f  xor     r9d, r9d
0x18002ae42  mov     r8d, ebx
0x18002ae45  lea     rdx, [rbp+40h+var_C0]
0x18002ae49  lea     rcx, WNF_PO_DYNAMIC_BRIGHTNESS_SLIDER
0x18002ae50  call    cs:__imp_NtUpdateWnfStateData
0x18002ae56  lea     rdx, [rbp+40h+var_80]
0x18002ae5a  lea     rcx, [rbp+40h+var_B8]
0x18002ae5e  call    ?GetOrMakeShared@DesTelemetry@Telemetry@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDesTelemetry@Telemetry@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::GetOrMakeShared(std::wstring const &)
0x18002ae63  mov     rdx, rax
0x18002ae66  mov     rcx, r15
0x18002ae69  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x18002ae6e  mov     rcx, qword ptr [rbp+40h+var_B8.Data4]; this
0x18002ae72  test    rcx, rcx
0x18002ae75  jz      short loc_18002AE7C
0x18002ae77  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002ae7c  lea     rax, WPP_GLOBAL_Control
0x18002ae83  mov     r10, cs:WPP_GLOBAL_Control
0x18002ae8a  cmp     r10, rax
0x18002ae8d  jz      short loc_18002AE9D
0x18002ae8f  test    byte ptr [r10+1Ch], 20h
0x18002ae94  jz      short loc_18002AE9D
0x18002ae96  cmp     byte ptr [r10+19h], 4
0x18002ae9b  jnb     short loc_18002AEA0
0x18002ae9d  mov     bl, sil
0x18002aea0  lea     rax, WPP_RECORDER_INITIALIZED
0x18002aea7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002aeae  setnz   r8b
0x18002aeb2  test    bl, bl
0x18002aeb4  jnz     short loc_18002AEBB
0x18002aeb6  test    r8b, r8b
0x18002aeb9  jz      short loc_18002AF09
0x18002aebb  lea     rcx, [rbp+40h+var_60]
0x18002aebf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002aec4  mov     r9, rax
0x18002aec7  lea     rcx, [rbp+40h+var_80]
0x18002aecb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002aed0  mov     qword ptr [rsp+140h+var_C8], r14; char
0x18002aed5  mov     [rsp+140h+var_D0], r12; __int64
0x18002aeda  mov     [rsp+140h+var_D8], r9; __int64
0x18002aedf  mov     [rsp+140h+var_E0], rax; __int64
0x18002aee4  mov     eax, dword ptr [rbp+40h+var_88]
0x18002aee7  mov     dword ptr [rsp+140h+var_E8], eax; char
0x18002aeeb  mov     eax, dword ptr [rbp+40h+var_8C]
0x18002aeee  mov     dword ptr [rsp+140h+var_F0], eax; char
0x18002aef2  mov     eax, dword ptr [rbp+40h+var_90]
0x18002aef5  mov     dword ptr [rsp+140h+var_F8], eax; char
0x18002aef9  mov     r9, [r10+28h]
0x18002aefd  mov     dl, bl
0x18002aeff  mov     rcx, [r10+10h]; LoggerHandle
0x18002af03  call    WPP_RECORDER_AND_TRACE_SF_sLldSS_guid_q
0x18002af08  nop
0x18002af09  lea     rcx, [rbp+40h+var_60]
0x18002af0d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002af12  nop
0x18002af13  lea     rcx, [rbp+40h+var_80]
0x18002af17  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002af1c  nop
0x18002af1d  mov     rax, r14
0x18002af20  mov     rcx, [rbp+40h+var_40]
0x18002af24  xor     rcx, rsp; StackCookie
0x18002af27  call    __security_check_cookie
0x18002af2c  mov     rbx, [rsp+140h+arg_8]
0x18002af34  add     rsp, 110h
0x18002af3b  pop     r15
0x18002af3d  pop     r14
0x18002af3f  pop     r13
0x18002af41  pop     r12
0x18002af43  pop     rdi
0x18002af44  pop     rsi
0x18002af45  pop     rbp
0x18002af46  retn
```
