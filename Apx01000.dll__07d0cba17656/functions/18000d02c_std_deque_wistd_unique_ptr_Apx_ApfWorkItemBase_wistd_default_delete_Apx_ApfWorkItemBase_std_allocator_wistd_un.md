# std::deque<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>,std::allocator<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>>>::_Xlen(void)

- ea: `0x18000d02c`
- end: `0x18000d03e`
- name: `?_Xlen@?$deque@V?$unique_ptr@VApfWorkItemBase@Apx@@U?$default_delete@VApfWorkItemBase@Apx@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VApfWorkItemBase@Apx@@U?$default_delete@VApfWorkItemBase@Apx@@@wistd@@@wistd@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ce2c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d037`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d037`

## pseudocode

```c
void __noreturn std::deque<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>>::_Xlen()
{
  std::_Xlength_error("deque<T> too long");
}

```

## disassembly

```asm
0x18000d02c  sub     rsp, 28h
0x18000d030  lea     rcx, aDequeTTooLong; "deque<T> too long"
0x18000d037  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
