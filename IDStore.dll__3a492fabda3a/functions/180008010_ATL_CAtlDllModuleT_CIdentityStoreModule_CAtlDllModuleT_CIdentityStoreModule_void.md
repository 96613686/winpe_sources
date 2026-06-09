# ATL::CAtlDllModuleT<CIdentityStoreModule>::~CAtlDllModuleT<CIdentityStoreModule>(void)

- ea: `0x180008010`
- end: `0x18000802d`
- name: `??1?$CAtlDllModuleT@VCIdentityStoreModule@@@ATL@@UEAA@XZ`
- size: `29`
- prototype: `void __fastcall(ATL::CAtlModule *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010b10`

## callees

- `0x1800080a4`
- `0x180008120`

## pseudocode

```c
void __fastcall ATL::CAtlDllModuleT<CIdentityStoreModule>::~CAtlDllModuleT<CIdentityStoreModule>(ATL::CAtlModule *this)
{
  ATL::CAtlComModule::ExecuteObjectMain(this, 0);
  ATL::CAtlModule::~CAtlModule(this);
}

```

## disassembly

```asm
0x180008010  push    rbx
0x180008012  sub     rsp, 20h
0x180008016  mov     rbx, rcx
0x180008019  xor     edx, edx; bool
0x18000801b  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x180008020  mov     rcx, rbx; this
0x180008023  add     rsp, 20h
0x180008027  pop     rbx
0x180008028  jmp     ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
```
