# Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualTouchPadServer>::CopyTo<IInspectable>(IInspectable * *)

- ea: `0x18000b748`
- end: `0x18000b7a1`
- name: `??$CopyTo@UIInspectable@@@?$ComPtr@VVirtualTouchPadServer@VirtualInput@Docking@@@WRL@Microsoft@@QEBAJPEAPEAUIInspectable@@@Z`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012960`
- `0x1800148f8`

## callees

- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualTouchPadServer>::CopyTo<IInspectable>(
        _QWORD *a1,
        __int64 a2)
{
  return (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*a1)(*a1, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, a2);
}

```

## disassembly

```asm
0x18000b748  mov     [rsp+arg_8], rdx
0x18000b74d  mov     [rsp+arg_0], rcx
0x18000b752  sub     rsp, 48h
0x18000b756  mov     rax, [rsp+48h+arg_0]
0x18000b75b  mov     rax, [rax]
0x18000b75e  mov     [rsp+48h+var_20], rax
0x18000b763  mov     rax, [rsp+48h+arg_0]
0x18000b768  mov     rax, [rax]
0x18000b76b  mov     rax, [rax]
0x18000b76e  mov     rax, [rax]
0x18000b771  mov     [rsp+48h+var_28], rax
0x18000b776  mov     rax, [rsp+48h+var_28]
0x18000b77b  mov     [rsp+48h+var_18], rax
0x18000b780  mov     r8, [rsp+48h+arg_8]
0x18000b785  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18000b78c  mov     rcx, [rsp+48h+var_20]
0x18000b791  mov     rax, [rsp+48h+var_18]
0x18000b796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b79b  nop
0x18000b79c  add     rsp, 48h
0x18000b7a0  retn
```
