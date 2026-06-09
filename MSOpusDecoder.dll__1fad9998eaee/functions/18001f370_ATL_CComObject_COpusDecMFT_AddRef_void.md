# ATL::CComObject<COpusDecMFT>::AddRef(void)

- ea: `0x18001f370`
- end: `0x18001f39f`
- name: `?AddRef@?$CComObject@VCOpusDecMFT@@@ATL@@UEAAKXZ`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001f3b0`

## callees

- `0x18001f370`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<COpusDecMFT>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 160);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 160), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x18001f370  mov     r9d, 7FFFFFFFh
0x18001f376  jmp     short loc_18001F389
0x18001f378  lea     edx, [r8+1]
0x18001f37c  mov     eax, r8d
0x18001f37f  lock cmpxchg [rcx+0A0h], edx
0x18001f387  jz      short loc_18001F397
0x18001f389  mov     r8d, [rcx+0A0h]
0x18001f390  cmp     r8d, r9d
0x18001f393  jnz     short loc_18001F378
0x18001f395  jmp     short loc_18001F39B
0x18001f397  lea     r9d, [r8+1]
0x18001f39b  mov     eax, r9d
0x18001f39e  retn
```
