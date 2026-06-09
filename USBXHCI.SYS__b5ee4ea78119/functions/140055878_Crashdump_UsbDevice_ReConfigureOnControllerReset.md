# Crashdump_UsbDevice_ReConfigureOnControllerReset

- ea: `0x140055878`
- end: `0x1400559a1`
- name: `Crashdump_UsbDevice_ReConfigureOnControllerReset`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140051fcc`

## callees

- `0x140054cf4`
- `0x140055878`
- `0x140055f0c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140055897`
- `ntoskrnl!DbgPrintEx` at `0x140055989`
- `ntoskrnl!DbgPrintEx` at `0x140055897`
- `ntoskrnl!DbgPrintEx` at `0x140055989`
- `ntoskrnl!PoSetHiberRange` at `0x14005590d`
- `ntoskrnl!PoSetHiberRange` at `0x14005590d`

## string_xrefs

- `0x140055883`: `XHCIDUMP: Crashdump_UsbDevice_ReConfigureOnControllerReset: begin\n`
- `0x140055978`: `XHCIDUMP: Crashdump_UsbDevice_ReConfigureOnControllerReset: end 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_UsbDevice_ReConfigureOnControllerReset(__int64 a1, int a2)
{
  int v4; // edi
  __int64 v5; // rsi
  __int64 v6; // rdi
  __int64 v7; // rax
  int v8; // r8d
  bool v9; // zf
  __int64 v10; // rax
  __int64 v11; // rax

  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_ReConfigureOnControllerReset: begin\n");
  v4 = Crashdump_UsbDevice_SendEnableSlotCommand(a1);
  if ( v4 >= 0 )
  {
    v5 = 1;
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 424LL) + 8LL * *(unsigned __int8 *)(a1 + 56)) = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 72) = *(_QWORD *)(a1 + 40);
    do
    {
      v6 = *(_QWORD *)(a1 + 8 * v5 + 112);
      if ( v6 )
      {
        if ( ((*(_DWORD *)(*(_QWORD *)a1 + 584LL) - 1) & 0xFFFFFFFB) == 0 )
          PoSetHiberRange(0, 0x10000u, (PVOID)v6, 0xC8u, 0x43434858u);
        v7 = *(_QWORD *)(v6 + 8);
        v8 = *(_DWORD *)(v6 + 32);
        *(_QWORD *)(v6 + 168) = 1;
        *(_DWORD *)(v6 + 160) = 0;
        v9 = (*(_DWORD *)(*(_QWORD *)v7 + 104LL) & 4) == 0;
        v10 = (unsigned int)(v8 - 1) + 1LL;
        if ( v9 )
          v11 = 32 * v10;
        else
          v11 = v10 << 6;
        *(_QWORD *)(v6 + 40) = *(_QWORD *)(a1 + 64) + v11;
      }
      ++v5;
    }
    while ( v5 != 32 );
    v4 = Crashdump_UsbDevice_Configure(a1, a2);
  }
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_ReConfigureOnControllerReset: end 0x%X\n", v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140055878  push    rbx
0x14005587a  push    rbp
0x14005587b  push    rsi
0x14005587c  push    rdi
0x14005587d  sub     rsp, 38h
0x140055881  mov     ebp, edx
0x140055883  lea     r8, aXhcidumpCrashd_49; "XHCIDUMP: Crashdump_UsbDevice_ReConfigu"...
0x14005588a  mov     rbx, rcx
0x14005588d  mov     edx, 3; Level
0x140055892  mov     ecx, 93h; ComponentId
0x140055897  call    cs:__imp_DbgPrintEx
0x14005589e  nop     dword ptr [rax+rax+00h]
0x1400558a3  mov     rcx, rbx
0x1400558a6  call    Crashdump_UsbDevice_SendEnableSlotCommand
0x1400558ab  mov     edi, eax
0x1400558ad  test    eax, eax
0x1400558af  js      loc_140055975
0x1400558b5  mov     rax, [rbx]
0x1400558b8  mov     esi, 1
0x1400558bd  movzx   edx, byte ptr [rbx+38h]
0x1400558c1  mov     rcx, [rax+1A8h]
0x1400558c8  mov     rax, [rbx+20h]
0x1400558cc  mov     [rcx+rdx*8], rax
0x1400558d0  mov     rax, [rbx+28h]
0x1400558d4  mov     [rbx+48h], rax
0x1400558d8  mov     rdi, [rbx+rsi*8+70h]
0x1400558dd  test    rdi, rdi
0x1400558e0  jz      short loc_14005595C
0x1400558e2  mov     rax, [rbx]
0x1400558e5  mov     ecx, [rax+248h]
0x1400558eb  dec     ecx
0x1400558ed  test    ecx, 0FFFFFFFBh
0x1400558f3  jnz     short loc_140055919
0x1400558f5  mov     r9d, 0C8h; Length
0x1400558fb  mov     [rsp+58h+Tag], 43434858h; Tag
0x140055903  mov     r8, rdi; Address
0x140055906  mov     edx, 10000h; Flags
0x14005590b  xor     ecx, ecx; MemoryMap
0x14005590d  call    cs:__imp_PoSetHiberRange
0x140055914  nop     dword ptr [rax+rax+00h]
0x140055919  mov     rax, [rdi+8]
0x14005591d  mov     r8d, [rdi+20h]
0x140055921  mov     qword ptr [rdi+0A8h], 1
0x14005592c  dec     r8d
0x14005592f  mov     dword ptr [rdi+0A0h], 0
0x140055939  mov     rcx, [rax]
0x14005593c  mov     rdx, [rbx+40h]
0x140055940  mov     eax, [rcx+68h]
0x140055943  test    al, 4
0x140055945  lea     rax, [r8+1]
0x140055949  jz      short loc_140055951
0x14005594b  shl     rax, 6
0x14005594f  jmp     short loc_140055955
0x140055951  shl     rax, 5
0x140055955  add     rax, rdx
0x140055958  mov     [rdi+28h], rax
0x14005595c  inc     rsi
0x14005595f  cmp     rsi, 20h ; ' '
0x140055963  jnz     loc_1400558D8
0x140055969  mov     edx, ebp
0x14005596b  mov     rcx, rbx
0x14005596e  call    Crashdump_UsbDevice_Configure
0x140055973  mov     edi, eax
0x140055975  mov     r9d, edi
0x140055978  lea     r8, aXhcidumpCrashd_66; "XHCIDUMP: Crashdump_UsbDevice_ReConfigu"...
0x14005597f  mov     edx, 3; Level
0x140055984  mov     ecx, 93h; ComponentId
0x140055989  call    cs:__imp_DbgPrintEx
0x140055990  nop     dword ptr [rax+rax+00h]
0x140055995  mov     eax, edi
0x140055997  add     rsp, 38h
0x14005599b  pop     rdi
0x14005599c  pop     rsi
0x14005599d  pop     rbp
0x14005599e  pop     rbx
0x14005599f  retn
```
