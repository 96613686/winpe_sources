# _o___std_exception_copy_0

- ea: `0x1800032f6`
- end: `0x1800032fc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x180004b60`
- `0x180008110`
- `0x180008160`
- `0x1800081b0`
- `0x180009460`
- `0x18000963c`
- `0x18001139c`
- `0x180011560`
- `0x1800115a4`
- `0x180011600`
- `0x180017d48`
- `0x180021344`
- `0x1800214a4`
- `0x1800215a0`
- `0x1800217d0`
- `0x180021814`
- `0x180021874`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800032f6`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy_0()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x1800032f6  jmp     cs:__imp__o___std_exception_copy
```
