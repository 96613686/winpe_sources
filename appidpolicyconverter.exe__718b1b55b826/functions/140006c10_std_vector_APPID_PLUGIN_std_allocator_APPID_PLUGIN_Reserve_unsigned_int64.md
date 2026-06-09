# std::vector<APPID_PLUGIN_,std::allocator<APPID_PLUGIN_>>::_Reserve(unsigned __int64)

- ea: `0x140006c10`
- end: `0x140006ca3`
- name: `?_Reserve@?$vector@UAPPID_PLUGIN_@@V?$allocator@UAPPID_PLUGIN_@@@std@@@std@@IEAAX_K@Z`
- size: `147`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140006e60`

## callees

- `0x14000696c`
- `0x140006c10`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140006c65`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140006c65`

## pseudocode

```c
__int64 __fastcall std::vector<APPID_PLUGIN_>::_Reserve(__int64 *a1)
{
  __int64 v2; // rdx
  __int64 result; // rax
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rcx

  v2 = a1[1];
  result = 0x8E38E38E38E38E39uLL * ((a1[2] - v2) >> 2);
  if ( !result )
  {
    v4 = 0x8E38E38E38E38E39uLL * ((v2 - *a1) >> 2);
    if ( v4 == 0x71C71C71C71C71CLL )
      std::_Xlength_error("vector<T> too long");
    v5 = v4 + 1;
    v6 = 0x8E38E38E38E38E39uLL * ((a1[2] - *a1) >> 2);
    v7 = 0;
    if ( 0x71C71C71C71C71CLL - (v6 >> 1) >= v6 )
      v7 = v6 + (v6 >> 1);
    if ( v7 >= v5 )
      v5 = v7;
    return std::vector<APPID_PLUGIN_>::_Reallocate(a1, v5);
  }
  return result;
}

```

## disassembly

```asm
0x140006c10  sub     rsp, 28h
0x140006c14  mov     r8, [rcx+10h]
0x140006c18  mov     r9, rcx
0x140006c1b  mov     rdx, [rcx+8]
0x140006c1f  mov     rax, r8
0x140006c22  sub     rax, rdx
0x140006c25  mov     rcx, 8E38E38E38E38E39h
0x140006c2f  sar     rax, 2
0x140006c33  imul    rax, rcx
0x140006c37  cmp     rax, 1
0x140006c3b  jnb     short loc_140006C9E
0x140006c3d  sub     rdx, [r9]
0x140006c40  mov     r10, 71C71C71C71C71Ch
0x140006c4a  sar     rdx, 2
0x140006c4e  mov     rax, r10
0x140006c51  imul    rdx, rcx
0x140006c55  sub     rax, rdx
0x140006c58  cmp     rax, 1
0x140006c5c  jnb     short loc_140006C6C
0x140006c5e  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x140006c65  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140006c6c  sub     r8, [r9]
0x140006c6f  inc     rdx
0x140006c72  sar     r8, 2
0x140006c76  imul    r8, rcx
0x140006c7a  xor     ecx, ecx
0x140006c7c  mov     rax, r8
0x140006c7f  shr     rax, 1
0x140006c82  sub     r10, rax
0x140006c85  add     rax, r8
0x140006c88  cmp     r10, r8
0x140006c8b  cmovnb  rcx, rax
0x140006c8f  cmp     rcx, rdx
0x140006c92  cmovnb  rdx, rcx
0x140006c96  mov     rcx, r9
0x140006c99  call    ?_Reallocate@?$vector@UAPPID_PLUGIN_@@V?$allocator@UAPPID_PLUGIN_@@@std@@@std@@IEAAX_K@Z; std::vector<APPID_PLUGIN_>::_Reallocate(unsigned __int64)
0x140006c9e  add     rsp, 28h
0x140006ca2  retn
```
