# _anonymous_namespace_::LoadPreviewThumbnail

- ea: `0x180174ab4`
- end: `0x180174e08`
- name: `_anonymous_namespace_::LoadPreviewThumbnail`
- size: `852`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180174700`

## callees

- `0x1800236e0`
- `0x1800496fc`
- `0x1800d55c0`
- `0x1800dffb0`
- `0x180172324`
- `0x180172d08`
- `0x180173f7c`
- `0x18017469c`
- `0x180174ab4`
- `0x180174ef8`
- `0x180197f28`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180174cc8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180174cc8`
- `USER32!GetSystemMetrics` at `0x180174c71`
- `USER32!GetSystemMetrics` at `0x180174c84`
- `USER32!GetSystemMetrics` at `0x180174c71`
- `USER32!GetSystemMetrics` at `0x180174c84`
- `SHELL32!SHCreateItemFromParsingName` at `0x180174b24`
- `SHELL32!SHCreateItemFromParsingName` at `0x180174b24`
- `SHCORE!CreateRandomAccessStreamOverStream` at `0x180174be3`
- `SHCORE!CreateRandomAccessStreamOverStream` at `0x180174d23`
- `SHCORE!CreateRandomAccessStreamOverStream` at `0x180174be3`
- `SHCORE!CreateRandomAccessStreamOverStream` at `0x180174d23`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
SystemSettings::Personalization *__fastcall anonymous_namespace_::LoadPreviewThumbnail(
        SystemSettings::Personalization *a1,
        const WCHAR *a2,
        unsigned __int64 a3)
{
  __m128 v5; // xmm7
  __int64 v6; // rdx
  HRESULT v7; // eax
  __int64 (__fastcall **v8)(void *, GUID *, __int64 **); // rax
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  struct IUnknown *v13; // rdx
  void **v14; // rax
  int RandomAccessStreamOverStream; // eax
  __int64 v16; // rax
  int SystemMetrics; // esi
  int v18; // eax
  __m128 v19; // xmm6
  __m128 v20; // xmm8
  int v21; // esi
  struct IUnknown *v22; // rdx
  void **v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v27; // [rsp+28h] [rbp-49h]
  __int64 v28; // [rsp+40h] [rbp-31h] BYREF
  __int64 *v29; // [rsp+48h] [rbp-29h] BYREF
  _QWORD v30[2]; // [rsp+50h] [rbp-21h] BYREF
  void *ppv; // [rsp+60h] [rbp-11h] BYREF
  unsigned __int64 v32; // [rsp+68h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]
  __int64 v34; // [rsp+F0h] [rbp+7Fh] BYREF

  v5 = (__m128)a3;
  v32 = a3;
  if ( SystemSettings::Personalization::IsVideoWallpaperSupported(a1)
    && (unsigned __int8)anonymous_namespace_::IsVideoFile(v6) )
  {
    ppv = 0;
    v7 = SHCreateItemFromParsingName(a2, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD9,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
        (const char *)(unsigned int)v7,
        v27);
    v29 = 0;
    v8 = *(__int64 (__fastcall ***)(void *, GUID *, __int64 **))ppv;
    v29 = 0;
    v9 = (*v8)(ppv, &GUID_bcc18b79_ba16_442f_80c4_8a59c30c463b, &v29);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDD,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
        (const char *)(unsigned int)v9,
        v27);
    LODWORD(v30[0]) = (int)v5.m128_f32[0];
    HIDWORD(v30[0]) = (int)*((float *)&v32 + 1);
    v28 = 0;
    v10 = *v29;
    v28 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, __int64 *))(v10 + 24))(v29, v30[0], 8, &v28);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE6,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
        (const char *)(unsigned int)v11,
        v27);
    v30[0] = 0;
    v12 = anonymous_namespace_::SaveHBITMAPToStream(v28, v30);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
        (const char *)(unsigned int)v12,
        v27);
    v34 = 0;
    v14 = winrt::put_abi((winrt *)&v34, v13);
    RandomAccessStreamOverStream = CreateRandomAccessStreamOverStream(
                                     v30[0],
                                     0,
                                     &winrt::impl::guid_v<winrt::Windows::Storage::Streams::IRandomAccessStream>,
                                     v14);
    if ( RandomAccessStreamOverStream < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xED,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
        (const char *)(unsigned int)RandomAccessStreamOverStream,
        v27);
    v16 = v34;
    v34 = 0;
    *(_QWORD *)a1 = v16;
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v34);
    wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(v30);
    wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>(&v28);
    wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v29);
    wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&ppv);
  }
  else if ( !a2 || !*a2 || v5.m128_f32[0] == 0.0 || *((float *)&v32 + 1) == 0.0 )
  {
    *(_QWORD *)a1 = 0;
  }
  else
  {
    SystemMetrics = GetSystemMetrics(0);
    v18 = GetSystemMetrics(1);
    v19 = (__m128)LODWORD(FLOAT_1_0);
    v20 = (__m128)LODWORD(FLOAT_1_0);
    if ( SystemMetrics && v18 )
    {
      v19 = v5;
      v19.m128_f32[0] = v5.m128_f32[0] / (float)SystemMetrics;
      v20 = (__m128)HIDWORD(v32);
      v20.m128_f32[0] = *((float *)&v32 + 1) / (float)v18;
    }
    v21 = 0;
    if ( !*PathFindExtensionW(a2) )
    {
      wil::basic_zstring_view<unsigned short>::basic_zstring_view<unsigned short>(v30);
      v21 = v30[0];
    }
    anonymous_namespace_::GetStreamRatio(&ppv, a2, _mm_unpacklo_ps(v19, v20).m128_u64[0], v30);
    v34 = 0;
    v23 = winrt::put_abi((winrt *)&v34, v22);
    v24 = CreateRandomAccessStreamOverStream(
            ppv,
            0,
            &winrt::impl::guid_v<winrt::Windows::Storage::Streams::IRandomAccessStream>,
            v23);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x113,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
        (const char *)(unsigned int)v24,
        v21);
    v25 = v34;
    v34 = 0;
    *(_QWORD *)a1 = v25;
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v34);
    wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&ppv);
  }
  return a1;
}

