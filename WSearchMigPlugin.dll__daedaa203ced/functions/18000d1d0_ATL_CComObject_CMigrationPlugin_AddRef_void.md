# ATL::CComObject<CMigrationPlugin>::AddRef(void)

- ea: `0x18000d1d0`
- end: `0x18000d1f9`
- name: `?AddRef@?$CComObject@VCMigrationPlugin@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d200`
- `0x18000d210`
- `0x18000d220`
- `0x18000d230`
- `0x18000d240`

## callees

- `0x18000d1d0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMigrationPlugin>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 48);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 48), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x18000d1d0  mov     r9d, 7FFFFFFFh
0x18000d1d6  jmp     short loc_18000D1E6
0x18000d1d8  lea     edx, [r8+1]
0x18000d1dc  mov     eax, r8d
0x18000d1df  lock cmpxchg [rcx+30h], edx
0x18000d1e4  jz      short loc_18000D1F1
0x18000d1e6  mov     r8d, [rcx+30h]
0x18000d1ea  cmp     r8d, r9d
0x18000d1ed  jnz     short loc_18000D1D8
0x18000d1ef  jmp     short loc_18000D1F5
0x18000d1f1  lea     r9d, [r8+1]
0x18000d1f5  mov     eax, r9d
0x18000d1f8  retn
```
