# jsonBadPathError

- ea: `0x180065750`
- end: `0x1800657a1`
- name: `jsonBadPathError`
- size: `81`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800655c0`
- `0x180066440`
- `0x180066b00`
- `0x180067314`
- `0x180068a00`
- `0x18006a710`

## callees

- `0x180012470`
- `0x180065750`
- `0x180096550`
- `0x180096df0`
- `0x180096e70`

## string_xrefs

- `0x18006575d`: `bad JSON path: %Q`

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
0x180065750  mov     [rsp+arg_0], rbx
0x180065755  push    rdi
0x180065756  sub     rsp, 20h
0x18006575a  mov     rdi, rcx
0x18006575d  lea     rcx, aBadJsonPathQ; "bad JSON path: %Q"
0x180065764  call    sqlite3_mprintf
0x180065769  mov     rbx, rax
0x18006576c  test    rdi, rdi
0x18006576f  jz      short loc_180065796
0x180065771  mov     rcx, rdi
0x180065774  test    rax, rax
0x180065777  jz      short loc_18006578F
0x180065779  or      r8d, 0FFFFFFFFh
0x18006577d  mov     rdx, rax
0x180065780  call    sqlite3_result_error
0x180065785  mov     rcx, rbx
0x180065788  call    sqlite3_free
0x18006578d  jmp     short loc_180065794
0x18006578f  call    sqlite3_result_error_nomem
0x180065794  xor     eax, eax
0x180065796  mov     rbx, [rsp+28h+arg_0]
0x18006579b  add     rsp, 20h
0x18006579f  pop     rdi
0x1800657a0  retn
```
