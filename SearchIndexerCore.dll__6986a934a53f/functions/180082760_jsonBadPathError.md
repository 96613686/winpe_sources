# jsonBadPathError

- ea: `0x180082760`
- end: `0x1800827b1`
- name: `jsonBadPathError`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800825d0`
- `0x1800834b0`
- `0x180083b70`
- `0x180084384`
- `0x180085a70`
- `0x180087790`

## callees

- `0x1800310a0`
- `0x180041eb0`
- `0x180082760`
- `0x18009d650`
- `0x18009d6d0`

## string_xrefs

- `0x18008276d`: `bad JSON path: %Q`

## pseudocode

```c
__int64 __fastcall jsonBadPathError(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rbx

  result = sqlite3_mprintf("bad JSON path: %Q");
  v3 = result;
  if ( a1 )
  {
    if ( result )
    {
      sqlite3_result_error(a1, result, 0xFFFFFFFFLL);
      sqlite3_free(v3);
    }
    else
    {
      sqlite3_result_error_nomem(a1);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180082760  mov     [rsp+arg_0], rbx
0x180082765  push    rdi
0x180082766  sub     rsp, 20h
0x18008276a  mov     rdi, rcx
0x18008276d  lea     rcx, aBadJsonPathQ; "bad JSON path: %Q"
0x180082774  call    sqlite3_mprintf
0x180082779  mov     rbx, rax
0x18008277c  test    rdi, rdi
0x18008277f  jz      short loc_1800827A6
0x180082781  mov     rcx, rdi
0x180082784  test    rax, rax
0x180082787  jz      short loc_18008279F
0x180082789  or      r8d, 0FFFFFFFFh
0x18008278d  mov     rdx, rax
0x180082790  call    sqlite3_result_error
0x180082795  mov     rcx, rbx
0x180082798  call    sqlite3_free
0x18008279d  jmp     short loc_1800827A4
0x18008279f  call    sqlite3_result_error_nomem
0x1800827a4  xor     eax, eax
0x1800827a6  mov     rbx, [rsp+28h+arg_0]
0x1800827ab  add     rsp, 20h
0x1800827af  pop     rdi
0x1800827b0  retn
```
