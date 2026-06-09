# jsonReturnStringAsBlob

- ea: `0x180076f78`
- end: `0x180077002`
- name: `jsonReturnStringAsBlob`
- size: `138`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180073178`
- `0x180075ef0`
- `0x180076e78`

## callees

- `0x18000a9e0`
- `0x180048d20`
- `0x180068190`
- `0x18006910e`
- `0x180076f78`
- `0x180077320`
- `0x180077a50`
- `0x18008f340`

## pseudocode

```c
__int64 __fastcall jsonReturnStringAsBlob(__int64 *a1)
{
  __int64 v2; // rcx
  __int64 v4; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v5; // [rsp+28h] [rbp-50h]
  __int64 v6; // [rsp+30h] [rbp-48h]
  __int64 v7; // [rsp+38h] [rbp-40h]
  int v8; // [rsp+40h] [rbp-38h]
  char v9; // [rsp+4Fh] [rbp-29h]

  memset_0(&v4, 0, 0x48u);
  jsonStringTerminate(a1);
  v2 = *a1;
  if ( *((_BYTE *)a1 + 33) )
    return sqlite3_result_error_nomem(v2);
  v6 = a1[1];
  v8 = *((_DWORD *)a1 + 6);
  v7 = sqlite3_context_db_handle(v2);
  jsonTranslateTextToBlob((__int64)&v4, 0);
  if ( v9 )
  {
    sqlite3DbFree(v7, v4);
    v2 = *a1;
    return sqlite3_result_error_nomem(v2);
  }
  return sqlite3_result_blob(*a1, v4, v5, sqlite3OomClear);
}

```

## disassembly

```asm
0x180076f78  push    rbx
0x180076f7a  sub     rsp, 70h
0x180076f7e  xor     edx, edx; Val
0x180076f80  mov     rbx, rcx
0x180076f83  lea     rcx, [rsp+78h+var_58]; void *
0x180076f88  lea     r8d, [rdx+48h]; Size
0x180076f8c  call    memset_0
0x180076f91  mov     rcx, rbx
0x180076f94  call    jsonStringTerminate
0x180076f99  cmp     byte ptr [rbx+21h], 0
0x180076f9d  mov     rcx, [rbx]
0x180076fa0  jnz     short loc_180076FE1
0x180076fa2  mov     rax, [rbx+8]
0x180076fa6  mov     [rsp+78h+var_48], rax
0x180076fab  mov     eax, [rbx+18h]
0x180076fae  mov     [rsp+78h+var_38], eax
0x180076fb2  call    sqlite3_context_db_handle
0x180076fb7  xor     edx, edx
0x180076fb9  mov     [rsp+78h+var_40], rax
0x180076fbe  lea     rcx, [rsp+78h+var_58]
0x180076fc3  call    jsonTranslateTextToBlob
0x180076fc8  cmp     [rsp+78h+var_29], 0
0x180076fcd  mov     rdx, [rsp+78h+var_58]
0x180076fd2  jz      short loc_180076FE8
0x180076fd4  mov     rcx, [rsp+78h+var_40]
0x180076fd9  call    sqlite3DbFree
0x180076fde  mov     rcx, [rbx]
0x180076fe1  call    sqlite3_result_error_nomem
0x180076fe6  jmp     short loc_180076FFC
0x180076fe8  mov     r8d, [rsp+78h+var_50]
0x180076fed  lea     r9, sqlite3OomClear
0x180076ff4  mov     rcx, [rbx]
0x180076ff7  call    sqlite3_result_blob
0x180076ffc  add     rsp, 70h
0x180077000  pop     rbx
0x180077001  retn
```
