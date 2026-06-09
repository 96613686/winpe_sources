# DiagHubCommon::ModulePath::~ModulePath(void)

- ea: `0x140006364`
- end: `0x140006369`
- name: `??1ModulePath@DiagHubCommon@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(__int64 this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140014fca`
- `0x14001540d`
- `0x140015425`
- `0x1400157f1`
- `0x140015928`

## callees

- `0x1400043a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
// attributes: thunk
void __fastcall DiagHubCommon::ModulePath::~ModulePath(__int64 this)
{
  std::vector<unsigned short>::~vector<unsigned short>(this);
}

```

## disassembly

```asm
0x140006364  jmp     ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
```
