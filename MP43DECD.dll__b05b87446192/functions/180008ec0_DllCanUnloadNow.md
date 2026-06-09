# DllCanUnloadNow

- ea: `0x180008ec0`
- end: `0x180008edd`
- name: `DllCanUnloadNow`
- size: `29`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008ec0`

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
0x180008ec0  cmp     cs:?m_cLocked@CClassFactory@@0HA, 0; int CClassFactory::m_cLocked
0x180008ec7  jg      short loc_180008ED7
0x180008ec9  mov     ecx, cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180008ecf  xor     eax, eax
0x180008ed1  test    ecx, ecx
0x180008ed3  setnz   al
0x180008ed6  retn
0x180008ed7  mov     eax, 1
0x180008edc  retn
```
