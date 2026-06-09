# Crashdump_UsbDevice_ConfigureEndpoints

- ea: `0x140054f9c`
- end: `0x140055211`
- name: `Crashdump_UsbDevice_ConfigureEndpoints`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140054cf4`

## callees

- `0x140053f98`
- `0x140054f9c`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140054fbf`
- `ntoskrnl!DbgPrintEx` at `0x140055192`
- `ntoskrnl!DbgPrintEx` at `0x1400551cd`
- `ntoskrnl!DbgPrintEx` at `0x1400551f2`
- `ntoskrnl!DbgPrintEx` at `0x140054fbf`
- `ntoskrnl!DbgPrintEx` at `0x140055192`
- `ntoskrnl!DbgPrintEx` at `0x1400551cd`
- `ntoskrnl!DbgPrintEx` at `0x1400551f2`

## string_xrefs

- `0x140054fae`: `XHCIDUMP: Crashdump_UsbDevice_ConfigureEndpoints: begin\n`
- `0x140055181`: `XHCIDUMP: SlotId %u: Configure Endpoint command failed\n`
- `0x1400551c6`: `XHCIDUMP: SlotId %u: After reset device command, slot state is not configured, it is %u\n`
- `0x1400551e1`: `XHCIDUMP: Crashdump_UsbDevice_ConfigureEndpoints: end 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_UsbDevice_ConfigureEndpoints(__int64 *a1)
{
  __int64 v2; // rsi
  __int64 v3; // r8
  unsigned int v4; // r11d
  unsigned int i; // r10d
  __int64 v6; // r9
  __int64 v7; // r11
  __int64 v8; // rcx
  int v9; // edx
  unsigned __int64 v10; // rcx
  unsigned int v11; // edx
  __int64 v12; // rax
  __int64 v13; // rdx
  int v14; // ecx
  __int64 *v15; // rcx
  int v16; // edi
  int v17; // r8d
  __int64 v19; // [rsp+30h] [rbp-18h] BYREF
  int v20; // [rsp+38h] [rbp-10h]
  int v21; // [rsp+3Ch] [rbp-Ch]

  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_ConfigureEndpoints: begin\n");
  v2 = *a1;
  memset(*(void **)(*a1 + 472), 0, *(unsigned int *)(*a1 + 480));
  v3 = *(_QWORD *)(v2 + 472);
  *(_DWORD *)(v3 + 4) |= 1u;
  v4 = 0;
  for ( i = 2; i < 0x20; ++i )
  {
    if ( ((1 << i) & 0xFFFFFFFC) != 0 )
    {
      v6 = a1[i + 14];
      if ( v6 )
      {
        v7 = (i - 1 + 2LL) * ((*(_DWORD *)(*(_QWORD *)a1[1] + 104LL) & 4) != 0 ? 64LL : 32LL);
        *(_DWORD *)(v7 + v3 + 4) ^= (*(_DWORD *)(v6 + 52) ^ *(_DWORD *)(v7 + v3 + 4)) & 0x38;
        *(_WORD *)(v7 + v3 + 6) = *(_WORD *)(v6 + 54);
        *(_DWORD *)(v7 + v3 + 4) ^= (*(_DWORD *)(v6 + 52) ^ *(_DWORD *)(v7 + v3 + 4)) & 6;
        *(_BYTE *)(v7 + v3 + 5) = BYTE1(*(_DWORD *)(v6 + 52));
        *(_WORD *)(v7 + v3 + 16) = *(_WORD *)(v6 + 64);
        if ( *(_BYTE *)(v6 + 128) )
          v8 = *(_QWORD *)(v6 + 136);
        else
          v8 = *(_QWORD *)(v6 + 24LL * *(unsigned int *)(v6 + 160) + 80);
        v9 = *(_DWORD *)(v7 + v3);
        *(_QWORD *)(v7 + v3 + 8) = v8;
        if ( (*(_DWORD *)(v6 + 48) & 0x7C00) != 0 )
        {
          v10 = v8 & 0xFFFFFFFFFFFFFFFEuLL;
          v11 = v9 & 0xFFFF03FF | 0x8400;
        }
        else
        {
          v10 = v8 | 1;
          v11 = v9 & 0xFFFF03FF;
        }
        *(_DWORD *)(v7 + v3) = v11;
        *(_QWORD *)(v7 + v3 + 8) = v10;
        v4 = i;
        *(_DWORD *)(v3 + 4) |= 1 << i;
      }
    }
  }
  v12 = a1[1];
  v20 = 0;
  v13 = (*(_DWORD *)(*(_QWORD *)v12 + 104LL) & 4) != 0 ? 0x20 : 0;
  v14 = (v4 << 27) | *(_DWORD *)(v13 + v3 + 32) & 0x7FFFFFF;
  *(_DWORD *)(v13 + v3 + 32) = v14;
  *(_DWORD *)(v13 + v3 + 32) = v14 ^ (*((_DWORD *)a1 + 20) ^ v14) & 0x4000000;
  *(_BYTE *)(v13 + v3 + 39) = *((_BYTE *)a1 + 87);
  v15 = (__int64 *)a1[2];
  v21 = (*((unsigned __int8 *)a1 + 56) << 24) | 0x3000;
  v19 = *(_QWORD *)(v2 + 464);
  v16 = Crashdump_Command_SendCommand(v15, (__int64)&v19, 0);
  if ( v16 >= 0 )
  {
    v17 = *(_DWORD *)(a1[9] + 12) >> 27;
    if ( v17 != 3 )
    {
      DbgPrintEx(
        0x93u,
        1u,
        "XHCIDUMP: SlotId %u: After reset device command, slot state is not configured, it is %u\n",
        *((unsigned __int8 *)a1 + 56),
        v17);
      v16 = -1073741630;
    }
  }
  else
  {
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: SlotId %u: Configure Endpoint command failed\n", *((unsigned __int8 *)a1 + 56));
  }
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_ConfigureEndpoints: end 0x%X\n", v16);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140054f9c  mov     [rsp+arg_0], rbx
0x140054fa1  mov     [rsp+arg_8], rsi
0x140054fa6  push    rdi
0x140054fa7  sub     rsp, 40h
0x140054fab  mov     rbx, rcx
0x140054fae  lea     r8, aXhcidumpCrashd_46; "XHCIDUMP: Crashdump_UsbDevice_Configure"...
0x140054fb5  mov     ecx, 93h; ComponentId
0x140054fba  mov     edx, 3; Level
0x140054fbf  call    cs:__imp_DbgPrintEx
0x140054fc6  nop     dword ptr [rax+rax+00h]
0x140054fcb  mov     rsi, [rbx]
0x140054fce  xor     edx, edx; Val
0x140054fd0  mov     r8d, [rsi+1E0h]; Size
0x140054fd7  mov     rcx, [rsi+1D8h]; void *
0x140054fde  call    memset
0x140054fe3  mov     r8, [rsi+1D8h]
0x140054fea  or      dword ptr [r8+4], 1
0x140054fef  xor     r11d, r11d
0x140054ff2  lea     r10d, [r11+2]
0x140054ff6  mov     ecx, r10d
0x140054ff9  mov     edi, 1
0x140054ffe  shl     edi, cl
0x140055000  test    edi, 0FFFFFFFCh
0x140055006  jz      loc_1400550F0
0x14005500c  mov     eax, r10d
0x14005500f  mov     r9, [rbx+rax*8+70h]
0x140055014  test    r9, r9
0x140055017  jz      loc_1400550F0
0x14005501d  mov     rax, [rbx+8]
0x140055021  mov     rcx, [rax]
0x140055024  mov     eax, [rcx+68h]
0x140055027  lea     ecx, [r10-1]
0x14005502b  and     al, 4
0x14005502d  neg     al
0x14005502f  sbb     r11, r11
0x140055032  add     rcx, 2
0x140055036  and     r11d, 20h
0x14005503a  add     r11, 20h ; ' '
0x14005503e  imul    r11, rcx
0x140055042  mov     ecx, [r11+r8+4]
0x140055047  mov     eax, ecx
0x140055049  xor     eax, [r9+34h]
0x14005504d  and     eax, 38h
0x140055050  xor     eax, ecx
0x140055052  mov     [r11+r8+4], eax
0x140055057  movzx   eax, word ptr [r9+36h]
0x14005505c  mov     [r11+r8+6], ax
0x140055062  mov     eax, [r11+r8+4]
0x140055067  mov     ecx, eax
0x140055069  xor     ecx, [r9+34h]
0x14005506d  and     ecx, 6
0x140055070  xor     ecx, eax
0x140055072  mov     [r11+r8+4], ecx
0x140055077  mov     eax, [r9+34h]
0x14005507b  shr     eax, 8
0x14005507e  mov     [r11+r8+5], al
0x140055083  movzx   eax, word ptr [r9+40h]
0x140055088  mov     [r11+r8+10h], ax
0x14005508e  cmp     byte ptr [r9+80h], 0
0x140055096  jz      short loc_1400550A1
0x140055098  mov     rcx, [r9+88h]
0x14005509f  jmp     short loc_1400550B1
0x1400550a1  mov     eax, [r9+0A0h]
0x1400550a8  lea     rcx, [rax+rax*2]
0x1400550ac  mov     rcx, [r9+rcx*8+50h]
0x1400550b1  mov     edx, [r11+r8]
0x1400550b5  mov     [r11+r8+8], rcx
0x1400550ba  test    dword ptr [r9+30h], 7C00h
0x1400550c2  jnz     short loc_1400550D0
0x1400550c4  or      rcx, 1
0x1400550c8  and     edx, 0FFFF03FFh
0x1400550ce  jmp     short loc_1400550E0
0x1400550d0  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1400550d4  and     edx, 0FFFF87FFh
0x1400550da  or      edx, 8400h
0x1400550e0  mov     [r11+r8], edx
0x1400550e4  mov     [r11+r8+8], rcx
0x1400550e9  mov     r11d, r10d
0x1400550ec  or      [r8+4], edi
0x1400550f0  inc     r10d
0x1400550f3  cmp     r10d, 20h ; ' '
0x1400550f7  jb      loc_140054FF6
0x1400550fd  mov     rax, [rbx+8]
0x140055101  mov     [rsp+48h+var_10], 0
0x140055109  mov     rcx, [rax]
0x14005510c  mov     eax, [rcx+68h]
0x14005510f  and     al, 4
0x140055111  neg     al
0x140055113  sbb     rdx, rdx
0x140055116  shl     r11d, 1Bh
0x14005511a  and     edx, 20h
0x14005511d  mov     ecx, [rdx+r8+20h]
0x140055122  and     ecx, 7FFFFFFh
0x140055128  or      ecx, r11d
0x14005512b  mov     [rdx+r8+20h], ecx
0x140055130  mov     eax, ecx
0x140055132  xor     eax, [rbx+50h]
0x140055135  and     eax, 4000000h
0x14005513a  xor     eax, ecx
0x14005513c  mov     [rdx+r8+20h], eax
0x140055141  mov     al, [rbx+57h]
0x140055144  mov     [rdx+r8+27h], al
0x140055149  xor     r8d, r8d
0x14005514c  movzx   eax, byte ptr [rbx+38h]
0x140055150  lea     rdx, [rsp+48h+var_18]
0x140055155  mov     rcx, [rbx+10h]
0x140055159  shl     eax, 18h
0x14005515c  or      eax, 3000h
0x140055161  mov     [rsp+48h+var_C], eax
0x140055165  mov     rax, [rsi+1D0h]
0x14005516c  mov     [rsp+48h+var_18], rax
0x140055171  call    Crashdump_Command_SendCommand
0x140055176  mov     edi, eax
0x140055178  test    eax, eax
0x14005517a  jns     short loc_1400551A0
0x14005517c  movzx   r9d, byte ptr [rbx+38h]
0x140055181  lea     r8, aXhcidumpSlotid_1; "XHCIDUMP: SlotId %u: Configure Endpoint"...
0x140055188  mov     edx, 1; Level
0x14005518d  mov     ecx, 93h; ComponentId
0x140055192  call    cs:__imp_DbgPrintEx
0x140055199  nop     dword ptr [rax+rax+00h]
0x14005519e  jmp     short loc_1400551DE
0x1400551a0  mov     rax, [rbx+48h]
0x1400551a4  mov     r8d, [rax+0Ch]
0x1400551a8  shr     r8d, 1Bh
0x1400551ac  cmp     r8d, 3
0x1400551b0  jz      short loc_1400551DE
0x1400551b2  movzx   r9d, byte ptr [rbx+38h]
0x1400551b7  mov     edx, 1; Level
0x1400551bc  mov     [rsp+48h+var_28], r8d
0x1400551c1  mov     ecx, 93h; ComponentId
0x1400551c6  lea     r8, aXhcidumpSlotid; "XHCIDUMP: SlotId %u: After reset device"...
0x1400551cd  call    cs:__imp_DbgPrintEx
0x1400551d4  nop     dword ptr [rax+rax+00h]
0x1400551d9  mov     edi, 0C00000C2h
0x1400551de  mov     r9d, edi
0x1400551e1  lea     r8, aXhcidumpCrashd_75; "XHCIDUMP: Crashdump_UsbDevice_Configure"...
0x1400551e8  mov     edx, 3; Level
0x1400551ed  mov     ecx, 93h; ComponentId
0x1400551f2  call    cs:__imp_DbgPrintEx
0x1400551f9  nop     dword ptr [rax+rax+00h]
0x1400551fe  mov     rbx, [rsp+48h+arg_0]
0x140055203  mov     eax, edi
0x140055205  mov     rsi, [rsp+48h+arg_8]
0x14005520a  add     rsp, 40h
0x14005520e  pop     rdi
0x14005520f  retn
```
