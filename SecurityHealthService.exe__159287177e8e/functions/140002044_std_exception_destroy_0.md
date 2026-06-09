# __std_exception_destroy_0

- ea: `0x140002044`
- end: `0x14000204a`
- name: `__std_exception_destroy_0`
- size: `6`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140008394`
- `0x1400086d0`
- `0x14000d614`
- `0x14000d640`
- `0x14000e4c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_exception_destroy` at `0x140002044`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall _std_exception_destroy_0(__int64 a1)
{
  return __std_exception_destroy(a1);
}

```

## disassembly

```asm
0x140002044  jmp     cs:__imp___std_exception_destroy
```
