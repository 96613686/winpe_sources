# ATL::CComAggObject<CLayerUIPropPage>::AddRef(void)

- ea: `0x18000a9f0`
- end: `0x18000aa03`
- name: `?AddRef@?$CComAggObject@VCLayerUIPropPage@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a9f0`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CLayerUIPropPage>::AddRef(__int64 a1)
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
0x18000a9f0  mov     edx, [rcx+8]
0x18000a9f3  mov     eax, 7FFFFFFFh
0x18000a9f8  cmp     edx, eax
0x18000a9fa  jz      short locret_18000AA02
0x18000a9fc  lea     eax, [rdx+1]
0x18000a9ff  mov     [rcx+8], eax
0x18000aa02  retn
```
