# jsonReplaceFunc

- ea: `0x180076940`
- end: `0x18007696e`
- name: `jsonReplaceFunc`
- size: `46`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180075144`
- `0x180076940`
- `0x1800789b4`

## string_xrefs

- `0x18007694e`: `replace`

## pseudocode

```c
__int64 __fastcall jsonReplaceFunc(__int64 a1, int a2, _QWORD *a3)
{
  __int64 result; // rax

  if ( a2 >= 1 )
  {
    if ( (a2 & 1) != 0 )
      return jsonInsertIntoBlob(a1, a2, a3, 2);
    else
      return jsonWrongNumArgs(a1, "replace");
  }
  return result;
}

```

## disassembly

```asm
0x180076940  sub     rsp, 28h
0x180076944  cmp     edx, 1
0x180076947  jl      short loc_180076969
0x180076949  test    dl, 1
0x18007694c  jnz     short loc_18007695E
0x18007694e  lea     rdx, aReplace; "replace"
0x180076955  add     rsp, 28h
0x180076959  jmp     jsonWrongNumArgs
0x18007695e  mov     r9d, 2
0x180076964  call    jsonInsertIntoBlob
0x180076969  add     rsp, 28h
0x18007696d  retn
```
