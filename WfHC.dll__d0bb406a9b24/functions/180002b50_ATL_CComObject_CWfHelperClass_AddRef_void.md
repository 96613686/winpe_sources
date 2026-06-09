# ATL::CComObject<CWfHelperClass>::AddRef(void)

- ea: `0x180002b50`
- end: `0x180002b7d`
- name: `?AddRef@?$CComObject@VCWfHelperClass@@@ATL@@UEAAKXZ`
- size: `45`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002b90`
- `0x180002ba0`

## callees

- `0x180002b50`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWfHelperClass>::AddRef(__int64 a1)
{
  signed __int32 v1; // eax

  v1 = *(_DWORD *)(a1 + 64);
  if ( v1 == 0x7FFFFFFF )
    return 0x7FFFFFFF;
  while ( v1 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 64), v1 + 1, v1) )
  {
    v1 = *(_DWORD *)(a1 + 64);
    if ( v1 == 0x7FFFFFFF )
      return 0x7FFFFFFF;
  }
  return (unsigned int)(v1 + 1);
}

```

## disassembly

```asm
0x180002b50  mov     eax, [rcx+40h]
0x180002b53  cmp     eax, 7FFFFFFFh
0x180002b58  jz      short loc_180002B74
0x180002b5a  nop     word ptr [rax+rax+00h]
0x180002b60  lea     edx, [rax+1]
0x180002b63  lock cmpxchg [rcx+40h], edx
0x180002b68  jz      short loc_180002B7A
0x180002b6a  mov     eax, [rcx+40h]
0x180002b6d  cmp     eax, 7FFFFFFFh
0x180002b72  jnz     short loc_180002B60
0x180002b74  mov     eax, 7FFFFFFFh
0x180002b79  retn
0x180002b7a  mov     eax, edx
0x180002b7c  retn
```
