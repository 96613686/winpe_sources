# std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>> &)

- ea: `0x180006a58`
- end: `0x180006a89`
- name: `??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z`
- size: `49`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006d28`
- `0x180006ed4`
- `0x1800075f4`
- `0x180009c50`
- `0x18000a500`

## callees

- `0x180002c84`
- `0x180006a58`

## pseudocode

```c
BOOL __fastcall std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>>(
        void **a1,
        void **a2)
{
  void **v3; // rbx
  BOOL result; // eax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
      result = wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>(v3++);
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x180006a58  cmp     rcx, rdx
0x180006a5b  jz      short locret_180006A88
0x180006a5d  mov     [rsp+arg_0], rbx
0x180006a62  push    rdi
0x180006a63  sub     rsp, 20h
0x180006a67  mov     rdi, rdx
0x180006a6a  mov     rbx, rcx
0x180006a6d  mov     rcx, rbx
0x180006a70  call    ??1?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>(void)
0x180006a75  add     rbx, 8
0x180006a79  cmp     rbx, rdi
0x180006a7c  jnz     short loc_180006A6D
0x180006a7e  mov     rbx, [rsp+28h+arg_0]
0x180006a83  add     rsp, 20h
0x180006a87  pop     rdi
0x180006a88  retn
```
