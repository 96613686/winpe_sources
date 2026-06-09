# wil::acquire_wdf_spin_lock(WDFSPINLOCK__ *)

- ea: `0x140011484`
- end: `0x1400114c0`
- name: `?acquire_wdf_spin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAUWDFSPINLOCK__@@@Z`
- size: `60`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x14000cb04`
- `0x14000d140`
- `0x14000d76c`
- `0x14000e510`
- `0x14000fa40`
- `0x14001117c`
- `0x1400139e8`
- `0x140013df8`
- `0x140015e9c`

## callees

- `0x14001ae00`

## pseudocode

```c
_QWORD *__fastcall wil::acquire_wdf_spin_lock(_QWORD *a1, __int64 a2)
{
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 2528))(WdfDriverGlobals);
  *a1 = a2;
  return a1;
}

```

## disassembly

```asm
0x140011484  mov     [rsp+arg_0], rbx
0x140011489  push    rdi
0x14001148a  sub     rsp, 20h
0x14001148e  mov     rax, cs:WdfFunctions_01015
0x140011495  mov     rdi, rcx
0x140011498  mov     rcx, cs:WdfDriverGlobals
0x14001149f  mov     rbx, rdx
0x1400114a2  mov     rax, [rax+9E0h]
0x1400114a9  call    _guard_dispatch_icall
0x1400114ae  mov     [rdi], rbx
0x1400114b1  mov     rax, rdi
0x1400114b4  mov     rbx, [rsp+28h+arg_0]
0x1400114b9  add     rsp, 20h
0x1400114bd  pop     rdi
0x1400114be  retn
```
