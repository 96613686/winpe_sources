# Crashdump_Register_ResetPort

- ea: `0x140053264`
- end: `0x1400534f0`
- name: `Crashdump_Register_ResetPort`
- size: `652`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140051fcc`
- `0x140052480`

## callees

- `0x140052fb8`
- `0x140053264`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140053295`
- `ntoskrnl!DbgPrintEx` at `0x1400532c2`
- `ntoskrnl!DbgPrintEx` at `0x140053328`
- `ntoskrnl!DbgPrintEx` at `0x140053350`
- `ntoskrnl!DbgPrintEx` at `0x14005338a`
- `ntoskrnl!DbgPrintEx` at `0x14005339f`
- `ntoskrnl!DbgPrintEx` at `0x1400533d8`
- `ntoskrnl!DbgPrintEx` at `0x140053451`
- `ntoskrnl!DbgPrintEx` at `0x1400534a5`
- `ntoskrnl!DbgPrintEx` at `0x1400534d2`
- `ntoskrnl!DbgPrintEx` at `0x140053295`
- `ntoskrnl!DbgPrintEx` at `0x1400532c2`
- `ntoskrnl!DbgPrintEx` at `0x140053328`
- `ntoskrnl!DbgPrintEx` at `0x140053350`
- `ntoskrnl!DbgPrintEx` at `0x14005338a`
- `ntoskrnl!DbgPrintEx` at `0x14005339f`
- `ntoskrnl!DbgPrintEx` at `0x1400533d8`
- `ntoskrnl!DbgPrintEx` at `0x140053451`
- `ntoskrnl!DbgPrintEx` at `0x1400534a5`
- `ntoskrnl!DbgPrintEx` at `0x1400534d2`
- `HAL!KeStallExecutionProcessor` at `0x1400532f6`
- `HAL!KeStallExecutionProcessor` at `0x14005341b`
- `HAL!KeStallExecutionProcessor` at `0x1400532f6`
- `HAL!KeStallExecutionProcessor` at `0x14005341b`

## string_xrefs

- `0x1400533c9`: `XHCIDUMP: Checking port %u for reset completion.\n`

## pseudocode

```c
__int64 __fastcall Crashdump_Register_ResetPort(__int64 a1, unsigned int a2, int a3)
{
  int *v6; // rsi
  int v7; // ebp
  int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v10; // ebp
  int v11; // ebx
  unsigned int i; // ebp
  int v13; // ebx
  int v14; // ebx
  int v15; // eax
  signed __int32 v17[8]; // [rsp+0h] [rbp-68h] BYREF

  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Register_ResetPort: begin: port %u\n", a2);
  v6 = (int *)(*(_QWORD *)(*(_QWORD *)a1 + 32LL) + 16 * (a2 - 1 + 64LL));
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Polling port %u for device presence\n", a2);
  v7 = 0;
  while ( 1 )
  {
    v8 = *v6;
    if ( (*v6 & 1) != 0 || a3 == 30 && (((*v6 & 0x1E0) - 192) & 0xFFFFFF7F) == 0 )
      break;
    KeStallExecutionProcessor(0xC8u);
    if ( (unsigned int)++v7 >= 0x4E20 )
    {
      if ( v7 == 20000 )
      {
        DbgPrintEx(0x93u, 1u, "XHCIDUMP: Unable to detect a device on port %u in %u ms\n", a2, 4000);
        v9 = -1073741632;
        goto LABEL_22;
      }
      break;
    }
  }
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Device found present on port %u\n", a2);
  *v6 = v8 & 0xE00C200 | 0x20000;
  _InterlockedOr(v17, 0);
  v10 = 16;
  v11 = *v6;
  if ( (*v6 & 0x10) != 0 )
  {
    DbgPrintEx(0x93u, 3u, "XHCIDUMP: Port reset is underway on port %u.\n", a2);
  }
  else
  {
    DbgPrintEx(0x93u, 3u, "XHCIDUMP: Issuing port reset on port %u.\n", a2);
    if ( a3 != 20 )
      v10 = 0x80000000;
    *v6 = v11 & 0xE00C200 | v10;
    _InterlockedOr(v17, 0);
  }
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Checking port %u for reset completion.\n", a2);
  for ( i = 0; ; ++i )
  {
    if ( i >= 0x3E8 )
    {
      DbgPrintEx(0x93u, 1u, "XHCIDUMP: Port %u failed to reset in %u ms\n", a2, 500 * i / 0x3E8);
      v9 = -1073741630;
      goto LABEL_22;
    }
    v13 = *v6;
    if ( (*v6 & 0x2001F3) == 0x200003 && (((*v6 & 0x3C00) - 1024) & 0xFFFFFBFF) != 0 )
      break;
    KeStallExecutionProcessor(0x1F4u);
  }
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Port %u is correctly reset in %u ms\n", a2, 500 * i / 0x3E8);
  v14 = v13 & 0xE00C200;
  v15 = v14 | 0x80000;
  if ( a3 != 30 )
    v15 = v14;
  *v6 = v15 | 0x200000;
  _InterlockedOr(v17, 0);
  v9 = 0;
LABEL_22:
  Crashdump_Register_LogRHPortInfo(a1, a2);
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Register_ResetPort: end 0x%X\n", v9);
  return v9;
}

```

