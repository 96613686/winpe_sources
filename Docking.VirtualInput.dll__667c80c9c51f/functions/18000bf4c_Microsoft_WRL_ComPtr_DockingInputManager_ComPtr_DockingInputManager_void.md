# Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)

- ea: `0x18000bf4c`
- end: `0x18000bf63`
- name: `??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `13`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000b97c`
- `0x18000ba4c`
- `0x18000bb28`
- `0x18000be08`
- `0x18000c464`
- `0x180012960`
- `0x180012e00`
- `0x180012f94`
- `0x1800130c8`
- `0x180013a30`
- `0x180013bd0`
- `0x1800148f8`
- `0x180014df0`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(_QWORD *a1)
{
  *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x18000bf4c  mov     [rsp+arg_0], rcx
0x18000bf51  mov     rax, [rsp+arg_0]
0x18000bf56  mov     qword ptr [rax], 0
0x18000bf5d  mov     rax, [rsp+arg_0]
0x18000bf62  retn
```
