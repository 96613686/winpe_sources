# SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverEstimatedTimeRemaining::GetValue(HSTRING__ *,IInspectable * *)

- ea: `0x180021970`
- end: `0x180021d90`
- name: `?GetValue@CBatterySaverEstimatedTimeRemaining@BatterySaverOneCoreDataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `1056`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverEstimatedTimeRemaining *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009190`
- `0x18000cfa4`
- `0x180015d30`
- `0x180015d6c`
- `0x18001d0f8`
- `0x18001d140`
- `0x180021970`
- `0x180023fb0`
- `0x18002570c`
- `0x1800280c0`
- `0x18002b760`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021c8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021d2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021c8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021d2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverEstimatedTimeRemaining::GetValue(
        SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverEstimatedTimeRemaining *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r8
  char v13; // di
  int v14; // eax
  unsigned int v15; // r8d
  const unsigned __int16 *v16; // rdx
  int v17; // eax
  HSTRING v18; // rcx
  HSTRING string; // [rsp+20h] [rbp-59h] BYREF
  __int64 v21; // [rsp+28h] [rbp-51h] BYREF
  __int64 v22; // [rsp+30h] [rbp-49h] BYREF
  int v23; // [rsp+38h] [rbp-41h] BYREF
  int v24; // [rsp+3Ch] [rbp-3Dh] BYREF
  __int64 v25; // [rsp+40h] [rbp-39h] BYREF
  __int64 v26; // [rsp+48h] [rbp-31h] BYREF
  __int64 v27; // [rsp+50h] [rbp-29h] BYREF
  __int64 v28; // [rsp+58h] [rbp-21h] BYREF
  int v29; // [rsp+60h] [rbp-19h] BYREF
  HSTRING v30; // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  __int64 v32; // [rsp+88h] [rbp+Fh]

  *a3 = 0;
  v28 = 0;
  v21 = 0;
  v26 = 0;
  v22 = 0;
  v25 = 0;
  v27 = 0;
  v23 = 0;
  v29 = 0;
  v30 = 0;
  v24 = 0;
  v32 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Power.PowerManager",
    0x22u,
    0x21u);
  v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Power::IPowerManagerStatics>>(
         v32,
         (__int64)&v21);
  if ( v6 >= 0 )
  {
    v32 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Devices.Power.Battery",
      0x1Eu,
      0x1Du);
    v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Devices::Power::IBatteryStatics>>(
           v32,
           (__int64)&v26);
    if ( v6 >= 0 )
    {
      v7 = v26;
      v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
      v6 = v8(v7, &v22);
      if ( v6 >= 0 )
      {
        v9 = v22;
        v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 56LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
        v6 = v10(v9, &v25);
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 96LL))(v21, &v29);
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 72LL))(v21, &v23);
            if ( v6 >= 0 )
            {
              v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 120LL))(v21, &v24);
              if ( v6 >= 0 )
              {
                if ( !v23 )
                {
                  *((_BYTE *)this + 240) = 0;
                  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"IsApplicable");
                  v6 = -2147467259;
                  goto LABEL_43;
                }
                if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180056260, v11) )
                {
                  if ( v23 != 2 )
                  {
                    if ( v23 == 3 )
                    {
                      *((_BYTE *)this + 240) = v24 != 100;
                      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"IsApplicable");
                      if ( qword_180065760 == (SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverEstimatedTimeRemaining *)0x7FFFFFFFFFFFFFFFLL )
                      {
                        v13 = 0;
LABEL_24:
                        *((_BYTE *)this + 240) = v13;
                        goto LABEL_25;
                      }
                      v14 = SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverEstimatedTimeRemaining::formatTimeRemaining(
                              qword_180065760,
                              (double)(int)qword_180065760 / 3600.0,
                              &v30);
                      if ( v14 >= 0 )
                      {
                        v6 = SystemSettings::DataModel::PropValueHelper::CreateString(v30, a3);
                        if ( v6 < 0 )
                          goto LABEL_43;
                        v13 = 1;
                        goto LABEL_24;
                      }
                      goto LABEL_16;
                    }
                    v13 = 1;
                    if ( v23 != 1 )
                      goto LABEL_43;
                    *((_BYTE *)this + 240) = 1;
                    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"IsApplicable");
                    if ( qword_180065750 != (SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverEstimatedTimeRemaining *)0x7FFFFFFFFFFFFFFFLL )
                    {
                      v14 = SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverEstimatedTimeRemaining::formatTimeRemaining(
                              qword_180065750,
                              (double)(int)qword_180065750 / 3600.0,
                              &v30);
                      if ( v14 >= 0 )
                      {
                        v6 = SystemSettings::DataModel::PropValueHelper::CreateString(v30, a3);
                        if ( v6 < 0 )
                          goto LABEL_43;
                        goto LABEL_24;
                      }
LABEL_16:
                      v6 = v14;
                      goto LABEL_43;
                    }
                  }
                  *((_BYTE *)this + 240) = 0;
