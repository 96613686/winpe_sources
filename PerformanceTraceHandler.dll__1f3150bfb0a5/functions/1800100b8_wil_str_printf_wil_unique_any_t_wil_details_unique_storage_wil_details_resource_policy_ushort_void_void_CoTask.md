# wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)

- ea: `0x1800100b8`
- end: `0x180010125`
- name: `??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ`
- size: `109`
- prototype: `_QWORD *(_QWORD *, __int64, ...)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180011e50`
- `0x1800120b8`
- `0x180016a30`
- `0x180016b6c`
- `0x18001874c`

## callees

- `0x1800100b8`
- `0x18001012c`
- `0x180012c40`

## string_xrefs

- `0x180010109`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        __int64 a2,
        ...)
{
  int v3; // eax
  va_list v5; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  *a1 = 0;
  va_copy(v5, va);
  v3 = wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         a1,
         a2,
         &v5);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7F0,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v3,
      1);
  return a1;
}

```

## disassembly

```asm
0x1800100b8  mov     r11, rsp
0x1800100bb  mov     [r11+10h], rdx
0x1800100bf  mov     [r11+8], rcx
0x1800100c3  mov     [r11+18h], r8
0x1800100c7  mov     [r11+20h], r9
0x1800100cb  push    rbx
0x1800100cc  sub     rsp, 30h
0x1800100d0  mov     rbx, rcx
0x1800100d3  mov     [rsp+38h+var_18], 0
0x1800100db  xor     eax, eax
0x1800100dd  mov     [rcx], rax
0x1800100e0  mov     [rsp+38h+var_18], 1; int
0x1800100e8  mov     [r11-10h], rax
0x1800100ec  lea     rax, [r11+18h]
0x1800100f0  mov     [r11-10h], rax
0x1800100f4  lea     r8, [r11-10h]
0x1800100f8  call    ??$str_vprintf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBGAEAPEAD@Z; wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,char * &)
0x1800100fd  test    eax, eax
0x1800100ff  jns     short loc_18001011B
0x180010101  mov     rcx, [rsp+38h]; this
0x180010106  mov     r9d, eax; char *
0x180010109  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010110  mov     edx, 7F0h; void *
0x180010115  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001011b  mov     rax, rbx
0x18001011e  add     rsp, 30h
0x180010122  pop     rbx
0x180010123  retn
```
