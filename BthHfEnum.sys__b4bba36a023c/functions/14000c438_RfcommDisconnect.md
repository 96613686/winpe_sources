# RfcommDisconnect

- ea: `0x14000c438`
- end: `0x14000c4d0`
- name: `RfcommDisconnect`
- size: `152`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400040b0`
- `0x140005830`
- `0x14000c030`

## callees

- `0x14000c438`
- `0x140014258`
- `0x14001ae00`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000c4b8`
- `ntoskrnl!KeSetEvent` at `0x14000c4b8`

## pseudocode

```c
LONG __fastcall RfcommDisconnect(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rdx

  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400220B0);
  v3 = *(_QWORD *)(v2 + 312);
  if ( v3
    && *(_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                     WdfDriverGlobals,
                     v3,
                     off_140022128)
                 + 8) )
  {
    return ScoUserDisconnectRequest(a1);
  }
  else
  {
    return KeSetEvent((PRKEVENT)(v2 + 216), 0, 0);
  }
}

```

## disassembly

```asm
0x14000c438  mov     [rsp+arg_0], rbx
0x14000c43d  push    rdi
0x14000c43e  sub     rsp, 20h
0x14000c442  mov     rax, cs:WdfFunctions_01015
0x14000c449  mov     rbx, rcx
0x14000c44c  mov     r8, cs:off_1400220B0
0x14000c453  mov     rdx, rcx
0x14000c456  mov     rcx, cs:WdfDriverGlobals
0x14000c45d  mov     rax, [rax+650h]
0x14000c464  call    _guard_dispatch_icall
0x14000c469  mov     rdi, rax
0x14000c46c  mov     rdx, [rax+138h]
0x14000c473  test    rdx, rdx
0x14000c476  jz      short loc_14000C4AC
0x14000c478  mov     rcx, cs:WdfFunctions_01015
0x14000c47f  mov     r8, cs:off_140022128
0x14000c486  mov     rax, [rcx+650h]
0x14000c48d  mov     rcx, cs:WdfDriverGlobals
0x14000c494  call    _guard_dispatch_icall
0x14000c499  mov     rdx, [rax+8]
0x14000c49d  test    rdx, rdx
0x14000c4a0  jz      short loc_14000C4AC
0x14000c4a2  mov     rcx, rbx
0x14000c4a5  call    ScoUserDisconnectRequest
0x14000c4aa  jmp     short loc_14000C4C4
0x14000c4ac  lea     rcx, [rdi+0D8h]; Event
0x14000c4b3  xor     r8d, r8d; Wait
0x14000c4b6  xor     edx, edx; Increment
0x14000c4b8  call    cs:__imp_KeSetEvent
0x14000c4bf  nop     dword ptr [rax+rax+00h]
0x14000c4c4  mov     rbx, [rsp+28h+arg_0]
0x14000c4c9  add     rsp, 20h
0x14000c4cd  pop     rdi
0x14000c4ce  retn
```
