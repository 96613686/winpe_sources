# Brain::GetPreviewFolder(void)

- ea: `0x1800397cc`
- end: `0x18003984f`
- name: `?GetPreviewFolder@Brain@@CA?AVpath@filesystem@std@@XZ`
- size: `131`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180038884`
- `0x180039858`

## callees

- `0x18000d660`
- `0x1800295e8`
- `0x1800397cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003983b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003983b`

## pseudocode

```c
__int64 __fastcall Brain::GetPreviewFolder(__int64 a1)
{
  __int64 *v2; // rdx
  __int64 v3; // rdx
  LPVOID pv[2]; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v6[3]; // [rsp+30h] [rbp-18h] BYREF

  pv[0] = 0;
  v2 = &Brain::_pathPreviewFolder;
  if ( (unsigned __int64)qword_180063AC8 > 7 )
    v2 = (__int64 *)Brain::_pathPreviewFolder;
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
0x1800397cc  mov     [rsp+arg_8], rbx
0x1800397d1  push    rdi
0x1800397d2  sub     rsp, 40h
0x1800397d6  mov     rbx, rcx
0x1800397d9  mov     [rsp+48h+pv], rcx
0x1800397de  xor     edi, edi
0x1800397e0  mov     [rsp+48h+pv], rdi
0x1800397e5  lea     rdx, ?_pathPreviewFolder@Brain@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Brain::_pathPreviewFolder
0x1800397ec  cmp     cs:qword_180063AC8, 7
0x1800397f4  cmova   rdx, cs:?_pathPreviewFolder@Brain@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Brain::_pathPreviewFolder
0x1800397fc  lea     rcx, [rsp+48h+pv]
0x180039801  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x180039806  nop
0x180039807  mov     rcx, [rsp+48h+pv]
0x18003980c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180039810  inc     rdx
0x180039813  cmp     [rcx+rdx*2], di
0x180039817  jnz     short loc_180039810
0x180039819  mov     [rsp+48h+var_18], rcx
0x18003981e  mov     [rsp+48h+var_10], rdx
0x180039823  lea     rdx, [rsp+48h+var_18]
0x180039828  mov     rcx, rbx
0x18003982b  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180039830  nop
0x180039831  mov     rcx, [rsp+48h+pv]; pv
0x180039836  test    rcx, rcx
0x180039839  jz      short loc_180039841
0x18003983b  call    cs:__imp_CoTaskMemFree
0x180039841  mov     rax, rbx
0x180039844  mov     rbx, [rsp+48h+arg_8]
0x180039849  add     rsp, 40h
0x18003984d  pop     rdi
0x18003984e  retn
```
