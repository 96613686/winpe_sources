# Microsoft::WRL::ComPtr<IUnknown>::ComPtr<IUnknown>(void)

- ea: `0x18000a7d8`
- end: `0x18000a7e3`
- name: `??0?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAA@XZ`
- size: `11`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a6d0`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IUnknown>::ComPtr<IUnknown>(_QWORD *a1)
{
  *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x18000a7d8  mov     qword ptr [rcx], 0
0x18000a7df  mov     rax, rcx
0x18000a7e2  retn
```
