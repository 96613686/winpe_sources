# ATL::CComAggObject<CBrowserCap>::AddRef(void)

- ea: `0x180002a10`
- end: `0x180002a39`
- name: `?AddRef@?$CComAggObject@VCBrowserCap@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002a10`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CBrowserCap>::AddRef(__int64 a1)
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
0x180002a10  mov     r9d, 7FFFFFFFh
0x180002a16  jmp     short loc_180002A26
0x180002a18  lea     edx, [r8+1]
0x180002a1c  mov     eax, r8d
0x180002a1f  lock cmpxchg [rcx+8], edx
0x180002a24  jz      short loc_180002A31
0x180002a26  mov     r8d, [rcx+8]
0x180002a2a  cmp     r8d, r9d
0x180002a2d  jnz     short loc_180002A18
0x180002a2f  jmp     short loc_180002A35
0x180002a31  lea     r9d, [r8+1]
0x180002a35  mov     eax, r9d
0x180002a38  retn
```
