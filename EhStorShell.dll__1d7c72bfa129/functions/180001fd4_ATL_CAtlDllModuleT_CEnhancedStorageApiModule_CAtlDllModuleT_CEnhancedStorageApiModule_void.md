# ATL::CAtlDllModuleT<CEnhancedStorageApiModule>::~CAtlDllModuleT<CEnhancedStorageApiModule>(void)

- ea: `0x180001fd4`
- end: `0x180001ff1`
- name: `??1?$CAtlDllModuleT@VCEnhancedStorageApiModule@@@ATL@@UEAA@XZ`
- size: `29`
- prototype: `void __fastcall(ATL::CAtlModule *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b340`

## callees

- `0x180001ff8`
- `0x180002320`

## pseudocode

```c
void __fastcall ATL::CAtlDllModuleT<CEnhancedStorageApiModule>::~CAtlDllModuleT<CEnhancedStorageApiModule>(
        ATL::CAtlModule *this)
{
  ATL::CAtlComModule::ExecuteObjectMain(this, 0);
  ATL::CAtlModule::~CAtlModule(this);
}

```

## disassembly

```asm
0x180001fd4  push    rbx
0x180001fd6  sub     rsp, 20h
0x180001fda  mov     rbx, rcx
0x180001fdd  xor     edx, edx; bool
0x180001fdf  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x180001fe4  mov     rcx, rbx; this
0x180001fe7  add     rsp, 20h
0x180001feb  pop     rbx
0x180001fec  jmp     ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
```
