# jsonWrongNumArgs

- ea: `0x1800789b4`
- end: `0x1800789f1`
- name: `jsonWrongNumArgs`
- size: `61`
- prototype: `__int64 __fastcall(__int64, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180076940`
- `0x1800770d0`

## callees

- `0x180001110`
- `0x18000aac0`
- `0x18008f3f0`

## string_xrefs

- `0x1800789c1`: `json_%s() needs an odd number of arguments`

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
0x1800789b4  mov     [rsp+arg_0], rbx
0x1800789b9  push    rdi
0x1800789ba  sub     rsp, 20h
0x1800789be  mov     rdi, rcx
0x1800789c1  lea     rcx, aJsonSNeedsAnOd; "json_%s() needs an odd number of argume"...
0x1800789c8  call    sqlite3_mprintf
0x1800789cd  or      r8d, 0FFFFFFFFh
0x1800789d1  mov     rdx, rax
0x1800789d4  mov     rcx, rdi
0x1800789d7  mov     rbx, rax
0x1800789da  call    sqlite3_result_error
0x1800789df  mov     rcx, rbx
0x1800789e2  mov     rbx, [rsp+28h+arg_0]
0x1800789e7  add     rsp, 20h
0x1800789eb  pop     rdi
0x1800789ec  jmp     sqlite3_free
```
