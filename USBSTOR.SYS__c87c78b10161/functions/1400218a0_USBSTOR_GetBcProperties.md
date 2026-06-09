# USBSTOR_GetBcProperties

- ea: `0x1400218a0`
- end: `0x1400218ef`
- name: `USBSTOR_GetBcProperties`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400226d0`

## callees

- `0x140011bf4`
- `0x1400218a0`
- `0x140022620`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400218d5`
- `ntoskrnl!IofCompleteRequest` at `0x1400218d5`

## pseudocode

```c
__int64 __fastcall USBSTOR_GetBcProperties(__int64 a1, IRP *a2)
{
  unsigned int BcProperties; // edi
  __int64 v4; // rcx

  BcProperties = -1073741808;
  if ( (unsigned __int8)USBSTOR_IsAvioEnabledDevice(*(_QWORD *)(a1 + 64)) )
    BcProperties = PortAvioGetBcProperties((PVOID)(v4 + 624));
  a2->IoStatus.Status = BcProperties;
  IofCompleteRequest(a2, 0);
  return BcProperties;
}

```

## disassembly

```asm
0x1400218a0  mov     [rsp+arg_0], rbx
0x1400218a5  push    rdi
0x1400218a6  sub     rsp, 20h
0x1400218aa  mov     rcx, [rcx+40h]
0x1400218ae  mov     rbx, rdx
0x1400218b1  mov     edi, 0C0000010h
0x1400218b6  call    USBSTOR_IsAvioEnabledDevice
0x1400218bb  test    al, al
0x1400218bd  jz      short loc_1400218CD
0x1400218bf  add     rcx, 270h; Signature
0x1400218c6  call    PortAvioGetBcProperties
0x1400218cb  mov     edi, eax
0x1400218cd  xor     edx, edx; PriorityBoost
0x1400218cf  mov     [rbx+30h], edi
0x1400218d2  mov     rcx, rbx; Irp
0x1400218d5  call    cs:__imp_IofCompleteRequest
0x1400218dc  nop     dword ptr [rax+rax+00h]
0x1400218e1  mov     rbx, [rsp+28h+arg_0]
0x1400218e6  mov     eax, edi
0x1400218e8  add     rsp, 20h
0x1400218ec  pop     rdi
0x1400218ed  retn
```
