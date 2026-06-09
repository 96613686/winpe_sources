# ATL::ModuleLockHelper::ModuleLockHelper(void)

- ea: `0x180003ca0`
- end: `0x180003cc5`
- name: `??0ModuleLockHelper@ATL@@QEAA@XZ`
- size: `37`
- prototype: `ATL::ModuleLockHelper *__fastcall(ATL::ModuleLockHelper *this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004150`
- `0x1800044b0`
- `0x180009010`
- `0x18000b0c0`

## callees

- `0x18000c010`

## pseudocode

```c
ATL::ModuleLockHelper *__fastcall ATL::ModuleLockHelper::ModuleLockHelper(ATL::ModuleLockHelper *this)
{
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return this;
}

```

## disassembly

```asm
0x180003ca0  push    rbx
0x180003ca2  sub     rsp, 20h
0x180003ca6  mov     rbx, rcx
0x180003ca9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003cb0  mov     rax, [rcx]
0x180003cb3  mov     rax, [rax+8]
0x180003cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cbc  mov     rax, rbx
0x180003cbf  add     rsp, 20h
0x180003cc3  pop     rbx
0x180003cc4  retn
```
