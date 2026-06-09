# Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Detach(void)

- ea: `0x18000dac0`
- end: `0x18000daea`
- name: `?Detach@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@QEAAPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@XZ`
- size: `42`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000d950`
- `0x180012e00`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Detach(
        __int64 *a1)
{
  __int64 v2; // [rsp+0h] [rbp-18h]

  v2 = *a1;
  *a1 = 0;
  return v2;
}

```

## disassembly

```asm
0x18000dac0  mov     [rsp+arg_0], rcx
0x18000dac5  sub     rsp, 18h
0x18000dac9  mov     rax, [rsp+18h+arg_0]
0x18000dace  mov     rax, [rax]
0x18000dad1  mov     [rsp+18h+var_18], rax
0x18000dad5  mov     rax, [rsp+18h+arg_0]
0x18000dada  mov     qword ptr [rax], 0
0x18000dae1  mov     rax, [rsp+18h+var_18]
0x18000dae5  add     rsp, 18h
0x18000dae9  retn
```
