# ATL::CComObject<CDfsShell>::AddRef(void)

- ea: `0x1800031b0`
- end: `0x1800031c3`
- name: `?AddRef@?$CComObject@VCDfsShell@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800031d0`

## callees

- `0x1800031b0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDfsShell>::AddRef(__int64 a1)
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
0x1800031b0  mov     edx, [rcx+10h]
0x1800031b3  mov     eax, 7FFFFFFFh
0x1800031b8  cmp     edx, eax
0x1800031ba  jz      short locret_1800031C2
0x1800031bc  lea     eax, [rdx+1]
0x1800031bf  mov     [rcx+10h], eax
0x1800031c2  retn
```
