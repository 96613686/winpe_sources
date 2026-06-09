# ParseProperties(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::shared_ptr<SCDProvider>,std::vector<std::shared_ptr<SCDSetting>,std::allocator<std::shared_ptr<SCDSetting>>> &)

- ea: `0x1800e9c4c`
- end: `0x1800ea031`
- name: `?ParseProperties@@YAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VSCDProvider@@@5@AEAV?$vector@V?$shared_ptr@VSCDSetting@@@std@@V?$allocator@V?$shared_ptr@VSCDSetting@@@std@@@2@@5@@Z`
- size: `997`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ea7ac`
- `0x1800ec038`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180019208`
- `0x180019d38`
- `0x1800370d4`
- `0x18004abf8`
- `0x1800e913c`
- `0x1800e9490`
- `0x1800e9610`
- `0x1800e9c4c`
- `0x1800ea7ac`
- `0x1800eef20`
- `0x180139010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e9e3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e9e3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e9dcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e9f13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e9fad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e9dcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e9f13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e9fad`

## string_xrefs

- `0x1800e9cc8`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`
- `0x1800e9d3b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`
- `0x1800e9f47`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`
- `0x1800e9f66`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`
- `0x1800e9f96`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`
- `0x1800e9fc1`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ParseProperties(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64 *),
        HSTRING a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rbx
  int v10; // eax
  int v11; // ebx
  std::_Ref_count_base *v12; // rcx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64 *); // rbx
  int v25; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v27; // r8
  _QWORD *v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  std::_Ref_count_base *v31; // rcx
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v34; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v35; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v36; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v40[8]; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v41; // [rsp+88h] [rbp-78h]
  char *v42[14]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v38[1] = (__int64)a1;
  v38[2] = (__int64)a3;
  v35 = 0;
  v8 = *a1;
  v9 = ***a1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  v10 = v9(v8, &GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099, &v35);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5AE,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
      (const char *)(unsigned int)v10,
      v32);
LABEL_3:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
    v12 = (std::_Ref_count_base *)a3[1];
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
    return (unsigned int)v11;
  }
  v34 = 0;
  v14 = v35;
  v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  v16 = v15(v14, &v34);
  v11 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B1,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
      (const char *)(unsigned int)v16,
      v32);
LABEL_8:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    goto LABEL_3;
  }
  LOBYTE(v32) = 1;
  while ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v34 + 56LL))(v34, &v32) >= 0 && (_BYTE)v32 )
  {
    v36 = 0;
    v17 = v34;
    v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    v19 = v18(v17, &v36);
    v11 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
        (const char *)(unsigned int)v19,
        v32);
      goto LABEL_32;
    }
    string = 0;
    v20 = v36;
    v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v22 = v21(v20, &string);
    v11 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5BA,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
        (const char *)(unsigned int)v22,
        v32);
      goto LABEL_30;
    }
    v37 = 0;
    v38[0] = 0;
    v23 = v36;
    v24 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    v25 = v24(v23, &v37);
    v11 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5BE,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
        (const char *)(unsigned int)v25,
        v32);
      goto LABEL_28;
    }
    SCDSetting::SCDSetting((SCDSetting *)v42);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v27 = -1;
    do
      ++v27;
    while ( StringRawBuffer[v27] );
    std::wstring::_Assign<unsigned short>(v42, StringRawBuffer, (char *)v27);
    v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 96LL))(v37, v38);
    if ( v11 < 0 )
    {
      v30 = 1474;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
        (const char *)(unsigned int)v11,
        v32);
      SCDSetting::~SCDSetting((SCDSetting *)v42);
LABEL_28:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v38);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
LABEL_30:
      WindowsDeleteString(string);
      string = 0;
LABEL_32:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
      goto LABEL_8;
    }
    v28 = std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(&v39, a3);
    v11 = ParseScdProperty(v38, a2, v28, (__int64)v42);
    if ( v11 < 0 )
    {
      v30 = 1475;
      goto LABEL_26;
    }
    v29 = std::make_shared<SCDSetting,SCDSetting &>(v40, v42);
    std::vector<std::shared_ptr<SCDSetting>>::push_back(a4, v29);
    if ( v41 )
      std::_Ref_count_base::_Decref(v41);
    v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v34 + 64LL))(v34, &v32);
    if ( v11 < 0 )
    {
      v30 = 1478;
      goto LABEL_26;
    }
    SCDSetting::~SCDSetting((SCDSetting *)v42);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v38);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
  v31 = (std::_Ref_count_base *)a3[1];
  if ( v31 )
    std::_Ref_count_base::_Decref(v31);
  return 0;
}

