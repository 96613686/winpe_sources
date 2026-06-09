# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)

- ea: `0x1400036c0`
- end: `0x1400036f3`
- name: `??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `51`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400021bc`
- `0x140005e44`
- `0x14000812c`

## callees

- `0x1400036c0`
- `0x140008294`

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
0x1400036c0  mov     [rsp+arg_0], rbx
0x1400036c5  push    rdi
0x1400036c6  sub     rsp, 20h
0x1400036ca  mov     rdi, rdx
0x1400036cd  mov     rbx, rcx
0x1400036d0  cmp     rcx, rdx
0x1400036d3  jz      short loc_1400036E4
0x1400036d5  mov     rdx, [rdx]
0x1400036d8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1400036dd  mov     qword ptr [rdi], 0
0x1400036e4  mov     rax, rbx
0x1400036e7  mov     rbx, [rsp+28h+arg_0]
0x1400036ec  add     rsp, 20h
0x1400036f0  pop     rdi
0x1400036f1  retn
```
