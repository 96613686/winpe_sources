# Windows::FileSystem::Expand(std::filesystem::path const &)

- ea: `0x180048268`
- end: `0x1800482e1`
- name: `?Expand@FileSystem@Windows@@QEAA?AVpath@filesystem@std@@AEBV345@@Z`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800482e8`

## callees

- `0x18002ebe8`
- `0x18002fe60`
- `0x180048268`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800482cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800482cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::FileSystem::Expand(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v4; // rax
  LPVOID pv[2]; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v7[3]; // [rsp+30h] [rbp-18h] BYREF

  pv[0] = 0;
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
    pv,
    a3);
  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)pv[0] + v4) );
  v7[0] = pv[0];
  v7[1] = v4;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(a2, v7);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return a2;
}

```

## disassembly

```asm
0x180048268  mov     [rsp+arg_0], rbx
0x18004826d  push    rdi
0x18004826e  sub     rsp, 40h
0x180048272  mov     rbx, rdx
0x180048275  mov     [rsp+48h+pv], rdx
0x18004827a  xor     edi, edi
0x18004827c  mov     [rsp+48h+pv], rdi
0x180048281  cmp     qword ptr [r8+18h], 7
0x180048286  jbe     short loc_18004828B
0x180048288  mov     r8, [r8]
0x18004828b  mov     rdx, r8
0x18004828e  lea     rcx, [rsp+48h+pv]
0x180048293  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x180048298  nop
0x180048299  mov     rcx, [rsp+48h+pv]
0x18004829e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800482a2  inc     rax
0x1800482a5  cmp     [rcx+rax*2], di
0x1800482a9  jnz     short loc_1800482A2
0x1800482ab  mov     [rsp+48h+var_18], rcx
0x1800482b0  mov     [rsp+48h+var_10], rax
0x1800482b5  lea     rdx, [rsp+48h+var_18]
0x1800482ba  mov     rcx, rbx
0x1800482bd  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x1800482c2  nop
0x1800482c3  mov     rcx, [rsp+48h+pv]; pv
0x1800482c8  test    rcx, rcx
0x1800482cb  jz      short loc_1800482D3
0x1800482cd  call    cs:__imp_CoTaskMemFree
0x1800482d3  mov     rax, rbx
0x1800482d6  mov     rbx, [rsp+48h+arg_0]
0x1800482db  add     rsp, 40h
0x1800482df  pop     rdi
0x1800482e0  retn
```
