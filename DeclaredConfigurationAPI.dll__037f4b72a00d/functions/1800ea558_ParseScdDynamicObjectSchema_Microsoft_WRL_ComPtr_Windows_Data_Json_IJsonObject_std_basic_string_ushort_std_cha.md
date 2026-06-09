# ParseScdDynamicObjectSchema(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,SCDSetting &)

- ea: `0x1800ea558`
- end: `0x1800ea7a6`
- name: `?ParseScdDynamicObjectSchema@@YAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVSCDSetting@@@Z`
- size: `590`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ea7ac`
- `0x1800ec038`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x18001438c`
- `0x180018ac0`
- `0x180019188`
- `0x180019208`
- `0x180019d38`
- `0x18001def8`
- `0x18001dfbc`
- `0x1800370d4`
- `0x18004abf8`
- `0x1800e8f54`
- `0x1800ea558`
- `0x1800ee34c`
- `0x1800f4070`
- `0x180139010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ea63d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ea6ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ea63d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ea6ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea5f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea689`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea754`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea762`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea5f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea689`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea754`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ea762`

## string_xrefs

- `0x1800ea5ce`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`
- `0x1800ea73f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ParseScdDynamicObjectSchema(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  __int64 v8; // rax
  int v9; // eax
  int v10; // ebx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v13; // rax
  __int64 v14; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v18; // rax
  PCWSTR v19; // rax
  __int64 v20; // rbx
  __int64 v21; // r8
  HSTRING v23; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+28h] [rbp-48h] BYREF
  __int64 v25; // [rsp+30h] [rbp-40h] BYREF
  __int64 v26; // [rsp+38h] [rbp-38h] BYREF
  std::_Ref_count_base *v27; // [rsp+40h] [rbp-30h]
  __int64 v28; // [rsp+48h] [rbp-28h] BYREF
  std::_Ref_count_base *v29; // [rsp+50h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  std::make_shared<SCDDynamicObjectSchema,>(&v26);
  v25 = 0;
  v6 = *a1;
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v6 + 64LL);
  v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v28, &c_tagItems);
  v9 = v7(v6, *(_QWORD *)(v8 + 24), &v25);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x509,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
      (const char *)(unsigned int)v9,
      (int)v23);
    goto LABEL_17;
  }
  v23 = 0;
  string = 0;
  v11 = v25;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v25 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v28, &c_tagType);
  v10 = v12(v11, *(_QWORD *)(v13 + 24), &string);
  if ( v10 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring((__int64)&v28, (__int64)StringRawBuffer);
    v10 = SCDSchemaMetaTypeFromString(&v28, 11, a3 + 92);
    std::wstring::_Tidy_deallocate(&v28);
    if ( v10 >= 0 )
    {
      v16 = v25;
      v17 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v25 + 80LL);
      WindowsDeleteString(v23);
      v23 = 0;
      v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v28, &c_tagAlias);
      v10 = v17(v16, *(_QWORD *)(v18 + 24), &v23);
      if ( v10 >= 0 )
      {
        v19 = WindowsGetStringRawBuffer(v23, 0);
        v20 = v26;
        v21 = -1;
        do
          ++v21;
        while ( v19[v21] );
        std::wstring::_Assign<unsigned short>((char **)(v26 + 72), v19, (char *)v21);
        std::wstring::operator=(v20 + 16, a2);
        std::shared_ptr<OsConfigSettingResult>::operator=(a3 + 96, &v26);
        std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(&v28, &v26);
        v10 = ValidateScdObjectSchema(&v28, 0, 0);
        if ( v29 )
          std::_Ref_count_base::_Decref(v29);
        if ( v10 >= 0 )
          goto LABEL_16;
        v14 = 1302;
      }
      else
      {
        v14 = 1295;
      }
    }
    else
    {
      v14 = 1293;
    }
  }
  else
  {
    v14 = 1292;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
    (const char *)(unsigned int)v10,
    (int)v23);
LABEL_16:
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v23);
  v23 = 0;
LABEL_17:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800ea558  mov     [rsp-28h+arg_18], rbx
0x1800ea55d  push    rbp
0x1800ea55e  push    rsi
0x1800ea55f  push    rdi
0x1800ea560  push    r14
0x1800ea562  push    r15
0x1800ea564  mov     rbp, rsp
0x1800ea567  sub     rsp, 70h
0x1800ea56b  mov     rax, cs:__security_cookie
0x1800ea572  xor     rax, rsp
0x1800ea575  mov     [rbp+var_8], rax
0x1800ea579  mov     rsi, r8
0x1800ea57c  mov     r14, rdx
0x1800ea57f  mov     rdi, rcx
0x1800ea582  lea     rcx, [rbp+var_38]
0x1800ea586  call    ??$make_shared@VSCDDynamicObjectSchema@@$$V@std@@YA?AV?$shared_ptr@VSCDDynamicObjectSchema@@@0@XZ; std::make_shared<SCDDynamicObjectSchema,>(void)
0x1800ea58b  nop
0x1800ea58c  xor     r15d, r15d
0x1800ea58f  mov     [rbp+var_40], r15
0x1800ea593  mov     rdi, [rdi]
0x1800ea596  mov     rax, [rdi]
0x1800ea599  mov     rbx, [rax+40h]
0x1800ea59d  lea     rdx, ?c_tagItems@@3PEBGEB; ushort const * const c_tagItems
0x1800ea5a4  lea     rcx, [rbp+var_28]
0x1800ea5a8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ea5ad  nop
0x1800ea5ae  lea     r8, [rbp+var_40]
0x1800ea5b2  mov     rdx, [rax+18h]
0x1800ea5b6  mov     rcx, rdi
0x1800ea5b9  mov     rax, rbx
0x1800ea5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea5c1  mov     ebx, eax
0x1800ea5c3  test    eax, eax
0x1800ea5c5  jns     short loc_1800EA5E4
0x1800ea5c7  mov     rcx, [rbp+28h]; this
0x1800ea5cb  mov     r9d, eax; char *
0x1800ea5ce  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ea5d5  mov     edx, 509h; void *
0x1800ea5da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ea5df  jmp     loc_1800EA76C
0x1800ea5e4  mov     [rbp+var_50], r15
0x1800ea5e8  mov     [rbp+string], r15
0x1800ea5ec  mov     rdi, [rbp+var_40]
0x1800ea5f0  mov     rax, [rdi]
0x1800ea5f3  mov     rbx, [rax+50h]
0x1800ea5f7  xor     ecx, ecx; string
0x1800ea5f9  call    cs:__imp_WindowsDeleteString
0x1800ea5ff  mov     [rbp+string], r15
0x1800ea603  lea     rdx, ?c_tagType@@3PEBGEB; ushort const * const c_tagType
0x1800ea60a  lea     rcx, [rbp+var_28]
0x1800ea60e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ea613  nop
0x1800ea614  lea     r8, [rbp+string]
0x1800ea618  mov     rdx, [rax+18h]
0x1800ea61c  mov     rcx, rdi
0x1800ea61f  mov     rax, rbx
0x1800ea622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea627  mov     ebx, eax
0x1800ea629  test    eax, eax
0x1800ea62b  jns     short loc_1800EA637
0x1800ea62d  mov     edx, 50Ch
0x1800ea632  jmp     loc_1800EA73C
0x1800ea637  xor     edx, edx; length
0x1800ea639  mov     rcx, [rbp+string]; string
0x1800ea63d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ea643  mov     rdx, rax
0x1800ea646  lea     rcx, [rbp+var_28]
0x1800ea64a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ea64f  lea     r8, [rsi+5Ch]
0x1800ea653  mov     edx, 0Bh
0x1800ea658  lea     rcx, [rbp+var_28]
0x1800ea65c  call    ?SCDSchemaMetaTypeFromString@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4SCD_SCHEMA_TYPE@@AEAW4SCD_SCHEMA_METATYPE@@@Z; SCDSchemaMetaTypeFromString(std::wstring const &,SCD_SCHEMA_TYPE,SCD_SCHEMA_METATYPE &)
0x1800ea661  mov     ebx, eax
0x1800ea663  lea     rcx, [rbp+var_28]
0x1800ea667  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ea66c  test    ebx, ebx
0x1800ea66e  jns     short loc_1800EA67A
0x1800ea670  mov     edx, 50Dh
0x1800ea675  jmp     loc_1800EA73C
0x1800ea67a  mov     rdi, [rbp+var_40]
0x1800ea67e  mov     rax, [rdi]
0x1800ea681  mov     rbx, [rax+50h]
0x1800ea685  mov     rcx, [rbp+var_50]; string
0x1800ea689  call    cs:__imp_WindowsDeleteString
0x1800ea68f  mov     [rbp+var_50], r15
0x1800ea693  lea     rdx, ?c_tagAlias@@3PEBGEB; ushort const * const c_tagAlias
0x1800ea69a  lea     rcx, [rbp+var_28]
0x1800ea69e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ea6a3  nop
0x1800ea6a4  lea     r8, [rbp+var_50]
0x1800ea6a8  mov     rdx, [rax+18h]
0x1800ea6ac  mov     rcx, rdi
0x1800ea6af  mov     rax, rbx
0x1800ea6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea6b7  mov     ebx, eax
0x1800ea6b9  test    eax, eax
0x1800ea6bb  jns     short loc_1800EA6C4
0x1800ea6bd  mov     edx, 50Fh
0x1800ea6c2  jmp     short loc_1800EA73C
0x1800ea6c4  xor     edx, edx; length
0x1800ea6c6  mov     rcx, [rbp+var_50]; string
0x1800ea6ca  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ea6d0  mov     rbx, [rbp+var_38]
0x1800ea6d4  lea     rcx, [rbx+48h]
0x1800ea6d8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800ea6dc  inc     r8
0x1800ea6df  cmp     [rax+r8*2], r15w
0x1800ea6e4  jnz     short loc_1800EA6DC
0x1800ea6e6  mov     rdx, rax
0x1800ea6e9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800ea6ee  lea     rcx, [rbx+10h]
0x1800ea6f2  mov     rdx, r14
0x1800ea6f5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800ea6fa  lea     rcx, [rsi+60h]
0x1800ea6fe  lea     rdx, [rbp+var_38]
0x1800ea702  call    ??4?$shared_ptr@VOsConfigSettingResult@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<OsConfigSettingResult>::operator=(std::shared_ptr<OsConfigSettingResult> const &)
0x1800ea707  lea     rdx, [rbp+var_38]
0x1800ea70b  lea     rcx, [rbp+var_28]
0x1800ea70f  call    ??0?$shared_ptr@VSCDSetting@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(std::shared_ptr<SCDSetting> const &)
0x1800ea714  nop
0x1800ea715  xor     r8d, r8d
0x1800ea718  xor     edx, edx
0x1800ea71a  lea     rcx, [rbp+var_28]
0x1800ea71e  call    ?ValidateScdObjectSchema@@YAJAEBV?$shared_ptr@VSCDObjectSchema@@@std@@PEBV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@_N@Z; ValidateScdObjectSchema(std::shared_ptr<SCDObjectSchema> const &,std::unordered_set<std::wstring> const *,bool)
0x1800ea723  mov     ebx, eax
0x1800ea725  mov     rcx, [rbp+var_20]; this
0x1800ea729  test    rcx, rcx
0x1800ea72c  jz      short loc_1800EA733
0x1800ea72e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ea733  test    ebx, ebx
0x1800ea735  jns     short loc_1800EA750
0x1800ea737  mov     edx, 516h; void *
0x1800ea73c  mov     r9d, ebx; char *
0x1800ea73f  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ea746  mov     rcx, [rbp+28h]; this
0x1800ea74a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ea74f  nop
0x1800ea750  mov     rcx, [rbp+string]; string
0x1800ea754  call    cs:__imp_WindowsDeleteString
0x1800ea75a  mov     [rbp+string], r15
0x1800ea75e  mov     rcx, [rbp+var_50]; string
0x1800ea762  call    cs:__imp_WindowsDeleteString
0x1800ea768  mov     [rbp+var_50], r15
0x1800ea76c  lea     rcx, [rbp+var_40]
0x1800ea770  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ea775  nop
0x1800ea776  mov     rcx, [rbp+var_30]; this
0x1800ea77a  test    rcx, rcx
0x1800ea77d  jz      short loc_1800EA784
0x1800ea77f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ea784  mov     eax, ebx
0x1800ea786  mov     rcx, [rbp+var_8]
0x1800ea78a  xor     rcx, rsp; StackCookie
0x1800ea78d  call    __security_check_cookie
0x1800ea792  mov     rbx, [rsp+70h+arg_18]
0x1800ea79a  add     rsp, 70h
0x1800ea79e  pop     r15
0x1800ea7a0  pop     r14
0x1800ea7a2  pop     rdi
0x1800ea7a3  pop     rsi
0x1800ea7a4  pop     rbp
0x1800ea7a5  retn
```
