# USBSTOR_FdoSetPowerSxCompletion

- ea: `0x1400109e0`
- end: `0x140010a95`
- name: `USBSTOR_FdoSetPowerSxCompletion`
- size: `181`
- prototype: `__int64 __fastcall(PVOID Context, PIRP Irp, POWER_STATE PowerState)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140003630`
- `0x140010664`
- `0x1400109e0`

## import_xrefs

- `ntoskrnl!PoRequestPowerIrp` at `0x140010a5c`
- `ntoskrnl!PoRequestPowerIrp` at `0x140010a5c`
- `ntoskrnl!IofCompleteRequest` at `0x140010a76`
- `ntoskrnl!IofCompleteRequest` at `0x140010a76`

## pseudocode

```c
__int64 __fastcall USBSTOR_FdoSetPowerSxCompletion(_QWORD *Context, PIRP Irp, POWER_STATE PowerState)
{
  __int64 v3; // rbp
  int v7; // eax
  unsigned int v8; // edi

  v3 = Context[8];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 177, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1129534278, Context, Irp, 0);
  v7 = PoRequestPowerIrp(*(PDEVICE_OBJECT *)(v3 + 16), 2u, PowerState, USBSTOR_FdoSetPowerCompletion, Context, 0);
  v8 = v7;
  if ( v7 >= 0 )
    return 3221225494LL;
  Irp->IoStatus.Status = v7;
  IofCompleteRequest(Irp, 0);
  return v8;
}

```

## disassembly

```asm
0x1400109e0  push    rbx
0x1400109e2  push    rbp
0x1400109e3  push    rsi
0x1400109e4  push    rdi
0x1400109e5  sub     rsp, 38h
0x1400109e9  mov     rbp, [rcx+40h]
0x1400109ed  mov     rsi, r8
0x1400109f0  mov     rbx, rdx
0x1400109f3  mov     rdi, rcx
0x1400109f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400109fd  lea     rax, WPP_GLOBAL_Control
0x140010a04  cmp     rcx, rax
0x140010a07  jz      short loc_140010A2B
0x140010a09  mov     eax, [rcx+2Ch]
0x140010a0c  test    al, 4
0x140010a0e  jz      short loc_140010A2B
0x140010a10  cmp     byte ptr [rcx+29h], 4
0x140010a14  jb      short loc_140010A2B
0x140010a16  mov     rcx, [rcx+18h]
0x140010a1a  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140010a21  mov     edx, 0B1h
0x140010a26  call    WPP_SF_
0x140010a2b  xor     r9d, r9d
0x140010a2e  mov     r8, rbx
0x140010a31  mov     rdx, rdi
0x140010a34  mov     ecx, 43535346h
0x140010a39  call    USBSTOR_LogEntry
0x140010a3e  mov     rcx, [rbp+10h]; DeviceObject
0x140010a42  lea     r9, USBSTOR_FdoSetPowerCompletion; CompletionFunction
0x140010a49  mov     r8d, esi; PowerState
0x140010a4c  mov     [rsp+58h+Irp], 0; Irp
0x140010a55  mov     dl, 2; MinorFunction
0x140010a57  mov     [rsp+58h+Context], rdi; Context
0x140010a5c  call    cs:__imp_PoRequestPowerIrp
0x140010a63  nop     dword ptr [rax+rax+00h]
0x140010a68  mov     edi, eax
0x140010a6a  test    eax, eax
0x140010a6c  jns     short loc_140010A86
0x140010a6e  xor     edx, edx; PriorityBoost
0x140010a70  mov     [rbx+30h], eax
0x140010a73  mov     rcx, rbx; Irp
0x140010a76  call    cs:__imp_IofCompleteRequest
0x140010a7d  nop     dword ptr [rax+rax+00h]
0x140010a82  mov     eax, edi
0x140010a84  jmp     short loc_140010A8B
0x140010a86  mov     eax, 0C0000016h
0x140010a8b  add     rsp, 38h
0x140010a8f  pop     rdi
0x140010a90  pop     rsi
0x140010a91  pop     rbp
0x140010a92  pop     rbx
0x140010a93  retn
```
