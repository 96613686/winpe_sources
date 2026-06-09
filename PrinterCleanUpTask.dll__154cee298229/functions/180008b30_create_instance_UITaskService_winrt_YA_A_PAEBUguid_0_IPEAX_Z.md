# ??$create_instance@UITaskService@@@winrt@@YA?A_PAEBUguid@0@IPEAX@Z

- ea: `0x180008b30`
- end: `0x180008b68`
- name: `??$create_instance@UITaskService@@@winrt@@YA?A_PAEBUguid@0@IPEAX@Z`
- size: `56`
- prototype: `_QWORD *__fastcall(_QWORD *, const IID *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010470`
- `0x1800151d0`

## callees

- `0x180008a2c`

## pseudocode

```c
_QWORD *__fastcall winrt::create_instance<ITaskService>(_QWORD *a1, const IID *a2)
{
  DWORD v4[4]; // [rsp+30h] [rbp-28h] BYREF
  IUnknown *v5; // [rsp+40h] [rbp-18h] BYREF

  v5 = 0;
  v4[0] = 1;
  ___capture_UITaskService__A6AHAEBUguid_winrt__PEAXI0PEAPEAX__EAEBU23_AEAPEAXAEAI_winrt__YA_AU__com_ptr_UITaskService___0_A6AHAEBUguid_0_PEAXI0PEAPEAX__E0AEAPEAXAEAI_Z(
    a1,
    (__int64)a2,
    a2,
    &v5,
    v4);
  return a1;
}

```

## disassembly

```asm
0x180008b30  mov     r11, rsp
0x180008b33  push    rbx
0x180008b34  sub     rsp, 50h
0x180008b38  lea     rax, [r11-28h]
0x180008b3c  mov     qword ptr [r11-18h], 0
0x180008b44  lea     r9, [r11-18h]
0x180008b48  mov     [r11-38h], rax
0x180008b4c  mov     r8, rdx
0x180008b4f  mov     [rsp+58h+var_28], 1
0x180008b57  mov     rbx, rcx
0x180008b5a  call    ??$capture@UITaskService@@A6AHAEBUguid@winrt@@PEAXI0PEAPEAX@_EAEBU23@AEAPEAXAEAI@winrt@@YA?AU?$com_ptr@UITaskService@@@0@A6AHAEBUguid@0@PEAXI0PEAPEAX@_E0AEAPEAXAEAI@Z
0x180008b5f  mov     rax, rbx
0x180008b62  add     rsp, 50h
0x180008b66  pop     rbx
0x180008b67  retn
```
