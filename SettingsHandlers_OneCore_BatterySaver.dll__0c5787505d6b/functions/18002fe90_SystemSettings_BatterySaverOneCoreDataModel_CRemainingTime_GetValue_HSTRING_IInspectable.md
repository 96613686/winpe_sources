# SystemSettings::BatterySaverOneCoreDataModel::CRemainingTime::GetValue(HSTRING__ *,IInspectable * *)

- ea: `0x18002fe90`
- end: `0x1800302a0`
- name: `?GetValue@CRemainingTime@BatterySaverOneCoreDataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `1040`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CRemainingTime *__hidden this, HSTRING, struct IInspectable **)`
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
- `0x180023fb0`
- `0x18002570c`
- `0x1800280c0`
- `0x18002fcd8`
- `0x18002fe90`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800301a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003022b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800301a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003022b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CRemainingTime::GetValue(
        SystemSettings::BatterySaverOneCoreDataModel::CRemainingTime *this,
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
  int v13; // eax
  char v14; // di
  const unsigned __int16 *v15; // rdx
  unsigned int v16; // r8d
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
  *a3 = 0;
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
                  goto LABEL_45;
                }
                if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180056260, v11) )
                {
                  switch ( v23 )
                  {
                    case 1:
                      v14 = 1;
                      *((_BYTE *)this + 240) = 1;
                      if ( qword_180065750 != (SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverEstimatedTimeRemaining *)0x7FFFFFFFFFFFFFFFLL )
                      {
                        v13 = SystemSettings::BatterySaverOneCoreDataModel::CRemainingTime::FormatTimeRemaining(
                                qword_180065750,
                                (double)(int)qword_180065750 / 3600.0,
                                &v30);
                        if ( v13 < 0 )
                          goto LABEL_16;
                        v6 = SystemSettings::DataModel::PropValueHelper::CreateString(v30, a3);
                        if ( v6 < 0 )
                          goto LABEL_45;
                        goto LABEL_24;
                      }
                      break;
                    case 2:
                      *((_BYTE *)this + 240) = 0;
LABEL_25:
                      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"IsApplicable");
                      goto LABEL_45;
                    case 3:
                      *((_BYTE *)this + 240) = v24 != 100;
                      if ( qword_180065760 != (SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverEstimatedTimeRemaining *)0x7FFFFFFFFFFFFFFFLL )
                      {
                        v13 = SystemSettings::BatterySaverOneCoreDataModel::CRemainingTime::FormatTimeRemaining(
                                qword_180065760,
                                (double)(int)qword_180065760 / 3600.0,
                                &v30);
                        if ( v13 < 0 )
                        {
LABEL_16:
                          v6 = v13;
                          goto LABEL_45;
                        }
                        v6 = SystemSettings::DataModel::PropValueHelper::CreateString(v30, a3);
                        if ( v6 < 0 )
                          goto LABEL_45;
                        v14 = 1;
                        goto LABEL_24;
                      }
                      break;
                    default:
                      goto LABEL_45;
                  }
                  v14 = 0;
LABEL_24:
                  *((_BYTE *)this + 240) = v14;
                  goto LABEL_25;
                }
                if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180057F08, v12) )
                  goto LABEL_45;
                string = 0;
                switch ( v23 )
                {
                  case 1:
                    v16 = 67;
                    v15 = L"BatterySaver_LandingPage_BatteryLife_EstimatedTime_DischargingLabel";
                    break;
                  case 2:
                    if ( v24 == 100 )
                    {
                      *((_BYTE *)this + 240) = 1;
                      v6 = Microsoft::WRL::Wrappers::HString::Set(
                             (Microsoft::WRL::Wrappers::HString *)&string,
                             L"BatterySaver_LandingPage_BatteryLife_EstimatedTime_FullyChargedLabel",
                             0x44u);
                      v18 = string;
                      if ( v6 < 0 )
                        goto LABEL_34;
                      string = 0;
                      v6 = SystemSettings::DataModel::PropValueHelper::CreateString(v18, a3);
                      if ( v6 < 0 )
                        goto LABEL_36;
                    }
                    else if ( v29 )
                    {
                      *((_BYTE *)this + 240) = 0;
                    }
                    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"IsApplicable");
