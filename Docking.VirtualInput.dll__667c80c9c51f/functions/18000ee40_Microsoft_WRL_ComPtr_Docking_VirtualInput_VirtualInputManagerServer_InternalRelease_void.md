# Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::InternalRelease(void)

- ea: `0x18000ee40`
- end: `0x18000ee89`
- name: `?InternalRelease@?$ComPtr@VVirtualInputManagerServer@VirtualInput@Docking@@@WRL@Microsoft@@IEAAKXZ`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c850`

## callees

- `0x18000ee40`
- `0x180010820`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::InternalRelease(
        Docking::VirtualInput::VirtualInputManagerServer **a1)
{
  unsigned int v2; // [rsp+20h] [rbp-18h]
  Docking::VirtualInput::VirtualInputManagerServer *v3; // [rsp+28h] [rbp-10h]

  v2 = 0;
  v3 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    return Docking::VirtualInput::VirtualInputManagerServer::Release(v3);
  }
  return v2;
}

```

## disassembly

```asm
0x18000ee40  mov     [rsp+arg_0], rcx
0x18000ee45  sub     rsp, 38h
0x18000ee49  mov     [rsp+38h+var_18], 0
0x18000ee51  mov     rax, [rsp+38h+arg_0]
0x18000ee56  mov     rax, [rax]
0x18000ee59  mov     [rsp+38h+var_10], rax
0x18000ee5e  cmp     [rsp+38h+var_10], 0
0x18000ee64  jz      short loc_18000EE80
0x18000ee66  mov     rax, [rsp+38h+arg_0]
0x18000ee6b  mov     qword ptr [rax], 0
0x18000ee72  mov     rcx, [rsp+38h+var_10]; this
0x18000ee77  call    ?Release@VirtualInputManagerServer@VirtualInput@Docking@@UEAAKXZ; Docking::VirtualInput::VirtualInputManagerServer::Release(void)
0x18000ee7c  mov     [rsp+38h+var_18], eax
0x18000ee80  mov     eax, [rsp+38h+var_18]
0x18000ee84  add     rsp, 38h
0x18000ee88  retn
```
