# ATL::CAtlDllModuleT<CAppHostNavigatorsModule>::~CAtlDllModuleT<CAppHostNavigatorsModule>(void)

- ea: `0x18000f000`
- end: `0x18000f01d`
- name: `??1?$CAtlDllModuleT@VCAppHostNavigatorsModule@@@ATL@@UEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f030`
- `0x180013e70`

## callees

- `0x18000f614`
- `0x18000f744`

## pseudocode

```c
void __fastcall ATL::CAtlDllModuleT<CAppHostNavigatorsModule>::~CAtlDllModuleT<CAppHostNavigatorsModule>(
        ATL::CAtlModule *this)
{
  ATL::CAtlComModule::ExecuteObjectMain(this, 0);
  ATL::CAtlModule::Term(this);
}

```

## disassembly

```asm
0x18000f000  push    rbx
0x18000f002  sub     rsp, 20h
0x18000f006  mov     rbx, rcx
0x18000f009  xor     edx, edx; bool
0x18000f00b  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x18000f010  mov     rcx, rbx; this
0x18000f013  add     rsp, 20h
0x18000f017  pop     rbx
0x18000f018  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
