# std::deque<ScheduledUmpMessage,std::allocator<ScheduledUmpMessage>>::_Xlen(void)

- ea: `0x18000c27c`
- end: `0x18000c28e`
- name: `?_Xlen@?$deque@UScheduledUmpMessage@@V?$allocator@UScheduledUmpMessage@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18000be34`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c287`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c287`

## pseudocode

```c
void __noreturn std::deque<ScheduledUmpMessage>::_Xlen()
{
  std::_Xlength_error("deque<T> too long");
}

```

## disassembly

```asm
0x18000c27c  sub     rsp, 28h
0x18000c280  lea     rcx, aDequeTTooLong; "deque<T> too long"
0x18000c287  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
