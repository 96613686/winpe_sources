# ATL::CComAggObject<CIdentityProfileHandler>::AddRef(void)

- ea: `0x18000e050`
- end: `0x18000e077`
- name: `?AddRef@?$CComAggObject@VCIdentityProfileHandler@@@ATL@@UEAAKXZ`
- size: `39`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e050`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CIdentityProfileHandler>::AddRef(__int64 a1)
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
0x18000e050  mov     r9d, 7FFFFFFFh
0x18000e056  mov     r8d, [rcx+8]
0x18000e05a  cmp     r8d, r9d
0x18000e05d  jnz     short loc_18000E063
0x18000e05f  mov     eax, r9d
0x18000e062  retn
0x18000e063  lea     edx, [r8+1]
0x18000e067  mov     eax, r8d
0x18000e06a  lock cmpxchg [rcx+8], edx
0x18000e06f  jnz     short loc_18000E056
0x18000e071  lea     r9d, [r8+1]
0x18000e075  jmp     short loc_18000E05F
```
