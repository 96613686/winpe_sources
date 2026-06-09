# ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::AddRef(void)

- ea: `0x14000fdb0`
- end: `0x14000fdd9`
- name: `?AddRef@?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000fde0`
- `0x14000fdf0`

## callees

- `0x14000fdb0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 24);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 24), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x14000fdb0  mov     r9d, 7FFFFFFFh
0x14000fdb6  jmp     short loc_14000FDC6
0x14000fdb8  lea     edx, [r8+1]
0x14000fdbc  mov     eax, r8d
0x14000fdbf  lock cmpxchg [rcx+18h], edx
0x14000fdc4  jz      short loc_14000FDD1
0x14000fdc6  mov     r8d, [rcx+18h]
0x14000fdca  cmp     r8d, r9d
0x14000fdcd  jnz     short loc_14000FDB8
0x14000fdcf  jmp     short loc_14000FDD5
0x14000fdd1  lea     r9d, [r8+1]
0x14000fdd5  mov     eax, r9d
0x14000fdd8  retn
```
