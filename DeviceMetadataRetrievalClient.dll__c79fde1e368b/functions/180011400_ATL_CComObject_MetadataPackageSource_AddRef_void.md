# ATL::CComObject<MetadataPackageSource>::AddRef(void)

- ea: `0x180011400`
- end: `0x180011429`
- name: `?AddRef@?$CComObject@VMetadataPackageSource@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011400`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<MetadataPackageSource>::AddRef(__int64 a1)
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
0x180011400  mov     r9d, 7FFFFFFFh
0x180011406  jmp     short loc_180011416
0x180011408  lea     edx, [r8+1]
0x18001140c  mov     eax, r8d
0x18001140f  lock cmpxchg [rcx+8], edx
0x180011414  jz      short loc_180011421
0x180011416  mov     r8d, [rcx+8]
0x18001141a  cmp     r8d, r9d
0x18001141d  jnz     short loc_180011408
0x18001141f  jmp     short loc_180011425
0x180011421  lea     r9d, [r8+1]
0x180011425  mov     eax, r9d
0x180011428  retn
```
