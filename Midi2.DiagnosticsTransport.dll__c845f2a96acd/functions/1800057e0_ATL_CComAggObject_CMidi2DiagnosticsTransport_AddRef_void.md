# ATL::CComAggObject<CMidi2DiagnosticsTransport>::AddRef(void)

- ea: `0x1800057e0`
- end: `0x180005809`
- name: `?AddRef@?$CComAggObject@VCMidi2DiagnosticsTransport@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800057e0`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMidi2DiagnosticsTransport>::AddRef(__int64 a1)
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
0x1800057e0  mov     r9d, 7FFFFFFFh
0x1800057e6  jmp     short loc_1800057F6
0x1800057e8  lea     edx, [r8+1]
0x1800057ec  mov     eax, r8d
0x1800057ef  lock cmpxchg [rcx+8], edx
0x1800057f4  jz      short loc_180005801
0x1800057f6  mov     r8d, [rcx+8]
0x1800057fa  cmp     r8d, r9d
0x1800057fd  jnz     short loc_1800057E8
0x1800057ff  jmp     short loc_180005805
0x180005801  lea     r9d, [r8+1]
0x180005805  mov     eax, r9d
0x180005808  retn
```
