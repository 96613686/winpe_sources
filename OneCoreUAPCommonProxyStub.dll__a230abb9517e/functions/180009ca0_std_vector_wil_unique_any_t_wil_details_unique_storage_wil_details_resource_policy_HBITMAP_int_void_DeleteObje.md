# std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>>::_Xlength(void)

- ea: `0x180009ca0`
- end: `0x180009cb2`
- name: `?_Xlength@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180006a90`
- `0x180006be8`
- `0x180006d28`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180009cab`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180009cab`

## pseudocode

```c
void __noreturn std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x180009ca0  sub     rsp, 28h
0x180009ca4  lea     rcx, aVectorTooLong; "vector too long"
0x180009cab  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
