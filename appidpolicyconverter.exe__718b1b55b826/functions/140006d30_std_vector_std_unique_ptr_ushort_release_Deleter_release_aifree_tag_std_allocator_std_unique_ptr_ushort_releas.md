# std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>,std::allocator<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>>::_Reserve(unsigned __int64)

- ea: `0x140006d30`
- end: `0x140006dad`
- name: `?_Reserve@?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@std@@IEAAX_K@Z`
- size: `125`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006f14`

## callees

- `0x140006ac8`
- `0x140006d30`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140006d73`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140006d73`

## pseudocode

```c
__int64 __fastcall std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>::_Reserve(
        __int64 a1)
{
  __int64 v2; // rdx
  __int64 result; // rax
  __int64 v4; // rdx
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  result = (*(_QWORD *)(a1 + 16) - v2) >> 3;
  if ( !result )
  {
    v4 = (v2 - *(_QWORD *)a1) >> 3;
    if ( v4 == 0x1FFFFFFFFFFFFFFFLL )
      std::_Xlength_error("vector<T> too long");
    v5 = v4 + 1;
    v6 = (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3;
    v7 = 0;
    if ( 0x1FFFFFFFFFFFFFFFLL - (v6 >> 1) >= v6 )
      v7 = v6 + (v6 >> 1);
    if ( v7 >= v5 )
      v5 = v7;
    return (__int64)std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>::_Reallocate(
                      (__int64 **)a1,
                      v5);
  }
  return result;
}

```

## disassembly

```asm
0x140006d30  sub     rsp, 28h
0x140006d34  mov     r9, [rcx+10h]
0x140006d38  mov     r8, rcx
0x140006d3b  mov     rdx, [rcx+8]
0x140006d3f  mov     rax, r9
0x140006d42  sub     rax, rdx
0x140006d45  sar     rax, 3
0x140006d49  cmp     rax, 1
0x140006d4d  jnb     short loc_140006DA8
0x140006d4f  sub     rdx, [rcx]
0x140006d52  mov     r10, 1FFFFFFFFFFFFFFFh
0x140006d5c  sar     rdx, 3
0x140006d60  mov     rax, r10
0x140006d63  sub     rax, rdx
0x140006d66  cmp     rax, 1
0x140006d6a  jnb     short loc_140006D7A
0x140006d6c  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x140006d73  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140006d7a  sub     r9, [rcx]
0x140006d7d  inc     rdx
0x140006d80  sar     r9, 3
0x140006d84  xor     ecx, ecx
0x140006d86  mov     rax, r9
0x140006d89  shr     rax, 1
0x140006d8c  sub     r10, rax
0x140006d8f  add     rax, r9
0x140006d92  cmp     r10, r9
0x140006d95  cmovnb  rcx, rax
0x140006d99  cmp     rcx, rdx
0x140006d9c  cmovnb  rdx, rcx
0x140006da0  mov     rcx, r8
0x140006da3  call    ?_Reallocate@?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>::_Reallocate(unsigned __int64)
0x140006da8  add     rsp, 28h
0x140006dac  retn
```
