# ATL::CComClassFactory::~CComClassFactory(void)

- ea: `0x180002fcc`
- end: `0x180002fd7`
- name: `??1CComClassFactory@ATL@@UEAA@XZ`
- size: `11`
- prototype: `void __fastcall(ATL::CComClassFactory *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000e539`
- `0x18000e602`

## pseudocode

```c
void __fastcall ATL::CComClassFactory::~CComClassFactory(ATL::CComClassFactory *this)
{
  *(_QWORD *)this = &ATL::CComClassFactory::`vftable';
}

```

## disassembly

```asm
0x180002fcc  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180002fd3  mov     [rcx], rax
0x180002fd6  retn
```
