# make_unique<Docking::VirtualInput::PtpInputManager,Docking::VirtualInput::VirtualTouchPadOptions * &,HMONITOR__ * &>(Docking::VirtualInput::VirtualTouchPadOptions * &,HMONITOR__ * &)

- ea: `0x18001477c`
- end: `0x180014824`
- name: `??$make_unique@VPtpInputManager@VirtualInput@Docking@@AEAPEAUVirtualTouchPadOptions@23@AEAPEAUHMONITOR__@@@@YA?AV?$unique_ptr@VPtpInputManager@VirtualInput@Docking@@U?$default_delete@VPtpInputManager@VirtualInput@Docking@@@std@@@std@@AEAPEAUVirtualTouchPadOptions@VirtualInput@Docking@@AEAPEAUHMONITOR__@@@Z`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014d08`

## callees

- `0x180004188`
- `0x18000b810`
- `0x180014610`
- `0x18001477c`
- `0x18001a114`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall make_unique<Docking::VirtualInput::PtpInputManager,Docking::VirtualInput::VirtualTouchPadOptions * &,HMONITOR__ * &>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  Docking::VirtualInput::PtpInputManager *v4; // [rsp+28h] [rbp-30h]
  __int64 v5; // [rsp+30h] [rbp-28h]
  HMONITOR v6; // [rsp+38h] [rbp-20h]
  struct Docking::VirtualInput::VirtualTouchPadOptions *v7; // [rsp+40h] [rbp-18h]

  v4 = (Docking::VirtualInput::PtpInputManager *)operator new(0x78u);
  if ( v4 )
  {
    v6 = *(HMONITOR *)Microsoft::WRL::Details::Forward<std::nullptr_t>(a3);
    v7 = *(struct Docking::VirtualInput::VirtualTouchPadOptions **)Microsoft::WRL::Details::Forward<std::nullptr_t>(a2);
    v5 = Docking::VirtualInput::PtpInputManager::PtpInputManager(v4, v7, v6);
  }
  else
  {
    v5 = 0;
  }
  std::unique_ptr<Docking::VirtualInput::PtpInputManager>::unique_ptr<Docking::VirtualInput::PtpInputManager>(a1, v5);
  return a1;
}

```

## disassembly

```asm
0x18001477c  mov     [rsp+arg_10], r8
0x180014781  mov     [rsp+arg_8], rdx
0x180014786  mov     [rsp+arg_0], rcx
0x18001478b  sub     rsp, 58h
0x18001478f  mov     [rsp+58h+var_38], 0
0x180014797  mov     ecx, 78h ; 'x'; Size
0x18001479c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800147a1  mov     [rsp+58h+var_30], rax
0x1800147a6  cmp     [rsp+58h+var_30], 0
0x1800147ac  jz      short loc_1800147ED
0x1800147ae  mov     rcx, [rsp+58h+arg_10]
0x1800147b3  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x1800147b8  mov     rax, [rax]
0x1800147bb  mov     [rsp+58h+var_20], rax
0x1800147c0  mov     rcx, [rsp+58h+arg_8]
0x1800147c5  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x1800147ca  mov     rax, [rax]
0x1800147cd  mov     [rsp+58h+var_18], rax
0x1800147d2  mov     r8, [rsp+58h+var_20]; HMONITOR
0x1800147d7  mov     rdx, [rsp+58h+var_18]; struct Docking::VirtualInput::VirtualTouchPadOptions *
0x1800147dc  mov     rcx, [rsp+58h+var_30]; this
0x1800147e1  call    ??0PtpInputManager@VirtualInput@Docking@@QEAA@PEBUVirtualTouchPadOptions@12@PEAUHMONITOR__@@@Z; Docking::VirtualInput::PtpInputManager::PtpInputManager(Docking::VirtualInput::VirtualTouchPadOptions const *,HMONITOR__ *)
0x1800147e6  mov     [rsp+58h+var_28], rax
0x1800147eb  jmp     short loc_1800147F6
0x1800147ed  mov     [rsp+58h+var_28], 0
0x1800147f6  mov     rax, [rsp+58h+var_28]
0x1800147fb  mov     [rsp+58h+var_10], rax
0x180014800  mov     rdx, [rsp+58h+var_10]
0x180014805  mov     rcx, [rsp+58h+arg_0]
0x18001480a  call    ??$?0U?$default_delete@VPtpInputManager@VirtualInput@Docking@@@std@@$0A@@?$unique_ptr@VPtpInputManager@VirtualInput@Docking@@U?$default_delete@VPtpInputManager@VirtualInput@Docking@@@std@@@std@@QEAA@PEAVPtpInputManager@VirtualInput@Docking@@@Z; std::unique_ptr<Docking::VirtualInput::PtpInputManager>::unique_ptr<Docking::VirtualInput::PtpInputManager>(Docking::VirtualInput::PtpInputManager *)
0x18001480f  mov     eax, [rsp+58h+var_38]
0x180014813  or      eax, 1
0x180014816  mov     [rsp+58h+var_38], eax
0x18001481a  mov     rax, [rsp+58h+arg_0]
0x18001481f  add     rsp, 58h
0x180014823  retn
```
