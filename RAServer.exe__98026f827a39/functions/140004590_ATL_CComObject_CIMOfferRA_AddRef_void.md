# ATL::CComObject<CIMOfferRA>::AddRef(void)

- ea: `0x140004590`
- end: `0x1400045a3`
- name: `?AddRef@?$CComObject@VCIMOfferRA@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140004590`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIMOfferRA>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 8);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 8) = result;
  }
  return result;
}

```

## disassembly

```asm
0x140004590  mov     edx, [rcx+8]
0x140004593  mov     eax, 7FFFFFFFh
0x140004598  cmp     edx, eax
0x14000459a  jz      short locret_1400045A2
0x14000459c  lea     eax, [rdx+1]
0x14000459f  mov     [rcx+8], eax
0x1400045a2  retn
```
