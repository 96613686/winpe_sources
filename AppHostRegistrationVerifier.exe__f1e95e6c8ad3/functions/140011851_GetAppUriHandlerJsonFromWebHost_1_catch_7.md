# _GetAppUriHandlerJsonFromWebHost_::_1_::catch$7

- ea: `0x140011851`
- end: `0x1400118e3`
- name: `_GetAppUriHandlerJsonFromWebHost_::_1_::catch$7`
- size: `146`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400076b8`
- `0x140007724`
- `0x1400077d0`
- `0x140009d48`
- `0x14000a500`
- `0x14000c848`
- `0x14000d49c`

## string_xrefs

- `0x140011885`: `/windows-app-web-link`

## pseudocode

```c
__int64 __fastcall GetAppUriHandlerJsonFromWebHost_::_1_::catch_7(__int64 a1, __int64 a2)
{
  const WCHAR *v3; // rdx
  __int64 *JsonFromUrl; // rax

  std::wstring::wstring(a2 + 64);
  std::wstring::append(a2 + 64, *(_QWORD *)(a2 + 40));
  std::wstring::append(a2 + 64, L"/.well-known");
  std::wstring::append(a2 + 64, L"/windows-app-web-link");
  if ( (unsigned __int8)std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(a2 + 64) )
    v3 = *(const WCHAR **)(a2 + 64);
  JsonFromUrl = (__int64 *)GetJsonFromUrl((const WCHAR *)(a2 + 40), v3);
  Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::operator=(*(__int64 **)(a2 + 48), JsonFromUrl);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease((__int64 *)(a2 + 40));
  std::wstring::_Tidy_deallocate(a2 + 64);
  return 0;
}

```

## disassembly

```asm
0x140011851  mov     [rsp+arg_8], rdx
0x140011856  push    rbp
0x140011857  sub     rsp, 20h
0x14001185b  mov     rbp, rdx
0x14001185e  lea     rcx, [rbp+40h]
0x140011862  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140011867  nop
0x140011868  mov     rdx, [rbp+28h]
0x14001186c  lea     rcx, [rbp+40h]
0x140011870  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x140011875  lea     rdx, aWellKnown; "/.well-known"
0x14001187c  lea     rcx, [rbp+40h]
0x140011880  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x140011885  lea     rdx, aWindowsAppWebL; "/windows-app-web-link"
0x14001188c  lea     rcx, [rbp+40h]
0x140011890  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x140011895  lea     rdx, [rbp+40h]
0x140011899  lea     rcx, [rbp+40h]
0x14001189d  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x1400118a2  test    al, al
0x1400118a4  cmovnz  rdx, [rbp+40h]
0x1400118a9  lea     rcx, [rbp+28h]
0x1400118ad  call    ?GetJsonFromUrl@@YA?AV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@PEBG@Z; GetJsonFromUrl(ushort const *)
0x1400118b2  mov     rdx, rax
0x1400118b5  mov     rcx, [rbp+30h]
0x1400118b9  call    ??4?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::operator=(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray> &&)
0x1400118be  lea     rcx, [rbp+28h]
0x1400118c2  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x1400118c7  nop
0x1400118c8  lea     rcx, [rbp+40h]
0x1400118cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400118d1  nop
0x1400118d2  mov     rax, 0
0x1400118dc  add     rsp, 20h
0x1400118e0  pop     rbp
0x1400118e1  retn
```