LABEL_25:
                  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"IsApplicable");
                  goto LABEL_43;
                }
                if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180056228, v12) )
                  goto LABEL_43;
                string = 0;
                switch ( v23 )
                {
                  case 3:
                    if ( v24 == 100 )
                    {
                      v15 = 68;
                      v16 = L"BatterySaver_LandingPage_BatteryLife_EstimatedTime_FullyChargedLabel";
                    }
                    else
                    {
                      v15 = 64;
                      v16 = L"BatterySaver_LandingPage_BatteryLife_EstimatedTime_ChargingLabel";
                    }
                    break;
                  case 1:
                    v15 = 67;
                    v16 = L"BatterySaver_LandingPage_BatteryLife_EstimatedTime_DischargingLabel";
                    break;
                  case 2:
                    if ( v24 != 100 )
                    {
                      if ( v29 )
                      {
                        *((_BYTE *)this + 240) = 0;
                        SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"IsApplicable");
                      }
                      goto LABEL_42;
                    }
                    *((_BYTE *)this + 240) = 1;
                    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"IsApplicable");
                    v15 = 68;
                    v16 = L"BatterySaver_LandingPage_BatteryLife_EstimatedTime_FullyChargedLabel";
                    break;
                  default:
                    goto LABEL_42;
                }
                v17 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v16, v15);
                v18 = string;
                v6 = v17;
                if ( v17 < 0 )
                {
LABEL_31:
                  WindowsDeleteString(v18);
                  string = 0;
                  goto LABEL_43;
                }
                string = 0;
                v6 = SystemSettings::DataModel::PropValueHelper::CreateString(v18, a3);
                if ( v6 < 0 )
                {
                  v18 = string;
                  goto LABEL_31;
                }
LABEL_42:
                WindowsDeleteString(string);
              }
            }
          }
        }
      }
    }
  }
