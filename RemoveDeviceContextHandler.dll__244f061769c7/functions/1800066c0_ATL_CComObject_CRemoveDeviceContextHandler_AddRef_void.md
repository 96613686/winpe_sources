# ATL::CComObject<CRemoveDeviceContextHandler>::AddRef(void)

- ea: `0x1800066c0`
- end: `0x1800066d3`
- name: `?AddRef@?$CComObject@VCRemoveDeviceContextHandler@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800066e0`

## callees

- `0x1800066c0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRemoveDeviceContextHandler>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 16);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 16) = result;
  }
  return result;
}

```

## disassembly

```asm
0x1800066c0  mov     edx, [rcx+10h]
0x1800066c3  mov     eax, 7FFFFFFFh
0x1800066c8  cmp     edx, eax
0x1800066ca  jz      short locret_1800066D2
0x1800066cc  lea     eax, [rdx+1]
0x1800066cf  mov     [rcx+10h], eax
0x1800066d2  retn
```
