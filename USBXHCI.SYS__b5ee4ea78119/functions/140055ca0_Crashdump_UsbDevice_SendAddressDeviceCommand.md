# Crashdump_UsbDevice_SendAddressDeviceCommand

- ea: `0x140055ca0`
- end: `0x140055f06`
- name: `Crashdump_UsbDevice_SendAddressDeviceCommand`
- size: `614`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140054cf4`

## callees

- `0x140053f98`
- `0x140055ca0`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140055cbf`
- `ntoskrnl!DbgPrintEx` at `0x140055e1b`
- `ntoskrnl!DbgPrintEx` at `0x140055e96`
- `ntoskrnl!DbgPrintEx` at `0x140055ecc`
- `ntoskrnl!DbgPrintEx` at `0x140055eee`
- `ntoskrnl!DbgPrintEx` at `0x140055cbf`
- `ntoskrnl!DbgPrintEx` at `0x140055e1b`
- `ntoskrnl!DbgPrintEx` at `0x140055e96`
- `ntoskrnl!DbgPrintEx` at `0x140055ecc`
- `ntoskrnl!DbgPrintEx` at `0x140055eee`

## string_xrefs

- `0x140055cac`: `XHCIDUMP: Crashdump_UsbDevice_SendAddressDeviceCommand: begin\n`
- `0x140055e0d`: `XHCIDUMP: SlotId %u: Address device command failed\n`
- `0x140055ec5`: `XHCIDUMP: SlotId %u: After address device command, slot state is not addressed, it is %u\n`
- `0x140055ee0`: `XHCIDUMP: Crashdump_UsbDevice_SendAddressDeviceCommand: end 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_UsbDevice_SendAddressDeviceCommand(__int64 *a1)
{
  __int64 v2; // rbx
  __int64 v3; // r10
  int v4; // r9d
  __int64 v5; // r8
  int v6; // ecx
  int v7; // edx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 *v11; // rcx
  int v12; // esi
  __int64 v13; // r9
  int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp-38h] BYREF
  int v17; // [rsp+68h] [rbp-30h]
  unsigned __int32 v18; // [rsp+6Ch] [rbp-2Ch]

  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_SendAddressDeviceCommand: begin\n");
  v2 = *a1;
  memset(*(void **)(*a1 + 472), 0, *(unsigned int *)(*a1 + 480));
  v3 = *(_QWORD *)(v2 + 472);
  *(_DWORD *)(v3 + 4) |= 3u;
  v4 = *(_DWORD *)(*(_QWORD *)a1[1] + 104LL) & 4;
  v5 = v4 != 0 ? 0x20 : 0;
  v6 = *(_DWORD *)(v5 + v3 + 32) ^ (*((_DWORD *)a1 + 20) ^ *(_DWORD *)(v5 + v3 + 32)) & 0xFFFFF;
  *(_DWORD *)(v5 + v3 + 32) = v6;
  v7 = v6 ^ (*((_DWORD *)a1 + 20) ^ v6) & 0xF00000;
  *(_DWORD *)(v5 + v3 + 32) = v7;
  *(_BYTE *)(v5 + v3 + 38) = *((_BYTE *)a1 + 86);
  *(_DWORD *)(v5 + v3 + 32) = v7 & 0x7FFFFFF | 0x8000000;
  v8 = a1[15];
  v9 = v4 != 0 ? 0x40 : 0;
  *(_DWORD *)(v9 + v3 + 68) ^= (*(_DWORD *)(v8 + 52) ^ *(_DWORD *)(v9 + v3 + 68)) & 0x38;
  *(_WORD *)(v9 + v3 + 70) = *(_WORD *)(v8 + 54);
  *(_DWORD *)(v9 + v3 + 68) ^= (*(_DWORD *)(v8 + 52) ^ *(_DWORD *)(v9 + v3 + 68)) & 6;
  if ( *(_BYTE *)(v8 + 128) )
    v10 = *(_QWORD *)(v8 + 136);
  else
    v10 = *(_QWORD *)(v8 + 24LL * *(unsigned int *)(v8 + 160) + 80);
  v17 = 0;
  *(_QWORD *)((v4 != 0 ? 0x40 : 0) + v3 + 72) = v10 | 1;
  v11 = (__int64 *)a1[2];
  v18 = _byteswap_ulong(*((unsigned __int8 *)a1 + 56)) | 0x2C00;
  v16 = *(_QWORD *)(v2 + 464);
  v12 = Crashdump_Command_SendCommand(v11, (__int64)&v16, 0);
  if ( v12 >= 0 )
  {
    v13 = a1[9];
    DbgPrintEx(
      0x93u,
      3u,
      "XHCIDUMP: Slot %u: RH %u, RS %u, Speed %u, IsHub %u, NumEntries %u, Addr %u, State %u\n",
      *((unsigned __int8 *)a1 + 56),
      *(unsigned __int8 *)(v13 + 6),
      *(_DWORD *)v13 & 0xFFFFF,
      (*(_DWORD *)v13 >> 20) & 0xF,
      (*(_DWORD *)v13 >> 26) & 1,
      *(_DWORD *)v13 >> 27,
      (unsigned __int8)*(_DWORD *)(v13 + 12),
      *(_DWORD *)(v13 + 12) >> 27);
    v14 = *(_DWORD *)(a1[9] + 12) >> 27;
    if ( v14 != 2 )
    {
      DbgPrintEx(
        0x93u,
        1u,
        "XHCIDUMP: SlotId %u: After address device command, slot state is not addressed, it is %u\n",
        *((unsigned __int8 *)a1 + 56),
        v14);
      v12 = -1073741630;
    }
  }
  else
  {
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: SlotId %u: Address device command failed\n", *((unsigned __int8 *)a1 + 56));
  }
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_SendAddressDeviceCommand: end 0x%X\n", v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140055ca0  push    rbx
0x140055ca2  push    rbp
0x140055ca3  push    rsi
0x140055ca4  push    rdi
0x140055ca5  sub     rsp, 78h
0x140055ca9  mov     rdi, rcx
0x140055cac  lea     r8, aXhcidumpCrashd_53; "XHCIDUMP: Crashdump_UsbDevice_SendAddre"...
0x140055cb3  mov     ebp, 93h
0x140055cb8  mov     edx, 3; Level
0x140055cbd  mov     ecx, ebp; ComponentId
0x140055cbf  call    cs:__imp_DbgPrintEx
0x140055cc6  nop     dword ptr [rax+rax+00h]
0x140055ccb  mov     rbx, [rdi]
0x140055cce  xor     edx, edx; Val
0x140055cd0  mov     r8d, [rbx+1E0h]; Size
0x140055cd7  mov     rcx, [rbx+1D8h]; void *
0x140055cde  call    memset
0x140055ce3  mov     r10, [rbx+1D8h]
0x140055cea  or      dword ptr [r10+4], 3
0x140055cef  mov     rax, [rdi+8]
0x140055cf3  mov     rcx, [rax]
0x140055cf6  mov     r9d, [rcx+68h]
0x140055cfa  and     r9d, 4
0x140055cfe  mov     eax, r9d
0x140055d01  neg     eax
0x140055d03  sbb     r8, r8
0x140055d06  and     r8d, 20h
0x140055d0a  mov     eax, [r8+r10+20h]
0x140055d0f  mov     ecx, eax
0x140055d11  xor     ecx, [rdi+50h]
0x140055d14  and     ecx, 0FFFFFh
0x140055d1a  xor     ecx, eax
0x140055d1c  mov     [r8+r10+20h], ecx
0x140055d21  mov     edx, ecx
0x140055d23  xor     edx, [rdi+50h]
0x140055d26  and     edx, 0F00000h
0x140055d2c  xor     edx, ecx
0x140055d2e  mov     [r8+r10+20h], edx
0x140055d33  and     edx, 7FFFFFFh
0x140055d39  mov     al, [rdi+56h]
0x140055d3c  bts     edx, 1Bh
0x140055d40  mov     [r8+r10+26h], al
0x140055d45  mov     eax, r9d
0x140055d48  mov     [r8+r10+20h], edx
0x140055d4d  neg     eax
0x140055d4f  mov     r8, [rdi+78h]
0x140055d53  sbb     rdx, rdx
0x140055d56  and     edx, 40h
0x140055d59  mov     ecx, [rdx+r10+44h]
0x140055d5e  mov     eax, ecx
0x140055d60  xor     eax, [r8+34h]
0x140055d64  and     eax, 38h
0x140055d67  xor     eax, ecx
0x140055d69  mov     [rdx+r10+44h], eax
0x140055d6e  mov     eax, r9d
0x140055d71  neg     eax
0x140055d73  movzx   eax, word ptr [r8+36h]
0x140055d78  sbb     rcx, rcx
0x140055d7b  and     ecx, 40h
0x140055d7e  mov     [rcx+r10+46h], ax
0x140055d84  mov     eax, [rdx+r10+44h]
0x140055d89  mov     ecx, eax
0x140055d8b  xor     ecx, [r8+34h]
0x140055d8f  and     ecx, 6
0x140055d92  xor     ecx, eax
0x140055d94  mov     [rdx+r10+44h], ecx
0x140055d99  cmp     byte ptr [r8+80h], 0
0x140055da1  jz      short loc_140055DAC
0x140055da3  mov     rcx, [r8+88h]
0x140055daa  jmp     short loc_140055DBC
0x140055dac  mov     eax, [r8+0A0h]
0x140055db3  lea     rcx, [rax+rax*2]
0x140055db7  mov     rcx, [r8+rcx*8+50h]
0x140055dbc  or      rcx, 1
0x140055dc0  mov     [rsp+98h+var_30], 0
0x140055dc8  neg     r9d
0x140055dcb  lea     rdx, [rsp+98h+var_38]
0x140055dd0  sbb     rax, rax
0x140055dd3  xor     r8d, r8d
0x140055dd6  and     eax, 40h
0x140055dd9  mov     [rax+r10+48h], rcx
0x140055dde  movzx   eax, byte ptr [rdi+38h]
0x140055de2  mov     rcx, [rdi+10h]
0x140055de6  bswap   eax
0x140055de8  or      eax, 2C00h
0x140055ded  mov     [rsp+98h+var_2C], eax
0x140055df1  mov     rax, [rbx+1D0h]
0x140055df8  mov     [rsp+98h+var_38], rax
0x140055dfd  call    Crashdump_Command_SendCommand
0x140055e02  mov     esi, eax
0x140055e04  test    eax, eax
0x140055e06  jns     short loc_140055E2C
0x140055e08  movzx   r9d, byte ptr [rdi+38h]
0x140055e0d  lea     r8, aXhcidumpSlotid_5; "XHCIDUMP: SlotId %u: Address device com"...
0x140055e14  mov     edx, 1; Level
0x140055e19  mov     ecx, ebp; ComponentId
0x140055e1b  call    cs:__imp_DbgPrintEx
0x140055e22  nop     dword ptr [rax+rax+00h]
0x140055e27  jmp     loc_140055EDD
0x140055e2c  mov     r9, [rdi+48h]
0x140055e30  mov     ebx, [r9]
0x140055e33  mov     r10d, ebx
0x140055e36  mov     eax, [r9+0Ch]
0x140055e3a  mov     edx, ebx
0x140055e3c  movzx   r8d, al
0x140055e40  mov     r11d, eax
0x140055e43  movzx   eax, byte ptr [r9+6]
0x140055e48  mov     ecx, ebx
0x140055e4a  movzx   r9d, byte ptr [rdi+38h]
0x140055e4f  and     ebx, 0FFFFFh
0x140055e55  shr     edx, 1Ah
0x140055e58  shr     ecx, 14h
0x140055e5b  and     edx, 1
0x140055e5e  and     ecx, 0Fh
0x140055e61  shr     r11d, 1Bh
0x140055e65  mov     [rsp+98h+var_48], r11d
0x140055e6a  mov     [rsp+98h+var_50], r8d
0x140055e6f  lea     r8, aXhcidumpSlotUR; "XHCIDUMP: Slot %u: RH %u, RS %u, Speed "...
0x140055e76  shr     r10d, 1Bh
0x140055e7a  mov     [rsp+98h+var_58], r10d
0x140055e7f  mov     [rsp+98h+var_60], edx
0x140055e83  mov     edx, 3; Level
0x140055e88  mov     [rsp+98h+var_68], ecx
0x140055e8c  mov     ecx, ebp; ComponentId
0x140055e8e  mov     [rsp+98h+var_70], ebx
0x140055e92  mov     [rsp+98h+var_78], eax
0x140055e96  call    cs:__imp_DbgPrintEx
0x140055e9d  nop     dword ptr [rax+rax+00h]
0x140055ea2  mov     rax, [rdi+48h]
0x140055ea6  mov     r8d, [rax+0Ch]
0x140055eaa  shr     r8d, 1Bh
0x140055eae  cmp     r8d, 2
0x140055eb2  jz      short loc_140055EDD
0x140055eb4  movzx   r9d, byte ptr [rdi+38h]
0x140055eb9  mov     edx, 1; Level
0x140055ebe  mov     [rsp+98h+var_78], r8d
0x140055ec3  mov     ecx, ebp; ComponentId
0x140055ec5  lea     r8, aXhcidumpSlotid_4; "XHCIDUMP: SlotId %u: After address devi"...
0x140055ecc  call    cs:__imp_DbgPrintEx
0x140055ed3  nop     dword ptr [rax+rax+00h]
0x140055ed8  mov     esi, 0C00000C2h
0x140055edd  mov     r9d, esi
0x140055ee0  lea     r8, aXhcidumpCrashd_61; "XHCIDUMP: Crashdump_UsbDevice_SendAddre"...
0x140055ee7  mov     edx, 3; Level
0x140055eec  mov     ecx, ebp; ComponentId
0x140055eee  call    cs:__imp_DbgPrintEx
0x140055ef5  nop     dword ptr [rax+rax+00h]
0x140055efa  mov     eax, esi
0x140055efc  add     rsp, 78h
0x140055f00  pop     rdi
0x140055f01  pop     rsi
0x140055f02  pop     rbp
0x140055f03  pop     rbx
0x140055f04  retn
```
