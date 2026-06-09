# ATL::CComAggObject<COpusDecMFT>::AddRef(void)

- ea: `0x18001f2f0`
- end: `0x18001f319`
- name: `?AddRef@?$CComAggObject@VCOpusDecMFT@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001f2f0`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<COpusDecMFT>::AddRef(__int64 a1)
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
0x18001f2f0  mov     r9d, 7FFFFFFFh
0x18001f2f6  jmp     short loc_18001F306
0x18001f2f8  lea     edx, [r8+1]
0x18001f2fc  mov     eax, r8d
0x18001f2ff  lock cmpxchg [rcx+8], edx
0x18001f304  jz      short loc_18001F311
0x18001f306  mov     r8d, [rcx+8]
0x18001f30a  cmp     r8d, r9d
0x18001f30d  jnz     short loc_18001F2F8
0x18001f30f  jmp     short loc_18001F315
0x18001f311  lea     r9d, [r8+1]
0x18001f315  mov     eax, r9d
0x18001f318  retn
```
