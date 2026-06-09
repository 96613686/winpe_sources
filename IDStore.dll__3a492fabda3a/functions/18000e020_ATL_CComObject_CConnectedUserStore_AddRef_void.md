# ATL::CComObject<CConnectedUserStore>::AddRef(void)

- ea: `0x18000e020`
- end: `0x18000e047`
- name: `?AddRef@?$CComObject@VCConnectedUserStore@@@ATL@@UEAAKXZ`
- size: `39`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010c80`

## callees

- `0x18000e020`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CConnectedUserStore>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 16);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 16), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x18000e020  mov     r9d, 7FFFFFFFh
0x18000e026  mov     r8d, [rcx+10h]
0x18000e02a  cmp     r8d, r9d
0x18000e02d  jnz     short loc_18000E033
0x18000e02f  mov     eax, r9d
0x18000e032  retn
0x18000e033  lea     edx, [r8+1]
0x18000e037  mov     eax, r8d
0x18000e03a  lock cmpxchg [rcx+10h], edx
0x18000e03f  jnz     short loc_18000E026
0x18000e041  lea     r9d, [r8+1]
0x18000e045  jmp     short loc_18000E02F
```
