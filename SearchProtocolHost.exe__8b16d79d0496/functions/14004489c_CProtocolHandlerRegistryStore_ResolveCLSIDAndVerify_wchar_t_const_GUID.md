# CProtocolHandlerRegistryStore::ResolveCLSIDAndVerify(wchar_t const *,_GUID &)

- ea: `0x14004489c`
- end: `0x1400449c8`
- name: `?ResolveCLSIDAndVerify@CProtocolHandlerRegistryStore@@AEAAJPEB_WAEAU_GUID@@@Z`
- size: `300`
- prototype: `HRESULT __fastcall(CProtocolHandlerRegistryStore *this, const wchar_t *, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140043310`

## callees

- `0x140005240`
- `0x14000e9b8`
- `0x14000f2b0`
- `0x1400104c8`
- `0x140037698`
- `0x140042dec`
- `0x14004489c`
- `0x1400470e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140044958`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140044958`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1400448c9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1400448c9`

## string_xrefs

- `0x1400448fd`: `CLSID\{`

## pseudocode

```c
HRESULT __fastcall CProtocolHandlerRegistryStore::ResolveCLSIDAndVerify(
        CProtocolHandlerRegistryStore *this,
        const wchar_t *a2,
        struct _GUID *a3)
{
  HRESULT result; // eax
  unsigned int v5; // r9d
  HKEY *phkResult; // rax
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  _QWORD v9[3]; // [rsp+38h] [rbp-D0h] BYREF
  struct _GUID v10; // [rsp+50h] [rbp-B8h] BYREF
  struct CLMString *v11; // [rsp+60h] [rbp-A8h]
  __int16 v12; // [rsp+68h] [rbp-A0h] BYREF
  void *retaddr; // [rsp+108h] [rbp+0h]

  v9[1] = -2;
  result = CLSIDFromProgID(a2, a3);
  if ( result >= 0 )
  {
    *(_QWORD *)v10.Data4 = &v12;
    v11 = (struct CLMString *)65;
    v12 = 0;
    *(_QWORD *)&v10.Data1 = &CCICommonPathString::`vftable';
    try
    {
      CLMString::operator=(&v10, L"CLSID\\{");
      SecUtil::GuidToString((SecUtil *)a3, &v10, (struct CLMString *)HIDWORD(v11), v5);
      CLMString::operator+=(&v10);
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        232,
        "onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\prothndlr.cxx");
    }
    v9[0] = 0;
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(v9);
    v7 = RegOpenKeyExW(HKEY_CLASSES_ROOT, *(LPCWSTR *)v10.Data4, 0, 0x20019u, phkResult);
    v8 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v9);
      TLMString<64,64,32767>::~TLMString<64,64,32767>(&v10);
      return v8;
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v9);
      TLMString<64,64,32767>::~TLMString<64,64,32767>(&v10);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14004489c  push    rbx
0x14004489e  sub     rsp, 100h
0x1400448a5  mov     [rsp+108h+var_C8], 0FFFFFFFFFFFFFFFEh
0x1400448ae  mov     rax, cs:__security_cookie
0x1400448b5  xor     rax, rsp
0x1400448b8  mov     [rsp+108h+var_18], rax
0x1400448c0  mov     rbx, r8
0x1400448c3  mov     rcx, rdx; lpszProgID
0x1400448c6  mov     rdx, r8; lpclsid
0x1400448c9  call    cs:__imp_CLSIDFromProgID
0x1400448cf  test    eax, eax
0x1400448d1  js      loc_1400449AF
0x1400448d7  lea     rax, [rsp+108h+var_A0]
0x1400448dc  mov     qword ptr [rsp+108h+var_B8.Data4], rax
0x1400448e1  mov     [rsp+108h+var_A8], 41h ; 'A'
0x1400448ea  xor     eax, eax
0x1400448ec  mov     [rsp+108h+var_A0], ax
0x1400448f1  lea     rax, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x1400448f8  mov     qword ptr [rsp+108h+var_B8.Data1], rax
0x1400448fd  lea     rdx, aClsid; "CLSID\\{"
0x140044904  lea     rcx, [rsp+108h+var_B8]
0x140044909  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x14004490e  mov     r8d, dword ptr [rsp+108h+var_A8+4]; struct CLMString *
0x140044913  lea     rdx, [rsp+108h+var_B8]; struct _GUID *
0x140044918  mov     rcx, rbx; this
0x14004491b  call    ?GuidToString@SecUtil@@YAPEB_WAEBU_GUID@@AEAVCLMString@@I@Z; SecUtil::GuidToString(_GUID const &,CLMString &,uint)
0x140044920  lea     rcx, [rsp+108h+var_B8]
0x140044925  call    ??YCLMString@@QEAAX_W@Z; CLMString::operator+=(wchar_t)
0x14004492a  nop
0x14004492b  mov     [rsp+108h+var_D0], 0
0x140044934  lea     rcx, [rsp+108h+var_D0]
0x140044939  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x14004493e  mov     [rsp+108h+phkResult], rax; phkResult
0x140044943  mov     r9d, 20019h; samDesired
0x140044949  xor     r8d, r8d; ulOptions
0x14004494c  mov     rdx, qword ptr [rsp+108h+var_B8.Data4]; lpSubKey
0x140044951  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140044958  call    cs:__imp_RegOpenKeyExW
0x14004495e  mov     ebx, eax
0x140044960  test    eax, eax
0x140044962  jz      short loc_140044988
0x140044964  jle     short loc_14004496F
0x140044966  movzx   ebx, ax
0x140044969  or      ebx, 80070000h
0x14004496f  lea     rcx, [rsp+108h+var_D0]
0x140044974  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140044979  nop
0x14004497a  lea     rcx, [rsp+108h+var_B8]
0x14004497f  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x140044984  mov     eax, ebx
0x140044986  jmp     short loc_1400449AF
0x140044988  lea     rcx, [rsp+108h+var_D0]
0x14004498d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140044992  nop
0x140044993  lea     rcx, [rsp+108h+var_B8]
0x140044998  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x14004499d  xor     eax, eax
0x14004499f  jmp     short loc_1400449AF
0x1400449a1  lea     rcx, [rsp+108h+var_B8]
0x1400449a6  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1400449ab  mov     eax, [rsp+108h+var_D8]
0x1400449af  mov     rcx, [rsp+108h+var_18]
0x1400449b7  xor     rcx, rsp; StackCookie
0x1400449ba  call    __security_check_cookie
0x1400449bf  add     rsp, 100h
0x1400449c6  pop     rbx
0x1400449c7  retn
```
