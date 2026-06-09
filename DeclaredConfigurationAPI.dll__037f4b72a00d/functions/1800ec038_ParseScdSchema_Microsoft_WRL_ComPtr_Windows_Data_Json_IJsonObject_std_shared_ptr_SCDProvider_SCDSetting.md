# ParseScdSchema(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,std::shared_ptr<SCDProvider>,SCDSetting &)

- ea: `0x1800ec038`
- end: `0x1800ec557`
- name: `?ParseScdSchema@@YAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@V?$shared_ptr@VSCDProvider@@@std@@AEAVSCDSetting@@@Z`
- size: `1311`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ec560`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x18001438c`
- `0x180018ac0`
- `0x180019188`
- `0x180019208`
- `0x180019270`
- `0x1800192f8`
- `0x18001dea8`
- `0x18001def8`
- `0x18001dfbc`
- `0x1800370b0`
- `0x1800370d4`
- `0x18004abf8`
- `0x1800e8dfc`
- `0x1800e8fd0`
- `0x1800e9c4c`
- `0x1800ea558`
- `0x1800ec038`
- `0x1800ee34c`
- `0x1800ee8cc`
- `0x1800f4070`
- `0x180139010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec0ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec1c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec453`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec0ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec1c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec453`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec0d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec188`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec3c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec416`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec4a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec4ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec0d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec188`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec3c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec416`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec4a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec4ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec516`

## string_xrefs

