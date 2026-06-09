# GetAppUriHandlerJsonFromWebHost(ushort const *)

- ea: `0x14000be20`
- end: `0x14000bef1`
- name: `?GetAppUriHandlerJsonFromWebHost@@YA?AV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@PEBG@Z`
- size: `209`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000ed9c`

## callees

- `0x140002210`
- `0x1400076b8`
- `0x140007724`
- `0x1400077d0`
- `0x140009d48`
- `0x14000a500`
- `0x14000be20`
- `0x14000c848`
- `0x14000d49c`

## string_xrefs

- `0x14000be78`: `/windows-app-web-link`

## pseudocode

```c
_QWORD *__fastcall GetAppUriHandlerJsonFromWebHost(_QWORD *a1, __int64 a2)
{
  _QWORD *v3; // rbx
  char v4; // al
  _QWORD *v5; // rdx
  __int64 JsonFromUrl; // rax
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // [rsp+28h] [rbp-50h] BYREF
  _QWORD *v11; // [rsp+30h] [rbp-48h]
  char v12[8]; // [rsp+38h] [rbp-40h] BYREF
  _QWORD v13[4]; // [rsp+40h] [rbp-38h] BYREF

  try
  {
    v3 = a1;
    v11 = a1;
    v10 = a2;
    *a1 = 0;
    std::wstring::wstring(v13);
    std::wstring::append(v13, a2);
    std::wstring::append(v13, L"/windows-app-web-link");
    v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(v13);
    v5 = v13;
    if ( v4 )
      v5 = (_QWORD *)v13[0];
    JsonFromUrl = GetJsonFromUrl(v12, v5);
    Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::operator=(v3, JsonFromUrl);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(v12);
    std::wstring::_Tidy_deallocate(v13);
  }
  catch ( ... )
  {
    std::wstring::wstring(v13);
    std::wstring::append(v13, v10);
    std::wstring::append(v13, L"/.well-known");
    std::wstring::append(v13, L"/windows-app-web-link");
    if ( (unsigned __int8)std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(v13) )
      v8 = v13[0];
    v9 = GetJsonFromUrl(&v10, v8);
    Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::operator=(v11, v9);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v10);
    std::wstring::_Tidy_deallocate(v13);
    return v11;
  }
  return v3;
}

```

## disassembly

```asm
0x14000be20  mov     [rsp+arg_10], rbx
0x14000be25  push    rdi
0x14000be26  sub     rsp, 70h
0x14000be2a  mov     rax, cs:__security_cookie
0x14000be31  xor     rax, rsp
0x14000be34  mov     [rsp+78h+var_18], rax
0x14000be39  mov     rdi, rdx
0x14000be3c  mov     rbx, rcx
0x14000be3f  mov     [rsp+78h+var_48], rcx
0x14000be44  mov     [rsp+78h+var_50], rdx
0x14000be49  mov     [rsp+78h+var_58], 0
0x14000be51  mov     qword ptr [rcx], 0
0x14000be58  mov     [rsp+78h+var_58], 1
0x14000be60  lea     rcx, [rsp+78h+var_38]
0x14000be65  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14000be6a  nop
0x14000be6b  mov     rdx, rdi
0x14000be6e  lea     rcx, [rsp+78h+var_38]
0x14000be73  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14000be78  lea     rdx, aWindowsAppWebL; "/windows-app-web-link"
0x14000be7f  lea     rcx, [rsp+78h+var_38]
0x14000be84  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14000be89  lea     rcx, [rsp+78h+var_38]
0x14000be8e  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x14000be93  lea     rdx, [rsp+78h+var_38]
0x14000be98  test    al, al
0x14000be9a  cmovnz  rdx, [rsp+78h+var_38]
0x14000bea0  lea     rcx, [rsp+78h+var_40]
0x14000bea5  call    ?GetJsonFromUrl@@YA?AV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@PEBG@Z; GetJsonFromUrl(ushort const *)
0x14000beaa  mov     rdx, rax
0x14000bead  mov     rcx, rbx
0x14000beb0  call    ??4?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::operator=(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray> &&)
0x14000beb5  lea     rcx, [rsp+78h+var_40]
0x14000beba  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000bebf  nop
0x14000bec0  lea     rcx, [rsp+78h+var_38]
0x14000bec5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000beca  nop
0x14000becb  jmp     short loc_14000BED2
0x14000becd  mov     rbx, [rsp+78h+var_48]
0x14000bed2  mov     rax, rbx
0x14000bed5  mov     rcx, [rsp+78h+var_18]
0x14000beda  xor     rcx, rsp; StackCookie
0x14000bedd  call    __security_check_cookie
0x14000bee2  mov     rbx, [rsp+78h+arg_10]
0x14000beea  add     rsp, 70h
0x14000beee  pop     rdi
0x14000beef  retn
```
