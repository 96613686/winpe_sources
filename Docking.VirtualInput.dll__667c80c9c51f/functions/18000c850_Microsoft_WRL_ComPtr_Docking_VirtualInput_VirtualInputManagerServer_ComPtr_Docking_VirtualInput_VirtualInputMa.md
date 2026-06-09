# Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::~ComPtr<Docking::VirtualInput::VirtualInputManagerServer>(void)

- ea: `0x18000c850`
- end: `0x18000c869`
- name: `??1?$ComPtr@VVirtualInputManagerServer@VirtualInput@Docking@@@WRL@Microsoft@@QEAA@XZ`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012850`

## callees

- `0x18000ee40`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::~ComPtr<Docking::VirtualInput::VirtualInputManagerServer>(
        Docking::VirtualInput::VirtualInputManagerServer **a1)
{
  return Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::InternalRelease(a1);
}

```

## disassembly

```asm
0x18000c850  mov     [rsp+arg_0], rcx
0x18000c855  sub     rsp, 28h
0x18000c859  mov     rcx, [rsp+28h+arg_0]
0x18000c85e  call    ?InternalRelease@?$ComPtr@VVirtualInputManagerServer@VirtualInput@Docking@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::InternalRelease(void)
0x18000c863  nop
0x18000c864  add     rsp, 28h
0x18000c868  retn
```
