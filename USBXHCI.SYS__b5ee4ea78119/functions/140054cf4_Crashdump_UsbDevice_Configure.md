# Crashdump_UsbDevice_Configure

- ea: `0x140054cf4`
- end: `0x140054f94`
- name: `Crashdump_UsbDevice_Configure`
- size: `672`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140055878`
- `0x1400559a8`

## callees

- `0x140054620`
- `0x140054cf4`
- `0x140054f9c`
- `0x1400552f0`
- `0x140055ca0`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140054d26`
- `ntoskrnl!DbgPrintEx` at `0x140054db2`
- `ntoskrnl!DbgPrintEx` at `0x140054de1`
- `ntoskrnl!DbgPrintEx` at `0x140054edc`
- `ntoskrnl!DbgPrintEx` at `0x140054f59`
- `ntoskrnl!DbgPrintEx` at `0x140054f73`
- `ntoskrnl!DbgPrintEx` at `0x140054d26`
- `ntoskrnl!DbgPrintEx` at `0x140054db2`
- `ntoskrnl!DbgPrintEx` at `0x140054de1`
- `ntoskrnl!DbgPrintEx` at `0x140054edc`
- `ntoskrnl!DbgPrintEx` at `0x140054f59`
- `ntoskrnl!DbgPrintEx` at `0x140054f73`

## string_xrefs

