# std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x1800075f4`
- end: `0x180007628`
- name: `??1_Reallocation_guard@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006d28`

## callees

- `0x1800069ec`
- `0x180006a58`
- `0x1800075f4`

## pseudocode

```c
__int64 __fastcall std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>::_Reallocation_guard::~_Reallocation_guard(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 8) )
  {
    std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>>(
      *(void ***)(a1 + 24),
      *(void ***)(a1 + 32));
    return std::_Deallocate<16>(*(_QWORD *)(a1 + 8), 8LL * *(_QWORD *)(a1 + 16));
  }
  return result;
}

```

## disassembly

```asm
0x1800075f4  push    rbx
0x1800075f6  sub     rsp, 20h
0x1800075fa  cmp     qword ptr [rcx+8], 0
0x1800075ff  mov     rbx, rcx
0x180007602  jz      short loc_180007622
0x180007604  mov     rdx, [rcx+20h]
0x180007608  mov     rcx, [rcx+18h]
0x18000760c  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>> &)
0x180007611  mov     rdx, [rbx+10h]
0x180007615  mov     rcx, [rbx+8]
0x180007619  shl     rdx, 3
0x18000761d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180007622  add     rsp, 20h
0x180007626  pop     rbx
0x180007627  retn
```
