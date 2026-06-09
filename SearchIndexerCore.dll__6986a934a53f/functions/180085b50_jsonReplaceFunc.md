# jsonReplaceFunc

- ea: `0x180085b50`
- end: `0x180085b7e`
- name: `jsonReplaceFunc`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180084384`
- `0x180085b50`
- `0x180087bc4`

## string_xrefs

- `0x180085b5e`: `replace`

## pseudocode

```c
__int64 __fastcall jsonReplaceFunc(__int64 a1, int a2, __int64 *a3)
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
0x180085b50  sub     rsp, 28h
0x180085b54  cmp     edx, 1
0x180085b57  jl      short loc_180085B79
0x180085b59  test    dl, 1
0x180085b5c  jnz     short loc_180085B6E
0x180085b5e  lea     rdx, aReplace; "replace"
0x180085b65  add     rsp, 28h
0x180085b69  jmp     jsonWrongNumArgs
0x180085b6e  mov     r9d, 2
0x180085b74  call    jsonInsertIntoBlob
0x180085b79  add     rsp, 28h
0x180085b7d  retn
```
