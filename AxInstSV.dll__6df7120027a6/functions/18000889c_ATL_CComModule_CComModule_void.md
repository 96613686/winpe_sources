# ATL::CComModule::~CComModule(void)

- ea: `0x18000889c`
- end: `0x1800088ab`
- name: `??1CComModule@ATL@@UEAA@XZ`
- size: `15`
- prototype: `void __fastcall(ATL::CComModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800148de`

## callees

- `0x180010154`

## pseudocode

```c
void __fastcall ATL::CComModule::~CComModule(ATL::CComModule *this)
{
  *(_QWORD *)this = &ATL::CComModule::`vftable';
  ATL::CAtlModule::Term(this);
}

```

## disassembly

```asm
0x18000889c  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x1800088a3  mov     [rcx], rax
0x1800088a6  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
