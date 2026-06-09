# CAccentAcrylicBlurBehind::GetLuminosityOpacityReference(double,Windows::Foundation::IReference<double> * *)

- ea: `0x18005c7fc`
- end: `0x18005cb5c`
- name: `?GetLuminosityOpacityReference@CAccentAcrylicBlurBehind@@AEAAJNPEAPEAU?$IReference@N@Foundation@Windows@@@Z`
- size: `864`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180094860`

## callees

- `0x1800028d4`
- `0x1800028f4`
- `0x18005c7fc`
- `0x180081a68`
- `0x180095130`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005c875`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005c875`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005c8d2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005c8d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005c85f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005c85f`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CAccentAcrylicBlurBehind::GetLuminosityOpacityReference(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v4; // rbx
  HRESULT v5; // eax
  unsigned int v6; // ebx
  int ActivationFactory; // eax
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rdi
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64, _QWORD); // rbx
  __int64 v14; // rdx
  int v15; // eax
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v17; // rcx
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v19)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v20)(_QWORD, GUID *, __int64 *); // rdi
  int v21; // eax
  __int64 v22; // rax
  __int64 (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v24; // rcx
  __int64 (__fastcall ***v25)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v27; // rcx
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v29; // rcx
  __int64 (__fastcall ***v30)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v33)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-60h] BYREF
  __int64 v34; // [rsp+28h] [rbp-58h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-50h] BYREF
  __int64 v36; // [rsp+38h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-40h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( !a3 )
    goto LABEL_4;
  *a3 = 0;
  v33 = 0;
  v4 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::UI::Composition::IExpCompositionProjectedShadow>>(&v33);
  string = 0;
  v5 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
LABEL_4:
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x466,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\accent.cpp",
      (const char *)0x80070057LL,
      (int)v33);
    return v6;
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, v4);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\accent.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v33);
    v26 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v33;
    if ( v33 )
    {
      v33 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v26)[2])(v26);
    }
    return v6;
  }
  v34 = 0;
  v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v33;
  v10 = **v33;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v34);
  v11 = v10(v9, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v34);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46F,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\accent.cpp",
      (const char *)(unsigned int)v11,
      (int)v33);
    v31 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v33;
    if ( v33 )
    {
      v33 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v32)[2])(v32);
    }
    return v6;
  }
  v35 = 0;
  v12 = v34;
  v13 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v34 + 120LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v35);
  v15 = v13(v12, v14, &v35);
  v6 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x472,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\accent.cpp",
      (const char *)(unsigned int)v15,
      (int)v33);
    v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
    if ( v35 )
    {
      v35 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v16)[2])(v16);
    }
    v17 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v33;
    if ( v33 )
    {
      v33 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v18)[2])(v18);
    }
    return v6;
  }
  v36 = 0;
  v19 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
  v20 = **v35;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v36);
  v21 = v20(v19, &GUID_2f2d6c29_5473_5f3e_92e7_96572bb990e2, &v36);
  v6 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x475,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\accent.cpp",
      (const char *)(unsigned int)v21,
      (int)v33);
    v27 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
    if ( v35 )
    {
      v35 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v28)[2])(v28);
    }
    v29 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v33;
    if ( v33 )
    {
      v33 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v30)[2])(v30);
    }
    return v6;
  }
  v22 = v36;
  v36 = 0;
  *a3 = v22;
  v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
  if ( v35 )
  {
    v35 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v23)[2])(v23);
  }
  v24 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v33;
  if ( v33 )
  {
    v33 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v25)[2])(v25);
  }
  return 0;
}

