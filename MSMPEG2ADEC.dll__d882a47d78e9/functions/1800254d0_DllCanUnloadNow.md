# DllCanUnloadNow

- ea: `0x1800254d0`
- end: `0x1800254f5`
- name: `DllCanUnloadNow`
- size: `37`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800254d0`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( CClassFactory::m_cLocked > 0 || CBaseObject::m_cObjects )
    LODWORD(v0) = 1;
  else
    return s_mfModuleLockCount > 0;
  return v0;
}

```

## disassembly

```asm
0x1800254d0  xor     ecx, ecx
0x1800254d2  cmp     cs:?m_cLocked@CClassFactory@@0HA, ecx; int CClassFactory::m_cLocked
0x1800254d8  jg      short loc_1800254EF
0x1800254da  cmp     cs:?m_cObjects@CBaseObject@@0JA, ecx; long CBaseObject::m_cObjects
0x1800254e0  jnz     short loc_1800254EF
0x1800254e2  cmp     cs:?s_mfModuleLockCount@@3JA, ecx; long s_mfModuleLockCount
0x1800254e8  mov     eax, ecx
0x1800254ea  setnle  al
0x1800254ed  retn
0x1800254ef  mov     eax, 1
0x1800254f4  retn
```
