# ATL::CComObject<CMidi2BS2UMPTransform>::AddRef(void)

- ea: `0x180003f30`
- end: `0x180003f59`
- name: `?AddRef@?$CComObject@VCMidi2BS2UMPTransform@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003f30`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMidi2BS2UMPTransform>::AddRef(__int64 a1)
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
0x180003f30  mov     r9d, 7FFFFFFFh
0x180003f36  jmp     short loc_180003F46
0x180003f38  lea     edx, [r8+1]
0x180003f3c  mov     eax, r8d
0x180003f3f  lock cmpxchg [rcx+8], edx
0x180003f44  jz      short loc_180003F51
0x180003f46  mov     r8d, [rcx+8]
0x180003f4a  cmp     r8d, r9d
0x180003f4d  jnz     short loc_180003F38
0x180003f4f  jmp     short loc_180003F55
0x180003f51  lea     r9d, [r8+1]
0x180003f55  mov     eax, r9d
0x180003f58  retn
```
