# ZTraceEnabledHelper(ZTraceLevel)

- ea: `0x180002f80`
- end: `0x180002fb9`
- name: `?ZTraceEnabledHelper@@YAHW4ZTraceLevel@@@Z`
- size: `57`
- prototype: `_BOOL8 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000308c`

## callees

- `0x180002f80`
- `0x180004010`

## pseudocode

```c
_BOOL8 __fastcall ZTraceEnabledHelper(unsigned int a1)
{
  return dword_1800072B0
      && qword_1800072B8
      && (*(unsigned int (__fastcall **)(ZTracer *, _QWORD))(*(_QWORD *)qword_1800072B8 + 24LL))(qword_1800072B8, a1);
}

```

## disassembly

```asm
0x180002f80  sub     rsp, 28h
0x180002f84  cmp     cs:dword_1800072B0, 0
0x180002f8b  mov     edx, ecx
0x180002f8d  jz      short loc_180002FB2
0x180002f8f  mov     rcx, cs:qword_1800072B8
0x180002f96  test    rcx, rcx
0x180002f99  jz      short loc_180002FB2
0x180002f9b  mov     rax, [rcx]
0x180002f9e  mov     rax, [rax+18h]
0x180002fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa7  test    eax, eax
0x180002fa9  jz      short loc_180002FB2
0x180002fab  mov     eax, 1
0x180002fb0  jmp     short loc_180002FB4
0x180002fb2  xor     eax, eax
0x180002fb4  add     rsp, 28h
0x180002fb8  retn
```
