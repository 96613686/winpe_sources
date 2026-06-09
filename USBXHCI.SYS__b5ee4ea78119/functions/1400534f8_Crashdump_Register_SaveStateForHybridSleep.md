# Crashdump_Register_SaveStateForHybridSleep

- ea: `0x1400534f8`
- end: `0x140053602`
- name: `Crashdump_Register_SaveStateForHybridSleep`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140051730`

## callees

- `0x1400534f8`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140053573`
- `ntoskrnl!DbgPrintEx` at `0x140053594`
- `ntoskrnl!DbgPrintEx` at `0x1400535c1`
- `ntoskrnl!DbgPrintEx` at `0x1400535e5`
- `ntoskrnl!DbgPrintEx` at `0x140053573`
- `ntoskrnl!DbgPrintEx` at `0x140053594`
- `ntoskrnl!DbgPrintEx` at `0x1400535c1`
- `ntoskrnl!DbgPrintEx` at `0x1400535e5`
- `HAL!KeStallExecutionProcessor` at `0x140053552`
- `HAL!KeStallExecutionProcessor` at `0x140053552`

## string_xrefs

- `0x1400535b0`: `XHCIDUMP: Controller State Save failed to complete\n`

## pseudocode

```c
__int64 __fastcall Crashdump_Register_SaveStateForHybridSleep(__int64 a1)
{
  _DWORD *v1; // rdi
  int v2; // eax
  unsigned int i; // ebx
  int v4; // eax
  signed __int32 v6[10]; // [rsp+0h] [rbp-28h] BYREF

  v1 = *(_DWORD **)(*(_QWORD *)a1 + 32LL);
  v2 = v1[1];
  if ( (v2 & 1) == 0 )
  {
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: Controller not halted\n");
    return 3221225666LL;
  }
  if ( (v2 & 0x300) != 0 )
  {
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: Controller State Save or Restore operation in progress\n");
    return 3221225666LL;
  }
  *v1 |= 0x100u;
  _InterlockedOr(v6, 0);
  for ( i = 0; i < 0x14; ++i )
  {
    v4 = v1[1];
    if ( (v4 & 0x400) != 0 )
    {
      DbgPrintEx(0x93u, 1u, "XHCIDUMP: Controller State Save failed\n");
      v1[1] = 1024;
      _InterlockedOr(v6, 0);
      return 3221225666LL;
    }
    if ( (v4 & 0x100) == 0 )
    {
      DbgPrintEx(0x93u, 3u, "XHCIDUMP: Controller State Save successful\n");
      return 0;
    }
    KeStallExecutionProcessor(0xC8u);
  }
  if ( i != 20 )
    return 0;
  DbgPrintEx(0x93u, 1u, "XHCIDUMP: Controller State Save failed to complete\n");
  return 3221225653LL;
}

```

## disassembly

```asm
0x1400534f8  mov     [rsp+arg_0], rbx
0x1400534fd  push    rdi
0x1400534fe  sub     rsp, 20h
0x140053502  mov     rax, [rcx]
0x140053505  mov     rdi, [rax+20h]
0x140053509  nop
0x14005350a  mov     eax, [rdi+4]
0x14005350d  test    al, 1
0x14005350f  jnz     short loc_14005351D
0x140053511  lea     r8, aXhcidumpContro_0; "XHCIDUMP: Controller not halted\n"
0x140053518  jmp     loc_1400535DB
0x14005351d  test    eax, 300h
0x140053522  jnz     loc_1400535D4
0x140053528  nop
0x140053529  mov     eax, [rdi]
0x14005352b  bts     eax, 8
0x14005352f  mov     [rdi], eax
0x140053531  lock or [rsp+28h+var_28], 0
0x140053536  xor     ebx, ebx
0x140053538  cmp     ebx, 14h
0x14005353b  jnb     short loc_1400535AE
0x14005353d  nop
0x14005353e  mov     eax, [rdi+4]
0x140053541  bt      eax, 0Ah
0x140053545  jb      short loc_140053583
0x140053547  bt      eax, 8
0x14005354b  jnb     short loc_140053562
0x14005354d  mov     ecx, 0C8h; MicroSeconds
0x140053552  call    cs:__imp_KeStallExecutionProcessor
0x140053559  nop     dword ptr [rax+rax+00h]
0x14005355e  inc     ebx
0x140053560  jmp     short loc_140053538
0x140053562  lea     r8, aXhcidumpContro_2; "XHCIDUMP: Controller State Save success"...
0x140053569  mov     edx, 3; Level
0x14005356e  mov     ecx, 93h; ComponentId
0x140053573  call    cs:__imp_DbgPrintEx
0x14005357a  nop     dword ptr [rax+rax+00h]
0x14005357f  xor     eax, eax
0x140053581  jmp     short loc_1400535F6
0x140053583  lea     r8, aXhcidumpContro_3; "XHCIDUMP: Controller State Save failed"...
0x14005358a  mov     edx, 1; Level
0x14005358f  mov     ecx, 93h; ComponentId
0x140053594  call    cs:__imp_DbgPrintEx
0x14005359b  nop     dword ptr [rax+rax+00h]
0x1400535a0  mov     dword ptr [rdi+4], 400h
0x1400535a7  lock or [rsp+28h+var_28], 0
0x1400535ac  jmp     short loc_1400535F1
0x1400535ae  jnz     short loc_14005357F
0x1400535b0  lea     r8, aXhcidumpContro_1; "XHCIDUMP: Controller State Save failed "...
0x1400535b7  mov     edx, 1; Level
0x1400535bc  mov     ecx, 93h; ComponentId
0x1400535c1  call    cs:__imp_DbgPrintEx
0x1400535c8  nop     dword ptr [rax+rax+00h]
0x1400535cd  mov     eax, 0C00000B5h
0x1400535d2  jmp     short loc_1400535F6
0x1400535d4  lea     r8, aXhcidumpContro; "XHCIDUMP: Controller State Save or Rest"...
0x1400535db  mov     edx, 1; Level
0x1400535e0  mov     ecx, 93h; ComponentId
0x1400535e5  call    cs:__imp_DbgPrintEx
0x1400535ec  nop     dword ptr [rax+rax+00h]
0x1400535f1  mov     eax, 0C00000C2h
0x1400535f6  mov     rbx, [rsp+28h+arg_0]
0x1400535fb  add     rsp, 20h
0x1400535ff  pop     rdi
0x140053600  retn
```
