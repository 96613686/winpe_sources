# Microsoft::WRL::ComPtr<DeploymentProgressHandler>::~ComPtr<DeploymentProgressHandler>(void)

- ea: `0x180015004`
- end: `0x18001502d`
- name: `??1?$ComPtr@VDeploymentProgressHandler@@@WRL@Microsoft@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020737`
- `0x180020749`
- `0x18002075b`
- `0x18002076d`
- `0x18002077f`
- `0x1800207a3`
- `0x1800207d9`
- `0x1800208e7`
- `0x1800208f9`

## callees

- `0x180015004`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<DeploymentProgressHandler>::~ComPtr<DeploymentProgressHandler>(_QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180015004  sub     rsp, 28h
0x180015008  mov     rax, rcx
0x18001500b  mov     rcx, [rcx]
0x18001500e  test    rcx, rcx
0x180015011  jz      short loc_180015027
0x180015013  mov     qword ptr [rax], 0
0x18001501a  mov     rax, [rcx]
0x18001501d  mov     rax, [rax+10h]
0x180015021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015026  nop
0x180015027  add     rsp, 28h
0x18001502b  retn
```