- `0x140054d0a`: `XHCIDUMP: Crashdump_UsbDevice_Configure: begin\n`
- `0x140054dd1`: `XHCIDUMP: Crashdump_UsbDevice_GetDeviceDescriptor: failed error = 0x%X\n`
- `0x140054e21`: `XHCIDUMP: USB_REQUEST_SET_CONFIGURATION: failed error = 0x%X\n`
- `0x140054f68`: `XHCIDUMP: Crashdump_UsbDevice_Configure: end 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_UsbDevice_Configure(__int64 a1, int a2)
{
  int v4; // r15d
  __int64 v5; // r9
  int DeviceDescriptor; // eax
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v15; // [rsp+B0h] [rbp+48h] BYREF

  v15 = 0;
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_Configure: begin\n");
  v4 = Crashdump_UsbDevice_SendAddressDeviceCommand(a1);
  if ( v4 >= 0 )
  {
    v5 = *(_QWORD *)(a1 + 72);
    DbgPrintEx(
      0x93u,
      3u,
      "XHCIDUMP: Slot %u: RH %u, RS %u, Speed %u, IsHub %u, NumEntries %u, Addr %u, State %u\n",
      *(unsigned __int8 *)(a1 + 56),
      *(unsigned __int8 *)(v5 + 6),
      *(_DWORD *)v5 & 0xFFFFF,
      (*(_DWORD *)v5 >> 20) & 0xF,
      (*(_DWORD *)v5 >> 26) & 1,
      *(_DWORD *)v5 >> 27,
      (unsigned __int8)*(_DWORD *)(v5 + 12),
      *(_DWORD *)(v5 + 12) >> 27);
    DeviceDescriptor = Crashdump_UsbDevice_GetDeviceDescriptor(a1, &v15);
    v4 = DeviceDescriptor;
    if ( DeviceDescriptor >= 0 )
    {
      v7 = *(_QWORD *)(a1 + 120);
      WORD1(v15) = *(unsigned __int8 *)(a1 + 369);
      LOWORD(v15) = 2304;
      HIDWORD(v15) = 0;
      v8 = Crashdump_Endpoint_SendControlTransfer(v7, &v15, 0, 0);
      v4 = v8;
      if ( v8 >= 0 )
      {
        if ( *(_BYTE *)(a1 + 371)
          && (v9 = *(_QWORD *)(a1 + 120),
              WORD1(v15) = *(unsigned __int8 *)(a1 + 371),
              WORD2(v15) = *(unsigned __int8 *)(a1 + 370),
              LOWORD(v15) = 2817,
              v10 = Crashdump_Endpoint_SendControlTransfer(v9, &v15, 0, 0),
              v4 = v10,
              v10 < 0) )
        {
          DbgPrintEx(0x93u, 1u, "XHCIDUMP: USB_REQUEST_SET_INTERFACE: failed error = 0x%X\n", (unsigned int)v10);
        }
        else if ( *(_BYTE *)(a1 + 368) )
        {
          if ( a2 == 30 )
          {
            v11 = *(_QWORD *)(a1 + 120);
            *(_DWORD *)((char *)&v15 + 2) = (unsigned __int16)(*(_WORD *)(a1 + 372) - 1);
            LOWORD(v15) = 3104;
            v12 = Crashdump_Endpoint_SendControlTransfer(v11, &v15, 0, 0);
            v4 = v12;
            if ( v12 < 0 )
              DbgPrintEx(
                0x93u,
                1u,
                "XHCIDUMP: USB_REQUEST_SET_HUB_DEPTH: failed depth = %u error = 0x%X\n",
                *(_DWORD *)(a1 + 372) - 1,
                v12);
          }
        }
        else
        {
          v4 = Crashdump_UsbDevice_ConfigureEndpoints(a1);
        }
      }
      else
      {
        DbgPrintEx(0x93u, 1u, "XHCIDUMP: USB_REQUEST_SET_CONFIGURATION: failed error = 0x%X\n", (unsigned int)v8);
      }
    }
    else
    {
      DbgPrintEx(
        0x93u,
        1u,
        "XHCIDUMP: Crashdump_UsbDevice_GetDeviceDescriptor: failed error = 0x%X\n",
        (unsigned int)DeviceDescriptor);
    }
  }
  v13 = *(_QWORD *)(a1 + 72);
  DbgPrintEx(
    0x93u,
    3u,
    "XHCIDUMP: Slot %u: RH %u, RS %u, Speed %u, IsHub %u, NumEntries %u, Addr %u, State %u\n",
    *(unsigned __int8 *)(a1 + 56),
    *(unsigned __int8 *)(v13 + 6),
    *(_DWORD *)v13 & 0xFFFFF,
    (*(_DWORD *)v13 >> 20) & 0xF,
    (*(_DWORD *)v13 >> 26) & 1,
    *(_DWORD *)v13 >> 27,
    (unsigned __int8)*(_DWORD *)(v13 + 12),
    *(_DWORD *)(v13 + 12) >> 27);
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_Configure: end 0x%X\n", v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140054cf4  push    rbp
0x140054cf6  push    rbx
0x140054cf7  push    rsi
0x140054cf8  push    rdi
0x140054cf9  push    r12
0x140054cfb  push    r13
0x140054cfd  push    r14
0x140054cff  push    r15
0x140054d01  mov     rbp, rsp
0x140054d04  sub     rsp, 68h
0x140054d08  xor     esi, esi
0x140054d0a  lea     r8, aXhcidumpCrashd_85; "XHCIDUMP: Crashdump_UsbDevice_Configure"...
0x140054d11  mov     edi, edx
0x140054d13  mov     [rbp+arg_0], rsi
0x140054d17  mov     r13, rcx
0x140054d1a  mov     r14d, 93h
0x140054d20  mov     ecx, r14d; ComponentId
0x140054d23  lea     edx, [rsi+3]; Level
0x140054d26  call    cs:__imp_DbgPrintEx
0x140054d2d  nop     dword ptr [rax+rax+00h]
0x140054d32  mov     rcx, r13
0x140054d35  call    Crashdump_UsbDevice_SendAddressDeviceCommand
0x140054d3a  lea     r12d, [rsi+1]
0x140054d3e  mov     r15d, eax
0x140054d41  test    eax, eax
0x140054d43  js      loc_140054EE8
0x140054d49  mov     r9, [r13+48h]
0x140054d4d  mov     ebx, [r9]
0x140054d50  mov     r10d, ebx
0x140054d53  mov     eax, [r9+0Ch]
0x140054d57  mov     edx, ebx
0x140054d59  movzx   r8d, al
0x140054d5d  mov     r11d, eax
0x140054d60  movzx   eax, byte ptr [r9+6]
0x140054d65  mov     ecx, ebx
0x140054d67  movzx   r9d, byte ptr [r13+38h]
0x140054d6c  and     ebx, 0FFFFFh
0x140054d72  shr     edx, 1Ah
0x140054d75  shr     ecx, 14h
0x140054d78  and     edx, r12d
0x140054d7b  and     ecx, 0Fh
0x140054d7e  shr     r11d, 1Bh
0x140054d82  mov     [rsp+68h+var_18], r11d
0x140054d87  mov     [rsp+68h+var_20], r8d
0x140054d8c  lea     r8, aXhcidumpSlotUR; "XHCIDUMP: Slot %u: RH %u, RS %u, Speed "...
0x140054d93  shr     r10d, 1Bh
0x140054d97  mov     [rsp+68h+var_28], r10d
0x140054d9c  mov     [rsp+68h+var_30], edx
0x140054da0  lea     edx, [rsi+3]; Level
0x140054da3  mov     [rsp+68h+var_38], ecx
0x140054da7  mov     ecx, r14d; ComponentId
0x140054daa  mov     [rsp+68h+var_40], ebx
0x140054dae  mov     [rsp+68h+var_48], eax
0x140054db2  call    cs:__imp_DbgPrintEx
0x140054db9  nop     dword ptr [rax+rax+00h]
0x140054dbe  lea     rdx, [rbp+arg_0]
0x140054dc2  mov     rcx, r13
0x140054dc5  call    Crashdump_UsbDevice_GetDeviceDescriptor
0x140054dca  mov     r15d, eax
0x140054dcd  test    eax, eax
0x140054dcf  jns     short loc_140054DF2
0x140054dd1  lea     r8, aXhcidumpCrashd_56; "XHCIDUMP: Crashdump_UsbDevice_GetDevice"...
0x140054dd8  mov     r9d, eax
0x140054ddb  mov     edx, r12d; Level
0x140054dde  mov     ecx, r14d; ComponentId
0x140054de1  call    cs:__imp_DbgPrintEx
0x140054de8  nop     dword ptr [rax+rax+00h]
0x140054ded  jmp     loc_140054EE8
0x140054df2  movzx   eax, byte ptr [r13+171h]
0x140054dfa  lea     rdx, [rbp+arg_0]
0x140054dfe  mov     rcx, [r13+78h]
0x140054e02  xor     r9d, r9d
0x140054e05  xor     r8d, r8d
0x140054e08  mov     word ptr [rbp+arg_0+2], ax
0x140054e0c  mov     word ptr [rbp+arg_0], 900h
0x140054e12  mov     dword ptr [rbp+arg_0+4], esi
0x140054e15  call    Crashdump_Endpoint_SendControlTransfer
0x140054e1a  mov     r15d, eax
0x140054e1d  test    eax, eax
0x140054e1f  jns     short loc_140054E2A
0x140054e21  lea     r8, aXhcidumpUsbReq; "XHCIDUMP: USB_REQUEST_SET_CONFIGURATION"...
0x140054e28  jmp     short loc_140054DD8
0x140054e2a  movzx   eax, byte ptr [r13+173h]
0x140054e32  test    al, al
0x140054e34  jz      short loc_140054E72
0x140054e36  mov     rcx, [r13+78h]
0x140054e3a  lea     rdx, [rbp+arg_0]
0x140054e3e  mov     word ptr [rbp+arg_0+2], ax
0x140054e42  xor     r9d, r9d
0x140054e45  movzx   eax, byte ptr [r13+172h]
0x140054e4d  xor     r8d, r8d
0x140054e50  mov     word ptr [rbp+arg_0+4], ax
0x140054e54  mov     word ptr [rbp+arg_0], 0B01h
0x140054e5a  call    Crashdump_Endpoint_SendControlTransfer
0x140054e5f  mov     r15d, eax
0x140054e62  test    eax, eax
0x140054e64  jns     short loc_140054E72
0x140054e66  lea     r8, aXhcidumpUsbReq_0; "XHCIDUMP: USB_REQUEST_SET_INTERFACE: fa"...
0x140054e6d  jmp     loc_140054DD8
0x140054e72  cmp     [r13+170h], sil
0x140054e79  jnz     short loc_140054E88
0x140054e7b  mov     rcx, r13
0x140054e7e  call    Crashdump_UsbDevice_ConfigureEndpoints
0x140054e83  mov     r15d, eax
0x140054e86  jmp     short loc_140054EE8
0x140054e88  cmp     edi, 1Eh
0x140054e8b  jnz     short loc_140054EE8
0x140054e8d  movzx   eax, word ptr [r13+174h]
0x140054e95  lea     rdx, [rbp+arg_0]
0x140054e99  mov     rcx, [r13+78h]
0x140054e9d  sub     ax, r12w
0x140054ea1  xor     r9d, r9d
0x140054ea4  mov     word ptr [rbp+arg_0+2], ax
0x140054ea8  xor     r8d, r8d
0x140054eab  mov     word ptr [rbp+arg_0], 0C20h
0x140054eb1  mov     word ptr [rbp+arg_0+4], si
0x140054eb5  call    Crashdump_Endpoint_SendControlTransfer
0x140054eba  mov     r15d, eax
0x140054ebd  test    eax, eax
0x140054ebf  jns     short loc_140054EE8
0x140054ec1  mov     r9d, [r13+174h]
0x140054ec8  lea     r8, aXhcidumpUsbReq_1; "XHCIDUMP: USB_REQUEST_SET_HUB_DEPTH: fa"...
0x140054ecf  sub     r9d, r12d
0x140054ed2  mov     [rsp+68h+var_48], eax
0x140054ed6  mov     edx, r12d; Level
0x140054ed9  mov     ecx, r14d; ComponentId
0x140054edc  call    cs:__imp_DbgPrintEx
0x140054ee3  nop     dword ptr [rax+rax+00h]
0x140054ee8  mov     rcx, [r13+48h]
0x140054eec  lea     r8, aXhcidumpSlotUR; "XHCIDUMP: Slot %u: RH %u, RS %u, Speed "...
0x140054ef3  movzx   r9d, byte ptr [r13+38h]
0x140054ef8  mov     r14d, [rcx]
0x140054efb  mov     edi, r14d
0x140054efe  mov     eax, [rcx+0Ch]
0x140054f01  mov     r11d, r14d
0x140054f04  movzx   ebx, al
0x140054f07  mov     esi, eax
0x140054f09  movzx   eax, byte ptr [rcx+6]
0x140054f0d  mov     r10d, r14d
0x140054f10  shr     r11d, 1Ah
0x140054f14  and     r14d, 0FFFFFh
0x140054f1b  shr     edi, 1Bh
0x140054f1e  and     r11d, r12d
0x140054f21  shr     r10d, 14h
0x140054f25  and     r10d, 0Fh
0x140054f29  shr     esi, 1Bh
0x140054f2c  mov     [rsp+68h+var_18], esi
0x140054f30  mov     [rsp+68h+var_20], ebx
0x140054f34  mov     ebx, 93h
0x140054f39  mov     [rsp+68h+var_28], edi
0x140054f3d  mov     ecx, ebx; ComponentId
0x140054f3f  mov     [rsp+68h+var_30], r11d
0x140054f44  mov     edi, 3
0x140054f49  mov     [rsp+68h+var_38], r10d
0x140054f4e  mov     edx, edi; Level
0x140054f50  mov     [rsp+68h+var_40], r14d
0x140054f55  mov     [rsp+68h+var_48], eax
0x140054f59  call    cs:__imp_DbgPrintEx
0x140054f60  nop     dword ptr [rax+rax+00h]
0x140054f65  mov     r9d, r15d
0x140054f68  lea     r8, aXhcidumpCrashd_0; "XHCIDUMP: Crashdump_UsbDevice_Configure"...
0x140054f6f  mov     edx, edi; Level
0x140054f71  mov     ecx, ebx; ComponentId
0x140054f73  call    cs:__imp_DbgPrintEx
0x140054f7a  nop     dword ptr [rax+rax+00h]
0x140054f7f  mov     eax, r15d
0x140054f82  add     rsp, 68h
0x140054f86  pop     r15
0x140054f88  pop     r14
0x140054f8a  pop     r13
0x140054f8c  pop     r12
0x140054f8e  pop     rdi
0x140054f8f  pop     rsi
0x140054f90  pop     rbx
0x140054f91  pop     rbp
0x140054f92  retn
```