```

## disassembly

```asm
0x18005c7fc  mov     [rsp-18h+arg_0], rbx
0x18005c801  mov     [rsp-18h+arg_18], rsi
0x18005c806  push    rbp
0x18005c807  push    rdi
0x18005c808  push    r14
0x18005c80a  mov     rbp, rsp
0x18005c80d  sub     rsp, 80h
0x18005c814  movaps  [rsp+80h+var_10], xmm6
0x18005c819  mov     rax, cs:__security_cookie
0x18005c820  xor     rax, rsp
0x18005c823  mov     [rbp+var_20], rax
0x18005c827  mov     rsi, r8
0x18005c82a  movaps  xmm6, xmm1
0x18005c82d  xor     r14d, r14d
0x18005c830  test    r8, r8
0x18005c833  jz      short loc_18005C87C
0x18005c835  mov     [r8], r14
0x18005c838  mov     [rbp+var_60], r14
0x18005c83c  lea     rcx, [rbp+var_60]
0x18005c840  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIExpCompositionProjectedShadow@Composition@UI@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIExpCompositionProjectedShadow@Composition@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::UI::Composition::IExpCompositionProjectedShadow>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::IExpCompositionProjectedShadow>>)
0x18005c845  mov     rbx, rax
0x18005c848  mov     [rbp+string], r14
0x18005c84c  lea     r9, [rbp+string]; string
0x18005c850  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18005c854  lea     edx, [r14+20h]; length
0x18005c858  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18005c85f  call    cs:__imp_WindowsCreateStringReference
0x18005c865  test    eax, eax
0x18005c867  jns     short loc_18005C8C4
0x18005c869  xor     r9d, r9d; lpArguments
0x18005c86c  xor     r8d, r8d; nNumberOfArguments
0x18005c86f  lea     edx, [r14+1]; dwExceptionFlags
0x18005c873  mov     ecx, eax; dwExceptionCode
0x18005c875  call    cs:__imp_RaiseException
0x18005c87b  nop
0x18005c87c  mov     rcx, [rbp+18h]; this
0x18005c880  mov     ebx, 80070057h
0x18005c885  mov     r9d, ebx; char *
0x18005c888  lea     r8, aClientcoreWind_4; "clientcore\\windows\\dwm\\udwm\\accent."...
0x18005c88f  mov     edx, 466h; void *
0x18005c894  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c899  mov     eax, ebx
0x18005c89b  mov     rcx, [rbp+var_20]
0x18005c89f  xor     rcx, rsp; StackCookie
0x18005c8a2  call    __security_check_cookie
0x18005c8a7  lea     r11, [rsp+80h+var_s0]
0x18005c8af  mov     rbx, [r11+20h]
0x18005c8b3  mov     rsi, [r11+38h]
0x18005c8b7  movaps  xmm6, [rsp+80h+var_10]
0x18005c8bc  mov     rsp, r11
0x18005c8bf  pop     r14
0x18005c8c1  pop     rdi
0x18005c8c2  pop     rbp
0x18005c8c3  retn
0x18005c8c4  mov     r8, rbx
0x18005c8c7  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18005c8ce  mov     rcx, [rbp+string]
0x18005c8d2  call    cs:__imp_RoGetActivationFactory
0x18005c8d8  mov     ebx, eax
0x18005c8da  test    eax, eax
0x18005c8dc  js      loc_18005CA4C
0x18005c8e2  mov     [rbp+var_58], r14
0x18005c8e6  mov     rbx, [rbp+var_60]
0x18005c8ea  mov     rax, [rbx]
0x18005c8ed  mov     rdi, [rax]
0x18005c8f0  lea     rcx, [rbp+var_58]
0x18005c8f4  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005c8f9  lea     r8, [rbp+var_58]
0x18005c8fd  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18005c904  mov     rcx, rbx
0x18005c907  mov     rax, rdi
0x18005c90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c90f  mov     ebx, eax
0x18005c911  test    eax, eax
0x18005c913  js      loc_18005CB0A
0x18005c919  mov     [rbp+var_50], r14
0x18005c91d  mov     rdi, [rbp+var_58]
0x18005c921  mov     rax, [rdi]
0x18005c924  mov     rbx, [rax+78h]
0x18005c928  lea     rcx, [rbp+var_50]
0x18005c92c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005c931  lea     r8, [rbp+var_50]
0x18005c935  movaps  xmm1, xmm6
0x18005c938  mov     rcx, rdi
0x18005c93b  mov     rax, rbx
0x18005c93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c943  mov     ebx, eax
0x18005c945  test    eax, eax
0x18005c947  jns     short loc_18005C9B5
0x18005c949  mov     rcx, [rbp+18h]; this
0x18005c94d  mov     r9d, eax; char *
0x18005c950  lea     r8, aClientcoreWind_4; "clientcore\\windows\\dwm\\udwm\\accent."...
0x18005c957  mov     edx, 472h; void *
0x18005c95c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c961  nop
0x18005c962  mov     rcx, [rbp+var_50]
0x18005c966  test    rcx, rcx
0x18005c969  jz      short loc_18005C97C
0x18005c96b  mov     [rbp+var_50], r14
0x18005c96f  mov     rax, [rcx]
0x18005c972  mov     rax, [rax+10h]
0x18005c976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c97b  nop
0x18005c97c  mov     rcx, [rbp+var_58]
0x18005c980  test    rcx, rcx
0x18005c983  jz      short loc_18005C996
0x18005c985  mov     [rbp+var_58], r14
0x18005c989  mov     rax, [rcx]
0x18005c98c  mov     rax, [rax+10h]
0x18005c990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c995  nop
0x18005c996  mov     rcx, [rbp+var_60]
0x18005c99a  test    rcx, rcx
0x18005c99d  jz      short loc_18005C9B0
0x18005c99f  mov     [rbp+var_60], r14
0x18005c9a3  mov     rax, [rcx]
0x18005c9a6  mov     rax, [rax+10h]
0x18005c9aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c9af  nop
0x18005c9b0  jmp     loc_18005C899
0x18005c9b5  mov     [rbp+var_48], r14
0x18005c9b9  mov     rbx, [rbp+var_50]
0x18005c9bd  mov     rax, [rbx]
0x18005c9c0  mov     rdi, [rax]
0x18005c9c3  lea     rcx, [rbp+var_48]
0x18005c9c7  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005c9cc  lea     r8, [rbp+var_48]
0x18005c9d0  lea     rdx, _GUID_2f2d6c29_5473_5f3e_92e7_96572bb990e2
0x18005c9d7  mov     rcx, rbx
0x18005c9da  mov     rax, rdi
0x18005c9dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c9e2  mov     ebx, eax
0x18005c9e4  test    eax, eax
0x18005c9e6  js      loc_18005CA84
0x18005c9ec  mov     rax, [rbp+var_48]
0x18005c9f0  mov     [rbp+var_48], r14
0x18005c9f4  mov     [rsi], rax
0x18005c9f7  mov     rcx, [rbp+var_50]
0x18005c9fb  test    rcx, rcx
0x18005c9fe  jz      short loc_18005CA11
0x18005ca00  mov     [rbp+var_50], r14
0x18005ca04  mov     rax, [rcx]
0x18005ca07  mov     rax, [rax+10h]
0x18005ca0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca10  nop
0x18005ca11  mov     rcx, [rbp+var_58]
0x18005ca15  test    rcx, rcx
0x18005ca18  jz      short loc_18005CA2B
0x18005ca1a  mov     [rbp+var_58], r14
0x18005ca1e  mov     rax, [rcx]
0x18005ca21  mov     rax, [rax+10h]
0x18005ca25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca2a  nop
0x18005ca2b  mov     rcx, [rbp+var_60]
0x18005ca2f  test    rcx, rcx
0x18005ca32  jz      short loc_18005CA45
0x18005ca34  mov     [rbp+var_60], r14
0x18005ca38  mov     rax, [rcx]
0x18005ca3b  mov     rax, [rax+10h]
0x18005ca3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca44  nop
0x18005ca45  xor     eax, eax
0x18005ca47  jmp     loc_18005C89B
0x18005ca4c  mov     rcx, [rbp+18h]; this
0x18005ca50  mov     r9d, ebx; char *
0x18005ca53  lea     r8, aClientcoreWind_4; "clientcore\\windows\\dwm\\udwm\\accent."...
0x18005ca5a  mov     edx, 46Ch; void *
0x18005ca5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ca64  nop
0x18005ca65  mov     rcx, [rbp+var_60]
0x18005ca69  test    rcx, rcx
0x18005ca6c  jz      short loc_18005CA7F
0x18005ca6e  mov     [rbp+var_60], r14
0x18005ca72  mov     rax, [rcx]
0x18005ca75  mov     rax, [rax+10h]
0x18005ca79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca7e  nop
0x18005ca7f  jmp     loc_18005C899
0x18005ca84  mov     rcx, [rbp+18h]; this
0x18005ca88  mov     r9d, ebx; char *
0x18005ca8b  lea     r8, aClientcoreWind_4; "clientcore\\windows\\dwm\\udwm\\accent."...
0x18005ca92  mov     edx, 475h; void *
0x18005ca97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ca9c  nop
0x18005ca9d  mov     rcx, [rbp+var_48]
0x18005caa1  test    rcx, rcx
0x18005caa4  jz      short loc_18005CAB7
0x18005caa6  mov     [rbp+var_48], r14
0x18005caaa  mov     rax, [rcx]
0x18005caad  mov     rax, [rax+10h]
0x18005cab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cab6  nop
0x18005cab7  mov     rcx, [rbp+var_50]
0x18005cabb  test    rcx, rcx
0x18005cabe  jz      short loc_18005CAD1
0x18005cac0  mov     [rbp+var_50], r14
0x18005cac4  mov     rax, [rcx]
0x18005cac7  mov     rax, [rax+10h]
0x18005cacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cad0  nop
0x18005cad1  mov     rcx, [rbp+var_58]
0x18005cad5  test    rcx, rcx
0x18005cad8  jz      short loc_18005CAEB
0x18005cada  mov     [rbp+var_58], r14
0x18005cade  mov     rax, [rcx]
0x18005cae1  mov     rax, [rax+10h]
0x18005cae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005caea  nop
0x18005caeb  mov     rcx, [rbp+var_60]
0x18005caef  test    rcx, rcx
0x18005caf2  jz      short loc_18005CB05
0x18005caf4  mov     [rbp+var_60], r14
0x18005caf8  mov     rax, [rcx]
0x18005cafb  mov     rax, [rax+10h]
0x18005caff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb04  nop
0x18005cb05  jmp     loc_18005C899
0x18005cb0a  mov     rcx, [rbp+18h]; this
0x18005cb0e  mov     r9d, ebx; char *
0x18005cb11  lea     r8, aClientcoreWind_4; "clientcore\\windows\\dwm\\udwm\\accent."...
0x18005cb18  mov     edx, 46Fh; void *
0x18005cb1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cb22  nop
0x18005cb23  mov     rcx, [rbp+var_58]
0x18005cb27  test    rcx, rcx
0x18005cb2a  jz      short loc_18005CB3D
0x18005cb2c  mov     [rbp+var_58], r14
0x18005cb30  mov     rax, [rcx]
0x18005cb33  mov     rax, [rax+10h]
0x18005cb37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb3c  nop
0x18005cb3d  mov     rcx, [rbp+var_60]
0x18005cb41  test    rcx, rcx
0x18005cb44  jz      short loc_18005CB57
0x18005cb46  mov     [rbp+var_60], r14
0x18005cb4a  mov     rax, [rcx]
0x18005cb4d  mov     rax, [rax+10h]
0x18005cb51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb56  nop
0x18005cb57  jmp     loc_18005C899
```
