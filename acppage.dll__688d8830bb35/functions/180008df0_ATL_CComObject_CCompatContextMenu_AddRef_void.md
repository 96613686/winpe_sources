# ATL::CComObject<CCompatContextMenu>::AddRef(void)

- ea: `0x180008df0`
- end: `0x180008e19`
- name: `?AddRef@?$CComObject@VCCompatContextMenu@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008e20`
- `0x180008e30`
- `0x180008e40`

## callees

- `0x180008df0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCompatContextMenu>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 32);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 32), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180008df0  mov     r9d, 7FFFFFFFh
0x180008df6  jmp     short loc_180008E06
0x180008df8  lea     edx, [r8+1]
0x180008dfc  mov     eax, r8d
0x180008dff  lock cmpxchg [rcx+20h], edx
0x180008e04  jz      short loc_180008E11
0x180008e06  mov     r8d, [rcx+20h]
0x180008e0a  cmp     r8d, r9d
0x180008e0d  jnz     short loc_180008DF8
0x180008e0f  jmp     short loc_180008E15
0x180008e11  lea     r9d, [r8+1]
0x180008e15  mov     eax, r9d
0x180008e18  retn
```
