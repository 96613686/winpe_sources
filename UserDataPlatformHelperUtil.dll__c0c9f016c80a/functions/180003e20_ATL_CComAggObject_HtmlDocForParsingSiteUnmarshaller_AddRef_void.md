# ATL::CComAggObject<HtmlDocForParsingSiteUnmarshaller>::AddRef(void)

- ea: `0x180003e20`
- end: `0x180003e49`
- name: `?AddRef@?$CComAggObject@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003e20`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<HtmlDocForParsingSiteUnmarshaller>::AddRef(__int64 a1)
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
0x180003e20  mov     r9d, 7FFFFFFFh
0x180003e26  jmp     short loc_180003E36
0x180003e28  lea     edx, [r8+1]
0x180003e2c  mov     eax, r8d
0x180003e2f  lock cmpxchg [rcx+8], edx
0x180003e34  jz      short loc_180003E41
0x180003e36  mov     r8d, [rcx+8]
0x180003e3a  cmp     r8d, r9d
0x180003e3d  jnz     short loc_180003E28
0x180003e3f  jmp     short loc_180003E45
0x180003e41  lea     r9d, [r8+1]
0x180003e45  mov     eax, r9d
0x180003e48  retn
```
