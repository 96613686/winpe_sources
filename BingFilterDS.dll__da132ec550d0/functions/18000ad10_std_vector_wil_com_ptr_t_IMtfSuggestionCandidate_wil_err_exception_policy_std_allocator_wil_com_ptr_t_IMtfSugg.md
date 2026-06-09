# std::vector<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>>::_Xlen(void)

- ea: `0x18000ad10`
- end: `0x18000ad21`
- name: `?_Xlen@?$vector@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@IEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a180`

## callees

- `0x180001ff8`

## pseudocode

```c
void __noreturn std::vector<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>::_Xlen()
{
  std::_Xlength_error("vector<T> too long");
}

```

## disassembly

```asm
0x18000ad10  sub     rsp, 28h
0x18000ad14  lea     rcx, aVectorTTooLong
0x18000ad1b  call    ?_Xlength_error@std@@YAXPEBD@Z
```
