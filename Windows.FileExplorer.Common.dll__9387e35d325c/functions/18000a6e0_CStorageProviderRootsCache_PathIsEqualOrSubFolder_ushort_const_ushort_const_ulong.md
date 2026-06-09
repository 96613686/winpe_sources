# CStorageProviderRootsCache::_PathIsEqualOrSubFolder(ushort const *,ushort const *,ulong *)

- ea: `0x18000a6e0`
- end: `0x18000a79e`
- name: `?_PathIsEqualOrSubFolder@CStorageProviderRootsCache@@AEAA_NPEBG0PEAK@Z`
- size: `190`
- prototype: `bool(CStorageProviderRootsCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800083f0`
- `0x18000a058`
- `0x18000a130`
- `0x1800610c8`

## callees

- `0x18000a030`
- `0x18000a6e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000a74d`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000a76d`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000a74d`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000a76d`
- `Windows.Storage!__imp_PathComparePaths` at `0x18000a727`
- `Windows.Storage!__imp_PathComparePaths` at `0x18000a727`

## pseudocode

```c
bool __fastcall CStorageProviderRootsCache::_PathIsEqualOrSubFolder(
        CStorageProviderRootsCache *this,
        wil *a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // rbx
  unsigned __int64 v6; // rax
  unsigned __int16 *v7; // rsi
  unsigned int v9; // eax
  const unsigned __int16 *v11; // r14
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // rdx

  v4 = -1;
  v6 = -1;
  v7 = a3;
  do
    ++v6;
  while ( a3[v6] );
  if ( v6 >= 6 )
  {
    v11 = a3 + 4;
    if ( (unsigned int)_o_iswalpha(a3[4]) )
    {
      if ( v7[5] == 58 && wil::is_extended_length_path((wil *)v7, v12) )
        v7 = (unsigned __int16 *)v11;
    }
  }
  do
    ++v4;
  while ( *((_WORD *)a2 + v4) );
  if ( v4 >= 6
    && (unsigned int)_o_iswalpha(*((unsigned __int16 *)a2 + 4))
    && *((_WORD *)a2 + 5) == 58
    && wil::is_extended_length_path(a2, v13) )
  {
    a2 = (wil *)((char *)a2 + 8);
  }
  v9 = PathComparePaths(a2, v7);
  *a4 = v9;
  return (v9 & 0xE) != 0;
}

```

## disassembly

```asm
0x18000a6e0  push    rbx
0x18000a6e2  push    rsi
0x18000a6e3  push    rdi
0x18000a6e4  push    r15
0x18000a6e6  sub     rsp, 28h
0x18000a6ea  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a6f1  mov     r15, r9
0x18000a6f4  mov     rax, rbx
0x18000a6f7  mov     rsi, r8
0x18000a6fa  mov     rdi, rdx
0x18000a6fd  nop     dword ptr [rax]
0x18000a700  inc     rax
0x18000a703  cmp     word ptr [r8+rax*2], 0
0x18000a709  jnz     short loc_18000A700
0x18000a70b  cmp     rax, 6
0x18000a70f  jnb     short loc_18000A73F
0x18000a711  inc     rbx
0x18000a714  cmp     word ptr [rdi+rbx*2], 0
0x18000a719  jnz     short loc_18000A711
0x18000a71b  cmp     rbx, 6
0x18000a71f  jnb     short loc_18000A765
0x18000a721  mov     rdx, rsi
0x18000a724  mov     rcx, rdi
0x18000a727  call    cs:__imp_PathComparePaths
0x18000a72d  test    al, 0Eh
0x18000a72f  mov     [r15], eax
0x18000a732  setnz   al
0x18000a735  add     rsp, 28h
0x18000a739  pop     r15
0x18000a73b  pop     rdi
0x18000a73c  pop     rsi
0x18000a73d  pop     rbx
0x18000a73e  retn
0x18000a73f  movzx   ecx, word ptr [r8+8]
0x18000a744  mov     [rsp+48h+arg_0], r14
0x18000a749  lea     r14, [r8+8]
0x18000a74d  call    cs:__imp__o_iswalpha
0x18000a753  test    eax, eax
0x18000a755  jz      short loc_18000A75E
0x18000a757  cmp     word ptr [rsi+0Ah], 3Ah ; ':'
0x18000a75c  jz      short loc_18000A78E
0x18000a75e  mov     r14, [rsp+48h+arg_0]
0x18000a763  jmp     short loc_18000A711
0x18000a765  movzx   ecx, word ptr [rdi+8]
0x18000a769  lea     rbx, [rdi+8]
0x18000a76d  call    cs:__imp__o_iswalpha
0x18000a773  test    eax, eax
0x18000a775  jz      short loc_18000A721
0x18000a777  cmp     word ptr [rdi+0Ah], 3Ah ; ':'
0x18000a77c  jnz     short loc_18000A721
0x18000a77e  mov     rcx, rdi; this
0x18000a781  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x18000a786  test    al, al
0x18000a788  cmovnz  rdi, rbx
0x18000a78c  jmp     short loc_18000A721
0x18000a78e  mov     rcx, rsi; this
0x18000a791  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x18000a796  test    al, al
0x18000a798  cmovnz  rsi, r14
0x18000a79c  jmp     short loc_18000A75E
```