- `0x1800ec0bd`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`
- `0x1800ec1f9`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`
- `0x1800ec2fc`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`
- `0x1800ec48e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`
- `0x1800ec501`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ParseScdSchema(__int64 *a1, _QWORD *a2, __int64 a3)
{
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v8; // rax
  int v9; // ebx
  __int64 v10; // rdx
  PCWSTR StringRawBuffer; // rax
  unsigned int v12; // r12d
  __int64 v13; // rdx
  __int64 *v14; // rsi
  __int64 v15; // rdi
  unsigned int (__fastcall *v16)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v17; // rax
  PCWSTR v18; // rax
  __int64 v19; // rdx
  __int64 *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rdx
  std::_Ref_count_base *v23; // rcx
  __int64 v24; // rdi
  unsigned int (__fastcall *v25)(__int64, _QWORD, __int64 *); // rbx
  __int64 v26; // rax
  __int64 v27; // rdi
  _QWORD *v28; // rbx
  __int64 v29; // rdx
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rdi
  unsigned int (__fastcall *v34)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v35; // rax
  PCWSTR v36; // rax
  std::_Ref_count_base *v37; // rcx
  HSTRING string; // [rsp+20h] [rbp-59h] BYREF
  HSTRING v40; // [rsp+28h] [rbp-51h] BYREF
  __int64 v41; // [rsp+30h] [rbp-49h] BYREF
  std::_Ref_count_base *v42; // [rsp+38h] [rbp-41h]
  __int64 v43; // [rsp+40h] [rbp-39h] BYREF
  std::_Ref_count_base *v44; // [rsp+48h] [rbp-31h]
  _QWORD *v45; // [rsp+50h] [rbp-29h]
  _QWORD v46[4]; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v47[32]; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v45 = a2;
  string = 0;
  LODWORD(v41) = 0;
  v6 = *a1;
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a1 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v47, &c_tagType);
  v9 = v7(v6, *(_QWORD *)(v8 + 24), &string);
  if ( v9 < 0 )
  {
    v10 = 1529;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
      (const char *)(unsigned int)v9,
      (int)string);
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_43;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring((__int64)v46, (__int64)StringRawBuffer);
  v9 = SCDSchemaTypeFromString(v46, &v41);
  std::wstring::_Tidy_deallocate(v46);
  if ( v9 < 0 )
  {
    v10 = 1530;
    goto LABEL_3;
  }
  v12 = v41;
  *(_DWORD *)(a3 + 88) = v41;
  if ( v12 == 11 )
  {
    v9 = ParseScdDynamicObjectSchema(a1, a3, a3);
    if ( v9 < 0 )
    {
      v13 = 1535;
LABEL_41:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
        (const char *)(unsigned int)v9,
        (int)string);
      goto LABEL_42;
    }
    v14 = (__int64 *)(a3 + 96);
    std::wstring::operator=(*(_QWORD *)(a3 + 96) + 16LL, a3);
    goto LABEL_39;
  }
  if ( v12 == 10 )
  {
    v40 = 0;
    LODWORD(v41) = 0;
    v15 = *a1;
    v16 = *(unsigned int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a1 + 80LL);
    WindowsDeleteString(0);
    v40 = 0;
    v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v47, &c_tagMetatype);
    if ( !v16(v15, *(_QWORD *)(v17 + 24), &v40) )
    {
      v18 = WindowsGetStringRawBuffer(v40, 0);
      std::wstring::wstring((__int64)v46, (__int64)v18);
      v9 = SCDSchemaMetaTypeFromString(v46, 10, &v41);
      std::wstring::_Tidy_deallocate(v46);
      if ( v9 < 0 )
      {
        v19 = 1548;
LABEL_14:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
          (const char *)(unsigned int)v9,
          (int)string);
LABEL_15:
        WindowsDeleteString(v40);
        v40 = 0;
        goto LABEL_42;
      }
      if ( !(_DWORD)v41 )
      {
        v9 = -2147418113;
        v19 = 1549;
        goto LABEL_14;
      }
    }
    v20 = (__int64 *)std::make_shared<SCDObjectSchema,>(&v41);
    v14 = (__int64 *)(a3 + 96);
    v21 = *v20;
    v22 = v20[1];
    *v20 = 0;
    v20[1] = 0;
    *(_QWORD *)(a3 + 96) = v21;
    v23 = *(std::_Ref_count_base **)(a3 + 104);
    *(_QWORD *)(a3 + 104) = v22;
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    if ( v42 )
      std::_Ref_count_base::_Decref(v42);
    std::wstring::operator=(*v14 + 16, a3);
    v43 = 0;
    v24 = *a1;
    v25 = *(unsigned int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*a1 + 64LL);
    v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v47, &c_tagProperties);
    if ( !v25(v24, *(_QWORD *)(v26 + 24), &v43) )
    {
      v27 = *v14;
      v28 = std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(v46, a2);
      v41 = v43;
      Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::InternalAddRef(&v41);
      v9 = ParseProperties(&v41, a3, v28, v27 + 48);
      if ( v9 < 0 )
      {
        v29 = 1558;
LABEL_25:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v29,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
          (const char *)(unsigned int)v9,
          (int)string);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        goto LABEL_15;
      }
      if ( *(_QWORD *)(*v14 + 56) == *(_QWORD *)(*v14 + 48) )
      {
        v9 = -2147024809;
        v29 = 1561;
        goto LABEL_25;
      }
      if ( *(_DWORD *)(a3 + 92) == 20 )
      {
        std::dynamic_pointer_cast<SCDDynamicObjectSchema,SCDObjectSchema>(&v41, a3 + 96);
        v30 = v41;
        std::wstring::operator=(v41 + 72, **(_QWORD **)(*v14 + 48));
        v31 = std::operator+<unsigned short>(v47, a3, L"-");
        v32 = std::operator+<unsigned short>(v46, v31, v30 + 72);
        std::wstring::operator=(*v14 + 16, v32);
        std::wstring::_Tidy_deallocate(v46);
        std::wstring::_Tidy_deallocate(v47);
        if ( v42 )
          std::_Ref_count_base::_Decref(v42);
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    WindowsDeleteString(v40);
  }
  else
  {
    std::make_shared<SCDObjectSchema,>(&v43);
    v14 = (__int64 *)(a3 + 96);
    std::shared_ptr<OsConfigSettingResult>::operator=(a3 + 96, &v43);
    std::wstring::operator=(*(_QWORD *)(a3 + 96) + 16LL, a3);
    v40 = 0;
    LODWORD(v41) = 0;
    v33 = *a1;
    v34 = *(unsigned int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a1 + 80LL);
    WindowsDeleteString(0);
    v40 = 0;
    v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v47, &c_tagMetatype);
    if ( !v34(v33, *(_QWORD *)(v35 + 24), &v40) )
    {
      v36 = WindowsGetStringRawBuffer(v40, 0);
      std::wstring::wstring((__int64)v46, (__int64)v36);
      v9 = SCDSchemaMetaTypeFromString(v46, v12, &v41);
      std::wstring::_Tidy_deallocate(v46);
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62F,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
          (const char *)(unsigned int)v9,
          (int)string);
        WindowsDeleteString(v40);
        v40 = 0;
        if ( v44 )
          std::_Ref_count_base::_Decref(v44);
        goto LABEL_42;
      }
      *(_DWORD *)(a3 + 92) = v41;
    }
    WindowsDeleteString(v40);
    v40 = 0;
    if ( v44 )
      std::_Ref_count_base::_Decref(v44);
  }
LABEL_39:
  v9 = ValidateScdObjectSchema(v14, 0, 0);
  if ( v9 < 0 )
  {
    v13 = 1588;
    goto LABEL_41;
  }
LABEL_42:
  WindowsDeleteString(string);
  string = 0;
LABEL_43:
  v37 = (std::_Ref_count_base *)a2[1];
  if ( v37 )
    std::_Ref_count_base::_Decref(v37);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800ec038  mov     [rsp-8+arg_18], rbx
0x1800ec03d  push    rbp
0x1800ec03e  push    rsi
0x1800ec03f  push    rdi
0x1800ec040  push    r12
0x1800ec042  push    r13
0x1800ec044  push    r14
0x1800ec046  push    r15
0x1800ec048  lea     rbp, [rsp-27h]
0x1800ec04d  sub     rsp, 0A0h
0x1800ec054  mov     rax, cs:__security_cookie
0x1800ec05b  xor     rax, rsp
0x1800ec05e  mov     [rbp+57h+var_38], rax
0x1800ec062  mov     r14, r8
0x1800ec065  mov     r15, rdx
0x1800ec068  mov     r13, rcx
0x1800ec06b  mov     [rbp+57h+var_80], rdx
0x1800ec06f  xor     esi, esi
0x1800ec071  mov     [rbp+57h+string], rsi
0x1800ec075  mov     dword ptr [rbp+57h+var_A0], esi
0x1800ec078  mov     rdi, [rcx]
0x1800ec07b  mov     rax, [rdi]
0x1800ec07e  mov     rbx, [rax+50h]
0x1800ec082  xor     ecx, ecx; string
0x1800ec084  call    cs:__imp_WindowsDeleteString
0x1800ec08a  mov     [rbp+57h+string], rsi
0x1800ec08e  lea     rdx, ?c_tagType@@3PEBGEB; ushort const * const c_tagType
0x1800ec095  lea     rcx, [rbp+57h+var_58]
0x1800ec099  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ec09e  nop
0x1800ec09f  lea     r8, [rbp+57h+string]
0x1800ec0a3  mov     rdx, [rax+18h]
0x1800ec0a7  mov     rcx, rdi
0x1800ec0aa  mov     rax, rbx
0x1800ec0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec0b2  mov     ebx, eax
0x1800ec0b4  test    eax, eax
0x1800ec0b6  jns     short loc_1800EC0E4
0x1800ec0b8  mov     edx, 5F9h; void *
0x1800ec0bd  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ec0c4  mov     r9d, ebx; char *
0x1800ec0c7  mov     rcx, [rbp+5Fh]; this
0x1800ec0cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec0d0  nop
0x1800ec0d1  mov     rcx, [rbp+57h+string]; string
0x1800ec0d5  call    cs:__imp_WindowsDeleteString
0x1800ec0db  mov     [rbp+57h+string], rsi
0x1800ec0df  jmp     loc_1800EC520
0x1800ec0e4  xor     edx, edx; length
0x1800ec0e6  mov     rcx, [rbp+57h+string]; string
0x1800ec0ea  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ec0f0  mov     rdx, rax
0x1800ec0f3  lea     rcx, [rbp+57h+var_78]
0x1800ec0f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ec0fc  lea     rdx, [rbp+57h+var_A0]
0x1800ec100  lea     rcx, [rbp+57h+var_78]
0x1800ec104  call    ?SCDSchemaTypeFromString@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAW4SCD_SCHEMA_TYPE@@@Z; SCDSchemaTypeFromString(std::wstring const &,SCD_SCHEMA_TYPE &)
0x1800ec109  mov     ebx, eax
0x1800ec10b  lea     rcx, [rbp+57h+var_78]
0x1800ec10f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ec114  test    ebx, ebx
0x1800ec116  jns     short loc_1800EC11F
0x1800ec118  mov     edx, 5FAh
0x1800ec11d  jmp     short loc_1800EC0BD
0x1800ec11f  mov     r12d, dword ptr [rbp+57h+var_A0]
0x1800ec123  mov     [r14+58h], r12d
0x1800ec127  cmp     r12d, 0Bh
0x1800ec12b  jnz     short loc_1800EC166
0x1800ec12d  mov     r8, r14
0x1800ec130  mov     rdx, r14
0x1800ec133  mov     rcx, r13
0x1800ec136  call    ?ParseScdDynamicObjectSchema@@YAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVSCDSetting@@@Z; ParseScdDynamicObjectSchema(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,std::wstring &,SCDSetting &)
0x1800ec13b  mov     ebx, eax
0x1800ec13d  xor     r12d, r12d
0x1800ec140  test    eax, eax
0x1800ec142  jns     short loc_1800EC14E
0x1800ec144  mov     edx, 5FFh
0x1800ec149  jmp     loc_1800EC4FE
0x1800ec14e  lea     rsi, [r14+60h]
0x1800ec152  mov     rcx, [rsi]
0x1800ec155  add     rcx, 10h
0x1800ec159  mov     rdx, r14
0x1800ec15c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800ec161  jmp     loc_1800EC4E6
0x1800ec166  cmp     r12d, 0Ah
0x1800ec16a  jnz     loc_1800EC3D1
0x1800ec170  xor     r12d, r12d
0x1800ec173  mov     [rbp+57h+var_A8], r12
0x1800ec177  mov     dword ptr [rbp+57h+var_A0], r12d
0x1800ec17b  mov     rdi, [r13+0]
0x1800ec17f  mov     rax, [rdi]
0x1800ec182  mov     rbx, [rax+50h]
0x1800ec186  xor     ecx, ecx; string
0x1800ec188  call    cs:__imp_WindowsDeleteString
0x1800ec18e  mov     [rbp+57h+var_A8], r12
0x1800ec192  lea     rdx, ?c_tagMetatype@@3PEBGEB; ushort const * const c_tagMetatype
0x1800ec199  lea     rcx, [rbp+57h+var_58]
0x1800ec19d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ec1a2  nop
0x1800ec1a3  lea     r8, [rbp+57h+var_A8]
0x1800ec1a7  mov     rdx, [rax+18h]
0x1800ec1ab  mov     rcx, rdi
0x1800ec1ae  mov     rax, rbx
0x1800ec1b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec1b6  nop
0x1800ec1b7  test    eax, eax
0x1800ec1b9  jnz     short loc_1800EC232
0x1800ec1bb  xor     edx, edx; length
0x1800ec1bd  mov     rcx, [rbp+57h+var_A8]; string
0x1800ec1c1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ec1c7  mov     rdx, rax
0x1800ec1ca  lea     rcx, [rbp+57h+var_78]
0x1800ec1ce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ec1d3  lea     r8, [rbp+57h+var_A0]
0x1800ec1d7  lea     edx, [r12+0Ah]
0x1800ec1dc  lea     rcx, [rbp+57h+var_78]
0x1800ec1e0  call    ?SCDSchemaMetaTypeFromString@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4SCD_SCHEMA_TYPE@@AEAW4SCD_SCHEMA_METATYPE@@@Z; SCDSchemaMetaTypeFromString(std::wstring const &,SCD_SCHEMA_TYPE,SCD_SCHEMA_METATYPE &)
0x1800ec1e5  mov     ebx, eax
0x1800ec1e7  lea     rcx, [rbp+57h+var_78]
0x1800ec1eb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ec1f0  test    ebx, ebx
0x1800ec1f2  jns     short loc_1800EC220
0x1800ec1f4  mov     edx, 60Ch; void *
0x1800ec1f9  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ec200  mov     r9d, ebx; char *
0x1800ec203  mov     rcx, [rbp+5Fh]; this
0x1800ec207  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec20c  nop
0x1800ec20d  mov     rcx, [rbp+57h+var_A8]; string
0x1800ec211  call    cs:__imp_WindowsDeleteString
0x1800ec217  mov     [rbp+57h+var_A8], r12
0x1800ec21b  jmp     loc_1800EC512
0x1800ec220  cmp     dword ptr [rbp+57h+var_A0], r12d
0x1800ec224  jnz     short loc_1800EC232
0x1800ec226  mov     ebx, 8000FFFFh
0x1800ec22b  mov     edx, 60Dh
0x1800ec230  jmp     short loc_1800EC1F9
0x1800ec232  lea     rcx, [rbp+57h+var_A0]
0x1800ec236  call    ??$make_shared@VSCDObjectSchema@@$$V@std@@YA?AV?$shared_ptr@VSCDObjectSchema@@@0@XZ; std::make_shared<SCDObjectSchema,>(void)
0x1800ec23b  lea     rsi, [r14+60h]
0x1800ec23f  mov     rcx, [rax]
0x1800ec242  mov     rdx, [rax+8]
0x1800ec246  mov     [rax], r12
0x1800ec249  mov     [rax+8], r12
0x1800ec24d  mov     [rsi], rcx
0x1800ec250  mov     rcx, [rsi+8]; this
0x1800ec254  mov     [rsi+8], rdx
0x1800ec258  test    rcx, rcx
0x1800ec25b  jz      short loc_1800EC262
0x1800ec25d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ec262  mov     rcx, [rbp+57h+var_98]; this
0x1800ec266  test    rcx, rcx
0x1800ec269  jz      short loc_1800EC270
0x1800ec26b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ec270  mov     rcx, [rsi]
0x1800ec273  add     rcx, 10h
0x1800ec277  mov     rdx, r14
0x1800ec27a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800ec27f  mov     [rbp+57h+var_90], r12
0x1800ec283  mov     rdi, [r13+0]
0x1800ec287  mov     rax, [rdi]
0x1800ec28a  mov     rbx, [rax+40h]
0x1800ec28e  lea     rdx, ?c_tagProperties@@3PEBGEB; ushort const * const c_tagProperties
0x1800ec295  lea     rcx, [rbp+57h+var_58]
0x1800ec299  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ec29e  nop
0x1800ec29f  lea     r8, [rbp+57h+var_90]
0x1800ec2a3  mov     rdx, [rax+18h]
0x1800ec2a7  mov     rcx, rdi
0x1800ec2aa  mov     rax, rbx
0x1800ec2ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec2b2  nop
0x1800ec2b3  test    eax, eax
0x1800ec2b5  jnz     loc_1800EC3B8
0x1800ec2bb  mov     rdi, [rsi]
0x1800ec2be  mov     rdx, r15
0x1800ec2c1  lea     rcx, [rbp+57h+var_78]
0x1800ec2c5  call    ??0?$shared_ptr@VSCDSetting@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(std::shared_ptr<SCDSetting> const &)
0x1800ec2ca  mov     rbx, rax
0x1800ec2cd  mov     rcx, [rbp+57h+var_90]
0x1800ec2d1  mov     [rbp+57h+var_A0], rcx
0x1800ec2d5  lea     rcx, [rbp+57h+var_A0]
0x1800ec2d9  call    ?InternalAddRef@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::InternalAddRef(void)
0x1800ec2de  lea     r9, [rdi+30h]
0x1800ec2e2  mov     r8, rbx
0x1800ec2e5  mov     rdx, r14
0x1800ec2e8  lea     rcx, [rbp+57h+var_A0]
0x1800ec2ec  call    ?ParseProperties@@YAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VSCDProvider@@@5@AEAV?$vector@V?$shared_ptr@VSCDSetting@@@std@@V?$allocator@V?$shared_ptr@VSCDSetting@@@std@@@2@@5@@Z; ParseProperties(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,std::wstring &,std::shared_ptr<SCDProvider>,std::vector<std::shared_ptr<SCDSetting>> &)
0x1800ec2f1  mov     ebx, eax
0x1800ec2f3  test    eax, eax
0x1800ec2f5  jns     short loc_1800EC31E
0x1800ec2f7  mov     edx, 616h; void *
0x1800ec2fc  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ec303  mov     r9d, ebx; char *
0x1800ec306  mov     rcx, [rbp+5Fh]; this
0x1800ec30a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec30f  nop
0x1800ec310  lea     rcx, [rbp+57h+var_90]
0x1800ec314  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ec319  jmp     loc_1800EC20D
0x1800ec31e  mov     rcx, [rsi]
0x1800ec321  mov     rax, [rcx+38h]
0x1800ec325  cmp     rax, [rcx+30h]
0x1800ec329  jnz     short loc_1800EC337
0x1800ec32b  mov     ebx, 80070057h
0x1800ec330  mov     edx, 619h
0x1800ec335  jmp     short loc_1800EC2FC
0x1800ec337  cmp     dword ptr [r14+5Ch], 14h
0x1800ec33c  jnz     short loc_1800EC3B8
0x1800ec33e  mov     rdx, rsi
0x1800ec341  lea     rcx, [rbp+57h+var_A0]
0x1800ec345  call    ??$dynamic_pointer_cast@VSCDDynamicObjectSchema@@VSCDObjectSchema@@@std@@YA?AV?$shared_ptr@VSCDDynamicObjectSchema@@@0@AEBV?$shared_ptr@VSCDObjectSchema@@@0@@Z; std::dynamic_pointer_cast<SCDDynamicObjectSchema,SCDObjectSchema>(std::shared_ptr<SCDObjectSchema> const &)
0x1800ec34a  nop
0x1800ec34b  mov     rbx, [rbp+57h+var_A0]
0x1800ec34f  mov     rax, [rsi]
0x1800ec352  mov     rdx, [rax+30h]
0x1800ec356  mov     rdx, [rdx]
0x1800ec359  lea     rcx, [rbx+48h]
0x1800ec35d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800ec362  lea     r8, asc_1801566E8; "-"
0x1800ec369  mov     rdx, r14
0x1800ec36c  lea     rcx, [rbp+57h+var_58]
0x1800ec370  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800ec375  nop
0x1800ec376  lea     r8, [rbx+48h]
0x1800ec37a  mov     rdx, rax
0x1800ec37d  lea     rcx, [rbp+57h+var_78]
0x1800ec381  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800ec386  mov     rcx, [rsi]
0x1800ec389  add     rcx, 10h
0x1800ec38d  mov     rdx, rax
0x1800ec390  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800ec395  lea     rcx, [rbp+57h+var_78]
0x1800ec399  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ec39e  nop
0x1800ec39f  lea     rcx, [rbp+57h+var_58]
0x1800ec3a3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ec3a8  nop
0x1800ec3a9  mov     rcx, [rbp+57h+var_98]; this
0x1800ec3ad  test    rcx, rcx
0x1800ec3b0  jz      short loc_1800EC3B8
0x1800ec3b2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ec3b7  nop
0x1800ec3b8  lea     rcx, [rbp+57h+var_90]
0x1800ec3bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ec3c1  nop
0x1800ec3c2  mov     rcx, [rbp+57h+var_A8]; string
0x1800ec3c6  call    cs:__imp_WindowsDeleteString
0x1800ec3cc  jmp     loc_1800EC4E6
0x1800ec3d1  lea     rcx, [rbp+57h+var_90]
0x1800ec3d5  call    ??$make_shared@VSCDObjectSchema@@$$V@std@@YA?AV?$shared_ptr@VSCDObjectSchema@@@0@XZ; std::make_shared<SCDObjectSchema,>(void)
0x1800ec3da  nop
0x1800ec3db  lea     rsi, [r14+60h]
0x1800ec3df  lea     rdx, [rbp+57h+var_90]
0x1800ec3e3  mov     rcx, rsi
0x1800ec3e6  call    ??4?$shared_ptr@VOsConfigSettingResult@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<OsConfigSettingResult>::operator=(std::shared_ptr<OsConfigSettingResult> const &)
0x1800ec3eb  mov     rcx, [rsi]
0x1800ec3ee  add     rcx, 10h
0x1800ec3f2  mov     rdx, r14
0x1800ec3f5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800ec3fa  mov     [rbp+57h+var_A8], 0
0x1800ec402  mov     dword ptr [rbp+57h+var_A0], 0
0x1800ec409  mov     rdi, [r13+0]
0x1800ec40d  mov     rax, [rdi]
0x1800ec410  mov     rbx, [rax+50h]
0x1800ec414  xor     ecx, ecx; string
0x1800ec416  call    cs:__imp_WindowsDeleteString
0x1800ec41c  mov     [rbp+57h+var_A8], 0
0x1800ec424  lea     rdx, ?c_tagMetatype@@3PEBGEB; ushort const * const c_tagMetatype
0x1800ec42b  lea     rcx, [rbp+57h+var_58]
0x1800ec42f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ec434  nop
0x1800ec435  lea     r8, [rbp+57h+var_A8]
0x1800ec439  mov     rdx, [rax+18h]
0x1800ec43d  mov     rcx, rdi
0x1800ec440  mov     rax, rbx
0x1800ec443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec448  nop
0x1800ec449  test    eax, eax
0x1800ec44b  jnz     short loc_1800EC4C7
0x1800ec44d  xor     edx, edx; length
0x1800ec44f  mov     rcx, [rbp+57h+var_A8]; string
0x1800ec453  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ec459  mov     rdx, rax
0x1800ec45c  lea     rcx, [rbp+57h+var_78]
0x1800ec460  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ec465  lea     r8, [rbp+57h+var_A0]
0x1800ec469  mov     edx, r12d
0x1800ec46c  lea     rcx, [rbp+57h+var_78]
0x1800ec470  call    ?SCDSchemaMetaTypeFromString@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4SCD_SCHEMA_TYPE@@AEAW4SCD_SCHEMA_METATYPE@@@Z; SCDSchemaMetaTypeFromString(std::wstring const &,SCD_SCHEMA_TYPE,SCD_SCHEMA_METATYPE &)
0x1800ec475  mov     ebx, eax
0x1800ec477  lea     rcx, [rbp+57h+var_78]
0x1800ec47b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ec480  xor     r12d, r12d
0x1800ec483  test    ebx, ebx
0x1800ec485  jns     short loc_1800EC4BE
0x1800ec487  mov     rcx, [rbp+5Fh]; this
0x1800ec48b  mov     r9d, ebx; char *
0x1800ec48e  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ec495  mov     edx, 62Fh; void *
  ... truncated ...
```