LABEL_43:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180021970  push    rbp
0x180021972  push    rbx
0x180021973  push    rsi
0x180021974  push    rdi
0x180021975  push    r12
0x180021977  push    r14
0x180021979  push    r15
0x18002197b  lea     rbp, [rsp-27h]
0x180021980  sub     rsp, 0A0h
0x180021987  mov     rax, cs:__security_cookie
0x18002198e  xor     rax, rsp
0x180021991  mov     [rbp+57h+var_40], rax
0x180021995  mov     r14, r8
0x180021998  mov     r15, rdx
0x18002199b  mov     rsi, rcx
0x18002199e  xor     r12d, r12d
0x1800219a1  mov     [r8], r12
0x1800219a4  mov     [rbp+57h+var_78], r12
0x1800219a8  mov     [rbp+57h+var_A8], r12
0x1800219ac  mov     [rbp+57h+var_88], r12
0x1800219b0  mov     [rbp+57h+var_A0], r12
0x1800219b4  mov     [rbp+57h+var_90], r12
0x1800219b8  mov     [rbp+57h+var_80], r12
0x1800219bc  mov     [rbp+57h+var_98], r12d
0x1800219c0  mov     [rbp+57h+var_70], r12d
0x1800219c4  mov     [rbp+57h+var_68], r12
0x1800219c8  mov     [rbp+57h+var_94], r12d
0x1800219cc  mov     [rbp+57h+var_48], r12
0x1800219d0  lea     r9d, [r12+21h]; unsigned int
0x1800219d5  lea     r8d, [r12+22h]; unsigned int
0x1800219da  lea     rdx, ?RuntimeClass_Windows_System_Power_PowerManager@@3QBGB; "Windows.System.Power.PowerManager"
0x1800219e1  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800219e5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800219ea  lea     rdx, [rbp+57h+var_A8]
0x1800219ee  mov     rcx, [rbp+57h+var_48]
0x1800219f2  call    ??$GetActivationFactory@V?$ComPtr@UIPowerManagerStatics@Power@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPowerManagerStatics@Power@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Power::IPowerManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Power::IPowerManagerStatics>>)
0x1800219f7  mov     ebx, eax
0x1800219f9  test    eax, eax
0x1800219fb  js      loc_180021D35
0x180021a01  mov     [rbp+57h+var_48], r12
0x180021a05  lea     r9d, [r12+1Dh]; unsigned int
0x180021a0a  lea     r8d, [r12+1Eh]; unsigned int
0x180021a0f  lea     rdx, ?RuntimeClass_Windows_Devices_Power_Battery@@3QBGB; "Windows.Devices.Power.Battery"
0x180021a16  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180021a1a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180021a1f  lea     rdx, [rbp+57h+var_88]
0x180021a23  mov     rcx, [rbp+57h+var_48]
0x180021a27  call    ??$GetActivationFactory@V?$ComPtr@UIBatteryStatics@Power@Devices@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIBatteryStatics@Power@Devices@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Devices::Power::IBatteryStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Power::IBatteryStatics>>)
0x180021a2c  mov     ebx, eax
0x180021a2e  test    eax, eax
0x180021a30  js      loc_180021D35
0x180021a36  mov     rdi, [rbp+57h+var_88]
0x180021a3a  mov     rax, [rdi]
0x180021a3d  mov     rbx, [rax+30h]
0x180021a41  lea     rcx, [rbp+57h+var_A0]
0x180021a45  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021a4a  lea     rdx, [rbp+57h+var_A0]
0x180021a4e  mov     rcx, rdi
0x180021a51  mov     rax, rbx
0x180021a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a59  mov     ebx, eax
0x180021a5b  test    eax, eax
0x180021a5d  js      loc_180021D35
0x180021a63  mov     rdi, [rbp+57h+var_A0]
0x180021a67  mov     rax, [rdi]
0x180021a6a  mov     rbx, [rax+38h]
0x180021a6e  lea     rcx, [rbp+57h+var_90]
0x180021a72  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021a77  lea     rdx, [rbp+57h+var_90]
0x180021a7b  mov     rcx, rdi
0x180021a7e  mov     rax, rbx
0x180021a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a86  mov     ebx, eax
0x180021a88  test    eax, eax
0x180021a8a  js      loc_180021D35
0x180021a90  mov     rcx, [rbp+57h+var_A8]
0x180021a94  mov     rax, [rcx]
0x180021a97  lea     rdx, [rbp+57h+var_70]
0x180021a9b  mov     rax, [rax+60h]
0x180021a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021aa4  mov     ebx, eax
0x180021aa6  test    eax, eax
0x180021aa8  js      loc_180021D35
0x180021aae  mov     rcx, [rbp+57h+var_A8]
0x180021ab2  mov     rax, [rcx]
0x180021ab5  lea     rdx, [rbp+57h+var_98]
0x180021ab9  mov     rax, [rax+48h]
0x180021abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ac2  mov     ebx, eax
0x180021ac4  test    eax, eax
0x180021ac6  js      loc_180021D35
0x180021acc  mov     rcx, [rbp+57h+var_A8]
0x180021ad0  mov     rax, [rcx]
0x180021ad3  lea     rdx, [rbp+57h+var_94]
0x180021ad7  mov     rax, [rax+78h]
0x180021adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ae0  mov     ebx, eax
0x180021ae2  test    eax, eax
0x180021ae4  js      loc_180021D35
0x180021aea  cmp     [rbp+57h+var_98], r12d
0x180021aee  jnz     short loc_180021B10
0x180021af0  mov     [rsi+0F0h], r12b
0x180021af7  lea     rdx, aIsapplicable; "IsApplicable"
0x180021afe  mov     rcx, rsi; this
0x180021b01  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180021b06  mov     ebx, 80004005h
0x180021b0b  jmp     loc_180021D35
0x180021b10  lea     rdx, stru_180056260; HSTRING
0x180021b17  mov     rcx, r15; this
0x180021b1a  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180021b1f  test    al, al
0x180021b21  jz      loc_180021C47
0x180021b27  mov     eax, [rbp+57h+var_98]
0x180021b2a  cmp     eax, 2
0x180021b2d  jz      loc_180021BEC
0x180021b33  cmp     eax, 3
0x180021b36  jnz     short loc_180021BB3
0x180021b38  cmp     [rbp+57h+var_94], 64h ; 'd'
0x180021b3c  setnz   al
0x180021b3f  mov     [rsi+0F0h], al
0x180021b45  lea     rdx, aIsapplicable; "IsApplicable"
0x180021b4c  mov     rcx, rsi; this
0x180021b4f  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180021b54  mov     rcx, cs:qword_180065760; this
0x180021b5b  mov     rax, 7FFFFFFFFFFFFFFFh
0x180021b65  cmp     rcx, rax
0x180021b68  jnz     short loc_180021B72
0x180021b6a  mov     dil, r12b
0x180021b6d  jmp     loc_180021C2C
0x180021b72  xorps   xmm1, xmm1
0x180021b75  cvtsi2sd xmm1, rcx
0x180021b7a  divsd   xmm1, cs:__real@40ac200000000000; double
0x180021b82  lea     r8, [rbp+57h+var_68]; HSTRING *
0x180021b86  call    ?formatTimeRemaining@CBatterySaverEstimatedTimeRemaining@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJNPEAPEAUHSTRING__@@@Z; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverEstimatedTimeRemaining::formatTimeRemaining(double,HSTRING__ * *)
0x180021b8b  test    eax, eax
0x180021b8d  jns     short loc_180021B96
0x180021b8f  mov     ebx, eax
0x180021b91  jmp     loc_180021D35
0x180021b96  mov     rdx, r14; struct IInspectable **
0x180021b99  mov     rcx, [rbp+57h+var_68]; HSTRING
0x180021b9d  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x180021ba2  mov     ebx, eax
0x180021ba4  test    eax, eax
0x180021ba6  js      loc_180021D35
0x180021bac  mov     edi, 1
0x180021bb1  jmp     short loc_180021C2C
0x180021bb3  mov     edi, 1
0x180021bb8  cmp     eax, edi
0x180021bba  jnz     loc_180021D35
0x180021bc0  mov     [rsi+0F0h], dil
0x180021bc7  lea     rdx, aIsapplicable; "IsApplicable"
0x180021bce  mov     rcx, rsi; this
0x180021bd1  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180021bd6  mov     rcx, cs:qword_180065750; this
0x180021bdd  mov     rax, 7FFFFFFFFFFFFFFFh
0x180021be7  cmp     rcx, rax
0x180021bea  jnz     short loc_180021BF5
0x180021bec  mov     [rsi+0F0h], r12b
0x180021bf3  jmp     short loc_180021C33
0x180021bf5  xorps   xmm1, xmm1
0x180021bf8  cvtsi2sd xmm1, rcx
0x180021bfd  divsd   xmm1, cs:__real@40ac200000000000; double
0x180021c05  lea     r8, [rbp+57h+var_68]; HSTRING *
0x180021c09  call    ?formatTimeRemaining@CBatterySaverEstimatedTimeRemaining@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJNPEAPEAUHSTRING__@@@Z; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverEstimatedTimeRemaining::formatTimeRemaining(double,HSTRING__ * *)
0x180021c0e  test    eax, eax
0x180021c10  js      loc_180021B8F
0x180021c16  mov     rdx, r14; struct IInspectable **
0x180021c19  mov     rcx, [rbp+57h+var_68]; HSTRING
0x180021c1d  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x180021c22  mov     ebx, eax
0x180021c24  test    eax, eax
0x180021c26  js      loc_180021D35
0x180021c2c  mov     [rsi+0F0h], dil
0x180021c33  lea     rdx, aIsapplicable; "IsApplicable"
0x180021c3a  mov     rcx, rsi; this
0x180021c3d  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180021c42  jmp     loc_180021D35
0x180021c47  lea     rdx, stru_180056228; HSTRING
0x180021c4e  mov     rcx, r15; this
0x180021c51  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180021c56  test    al, al
0x180021c58  jz      loc_180021D35
0x180021c5e  mov     [rbp+57h+string], r12
0x180021c62  mov     eax, [rbp+57h+var_98]
0x180021c65  cmp     eax, 3
0x180021c68  jnz     short loc_180021CC4
0x180021c6a  lea     rcx, [rbp+57h+string]; this
0x180021c6e  cmp     [rbp+57h+var_94], 64h ; 'd'
0x180021c72  jnz     short loc_180021CB5
0x180021c74  lea     r8d, [rax+41h]; unsigned int
0x180021c78  lea     rdx, aBatterysaverLa_5; "BatterySaver_LandingPage_BatteryLife_Es"...
0x180021c7f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180021c84  test    eax, eax
0x180021c86  mov     rcx, [rbp+57h+string]; HSTRING
0x180021c8a  mov     ebx, eax
0x180021c8c  jns     short loc_180021C9D
0x180021c8e  call    cs:__imp_WindowsDeleteString
0x180021c94  mov     [rbp+57h+string], r12
0x180021c98  jmp     loc_180021D35
0x180021c9d  mov     [rbp+57h+string], r12
0x180021ca1  mov     rdx, r14; struct IInspectable **
0x180021ca4  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x180021ca9  mov     ebx, eax
0x180021cab  test    eax, eax
0x180021cad  jns     short loc_180021D2A
0x180021caf  mov     rcx, [rbp+57h+string]
0x180021cb3  jmp     short loc_180021C8E
0x180021cb5  mov     r8d, 40h ; '@'
0x180021cbb  lea     rdx, aBatterysaverLa_4; "BatterySaver_LandingPage_BatteryLife_Es"...
0x180021cc2  jmp     short loc_180021C7F
0x180021cc4  mov     edi, 1
0x180021cc9  cmp     eax, edi
0x180021ccb  jnz     short loc_180021CDE
0x180021ccd  lea     r8d, [rdi+42h]
0x180021cd1  lea     rdx, aBatterysaverLa_1; "BatterySaver_LandingPage_BatteryLife_Es"...
0x180021cd8  lea     rcx, [rbp+57h+string]
0x180021cdc  jmp     short loc_180021C7F
0x180021cde  cmp     eax, 2
0x180021ce1  jnz     short loc_180021D2A
0x180021ce3  cmp     [rbp+57h+var_94], 64h ; 'd'
0x180021ce7  jnz     short loc_180021D0E
0x180021ce9  mov     [rsi+0F0h], dil
0x180021cf0  lea     rdx, aIsapplicable; "IsApplicable"
0x180021cf7  mov     rcx, rsi; this
0x180021cfa  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180021cff  mov     r8d, 44h ; 'D'
0x180021d05  lea     rdx, aBatterysaverLa_5; "BatterySaver_LandingPage_BatteryLife_Es"...
0x180021d0c  jmp     short loc_180021CD8
0x180021d0e  cmp     [rbp+57h+var_70], r12d
0x180021d12  jz      short loc_180021D2A
0x180021d14  mov     [rsi+0F0h], r12b
0x180021d1b  lea     rdx, aIsapplicable; "IsApplicable"
0x180021d22  mov     rcx, rsi; this
0x180021d25  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180021d2a  mov     rcx, [rbp+57h+string]; string
0x180021d2e  call    cs:__imp_WindowsDeleteString
0x180021d34  nop
0x180021d35  lea     rcx, [rbp+57h+var_80]
0x180021d39  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021d3e  nop
0x180021d3f  lea     rcx, [rbp+57h+var_90]
0x180021d43  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021d48  nop
0x180021d49  lea     rcx, [rbp+57h+var_A0]
0x180021d4d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021d52  nop
0x180021d53  lea     rcx, [rbp+57h+var_88]
0x180021d57  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021d5c  nop
0x180021d5d  lea     rcx, [rbp+57h+var_A8]
0x180021d61  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021d66  nop
0x180021d67  lea     rcx, [rbp+57h+var_78]
0x180021d6b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021d70  mov     eax, ebx
0x180021d72  mov     rcx, [rbp+57h+var_40]
0x180021d76  xor     rcx, rsp; StackCookie
0x180021d79  call    __security_check_cookie
0x180021d7e  add     rsp, 0A0h
0x180021d85  pop     r15
0x180021d87  pop     r14
0x180021d89  pop     r12
0x180021d8b  pop     rdi
0x180021d8c  pop     rsi
0x180021d8d  pop     rbx
0x180021d8e  pop     rbp
0x180021d8f  retn
```
