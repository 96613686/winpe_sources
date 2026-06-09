# ATL::CComModule::~CComModule(void)

- ea: `0x1800024d8`
- end: `0x1800024e7`
- name: `??1CComModule@ATL@@UEAA@XZ`
- size: `15`
- prototype: `void __fastcall(ATL::CComModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bad6`

## callees

- `0x1800064c0`

## pseudocode

```c
void __fastcall ATL::CComModule::~CComModule(ATL::CAtlModule *this, unsigned int a2)
{
  *(_QWORD *)this = &ATL::CComModule::`vftable';
  ATL::CAtlModule::Term(this, a2);
}

```

## disassembly

```asm
0x1800024d8  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x1800024df  mov     [rcx], rax
0x1800024e2  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
