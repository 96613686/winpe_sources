# ATL::CComObject<CEnhancedStorageEnumerator>::AddRef(void)

- ea: `0x180003f10`
- end: `0x180003f23`
- name: `?AddRef@?$CComObject@VCEnhancedStorageEnumerator@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003f10`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageEnumerator>::AddRef(__int64 a1)
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
0x180003f10  mov     edx, [rcx+8]
0x180003f13  mov     eax, 7FFFFFFFh
0x180003f18  cmp     edx, eax
0x180003f1a  jz      short locret_180003F22
0x180003f1c  lea     eax, [rdx+1]
0x180003f1f  mov     [rcx+8], eax
0x180003f22  retn
```
