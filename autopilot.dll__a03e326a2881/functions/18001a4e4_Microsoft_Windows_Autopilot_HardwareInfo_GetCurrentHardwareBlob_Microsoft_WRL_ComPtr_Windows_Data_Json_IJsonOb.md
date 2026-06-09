# Microsoft::Windows::Autopilot::HardwareInfo::GetCurrentHardwareBlob(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x18001a4e4`
- end: `0x18001a89f`
- name: `?GetCurrentHardwareBlob@HardwareInfo@Autopilot@Windows@Microsoft@@CAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z`
- size: `955`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ada0`

## callees

- `0x1800045b0`
- `0x180009957`
- `0x1800105f4`
- `0x1800174f0`
- `0x180018cd0`
- `0x18001a4e4`
- `0x18001e7b4`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a572`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a572`
- `OLEAUT32!__imp_VariantInit` at `0x18001a51c`
- `OLEAUT32!__imp_VariantInit` at `0x18001a51c`
- `OLEAUT32!__imp_VariantClear` at `0x18001a5a5`
- `OLEAUT32!__imp_VariantClear` at `0x18001a64a`
- `OLEAUT32!__imp_VariantClear` at `0x18001a6c3`
- `OLEAUT32!__imp_VariantClear` at `0x18001a732`
- `OLEAUT32!__imp_VariantClear` at `0x18001a800`
- `OLEAUT32!__imp_VariantClear` at `0x18001a846`
- `OLEAUT32!__imp_VariantClear` at `0x18001a5a5`
- `OLEAUT32!__imp_VariantClear` at `0x18001a64a`
- `OLEAUT32!__imp_VariantClear` at `0x18001a6c3`
- `OLEAUT32!__imp_VariantClear` at `0x18001a732`
- `OLEAUT32!__imp_VariantClear` at `0x18001a800`
- `OLEAUT32!__imp_VariantClear` at `0x18001a846`

## string_xrefs

- `0x18001a585`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001a62a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001a6a3`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001a712`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001a7e0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
    std::wstring::_Tidy_deallocate(v20);
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
    std::wstring::_Tidy_deallocate(v20);
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
    std::wstring::_Tidy_deallocate(v20);
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
    std::wstring::_Tidy_deallocate(v20);
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
      v20,
      v11,
      v10,
      pvarg.llVal);
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
    std::wstring::_Tidy_deallocate(v20);
    VariantClear(&pvarg);
    if ( v17 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    return v3;
  }
  std::wstring::_Tidy_deallocate(v20);
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
0x18001a4e4  mov     [rsp-18h+arg_8], rbx
0x18001a4e9  mov     [rsp-18h+arg_10], rsi
0x18001a4ee  push    rbp
0x18001a4ef  push    rdi
0x18001a4f0  push    r14
0x18001a4f2  mov     rbp, rsp
0x18001a4f5  sub     rsp, 80h
0x18001a4fc  mov     rax, cs:__security_cookie
0x18001a503  xor     rax, rsp
0x18001a506  mov     [rbp+var_8], rax
0x18001a50a  mov     rsi, rcx
0x18001a50d  xor     r14d, r14d
0x18001a510  mov     [rbp+var_48], r14
0x18001a514  mov     [rbp+var_50], r14
0x18001a518  lea     rcx, [rbp+pvarg]; pvarg
0x18001a51c  call    cs:__imp_VariantInit
0x18001a522  nop
0x18001a523  xorps   xmm0, xmm0
0x18001a526  movups  xmmword ptr [rbp+var_28], xmm0
0x18001a52a  mov     [rbp+var_18], r14
0x18001a52e  mov     [rbp+var_10], 7
0x18001a536  mov     word ptr [rbp+var_28], r14w
0x18001a53b  mov     rcx, [rbp+var_50]
0x18001a53f  mov     [rbp+var_50], r14
0x18001a543  test    rcx, rcx
0x18001a546  jz      short loc_18001A555
0x18001a548  mov     rax, [rcx]
0x18001a54b  mov     rax, [rax+10h]
0x18001a54f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a554  nop
0x18001a555  lea     rax, [rbp+var_50]
0x18001a559  mov     qword ptr [rsp+80h+ppv], rax; int
0x18001a55e  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x18001a565  xor     edx, edx; pUnkOuter
0x18001a567  lea     r8d, [rdx+1]; dwClsContext
0x18001a56b  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x18001a572  call    cs:__imp_CoCreateInstance
0x18001a578  mov     ebx, eax
0x18001a57a  test    eax, eax
0x18001a57c  jns     short loc_18001A5DF
0x18001a57e  mov     rcx, [rbp+18h]; this
0x18001a582  mov     r9d, eax; char *
0x18001a585  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a58c  mov     edx, 24Ch; void *
0x18001a591  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a596  nop
0x18001a597  lea     rcx, [rbp+var_28]
0x18001a59b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a5a0  nop
0x18001a5a1  lea     rcx, [rbp+pvarg]; pvarg
0x18001a5a5  call    cs:__imp_VariantClear
0x18001a5ab  nop
0x18001a5ac  mov     rcx, [rbp+var_50]
0x18001a5b0  test    rcx, rcx
0x18001a5b3  jz      short loc_18001A5C2
0x18001a5b5  mov     rax, [rcx]
0x18001a5b8  mov     rax, [rax+10h]
0x18001a5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5c1  nop
0x18001a5c2  mov     rcx, [rbp+var_48]
0x18001a5c6  test    rcx, rcx
0x18001a5c9  jz      short loc_18001A5D8
0x18001a5cb  mov     rax, [rcx]
0x18001a5ce  mov     rax, [rax+10h]
0x18001a5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5d7  nop
0x18001a5d8  mov     eax, ebx
0x18001a5da  jmp     loc_18001A87B
0x18001a5df  mov     rbx, [rbp+var_50]
0x18001a5e3  mov     rax, [rbx]
0x18001a5e6  mov     rdi, [rax+50h]
0x18001a5ea  mov     rdx, [rbp+var_48]
0x18001a5ee  mov     [rbp+var_48], r14
0x18001a5f2  test    rdx, rdx
0x18001a5f5  jz      short loc_18001A607
0x18001a5f7  mov     rcx, [rdx]
0x18001a5fa  mov     rax, [rcx+10h]
0x18001a5fe  mov     rcx, rdx
0x18001a601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a606  nop
0x18001a607  lea     r8, [rbp+var_48]
0x18001a60b  lea     rdx, aDevdetailExtDe; "./DevDetail/Ext/DeviceHardwareData"
0x18001a612  mov     rcx, rbx
0x18001a615  mov     rax, rdi
0x18001a618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a61d  mov     ebx, eax
0x18001a61f  test    eax, eax
0x18001a621  jns     short loc_18001A682
0x18001a623  mov     rcx, [rbp+18h]; this
0x18001a627  mov     r9d, eax; char *
0x18001a62a  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a631  mov     edx, 24Dh; void *
0x18001a636  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a63b  nop
0x18001a63c  lea     rcx, [rbp+var_28]
0x18001a640  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a645  nop
0x18001a646  lea     rcx, [rbp+pvarg]; pvarg
0x18001a64a  call    cs:__imp_VariantClear
0x18001a650  nop
0x18001a651  mov     rcx, [rbp+var_50]
0x18001a655  test    rcx, rcx
0x18001a658  jz      short loc_18001A667
0x18001a65a  mov     rax, [rcx]
0x18001a65d  mov     rax, [rax+10h]
0x18001a661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a666  nop
0x18001a667  mov     rcx, [rbp+var_48]
0x18001a66b  test    rcx, rcx
0x18001a66e  jz      short loc_18001A67D
0x18001a670  mov     rax, [rcx]
0x18001a673  mov     rax, [rax+10h]
0x18001a677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a67c  nop
0x18001a67d  jmp     loc_18001A5D8
0x18001a682  mov     rcx, [rbp+var_48]
0x18001a686  mov     rax, [rcx]
0x18001a689  lea     rdx, [rbp+pvarg]
0x18001a68d  mov     rax, [rax+68h]
0x18001a691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a696  mov     ebx, eax
0x18001a698  test    eax, eax
0x18001a69a  jns     short loc_18001A6FB
0x18001a69c  mov     rcx, [rbp+18h]; this
0x18001a6a0  mov     r9d, eax; char *
0x18001a6a3  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a6aa  mov     edx, 24Eh; void *
0x18001a6af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a6b4  nop
0x18001a6b5  lea     rcx, [rbp+var_28]
0x18001a6b9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a6be  nop
0x18001a6bf  lea     rcx, [rbp+pvarg]; pvarg
0x18001a6c3  call    cs:__imp_VariantClear
0x18001a6c9  nop
0x18001a6ca  mov     rcx, [rbp+var_50]
0x18001a6ce  test    rcx, rcx
0x18001a6d1  jz      short loc_18001A6E0
0x18001a6d3  mov     rax, [rcx]
0x18001a6d6  mov     rax, [rax+10h]
0x18001a6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6df  nop
0x18001a6e0  mov     rcx, [rbp+var_48]
0x18001a6e4  test    rcx, rcx
0x18001a6e7  jz      short loc_18001A6F6
0x18001a6e9  mov     rax, [rcx]
0x18001a6ec  mov     rax, [rax+10h]
0x18001a6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6f5  nop
0x18001a6f6  jmp     loc_18001A5D8
0x18001a6fb  mov     eax, 8
0x18001a700  cmp     ax, word ptr [rbp+pvarg]
0x18001a704  jz      short loc_18001A76A
0x18001a706  mov     rcx, [rbp+18h]; this
0x18001a70a  mov     ebx, 8000FFFFh
0x18001a70f  mov     r9d, ebx; char *
0x18001a712  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a719  mov     edx, 24Fh; void *
0x18001a71e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a723  nop
0x18001a724  lea     rcx, [rbp+var_28]
0x18001a728  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a72d  nop
0x18001a72e  lea     rcx, [rbp+pvarg]; pvarg
0x18001a732  call    cs:__imp_VariantClear
0x18001a738  nop
0x18001a739  mov     rcx, [rbp+var_50]
0x18001a73d  test    rcx, rcx
0x18001a740  jz      short loc_18001A74F
0x18001a742  mov     rax, [rcx]
0x18001a745  mov     rax, [rax+10h]
0x18001a749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a74e  nop
0x18001a74f  mov     rcx, [rbp+var_48]
0x18001a753  test    rcx, rcx
0x18001a756  jz      short loc_18001A765
0x18001a758  mov     rdx, [rcx]
0x18001a75b  mov     rax, [rdx+10h]
0x18001a75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a764  nop
0x18001a765  jmp     loc_18001A5D8
0x18001a76a  mov     r9, qword ptr [rbp+pvarg+8]
0x18001a76e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001a772  inc     rdx
0x18001a775  cmp     [r9+rdx*2], r14w
0x18001a77a  jnz     short loc_18001A772
0x18001a77c  cmp     rdx, [rbp+var_10]
0x18001a780  ja      short loc_18001A7AD
0x18001a782  lea     rdi, [rbp+var_28]
0x18001a786  cmp     [rbp+var_10], 7
0x18001a78b  cmova   rdi, [rbp+var_28]
0x18001a790  mov     [rbp+var_18], rdx
0x18001a794  lea     rbx, [rdx+rdx]
0x18001a798  mov     r8, rbx; Size
0x18001a79b  mov     rdx, r9; Src
0x18001a79e  mov     rcx, rdi; void *
0x18001a7a1  call    memmove_0
0x18001a7a6  mov     [rbx+rdi], r14w
0x18001a7ab  jmp     short loc_18001A7B6
0x18001a7ad  lea     rcx, [rbp+var_28]
0x18001a7b1  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001a7b6  lea     r8, [rbp+var_28]
0x18001a7ba  cmp     [rbp+var_10], 7
0x18001a7bf  cmova   r8, [rbp+var_28]; unsigned __int16 *
0x18001a7c4  lea     rdx, aCurrenthardwar; "CurrentHardwareBlob"
0x18001a7cb  mov     rcx, [rsi]; struct Windows::Data::Json::IJsonObject *
0x18001a7ce  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18001a7d3  mov     ebx, eax
0x18001a7d5  test    eax, eax
0x18001a7d7  jns     short loc_18001A838
0x18001a7d9  mov     rcx, [rbp+18h]; this
0x18001a7dd  mov     r9d, eax; char *
0x18001a7e0  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a7e7  mov     edx, 252h; void *
0x18001a7ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a7f1  nop
0x18001a7f2  lea     rcx, [rbp+var_28]
0x18001a7f6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a7fb  nop
0x18001a7fc  lea     rcx, [rbp+pvarg]; pvarg
0x18001a800  call    cs:__imp_VariantClear
0x18001a806  nop
0x18001a807  mov     rcx, [rbp+var_50]
0x18001a80b  test    rcx, rcx
0x18001a80e  jz      short loc_18001A81D
0x18001a810  mov     rax, [rcx]
0x18001a813  mov     rax, [rax+10h]
0x18001a817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a81c  nop
0x18001a81d  mov     rcx, [rbp+var_48]
0x18001a821  test    rcx, rcx
0x18001a824  jz      short loc_18001A833
0x18001a826  mov     rax, [rcx]
0x18001a829  mov     rax, [rax+10h]
0x18001a82d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a832  nop
0x18001a833  jmp     loc_18001A5D8
0x18001a838  lea     rcx, [rbp+var_28]
0x18001a83c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a841  nop
0x18001a842  lea     rcx, [rbp+pvarg]; pvarg
0x18001a846  call    cs:__imp_VariantClear
0x18001a84c  nop
0x18001a84d  mov     rcx, [rbp+var_50]
0x18001a851  test    rcx, rcx
0x18001a854  jz      short loc_18001A863
0x18001a856  mov     rax, [rcx]
0x18001a859  mov     rax, [rax+10h]
0x18001a85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a862  nop
0x18001a863  mov     rcx, [rbp+var_48]
0x18001a867  test    rcx, rcx
0x18001a86a  jz      short loc_18001A879
0x18001a86c  mov     rax, [rcx]
0x18001a86f  mov     rax, [rax+10h]
0x18001a873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a878  nop
0x18001a879  xor     eax, eax
0x18001a87b  mov     rcx, [rbp+var_8]
0x18001a87f  xor     rcx, rsp; StackCookie
0x18001a882  call    __security_check_cookie
0x18001a887  lea     r11, [rsp+80h+var_s0]
0x18001a88f  mov     rbx, [r11+28h]
0x18001a893  mov     rsi, [r11+30h]
0x18001a897  mov     rsp, r11
0x18001a89a  pop     r14
0x18001a89c  pop     rdi
0x18001a89d  pop     rbp
0x18001a89e  retn
```
