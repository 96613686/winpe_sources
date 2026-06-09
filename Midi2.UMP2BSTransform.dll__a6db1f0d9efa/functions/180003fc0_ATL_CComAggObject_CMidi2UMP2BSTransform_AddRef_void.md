# ATL::CComAggObject<CMidi2UMP2BSTransform>::AddRef(void)

- ea: `0x180003fc0`
- end: `0x180003fe9`
- name: `?AddRef@?$CComAggObject@VCMidi2UMP2BSTransform@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003fc0`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMidi2UMP2BSTransform>::AddRef(__int64 a1)
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
0x180003fc0  mov     r9d, 7FFFFFFFh
0x180003fc6  jmp     short loc_180003FD6
0x180003fc8  lea     edx, [r8+1]
0x180003fcc  mov     eax, r8d
0x180003fcf  lock cmpxchg [rcx+8], edx
0x180003fd4  jz      short loc_180003FE1
0x180003fd6  mov     r8d, [rcx+8]
0x180003fda  cmp     r8d, r9d
0x180003fdd  jnz     short loc_180003FC8
0x180003fdf  jmp     short loc_180003FE5
0x180003fe1  lea     r9d, [r8+1]
0x180003fe5  mov     eax, r9d
0x180003fe8  retn
```
