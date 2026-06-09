# ATL::CComObject<CRemoveDeviceElevatedHandler>::AddRef(void)

- ea: `0x180006650`
- end: `0x180006663`
- name: `?AddRef@?$CComObject@VCRemoveDeviceElevatedHandler@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006650`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRemoveDeviceElevatedHandler>::AddRef(__int64 a1)
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
0x180006650  mov     edx, [rcx+8]
0x180006653  mov     eax, 7FFFFFFFh
0x180006658  cmp     edx, eax
0x18000665a  jz      short locret_180006662
0x18000665c  lea     eax, [rdx+1]
0x18000665f  mov     [rcx+8], eax
0x180006662  retn
```
