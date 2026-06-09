# DllCanUnloadNow

- ea: `0x180028450`
- end: `0x18002846d`
- name: `DllCanUnloadNow`
- size: `29`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180028450`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( CClassFactory::m_cLocked > 0 )
    LODWORD(v0) = 1;
  else
    return g_cActiveObjects != 0;
  return v0;
}

```

## disassembly

```asm
0x180028450  cmp     cs:?m_cLocked@CClassFactory@@0HA, 0; int CClassFactory::m_cLocked
0x180028457  jg      short loc_180028467
0x180028459  mov     ecx, cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x18002845f  xor     eax, eax
0x180028461  test    ecx, ecx
0x180028463  setnz   al
0x180028466  retn
0x180028467  mov     eax, 1
0x18002846c  retn
```
