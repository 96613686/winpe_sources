# ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory>::AddRef(void)

- ea: `0x140010300`
- end: `0x140010329`
- name: `?AddRef@?$CComObject@VCHostProviderFactory@Spelling@Globalization@Windows@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140010300`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory>::AddRef(__int64 a1)
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
0x140010300  mov     r9d, 7FFFFFFFh
0x140010306  jmp     short loc_140010316
0x140010308  lea     edx, [r8+1]
0x14001030c  mov     eax, r8d
0x14001030f  lock cmpxchg [rcx+8], edx
0x140010314  jz      short loc_140010321
0x140010316  mov     r8d, [rcx+8]
0x14001031a  cmp     r8d, r9d
0x14001031d  jnz     short loc_140010308
0x14001031f  jmp     short loc_140010325
0x140010321  lea     r9d, [r8+1]
0x140010325  mov     eax, r9d
0x140010328  retn
```
