# CloudPrint::CloudPrintHelper::OpenCurrentUserMpsRegKey(CloudPrint::MpsRegKey,bool,ulong)

- ea: `0x18001a404`
- end: `0x18001a59c`
- name: `?OpenCurrentUserMpsRegKey@CloudPrintHelper@CloudPrint@@IEAAPEAUHKEY__@@W4MpsRegKey@2@_NK@Z`
- size: `408`
- prototype: `__int64 __fastcall(__int64, int, char, unsigned int)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014de4`
- `0x1800154fc`
- `0x18001bc2c`

## callees

- `0x180003a60`
- `0x180007468`
- `0x18000af7c`
- `0x18000e208`
- `0x18000e2dc`
- `0x18000e790`
- `0x180011d98`
- `0x1800132e8`
- `0x18001463c`
- `0x18001a404`
- `0x18001baa4`
- `0x18001c0a8`

## string_xrefs

- `0x18001a453`: `Config`
- `0x18001a44c`: `Cache`
- `0x18001a464`: `Opening Current User MPS %s RegKey. CreateIfNotExist=%s, AccessMask=%u`
- `0x18001a46b`: `CloudPrint::CloudPrintHelper::OpenCurrentUserMpsRegKey`
- `0x18001a4a1`: `Couldn't get Current User SID.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CloudPrint::CloudPrintHelper::OpenCurrentUserMpsRegKey(__int64 a1, int a2, char a3, unsigned int a4)
{
  const wchar_t *v8; // r9
  const wchar_t *v9; // r8
  unsigned int CurrentUserSid; // eax
  __int64 v11; // rax
  __int64 v12; // rbx
  const char *v14; // [rsp+28h] [rbp-21h]
  __int64 v15; // [rsp+30h] [rbp-19h] BYREF
  __int64 v16; // [rsp+38h] [rbp-11h] BYREF
  _BYTE v17[32]; // [rsp+40h] [rbp-9h] BYREF
  _OWORD v18[2]; // [rsp+60h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v8 = L"true";
  if ( !a3 )
    v8 = L"false";
  v9 = L"Config";
  if ( a2 )
    v9 = L"Cache";
  CloudPrintHelperTelemetry::WriteDbgTraceInfo(
    "CloudPrint::CloudPrintHelper::OpenCurrentUserMpsRegKey",
    L"Opening Current User MPS %s RegKey. CreateIfNotExist=%s, AccessMask=%u",
    v9,
    v8,
    a4);
  v18[0] = 0;
  v18[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v18[0]) = 0;
  CurrentUserSid = CloudPrint::CloudPrintHelper::GetCurrentUserSid(a1, v18);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x71D,
    (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
    (const char *)CurrentUserSid,
    (int)"Couldn't get Current User SID.",
    v14);
  std::wstring::wstring(v17, v18);
  std::wstring::append(v17, L"\\");
  std::wstring::append(v17, L"Software\\Microsoft\\Print\\MPS");
  if ( a2 == 1 )
  {
    std::wstring::append(v17, L"\\");
    std::wstring::append(v17, L"State");
  }
  v15 = 0;
  v16 = -2147483645;
  if ( a3 )
    v11 = PrintCore::RegHelpers::CreateOrOpenKey(&v16, v17, a4);
  else
    v11 = PrintCore::RegHelpers::OpenKey(&v16, v17, a4);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v15,
    v11);
  v12 = v15;
  v15 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
  std::wstring::_Tidy_deallocate(v17);
  std::wstring::_Tidy_deallocate(v18);
  return v12;
}

```

## disassembly

