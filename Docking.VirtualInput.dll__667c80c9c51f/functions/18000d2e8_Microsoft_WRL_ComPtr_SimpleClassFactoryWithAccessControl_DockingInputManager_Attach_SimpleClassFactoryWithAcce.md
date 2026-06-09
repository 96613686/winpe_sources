# Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Attach(SimpleClassFactoryWithAccessControl<DockingInputManager> *)

- ea: `0x18000d2e8`
- end: `0x18000d33d`
- name: `?Attach@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@QEAAXPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@Z`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000bb28`
- `0x180012f94`

## callees

- `0x18000d2e8`
- `0x18001c010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Attach(
        _QWORD *a1,
        __int64 a2)
{
  _QWORD *result; // rax

  if ( *a1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
  result = a1;
  *a1 = a2;
  return result;
}

```

## disassembly

```asm
0x18000d2e8  mov     [rsp+arg_8], rdx
0x18000d2ed  mov     [rsp+arg_0], rcx
0x18000d2f2  sub     rsp, 38h
0x18000d2f6  mov     rax, [rsp+38h+arg_0]
0x18000d2fb  cmp     qword ptr [rax], 0
0x18000d2ff  jz      short loc_18000D32B
0x18000d301  mov     rax, [rsp+38h+arg_0]
0x18000d306  mov     rax, [rax]
0x18000d309  mov     rcx, [rsp+38h+arg_0]
0x18000d30e  mov     rcx, [rcx]
0x18000d311  mov     rax, [rax]
0x18000d314  mov     rax, [rax+10h]
0x18000d318  mov     [rsp+38h+var_10], rax
0x18000d31d  mov     rax, [rsp+38h+var_10]
0x18000d322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d327  mov     [rsp+38h+var_18], eax
0x18000d32b  mov     rax, [rsp+38h+arg_0]
0x18000d330  mov     rcx, [rsp+38h+arg_8]
0x18000d335  mov     [rax], rcx
0x18000d338  add     rsp, 38h
0x18000d33c  retn
```
