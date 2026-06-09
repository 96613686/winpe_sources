# RfcommStartConnect

- ea: `0x14000c4d8`
- end: `0x14000c567`
- name: `RfcommStartConnect`
- size: `143`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400040b0`
- `0x140005900`
- `0x14000c0e0`

## callees

- `0x14000b270`
- `0x14000c4d8`
- `0x14001ae00`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000c54f`
- `ntoskrnl!KeSetEvent` at `0x14000c54f`

## pseudocode

```c
int __fastcall RfcommStartConnect(__int64 a1)
{
  PRKEVENT *v2; // rax
  PRKEVENT v3; // rdx
  PRKEVENT *v4; // rbx

  v2 = (PRKEVENT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                     WdfDriverGlobals,
                     a1,
                     off_1400220B0);
  v3 = v2[39];
  if ( v3 )
  {
    v2 = (PRKEVENT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, PRKEVENT, __int64 *))(WdfFunctions_01015 + 1616))(
                       WdfDriverGlobals,
                       v3,
                       off_140022128);
    v4 = v2;
    if ( *v2 )
    {
      BthHwEnterActiveMode(a1);
      LODWORD(v2) = KeSetEvent(*v4, 0, 0);
    }
  }
  return (int)v2;
}

```

## disassembly

```asm
0x14000c4d8  mov     [rsp+arg_0], rbx
0x14000c4dd  push    rdi
0x14000c4de  sub     rsp, 20h
0x14000c4e2  mov     rax, cs:WdfFunctions_01015
0x14000c4e9  mov     rdi, rcx
0x14000c4ec  mov     r8, cs:off_1400220B0
0x14000c4f3  mov     rdx, rcx
0x14000c4f6  mov     rcx, cs:WdfDriverGlobals
0x14000c4fd  mov     rax, [rax+650h]
0x14000c504  call    _guard_dispatch_icall
0x14000c509  mov     rdx, [rax+138h]
0x14000c510  test    rdx, rdx
0x14000c513  jz      short loc_14000C55B
0x14000c515  mov     rax, cs:WdfFunctions_01015
0x14000c51c  mov     r8, cs:off_140022128
0x14000c523  mov     rcx, cs:WdfDriverGlobals
0x14000c52a  mov     rax, [rax+650h]
0x14000c531  call    _guard_dispatch_icall
0x14000c536  mov     rbx, rax
0x14000c539  cmp     qword ptr [rax], 0
0x14000c53d  jz      short loc_14000C55B
0x14000c53f  mov     rcx, rdi
0x14000c542  call    BthHwEnterActiveMode
0x14000c547  mov     rcx, [rbx]; Event
0x14000c54a  xor     r8d, r8d; Wait
0x14000c54d  xor     edx, edx; Increment
0x14000c54f  call    cs:__imp_KeSetEvent
0x14000c556  nop     dword ptr [rax+rax+00h]
0x14000c55b  mov     rbx, [rsp+28h+arg_0]
0x14000c560  add     rsp, 20h
0x14000c564  pop     rdi
0x14000c565  retn
```
