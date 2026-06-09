# ATL::CComObject<CBrowserCap>::AddRef(void)

- ea: `0x180002a70`
- end: `0x180002a99`
- name: `?AddRef@?$CComObject@VCBrowserCap@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002aa0`

## callees

- `0x180002a70`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CBrowserCap>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 16);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 16), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180002a70  mov     r9d, 7FFFFFFFh
0x180002a76  jmp     short loc_180002A86
0x180002a78  lea     edx, [r8+1]
0x180002a7c  mov     eax, r8d
0x180002a7f  lock cmpxchg [rcx+10h], edx
0x180002a84  jz      short loc_180002A91
0x180002a86  mov     r8d, [rcx+10h]
0x180002a8a  cmp     r8d, r9d
0x180002a8d  jnz     short loc_180002A78
0x180002a8f  jmp     short loc_180002A95
0x180002a91  lea     r9d, [r8+1]
0x180002a95  mov     eax, r9d
0x180002a98  retn
```
