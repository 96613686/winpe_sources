# Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(HSTRING__ *,IInspectable * *),HSTRING__ *)

- ea: `0x180007b98`
- end: `0x180007ef6`
- name: `??$SetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJ0PEAPEAUIInspectable@@@Z0@Z`
- size: `862`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000881c`

## callees

- `0x180001e20`
- `0x180005524`
- `0x180007b98`
- `0x180009bd4`
- `0x18000d4f0`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007be3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007be3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180007c00`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180007c00`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<HSTRING__ *>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int ActivationFactory; // eax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int v14; // eax
  __int64 (__fastcall ***v15)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 (__fastcall ***v19)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 (__fastcall ***v22)(_QWORD, GUID *, __int64 *); // r9
  __int64 v23; // rdi
  int v24; // eax
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 (__fastcall ***v28)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v33; // rcx
  int v34; // [rsp+20h] [rbp-60h]
  _BYTE v35[8]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v36; // [rsp+38h] [rbp-48h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-40h] BYREF
  __int64 v38; // [rsp+48h] [rbp-38h] BYREF
  __int64 v39; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  HSTRING string; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v36 = 0;
  string = 0;
  v7 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
    JUMPOUT(0x180007EF5LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v36);
  v11 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecore\\internal\\shell\\inc\\PropertySetHelpers.h",
      (const char *)(unsigned int)ActivationFactory,
      v34);
    v12 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v11;
  }
  v37 = 0;
  v14 =  Windows::Foundation::IPropertyValueStatics::`vcall'{144,{flat}}(v36, a4, &v37);
  v11 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\internal\\shell\\inc\\PropertySetHelpers.h",
      (const char *)(unsigned int)v14,
      v34);
    v15 = v37;
    if ( v37 )
    {
      v37 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v15)[2])(v15);
    }
    v16 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v11;
  }
  v39 = 0;
  v17 = (**v37)(v37, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v39);
  v11 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecore\\internal\\shell\\inc\\PropertySetHelpers.h",
      (const char *)(unsigned int)v17,
      v34);
    v18 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v37;
    if ( v37 )
    {
      v37 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v19)[2])(v19);
    }
    v20 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return v11;
  }
  v21 = 0;
  v38 = 0;
  v22 = *a1;
  if ( !*a1 )
  {
    v11 = -2147467261;
    goto LABEL_24;
  }
  v23 = v39;
  v24 = (**v22)(v22, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v38);
  v11 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecore\\internal\\shell\\inc\\PropertySetHelpers.h",
      (const char *)(unsigned int)v24,
      v34);
    v21 = v38;
LABEL_24:
    if ( v21 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    if ( (v11 & 0x80000000) != 0 )
    {
LABEL_31:
      v27 = v39;
      if ( v39 )
      {
        v39 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
      v28 = v37;
      if ( v37 )
      {
        v37 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v28)[2])(v28);
      }
      v29 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      return v11;
    }
    goto LABEL_40;
  }
  v35[0] = 0;
  v25 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _BYTE *))(*(_QWORD *)v38 + 80LL))(v38, a2, v23, v35);
  v11 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecore\\internal\\shell\\inc\\PropertySetHelpers.h",
      (const char *)(unsigned int)v25,
      v34);
    v26 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    goto LABEL_31;
  }
  v30 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
LABEL_40:
  v31 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  v32 = v37;
  if ( v37 )
  {
    v37 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v32)[2])(v32);
  }
  v33 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  return 0;
}

