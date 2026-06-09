# DllGetClassObject

- ea: `0x180006010`
- end: `0x180006038`
- name: `DllGetClassObject`
- size: `40`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006040`

## callees

- `0x180006010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  result = -2147221231;
  if ( !g_pMalloc )
    return -2147024882;
  return result;
}

```

## disassembly

```asm
0x180006010  test    r8, r8
0x180006013  jnz     short loc_18000601B
0x180006015  mov     eax, 80070057h
0x18000601a  retn
0x18000601b  mov     qword ptr [r8], 0
0x180006022  mov     eax, 80040111h
0x180006027  cmp     cs:?g_pMalloc@@3PEAUIMalloc@@EA, 0; IMalloc * g_pMalloc
0x18000602f  mov     ecx, 8007000Eh
0x180006034  cmovz   eax, ecx
0x180006037  retn
```
