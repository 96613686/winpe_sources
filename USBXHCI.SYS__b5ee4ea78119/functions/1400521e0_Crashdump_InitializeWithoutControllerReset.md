# Crashdump_InitializeWithoutControllerReset

- ea: `0x1400521e0`
- end: `0x1400523be`
- name: `Crashdump_InitializeWithoutControllerReset`
- size: `478`
- prototype: `__int64 __fastcall(PVOID Address)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140051aa0`

## callees

- `0x14003d400`
- `0x1400521e0`
- `0x140053108`
- `0x140053e70`
- `0x1400542f8`
- `0x140055778`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1400523a6`
- `ntoskrnl!DbgPrintEx` at `0x1400523a6`
- `ntoskrnl!PoSetHiberRange` at `0x140052213`
- `ntoskrnl!PoSetHiberRange` at `0x14005222f`
- `ntoskrnl!PoSetHiberRange` at `0x14005225b`
- `ntoskrnl!PoSetHiberRange` at `0x140052281`
- `ntoskrnl!PoSetHiberRange` at `0x14005229e`
- `ntoskrnl!PoSetHiberRange` at `0x1400522bf`
- `ntoskrnl!PoSetHiberRange` at `0x1400522e0`
- `ntoskrnl!PoSetHiberRange` at `0x140052213`
- `ntoskrnl!PoSetHiberRange` at `0x14005222f`
- `ntoskrnl!PoSetHiberRange` at `0x14005225b`
- `ntoskrnl!PoSetHiberRange` at `0x140052281`
- `ntoskrnl!PoSetHiberRange` at `0x14005229e`
- `ntoskrnl!PoSetHiberRange` at `0x1400522bf`
- `ntoskrnl!PoSetHiberRange` at `0x1400522e0`
- `HAL!KeStallExecutionProcessor` at `0x140052306`
- `HAL!KeStallExecutionProcessor` at `0x140052306`

## string_xrefs

- `0x140052349`: `XHCIDUMP: Crashdump_Command_PrepareForDump failed with error 0x%X\n`
- `0x140052360`: `XHCIDUMP: Crashdump_Command_TestCommandRingOperation failed with error 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_InitializeWithoutControllerReset(char *Address)
{
  _QWORD *v1; // rbx
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  unsigned int i; // esi
  int v7; // eax
  signed __int32 v9[8]; // [rsp+0h] [rbp-58h] BYREF

  v1 = (_QWORD *)*((_QWORD *)Address + 62);
  if ( (_QWORD *)*v1 != v1 )
  {
    do
    {
      PoSetHiberRange(0, 0x10000u, v1, 0x68u, 0x43434858u);
      PoSetHiberRange(0, 0x10000u, (PVOID)v1[2], *((unsigned int *)v1 + 10), 0x43434858u);
      v1 = (_QWORD *)*v1;
    }
    while ( *v1 != *((_QWORD *)Address + 62) );
  }
  PoSetHiberRange(0, 0x10000u, Address, 0x278u, 0x43434858u);
  PoSetHiberRange(0, 0x10000u, *((PVOID *)Address + 71), (unsigned int)(376 * *((_DWORD *)Address + 134)), 0x43434858u);
  PoSetHiberRange(0, 0x10000u, *(PVOID *)Address, 0x90u, 0x43434858u);
  PoSetHiberRange(0, 0x10000u, *((PVOID *)Address + 77), 0x530u, 0x43434858u);
  PoSetHiberRange(0, 0x10000u, *((PVOID *)Address + 22), 0x68u, 0x43434858u);
  **(_DWORD **)(*(_QWORD *)Address + 32LL) &= ~0x400u;
  _InterlockedOr(v9, 0);
  KeStallExecutionProcessor(0x3E80u);
  Crashdump_Register_PrepareForHibernate(Address);
  Crashdump_EventRing_PrepareForHibernate(Address + 200, *(_QWORD *)(*((_QWORD *)Address + 77) + 128LL));
  v3 = Crashdump_Command_PrepareForDump((__int64)(Address + 328));
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = Crashdump_Command_TestCommandRingOperation((__int64 *)Address + 41);
    v4 = v5;
    if ( v5 >= 0 )
    {
      for ( i = 0; i < *((_DWORD *)Address + 134); ++i )
      {
        v7 = Crashdump_UsbDevice_PrepareForHibernate(*((_QWORD *)Address + 71) + 376LL * i);
        v4 = v7;
        if ( v7 < 0 )
        {
          DbgPrintEx(
            0x93u,
            1u,
            "XHCIDUMP: Crashdump_UsbDevice_PrepareForHibernate failed with error 0x%X\n",
            (unsigned int)v7);
          return v4;
        }
      }
    }
    else
    {
      DbgPrintEx(
        0x93u,
        1u,
        "XHCIDUMP: Crashdump_Command_TestCommandRingOperation failed with error 0x%X\n",
        (unsigned int)v5);
    }
  }
  else
  {
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: Crashdump_Command_PrepareForDump failed with error 0x%X\n", (unsigned int)v3);
  }
  return v4;
}

