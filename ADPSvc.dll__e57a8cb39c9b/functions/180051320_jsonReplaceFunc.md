# jsonReplaceFunc

- ea: `0x180051320`
- end: `0x18005138b`
- name: `jsonReplaceFunc`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18004f97c`
- `0x180051320`
- `0x18009b4ec`
- `0x1800a98a0`
- `0x1800aa540`

## string_xrefs

- `0x180051337`: `replace`
- `0x18005133e`: `json_%s() needs an odd number of arguments`

## pseudocode

```c
void __fastcall jsonReplaceFunc(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 v7; // rbx

  if ( (int)a2 >= 1 )
  {
    if ( (a2 & 1) != 0 )
    {
      jsonInsertIntoBlob(a1, a2, a3, 2);
    }
    else
    {
      v4 = sqlite3_mprintf("json_%s() needs an odd number of arguments", "replace");
      v5 = *a1;
      LOBYTE(v6) = 1;
      *((_DWORD *)a1 + 9) = 1;
      v7 = v4;
      sqlite3VdbeMemSetStr(v5, v4, -1, v6, -1);
      sqlite3_free(v7);
    }
  }
}

```

## disassembly

```asm
0x180051320  cmp     edx, 1
0x180051323  jl      short locret_18005138A
0x180051325  mov     [rsp+arg_0], rbx
0x18005132a  push    rdi
0x18005132b  sub     rsp, 30h
0x18005132f  mov     rdi, rcx
0x180051332  test    dl, 1
0x180051335  jnz     short loc_180051375
0x180051337  lea     rdx, aReplace; "replace"
0x18005133e  lea     rcx, aJsonSNeedsAnOd; "json_%s() needs an odd number of argume"...
0x180051345  call    sqlite3_mprintf
0x18005134a  mov     rcx, [rdi]
0x18005134d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180051351  mov     r9b, 1
0x180051354  mov     [rsp+38h+var_18], r8
0x180051359  mov     rdx, rax
0x18005135c  mov     dword ptr [rdi+24h], 1
0x180051363  mov     rbx, rax
0x180051366  call    sqlite3VdbeMemSetStr
0x18005136b  mov     rcx, rbx
0x18005136e  call    sqlite3_free
0x180051373  jmp     short loc_180051380
0x180051375  mov     r9d, 2
0x18005137b  call    jsonInsertIntoBlob
0x180051380  mov     rbx, [rsp+38h+arg_0]
0x180051385  add     rsp, 30h
0x180051389  pop     rdi
0x18005138a  retn
```