```

## disassembly

```asm
0x180174ab4  mov     rax, rsp
0x180174ab7  mov     [rax+8], rbx
0x180174abb  mov     [rax+10h], rsi
0x180174abf  push    rbp
0x180174ac0  push    rdi
0x180174ac1  push    r14
0x180174ac3  lea     rbp, [rax-5Fh]
0x180174ac7  sub     rsp, 0B0h
0x180174ace  movaps  xmmword ptr [rax-28h], xmm6
0x180174ad2  movaps  xmmword ptr [rax-38h], xmm7
0x180174ad6  movaps  xmmword ptr [rax-48h], xmm8
0x180174adb  movaps  xmmword ptr [rax-58h], xmm9
0x180174ae0  mov     rdi, rdx
0x180174ae3  mov     rbx, rcx
0x180174ae6  movq    xmm7, r8
0x180174aeb  movsd   [rbp+57h+var_60], xmm7
0x180174af0  xor     r14d, r14d
0x180174af3  call    ?IsVideoWallpaperSupported@Personalization@SystemSettings@@YA_NXZ; SystemSettings::Personalization::IsVideoWallpaperSupported(void)
0x180174af8  test    al, al
0x180174afa  jz      loc_180174C3C
0x180174b00  mov     rcx, rdx
0x180174b03  call    _anonymous_namespace___IsVideoFile
0x180174b08  test    al, al
0x180174b0a  jz      loc_180174C3C
0x180174b10  mov     [rbp+57h+ppv], r14
0x180174b14  lea     r9, [rbp+57h+ppv]; ppv
0x180174b18  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180174b1f  xor     edx, edx; pbc
0x180174b21  mov     rcx, rdi; pszPath
0x180174b24  call    cs:__imp_SHCreateItemFromParsingName
0x180174b2b  nop     dword ptr [rax+rax+00h]
0x180174b30  mov     rcx, [rbp+5Fh]; this
0x180174b34  test    eax, eax
0x180174b36  js      loc_180174D9F
0x180174b3c  mov     [rbp+57h+var_80], r14
0x180174b40  mov     rcx, [rbp+57h+ppv]
0x180174b44  mov     rax, [rcx]
0x180174b47  mov     [rbp+57h+var_80], r14
0x180174b4b  lea     r8, [rbp+57h+var_80]
0x180174b4f  lea     rdx, _GUID_bcc18b79_ba16_442f_80c4_8a59c30c463b
0x180174b56  mov     rax, [rax]
0x180174b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180174b5e  mov     rcx, [rbp+5Fh]; this
0x180174b62  test    eax, eax
0x180174b64  js      loc_180174DB4
0x180174b6a  cvttss2si eax, xmm7
0x180174b6e  mov     dword ptr [rbp+57h+var_78], eax
0x180174b71  cvttss2si eax, dword ptr [rbp+57h+var_60+4]
0x180174b76  mov     dword ptr [rbp+57h+var_78+4], eax
0x180174b79  mov     [rbp+57h+var_88], r14
0x180174b7d  mov     rcx, [rbp+57h+var_80]
0x180174b81  mov     rax, [rcx]
0x180174b84  mov     [rbp+57h+var_88], r14
0x180174b88  lea     r9, [rbp+57h+var_88]
0x180174b8c  lea     r8d, [r14+8]
0x180174b90  mov     rdx, [rbp+57h+var_78]
0x180174b94  mov     rax, [rax+18h]
0x180174b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180174b9d  mov     rcx, [rbp+5Fh]; this
0x180174ba1  test    eax, eax
0x180174ba3  js      loc_180174DC9
0x180174ba9  mov     [rbp+57h+var_78], r14
0x180174bad  lea     rdx, [rbp+57h+var_78]
0x180174bb1  mov     rcx, [rbp+57h+var_88]
0x180174bb5  call    _anonymous_namespace___SaveHBITMAPToStream
0x180174bba  mov     rcx, [rbp+5Fh]; this
0x180174bbe  test    eax, eax
0x180174bc0  js      loc_180174DDE
0x180174bc6  mov     [rbp+57h+arg_18], r14
0x180174bca  lea     rcx, [rbp+57h+arg_18]; this
0x180174bce  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x180174bd3  mov     r9, rax
0x180174bd6  lea     r8, ??$guid_v@UIRandomAccessStream@Streams@Storage@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Storage::Streams::IRandomAccessStream>
0x180174bdd  xor     edx, edx
0x180174bdf  mov     rcx, [rbp+57h+var_78]
0x180174be3  call    cs:__imp_CreateRandomAccessStreamOverStream
0x180174bea  nop     dword ptr [rax+rax+00h]
0x180174bef  mov     rcx, [rbp+5Fh]; this
0x180174bf3  test    eax, eax
0x180174bf5  js      loc_180174DF3
0x180174bfb  mov     rax, [rbp+57h+arg_18]
0x180174bff  mov     [rbp+57h+arg_18], r14
0x180174c03  mov     [rbx], rax
0x180174c06  lea     rcx, [rbp+57h+arg_18]; this
0x180174c0a  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x180174c0f  nop
0x180174c10  lea     rcx, [rbp+57h+var_78]
0x180174c14  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x180174c19  nop
0x180174c1a  lea     rcx, [rbp+57h+var_88]
0x180174c1e  call    ??1?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>(void)
0x180174c23  nop
0x180174c24  lea     rcx, [rbp+57h+var_80]
0x180174c28  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x180174c2d  nop
0x180174c2e  lea     rcx, [rbp+57h+ppv]
0x180174c32  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x180174c37  jmp     loc_180174D5A
0x180174c3c  test    rdi, rdi
0x180174c3f  jz      loc_180174D57
0x180174c45  cmp     [rdi], r14w
0x180174c49  jz      loc_180174D57
0x180174c4f  xorps   xmm0, xmm0
0x180174c52  ucomiss xmm7, xmm0
0x180174c55  jp      short loc_180174C5D
0x180174c57  jz      loc_180174D57
0x180174c5d  movss   xmm9, dword ptr [rbp+57h+var_60+4]
0x180174c63  ucomiss xmm9, xmm0
0x180174c67  jp      short loc_180174C6F
0x180174c69  jz      loc_180174D57
0x180174c6f  xor     ecx, ecx; nIndex
0x180174c71  call    cs:__imp_GetSystemMetrics
0x180174c78  nop     dword ptr [rax+rax+00h]
0x180174c7d  mov     esi, eax
0x180174c7f  mov     ecx, 1; nIndex
0x180174c84  call    cs:__imp_GetSystemMetrics
0x180174c8b  nop     dword ptr [rax+rax+00h]
0x180174c90  movss   xmm6, cs:__real@3f800000
0x180174c98  movaps  xmm8, xmm6
0x180174c9c  test    esi, esi
0x180174c9e  jz      short loc_180174CC2
0x180174ca0  test    eax, eax
0x180174ca2  jz      short loc_180174CC2
0x180174ca4  movd    xmm0, esi
0x180174ca8  cvtdq2ps xmm0, xmm0
0x180174cab  movaps  xmm6, xmm7
0x180174cae  divss   xmm6, xmm0
0x180174cb2  movd    xmm1, eax
0x180174cb6  cvtdq2ps xmm1, xmm1
0x180174cb9  movaps  xmm8, xmm9
0x180174cbd  divss   xmm8, xmm1
0x180174cc2  mov     rsi, r14
0x180174cc5  mov     rcx, rdi; pszPath
0x180174cc8  call    cs:__imp_PathFindExtensionW
0x180174ccf  nop     dword ptr [rax+rax+00h]
0x180174cd4  cmp     [rax], r14w
0x180174cd8  jnz     short loc_180174CE7
0x180174cda  lea     rcx, [rbp+57h+var_78]
0x180174cde  call    ??$?0$08@?$basic_zstring_view@G@wil@@QEAA@AEAY08$$CBG@Z; wil::basic_zstring_view<ushort>::basic_zstring_view<ushort>(ushort const (&)[9])
0x180174ce3  mov     rsi, [rbp+57h+var_78]
0x180174ce7  mov     qword ptr [rsp+0C0h+var_A0], rsi; int
0x180174cec  lea     r9, [rbp+57h+var_78]
0x180174cf0  unpcklps xmm6, xmm8
0x180174cf4  movq    r8, xmm6
0x180174cf9  mov     rdx, rdi
0x180174cfc  lea     rcx, [rbp+57h+ppv]
0x180174d00  call    _anonymous_namespace___GetStreamRatio
0x180174d05  nop
0x180174d06  mov     [rbp+57h+arg_18], r14
0x180174d0a  lea     rcx, [rbp+57h+arg_18]; this
0x180174d0e  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x180174d13  mov     r9, rax
0x180174d16  lea     r8, ??$guid_v@UIRandomAccessStream@Streams@Storage@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Storage::Streams::IRandomAccessStream>
0x180174d1d  xor     edx, edx
0x180174d1f  mov     rcx, [rbp+57h+ppv]
0x180174d23  call    cs:__imp_CreateRandomAccessStreamOverStream
0x180174d2a  nop     dword ptr [rax+rax+00h]
0x180174d2f  mov     rcx, [rbp+5Fh]; this
0x180174d33  test    eax, eax
0x180174d35  js      short loc_180174D8A
0x180174d37  mov     rax, [rbp+57h+arg_18]
0x180174d3b  mov     [rbp+57h+arg_18], r14
0x180174d3f  mov     [rbx], rax
0x180174d42  lea     rcx, [rbp+57h+arg_18]; this
0x180174d46  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x180174d4b  nop
0x180174d4c  lea     rcx, [rbp+57h+ppv]
0x180174d50  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x180174d55  jmp     short loc_180174D5A
0x180174d57  mov     [rbx], r14
0x180174d5a  mov     rax, rbx
0x180174d5d  lea     r11, [rsp+0C0h+var_10]
0x180174d65  mov     rbx, [r11+20h]
0x180174d69  mov     rsi, [r11+28h]
0x180174d6d  movaps  xmm6, xmmword ptr [r11-10h]
0x180174d72  movaps  xmm7, xmmword ptr [r11-20h]
0x180174d77  movaps  xmm8, xmmword ptr [r11-30h]
0x180174d7c  movaps  xmm9, xmmword ptr [r11-40h]
0x180174d81  mov     rsp, r11
0x180174d84  pop     r14
0x180174d86  pop     rdi
0x180174d87  pop     rbp
0x180174d88  retn
0x180174d8a  mov     r9d, eax; char *
0x180174d8d  lea     r8, aShellSystemset_87; "shell\\systemsettingsthreshold\\handler"...
0x180174d94  mov     edx, 113h; void *
0x180174d99  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180174d9f  mov     r9d, eax; char *
0x180174da2  lea     r8, aShellSystemset_87; "shell\\systemsettingsthreshold\\handler"...
0x180174da9  mov     edx, 0D9h; void *
0x180174dae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180174db4  mov     r9d, eax; char *
0x180174db7  lea     r8, aShellSystemset_87; "shell\\systemsettingsthreshold\\handler"...
0x180174dbe  mov     edx, 0DDh; void *
0x180174dc3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180174dc9  mov     r9d, eax; char *
0x180174dcc  lea     r8, aShellSystemset_87; "shell\\systemsettingsthreshold\\handler"...
0x180174dd3  mov     edx, 0E6h; void *
0x180174dd8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180174dde  mov     r9d, eax; char *
0x180174de1  lea     r8, aShellSystemset_87; "shell\\systemsettingsthreshold\\handler"...
0x180174de8  mov     edx, 0EAh; void *
0x180174ded  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180174df3  mov     r9d, eax; char *
0x180174df6  lea     r8, aShellSystemset_87; "shell\\systemsettingsthreshold\\handler"...
0x180174dfd  mov     edx, 0EDh; void *
0x180174e02  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
