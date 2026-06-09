# ATL::CComObject<CRemMdmObj>::AddRef(void)

- ea: `0x180005260`
- end: `0x180005273`
- name: `?AddRef@?$CComObject@VCRemMdmObj@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005260`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRemMdmObj>::AddRef(__int64 a1)
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
0x180005260  mov     edx, [rcx+8]
0x180005263  mov     eax, 7FFFFFFFh
0x180005268  cmp     edx, eax
0x18000526a  jz      short locret_180005272
0x18000526c  lea     eax, [rdx+1]
0x18000526f  mov     [rcx+8], eax
0x180005272  retn
```
