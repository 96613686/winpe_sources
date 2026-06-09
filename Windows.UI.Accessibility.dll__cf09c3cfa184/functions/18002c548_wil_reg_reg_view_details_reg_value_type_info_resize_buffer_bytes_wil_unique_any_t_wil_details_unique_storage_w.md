# wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)

- ea: `0x18002c548`
- end: `0x18002c5c4`
- name: `?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@K@Z`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18002a96c`

## callees

- `0x18000be1c`
- `0x18002aa2c`
- `0x18002aeb8`
- `0x18002c4a0`
- `0x18002c548`

## string_xrefs

- `0x18002c57a`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(
        char **a1,
        unsigned int a2,
        __int64 a3,
        const char *a4)
{
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // r8
  unsigned int v7; // ebx
  void *v9[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = (unsigned __int64)a2 >> 1;
  v6 = v5 - 1;
  if ( !v5 )
    v6 = 0;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    v9,
    *a1,
    v6,
    a4);
  if ( v9[0] )
  {
    if ( a1 != (char **)v9 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        (void **)a1,
        v9[0]);
      v9[0] = 0;
    }
    v7 = 0;
  }
  else
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32C,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
      (const char *)0x8007000ELL,
      0);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v9);
  return v7;
}

```

## disassembly

```asm
0x18002c548  push    rbx
0x18002c54a  sub     rsp, 30h
0x18002c54e  mov     eax, edx
0x18002c550  mov     rbx, rcx
0x18002c553  mov     rdx, [rcx]
0x18002c556  lea     rcx, [rsp+38h+var_18]
0x18002c55b  shr     rax, 1
0x18002c55e  lea     r8, [rax-1]
0x18002c562  cmovz   r8, rax
0x18002c566  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002c56b  mov     rdx, [rsp+38h+var_18]
0x18002c570  test    rdx, rdx
0x18002c573  jnz     short loc_18002C595
0x18002c575  mov     rcx, [rsp+38h]; this
0x18002c57a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c581  mov     ebx, 8007000Eh
0x18002c586  mov     edx, 32Ch; void *
0x18002c58b  mov     r9d, ebx; char *
0x18002c58e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c593  jmp     short loc_18002C5B2
0x18002c595  lea     rax, [rsp+38h+var_18]
0x18002c59a  cmp     rbx, rax
0x18002c59d  jz      short loc_18002C5B0
0x18002c59f  mov     rcx, rbx
0x18002c5a2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002c5a7  mov     [rsp+38h+var_18], 0
0x18002c5b0  xor     ebx, ebx
0x18002c5b2  lea     rcx, [rsp+38h+var_18]
0x18002c5b7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c5bc  mov     eax, ebx
0x18002c5be  add     rsp, 30h
0x18002c5c2  pop     rbx
0x18002c5c3  retn
```
