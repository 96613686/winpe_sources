# ZTraceTestCopyTrace(ushort const *)

- ea: `0x180003560`
- end: `0x180003584`
- name: `?ZTraceTestCopyTrace@@YAXPEBG@Z`
- size: `36`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003560`
- `0x180004010`

## pseudocode

```c
void __fastcall ZTraceTestCopyTrace(const unsigned __int16 *a1)
{
  if ( qword_1800072B8 )
    (*(void (__fastcall **)(ZTracer *, const unsigned __int16 *))(*(_QWORD *)qword_1800072B8 + 32LL))(
      qword_1800072B8,
      a1);
}

```

## disassembly

```asm
0x180003560  sub     rsp, 28h
0x180003564  mov     rdx, rcx
0x180003567  mov     rcx, cs:qword_1800072B8
0x18000356e  test    rcx, rcx
0x180003571  jz      short loc_18000357F
0x180003573  mov     rax, [rcx]
0x180003576  mov     rax, [rax+20h]
0x18000357a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000357f  add     rsp, 28h
0x180003583  retn
```