LABEL_44:
                    WindowsDeleteString(string);
                    goto LABEL_45;
                  case 3:
                    if ( v24 == 100 )
                    {
                      v15 = L"BatterySaver_LandingPage_BatteryLife_EstimatedTime_FullyChargedLabel";
                      v16 = 68;
                    }
                    else
                    {
                      v15 = L"BatterySaver_LandingPage_BatteryLife_EstimatedTime_ChargingLabel";
                      v16 = 64;
                    }
                    break;
                  default:
                    goto LABEL_44;
                }
                v17 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v15, v16);
                v18 = string;
                v6 = v17;
                if ( v17 < 0 )
                {
LABEL_34:
                  WindowsDeleteString(v18);
                  string = 0;
                  goto LABEL_45;
                }
                string = 0;
                v6 = SystemSettings::DataModel::PropValueHelper::CreateString(v18, a3);
                if ( v6 < 0 )
                {
LABEL_36:
                  v18 = string;
                  goto LABEL_34;
                }
                goto LABEL_44;
              }
            }
          }
        }
      }
    }
  }
LABEL_45:
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
0x18002fe90  push    rbp
0x18002fe92  push    rbx
0x18002fe93  push    rsi
0x18002fe94  push    rdi
0x18002fe95  push    r12
0x18002fe97  push    r14
0x18002fe99  push    r15
0x18002fe9b  lea     rbp, [rsp-27h]
0x18002fea0  sub     rsp, 0A0h
0x18002fea7  mov     rax, cs:__security_cookie
0x18002feae  xor     rax, rsp
0x18002feb1  mov     [rbp+57h+var_40], rax
0x18002feb5  mov     r14, r8
0x18002feb8  mov     r15, rdx
0x18002febb  mov     rsi, rcx
0x18002febe  xor     r12d, r12d
0x18002fec1  mov     [rbp+57h+var_78], r12
0x18002fec5  mov     [rbp+57h+var_A8], r12
0x18002fec9  mov     [rbp+57h+var_88], r12
0x18002fecd  mov     [rbp+57h+var_A0], r12
0x18002fed1  mov     [rbp+57h+var_90], r12
0x18002fed5  mov     [rbp+57h+var_80], r12
0x18002fed9  mov     [rbp+57h+var_98], r12d
0x18002fedd  mov     [rbp+57h+var_70], r12d
0x18002fee1  mov     [rbp+57h+var_68], r12
0x18002fee5  mov     [rbp+57h+var_94], r12d
0x18002fee9  mov     [r8], r12
0x18002feec  mov     [rbp+57h+var_48], r12
0x18002fef0  lea     r9d, [r12+21h]; unsigned int
0x18002fef5  lea     r8d, [r12+22h]; unsigned int
0x18002fefa  lea     rdx, ?RuntimeClass_Windows_System_Power_PowerManager@@3QBGB; "Windows.System.Power.PowerManager"
0x18002ff01  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002ff05  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002ff0a  lea     rdx, [rbp+57h+var_A8]
0x18002ff0e  mov     rcx, [rbp+57h+var_48]
0x18002ff12  call    ??$GetActivationFactory@V?$ComPtr@UIPowerManagerStatics@Power@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPowerManagerStatics@Power@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Power::IPowerManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Power::IPowerManagerStatics>>)
0x18002ff17  mov     ebx, eax
0x18002ff19  test    eax, eax
0x18002ff1b  js      loc_180030232
0x18002ff21  mov     [rbp+57h+var_48], r12
0x18002ff25  lea     r9d, [r12+1Dh]; unsigned int
0x18002ff2a  lea     r8d, [r12+1Eh]; unsigned int
0x18002ff2f  lea     rdx, ?RuntimeClass_Windows_Devices_Power_Battery@@3QBGB; "Windows.Devices.Power.Battery"
0x18002ff36  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002ff3a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002ff3f  lea     rdx, [rbp+57h+var_88]
0x18002ff43  mov     rcx, [rbp+57h+var_48]
0x18002ff47  call    ??$GetActivationFactory@V?$ComPtr@UIBatteryStatics@Power@Devices@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIBatteryStatics@Power@Devices@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Devices::Power::IBatteryStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Power::IBatteryStatics>>)
0x18002ff4c  mov     ebx, eax
0x18002ff4e  test    eax, eax
0x18002ff50  js      loc_180030232
0x18002ff56  mov     rdi, [rbp+57h+var_88]
0x18002ff5a  mov     rax, [rdi]
0x18002ff5d  mov     rbx, [rax+30h]
0x18002ff61  lea     rcx, [rbp+57h+var_A0]
0x18002ff65  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ff6a  lea     rdx, [rbp+57h+var_A0]
0x18002ff6e  mov     rcx, rdi
0x18002ff71  mov     rax, rbx
0x18002ff74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff79  mov     ebx, eax
0x18002ff7b  test    eax, eax
0x18002ff7d  js      loc_180030232
0x18002ff83  mov     rdi, [rbp+57h+var_A0]
0x18002ff87  mov     rax, [rdi]
0x18002ff8a  mov     rbx, [rax+38h]
0x18002ff8e  lea     rcx, [rbp+57h+var_90]
0x18002ff92  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ff97  lea     rdx, [rbp+57h+var_90]
0x18002ff9b  mov     rcx, rdi
0x18002ff9e  mov     rax, rbx
0x18002ffa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffa6  mov     ebx, eax
0x18002ffa8  test    eax, eax
0x18002ffaa  js      loc_180030232
0x18002ffb0  mov     rcx, [rbp+57h+var_A8]
0x18002ffb4  mov     rax, [rcx]
0x18002ffb7  lea     rdx, [rbp+57h+var_70]
0x18002ffbb  mov     rax, [rax+60h]
0x18002ffbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffc4  mov     ebx, eax
0x18002ffc6  test    eax, eax
0x18002ffc8  js      loc_180030232
0x18002ffce  mov     rcx, [rbp+57h+var_A8]
0x18002ffd2  mov     rax, [rcx]
0x18002ffd5  lea     rdx, [rbp+57h+var_98]
0x18002ffd9  mov     rax, [rax+48h]
0x18002ffdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffe2  mov     ebx, eax
0x18002ffe4  test    eax, eax
0x18002ffe6  js      loc_180030232
0x18002ffec  mov     rcx, [rbp+57h+var_A8]
0x18002fff0  mov     rax, [rcx]
0x18002fff3  lea     rdx, [rbp+57h+var_94]
0x18002fff7  mov     rax, [rax+78h]
0x18002fffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030000  mov     ebx, eax
0x180030002  test    eax, eax
0x180030004  js      loc_180030232
0x18003000a  cmp     [rbp+57h+var_98], r12d
0x18003000e  jnz     short loc_180030030
0x180030010  mov     [rsi+0F0h], r12b
0x180030017  lea     rdx, aIsapplicable; "IsApplicable"
0x18003001e  mov     rcx, rsi; this
0x180030021  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180030026  mov     ebx, 80004005h
0x18003002b  jmp     loc_180030232
0x180030030  lea     rdx, stru_180056260; HSTRING
0x180030037  mov     rcx, r15; this
0x18003003a  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18003003f  test    al, al
0x180030041  jz      loc_18003013B
0x180030047  mov     ecx, [rbp+57h+var_98]
0x18003004a  sub     ecx, 1
0x18003004d  jz      short loc_1800300C8
0x18003004f  sub     ecx, 1
0x180030052  jz      short loc_1800300BF
0x180030054  cmp     ecx, 1
0x180030057  jnz     loc_180030232
0x18003005d  cmp     [rbp+57h+var_94], 64h ; 'd'
0x180030061  setnz   al
0x180030064  mov     [rsi+0F0h], al
0x18003006a  mov     rcx, cs:qword_180065760; this
0x180030071  mov     rax, 7FFFFFFFFFFFFFFFh
0x18003007b  cmp     rcx, rax
0x18003007e  jz      short loc_1800300E8
0x180030080  xorps   xmm1, xmm1
0x180030083  cvtsi2sd xmm1, rcx
0x180030088  divsd   xmm1, cs:__real@40ac200000000000; double
0x180030090  lea     r8, [rbp+57h+var_68]; HSTRING *
0x180030094  call    ?FormatTimeRemaining@CRemainingTime@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJNPEAPEAUHSTRING__@@@Z; SystemSettings::BatterySaverOneCoreDataModel::CRemainingTime::FormatTimeRemaining(double,HSTRING__ * *)
0x180030099  test    eax, eax
0x18003009b  jns     short loc_1800300A4
0x18003009d  mov     ebx, eax
0x18003009f  jmp     loc_180030232
0x1800300a4  mov     rdx, r14; struct IInspectable **
0x1800300a7  mov     rcx, [rbp+57h+var_68]; HSTRING
0x1800300ab  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1800300b0  mov     ebx, eax
0x1800300b2  test    eax, eax
0x1800300b4  js      loc_180030232
0x1800300ba  mov     dil, 1
0x1800300bd  jmp     short loc_180030120
0x1800300bf  mov     [rsi+0F0h], r12b
0x1800300c6  jmp     short loc_180030127
0x1800300c8  mov     dil, 1
0x1800300cb  mov     [rsi+0F0h], dil
0x1800300d2  mov     rcx, cs:qword_180065750; this
0x1800300d9  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800300e3  cmp     rcx, rax
0x1800300e6  jnz     short loc_1800300ED
0x1800300e8  mov     dil, r12b
0x1800300eb  jmp     short loc_180030120
0x1800300ed  xorps   xmm1, xmm1
0x1800300f0  cvtsi2sd xmm1, rcx
0x1800300f5  divsd   xmm1, cs:__real@40ac200000000000; double
0x1800300fd  lea     r8, [rbp+57h+var_68]; HSTRING *
0x180030101  call    ?FormatTimeRemaining@CRemainingTime@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJNPEAPEAUHSTRING__@@@Z; SystemSettings::BatterySaverOneCoreDataModel::CRemainingTime::FormatTimeRemaining(double,HSTRING__ * *)
0x180030106  test    eax, eax
0x180030108  js      short loc_18003009D
0x18003010a  mov     rdx, r14; struct IInspectable **
0x18003010d  mov     rcx, [rbp+57h+var_68]; HSTRING
0x180030111  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x180030116  mov     ebx, eax
0x180030118  test    eax, eax
0x18003011a  js      loc_180030232
0x180030120  mov     [rsi+0F0h], dil
0x180030127  lea     rdx, aIsapplicable; "IsApplicable"
0x18003012e  mov     rcx, rsi; this
0x180030131  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180030136  jmp     loc_180030232
0x18003013b  lea     rdx, stru_180057F08; HSTRING
0x180030142  mov     rcx, r15; this
0x180030145  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18003014a  test    al, al
0x18003014c  jz      loc_180030232
0x180030152  mov     [rbp+57h+string], r12
0x180030156  mov     ecx, [rbp+57h+var_98]
0x180030159  sub     ecx, 1
0x18003015c  jz      loc_18003028D
0x180030162  sub     ecx, 1
0x180030165  jz      short loc_1800301CA
0x180030167  cmp     ecx, 1
0x18003016a  jnz     loc_180030227
0x180030170  cmp     [rbp+57h+var_94], 64h ; 'd'
0x180030174  jnz     short loc_180030183
0x180030176  lea     rdx, aBatterysaverLa_5; "BatterySaver_LandingPage_BatteryLife_Es"...
0x18003017d  lea     r8d, [rcx+43h]
0x180030181  jmp     short loc_180030190
0x180030183  lea     rdx, aBatterysaverLa_4; "BatterySaver_LandingPage_BatteryLife_Es"...
0x18003018a  mov     r8d, 40h ; '@'; unsigned int
0x180030190  lea     rcx, [rbp+57h+string]; this
0x180030194  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180030199  test    eax, eax
0x18003019b  mov     rcx, [rbp+57h+string]; HSTRING
0x18003019f  mov     ebx, eax
0x1800301a1  jns     short loc_1800301B2
0x1800301a3  call    cs:__imp_WindowsDeleteString
0x1800301a9  mov     [rbp+57h+string], r12
0x1800301ad  jmp     loc_180030232
0x1800301b2  mov     [rbp+57h+string], r12
0x1800301b6  mov     rdx, r14; struct IInspectable **
0x1800301b9  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1800301be  mov     ebx, eax
0x1800301c0  test    eax, eax
0x1800301c2  jns     short loc_180030227
0x1800301c4  mov     rcx, [rbp+57h+string]
0x1800301c8  jmp     short loc_1800301A3
0x1800301ca  cmp     [rbp+57h+var_94], 64h ; 'd'
0x1800301ce  jnz     short loc_18003020B
0x1800301d0  mov     byte ptr [rsi+0F0h], 1
0x1800301d7  mov     r8d, 44h ; 'D'; unsigned int
0x1800301dd  lea     rdx, aBatterysaverLa_5; "BatterySaver_LandingPage_BatteryLife_Es"...
0x1800301e4  lea     rcx, [rbp+57h+string]; this
0x1800301e8  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800301ed  mov     ebx, eax
0x1800301ef  mov     rcx, [rbp+57h+string]; HSTRING
0x1800301f3  test    eax, eax
0x1800301f5  js      short loc_1800301A3
0x1800301f7  mov     [rbp+57h+string], r12
0x1800301fb  mov     rdx, r14; struct IInspectable **
0x1800301fe  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x180030203  mov     ebx, eax
0x180030205  test    eax, eax
0x180030207  jns     short loc_180030218
0x180030209  jmp     short loc_1800301C4
0x18003020b  cmp     [rbp+57h+var_70], r12d
0x18003020f  jz      short loc_180030218
0x180030211  mov     [rsi+0F0h], r12b
0x180030218  lea     rdx, aIsapplicable; "IsApplicable"
0x18003021f  mov     rcx, rsi; this
0x180030222  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180030227  mov     rcx, [rbp+57h+string]; string
0x18003022b  call    cs:__imp_WindowsDeleteString
0x180030231  nop
0x180030232  lea     rcx, [rbp+57h+var_80]
0x180030236  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003023b  nop
0x18003023c  lea     rcx, [rbp+57h+var_90]
0x180030240  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180030245  nop
0x180030246  lea     rcx, [rbp+57h+var_A0]
0x18003024a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003024f  nop
0x180030250  lea     rcx, [rbp+57h+var_88]
0x180030254  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180030259  nop
0x18003025a  lea     rcx, [rbp+57h+var_A8]
0x18003025e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180030263  nop
0x180030264  lea     rcx, [rbp+57h+var_78]
0x180030268  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003026d  mov     eax, ebx
0x18003026f  mov     rcx, [rbp+57h+var_40]
0x180030273  xor     rcx, rsp; StackCookie
0x180030276  call    __security_check_cookie
0x18003027b  add     rsp, 0A0h
0x180030282  pop     r15
0x180030284  pop     r14
0x180030286  pop     r12
0x180030288  pop     rdi
0x180030289  pop     rsi
0x18003028a  pop     rbx
0x18003028b  pop     rbp
0x18003028c  retn
0x18003028d  mov     r8d, 43h ; 'C'
0x180030293  lea     rdx, aBatterysaverLa_1; "BatterySaver_LandingPage_BatteryLife_Es"...
0x18003029a  jmp     loc_180030190
```
