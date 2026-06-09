# wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)

- ea: `0x18000b5f0`
- end: `0x18000b606`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b60c`
- `0x18000b910`
- `0x18000ce40`
- `0x18000d178`

## callees

- `0x18000b5f0`
- `0x18000b63c`

## pseudocode

```c
__int64 __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return wil::details::DestroyThreadPoolWork<0>::Destroy();
  return result;
}

```

## disassembly

```asm
0x18000b5f0  sub     rsp, 28h
0x18000b5f4  mov     rcx, [rcx]
0x18000b5f7  test    rcx, rcx
0x18000b5fa  jz      short loc_18000B601
0x18000b5fc  call    ?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAXPEAU_TP_WORK@@@Z; wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *)
0x18000b601  add     rsp, 28h
0x18000b605  retn
```
