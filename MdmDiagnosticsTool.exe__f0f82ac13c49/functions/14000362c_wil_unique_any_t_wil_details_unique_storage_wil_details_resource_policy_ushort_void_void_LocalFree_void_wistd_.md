# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)

- ea: `0x14000362c`
- end: `0x14000365e`
- name: `??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140002168`
- `0x140005b1c`
- `0x140007cf4`

## callees

- `0x14000362c`
- `0x140007e64`

## pseudocode

```c
_QWORD *__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        _QWORD *a1,
        _QWORD *a2)
{
  if ( a1 != a2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a1,
      *a2);
    *a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x14000362c  mov     [rsp+arg_0], rbx
0x140003631  push    rdi
0x140003632  sub     rsp, 20h
0x140003636  mov     rdi, rdx
0x140003639  mov     rbx, rcx
0x14000363c  cmp     rcx, rdx
0x14000363f  jz      short loc_140003650
0x140003641  mov     rdx, [rdx]
0x140003644  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140003649  mov     qword ptr [rdi], 0
0x140003650  mov     rax, rbx
0x140003653  mov     rbx, [rsp+28h+arg_0]
0x140003658  add     rsp, 20h
0x14000365c  pop     rdi
0x14000365d  retn
```
