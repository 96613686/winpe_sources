# OE_SafeReleaseAndNullPtr<CFileStream>(CFileStream * &)

- ea: `0x180001c50`
- end: `0x180001c6f`
- name: `??$OE_SafeReleaseAndNullPtr@VCFileStream@@@@YAXAEAPEAVCFileStream@@@Z`
- size: `31`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e940`
- `0x180011550`
- `0x1800117b0`

## callees

- `0x180001c50`
- `0x180014010`

## pseudocode

```c
_QWORD *__fastcall OE_SafeReleaseAndNullPtr<CFileStream>(_QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180001c50  mov     rax, rcx
0x180001c53  mov     rcx, [rcx]
0x180001c56  test    rcx, rcx
0x180001c59  jz      short locret_180001C6E
0x180001c5b  mov     qword ptr [rax], 0
0x180001c62  mov     rax, [rcx]
0x180001c65  mov     rax, [rax+10h]
0x180001c69  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001c6e  retn
```
