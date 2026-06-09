# jsonReplaceFunc

- ea: `0x180068ae0`
- end: `0x180068b0e`
- name: `jsonReplaceFunc`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180067314`
- `0x180068ae0`
- `0x18006ab94`

## string_xrefs

- `0x180068aee`: `replace`

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
0x180068ae0  sub     rsp, 28h
0x180068ae4  cmp     edx, 1
0x180068ae7  jl      short loc_180068B09
0x180068ae9  test    dl, 1
0x180068aec  jnz     short loc_180068AFE
0x180068aee  lea     rdx, aReplace; "replace"
0x180068af5  add     rsp, 28h
0x180068af9  jmp     jsonWrongNumArgs
0x180068afe  mov     r9d, 2
0x180068b04  call    jsonInsertIntoBlob
0x180068b09  add     rsp, 28h
0x180068b0d  retn
```
