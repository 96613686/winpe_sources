# Crashdump_Register_BiosHandoff

- ea: `0x140052e78`
- end: `0x140052fb0`
- name: `Crashdump_Register_BiosHandoff`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140051aa0`

## callees

- `0x140052e78`
- `0x1400536cc`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140052ea2`
- `ntoskrnl!DbgPrintEx` at `0x140052f11`
- `ntoskrnl!DbgPrintEx` at `0x140052f3a`
- `ntoskrnl!DbgPrintEx` at `0x140052f65`
- `ntoskrnl!DbgPrintEx` at `0x140052f7f`
- `ntoskrnl!DbgPrintEx` at `0x140052ea2`
- `ntoskrnl!DbgPrintEx` at `0x140052f11`
- `ntoskrnl!DbgPrintEx` at `0x140052f3a`
- `ntoskrnl!DbgPrintEx` at `0x140052f65`
- `ntoskrnl!DbgPrintEx` at `0x140052f7f`
- `HAL!KeStallExecutionProcessor` at `0x140052ede`
- `HAL!KeStallExecutionProcessor` at `0x140052ede`

## string_xrefs

- `0x140052e96`: `XHCIDUMP: Legacy support capability not implemented, BIOS handoff will not be attempted.\n`
- `0x140052f2e`: `XHCIDUMP: Controller not halted after BIOS handoff, attempting to stop.\n`

## pseudocode

