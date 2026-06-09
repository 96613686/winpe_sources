# jsonWrongNumArgs

- ea: `0x180087bc4`
- end: `0x180087c01`
- name: `jsonWrongNumArgs`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180085b50`
- `0x1800862e0`

## callees

- `0x1800310a0`
- `0x180041eb0`
- `0x18009d650`

## string_xrefs

- `0x180087bd1`: `json_%s() needs an odd number of arguments`

## pseudocode

```c
__int64 __fastcall jsonWrongNumArgs(__int64 a1, const char *a2)
{
  __int64 v3; // rbx

  v3 = sqlite3_mprintf("json_%s() needs an odd number of arguments", a2);
  sqlite3_result_error(a1, v3, 0xFFFFFFFFLL);
  return sqlite3_free(v3);
}

```

## disassembly

```asm
0x180087bc4  mov     [rsp+arg_0], rbx
0x180087bc9  push    rdi
0x180087bca  sub     rsp, 20h
0x180087bce  mov     rdi, rcx
0x180087bd1  lea     rcx, aJsonSNeedsAnOd; "json_%s() needs an odd number of argume"...
0x180087bd8  call    sqlite3_mprintf
0x180087bdd  or      r8d, 0FFFFFFFFh
0x180087be1  mov     rdx, rax
0x180087be4  mov     rcx, rdi
0x180087be7  mov     rbx, rax
0x180087bea  call    sqlite3_result_error
0x180087bef  mov     rcx, rbx
0x180087bf2  mov     rbx, [rsp+28h+arg_0]
0x180087bf7  add     rsp, 20h
0x180087bfb  pop     rdi
0x180087bfc  jmp     sqlite3_free
```
