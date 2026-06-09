# wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,ushort const * *)

- ea: `0x18001aeb4`
- end: `0x18001af0c`
- name: `??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGPEAPEBG@Z`
- size: `88`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18001c8cc`
- `0x18001cb1c`
- `0x18001cd30`
- `0x18001cffc`
- `0x18001d224`
- `0x18001d438`
- `0x18001d790`
- `0x18001daa0`
- `0x18001dd30`
- `0x18001dfc0`
- `0x18001e210`

## callees

- `0x180010670`
- `0x18001aeb4`
- `0x18001af14`

## string_xrefs

- `0x18001aef0`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        _QWORD *a1,
        __int64 a2)
{
  int v3; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  v3 = wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         a2,
         a1);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
      (const char *)(unsigned int)v3,
      1);
  return a1;
}

```

## disassembly

```asm
0x18001aeb4  mov     [rsp+arg_0], rcx
0x18001aeb9  push    rbx
0x18001aeba  sub     rsp, 30h
0x18001aebe  mov     rax, rdx
0x18001aec1  mov     rbx, rcx
0x18001aec4  mov     [rsp+38h+var_18], 0
0x18001aecc  xor     ecx, ecx
0x18001aece  mov     [rbx], rcx
0x18001aed1  mov     [rsp+38h+var_18], 1; int
0x18001aed9  mov     rdx, rbx
0x18001aedc  mov     rcx, rax
0x18001aedf  call    ??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAPEBG@Z; wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)
0x18001aee4  test    eax, eax
0x18001aee6  jns     short loc_18001AF02
0x18001aee8  mov     rcx, [rsp+38h]; this
0x18001aeed  mov     r9d, eax; char *
0x18001aef0  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001aef7  mov     edx, 0C1h; void *
0x18001aefc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001af02  mov     rax, rbx
0x18001af05  add     rsp, 30h
0x18001af09  pop     rbx
0x18001af0a  retn
```
