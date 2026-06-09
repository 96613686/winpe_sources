# CClassFactory::CClassFactory(CComClassTemplate const *)

- ea: `0x180025f38`
- end: `0x180025f58`
- name: `??0CClassFactory@@QEAA@PEBUCComClassTemplate@@@Z`
- size: `32`
- prototype: `CClassFactory *__fastcall(CClassFactory *__hidden this, const struct CComClassTemplate *)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180025e40`
- `0x18002e970`

## pseudocode

```c
CClassFactory *__fastcall CClassFactory::CClassFactory(CClassFactory *this, const struct CComClassTemplate *a2)
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
0x180025f38  lock inc cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180025f3f  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x180025f46  mov     [rcx+8], rdx
0x180025f4a  mov     [rcx], rax
0x180025f4d  mov     rax, rcx
0x180025f50  mov     dword ptr [rcx+10h], 0
0x180025f57  retn
```
