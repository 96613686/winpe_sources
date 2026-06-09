# DllCanUnloadNow

- ea: `0x1800092a0`
- end: `0x1800092bd`
- name: `DllCanUnloadNow`
- size: `29`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800092a0`

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
0x1800092a0  cmp     cs:?m_cLocked@CClassFactory@@0HA, 0; int CClassFactory::m_cLocked
0x1800092a7  jg      short loc_1800092B7
0x1800092a9  mov     ecx, cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x1800092af  xor     eax, eax
0x1800092b1  test    ecx, ecx
0x1800092b3  setnz   al
0x1800092b6  retn
0x1800092b7  mov     eax, 1
0x1800092bc  retn
```
