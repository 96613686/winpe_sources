# ATL::CComObject<CEnhancedStorageFolder>::AddRef(void)

- ea: `0x180002e80`
- end: `0x180002e98`
- name: `?AddRef@?$CComObject@VCEnhancedStorageFolder@@@ATL@@UEAAKXZ`
- size: `24`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007ea0`
- `0x180007eb0`

## callees

- `0x180002e80`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageFolder>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 32);
  if ( v1 == 0x7FFFFFFF )
    return 0x7FFFFFFF;
  result = (unsigned int)(v1 + 1);
  *(_DWORD *)(a1 + 32) = result;
  return result;
}

```

## disassembly

```asm
0x180002e80  mov     edx, [rcx+20h]
0x180002e83  cmp     edx, 7FFFFFFFh
0x180002e89  jz      short loc_180002E92
0x180002e8b  lea     eax, [rdx+1]
0x180002e8e  mov     [rcx+20h], eax
0x180002e91  retn
0x180002e92  mov     eax, 7FFFFFFFh
0x180002e97  retn
```
