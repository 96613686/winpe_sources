# Microsoft::WRL::ComPtr<IUnknown>::ComPtr<IUnknown>(void)

- ea: `0x1800042e0`
- end: `0x1800042eb`
- name: `??0?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAA@XZ`
- size: `11`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
void __fastcall Microsoft::WRL::ComPtr<IUnknown>::ComPtr<IUnknown>(_QWORD *a1)
{
  *a1 = 0;
}

```

## disassembly

```asm
0x1800042e0  mov     qword ptr [rcx], 0
0x1800042e7  mov     rax, rcx
0x1800042ea  retn
```
