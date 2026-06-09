# Win32FileSystem::GetInputDataPath(void)

- ea: `0x18004dc40`
- end: `0x18004dd24`
- name: `?GetInputDataPath@Win32FileSystem@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `228`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001ee7c`
- `0x1800202e4`
- `0x18004dc40`
- `0x180054bc0`
- `0x180061320`
- `0x180091c54`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dcbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dcbb`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18004dc98`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18004dc98`

## pseudocode

```c
__int64 __fastcall Win32FileSystem::GetInputDataPath(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  PWSTR ppszPath[2]; // [rsp+20h] [rbp-19h] BYREF
  _BYTE v6[32]; // [rsp+30h] [rbp-9h] BYREF
  KNOWNFOLDERID rfid; // [rsp+50h] [rbp+17h] BYREF
  _BYTE v8[32]; // [rsp+60h] [rbp+27h] BYREF

  ppszPath[0] = 0;
  rfid.Data1 = 676772115;
  *(_DWORD *)&rfid.Data2 = 1285386629;
  *(_DWORD *)rfid.Data4 = 312003738;
  *(_DWORD *)&rfid.Data4[4] = 339519593;
  if ( SHGetKnownFolderPath(&rfid, 0, 0, ppszPath) >= 0 )
  {
    std::wstring::wstring(v8, L"Input");
    v3 = std::wstring::wstring(v6, ppszPath[0]);
    FileSystem::CombinePaths(a2, v3, v8);
    std::wstring::_Tidy_deallocate(v8);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(ppszPath);
  }
  else
  {
    std::wstring::wstring(a2, &dword_1800D3F14);
    if ( ppszPath[0] )
      CoTaskMemFree(ppszPath[0]);
  }
  return a2;
}

```

## disassembly

```asm
0x18004dc40  mov     [rsp-8+arg_0], rbx
0x18004dc45  push    rbp
0x18004dc46  lea     rbp, [rsp-57h]
0x18004dc4b  sub     rsp, 90h
0x18004dc52  mov     rax, cs:__security_cookie
0x18004dc59  xor     rax, rsp
0x18004dc5c  mov     [rbp+57h+var_10], rax
0x18004dc60  mov     rbx, rdx
0x18004dc63  mov     [rbp+57h+ppszPath], rdx
0x18004dc67  mov     [rbp+57h+ppszPath], 0
0x18004dc6f  mov     [rbp+57h+rfid.Data1], 2856B913h
0x18004dc76  mov     dword ptr [rbp+57h+rfid.Data2], 4C9D7185h
0x18004dc7d  mov     dword ptr [rbp+57h+rfid.Data4], 1298CC9Ah
0x18004dc84  mov     dword ptr [rbp+57h+rfid.Data4+4], 143CA869h
0x18004dc8b  lea     r9, [rbp+57h+ppszPath]; ppszPath
0x18004dc8f  xor     r8d, r8d; hToken
0x18004dc92  xor     edx, edx; dwFlags
0x18004dc94  lea     rcx, [rbp+57h+rfid]; rfid
0x18004dc98  call    cs:__imp_SHGetKnownFolderPath
0x18004dc9e  test    eax, eax
0x18004dca0  jns     short loc_18004DCC3
0x18004dca2  lea     rdx, dword_1800D3F14
0x18004dca9  mov     rcx, rbx
0x18004dcac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004dcb1  nop
0x18004dcb2  mov     rcx, [rbp+57h+ppszPath]; pv
0x18004dcb6  test    rcx, rcx
0x18004dcb9  jz      short loc_18004DD04
0x18004dcbb  call    cs:__imp_CoTaskMemFree
0x18004dcc1  jmp     short loc_18004DD04
0x18004dcc3  lea     rdx, aInput; "Input"
0x18004dcca  lea     rcx, [rbp+57h+var_30]
0x18004dcce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004dcd3  nop
0x18004dcd4  mov     rdx, [rbp+57h+ppszPath]
0x18004dcd8  lea     rcx, [rbp+57h+var_60]
0x18004dcdc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004dce1  lea     r8, [rbp+57h+var_30]
0x18004dce5  mov     rdx, rax
0x18004dce8  mov     rcx, rbx
0x18004dceb  call    ?CombinePaths@FileSystem@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@AEBV23@@Z; FileSystem::CombinePaths(std::wstring,std::wstring const &)
0x18004dcf0  nop
0x18004dcf1  lea     rcx, [rbp+57h+var_30]
0x18004dcf5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004dcfa  nop
0x18004dcfb  lea     rcx, [rbp+57h+ppszPath]
0x18004dcff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004dd04  mov     rax, rbx
0x18004dd07  mov     rcx, [rbp+57h+var_10]
0x18004dd0b  xor     rcx, rsp; StackCookie
0x18004dd0e  call    __security_check_cookie
0x18004dd13  mov     rbx, [rsp+90h+arg_0]
0x18004dd1b  add     rsp, 90h
0x18004dd22  pop     rbp
0x18004dd23  retn
```
