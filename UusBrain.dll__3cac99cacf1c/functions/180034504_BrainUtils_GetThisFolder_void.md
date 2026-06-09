# BrainUtils::GetThisFolder(void)

- ea: `0x180034504`
- end: `0x18003459a`
- name: `?GetThisFolder@BrainUtils@@SA?AVpath@filesystem@std@@XZ`
- size: `150`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180037064`

## callees

- `0x180026370`
- `0x180028728`
- `0x1800295e8`
- `0x180029644`
- `0x180034504`
- `0x18003e1bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034565`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034565`

## pseudocode

```c
__int64 __fastcall BrainUtils::GetThisFolder(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  struct std::filesystem::path *v4; // rax
  LPVOID pv[2]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v7[2]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v8[40]; // [rsp+40h] [rbp-28h] BYREF

  pv[0] = 0;
  wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(
    pv,
    a2,
    &_ImageBase);
  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)pv[0] + v3) );
  v7[0] = pv[0];
  v7[1] = v3;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v8, v7);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  v4 = std::filesystem::path::remove_filename((std::filesystem::path *)v8);
  std::wstring::wstring(a1, v4);
  std::wstring::_Tidy_deallocate(v8);
  return a1;
}

```

## disassembly

```asm
0x180034504  mov     [rsp+arg_8], rbx
0x180034509  push    rdi
0x18003450a  sub     rsp, 60h
0x18003450e  mov     rbx, rcx
0x180034511  mov     [rsp+68h+pv], rcx
0x180034516  xor     edi, edi
0x180034518  mov     [rsp+68h+pv], rdi
0x18003451d  lea     r8, __ImageBase
0x180034524  lea     rcx, [rsp+68h+pv]
0x180034529  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEAXPEAUHINSTANCE__@@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *)
0x18003452e  nop
0x18003452f  mov     rax, [rsp+68h+pv]
0x180034534  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180034538  inc     rcx
0x18003453b  cmp     [rax+rcx*2], di
0x18003453f  jnz     short loc_180034538
0x180034541  mov     [rsp+68h+var_38], rax
0x180034546  mov     [rsp+68h+var_30], rcx
0x18003454b  lea     rdx, [rsp+68h+var_38]
0x180034550  lea     rcx, [rsp+68h+var_28]
0x180034555  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18003455a  nop
0x18003455b  mov     rcx, [rsp+68h+pv]; pv
0x180034560  test    rcx, rcx
0x180034563  jz      short loc_18003456C
0x180034565  call    cs:__imp_CoTaskMemFree
0x18003456b  nop
0x18003456c  lea     rcx, [rsp+68h+var_28]; this
0x180034571  call    ?remove_filename@path@filesystem@std@@QEAAAEAV123@XZ; std::filesystem::path::remove_filename(void)
0x180034576  mov     rdx, rax
0x180034579  mov     rcx, rbx
0x18003457c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180034581  nop
0x180034582  lea     rcx, [rsp+68h+var_28]
0x180034587  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003458c  mov     rax, rbx
0x18003458f  mov     rbx, [rsp+68h+arg_8]
0x180034594  add     rsp, 60h
0x180034598  pop     rdi
0x180034599  retn
```