```

## disassembly

```asm
0x180007b98  mov     [rsp-28h+arg_10], rbx
0x180007b9d  push    rbp
0x180007b9e  push    rsi
0x180007b9f  push    rdi
0x180007ba0  push    r14
0x180007ba2  push    r15
0x180007ba4  mov     rbp, rsp
0x180007ba7  sub     rsp, 80h
0x180007bae  mov     rax, cs:__security_cookie
0x180007bb5  xor     rax, rsp
0x180007bb8  mov     [rbp+var_8], rax
0x180007bbc  mov     rsi, r9
0x180007bbf  mov     r14, rdx
0x180007bc2  mov     rdi, rcx
0x180007bc5  xor     r15d, r15d
0x180007bc8  mov     [rbp+var_48], r15
0x180007bcc  mov     [rbp+string], r15
0x180007bd0  lea     r9, [rbp+string]; string
0x180007bd4  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180007bd8  lea     edx, [r15+20h]; length
0x180007bdc  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180007be3  call    cs:__imp_WindowsCreateStringReference
0x180007be9  test    eax, eax
0x180007beb  js      loc_180007EEE
0x180007bf1  lea     r8, [rbp+var_48]
0x180007bf5  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x180007bfc  mov     rcx, [rbp+string]
0x180007c00  call    cs:__imp_RoGetActivationFactory
0x180007c06  mov     ebx, eax
0x180007c08  test    eax, eax
0x180007c0a  jns     short loc_180007C45
0x180007c0c  mov     rcx, [rbp+28h]; this
0x180007c10  mov     r9d, eax; char *
0x180007c13  lea     r8, aOnecoreInterna_0; "onecore\\internal\\shell\\inc\\Property"...
0x180007c1a  lea     edx, [r15+50h]; void *
0x180007c1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c23  nop
0x180007c24  mov     rcx, [rbp+var_48]
0x180007c28  test    rcx, rcx
0x180007c2b  jz      short loc_180007C3E
0x180007c2d  mov     [rbp+var_48], r15
0x180007c31  mov     rax, [rcx]
0x180007c34  mov     rax, [rax+10h]
0x180007c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c3d  nop
0x180007c3e  mov     eax, ebx
0x180007c40  jmp     loc_180007ECB
0x180007c45  mov     [rbp+var_40], r15
0x180007c49  lea     r8, [rbp+var_40]
0x180007c4d  mov     rdx, rsi
0x180007c50  mov     rcx, [rbp+var_48]
0x180007c54  call    ??_9IPropertyValueStatics@Foundation@Windows@@$BJA@AA; [thunk]: Windows::Foundation::IPropertyValueStatics::`vcall'{144,{flat}}
0x180007c59  mov     ebx, eax
0x180007c5b  test    eax, eax
0x180007c5d  jns     short loc_180007CAE
0x180007c5f  mov     rcx, [rbp+28h]; this
0x180007c63  mov     r9d, eax; char *
0x180007c66  lea     r8, aOnecoreInterna_0; "onecore\\internal\\shell\\inc\\Property"...
0x180007c6d  mov     edx, 52h ; 'R'; void *
0x180007c72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c77  nop
0x180007c78  mov     rcx, [rbp+var_40]
0x180007c7c  test    rcx, rcx
0x180007c7f  jz      short loc_180007C92
0x180007c81  mov     [rbp+var_40], r15
0x180007c85  mov     rax, [rcx]
0x180007c88  mov     rax, [rax+10h]
0x180007c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c91  nop
0x180007c92  mov     rcx, [rbp+var_48]
0x180007c96  test    rcx, rcx
0x180007c99  jz      short loc_180007CAC
0x180007c9b  mov     [rbp+var_48], r15
0x180007c9f  mov     rax, [rcx]
0x180007ca2  mov     rax, [rax+10h]
0x180007ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cab  nop
0x180007cac  jmp     short loc_180007C3E
0x180007cae  mov     [rbp+var_30], r15
0x180007cb2  mov     rcx, [rbp+var_40]
0x180007cb6  mov     rax, [rcx]
0x180007cb9  lea     r8, [rbp+var_30]
0x180007cbd  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180007cc4  mov     rax, [rax]
0x180007cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ccc  mov     ebx, eax
0x180007cce  test    eax, eax
0x180007cd0  jns     short loc_180007D3E
0x180007cd2  mov     rcx, [rbp+28h]; this
0x180007cd6  mov     r9d, eax; char *
0x180007cd9  lea     r8, aOnecoreInterna_0; "onecore\\internal\\shell\\inc\\Property"...
0x180007ce0  mov     edx, 54h ; 'T'; void *
0x180007ce5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007cea  nop
0x180007ceb  mov     rcx, [rbp+var_30]
0x180007cef  test    rcx, rcx
0x180007cf2  jz      short loc_180007D05
0x180007cf4  mov     [rbp+var_30], r15
0x180007cf8  mov     rax, [rcx]
0x180007cfb  mov     rax, [rax+10h]
0x180007cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d04  nop
0x180007d05  mov     rcx, [rbp+var_40]
0x180007d09  test    rcx, rcx
0x180007d0c  jz      short loc_180007D1F
0x180007d0e  mov     [rbp+var_40], r15
0x180007d12  mov     rax, [rcx]
0x180007d15  mov     rax, [rax+10h]
0x180007d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d1e  nop
0x180007d1f  mov     rcx, [rbp+var_48]
0x180007d23  test    rcx, rcx
0x180007d26  jz      short loc_180007D39
0x180007d28  mov     [rbp+var_48], r15
0x180007d2c  mov     rax, [rcx]
0x180007d2f  mov     rax, [rax+10h]
0x180007d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d38  nop
0x180007d39  jmp     loc_180007C3E
0x180007d3e  mov     rcx, r15
0x180007d41  mov     [rbp+var_38], rcx
0x180007d45  mov     r9, [rdi]
0x180007d48  test    r9, r9
0x180007d4b  jnz     short loc_180007D54
0x180007d4d  mov     ebx, 80004003h
0x180007d52  jmp     short loc_180007D93
0x180007d54  mov     rdi, [rbp+var_30]
0x180007d58  mov     rax, [r9]
0x180007d5b  lea     r8, [rbp+var_38]
0x180007d5f  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180007d66  mov     rcx, r9
0x180007d69  mov     rax, [rax]
0x180007d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d71  mov     ebx, eax
0x180007d73  test    eax, eax
0x180007d75  jns     short loc_180007DB3
0x180007d77  mov     rcx, [rbp+28h]; this
0x180007d7b  mov     r9d, eax; char *
0x180007d7e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\shell\\inc\\Property"...
0x180007d85  mov     edx, 1Bh; void *
0x180007d8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007d8f  mov     rcx, [rbp+var_38]
0x180007d93  test    rcx, rcx
0x180007d96  jz      short loc_180007DA9
0x180007d98  mov     [rbp+var_38], r15
0x180007d9c  mov     rax, [rcx]
0x180007d9f  mov     rax, [rax+10h]
0x180007da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007da8  nop
0x180007da9  test    ebx, ebx
0x180007dab  jns     loc_180007E7B
0x180007db1  jmp     short loc_180007E0E
0x180007db3  mov     [rbp+var_50], r15b
0x180007db7  mov     rcx, [rbp+var_38]
0x180007dbb  mov     rax, [rcx]
0x180007dbe  lea     r9, [rbp+var_50]
0x180007dc2  mov     r8, rdi
0x180007dc5  mov     rdx, r14
0x180007dc8  mov     rax, [rax+50h]
0x180007dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dd1  mov     ebx, eax
0x180007dd3  test    eax, eax
0x180007dd5  jns     loc_180007E61
0x180007ddb  mov     rcx, [rbp+28h]; this
0x180007ddf  mov     r9d, eax; char *
0x180007de2  lea     r8, aOnecoreInterna_0; "onecore\\internal\\shell\\inc\\Property"...
0x180007de9  mov     edx, 48h ; 'H'; void *
0x180007dee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007df3  nop
0x180007df4  mov     rcx, [rbp+var_38]
0x180007df8  test    rcx, rcx
0x180007dfb  jz      short loc_180007E0E
0x180007dfd  mov     [rbp+var_38], r15
0x180007e01  mov     rax, [rcx]
0x180007e04  mov     rax, [rax+10h]
0x180007e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e0d  nop
0x180007e0e  mov     rcx, [rbp+var_30]
0x180007e12  test    rcx, rcx
0x180007e15  jz      short loc_180007E28
0x180007e17  mov     [rbp+var_30], r15
0x180007e1b  mov     rax, [rcx]
0x180007e1e  mov     rax, [rax+10h]
0x180007e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e27  nop
0x180007e28  mov     rcx, [rbp+var_40]
0x180007e2c  test    rcx, rcx
0x180007e2f  jz      short loc_180007E42
0x180007e31  mov     [rbp+var_40], r15
0x180007e35  mov     rax, [rcx]
0x180007e38  mov     rax, [rax+10h]
0x180007e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e41  nop
0x180007e42  mov     rcx, [rbp+var_48]
0x180007e46  test    rcx, rcx
0x180007e49  jz      short loc_180007E5C
0x180007e4b  mov     [rbp+var_48], r15
0x180007e4f  mov     rdx, [rcx]
0x180007e52  mov     rax, [rdx+10h]
0x180007e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e5b  nop
0x180007e5c  jmp     loc_180007C3E
0x180007e61  mov     rcx, [rbp+var_38]
0x180007e65  test    rcx, rcx
0x180007e68  jz      short loc_180007E7B
0x180007e6a  mov     [rbp+var_38], r15
0x180007e6e  mov     rax, [rcx]
0x180007e71  mov     rax, [rax+10h]
0x180007e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e7a  nop
0x180007e7b  mov     rcx, [rbp+var_30]
0x180007e7f  test    rcx, rcx
0x180007e82  jz      short loc_180007E95
0x180007e84  mov     [rbp+var_30], r15
0x180007e88  mov     rax, [rcx]
0x180007e8b  mov     rax, [rax+10h]
0x180007e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e94  nop
0x180007e95  mov     rcx, [rbp+var_40]
0x180007e99  test    rcx, rcx
0x180007e9c  jz      short loc_180007EAF
0x180007e9e  mov     [rbp+var_40], r15
0x180007ea2  mov     rax, [rcx]
0x180007ea5  mov     rax, [rax+10h]
0x180007ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eae  nop
0x180007eaf  mov     rcx, [rbp+var_48]
0x180007eb3  test    rcx, rcx
0x180007eb6  jz      short loc_180007EC9
0x180007eb8  mov     [rbp+var_48], r15
0x180007ebc  mov     rax, [rcx]
0x180007ebf  mov     rax, [rax+10h]
0x180007ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ec8  nop
0x180007ec9  xor     eax, eax
0x180007ecb  mov     rcx, [rbp+var_8]
0x180007ecf  xor     rcx, rsp; StackCookie
0x180007ed2  call    __security_check_cookie
0x180007ed7  mov     rbx, [rsp+80h+arg_10]
0x180007edf  add     rsp, 80h
0x180007ee6  pop     r15
0x180007ee8  pop     r14
0x180007eea  pop     rdi
0x180007eeb  pop     rsi
0x180007eec  pop     rbp
0x180007eed  retn
0x180007eee  mov     ecx, eax; this
0x180007ef0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
