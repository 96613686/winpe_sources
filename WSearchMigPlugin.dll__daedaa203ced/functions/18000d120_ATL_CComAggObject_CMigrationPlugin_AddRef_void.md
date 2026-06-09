# ATL::CComAggObject<CMigrationPlugin>::AddRef(void)

- ea: `0x18000d120`
- end: `0x18000d149`
- name: `?AddRef@?$CComAggObject@VCMigrationPlugin@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d120`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMigrationPlugin>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x18000d120  mov     r9d, 7FFFFFFFh
0x18000d126  jmp     short loc_18000D136
0x18000d128  lea     edx, [r8+1]
0x18000d12c  mov     eax, r8d
0x18000d12f  lock cmpxchg [rcx+8], edx
0x18000d134  jz      short loc_18000D141
0x18000d136  mov     r8d, [rcx+8]
0x18000d13a  cmp     r8d, r9d
0x18000d13d  jnz     short loc_18000D128
0x18000d13f  jmp     short loc_18000D145
0x18000d141  lea     r9d, [r8+1]
0x18000d145  mov     eax, r9d
0x18000d148  retn
```
