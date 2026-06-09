# ATL::CComObject<CDfsShellAdmin>::AddRef(void)

- ea: `0x180003140`
- end: `0x180003153`
- name: `?AddRef@?$CComObject@VCDfsShellAdmin@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003140`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDfsShellAdmin>::AddRef(__int64 a1)
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
0x180003140  mov     edx, [rcx+8]
0x180003143  mov     eax, 7FFFFFFFh
0x180003148  cmp     edx, eax
0x18000314a  jz      short locret_180003152
0x18000314c  lea     eax, [rdx+1]
0x18000314f  mov     [rcx+8], eax
0x180003152  retn
```