```c
__int64 __fastcall Crashdump_Register_BiosHandoff(__int64 a1)
{
  __int64 v2; // rbx
  int v3; // edi
  unsigned int v4; // esi
  __int64 v5; // r9
  const CHAR *v6; // r8
  int v7; // eax
  unsigned int v8; // esi
  signed __int32 v10[18]; // [rsp+0h] [rbp-48h] BYREF

  v2 = *(_QWORD *)(*(_QWORD *)a1 + 64LL);
  if ( v2 )
  {
    *(_BYTE *)(v2 + 3) |= 1u;
    _InterlockedOr(v10, 0);
    v3 = 20;
    v4 = 0;
    while ( (*(_BYTE *)(v2 + 2) & 1) != 0 )
    {
      if ( !v3 )
      {
        v5 = 2000000;
        v6 = "XHCIDUMP: HC BIOS Owned Semaphore bit not cleared after %dus. Ignoring for this controller.\n";
        goto LABEL_9;
      }
      --v3;
      v4 += 100000;
      KeStallExecutionProcessor(0x186A0u);
    }
    v5 = v4;
    v6 = "XHCIDUMP: HC BIOS Owned Semaphore bit cleared after %dus\n";
LABEL_9:
    DbgPrintEx(0x93u, 3u, v6, v5);
  }
  else
  {
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: Legacy support capability not implemented, BIOS handoff will not be attempted.\n");
  }
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 32LL) + 4LL) & 1) != 0 )
  {
    DbgPrintEx(0x93u, 3u, "XHCIDUMP: Controller halted after BIOS handoff.\n");
  }
  else
  {
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: Controller not halted after BIOS handoff, attempting to stop.\n");
    v7 = Crashdump_Register_StopController(a1);
    v8 = v7;
    if ( v7 < 0 )
    {
      DbgPrintEx(0x93u, 1u, "XHCIDUMP: Failed to stop controller 0x%X\n", v7);
      return v8;
    }
  }
  if ( v2 )
  {
    *(_DWORD *)(v2 + 4) &= 0x1FFFDFFFu;
    _InterlockedOr(v10, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140052e78  push    rbx
0x140052e7a  push    rsi
0x140052e7b  push    rdi
0x140052e7c  push    r14
0x140052e7e  sub     rsp, 28h
0x140052e82  mov     rax, [rcx]
0x140052e85  mov     r14, rcx
0x140052e88  mov     rbx, [rax+40h]
0x140052e8c  test    rbx, rbx
0x140052e8f  jnz     short loc_140052EB0
0x140052e91  mov     edi, 93h
0x140052e96  lea     r8, aXhcidumpLegacy; "XHCIDUMP: Legacy support capability not"...
0x140052e9d  mov     ecx, edi; ComponentId
0x140052e9f  lea     edx, [rbx+1]; Level
0x140052ea2  call    cs:__imp_DbgPrintEx
0x140052ea9  nop     dword ptr [rax+rax+00h]
0x140052eae  jmp     short loc_140052F1D
0x140052eb0  nop
0x140052eb1  mov     al, [rbx+3]
0x140052eb4  or      al, 1
0x140052eb6  mov     [rbx+3], al
0x140052eb9  lock or [rsp+48h+var_48], 0
0x140052ebe  mov     edi, 14h
0x140052ec3  xor     esi, esi
0x140052ec5  nop
0x140052ec6  mov     al, [rbx+2]
0x140052ec9  test    al, 1
0x140052ecb  jz      short loc_140052EFB
0x140052ecd  test    edi, edi
0x140052ecf  jz      short loc_140052EEC
0x140052ed1  dec     edi
0x140052ed3  add     esi, 186A0h
0x140052ed9  mov     ecx, 186A0h; MicroSeconds
0x140052ede  call    cs:__imp_KeStallExecutionProcessor
0x140052ee5  nop     dword ptr [rax+rax+00h]
0x140052eea  jmp     short loc_140052EC5
0x140052eec  mov     r9d, 1E8480h
0x140052ef2  lea     r8, aXhcidumpHcBios; "XHCIDUMP: HC BIOS Owned Semaphore bit n"...
0x140052ef9  jmp     short loc_140052F05
0x140052efb  mov     r9d, esi
0x140052efe  lea     r8, aXhcidumpHcBios_0; "XHCIDUMP: HC BIOS Owned Semaphore bit c"...
0x140052f05  mov     edi, 93h
0x140052f0a  mov     edx, 3; Level
0x140052f0f  mov     ecx, edi; ComponentId
0x140052f11  call    cs:__imp_DbgPrintEx
0x140052f18  nop     dword ptr [rax+rax+00h]
0x140052f1d  mov     rax, [r14]
0x140052f20  mov     ecx, edi; ComponentId
0x140052f22  mov     rax, [rax+20h]
0x140052f26  nop
0x140052f27  mov     eax, [rax+4]
0x140052f2a  test    al, 1
0x140052f2c  jnz     short loc_140052F73
0x140052f2e  lea     r8, aXhcidumpContro_4; "XHCIDUMP: Controller not halted after B"...
0x140052f35  mov     edx, 1; Level
0x140052f3a  call    cs:__imp_DbgPrintEx
0x140052f41  nop     dword ptr [rax+rax+00h]
0x140052f46  mov     rcx, r14
0x140052f49  call    Crashdump_Register_StopController
0x140052f4e  mov     esi, eax
0x140052f50  test    eax, eax
0x140052f52  jns     short loc_140052F8B
0x140052f54  mov     r9d, eax
0x140052f57  lea     r8, aXhcidumpFailed; "XHCIDUMP: Failed to stop controller 0x%"...
0x140052f5e  mov     edx, 1; Level
0x140052f63  mov     ecx, edi; ComponentId
0x140052f65  call    cs:__imp_DbgPrintEx
0x140052f6c  nop     dword ptr [rax+rax+00h]
0x140052f71  jmp     short loc_140052FA3
0x140052f73  lea     r8, aXhcidumpContro_5; "XHCIDUMP: Controller halted after BIOS "...
0x140052f7a  mov     edx, 3; Level
0x140052f7f  call    cs:__imp_DbgPrintEx
0x140052f86  nop     dword ptr [rax+rax+00h]
0x140052f8b  test    rbx, rbx
0x140052f8e  jz      short loc_140052FA1
0x140052f90  nop
0x140052f91  mov     eax, [rbx+4]
0x140052f94  and     eax, 1FFFDFFFh
0x140052f99  mov     [rbx+4], eax
0x140052f9c  lock or [rsp+48h+var_48], 0
0x140052fa1  xor     esi, esi
0x140052fa3  mov     eax, esi
0x140052fa5  add     rsp, 28h
0x140052fa9  pop     r14
0x140052fab  pop     rdi
0x140052fac  pop     rsi
0x140052fad  pop     rbx
0x140052fae  retn
```
