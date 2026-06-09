# SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::SetProperty(HSTRING__ *,IInspectable *)

- ea: `0x1800286d0`
- end: `0x180028852`
- name: `?SetProperty@CBatterySaverDynamicResolution@BatterySaverOneCoreDataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z`
- size: `386`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution *__hidden this, HSTRING, struct IInspectable *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000cfa4`
- `0x18000eacc`
- `0x180015cb8`
- `0x18001e5d4`
- `0x180023fb0`
- `0x18002570c`
- `0x1800286d0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002879a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800287f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002879a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800287f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::SetProperty(
        SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution *this,
        SystemSettings::DataModel *a2,
        struct IInspectable *a3)
{
  const unsigned __int16 *v6; // r8
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v15; // r8
  void *v16; // rax
  SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution *v17; // rcx
  int v18[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  HSTRING string; // [rsp+78h] [rbp+40h] BYREF

  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180056AA0, (const unsigned __int16 *)a3) )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180056B80, v6) )
    {
      LOBYTE(string) = 1;
      PowerAndBatteryTelemetry::DynamicResolutionChanged<unsigned int const &,bool>(*((_QWORD *)this + 28), &string);
      *((_QWORD *)this + 28) = SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::GetCurrentlyAppliedResolution(
                                 v17,
                                 0);
      *((_BYTE *)this + 232) = 1;
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180056AA0);
    }
    return 0;
  }
  string = 0;
  *(_QWORD *)v18 = 0;
  QueryInterface = a3->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v18);
  v8 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, int *))QueryInterface)(
         a3,
         &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
         v18);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 3382;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\batterysaver.cpp",
      (const char *)(unsigned int)v8,
      v18[0]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v18);
    WindowsDeleteString(string);
    return v9;
  }
  v11 = *(_QWORD *)v18;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v18 + 152LL);
  WindowsDeleteString(string);
  string = 0;
  v8 = v12(v11, &string);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 3383;
    goto LABEL_6;
  }
  if ( SystemSettings::DataModel::IsHstringEqual((SystemSettings::DataModel *)string, (HSTRING)&stru_180056970, v13) )
  {
    v16 = &SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::s_SUPPORTED_RESOLUTION_1440;
LABEL_11:
    *((_QWORD *)this + 28) = v16;
    goto LABEL_12;
  }
  if ( SystemSettings::DataModel::IsHstringEqual((SystemSettings::DataModel *)string, (HSTRING)&stru_180056A00, v15) )
  {
    v16 = &SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::s_SUPPORTED_RESOLUTION_1080;
    goto LABEL_11;
  }
