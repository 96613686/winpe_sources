# __report_rangecheckfailure

- ea: `0x180001590`
- end: `0x180001597`
- name: `__report_rangecheckfailure`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180006bcc`
- `0x180006ef4`

## pseudocode

```c
void __noreturn _report_rangecheckfailure()
{
  __fastfail(8u);
}

```

## disassembly

```asm
0x180001590  mov     ecx, 8
0x180001595  int     29h; Win8: RtlFailFast(ecx)
```
