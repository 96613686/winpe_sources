# CoreGlobConfigTraceLogging::Provider(void)

- ea: `0x180016fcc`
- end: `0x180016fe5`
- name: `?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `17`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180016730`
- `0x180016fc0`
- `0x18001997c`
- `0x180019a3c`
- `0x180019afc`
- `0x180019bbc`
- `0x180019c7c`
- `0x180019d3c`
- `0x180019dfc`
- `0x180019f30`
- `0x18001a010`
- `0x18001a240`
- `0x18001a470`
- `0x18001a6a0`
- `0x18001a8d0`
- `0x18001ab00`
- `0x18001ad30`

## callees

- `0x18001e4b0`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall CoreGlobConfigTraceLogging::Provider(__int64 a1)
{
  return *(const struct _tlgProvider_t **)(wil::details::static_lazy<CoreGlobConfigTraceLogging>::get(
                                             a1,
                                             _lambda_7b1e3ad868b1ebacb123ca2244fd53e4_::_lambda_invoker_cdecl_)
                                         + 8);
}

```

## disassembly

```asm
0x180016fcc  sub     rsp, 28h
0x180016fd0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_7b1e3ad868b1ebacb123ca2244fd53e4_@@CA@XZ; _lambda_7b1e3ad868b1ebacb123ca2244fd53e4_::_lambda_invoker_cdecl_(void)
0x180016fd7  call    ?get@?$static_lazy@VCoreGlobConfigTraceLogging@@@details@wil@@QEAAPEAVCoreGlobConfigTraceLogging@@P6AXXZ@Z; wil::details::static_lazy<CoreGlobConfigTraceLogging>::get(void (*)(void))
0x180016fdc  mov     rax, [rax+8]
0x180016fe0  add     rsp, 28h
0x180016fe4  retn
```
