# ATL::CComAggObject<CALACDecMFT>::AddRef(void)

- ea: `0x1800044c0`
- end: `0x1800044e9`
- name: `?AddRef@?$CComAggObject@VCALACDecMFT@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800044c0`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CALACDecMFT>::AddRef(__int64 a1)
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
0x1800044c0  mov     r9d, 7FFFFFFFh
0x1800044c6  jmp     short loc_1800044D6
0x1800044c8  lea     edx, [r8+1]
0x1800044cc  mov     eax, r8d
0x1800044cf  lock cmpxchg [rcx+8], edx
0x1800044d4  jz      short loc_1800044E1
0x1800044d6  mov     r8d, [rcx+8]
0x1800044da  cmp     r8d, r9d
0x1800044dd  jnz     short loc_1800044C8
0x1800044df  jmp     short loc_1800044E5
0x1800044e1  lea     r9d, [r8+1]
0x1800044e5  mov     eax, r9d
0x1800044e8  retn
```
