# Crashdump_UsbDevice_SendResetDeviceCommand

- ea: `0x140055fc8`
- end: `0x1400560b1`
- name: `Crashdump_UsbDevice_SendResetDeviceCommand`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400559a8`

## callees

- `0x140053f98`
- `0x140055fc8`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140055fe6`
- `ntoskrnl!DbgPrintEx` at `0x140056037`
- `ntoskrnl!DbgPrintEx` at `0x140056072`
- `ntoskrnl!DbgPrintEx` at `0x140056097`
- `ntoskrnl!DbgPrintEx` at `0x140055fe6`
- `ntoskrnl!DbgPrintEx` at `0x140056037`
- `ntoskrnl!DbgPrintEx` at `0x140056072`
- `ntoskrnl!DbgPrintEx` at `0x140056097`

## string_xrefs

- `0x140055fd5`: `XHCIDUMP: Crashdump_UsbDevice_SendResetDeviceCommand: begin\n`
- `0x140056026`: `XHCIDUMP: SlotId %u: Reset device command failed\n`
- `0x14005606b`: `XHCIDUMP: SlotId %u: After reset device command, slot state is not default, it is %u\n`
- `0x140056086`: `XHCIDUMP: Crashdump_UsbDevice_SendResetDeviceCommand: end 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_UsbDevice_SendResetDeviceCommand(__int64 a1)
{
  __int64 *v2; // rcx
  int v3; // eax
  int v4; // edi
  int v5; // r8d
  __int128 v7; // [rsp+30h] [rbp-18h] BYREF

  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_SendResetDeviceCommand: begin\n");
  v2 = *(__int64 **)(a1 + 16);
  v3 = (*(unsigned __int8 *)(a1 + 56) << 24) | 0x4400;
  v7 = 0;
  HIDWORD(v7) = v3;
  v4 = Crashdump_Command_SendCommand(v2, (__int64)&v7, 0);
  if ( v4 >= 0 )
  {
    v5 = *(_DWORD *)(*(_QWORD *)(a1 + 72) + 12LL) >> 27;
    if ( v5 != 1 )
    {
      DbgPrintEx(
        0x93u,
        1u,
        "XHCIDUMP: SlotId %u: After reset device command, slot state is not default, it is %u\n",
        *(unsigned __int8 *)(a1 + 56),
        v5);
      v4 = -1073741630;
    }
  }
  else
  {
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: SlotId %u: Reset device command failed\n", *(unsigned __int8 *)(a1 + 56));
  }
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_SendResetDeviceCommand: end 0x%X\n", v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140055fc8  mov     [rsp+arg_0], rbx
0x140055fcd  push    rdi
0x140055fce  sub     rsp, 40h
0x140055fd2  mov     rbx, rcx
0x140055fd5  lea     r8, aXhcidumpCrashd_64; "XHCIDUMP: Crashdump_UsbDevice_SendReset"...
0x140055fdc  mov     ecx, 93h; ComponentId
0x140055fe1  mov     edx, 3; Level
0x140055fe6  call    cs:__imp_DbgPrintEx
0x140055fed  nop     dword ptr [rax+rax+00h]
0x140055ff2  movzx   eax, byte ptr [rbx+38h]
0x140055ff6  lea     rdx, [rsp+48h+var_18]
0x140055ffb  mov     rcx, [rbx+10h]
0x140055fff  xorps   xmm0, xmm0
0x140056002  shl     eax, 18h
0x140056005  xor     r8d, r8d
0x140056008  or      eax, 4400h
0x14005600d  movups  [rsp+48h+var_18], xmm0
0x140056012  mov     dword ptr [rsp+48h+var_18+0Ch], eax
0x140056016  call    Crashdump_Command_SendCommand
0x14005601b  mov     edi, eax
0x14005601d  test    eax, eax
0x14005601f  jns     short loc_140056045
0x140056021  movzx   r9d, byte ptr [rbx+38h]
0x140056026  lea     r8, aXhcidumpSlotid_2; "XHCIDUMP: SlotId %u: Reset device comma"...
0x14005602d  mov     edx, 1; Level
0x140056032  mov     ecx, 93h; ComponentId
0x140056037  call    cs:__imp_DbgPrintEx
0x14005603e  nop     dword ptr [rax+rax+00h]
0x140056043  jmp     short loc_140056083
0x140056045  mov     rax, [rbx+48h]
0x140056049  mov     r8d, [rax+0Ch]
0x14005604d  shr     r8d, 1Bh
0x140056051  cmp     r8d, 1
0x140056055  jz      short loc_140056083
0x140056057  movzx   r9d, byte ptr [rbx+38h]
0x14005605c  mov     edx, 1; Level
0x140056061  mov     [rsp+48h+var_28], r8d
0x140056066  mov     ecx, 93h; ComponentId
0x14005606b  lea     r8, aXhcidumpSlotid_0; "XHCIDUMP: SlotId %u: After reset device"...
0x140056072  call    cs:__imp_DbgPrintEx
0x140056079  nop     dword ptr [rax+rax+00h]
0x14005607e  mov     edi, 0C00000C2h
0x140056083  mov     r9d, edi
0x140056086  lea     r8, aXhcidumpCrashd_26; "XHCIDUMP: Crashdump_UsbDevice_SendReset"...
0x14005608d  mov     edx, 3; Level
0x140056092  mov     ecx, 93h; ComponentId
0x140056097  call    cs:__imp_DbgPrintEx
0x14005609e  nop     dword ptr [rax+rax+00h]
0x1400560a3  mov     rbx, [rsp+48h+arg_0]
0x1400560a8  mov     eax, edi
0x1400560aa  add     rsp, 40h
0x1400560ae  pop     rdi
0x1400560af  retn
```
