# UserDisplayLanguage::GetInstalledLanguages(void)

- ea: `0x1800223f8`
- end: `0x180022494`
- name: `?GetInstalledLanguages@UserDisplayLanguage@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `156`
- prototype: `void **__fastcall(void **lParam)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, installer_update`

## callers

- `0x18000fb54`

## callees

- `0x180010dd0`
- `0x180013294`
- `0x180016cc8`
- `0x18001e5ec`
- `0x1800223f8`
- `0x18002249c`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!EnumUILanguagesW` at `0x180022455`
- `api-ms-win-core-localization-obsolete-l1-2-0!EnumUILanguagesW` at `0x180022455`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall UserDisplayLanguage::GetInstalledLanguages(void **lParam)
{
  _QWORD v3[5]; // [rsp+30h] [rbp-28h] BYREF
  int pExceptionObject; // [rsp+68h] [rbp+10h] BYREF

  v3[0] = &std::tr1::_Impl_no_alloc0<std::tr1::_Callable_fun<std::vector<std::wstring> (*const)(void),0>,std::vector<std::wstring>>::`vftable';
  v3[1] = UserDisplayLanguage::DefaultGetUserDisplayLanguageList;
  v3[3] = v3;
  UserDisplayLanguage::GetPreferredLanguages(lParam, v3);
  if ( !EnumUILanguagesW(EnumUILanguagesProc, 0x48u, (LONG_PTR)lParam) )
  {
    pExceptionObject = ResultFromKnownLastError();
    throw (long *)&pExceptionObject;
  }
  NormalizeAllLanguageTags<std::vector<std::wstring>>(lParam);
  RemoveDuplicates<std::vector<std::wstring>>(lParam);
  return lParam;
}

```

## disassembly

```asm
0x1800223f8  mov     r11, rsp
0x1800223fb  mov     [r11+8], rcx
0x1800223ff  push    rbx
0x180022400  sub     rsp, 50h
0x180022404  mov     qword ptr [r11-30h], 0FFFFFFFFFFFFFFFEh
0x18002240c  mov     rbx, rcx
0x18002240f  mov     [rsp+58h+var_38], 0
0x180022417  lea     rax, ??_7?$_Impl_no_alloc0@U?$_Callable_fun@Q6A?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ$0A@@tr1@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@@tr1@std@@6B@; const std::tr1::_Impl_no_alloc0<std::tr1::_Callable_fun<std::vector<std::wstring> (*const)(void),0>,std::vector<std::wstring>>::`vftable'
0x18002241e  mov     [r11-28h], rax
0x180022422  lea     rax, ?DefaultGetUserDisplayLanguageList@UserDisplayLanguage@@CA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; UserDisplayLanguage::DefaultGetUserDisplayLanguageList(void)
0x180022429  mov     [r11-20h], rax
0x18002242d  lea     rax, [r11-28h]
0x180022431  mov     [r11-10h], rax
0x180022435  lea     rdx, [r11-28h]
0x180022439  call    ?GetPreferredLanguages@UserDisplayLanguage@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$function@$$A6A?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ@tr1@3@@Z; UserDisplayLanguage::GetPreferredLanguages(std::tr1::function<std::vector<std::wstring> (void)>)
0x18002243e  mov     [rsp+58h+var_38], 1
0x180022446  mov     r8, rbx; lParam
0x180022449  mov     edx, 48h ; 'H'; dwFlags
0x18002244e  lea     rcx, ?EnumUILanguagesProc@@YAHPEAG_J@Z; lpUILanguageEnumProc
0x180022455  call    cs:__imp_EnumUILanguagesW
0x18002245b  test    eax, eax
0x18002245d  jnz     short loc_18002247A
0x18002245f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180022464  mov     [rsp+58h+pExceptionObject], eax
0x180022468  lea     rdx, _TI1J; pThrowInfo
0x18002246f  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180022474  call    _CxxThrowException_0
0x18002247a  mov     rcx, rbx
0x18002247d  call    ??$NormalizeAllLanguageTags@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; NormalizeAllLanguageTags<std::vector<std::wstring>>(std::vector<std::wstring> &)
0x180022482  mov     rcx, rbx
0x180022485  call    ??$RemoveDuplicates@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; RemoveDuplicates<std::vector<std::wstring>>(std::vector<std::wstring> &)
0x18002248a  mov     rax, rbx
0x18002248d  add     rsp, 50h
0x180022491  pop     rbx
0x180022492  retn
```
