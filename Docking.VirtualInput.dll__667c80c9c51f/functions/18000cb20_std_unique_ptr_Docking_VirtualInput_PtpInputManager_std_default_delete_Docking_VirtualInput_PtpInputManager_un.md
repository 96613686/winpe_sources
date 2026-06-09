# std::unique_ptr<Docking::VirtualInput::PtpInputManager,std::default_delete<Docking::VirtualInput::PtpInputManager>>::~unique_ptr<Docking::VirtualInput::PtpInputManager,std::default_delete<Docking::VirtualInput::PtpInputManager>>(void)

- ea: `0x18000cb20`
- end: `0x18000cb68`
- name: `??1?$unique_ptr@VPtpInputManager@VirtualInput@Docking@@U?$default_delete@VPtpInputManager@VirtualInput@Docking@@@std@@@std@@QEAA@XZ`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cc80`
- `0x180014d08`

## callees

- `0x18000b810`
- `0x18000cb20`
- `0x18000ce24`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<Docking::VirtualInput::PtpInputManager>::~unique_ptr<Docking::VirtualInput::PtpInputManager>(
        _QWORD *a1)
{
  __int64 result; // rax
  __int64 v2; // [rsp+28h] [rbp-10h]

  result = (__int64)a1;
  if ( *a1 )
  {
    v2 = Microsoft::WRL::Details::Forward<std::nullptr_t>(a1);
    return std::default_delete<Docking::VirtualInput::PtpInputManager>::operator()(v2, *a1);
  }
  return result;
}

```

## disassembly

```asm
0x18000cb20  mov     [rsp+arg_0], rcx
0x18000cb25  sub     rsp, 38h
0x18000cb29  mov     rax, [rsp+38h+arg_0]
0x18000cb2e  cmp     qword ptr [rax], 0
0x18000cb32  jz      short loc_18000CB63
0x18000cb34  mov     rax, [rsp+38h+arg_0]
0x18000cb39  mov     rcx, rax
0x18000cb3c  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x18000cb41  mov     [rsp+38h+var_10], rax
0x18000cb46  mov     rax, [rsp+38h+arg_0]
0x18000cb4b  mov     rax, [rax]
0x18000cb4e  mov     [rsp+38h+var_18], rax
0x18000cb53  mov     rdx, [rsp+38h+var_18]
0x18000cb58  mov     rcx, [rsp+38h+var_10]
0x18000cb5d  call    ??R?$default_delete@VPtpInputManager@VirtualInput@Docking@@@std@@QEBAXPEAVPtpInputManager@VirtualInput@Docking@@@Z; std::default_delete<Docking::VirtualInput::PtpInputManager>::operator()(Docking::VirtualInput::PtpInputManager *)
0x18000cb62  nop
0x18000cb63  add     rsp, 38h
0x18000cb67  retn
```