```asm
0x18001a404  mov     [rsp-8+arg_8], rbx
0x18001a409  mov     [rsp-8+arg_10], rsi
0x18001a40e  push    rbp
0x18001a40f  push    rdi
0x18001a410  push    r14
0x18001a412  lea     rbp, [rsp-47h]
0x18001a417  sub     rsp, 90h
0x18001a41e  mov     rax, cs:__security_cookie
0x18001a425  xor     rax, rsp
0x18001a428  mov     [rbp+57h+var_20], rax
0x18001a42c  mov     esi, r9d
0x18001a42f  mov     r14b, r8b
0x18001a432  mov     edi, edx
0x18001a434  mov     rbx, rcx
0x18001a437  lea     rax, aFalse; "false"
0x18001a43e  lea     r9, aTrue; "true"
0x18001a445  test    r8b, r8b
0x18001a448  cmovz   r9, rax
0x18001a44c  lea     rax, aCache; "Cache"
0x18001a453  lea     r8, aConfig; "Config"
0x18001a45a  test    edx, edx
0x18001a45c  cmovnz  r8, rax
0x18001a460  mov     [rsp+0A0h+var_80], esi
0x18001a464  lea     rdx, aOpeningCurrent; "Opening Current User MPS %s RegKey. Cre"...
0x18001a46b  lea     rcx, aCloudprintClou_27; "CloudPrint::CloudPrintHelper::OpenCurre"...
0x18001a472  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001a477  xorps   xmm0, xmm0
0x18001a47a  movups  [rbp+57h+var_40], xmm0
0x18001a47e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001a486  movdqu  [rbp+57h+var_30], xmm1
0x18001a48b  xor     eax, eax
0x18001a48d  mov     word ptr [rbp+57h+var_40], ax
0x18001a491  lea     rdx, [rbp+57h+var_40]
0x18001a495  mov     rcx, rbx
0x18001a498  call    ?GetCurrentUserSid@CloudPrintHelper@CloudPrint@@IEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudPrint::CloudPrintHelper::GetCurrentUserSid(std::wstring &)
0x18001a49d  mov     rcx, [rbp+5Fh]; this
0x18001a4a1  lea     rdx, aCouldnTGetCurr; "Couldn't get Current User SID."
0x18001a4a8  mov     qword ptr [rsp+0A0h+var_80], rdx; int
0x18001a4ad  mov     r9d, eax; char *
0x18001a4b0  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x18001a4b7  mov     edx, 71Dh; void *
0x18001a4bc  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001a4c1  lea     rdx, [rbp+57h+var_40]
0x18001a4c5  lea     rcx, [rbp+57h+var_60]
0x18001a4c9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a4ce  nop
0x18001a4cf  lea     rdx, asc_18002DEF8; "\\"
0x18001a4d6  lea     rcx, [rbp+57h+var_60]
0x18001a4da  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001a4df  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Print\\MPS"
0x18001a4e6  lea     rcx, [rbp+57h+var_60]
0x18001a4ea  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001a4ef  cmp     edi, 1
0x18001a4f2  jnz     short loc_18001A514
0x18001a4f4  lea     rdx, asc_18002DEF8; "\\"
0x18001a4fb  lea     rcx, [rbp+57h+var_60]
0x18001a4ff  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001a504  lea     rdx, ValueName; "State"
0x18001a50b  lea     rcx, [rbp+57h+var_60]
0x18001a50f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001a514  mov     [rbp+57h+var_70], 0
0x18001a51c  mov     [rbp+57h+var_68], 0FFFFFFFF80000003h
0x18001a524  mov     r8d, esi
0x18001a527  lea     rdx, [rbp+57h+var_60]
0x18001a52b  lea     rcx, [rbp+57h+var_68]
0x18001a52f  test    r14b, r14b
0x18001a532  jz      short loc_18001A53B
0x18001a534  call    ?CreateOrOpenKey@RegHelpers@PrintCore@@SAPEAUHKEY__@@AEBQEAU3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::CreateOrOpenKey(HKEY__ * const &,std::wstring const &,ulong)
0x18001a539  jmp     short loc_18001A540
0x18001a53b  call    ?OpenKey@RegHelpers@PrintCore@@SAPEAUHKEY__@@AEBQEAU3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::OpenKey(HKEY__ * const &,std::wstring const &,ulong)
0x18001a540  mov     rdx, rax
0x18001a543  lea     rcx, [rbp+57h+var_70]
0x18001a547  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001a54c  mov     rbx, [rbp+57h+var_70]
0x18001a550  mov     [rbp+57h+var_70], 0
0x18001a558  lea     rcx, [rbp+57h+var_70]
0x18001a55c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001a561  nop
0x18001a562  lea     rcx, [rbp+57h+var_60]
0x18001a566  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a56b  nop
0x18001a56c  lea     rcx, [rbp+57h+var_40]
0x18001a570  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a575  mov     rax, rbx
0x18001a578  mov     rcx, [rbp+57h+var_20]
0x18001a57c  xor     rcx, rsp; StackCookie
0x18001a57f  call    __security_check_cookie
0x18001a584  lea     r11, [rsp+0A0h+var_10]
0x18001a58c  mov     rbx, [r11+28h]
0x18001a590  mov     rsi, [r11+30h]
0x18001a594  mov     rsp, r11
0x18001a597  pop     r14
0x18001a599  pop     rdi
0x18001a59a  pop     rbp
0x18001a59b  retn
```
