# CPlutonTasksHandler::Worker(void)

- ea: `0x180008820`
- end: `0x180008837`
- name: `?Worker@CPlutonTasksHandler@@EEAAJXZ`
- size: `23`
- prototype: `__int64 __fastcall(CPlutonTasksHandler *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800081c8`

## string_xrefs

- `0x180008824`: `PlutonProvision task skipped. Feature is not enabled.`

## pseudocode

```c
__int64 __fastcall CPlutonTasksHandler::Worker(CPlutonTasksHandler *this)
{
  PlutonTasksTrace::TraceLoggingInfo("PlutonProvision task skipped. Feature is not enabled.");
  return 0;
}

```

## disassembly

```asm
0x180008820  sub     rsp, 28h
0x180008824  lea     rcx, aPlutonprovisio
0x18000882b  call    ?TraceLoggingInfo@PlutonTasksTrace@@SAXPEBDZZ
0x180008830  xor     eax, eax
0x180008832  add     rsp, 28h
0x180008836  retn
```