LABEL_12:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v18);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x1800286d0  push    rbp
0x1800286d2  push    rbx
0x1800286d3  push    rsi
0x1800286d4  push    rdi
0x1800286d5  mov     rbp, rsp
0x1800286d8  sub     rsp, 38h
0x1800286dc  mov     rdi, r8
0x1800286df  mov     rbx, rdx
0x1800286e2  mov     rsi, rcx
0x1800286e5  lea     rdx, stru_180056AA0; HSTRING
0x1800286ec  mov     rcx, rbx; this
0x1800286ef  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800286f4  test    al, al
0x1800286f6  jz      loc_1800287FC
0x1800286fc  mov     [rbp+string], 0
0x180028704  mov     qword ptr [rbp+var_18], 0
0x18002870c  mov     rax, [rdi]
0x18002870f  mov     rbx, [rax]
0x180028712  lea     rcx, [rbp+var_18]
0x180028716  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002871b  lea     r8, [rbp+var_18]
0x18002871f  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180028726  mov     rcx, rdi
0x180028729  mov     rax, rbx
0x18002872c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028731  mov     ebx, eax
0x180028733  test    eax, eax
0x180028735  jns     short loc_18002873E
0x180028737  mov     edx, 0D36h
0x18002873c  jmp     short loc_180028778
0x18002873e  mov     rdi, qword ptr [rbp+var_18]
0x180028742  mov     rax, [rdi]
0x180028745  mov     rbx, [rax+98h]
0x18002874c  mov     rcx, [rbp+string]; string
0x180028750  call    cs:__imp_WindowsDeleteString
0x180028756  mov     [rbp+string], 0
0x18002875e  lea     rdx, [rbp+string]
0x180028762  mov     rcx, rdi
0x180028765  mov     rax, rbx
0x180028768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002876d  mov     ebx, eax
0x18002876f  test    eax, eax
0x180028771  jns     short loc_1800287A7
0x180028773  mov     edx, 0D37h; void *
0x180028778  mov     r9d, eax; char *
0x18002877b  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x180028782  mov     rcx, [rbp+20h]; this
0x180028786  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002878b  nop
0x18002878c  lea     rcx, [rbp+var_18]
0x180028790  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028795  nop
0x180028796  mov     rcx, [rbp+string]; string
0x18002879a  call    cs:__imp_WindowsDeleteString
0x1800287a0  mov     eax, ebx
0x1800287a2  jmp     loc_180028849
0x1800287a7  lea     rdx, stru_180056970; HSTRING
0x1800287ae  mov     rcx, [rbp+string]; this
0x1800287b2  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800287b7  test    al, al
0x1800287b9  jz      short loc_1800287C4
0x1800287bb  lea     rax, ?s_SUPPORTED_RESOLUTION_1440@CBatterySaverDynamicResolution@BatterySaverOneCoreDataModel@SystemSettings@@0USUPPORTED_RESOLUTION@23@B; SystemSettings::BatterySaverOneCoreDataModel::SUPPORTED_RESOLUTION const SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::s_SUPPORTED_RESOLUTION_1440
0x1800287c2  jmp     short loc_1800287DF
0x1800287c4  lea     rdx, stru_180056A00; HSTRING
0x1800287cb  mov     rcx, [rbp+string]; this
0x1800287cf  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800287d4  test    al, al
0x1800287d6  jz      short loc_1800287E6
0x1800287d8  lea     rax, ?s_SUPPORTED_RESOLUTION_1080@CBatterySaverDynamicResolution@BatterySaverOneCoreDataModel@SystemSettings@@0USUPPORTED_RESOLUTION@23@B; SystemSettings::BatterySaverOneCoreDataModel::SUPPORTED_RESOLUTION const SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::s_SUPPORTED_RESOLUTION_1080
0x1800287df  mov     [rsi+0E0h], rax
0x1800287e6  lea     rcx, [rbp+var_18]
0x1800287ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800287ef  nop
0x1800287f0  mov     rcx, [rbp+string]; string
0x1800287f4  call    cs:__imp_WindowsDeleteString
0x1800287fa  jmp     short loc_180028847
0x1800287fc  lea     rdx, stru_180056B80; HSTRING
0x180028803  mov     rcx, rbx; this
0x180028806  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002880b  test    al, al
0x18002880d  jz      short loc_180028847
0x18002880f  mov     byte ptr [rbp+string], 1
0x180028813  lea     rdx, [rbp+string]
0x180028817  mov     rcx, [rsi+0E0h]
0x18002881e  call    ??$DynamicResolutionChanged@AEBI_N@PowerAndBatteryTelemetry@@SAXAEBI$$QEA_N@Z; PowerAndBatteryTelemetry::DynamicResolutionChanged<uint const &,bool>(uint const &,bool &&)
0x180028823  xor     edx, edx; bool *
0x180028825  call    ?GetCurrentlyAppliedResolution@CBatterySaverDynamicResolution@BatterySaverOneCoreDataModel@SystemSettings@@AEAAPEBUSUPPORTED_RESOLUTION@23@PEA_N@Z; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::GetCurrentlyAppliedResolution(bool *)
0x18002882a  mov     [rsi+0E0h], rax
0x180028831  mov     byte ptr [rsi+0E8h], 1
0x180028838  lea     rdx, stru_180056AA0; unsigned __int16 *
0x18002883f  mov     rcx, rsi; this
0x180028842  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180028847  xor     eax, eax
0x180028849  add     rsp, 38h
0x18002884d  pop     rdi
0x18002884e  pop     rsi
0x18002884f  pop     rbx
0x180028850  pop     rbp
0x180028851  retn
```
