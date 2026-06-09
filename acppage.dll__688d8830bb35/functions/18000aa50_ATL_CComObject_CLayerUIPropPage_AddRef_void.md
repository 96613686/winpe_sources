# ATL::CComObject<CLayerUIPropPage>::AddRef(void)

- ea: `0x18000aa50`
- end: `0x18000aa63`
- name: `?AddRef@?$CComObject@VCLayerUIPropPage@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000aa70`
- `0x18000aa80`

## callees

- `0x18000aa50`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CLayerUIPropPage>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 24);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 24) = result;
  }
  return result;
}

```

## disassembly

```asm
0x18000aa50  mov     edx, [rcx+18h]
0x18000aa53  mov     eax, 7FFFFFFFh
0x18000aa58  cmp     edx, eax
0x18000aa5a  jz      short locret_18000AA62
0x18000aa5c  lea     eax, [rdx+1]
0x18000aa5f  mov     [rcx+18h], eax
0x18000aa62  retn
```
