# jsonBadPathError

- ea: `0x1800734f0`
- end: `0x180073541`
- name: `jsonBadPathError`
- size: `81`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180073360`
- `0x180074260`
- `0x180074920`
- `0x180075144`
- `0x180076860`
- `0x180078580`

## callees

- `0x180001110`
- `0x18000aac0`
- `0x180068190`
- `0x1800734f0`
- `0x18008f3f0`

## string_xrefs

- `0x1800734fd`: `bad JSON path: %Q`

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
0x1800734f0  mov     [rsp+arg_0], rbx
0x1800734f5  push    rdi
0x1800734f6  sub     rsp, 20h
0x1800734fa  mov     rdi, rcx
0x1800734fd  lea     rcx, aBadJsonPathQ; "bad JSON path: %Q"
0x180073504  call    sqlite3_mprintf
0x180073509  mov     rbx, rax
0x18007350c  test    rdi, rdi
0x18007350f  jz      short loc_180073536
0x180073511  mov     rcx, rdi
0x180073514  test    rax, rax
0x180073517  jz      short loc_18007352F
0x180073519  or      r8d, 0FFFFFFFFh
0x18007351d  mov     rdx, rax
0x180073520  call    sqlite3_result_error
0x180073525  mov     rcx, rbx
0x180073528  call    sqlite3_free
0x18007352d  jmp     short loc_180073534
0x18007352f  call    sqlite3_result_error_nomem
0x180073534  xor     eax, eax
0x180073536  mov     rbx, [rsp+28h+arg_0]
0x18007353b  add     rsp, 20h
0x18007353f  pop     rdi
0x180073540  retn
```
