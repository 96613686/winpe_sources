# ATL::CComObject<CWerEventTraceExtender>::AddRef(void)

- ea: `0x180002b60`
- end: `0x180002b89`
- name: `?AddRef@?$CComObject@VCWerEventTraceExtender@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002b60`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWerEventTraceExtender>::AddRef(__int64 a1)
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
0x180002b60  mov     r9d, 7FFFFFFFh
0x180002b66  jmp     short loc_180002B76
0x180002b68  lea     edx, [r8+1]
0x180002b6c  mov     eax, r8d
0x180002b6f  lock cmpxchg [rcx+18h], edx
0x180002b74  jz      short loc_180002B81
0x180002b76  mov     r8d, [rcx+18h]
0x180002b7a  cmp     r8d, r9d
0x180002b7d  jnz     short loc_180002B68
0x180002b7f  jmp     short loc_180002B85
0x180002b81  lea     r9d, [r8+1]
0x180002b85  mov     eax, r9d
0x180002b88  retn
```
