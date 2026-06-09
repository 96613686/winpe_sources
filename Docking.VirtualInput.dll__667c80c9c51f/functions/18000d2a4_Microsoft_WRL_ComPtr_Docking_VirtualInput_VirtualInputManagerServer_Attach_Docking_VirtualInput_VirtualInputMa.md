# Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::Attach(Docking::VirtualInput::VirtualInputManagerServer *)

- ea: `0x18000d2a4`
- end: `0x18000d2e0`
- name: `?Attach@?$ComPtr@VVirtualInputManagerServer@VirtualInput@Docking@@@WRL@Microsoft@@QEAAXPEAVVirtualInputManagerServer@VirtualInput@Docking@@@Z`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b97c`

## callees

- `0x18000d2a4`
- `0x180010820`

## pseudocode

```c
Docking::VirtualInput::VirtualInputManagerServer **__fastcall Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::Attach(
        Docking::VirtualInput::VirtualInputManagerServer **a1,
        Docking::VirtualInput::VirtualInputManagerServer *a2)
{
  Docking::VirtualInput::VirtualInputManagerServer **result; // rax

  if ( *a1 )
    Docking::VirtualInput::VirtualInputManagerServer::Release(*a1);
  result = a1;
  *a1 = a2;
  return result;
}

```

## disassembly

```asm
0x18000d2a4  mov     [rsp+arg_8], rdx
0x18000d2a9  mov     [rsp+arg_0], rcx
0x18000d2ae  sub     rsp, 38h
0x18000d2b2  mov     rax, [rsp+38h+arg_0]
0x18000d2b7  cmp     qword ptr [rax], 0
0x18000d2bb  jz      short loc_18000D2CE
0x18000d2bd  mov     rax, [rsp+38h+arg_0]
0x18000d2c2  mov     rcx, [rax]; this
0x18000d2c5  call    ?Release@VirtualInputManagerServer@VirtualInput@Docking@@UEAAKXZ; Docking::VirtualInput::VirtualInputManagerServer::Release(void)
0x18000d2ca  mov     [rsp+38h+var_18], eax
0x18000d2ce  mov     rax, [rsp+38h+arg_0]
0x18000d2d3  mov     rcx, [rsp+38h+arg_8]
0x18000d2d8  mov     [rax], rcx
0x18000d2db  add     rsp, 38h
0x18000d2df  retn
```
