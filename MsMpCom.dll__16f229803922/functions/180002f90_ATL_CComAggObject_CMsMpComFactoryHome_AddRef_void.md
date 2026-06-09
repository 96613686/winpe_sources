# ATL::CComAggObject<CMsMpComFactoryHome>::AddRef(void)

- ea: `0x180002f90`
- end: `0x180002fb9`
- name: `?AddRef@?$CComAggObject@VCMsMpComFactoryHome@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002f90`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMsMpComFactoryHome>::AddRef(__int64 a1)
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
0x180002f90  mov     r9d, 7FFFFFFFh
0x180002f96  jmp     short loc_180002FA6
0x180002f98  lea     edx, [r8+1]
0x180002f9c  mov     eax, r8d
0x180002f9f  lock cmpxchg [rcx+8], edx
0x180002fa4  jz      short loc_180002FB1
0x180002fa6  mov     r8d, [rcx+8]
0x180002faa  cmp     r8d, r9d
0x180002fad  jnz     short loc_180002F98
0x180002faf  jmp     short loc_180002FB5
0x180002fb1  lea     r9d, [r8+1]
0x180002fb5  mov     eax, r9d
0x180002fb8  retn
```
