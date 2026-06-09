# std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>::operator()<ulong>(ulong const &)

- ea: `0x18000f91c`
- end: `0x18000f94c`
- name: `??$?RK@?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@QEBA_KAEBK@Z`
- size: `48`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fe60`
- `0x180010fa4`
- `0x180011188`

## callees

- `0x18000f91c`

## pseudocode

```c
__int64 __fastcall std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>::operator()<unsigned long>(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rcx
  unsigned __int64 i; // r8
  __int64 v4; // rax

  v2 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
  {
    v4 = *(unsigned __int8 *)(a2 + i);
    v2 = 0x100000001B3LL * (v4 ^ v2);
  }
  return v2;
}

```

## disassembly

```asm
0x18000f91c  mov     rcx, 0CBF29CE484222325h
0x18000f926  xor     r8d, r8d
0x18000f929  movzx   eax, byte ptr [rdx+r8]
0x18000f92e  mov     r9, 100000001B3h
0x18000f938  xor     rcx, rax
0x18000f93b  inc     r8
0x18000f93e  imul    rcx, r9
0x18000f942  cmp     r8, 4
0x18000f946  jb      short loc_18000F929
0x18000f948  mov     rax, rcx
0x18000f94b  retn
```
