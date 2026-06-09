# Crashdump_UsbDevice_ReConfigureOnPortReset

- ea: `0x1400559a8`
- end: `0x140055a9f`
- name: `Crashdump_UsbDevice_ReConfigureOnPortReset`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140052480`

## callees

- `0x140054cf4`
- `0x1400559a8`
- `0x140055fc8`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1400559cd`
- `ntoskrnl!DbgPrintEx` at `0x140055a46`
- `ntoskrnl!DbgPrintEx` at `0x140055a80`
- `ntoskrnl!DbgPrintEx` at `0x1400559cd`
- `ntoskrnl!DbgPrintEx` at `0x140055a46`
- `ntoskrnl!DbgPrintEx` at `0x140055a80`

## string_xrefs

- `0x1400559b9`: `XHCIDUMP: Crashdump_UsbDevice_ReConfigureOnPortReset: begin\n`
- `0x140055a6f`: `XHCIDUMP: Crashdump_UsbDevice_ReConfigureOnPortReset: end 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_UsbDevice_ReConfigureOnPortReset(__int64 a1, int a2)
{
  __int64 v4; // r9
  int v5; // ebx

  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_ReConfigureOnPortReset: begin\n");
  v4 = *(_QWORD *)(a1 + 72);
  DbgPrintEx(
    0x93u,
    3u,
    "XHCIDUMP: Slot %u: RH %u, RS %u, Speed %u, IsHub %u, NumEntries %u, Addr %u, State %u\n",
    *(unsigned __int8 *)(a1 + 56),
    *(unsigned __int8 *)(v4 + 6),
    *(_DWORD *)v4 & 0xFFFFF,
    (*(_DWORD *)v4 >> 20) & 0xF,
    (*(_DWORD *)v4 >> 26) & 1,
    *(_DWORD *)v4 >> 27,
    (unsigned __int8)*(_DWORD *)(v4 + 12),
    *(_DWORD *)(v4 + 12) >> 27);
  v5 = Crashdump_UsbDevice_SendResetDeviceCommand(a1);
  if ( v5 >= 0 )
    v5 = Crashdump_UsbDevice_Configure(a1, a2);
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_ReConfigureOnPortReset: end 0x%X\n", v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400559a8  mov     [rsp+arg_0], rbx
0x1400559ad  mov     [rsp+arg_8], rsi
0x1400559b2  push    rdi
0x1400559b3  sub     rsp, 60h
0x1400559b7  mov     esi, edx
0x1400559b9  lea     r8, aXhcidumpCrashd_36; "XHCIDUMP: Crashdump_UsbDevice_ReConfigu"...
0x1400559c0  mov     rdi, rcx
0x1400559c3  mov     edx, 3; Level
0x1400559c8  mov     ecx, 93h; ComponentId
0x1400559cd  call    cs:__imp_DbgPrintEx
0x1400559d4  nop     dword ptr [rax+rax+00h]
0x1400559d9  mov     r9, [rdi+48h]
0x1400559dd  mov     ebx, [r9]
0x1400559e0  mov     r10d, ebx
0x1400559e3  mov     eax, [r9+0Ch]
0x1400559e7  mov     edx, ebx
0x1400559e9  movzx   r8d, al
0x1400559ed  mov     r11d, eax
0x1400559f0  movzx   eax, byte ptr [r9+6]
0x1400559f5  mov     ecx, ebx
0x1400559f7  movzx   r9d, byte ptr [rdi+38h]
0x1400559fc  and     ebx, 0FFFFFh
0x140055a02  shr     edx, 1Ah
0x140055a05  shr     ecx, 14h
0x140055a08  and     edx, 1
0x140055a0b  and     ecx, 0Fh
0x140055a0e  shr     r11d, 1Bh
0x140055a12  mov     [rsp+68h+var_18], r11d
0x140055a17  mov     [rsp+68h+var_20], r8d
0x140055a1c  lea     r8, aXhcidumpSlotUR; "XHCIDUMP: Slot %u: RH %u, RS %u, Speed "...
0x140055a23  shr     r10d, 1Bh
0x140055a27  mov     [rsp+68h+var_28], r10d
0x140055a2c  mov     [rsp+68h+var_30], edx
0x140055a30  mov     edx, 3; Level
0x140055a35  mov     [rsp+68h+var_38], ecx
0x140055a39  mov     ecx, 93h; ComponentId
0x140055a3e  mov     [rsp+68h+var_40], ebx
0x140055a42  mov     [rsp+68h+var_48], eax
0x140055a46  call    cs:__imp_DbgPrintEx
0x140055a4d  nop     dword ptr [rax+rax+00h]
0x140055a52  mov     rcx, rdi
0x140055a55  call    Crashdump_UsbDevice_SendResetDeviceCommand
0x140055a5a  mov     ebx, eax
0x140055a5c  test    eax, eax
0x140055a5e  js      short loc_140055A6C
0x140055a60  mov     edx, esi
0x140055a62  mov     rcx, rdi
0x140055a65  call    Crashdump_UsbDevice_Configure
0x140055a6a  mov     ebx, eax
0x140055a6c  mov     r9d, ebx
0x140055a6f  lea     r8, aXhcidumpCrashd_23; "XHCIDUMP: Crashdump_UsbDevice_ReConfigu"...
0x140055a76  mov     edx, 3; Level
0x140055a7b  mov     ecx, 93h; ComponentId
0x140055a80  call    cs:__imp_DbgPrintEx
0x140055a87  nop     dword ptr [rax+rax+00h]
0x140055a8c  mov     rsi, [rsp+68h+arg_8]
0x140055a91  mov     eax, ebx
0x140055a93  mov     rbx, [rsp+68h+arg_0]
0x140055a98  add     rsp, 60h
0x140055a9c  pop     rdi
0x140055a9d  retn
```
