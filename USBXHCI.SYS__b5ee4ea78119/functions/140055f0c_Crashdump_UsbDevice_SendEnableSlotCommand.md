# Crashdump_UsbDevice_SendEnableSlotCommand

- ea: `0x140055f0c`
- end: `0x140055fbf`
- name: `Crashdump_UsbDevice_SendEnableSlotCommand`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140055878`

## callees

- `0x140053f98`
- `0x140055f0c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140055f32`
- `ntoskrnl!DbgPrintEx` at `0x140055f85`
- `ntoskrnl!DbgPrintEx` at `0x140055fa5`
- `ntoskrnl!DbgPrintEx` at `0x140055f32`
- `ntoskrnl!DbgPrintEx` at `0x140055f85`
- `ntoskrnl!DbgPrintEx` at `0x140055fa5`

## string_xrefs

- `0x140055f19`: `XHCIDUMP: Crashdump_UsbDevice_SendEnableSlotCommand: begin\n`
- `0x140055f94`: `XHCIDUMP: Crashdump_UsbDevice_SendEnableSlotCommand: end 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_UsbDevice_SendEnableSlotCommand(__int64 a1)
{
  __int64 *v2; // rcx
  int v3; // ebx
  int v4; // r9d
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  __int128 v7; // [rsp+30h] [rbp-18h] BYREF

  v7 = 0;
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_SendEnableSlotCommand: begin\n");
  v2 = *(__int64 **)(a1 + 16);
  v6 = 0;
  HIDWORD(v6) = 9216;
  v3 = Crashdump_Command_SendCommand(v2, (__int64)&v6, &v7);
  if ( v3 >= 0 )
  {
    v4 = HIBYTE(HIDWORD(v7));
    *(_BYTE *)(a1 + 56) = HIBYTE(v7);
    DbgPrintEx(0x93u, 3u, "XHCIDUMP: SlotId is %u\n", v4);
  }
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_SendEnableSlotCommand: end 0x%X\n", v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140055f0c  mov     [rsp+arg_0], rbx
0x140055f11  push    rdi
0x140055f12  sub     rsp, 40h
0x140055f16  mov     rdi, rcx
0x140055f19  lea     r8, aXhcidumpCrashd_38; "XHCIDUMP: Crashdump_UsbDevice_SendEnabl"...
0x140055f20  xorps   xmm0, xmm0
0x140055f23  mov     ecx, 93h; ComponentId
0x140055f28  mov     edx, 3; Level
0x140055f2d  movups  [rsp+48h+var_18], xmm0
0x140055f32  call    cs:__imp_DbgPrintEx
0x140055f39  nop     dword ptr [rax+rax+00h]
0x140055f3e  mov     rcx, [rdi+10h]
0x140055f42  lea     r8, [rsp+48h+var_18]
0x140055f47  xorps   xmm0, xmm0
0x140055f4a  lea     rdx, [rsp+48h+var_28]
0x140055f4f  movups  [rsp+48h+var_28], xmm0
0x140055f54  mov     dword ptr [rsp+48h+var_28+0Ch], 2400h
0x140055f5c  call    Crashdump_Command_SendCommand
0x140055f61  mov     ebx, eax
0x140055f63  test    eax, eax
0x140055f65  js      short loc_140055F91
0x140055f67  mov     r9d, dword ptr [rsp+48h+var_18+0Ch]
0x140055f6c  lea     r8, aXhcidumpSlotid_3; "XHCIDUMP: SlotId is %u\n"
0x140055f73  shr     r9d, 18h
0x140055f77  mov     edx, 3; Level
0x140055f7c  mov     ecx, 93h; ComponentId
0x140055f81  mov     [rdi+38h], r9b
0x140055f85  call    cs:__imp_DbgPrintEx
0x140055f8c  nop     dword ptr [rax+rax+00h]
0x140055f91  mov     r9d, ebx
0x140055f94  lea     r8, aXhcidumpCrashd_74; "XHCIDUMP: Crashdump_UsbDevice_SendEnabl"...
0x140055f9b  mov     edx, 3; Level
0x140055fa0  mov     ecx, 93h; ComponentId
0x140055fa5  call    cs:__imp_DbgPrintEx
0x140055fac  nop     dword ptr [rax+rax+00h]
0x140055fb1  mov     eax, ebx
0x140055fb3  mov     rbx, [rsp+48h+arg_0]
0x140055fb8  add     rsp, 40h
0x140055fbc  pop     rdi
0x140055fbd  retn
```
