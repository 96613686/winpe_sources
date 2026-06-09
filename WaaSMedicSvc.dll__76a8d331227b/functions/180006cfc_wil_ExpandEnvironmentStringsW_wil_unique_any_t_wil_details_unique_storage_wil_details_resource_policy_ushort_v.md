# wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)

- ea: `0x180006cfc`
- end: `0x180006d4d`
- name: `??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z`
- size: `81`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000865c`
- `0x18000aa84`

## callees

- `0x180006cfc`
- `0x180006d54`
- `0x18000b258`

## string_xrefs

- `0x180006d3b`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
_QWORD *__fastcall wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        _QWORD *a1)
{
  int v2; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  v2 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         a1,
         a1);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
      (const char *)(unsigned int)v2,
      1);
  return a1;
}

```

## disassembly

```asm
0x180006cfc  mov     [rsp+arg_0], rcx
0x180006d01  push    rbx
0x180006d02  sub     rsp, 30h
0x180006d06  mov     rbx, rcx
0x180006d09  mov     [rsp+38h+var_18], 0
0x180006d11  xor     eax, eax
0x180006d13  mov     [rcx], rax
0x180006d16  mov     [rsp+38h+var_18], 1; int
0x180006d1e  mov     rdx, rcx
0x180006d21  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180006d26  test    eax, eax
0x180006d28  js      short loc_180006D33
0x180006d2a  mov     rax, rbx
0x180006d2d  add     rsp, 30h
0x180006d31  pop     rbx
0x180006d32  retn
0x180006d33  mov     rcx, [rsp+38h]; this
0x180006d38  mov     r9d, eax; char *
0x180006d3b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006d42  mov     edx, 250h; void *
0x180006d47  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
