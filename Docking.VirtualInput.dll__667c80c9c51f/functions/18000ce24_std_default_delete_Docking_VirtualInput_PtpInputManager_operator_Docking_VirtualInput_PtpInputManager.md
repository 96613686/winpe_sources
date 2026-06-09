# std::default_delete<Docking::VirtualInput::PtpInputManager>::operator()(Docking::VirtualInput::PtpInputManager *)

- ea: `0x18000ce24`
- end: `0x18000ce87`
- name: `??R?$default_delete@VPtpInputManager@VirtualInput@Docking@@@std@@QEBAXPEAVPtpInputManager@VirtualInput@Docking@@@Z`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cb20`
- `0x180015378`

## callees

- `0x18000ce24`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall std::default_delete<Docking::VirtualInput::PtpInputManager>::operator()(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, __int64))
{
  __int64 result; // rax

  result = (__int64)a2;
  if ( a2 )
    return (**a2)(a2, 1);
  return result;
}

```

## disassembly

```asm
0x18000ce24  mov     [rsp+arg_8], rdx
0x18000ce29  mov     [rsp+arg_0], rcx
0x18000ce2e  sub     rsp, 48h
0x18000ce32  mov     rax, [rsp+48h+arg_8]
0x18000ce37  mov     [rsp+48h+var_28], rax
0x18000ce3c  cmp     [rsp+48h+var_28], 0
0x18000ce42  jz      short loc_18000CE79
0x18000ce44  mov     rax, [rsp+48h+var_28]
0x18000ce49  mov     rax, [rax]
0x18000ce4c  mov     rax, [rax]
0x18000ce4f  mov     [rsp+48h+var_20], rax
0x18000ce54  mov     rax, [rsp+48h+var_20]
0x18000ce59  mov     [rsp+48h+var_18], rax
0x18000ce5e  mov     edx, 1
0x18000ce63  mov     rcx, [rsp+48h+var_28]
0x18000ce68  mov     rax, [rsp+48h+var_18]
0x18000ce6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce72  mov     [rsp+48h+var_10], rax
0x18000ce77  jmp     short loc_18000CE82
0x18000ce79  mov     [rsp+48h+var_10], 0
0x18000ce82  add     rsp, 48h
0x18000ce86  retn
```
