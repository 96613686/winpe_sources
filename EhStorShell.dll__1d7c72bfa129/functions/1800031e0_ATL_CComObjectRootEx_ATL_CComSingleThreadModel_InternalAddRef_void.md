# ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef(void)

- ea: `0x1800031e0`
- end: `0x1800031f6`
- name: `?InternalAddRef@?$CComObjectRootEx@VCComSingleThreadModel@ATL@@@ATL@@QEAAKXZ`
- size: `22`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `8`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003000`
- `0x180003104`
- `0x180003fb8`
- `0x180005c80`
- `0x180006250`
- `0x180007e80`
- `0x180008718`
- `0x18000a800`

## callees

- `0x1800031e0`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef(_DWORD *a1)
{
  __int64 result; // rax

  if ( *a1 == 0x7FFFFFFF )
    return 0x7FFFFFFF;
  result = (unsigned int)(*a1 + 1);
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x1800031e0  mov     edx, [rcx]
0x1800031e2  cmp     edx, 7FFFFFFFh
0x1800031e8  jz      short loc_1800031F0
0x1800031ea  lea     eax, [rdx+1]
0x1800031ed  mov     [rcx], eax
0x1800031ef  retn
0x1800031f0  mov     eax, 7FFFFFFFh
0x1800031f5  retn
```
