# Microsoft::Windows::Autopilot::HardwareInfo::GetCurrentHardwareBlob(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x18001ab2c`
- end: `0x18001af18`
- name: `?GetCurrentHardwareBlob@HardwareInfo@Autopilot@Windows@Microsoft@@CAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z`
- size: `1004`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b430`

## callees

- `0x1800045d0`
- `0x1800098e7`
- `0x180010764`
- `0x180017a20`
- `0x1800192a4`
- `0x18001ab2c`
- `0x18001f030`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001abc0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001abc0`
- `OLEAUT32!__imp_VariantInit` at `0x18001ab64`
- `OLEAUT32!__imp_VariantInit` at `0x18001ab64`
- `OLEAUT32!__imp_VariantClear` at `0x18001abf9`
- `OLEAUT32!__imp_VariantClear` at `0x18001aca4`
- `OLEAUT32!__imp_VariantClear` at `0x18001ad23`
- `OLEAUT32!__imp_VariantClear` at `0x18001ad98`
- `OLEAUT32!__imp_VariantClear` at `0x18001ae6c`
- `OLEAUT32!__imp_VariantClear` at `0x18001aeb8`
- `OLEAUT32!__imp_VariantClear` at `0x18001abf9`
- `OLEAUT32!__imp_VariantClear` at `0x18001aca4`
- `OLEAUT32!__imp_VariantClear` at `0x18001ad23`
- `OLEAUT32!__imp_VariantClear` at `0x18001ad98`
- `OLEAUT32!__imp_VariantClear` at `0x18001ae6c`
- `OLEAUT32!__imp_VariantClear` at `0x18001aeb8`

## string_xrefs

- `0x18001abd9`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001ac84`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001ad03`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001ad78`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001ae4c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetCurrentHardwareBlob(
        struct Windows::Data::Json::IJsonObject **a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  LPVOID v5; // rbx
  __int64 (__fastcall *v6)(LPVOID, const wchar_t *, __int64 *); // rdi
  __int64 v7; // rdx
  int v8; // eax
  int v9; // eax
  __int64 v10; // r8
  unsigned __int64 v11; // rdx
  unsigned __int16 **v12; // rdi
  __int64 v13; // rbx
  const unsigned __int16 *v14; // r8
  int v15; // eax
  int ppv; // [rsp+20h] [rbp-60h]
  LPVOID v17; // [rsp+30h] [rbp-50h] BYREF
  __int64 v18; // [rsp+38h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 *v20[2]; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v21; // [rsp+68h] [rbp-18h]
  unsigned __int64 v22; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v18 = 0;
  VariantInit(&pvarg);
  *(_OWORD *)v20 = 0;
  v21 = 0;
  v22 = 7;
  LOWORD(v20[0]) = 0;
  v17 = 0;
  v2 = CoCreateInstance(
         &GUID_66d0db14_5638_475f_a386_629522d8c461,
         0,
         1u,
         &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
         &v17);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v2,
      ppv);
    std::wstring::_Tidy_deallocate((char **)v20);
    VariantClear(&pvarg);
    if ( v17 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    return v3;
  }
  v5 = v17;
  v6 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)v17 + 80LL);
  v7 = v18;
  v18 = 0;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = v6(v5, L"./DevDetail/Ext/DeviceHardwareData", &v18);
  v3 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v8,
      ppv);
    std::wstring::_Tidy_deallocate((char **)v20);
    VariantClear(&pvarg);
    if ( v17 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    return v3;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v18 + 104LL))(v18, &pvarg);
  v3 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24E,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    std::wstring::_Tidy_deallocate((char **)v20);
    VariantClear(&pvarg);
    if ( v17 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    return v3;
  }
  if ( pvarg.vt != 8 )
  {
    v3 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)0x8000FFFFLL,
      ppv);
    std::wstring::_Tidy_deallocate((char **)v20);
    VariantClear(&pvarg);
    if ( v17 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    return v3;
  }
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(pvarg.llVal + 2 * v11) );
  if ( v11 > v22 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)v20,
      v11,
      v10,
      pvarg.bstrVal);
  }
  else
  {
    v12 = v20;
    if ( v22 > 7 )
      v12 = (unsigned __int16 **)v20[0];
    v21 = v11;
    v13 = 2 * v11;
    memmove_0(v12, pvarg.bstrVal, 2 * v11);
    *(_WORD *)((char *)v12 + v13) = 0;
  }
  v14 = (const unsigned __int16 *)v20;
  if ( v22 > 7 )
    v14 = v20[0];
  v15 = Microsoft::Windows::Autopilot::JsonHelpers::Append(*a1, L"CurrentHardwareBlob", v14);
  v3 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x252,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v15,
      ppv);
    std::wstring::_Tidy_deallocate((char **)v20);
    VariantClear(&pvarg);
    if ( v17 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    return v3;
  }
  std::wstring::_Tidy_deallocate((char **)v20);
  VariantClear(&pvarg);
  if ( v17 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return 0;
}

```

