# jsonWrongNumArgs

- ea: `0x18006ab94`
- end: `0x18006abd1`
- name: `jsonWrongNumArgs`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180068ae0`
- `0x180069270`

## callees

- `0x180012470`
- `0x180096550`
- `0x180096df0`

## string_xrefs

- `0x18006aba1`: `json_%s() needs an odd number of arguments`

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
0x18006ab94  mov     [rsp+arg_0], rbx
0x18006ab99  push    rdi
0x18006ab9a  sub     rsp, 20h
0x18006ab9e  mov     rdi, rcx
0x18006aba1  lea     rcx, aJsonSNeedsAnOd; "json_%s() needs an odd number of argume"...
0x18006aba8  call    sqlite3_mprintf
0x18006abad  or      r8d, 0FFFFFFFFh
0x18006abb1  mov     rdx, rax
0x18006abb4  mov     rcx, rdi
0x18006abb7  mov     rbx, rax
0x18006abba  call    sqlite3_result_error
0x18006abbf  mov     rcx, rbx
0x18006abc2  mov     rbx, [rsp+28h+arg_0]
0x18006abc7  add     rsp, 20h
0x18006abcb  pop     rdi
0x18006abcc  jmp     sqlite3_free
```
