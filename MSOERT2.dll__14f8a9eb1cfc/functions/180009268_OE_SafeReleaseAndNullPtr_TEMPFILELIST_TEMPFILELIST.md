# OE_SafeReleaseAndNullPtr<TEMPFILELIST>(TEMPFILELIST * &)

- ea: `0x180009268`
- end: `0x180009293`
- name: `??$OE_SafeReleaseAndNullPtr@VTEMPFILELIST@@@@YAXAEAPEAVTEMPFILELIST@@@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a420`
- `0x18000b340`

## callees

- `0x180009268`
- `0x180014010`

## pseudocode

```c
_QWORD *__fastcall OE_SafeReleaseAndNullPtr<TEMPFILELIST>(_QWORD *a1)
{
  _QWORD *result; // rax
  __int64 (__fastcall ***v2)(_QWORD, __int64); // rcx

  result = a1;
  v2 = (__int64 (__fastcall ***)(_QWORD, __int64))*a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(**v2)(v2, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180009268  sub     rsp, 28h
0x18000926c  mov     rax, rcx
0x18000926f  mov     rcx, [rcx]
0x180009272  test    rcx, rcx
0x180009275  jz      short loc_18000928E
0x180009277  mov     qword ptr [rax], 0
0x18000927e  mov     edx, 1
0x180009283  mov     rax, [rcx]
0x180009286  mov     rax, [rax]
0x180009289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000928e  add     rsp, 28h
0x180009292  retn
```
