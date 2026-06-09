# ??$Fill@$$V@?$_tlgDataDescInit@U?$_tlgIndexSequence@$0A@$S@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z

- ea: `0x180001d98`
- end: `0x180001dac`
- name: `??$Fill@$$V@?$_tlgDataDescInit@U?$_tlgIndexSequence@$0A@$S@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002900`

## callees

- `0x180001d40`

## pseudocode

```c
__int64 ___Fill___V____tlgDataDescInit_U___tlgIndexSequence__0A__S____SAXPEAU_EVENT_DATA_DESCRIPTOR___Z()
{
  return Microsoft::WRL::Details::VerifyInterfaceHelper<1,Docking::VirtualInput::ITouch,0,0>::Verify();
}

```

## disassembly

```asm
0x180001d98  mov     [rsp+arg_0], rcx
0x180001d9d  sub     rsp, 28h
0x180001da1  call    ?Verify@?$VerifyInterfaceHelper@$00UITouch@VirtualInput@Docking@@$0A@$0A@@Details@WRL@Microsoft@@SAXXZ; Microsoft::WRL::Details::VerifyInterfaceHelper<1,Docking::VirtualInput::ITouch,0,0>::Verify(void)
0x180001da6  nop
0x180001da7  add     rsp, 28h
0x180001dab  retn
```
