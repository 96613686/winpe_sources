# Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::CopyTo<IInspectable>(IInspectable * *)

- ea: `0x18000b70c`
- end: `0x18000b742`
- name: `??$CopyTo@UIInspectable@@@?$ComPtr@VVirtualInputManagerServer@VirtualInput@Docking@@@WRL@Microsoft@@QEBAJPEAPEAUIInspectable@@@Z`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012850`

## callees

- `0x180010430`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::CopyTo<IInspectable>(
        Docking::VirtualInput::VirtualInputManagerServer **a1,
        void **a2)
{
  return Docking::VirtualInput::VirtualInputManagerServer::QueryInterface(
           *a1,
           &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
           a2);
}

```

## disassembly

```asm
0x18000b70c  mov     [rsp+arg_8], rdx
0x18000b711  mov     [rsp+arg_0], rcx
0x18000b716  sub     rsp, 38h
0x18000b71a  mov     rax, [rsp+38h+arg_0]
0x18000b71f  mov     rax, [rax]
0x18000b722  mov     [rsp+38h+var_18], rax
0x18000b727  mov     r8, [rsp+38h+arg_8]; void **
0x18000b72c  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x18000b733  mov     rcx, [rsp+38h+var_18]; this
0x18000b738  call    ?QueryInterface@VirtualInputManagerServer@VirtualInput@Docking@@UEAAJAEBU_GUID@@PEAPEAX@Z; Docking::VirtualInput::VirtualInputManagerServer::QueryInterface(_GUID const &,void * *)
0x18000b73d  add     rsp, 38h
0x18000b741  retn
```
