# UusState::GetRootFolder(void)

- ea: `0x180009e64`
- end: `0x180009ee7`
- name: `?GetRootFolder@UusState@@SA?AVpath@filesystem@std@@XZ`
- size: `131`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c510`
- `0x180036a04`
- `0x180039904`
- `0x180039ee0`

## callees

- `0x180009e64`
- `0x18000d660`
- `0x1800295e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009ed3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009ed3`

## pseudocode

```c
__int64 __fastcall UusState::GetRootFolder(__int64 a1)
{
  __int64 *v2; // rdx
  __int64 v3; // rdx
  LPVOID pv[2]; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v6[3]; // [rsp+30h] [rbp-18h] BYREF

  pv[0] = 0;
  v2 = &UusState::_subdirStateFolder;
  if ( (unsigned __int64)qword_180063788 > 7 )
    v2 = (__int64 *)UusState::_subdirStateFolder;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
    pv,
    v2);
  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)pv[0] + v3) );
  v6[0] = pv[0];
  v6[1] = v3;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(a1, v6);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return a1;
}

```

## disassembly

```asm
0x180009e64  mov     [rsp+arg_8], rbx
0x180009e69  push    rdi
0x180009e6a  sub     rsp, 40h
0x180009e6e  mov     rbx, rcx
0x180009e71  mov     [rsp+48h+pv], rcx
0x180009e76  xor     edi, edi
0x180009e78  mov     [rsp+48h+pv], rdi
0x180009e7d  lea     rdx, ?_subdirStateFolder@UusState@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusState::_subdirStateFolder
0x180009e84  cmp     cs:qword_180063788, 7
0x180009e8c  cmova   rdx, cs:?_subdirStateFolder@UusState@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusState::_subdirStateFolder
0x180009e94  lea     rcx, [rsp+48h+pv]
0x180009e99  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x180009e9e  nop
0x180009e9f  mov     rcx, [rsp+48h+pv]
0x180009ea4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180009ea8  inc     rdx
0x180009eab  cmp     [rcx+rdx*2], di
0x180009eaf  jnz     short loc_180009EA8
0x180009eb1  mov     [rsp+48h+var_18], rcx
0x180009eb6  mov     [rsp+48h+var_10], rdx
0x180009ebb  lea     rdx, [rsp+48h+var_18]
0x180009ec0  mov     rcx, rbx
0x180009ec3  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180009ec8  nop
0x180009ec9  mov     rcx, [rsp+48h+pv]; pv
0x180009ece  test    rcx, rcx
0x180009ed1  jz      short loc_180009ED9
0x180009ed3  call    cs:__imp_CoTaskMemFree
0x180009ed9  mov     rax, rbx
0x180009edc  mov     rbx, [rsp+48h+arg_8]
0x180009ee1  add     rsp, 40h
0x180009ee5  pop     rdi
0x180009ee6  retn
```