```

## disassembly

```asm
0x1800e9c4c  push    rbp
0x1800e9c4e  push    rbx
0x1800e9c4f  push    rsi
0x1800e9c50  push    rdi
0x1800e9c51  push    r12
0x1800e9c53  push    r13
0x1800e9c55  push    r14
0x1800e9c57  push    r15
0x1800e9c59  lea     rbp, [rsp-18h]
0x1800e9c5e  sub     rsp, 118h
0x1800e9c65  mov     rax, cs:__security_cookie
0x1800e9c6c  xor     rax, rsp
0x1800e9c6f  mov     [rbp+50h+var_50], rax
0x1800e9c73  mov     r15, r9
0x1800e9c76  mov     rsi, r8
0x1800e9c79  mov     r12, rdx
0x1800e9c7c  mov     r14, rcx
0x1800e9c7f  mov     [rsp+150h+var_F8], rcx
0x1800e9c84  mov     [rsp+150h+var_F0], r8
0x1800e9c89  xor     r13d, r13d
0x1800e9c8c  mov     [rsp+150h+var_118], r13
0x1800e9c91  mov     rdi, [rcx]
0x1800e9c94  mov     rax, [rdi]
0x1800e9c97  mov     rbx, [rax]
0x1800e9c9a  lea     rcx, [rsp+150h+var_118]
0x1800e9c9f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e9ca4  lea     r8, [rsp+150h+var_118]
0x1800e9ca9  lea     rdx, _GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099
0x1800e9cb0  mov     rcx, rdi
0x1800e9cb3  mov     rax, rbx
0x1800e9cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9cbb  mov     ebx, eax
0x1800e9cbd  test    eax, eax
0x1800e9cbf  jns     short loc_1800E9D03
0x1800e9cc1  mov     rcx, [rbp+58h]; this
0x1800e9cc5  mov     r9d, eax; char *
0x1800e9cc8  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e9ccf  mov     edx, 5AEh; void *
0x1800e9cd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e9cd9  nop
0x1800e9cda  lea     rcx, [rsp+150h+var_118]
0x1800e9cdf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e9ce4  nop
0x1800e9ce5  mov     rcx, r14
0x1800e9ce8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e9ced  nop
0x1800e9cee  mov     rcx, [rsi+8]; this
0x1800e9cf2  test    rcx, rcx
0x1800e9cf5  jz      short loc_1800E9CFC
0x1800e9cf7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800e9cfc  mov     eax, ebx
0x1800e9cfe  jmp     loc_1800EA011
0x1800e9d03  mov     [rsp+150h+var_120], r13
0x1800e9d08  mov     rdi, [rsp+150h+var_118]
0x1800e9d0d  mov     rax, [rdi]
0x1800e9d10  mov     rbx, [rax+30h]
0x1800e9d14  lea     rcx, [rsp+150h+var_120]
0x1800e9d19  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e9d1e  lea     rdx, [rsp+150h+var_120]
0x1800e9d23  mov     rcx, rdi
0x1800e9d26  mov     rax, rbx
0x1800e9d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9d2e  mov     ebx, eax
0x1800e9d30  test    eax, eax
0x1800e9d32  jns     short loc_1800E9D59
0x1800e9d34  mov     rcx, [rbp+58h]; this
0x1800e9d38  mov     r9d, eax; char *
0x1800e9d3b  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e9d42  mov     edx, 5B1h; void *
0x1800e9d47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e9d4c  nop
0x1800e9d4d  lea     rcx, [rsp+150h+var_120]
0x1800e9d52  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e9d57  jmp     short loc_1800E9CDA
0x1800e9d59  mov     byte ptr [rsp+150h+var_130], 1; int
0x1800e9d5e  mov     rcx, [rsp+150h+var_120]
0x1800e9d63  mov     rax, [rcx]
0x1800e9d66  lea     rdx, [rsp+150h+var_130]
0x1800e9d6b  mov     rax, [rax+38h]
0x1800e9d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9d74  test    eax, eax
0x1800e9d76  js      loc_1800E9FE2
0x1800e9d7c  cmp     byte ptr [rsp+150h+var_130], r13b
0x1800e9d81  jz      loc_1800E9FE2
0x1800e9d87  mov     [rsp+150h+var_110], r13
0x1800e9d8c  mov     rdi, [rsp+150h+var_120]
0x1800e9d91  mov     rax, [rdi]
0x1800e9d94  mov     rbx, [rax+30h]
0x1800e9d98  lea     rcx, [rsp+150h+var_110]
0x1800e9d9d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e9da2  lea     rdx, [rsp+150h+var_110]
0x1800e9da7  mov     rcx, rdi
0x1800e9daa  mov     rax, rbx
0x1800e9dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9db2  mov     ebx, eax
0x1800e9db4  test    eax, eax
0x1800e9db6  js      loc_1800E9FBA
0x1800e9dbc  mov     [rsp+150h+string], r13
0x1800e9dc1  mov     rdi, [rsp+150h+var_110]
0x1800e9dc6  mov     rax, [rdi]
0x1800e9dc9  mov     rbx, [rax+30h]
0x1800e9dcd  xor     ecx, ecx; string
0x1800e9dcf  call    cs:__imp_WindowsDeleteString
0x1800e9dd5  mov     [rsp+150h+string], r13
0x1800e9dda  lea     rdx, [rsp+150h+string]
0x1800e9ddf  mov     rcx, rdi
0x1800e9de2  mov     rax, rbx
0x1800e9de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9dea  mov     ebx, eax
0x1800e9dec  test    eax, eax
0x1800e9dee  js      loc_1800E9F8F
0x1800e9df4  mov     [rsp+150h+var_108], r13
0x1800e9df9  mov     [rsp+150h+var_100], r13
0x1800e9dfe  mov     rdi, [rsp+150h+var_110]
0x1800e9e03  mov     rax, [rdi]
0x1800e9e06  mov     rbx, [rax+38h]
0x1800e9e0a  lea     rcx, [rsp+150h+var_108]
0x1800e9e0f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e9e14  lea     rdx, [rsp+150h+var_108]
0x1800e9e19  mov     rcx, rdi
0x1800e9e1c  mov     rax, rbx
0x1800e9e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9e24  mov     ebx, eax
0x1800e9e26  test    eax, eax
0x1800e9e28  js      loc_1800E9F5F
0x1800e9e2e  lea     rcx, [rbp+50h+var_C0]; this
0x1800e9e32  call    ??0SCDSetting@@QEAA@XZ; SCDSetting::SCDSetting(void)
0x1800e9e37  nop
0x1800e9e38  xor     edx, edx; length
0x1800e9e3a  mov     rcx, [rsp+150h+string]; string
0x1800e9e3f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e9e45  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800e9e49  inc     r8
0x1800e9e4c  cmp     [rax+r8*2], r13w
0x1800e9e51  jnz     short loc_1800E9E49
0x1800e9e53  mov     rdx, rax
0x1800e9e56  lea     rcx, [rbp+50h+var_C0]
0x1800e9e5a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800e9e5f  mov     rcx, [rsp+150h+var_108]
0x1800e9e64  mov     rax, [rcx]
0x1800e9e67  lea     rdx, [rsp+150h+var_100]
0x1800e9e6c  mov     rax, [rax+60h]
0x1800e9e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9e75  mov     ebx, eax
0x1800e9e77  test    eax, eax
0x1800e9e79  js      loc_1800E9F3B
0x1800e9e7f  mov     rdx, rsi
0x1800e9e82  lea     rcx, [rsp+150h+var_E0]
0x1800e9e87  call    ??0?$shared_ptr@VSCDSetting@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(std::shared_ptr<SCDSetting> const &)
0x1800e9e8c  lea     r9, [rbp+50h+var_C0]
0x1800e9e90  mov     r8, rax
0x1800e9e93  mov     rdx, r12
0x1800e9e96  lea     rcx, [rsp+150h+var_100]
0x1800e9e9b  call    ?ParseScdProperty@@YAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VSCDProvider@@@5@AEAVSCDSetting@@@Z; ParseScdProperty(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,std::wstring &,std::shared_ptr<SCDProvider>,SCDSetting &)
0x1800e9ea0  mov     ebx, eax
0x1800e9ea2  test    eax, eax
0x1800e9ea4  js      loc_1800E9F34
0x1800e9eaa  lea     rdx, [rbp+50h+var_C0]
0x1800e9eae  lea     rcx, [rbp+50h+var_D0]
0x1800e9eb2  call    ??$make_shared@VSCDSetting@@AEAV1@@std@@YA?AV?$shared_ptr@VSCDSetting@@@0@AEAVSCDSetting@@@Z; std::make_shared<SCDSetting,SCDSetting &>(SCDSetting &)
0x1800e9eb7  nop
0x1800e9eb8  mov     rdx, rax
0x1800e9ebb  mov     rcx, r15
0x1800e9ebe  call    ?push_back@?$vector@V?$shared_ptr@VSCDSetting@@@std@@V?$allocator@V?$shared_ptr@VSCDSetting@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VSCDSetting@@@2@@Z; std::vector<std::shared_ptr<SCDSetting>>::push_back(std::shared_ptr<SCDSetting> &&)
0x1800e9ec3  nop
0x1800e9ec4  mov     rcx, [rbp+50h+var_C8]; this
0x1800e9ec8  test    rcx, rcx
0x1800e9ecb  jz      short loc_1800E9ED2
0x1800e9ecd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800e9ed2  mov     rcx, [rsp+150h+var_120]
0x1800e9ed7  mov     rax, [rcx]
0x1800e9eda  lea     rdx, [rsp+150h+var_130]
0x1800e9edf  mov     rax, [rax+40h]
0x1800e9ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9ee8  mov     ebx, eax
0x1800e9eea  test    eax, eax
0x1800e9eec  js      short loc_1800E9F2D
0x1800e9eee  lea     rcx, [rbp+50h+var_C0]; this
0x1800e9ef2  call    ??1SCDSetting@@QEAA@XZ; SCDSetting::~SCDSetting(void)
0x1800e9ef7  nop
0x1800e9ef8  lea     rcx, [rsp+150h+var_100]
0x1800e9efd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e9f02  nop
0x1800e9f03  lea     rcx, [rsp+150h+var_108]
0x1800e9f08  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e9f0d  nop
0x1800e9f0e  mov     rcx, [rsp+150h+string]; string
0x1800e9f13  call    cs:__imp_WindowsDeleteString
0x1800e9f19  mov     [rsp+150h+string], r13
0x1800e9f1e  lea     rcx, [rsp+150h+var_110]
0x1800e9f23  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e9f28  jmp     loc_1800E9D5E
0x1800e9f2d  mov     edx, 5C6h
0x1800e9f32  jmp     short loc_1800E9F40
0x1800e9f34  mov     edx, 5C3h
0x1800e9f39  jmp     short loc_1800E9F40
0x1800e9f3b  mov     edx, 5C2h; void *
0x1800e9f40  mov     rcx, [rbp+58h]; this
0x1800e9f44  mov     r9d, ebx; char *
0x1800e9f47  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e9f4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e9f53  nop
0x1800e9f54  lea     rcx, [rbp+50h+var_C0]; this
0x1800e9f58  call    ??1SCDSetting@@QEAA@XZ; SCDSetting::~SCDSetting(void)
0x1800e9f5d  jmp     short loc_1800E9F78
0x1800e9f5f  mov     rcx, [rbp+58h]; this
0x1800e9f63  mov     r9d, ebx; char *
0x1800e9f66  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e9f6d  mov     edx, 5BEh; void *
0x1800e9f72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e9f77  nop
0x1800e9f78  lea     rcx, [rsp+150h+var_100]
0x1800e9f7d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e9f82  nop
0x1800e9f83  lea     rcx, [rsp+150h+var_108]
0x1800e9f88  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e9f8d  jmp     short loc_1800E9FA8
0x1800e9f8f  mov     rcx, [rbp+58h]; this
0x1800e9f93  mov     r9d, ebx; char *
0x1800e9f96  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e9f9d  mov     edx, 5BAh; void *
0x1800e9fa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e9fa7  nop
0x1800e9fa8  mov     rcx, [rsp+150h+string]; string
0x1800e9fad  call    cs:__imp_WindowsDeleteString
0x1800e9fb3  mov     [rsp+150h+string], r13
0x1800e9fb8  jmp     short loc_1800E9FD3
0x1800e9fba  mov     rcx, [rbp+58h]; this
0x1800e9fbe  mov     r9d, ebx; char *
0x1800e9fc1  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e9fc8  mov     edx, 5B7h; void *
0x1800e9fcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e9fd2  nop
0x1800e9fd3  lea     rcx, [rsp+150h+var_110]
0x1800e9fd8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e9fdd  jmp     loc_1800E9D4D
0x1800e9fe2  lea     rcx, [rsp+150h+var_120]
0x1800e9fe7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e9fec  nop
0x1800e9fed  lea     rcx, [rsp+150h+var_118]
0x1800e9ff2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e9ff7  nop
0x1800e9ff8  mov     rcx, r14
0x1800e9ffb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ea000  nop
0x1800ea001  mov     rcx, [rsi+8]; this
0x1800ea005  test    rcx, rcx
0x1800ea008  jz      short loc_1800EA00F
0x1800ea00a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ea00f  xor     eax, eax
0x1800ea011  mov     rcx, [rbp+50h+var_50]
0x1800ea015  xor     rcx, rsp; StackCookie
0x1800ea018  call    __security_check_cookie
0x1800ea01d  add     rsp, 118h
0x1800ea024  pop     r15
0x1800ea026  pop     r14
0x1800ea028  pop     r13
0x1800ea02a  pop     r12
0x1800ea02c  pop     rdi
0x1800ea02d  pop     rsi
0x1800ea02e  pop     rbx
0x1800ea02f  pop     rbp
0x1800ea030  retn
```