## disassembly

```asm
0x18001ab2c  mov     [rsp-18h+arg_8], rbx
0x18001ab31  mov     [rsp-18h+arg_10], rsi
0x18001ab36  push    rbp
0x18001ab37  push    rdi
0x18001ab38  push    r14
0x18001ab3a  mov     rbp, rsp
0x18001ab3d  sub     rsp, 80h
0x18001ab44  mov     rax, cs:__security_cookie
0x18001ab4b  xor     rax, rsp
0x18001ab4e  mov     [rbp+var_8], rax
0x18001ab52  mov     rsi, rcx
0x18001ab55  xor     r14d, r14d
0x18001ab58  mov     [rbp+var_48], r14
0x18001ab5c  mov     [rbp+var_50], r14
0x18001ab60  lea     rcx, [rbp+pvarg]; pvarg
0x18001ab64  call    cs:__imp_VariantInit
0x18001ab6b  nop     dword ptr [rax+rax+00h]
0x18001ab70  nop
0x18001ab71  xorps   xmm0, xmm0
0x18001ab74  movups  xmmword ptr [rbp+var_28], xmm0
0x18001ab78  mov     [rbp+var_18], r14
0x18001ab7c  mov     [rbp+var_10], 7
0x18001ab84  mov     word ptr [rbp+var_28], r14w
0x18001ab89  mov     rcx, [rbp+var_50]
0x18001ab8d  mov     [rbp+var_50], r14
0x18001ab91  test    rcx, rcx
0x18001ab94  jz      short loc_18001ABA3
0x18001ab96  mov     rax, [rcx]
0x18001ab99  mov     rax, [rax+10h]
0x18001ab9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aba2  nop
0x18001aba3  lea     rax, [rbp+var_50]
0x18001aba7  mov     qword ptr [rsp+80h+ppv], rax; int
0x18001abac  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x18001abb3  xor     edx, edx; pUnkOuter
0x18001abb5  lea     r8d, [rdx+1]; dwClsContext
0x18001abb9  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x18001abc0  call    cs:__imp_CoCreateInstance
0x18001abc7  nop     dword ptr [rax+rax+00h]
0x18001abcc  mov     ebx, eax
0x18001abce  test    eax, eax
0x18001abd0  jns     short loc_18001AC39
0x18001abd2  mov     rcx, [rbp+18h]; this
0x18001abd6  mov     r9d, eax; char *
0x18001abd9  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001abe0  mov     edx, 24Ch; void *
0x18001abe5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001abea  nop
0x18001abeb  lea     rcx, [rbp+var_28]
0x18001abef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001abf4  nop
0x18001abf5  lea     rcx, [rbp+pvarg]; pvarg
0x18001abf9  call    cs:__imp_VariantClear
0x18001ac00  nop     dword ptr [rax+rax+00h]
0x18001ac05  nop
0x18001ac06  mov     rcx, [rbp+var_50]
0x18001ac0a  test    rcx, rcx
0x18001ac0d  jz      short loc_18001AC1C
0x18001ac0f  mov     rax, [rcx]
0x18001ac12  mov     rax, [rax+10h]
0x18001ac16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac1b  nop
0x18001ac1c  mov     rcx, [rbp+var_48]
0x18001ac20  test    rcx, rcx
0x18001ac23  jz      short loc_18001AC32
0x18001ac25  mov     rax, [rcx]
0x18001ac28  mov     rax, [rax+10h]
0x18001ac2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac31  nop
0x18001ac32  mov     eax, ebx
0x18001ac34  jmp     loc_18001AEF3
0x18001ac39  mov     rbx, [rbp+var_50]
0x18001ac3d  mov     rax, [rbx]
0x18001ac40  mov     rdi, [rax+50h]
0x18001ac44  mov     rdx, [rbp+var_48]
0x18001ac48  mov     [rbp+var_48], r14
0x18001ac4c  test    rdx, rdx
0x18001ac4f  jz      short loc_18001AC61
0x18001ac51  mov     rcx, [rdx]
0x18001ac54  mov     rax, [rcx+10h]
0x18001ac58  mov     rcx, rdx
0x18001ac5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac60  nop
0x18001ac61  lea     r8, [rbp+var_48]
0x18001ac65  lea     rdx, aDevdetailExtDe; "./DevDetail/Ext/DeviceHardwareData"
0x18001ac6c  mov     rcx, rbx
0x18001ac6f  mov     rax, rdi
0x18001ac72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac77  mov     ebx, eax
0x18001ac79  test    eax, eax
0x18001ac7b  jns     short loc_18001ACE2
0x18001ac7d  mov     rcx, [rbp+18h]; this
0x18001ac81  mov     r9d, eax; char *
0x18001ac84  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ac8b  mov     edx, 24Dh; void *
0x18001ac90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ac95  nop
0x18001ac96  lea     rcx, [rbp+var_28]
0x18001ac9a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ac9f  nop
0x18001aca0  lea     rcx, [rbp+pvarg]; pvarg
0x18001aca4  call    cs:__imp_VariantClear
0x18001acab  nop     dword ptr [rax+rax+00h]
0x18001acb0  nop
0x18001acb1  mov     rcx, [rbp+var_50]
0x18001acb5  test    rcx, rcx
0x18001acb8  jz      short loc_18001ACC7
0x18001acba  mov     rax, [rcx]
0x18001acbd  mov     rax, [rax+10h]
0x18001acc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acc6  nop
0x18001acc7  mov     rcx, [rbp+var_48]
0x18001accb  test    rcx, rcx
0x18001acce  jz      short loc_18001ACDD
0x18001acd0  mov     rax, [rcx]
0x18001acd3  mov     rax, [rax+10h]
0x18001acd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acdc  nop
0x18001acdd  jmp     loc_18001AC32
0x18001ace2  mov     rcx, [rbp+var_48]
0x18001ace6  mov     rax, [rcx]
0x18001ace9  lea     rdx, [rbp+pvarg]
0x18001aced  mov     rax, [rax+68h]
0x18001acf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acf6  mov     ebx, eax
0x18001acf8  test    eax, eax
0x18001acfa  jns     short loc_18001AD61
0x18001acfc  mov     rcx, [rbp+18h]; this
0x18001ad00  mov     r9d, eax; char *
0x18001ad03  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ad0a  mov     edx, 24Eh; void *
0x18001ad0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ad14  nop
0x18001ad15  lea     rcx, [rbp+var_28]
0x18001ad19  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ad1e  nop
0x18001ad1f  lea     rcx, [rbp+pvarg]; pvarg
0x18001ad23  call    cs:__imp_VariantClear
0x18001ad2a  nop     dword ptr [rax+rax+00h]
0x18001ad2f  nop
0x18001ad30  mov     rcx, [rbp+var_50]
0x18001ad34  test    rcx, rcx
0x18001ad37  jz      short loc_18001AD46
0x18001ad39  mov     rax, [rcx]
0x18001ad3c  mov     rax, [rax+10h]
0x18001ad40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad45  nop
0x18001ad46  mov     rcx, [rbp+var_48]
0x18001ad4a  test    rcx, rcx
0x18001ad4d  jz      short loc_18001AD5C
0x18001ad4f  mov     rax, [rcx]
0x18001ad52  mov     rax, [rax+10h]
0x18001ad56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad5b  nop
0x18001ad5c  jmp     loc_18001AC32
0x18001ad61  mov     eax, 8
0x18001ad66  cmp     ax, word ptr [rbp+pvarg]
0x18001ad6a  jz      short loc_18001ADD6
0x18001ad6c  mov     rcx, [rbp+18h]; this
0x18001ad70  mov     ebx, 8000FFFFh
0x18001ad75  mov     r9d, ebx; char *
0x18001ad78  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ad7f  mov     edx, 24Fh; void *
0x18001ad84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ad89  nop
0x18001ad8a  lea     rcx, [rbp+var_28]
0x18001ad8e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ad93  nop
0x18001ad94  lea     rcx, [rbp+pvarg]; pvarg
0x18001ad98  call    cs:__imp_VariantClear
0x18001ad9f  nop     dword ptr [rax+rax+00h]
0x18001ada4  nop
0x18001ada5  mov     rcx, [rbp+var_50]
0x18001ada9  test    rcx, rcx
0x18001adac  jz      short loc_18001ADBB
0x18001adae  mov     rax, [rcx]
0x18001adb1  mov     rax, [rax+10h]
0x18001adb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adba  nop
0x18001adbb  mov     rcx, [rbp+var_48]
0x18001adbf  test    rcx, rcx
0x18001adc2  jz      short loc_18001ADD1
0x18001adc4  mov     rdx, [rcx]
0x18001adc7  mov     rax, [rdx+10h]
0x18001adcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001add0  nop
0x18001add1  jmp     loc_18001AC32
0x18001add6  mov     r9, qword ptr [rbp+pvarg+8]
0x18001adda  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001adde  inc     rdx
0x18001ade1  cmp     [r9+rdx*2], r14w
0x18001ade6  jnz     short loc_18001ADDE
0x18001ade8  cmp     rdx, [rbp+var_10]
0x18001adec  ja      short loc_18001AE19
0x18001adee  lea     rdi, [rbp+var_28]
0x18001adf2  cmp     [rbp+var_10], 7
0x18001adf7  cmova   rdi, [rbp+var_28]
0x18001adfc  mov     [rbp+var_18], rdx
0x18001ae00  lea     rbx, [rdx+rdx]
0x18001ae04  mov     r8, rbx; Size
0x18001ae07  mov     rdx, r9; Src
0x18001ae0a  mov     rcx, rdi; void *
0x18001ae0d  call    memmove_0
0x18001ae12  mov     [rbx+rdi], r14w
0x18001ae17  jmp     short loc_18001AE22
0x18001ae19  lea     rcx, [rbp+var_28]
0x18001ae1d  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001ae22  lea     r8, [rbp+var_28]
0x18001ae26  cmp     [rbp+var_10], 7
0x18001ae2b  cmova   r8, [rbp+var_28]; unsigned __int16 *
0x18001ae30  lea     rdx, aCurrenthardwar; "CurrentHardwareBlob"
0x18001ae37  mov     rcx, [rsi]; struct Windows::Data::Json::IJsonObject *
0x18001ae3a  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18001ae3f  mov     ebx, eax
0x18001ae41  test    eax, eax
0x18001ae43  jns     short loc_18001AEAA
0x18001ae45  mov     rcx, [rbp+18h]; this
0x18001ae49  mov     r9d, eax; char *
0x18001ae4c  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ae53  mov     edx, 252h; void *
0x18001ae58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ae5d  nop
0x18001ae5e  lea     rcx, [rbp+var_28]
0x18001ae62  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ae67  nop
0x18001ae68  lea     rcx, [rbp+pvarg]; pvarg
0x18001ae6c  call    cs:__imp_VariantClear
0x18001ae73  nop     dword ptr [rax+rax+00h]
0x18001ae78  nop
0x18001ae79  mov     rcx, [rbp+var_50]
0x18001ae7d  test    rcx, rcx
0x18001ae80  jz      short loc_18001AE8F
0x18001ae82  mov     rax, [rcx]
0x18001ae85  mov     rax, [rax+10h]
0x18001ae89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae8e  nop
0x18001ae8f  mov     rcx, [rbp+var_48]
0x18001ae93  test    rcx, rcx
0x18001ae96  jz      short loc_18001AEA5
0x18001ae98  mov     rax, [rcx]
0x18001ae9b  mov     rax, [rax+10h]
0x18001ae9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aea4  nop
0x18001aea5  jmp     loc_18001AC32
0x18001aeaa  lea     rcx, [rbp+var_28]
0x18001aeae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001aeb3  nop
0x18001aeb4  lea     rcx, [rbp+pvarg]; pvarg
0x18001aeb8  call    cs:__imp_VariantClear
0x18001aebf  nop     dword ptr [rax+rax+00h]
0x18001aec4  nop
0x18001aec5  mov     rcx, [rbp+var_50]
0x18001aec9  test    rcx, rcx
0x18001aecc  jz      short loc_18001AEDB
0x18001aece  mov     rax, [rcx]
0x18001aed1  mov     rax, [rax+10h]
0x18001aed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aeda  nop
0x18001aedb  mov     rcx, [rbp+var_48]
0x18001aedf  test    rcx, rcx
0x18001aee2  jz      short loc_18001AEF1
0x18001aee4  mov     rax, [rcx]
0x18001aee7  mov     rax, [rax+10h]
0x18001aeeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aef0  nop
0x18001aef1  xor     eax, eax
0x18001aef3  mov     rcx, [rbp+var_8]
0x18001aef7  xor     rcx, rsp; StackCookie
0x18001aefa  call    __security_check_cookie
0x18001aeff  lea     r11, [rsp+80h+var_s0]
0x18001af07  mov     rbx, [r11+28h]
0x18001af0b  mov     rsi, [r11+30h]
0x18001af0f  mov     rsp, r11
0x18001af12  pop     r14
0x18001af14  pop     rdi
0x18001af15  pop     rbp
0x18001af16  retn
```
