# sqlite3ExprListDeleteGeneric

- ea: `0x18001bc40`
- end: `0x18001bc53`
- name: `sqlite3ExprListDeleteGeneric`
- size: `19`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `41`
- callee_count: `2`
- tags: ``

## callers

- `0x180001214`
- `0x180001498`
- `0x18000213c`
- `0x180005190`
- `0x180005650`
- `0x18000a754`
- `0x180013ed8`
- `0x18001b4b0`
- `0x18001b818`
- `0x18001bb70`
- `0x18002f6b0`
- `0x1800504a8`
- `0x180051740`
- `0x180051808`
- `0x1800554f0`
- `0x18005e21c`
- `0x18005e9f0`
- `0x180060370`
- `0x1800635fc`
- `0x1800643e0`
- `0x1800656dc`
- `0x1800658bc`
- `0x180066270`
- `0x180067af4`
- `0x18006af8c`
- `0x18007243c`
- `0x180073198`
- `0x180074a88`
- `0x180076a98`
- `0x180077480`
- `0x18007bb54`
- `0x18007ca00`
- `0x18007f76c`
- `0x180080260`
- `0x18008f33c`
- `0x180091860`
- `0x180091b88`
- `0x18009345c`
- `0x180093bb0`
- `0x18009bf50`
- `0x1800a14d0`

## callees

- `0x18001bc40`
- `0x18001bc5c`

## pseudocode

```c
__int64 __fastcall sqlite3ExprListDeleteGeneric(_QWORD *a1, _DWORD *a2)
{
  __int64 result; // rax

  if ( a2 )
    return exprListDeleteNN(a1, a2);
  return result;
}

```

## disassembly

```asm
0x18001bc40  sub     rsp, 28h
0x18001bc44  test    rdx, rdx
0x18001bc47  jz      short loc_18001BC4E
0x18001bc49  call    exprListDeleteNN
0x18001bc4e  add     rsp, 28h
0x18001bc52  retn
```
