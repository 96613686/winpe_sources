# common_refill_and_read_nolock<wchar_t>(__crt_stdio_stream)

- ea: `0x1400157a4`
- end: `0x1400157a9`
- name: `j_??$common_refill_and_read_nolock@_W@@YAHV__crt_stdio_stream@@@Z`
- size: `5`
- prototype: `__int64 __fastcall(FILE *File)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001183c`

## callees

- `0x140015498`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall common_refill_and_read_nolock<wchar_t>(FILE *File)
{
  return ??$common_refill_and_read_nolock@_W@@YAHV__crt_stdio_stream@@@Z(File);
}

```

## disassembly

```asm
0x1400157a4  jmp     ??$common_refill_and_read_nolock@_W@@YAHV__crt_stdio_stream@@@Z
```
