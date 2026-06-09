# DllCanUnloadNow

- ea: `0x180008f80`
- end: `0x180008f9d`
- name: `DllCanUnloadNow`
- size: `29`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008f80`

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
0x180008f80  cmp     cs:?m_cLocked@CClassFactory@@0HA, 0; int CClassFactory::m_cLocked
0x180008f87  jg      short loc_180008F97
0x180008f89  mov     ecx, cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180008f8f  xor     eax, eax
0x180008f91  test    ecx, ecx
0x180008f93  setnz   al
0x180008f96  retn
0x180008f97  mov     eax, 1
0x180008f9c  retn
```
