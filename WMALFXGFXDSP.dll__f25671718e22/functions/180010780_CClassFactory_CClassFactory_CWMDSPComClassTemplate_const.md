# CClassFactory::CClassFactory(CWMDSPComClassTemplate const *)

- ea: `0x180010780`
- end: `0x1800107a0`
- name: `??0CClassFactory@@QEAA@PEBUCWMDSPComClassTemplate@@@Z`
- size: `32`
- prototype: `CClassFactory *__fastcall(CClassFactory *__hidden this, const struct CWMDSPComClassTemplate *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180010680`

## pseudocode

```c
CClassFactory *__fastcall CClassFactory::CClassFactory(CClassFactory *this, const struct CWMDSPComClassTemplate *a2)
{
  CClassFactory *result; // rax

  _InterlockedIncrement(&g_cActiveObjects);
  *((_QWORD *)this + 1) = a2;
  *(_QWORD *)this = &CClassFactory::`vftable';
  result = this;
  *((_DWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x180010780  lock inc cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180010787  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x18001078e  mov     [rcx+8], rdx
0x180010792  mov     [rcx], rax
0x180010795  mov     rax, rcx
0x180010798  mov     dword ptr [rcx+10h], 0
0x18001079f  retn
```