## disassembly

```asm
0x140053264  push    rbx
0x140053266  push    rbp
0x140053267  push    rsi
0x140053268  push    rdi
0x140053269  push    r12
0x14005326b  push    r14
0x14005326d  push    r15
0x14005326f  sub     rsp, 30h
0x140053273  mov     r14d, r8d
0x140053276  mov     edi, edx
0x140053278  mov     r15, rcx
0x14005327b  lea     r8, aXhcidumpCrashd_35; "XHCIDUMP: Crashdump_Register_ResetPort:"...
0x140053282  mov     r9d, edx
0x140053285  mov     ebx, 3
0x14005328a  mov     r12d, 93h
0x140053290  mov     edx, ebx; Level
0x140053292  mov     ecx, r12d; ComponentId
0x140053295  call    cs:__imp_DbgPrintEx
0x14005329c  nop     dword ptr [rax+rax+00h]
0x1400532a1  mov     rax, [r15]
0x1400532a4  lea     esi, [rdi-1]
0x1400532a7  add     rsi, 40h ; '@'
0x1400532ab  lea     r8, aXhcidumpPollin; "XHCIDUMP: Polling port %u for device pr"...
0x1400532b2  shl     rsi, 4
0x1400532b6  mov     r9d, edi
0x1400532b9  mov     edx, ebx; Level
0x1400532bb  mov     ecx, r12d; ComponentId
0x1400532be  add     rsi, [rax+20h]
0x1400532c2  call    cs:__imp_DbgPrintEx
0x1400532c9  nop     dword ptr [rax+rax+00h]
0x1400532ce  xor     ebp, ebp
0x1400532d0  nop
0x1400532d1  mov     ebx, [rsi]
0x1400532d3  test    bl, 1
0x1400532d6  jnz     short loc_14005333E
0x1400532d8  cmp     r14d, 1Eh
0x1400532dc  jnz     short loc_1400532F1
0x1400532de  mov     eax, ebx
0x1400532e0  and     eax, 1E0h
0x1400532e5  sub     eax, 0C0h
0x1400532ea  test    eax, 0FFFFFF7Fh
0x1400532ef  jz      short loc_14005333E
0x1400532f1  mov     ecx, 0C8h; MicroSeconds
0x1400532f6  call    cs:__imp_KeStallExecutionProcessor
0x1400532fd  nop     dword ptr [rax+rax+00h]
0x140053302  inc     ebp
0x140053304  cmp     ebp, 4E20h
0x14005330a  jb      short loc_1400532D0
0x14005330c  jnz     short loc_14005333E
0x14005330e  mov     r9d, edi
0x140053311  mov     [rsp+68h+var_48], 0FA0h
0x140053319  lea     r8, aXhcidumpUnable; "XHCIDUMP: Unable to detect a device on "...
0x140053320  mov     edx, 1; Level
0x140053325  mov     ecx, r12d; ComponentId
0x140053328  call    cs:__imp_DbgPrintEx
0x14005332f  nop     dword ptr [rax+rax+00h]
0x140053334  mov     ebx, 0C00000C0h
0x140053339  jmp     loc_1400534B6
0x14005333e  mov     r9d, edi
0x140053341  lea     r8, aXhcidumpDevice_1; "XHCIDUMP: Device found present on port "...
0x140053348  mov     edx, 3; Level
0x14005334d  mov     ecx, r12d; ComponentId
0x140053350  call    cs:__imp_DbgPrintEx
0x140053357  nop     dword ptr [rax+rax+00h]
0x14005335c  and     ebx, 0E00C200h
0x140053362  bts     ebx, 11h
0x140053366  mov     [rsi], ebx
0x140053368  lock or [rsp+68h+var_68], 0
0x14005336d  mov     ebp, 10h
0x140053372  nop
0x140053373  mov     ebx, [rsi]
0x140053375  mov     r9d, edi
0x140053378  mov     ecx, r12d; ComponentId
0x14005337b  lea     edx, [rbp-0Dh]; Level
0x14005337e  test    bpl, bl
0x140053381  jz      short loc_140053398
0x140053383  lea     r8, aXhcidumpPortRe_1; "XHCIDUMP: Port reset is underway on por"...
0x14005338a  call    cs:__imp_DbgPrintEx
0x140053391  nop     dword ptr [rax+rax+00h]
0x140053396  jmp     short loc_1400533C6
0x140053398  lea     r8, aXhcidumpIssuin; "XHCIDUMP: Issuing port reset on port %u"...
0x14005339f  call    cs:__imp_DbgPrintEx
0x1400533a6  nop     dword ptr [rax+rax+00h]
0x1400533ab  cmp     r14d, 14h
0x1400533af  mov     eax, 80000000h
0x1400533b4  cmovnz  ebp, eax
0x1400533b7  and     ebx, 0E00C200h
0x1400533bd  or      ebp, ebx
0x1400533bf  mov     [rsi], ebp
0x1400533c1  lock or [rsp+68h+var_68], 0
0x1400533c6  mov     r9d, edi
0x1400533c9  lea     r8, aXhcidumpChecki; "XHCIDUMP: Checking port %u for reset co"...
0x1400533d0  mov     edx, 3; Level
0x1400533d5  mov     ecx, r12d; ComponentId
0x1400533d8  call    cs:__imp_DbgPrintEx
0x1400533df  nop     dword ptr [rax+rax+00h]
0x1400533e4  xor     ebp, ebp
0x1400533e6  cmp     ebp, 3E8h
0x1400533ec  jnb     loc_14005347F
0x1400533f2  nop
0x1400533f3  mov     ebx, [rsi]
0x1400533f5  mov     eax, ebx
0x1400533f7  and     eax, 2001F3h
0x1400533fc  cmp     eax, 200003h
0x140053401  jnz     short loc_140053416
0x140053403  mov     eax, ebx
0x140053405  and     eax, 3C00h
0x14005340a  sub     eax, 400h
0x14005340f  test    eax, 0FFFFFBFFh
0x140053414  jnz     short loc_14005342B
0x140053416  mov     ecx, 1F4h; MicroSeconds
0x14005341b  call    cs:__imp_KeStallExecutionProcessor
0x140053422  nop     dword ptr [rax+rax+00h]
0x140053427  inc     ebp
0x140053429  jmp     short loc_1400533E6
0x14005342b  imul    ecx, ebp, 1F4h
0x140053431  lea     r8, aXhcidumpPortUI; "XHCIDUMP: Port %u is correctly reset in"...
0x140053438  mov     eax, 10624DD3h
0x14005343d  mov     r9d, edi
0x140053440  mul     ecx
0x140053442  mov     ecx, r12d; ComponentId
0x140053445  shr     edx, 6
0x140053448  mov     [rsp+68h+var_48], edx
0x14005344c  mov     edx, 3; Level
0x140053451  call    cs:__imp_DbgPrintEx
0x140053458  nop     dword ptr [rax+rax+00h]
0x14005345d  and     ebx, 0E00C200h
0x140053463  mov     eax, ebx
0x140053465  bts     eax, 13h
0x140053469  cmp     r14d, 1Eh
0x14005346d  cmovnz  eax, ebx
0x140053470  bts     eax, 15h
0x140053474  mov     [rsi], eax
0x140053476  lock or [rsp+68h+var_68], 0
0x14005347b  xor     ebx, ebx
0x14005347d  jmp     short loc_1400534B6
0x14005347f  imul    ecx, ebp, 1F4h
0x140053485  lea     r8, aXhcidumpPortUF; "XHCIDUMP: Port %u failed to reset in %u"...
0x14005348c  mov     eax, 10624DD3h
0x140053491  mov     r9d, edi
0x140053494  mul     ecx
0x140053496  mov     ecx, r12d; ComponentId
0x140053499  shr     edx, 6
0x14005349c  mov     [rsp+68h+var_48], edx
0x1400534a0  mov     edx, 1; Level
0x1400534a5  call    cs:__imp_DbgPrintEx
0x1400534ac  nop     dword ptr [rax+rax+00h]
0x1400534b1  mov     ebx, 0C00000C2h
0x1400534b6  mov     edx, edi
0x1400534b8  mov     rcx, r15
0x1400534bb  call    Crashdump_Register_LogRHPortInfo
0x1400534c0  mov     r9d, ebx
0x1400534c3  lea     r8, aXhcidumpCrashd_14; "XHCIDUMP: Crashdump_Register_ResetPort:"...
0x1400534ca  mov     edx, 3; Level
0x1400534cf  mov     ecx, r12d; ComponentId
0x1400534d2  call    cs:__imp_DbgPrintEx
0x1400534d9  nop     dword ptr [rax+rax+00h]
0x1400534de  mov     eax, ebx
0x1400534e0  add     rsp, 30h
0x1400534e4  pop     r15
0x1400534e6  pop     r14
0x1400534e8  pop     r12
0x1400534ea  pop     rdi
0x1400534eb  pop     rsi
0x1400534ec  pop     rbp
0x1400534ed  pop     rbx
0x1400534ee  retn
```
