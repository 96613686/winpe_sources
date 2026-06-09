# Crashdump_Command_TestCommandRingOperation

- ea: `0x1400542f8`
- end: `0x140054369`
- name: `Crashdump_Command_TestCommandRingOperation`
- size: `113`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140051fcc`
- `0x1400521e0`

## callees

- `0x140053f98`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140054312`
- `ntoskrnl!DbgPrintEx` at `0x140054354`
- `ntoskrnl!DbgPrintEx` at `0x140054312`
- `ntoskrnl!DbgPrintEx` at `0x140054354`

## string_xrefs

- `0x140054301`: `XHCIDUMP: Crashdump_Command_TestCommandRingOperation: begin\n`
- `0x140054341`: `XHCIDUMP: Crashdump_Command_TestCommandRingOperation: end 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_Command_TestCommandRingOperation(__int64 *a1)
{
  __int128 v3; // [rsp+20h] [rbp-18h] BYREF

  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Command_TestCommandRingOperation: begin\n");
  v3 = 0;
  HIDWORD(v3) = 23552;
  LODWORD(a1) = Crashdump_Command_SendCommand(a1, (__int64)&v3, 0);
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Command_TestCommandRingOperation: end 0x%X\n", (_DWORD)a1);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x1400542f8  push    rbx
0x1400542fa  sub     rsp, 30h
0x1400542fe  mov     rbx, rcx
0x140054301  lea     r8, aXhcidumpCrashd_97; "XHCIDUMP: Crashdump_Command_TestCommand"...
0x140054308  mov     ecx, 93h; ComponentId
0x14005430d  mov     edx, 3; Level
0x140054312  call    cs:__imp_DbgPrintEx
0x140054319  nop     dword ptr [rax+rax+00h]
0x14005431e  xorps   xmm0, xmm0
0x140054321  lea     rdx, [rsp+38h+var_18]
0x140054326  movups  [rsp+38h+var_18], xmm0
0x14005432b  xor     r8d, r8d
0x14005432e  mov     dword ptr [rsp+38h+var_18+0Ch], 5C00h
0x140054336  mov     rcx, rbx
0x140054339  call    Crashdump_Command_SendCommand
0x14005433e  mov     r9d, eax
0x140054341  lea     r8, aXhcidumpCrashd_58; "XHCIDUMP: Crashdump_Command_TestCommand"...
0x140054348  mov     edx, 3; Level
0x14005434d  mov     ecx, 93h; ComponentId
0x140054352  mov     ebx, eax
0x140054354  call    cs:__imp_DbgPrintEx
0x14005435b  nop     dword ptr [rax+rax+00h]
0x140054360  mov     eax, ebx
0x140054362  add     rsp, 30h
0x140054366  pop     rbx
0x140054367  retn
```
