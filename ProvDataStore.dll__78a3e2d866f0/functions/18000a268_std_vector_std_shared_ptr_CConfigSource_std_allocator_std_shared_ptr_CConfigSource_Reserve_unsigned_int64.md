# std::vector<std::shared_ptr<CConfigSource>,std::allocator<std::shared_ptr<CConfigSource>>>::_Reserve(unsigned __int64)

- ea: `0x18000a268`
- end: `0x18000a2dd`
- name: `?_Reserve@?$vector@V?$shared_ptr@VCConfigSource@@@std@@V?$allocator@V?$shared_ptr@VCConfigSource@@@std@@@2@@std@@IEAAX_K@Z`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009bd0`
- `0x18000b31c`

## callees

- `0x18000a1c4`
- `0x18000a268`
- `0x18000a398`

## pseudocode

```c
__int64 __fastcall std::vector<std::shared_ptr<CConfigSource>>::_Reserve(_QWORD *a1)
{
  __int64 v2; // rdx
  __int64 result; // rax
  __int64 v4; // rdx
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rcx

  v2 = a1[1];
  result = (a1[2] - v2) >> 4;
  if ( !result )
  {
    v4 = (v2 - *a1) >> 4;
    if ( v4 == 0xFFFFFFFFFFFFFFFLL )
      std::vector<std::shared_ptr<CConfigSource>>::_Xlen(a1, 0xFFFFFFFFFFFFFFFLL, a1);
    v5 = v4 + 1;
    v6 = (__int64)(a1[2] - *a1) >> 4;
    v7 = 0;
    if ( 0xFFFFFFFFFFFFFFFLL - (v6 >> 1) >= v6 )
      v7 = v6 + (v6 >> 1);
    if ( v7 >= v5 )
      v5 = v7;
    return (__int64)std::vector<std::shared_ptr<CConfigSet>>::_Reallocate((__int64)a1, v5);
  }
  return result;
}

```

## disassembly

```asm
0x18000a268  sub     rsp, 28h
0x18000a26c  mov     r9, [rcx+10h]
0x18000a270  mov     r8, rcx
0x18000a273  mov     rdx, [rcx+8]
0x18000a277  mov     rax, r9
0x18000a27a  sub     rax, rdx
0x18000a27d  sar     rax, 4
0x18000a281  cmp     rax, 1
0x18000a285  jnb     short loc_18000A2D2
0x18000a287  sub     rdx, [rcx]
0x18000a28a  mov     r10, 0FFFFFFFFFFFFFFFh
0x18000a294  sar     rdx, 4
0x18000a298  mov     rax, r10
0x18000a29b  sub     rax, rdx
0x18000a29e  cmp     rax, 1
0x18000a2a2  jb      short loc_18000A2D7
0x18000a2a4  sub     r9, [rcx]
0x18000a2a7  inc     rdx
0x18000a2aa  sar     r9, 4
0x18000a2ae  xor     ecx, ecx
0x18000a2b0  mov     rax, r9
0x18000a2b3  shr     rax, 1
0x18000a2b6  sub     r10, rax
0x18000a2b9  add     rax, r9
0x18000a2bc  cmp     r10, r9
0x18000a2bf  cmovnb  rcx, rax
0x18000a2c3  cmp     rcx, rdx
0x18000a2c6  cmovnb  rdx, rcx
0x18000a2ca  mov     rcx, r8
0x18000a2cd  call    ?_Reallocate@?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::shared_ptr<CConfigSet>>::_Reallocate(unsigned __int64)
0x18000a2d2  add     rsp, 28h
0x18000a2d6  retn
0x18000a2d7  call    ?_Xlen@?$vector@V?$shared_ptr@VCConfigSource@@@std@@V?$allocator@V?$shared_ptr@VCConfigSource@@@std@@@2@@std@@IEBAXXZ; std::vector<std::shared_ptr<CConfigSource>>::_Xlen(void)
```
