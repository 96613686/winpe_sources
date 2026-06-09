# std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>,std::allocator<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>>::_Xlength(void)

- ea: `0x18000e134`
- end: `0x18000e146`
- name: `?_Xlength@?$vector@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `5`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18000cd80`
- `0x18000ee58`
- `0x18000f5c8`
- `0x18001187c`
- `0x180013784`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000e13f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000e13f`

## pseudocode

```c
void __noreturn std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x18000e134  sub     rsp, 28h
0x18000e138  lea     rcx, aVectorTooLong; "vector too long"
0x18000e13f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