```

## disassembly

```asm
0x1400521e0  push    rbx
0x1400521e2  push    rbp
0x1400521e3  push    rsi
0x1400521e4  push    rdi
0x1400521e5  sub     rsp, 38h
0x1400521e9  mov     rbx, [rcx+1F0h]
0x1400521f0  mov     rdi, rcx
0x1400521f3  mov     esi, 43434858h
0x1400521f8  mov     ebp, 10000h
0x1400521fd  cmp     [rbx], rbx
0x140052200  jz      short loc_14005224A
0x140052202  mov     r9d, 68h ; 'h'; Length
0x140052208  mov     [rsp+58h+Tag], esi; Tag
0x14005220c  mov     r8, rbx; Address
0x14005220f  mov     edx, ebp; Flags
0x140052211  xor     ecx, ecx; MemoryMap
0x140052213  call    cs:__imp_PoSetHiberRange
0x14005221a  nop     dword ptr [rax+rax+00h]
0x14005221f  mov     r9d, [rbx+28h]; Length
0x140052223  mov     edx, ebp; Flags
0x140052225  mov     r8, [rbx+10h]; Address
0x140052229  xor     ecx, ecx; MemoryMap
0x14005222b  mov     [rsp+58h+Tag], esi; Tag
0x14005222f  call    cs:__imp_PoSetHiberRange
0x140052236  nop     dword ptr [rax+rax+00h]
0x14005223b  mov     rbx, [rbx]
0x14005223e  mov     rax, [rdi+1F0h]
0x140052245  cmp     [rbx], rax
0x140052248  jnz     short loc_140052202
0x14005224a  mov     r9d, 278h; Length
0x140052250  mov     [rsp+58h+Tag], esi; Tag
0x140052254  mov     r8, rdi; Address
0x140052257  mov     edx, ebp; Flags
0x140052259  xor     ecx, ecx; MemoryMap
0x14005225b  call    cs:__imp_PoSetHiberRange
0x140052262  nop     dword ptr [rax+rax+00h]
0x140052267  imul    r9d, [rdi+218h], 178h; Length
0x140052272  mov     edx, ebp; Flags
0x140052274  mov     r8, [rdi+238h]; Address
0x14005227b  xor     ecx, ecx; MemoryMap
0x14005227d  mov     [rsp+58h+Tag], esi; Tag
0x140052281  call    cs:__imp_PoSetHiberRange
0x140052288  nop     dword ptr [rax+rax+00h]
0x14005228d  mov     r8, [rdi]; Address
0x140052290  mov     r9d, 90h; Length
0x140052296  mov     edx, ebp; Flags
0x140052298  mov     [rsp+58h+Tag], esi; Tag
0x14005229c  xor     ecx, ecx; MemoryMap
0x14005229e  call    cs:__imp_PoSetHiberRange
0x1400522a5  nop     dword ptr [rax+rax+00h]
0x1400522aa  mov     r8, [rdi+268h]; Address
0x1400522b1  mov     r9d, 530h; Length
0x1400522b7  mov     edx, ebp; Flags
0x1400522b9  mov     [rsp+58h+Tag], esi; Tag
0x1400522bd  xor     ecx, ecx; MemoryMap
0x1400522bf  call    cs:__imp_PoSetHiberRange
0x1400522c6  nop     dword ptr [rax+rax+00h]
0x1400522cb  mov     r8, [rdi+0B0h]; Address
0x1400522d2  mov     r9d, 68h ; 'h'; Length
0x1400522d8  mov     edx, ebp; Flags
0x1400522da  mov     [rsp+58h+Tag], esi; Tag
0x1400522de  xor     ecx, ecx; MemoryMap
0x1400522e0  call    cs:__imp_PoSetHiberRange
0x1400522e7  nop     dword ptr [rax+rax+00h]
0x1400522ec  mov     rax, [rdi]
0x1400522ef  mov     rcx, [rax+20h]
0x1400522f3  nop
0x1400522f4  mov     eax, [rcx]
0x1400522f6  btr     eax, 0Ah
0x1400522fa  mov     [rcx], eax
0x1400522fc  lock or [rsp+58h+var_58], 0
0x140052301  mov     ecx, 3E80h; MicroSeconds
0x140052306  call    cs:__imp_KeStallExecutionProcessor
0x14005230d  nop     dword ptr [rax+rax+00h]
0x140052312  mov     rcx, rdi
0x140052315  call    Crashdump_Register_PrepareForHibernate
0x14005231a  mov     rdx, [rdi+268h]
0x140052321  lea     rcx, [rdi+0C8h]
0x140052328  mov     rdx, [rdx+80h]
0x14005232f  call    Crashdump_EventRing_PrepareForHibernate
0x140052334  lea     rsi, [rdi+148h]
0x14005233b  mov     rcx, rsi
0x14005233e  call    Crashdump_Command_PrepareForDump
0x140052343  mov     ebx, eax
0x140052345  test    eax, eax
0x140052347  jns     short loc_140052352
0x140052349  lea     r8, aXhcidumpCrashd_42; "XHCIDUMP: Crashdump_Command_PrepareForD"...
0x140052350  jmp     short loc_140052399
0x140052352  mov     rcx, rsi
0x140052355  call    Crashdump_Command_TestCommandRingOperation
0x14005235a  mov     ebx, eax
0x14005235c  test    eax, eax
0x14005235e  jns     short loc_140052369
0x140052360  lea     r8, aXhcidumpCrashd_54; "XHCIDUMP: Crashdump_Command_TestCommand"...
0x140052367  jmp     short loc_140052399
0x140052369  xor     esi, esi
0x14005236b  cmp     esi, [rdi+218h]
0x140052371  jnb     short loc_1400523B2
0x140052373  mov     eax, esi
0x140052375  imul    rcx, rax, 178h
0x14005237c  add     rcx, [rdi+238h]
0x140052383  call    Crashdump_UsbDevice_PrepareForHibernate
0x140052388  mov     ebx, eax
0x14005238a  test    eax, eax
0x14005238c  js      short loc_140052392
0x14005238e  inc     esi
0x140052390  jmp     short loc_14005236B
0x140052392  lea     r8, aXhcidumpCrashd_32; "XHCIDUMP: Crashdump_UsbDevice_PrepareFo"...
0x140052399  mov     r9d, eax
0x14005239c  mov     edx, 1; Level
0x1400523a1  mov     ecx, 93h; ComponentId
0x1400523a6  call    cs:__imp_DbgPrintEx
0x1400523ad  nop     dword ptr [rax+rax+00h]
0x1400523b2  mov     eax, ebx
0x1400523b4  add     rsp, 38h
0x1400523b8  pop     rdi
0x1400523b9  pop     rsi
0x1400523ba  pop     rbp
0x1400523bb  pop     rbx
0x1400523bc  retn
```
