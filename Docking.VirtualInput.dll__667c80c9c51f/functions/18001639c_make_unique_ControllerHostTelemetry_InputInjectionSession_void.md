# make_unique<ControllerHostTelemetry::InputInjectionSession,>(void)

- ea: `0x18001639c`
- end: `0x180016402`
- name: `??$make_unique@VInputInjectionSession@ControllerHostTelemetry@@$$V@@YA?AV?$unique_ptr@VInputInjectionSession@ControllerHostTelemetry@@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@@std@@XZ`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800174bc`

## callees

- `0x180004188`
- `0x180014610`
- `0x18001639c`
- `0x1800168b0`

## pseudocode

```c
__int64 __fastcall make_unique<ControllerHostTelemetry::InputInjectionSession,>(__int64 a1)
{
  ControllerHostTelemetry::InputInjectionSession *v2; // [rsp+28h] [rbp-20h]
  __int64 v3; // [rsp+30h] [rbp-18h]

  v2 = (ControllerHostTelemetry::InputInjectionSession *)operator new(0x150u);
  if ( v2 )
  {
    v3 = ControllerHostTelemetry::InputInjectionSession::InputInjectionSession(v2);
    std::unique_ptr<Docking::VirtualInput::PtpInputManager>::unique_ptr<Docking::VirtualInput::PtpInputManager>(a1, v3);
  }
  else
  {
    std::unique_ptr<Docking::VirtualInput::PtpInputManager>::unique_ptr<Docking::VirtualInput::PtpInputManager>(a1, 0);
  }
  return a1;
}

```

## disassembly

```asm
0x18001639c  mov     [rsp+arg_0], rcx
0x1800163a1  sub     rsp, 48h
0x1800163a5  mov     [rsp+48h+var_28], 0
0x1800163ad  mov     ecx, 150h; Size
0x1800163b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800163b7  mov     [rsp+48h+var_20], rax
0x1800163bc  cmp     [rsp+48h+var_20], 0
0x1800163c2  jz      short loc_1800163D5
0x1800163c4  mov     rcx, [rsp+48h+var_20]; this
0x1800163c9  call    ??0InputInjectionSession@ControllerHostTelemetry@@QEAA@XZ; ControllerHostTelemetry::InputInjectionSession::InputInjectionSession(void)
0x1800163ce  mov     [rsp+48h+var_18], rax
0x1800163d3  jmp     short loc_1800163DE
0x1800163d5  mov     [rsp+48h+var_18], 0
0x1800163de  mov     rdx, [rsp+48h+var_18]
0x1800163e3  mov     rcx, [rsp+48h+arg_0]
0x1800163e8  call    ??$?0U?$default_delete@VPtpInputManager@VirtualInput@Docking@@@std@@$0A@@?$unique_ptr@VPtpInputManager@VirtualInput@Docking@@U?$default_delete@VPtpInputManager@VirtualInput@Docking@@@std@@@std@@QEAA@PEAVPtpInputManager@VirtualInput@Docking@@@Z; std::unique_ptr<Docking::VirtualInput::PtpInputManager>::unique_ptr<Docking::VirtualInput::PtpInputManager>(Docking::VirtualInput::PtpInputManager *)
0x1800163ed  mov     eax, [rsp+48h+var_28]
0x1800163f1  or      eax, 1
0x1800163f4  mov     [rsp+48h+var_28], eax
0x1800163f8  mov     rax, [rsp+48h+arg_0]
0x1800163fd  add     rsp, 48h
0x180016401  retn
```
