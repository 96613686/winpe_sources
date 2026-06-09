# jsonCacheInsert

- ea: `0x180073a54`
- end: `0x180073b1e`
- name: `jsonCacheInsert`
- size: `202`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18007627c`
- `0x180076e78`

## callees

- `0x18000f720`
- `0x180048d20`
- `0x180073a54`
- `0x180076240`
- `0x18008e890`
- `0x18008f980`
- `0x180099820`

## pseudocode

```c
__int64 __fastcall jsonCacheInsert(__int64 a1, __int64 a2)
{
  _DWORD *auxdata; // rdi
  __int64 v5; // rdi
  __int64 *v6; // rax

  auxdata = (_DWORD *)sqlite3_get_auxdata(a1, 4294537358LL);
  if ( !auxdata )
  {
    v5 = sqlite3_context_db_handle(a1);
    v6 = (__int64 *)sqlite3DbMallocZero(v5, 48);
    if ( !v6 )
      return 7;
    *v6 = v5;
    sqlite3_set_auxdata(a1, 4294537358LL, v6, jsonCacheDeleteGeneric);
    auxdata = (_DWORD *)sqlite3_get_auxdata(a1, 4294537358LL);
    if ( !auxdata )
      return 7;
  }
  if ( (int)auxdata[2] >= 4 )
  {
    jsonParseFree(*((_QWORD *)auxdata + 2));
    memmove_0(auxdata + 4, auxdata + 6, 0x18u);
    auxdata[2] = 3;
  }
  ++*(_DWORD *)(a2 + 36);
  *(_WORD *)(a2 + 50) = 1;
  *(_QWORD *)&auxdata[2 * auxdata[2]++ + 4] = a2;
  return 0;
}

```

## disassembly

```asm
0x180073a54  mov     [rsp+arg_0], rbx
0x180073a59  mov     [rsp+arg_8], rsi
0x180073a5e  push    rdi
0x180073a5f  sub     rsp, 20h
0x180073a63  mov     rsi, rdx
0x180073a66  mov     rbx, rcx
0x180073a69  mov     edx, 0FFF9708Eh
0x180073a6e  call    sqlite3_get_auxdata
0x180073a73  mov     rdi, rax
0x180073a76  test    rax, rax
0x180073a79  jnz     short loc_180073ACE
0x180073a7b  mov     rcx, rbx
0x180073a7e  call    sqlite3_context_db_handle
0x180073a83  mov     edx, 30h ; '0'
0x180073a88  mov     rcx, rax
0x180073a8b  mov     rdi, rax
0x180073a8e  call    sqlite3DbMallocZero
0x180073a93  test    rax, rax
0x180073a96  jz      short loc_180073AC7
0x180073a98  lea     r9, jsonCacheDeleteGeneric
0x180073a9f  mov     [rax], rdi
0x180073aa2  mov     r8, rax
0x180073aa5  mov     edx, 0FFF9708Eh
0x180073aaa  mov     rcx, rbx
0x180073aad  call    sqlite3_set_auxdata
0x180073ab2  mov     edx, 0FFF9708Eh
0x180073ab7  mov     rcx, rbx
0x180073aba  call    sqlite3_get_auxdata
0x180073abf  mov     rdi, rax
0x180073ac2  test    rax, rax
0x180073ac5  jnz     short loc_180073ACE
0x180073ac7  mov     eax, 7
0x180073acc  jmp     short loc_180073B0E
0x180073ace  cmp     dword ptr [rdi+8], 4
0x180073ad2  jl      short loc_180073AF7
0x180073ad4  mov     rcx, [rdi+10h]
0x180073ad8  call    jsonParseFree
0x180073add  lea     rdx, [rdi+18h]; Src
0x180073ae1  mov     r8d, 18h; Size
0x180073ae7  lea     rcx, [rdi+10h]; void *
0x180073aeb  call    memmove_0
0x180073af0  mov     dword ptr [rdi+8], 3
0x180073af7  inc     dword ptr [rsi+24h]
0x180073afa  mov     word ptr [rsi+32h], 1
0x180073b00  movsxd  rax, dword ptr [rdi+8]
0x180073b04  mov     [rdi+rax*8+10h], rsi
0x180073b09  inc     dword ptr [rdi+8]
0x180073b0c  xor     eax, eax
0x180073b0e  mov     rbx, [rsp+28h+arg_0]
0x180073b13  mov     rsi, [rsp+28h+arg_8]
0x180073b18  add     rsp, 20h
0x180073b1c  pop     rdi
0x180073b1d  retn
```
