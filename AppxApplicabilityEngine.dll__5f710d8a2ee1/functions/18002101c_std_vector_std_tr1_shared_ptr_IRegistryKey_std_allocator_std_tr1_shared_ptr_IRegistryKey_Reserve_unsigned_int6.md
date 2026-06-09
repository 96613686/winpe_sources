# std::vector<std::tr1::shared_ptr<IRegistryKey>,std::allocator<std::tr1::shared_ptr<IRegistryKey>>>::_Reserve(unsigned __int64)

- ea: `0x18002101c`
- end: `0x180021092`
- name: `?_Reserve@?$vector@V?$shared_ptr@VIRegistryKey@@@tr1@std@@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@3@@std@@IEAAX_K@Z`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800211a8`

## callees

- `0x180011b84`
- `0x18002101c`
- `0x18002136c`

## pseudocode

```c
unsigned __int64 __fastcall std::vector<std::tr1::shared_ptr<IRegistryKey>>::_Reserve(__int64 a1)
{
  unsigned __int64 result; // rax
  unsigned __int64 v2; // rdx
  unsigned __int64 v3; // r9
  unsigned __int64 v4; // r8

  result = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 4;
  if ( result > 0xFFFFFFFFFFFFFFELL )
    std::_Xlength_error("vector<T> too long");
  v2 = result + 1;
  v3 = (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 4;
  if ( result + 1 > v3 )
  {
    v4 = 0;
    if ( 0xFFFFFFFFFFFFFFFLL - (v3 >> 1) >= v3 )
      v4 = v3 + (v3 >> 1);
    if ( v4 >= v2 )
      v2 = v4;
    return std::vector<std::tr1::shared_ptr<IRegistryKey>>::reserve((const char **)a1, v2);
  }
  return result;
}

```

## disassembly

```asm
0x18002101c  sub     rsp, 28h
0x180021020  mov     rax, [rcx+8]
0x180021024  mov     r10, rcx
0x180021027  sub     rax, [rcx]
0x18002102a  mov     rcx, 0FFFFFFFFFFFFFFEh
0x180021034  sar     rax, 4
0x180021038  cmp     rax, rcx
0x18002103b  jbe     short loc_18002104A
0x18002103d  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x180021044  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002104a  mov     r9, [r10+10h]
0x18002104e  lea     rdx, [rax+1]
0x180021052  sub     r9, [r10]
0x180021055  sar     r9, 4
0x180021059  cmp     rdx, r9
0x18002105c  jbe     short loc_18002108D
0x18002105e  xor     r8d, r8d
0x180021061  mov     rax, r9
0x180021064  shr     rax, 1
0x180021067  mov     rcx, 0FFFFFFFFFFFFFFFh
0x180021071  sub     rcx, rax
0x180021074  add     rax, r9
0x180021077  cmp     rcx, r9
0x18002107a  mov     rcx, r10
0x18002107d  cmovnb  r8, rax
0x180021081  cmp     r8, rdx
0x180021084  cmovnb  rdx, r8
0x180021088  call    ?reserve@?$vector@V?$shared_ptr@VIRegistryKey@@@tr1@std@@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@3@@std@@QEAAX_K@Z; std::vector<std::tr1::shared_ptr<IRegistryKey>>::reserve(unsigned __int64)
0x18002108d  add     rsp, 28h
0x180021091  retn
```
