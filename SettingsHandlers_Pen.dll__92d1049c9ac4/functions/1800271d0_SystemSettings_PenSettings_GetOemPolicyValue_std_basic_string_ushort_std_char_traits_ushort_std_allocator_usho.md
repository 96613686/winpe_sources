# SystemSettings::PenSettings::GetOemPolicyValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800271d0`
- end: `0x1800272b1`
- name: `?GetOemPolicyValue@PenSettings@SystemSettings@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z`
- size: `225`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180027350`
- `0x180028910`
- `0x18002faf0`

## callees

- `0x1800030e0`
- `0x180005af0`
- `0x180006240`
- `0x1800103b4`
- `0x180019fcc`
- `0x18001a378`
- `0x18001acf8`
- `0x18001cff8`
- `0x18001f3b0`
- `0x180020700`
- `0x1800271d0`

## import_xrefs

- `policymanager!PolicyManager_GetPolicyString` at `0x18002724b`
- `policymanager!PolicyManager_GetPolicyString` at `0x18002724b`
- `policymanager!PolicyManager_FreeStringValue` at `0x18002721e`
- `policymanager!PolicyManager_FreeStringValue` at `0x18002721e`

## string_xrefs

- `0x180027244`: `PenConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::PenSettings::GetOemPolicyValue(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  _QWORD v8[3]; // [rsp+20h] [rbp-40h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-28h] BYREF

  v8[1] = a1;
  std::wstring::wstring(v9, a2, a3);
  v8[0] = 0;
  v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  if ( (int)PolicyManager_GetPolicyString(L"PenConfiguration", v5, v8) >= 0 && v8[0] )
  {
    std::_WChar_traits<unsigned short>::length(v8[0]);
    std::wstring::_Assign<unsigned short>(v9, v6);
  }
  std::wstring::wstring(a1, v9);
  std::wstring::_Tidy_deallocate(v9);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(unsigned short *),&long PolicyManager_FreeStringValue(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(unsigned short *),&long PolicyManager_FreeStringValue(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v8);
  return a1;
}

```

## disassembly

```asm
0x1800271d0  mov     [rsp-18h+arg_10], rbx
0x1800271d5  push    rbp
0x1800271d6  push    rsi
0x1800271d7  push    rdi
0x1800271d8  mov     rbp, rsp
0x1800271db  sub     rsp, 60h
0x1800271df  mov     rax, cs:__security_cookie
0x1800271e6  xor     rax, rsp
0x1800271e9  mov     [rbp+var_8], rax
0x1800271ed  mov     rsi, rdx
0x1800271f0  mov     rbx, rcx
0x1800271f3  mov     [rbp+var_38], rcx
0x1800271f7  mov     [rbp+var_40], 0
0x1800271ff  lea     rcx, [rbp+var_28]
0x180027203  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180027208  nop
0x180027209  mov     rdi, [rbp+var_40]
0x18002720d  test    rdi, rdi
0x180027210  jz      short loc_18002722D
0x180027212  lea     rcx, [rbp+var_38]; this
0x180027216  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002721b  mov     rcx, rdi
0x18002721e  call    cs:__imp_PolicyManager_FreeStringValue
0x180027224  lea     rcx, [rbp+var_38]; this
0x180027228  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002722d  mov     [rbp+var_40], 0
0x180027235  mov     rcx, rsi
0x180027238  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002723d  lea     r8, [rbp+var_40]
0x180027241  mov     rdx, rax
0x180027244  lea     rcx, aPenconfigurati; "PenConfiguration"
0x18002724b  call    cs:__imp_PolicyManager_GetPolicyString
0x180027251  test    eax, eax
0x180027253  js      short loc_180027272
0x180027255  mov     rcx, [rbp+var_40]
0x180027259  test    rcx, rcx
0x18002725c  jz      short loc_180027272
0x18002725e  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180027263  mov     r8, rax
0x180027266  mov     rdx, rcx
0x180027269  lea     rcx, [rbp+var_28]
0x18002726d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180027272  lea     rdx, [rbp+var_28]
0x180027276  mov     rcx, rbx
0x180027279  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18002727e  nop
0x18002727f  lea     rcx, [rbp+var_28]
0x180027283  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027288  nop
0x180027289  lea     rcx, [rbp+var_40]
0x18002728d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAG@Z$1?PolicyManager_FreeStringValue@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(ushort *),&PolicyManager_FreeStringValue(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(ushort *),&PolicyManager_FreeStringValue(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180027292  mov     rax, rbx
0x180027295  mov     rcx, [rbp+var_8]
0x180027299  xor     rcx, rsp; StackCookie
0x18002729c  call    __security_check_cookie
0x1800272a1  mov     rbx, [rsp+60h+arg_10]
0x1800272a9  add     rsp, 60h
0x1800272ad  pop     rdi
0x1800272ae  pop     rsi
0x1800272af  pop     rbp
0x1800272b0  retn
```
