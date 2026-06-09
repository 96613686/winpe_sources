# Microsoft::WRL::operator==<Docking::VirtualInput::VirtualTouchPadServer>(Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualTouchPadServer> const &,std::nullptr_t)

- ea: `0x18000b394`
- end: `0x18000b3cc`
- name: `??$?8VVirtualTouchPadServer@VirtualInput@Docking@@@WRL@Microsoft@@YA_NAEBV?$ComPtr@VVirtualTouchPadServer@VirtualInput@Docking@@@01@$$T@Z`
- size: `56`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012850`
- `0x180012960`
- `0x1800148f8`

## callees

- `0x18000b394`
- `0x18000cdc0`

## pseudocode

```c
bool __fastcall Microsoft::WRL::operator==<Docking::VirtualInput::VirtualTouchPadServer>(__int64 a1)
{
  return Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get(a1) == 0;
}

```

## disassembly

```asm
0x18000b394  mov     [rsp+arg_8], rdx
0x18000b399  mov     [rsp+arg_0], rcx
0x18000b39e  sub     rsp, 38h
0x18000b3a2  mov     rcx, [rsp+38h+arg_0]
0x18000b3a7  call    ?Get@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@QEBAPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@XZ; Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get(void)
0x18000b3ac  test    rax, rax
0x18000b3af  jnz     short loc_18000B3BB
0x18000b3b1  mov     [rsp+38h+var_18], 1
0x18000b3b9  jmp     short loc_18000B3C3
0x18000b3bb  mov     [rsp+38h+var_18], 0
0x18000b3c3  mov     al, byte ptr [rsp+38h+var_18]
0x18000b3c7  add     rsp, 38h
0x18000b3cb  retn
```
