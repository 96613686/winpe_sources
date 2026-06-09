# BfsIdleCheckWorkitemRoutine

- ea: `0x140007880`
- end: `0x140007919`
- name: `BfsIdleCheckWorkitemRoutine`
- size: `153`
- prototype: `void __fastcall(PVOID IoObject, __int64 Context, PIO_WORKITEM IoWorkItem)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callees

- `0x140005d9c`
- `0x140007880`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x1400078fc`
- `ntoskrnl!IoFreeWorkItem` at `0x1400078fc`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400078e1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400078e1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007895`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400078ce`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007895`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400078ce`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400078a8`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400078a8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400078b6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400078ed`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400078b6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400078ed`

## pseudocode

```c
void __fastcall BfsIdleCheckWorkitemRoutine(PVOID IoObject, __int64 Context, PIO_WORKITEM IoWorkItem)
{
  BOOLEAN v5; // bl

  KeEnterCriticalRegion();
  v5 = ExAcquireRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( v5 )
  {
    BfsCheckAndReleaseIdlePolicy(Context);
    KeEnterCriticalRegion();
    ExReleaseRundownProtection(&gBfsRundownProtection);
    KeLeaveCriticalRegion();
  }
  IoFreeWorkItem(IoWorkItem);
}

```

## disassembly

```asm
0x140007880  mov     [rsp+arg_0], rbx
0x140007885  mov     [rsp+arg_8], rsi
0x14000788a  push    rdi
0x14000788b  sub     rsp, 20h
0x14000788f  mov     rdi, r8
0x140007892  mov     rsi, rdx
0x140007895  call    cs:__imp_KeEnterCriticalRegion
0x14000789c  nop     dword ptr [rax+rax+00h]
0x1400078a1  lea     rcx, gBfsRundownProtection; RunRef
0x1400078a8  call    cs:__imp_ExAcquireRundownProtection
0x1400078af  nop     dword ptr [rax+rax+00h]
0x1400078b4  mov     bl, al
0x1400078b6  call    cs:__imp_KeLeaveCriticalRegion
0x1400078bd  nop     dword ptr [rax+rax+00h]
0x1400078c2  test    bl, bl
0x1400078c4  jz      short loc_1400078F9
0x1400078c6  mov     rcx, rsi
0x1400078c9  call    BfsCheckAndReleaseIdlePolicy
0x1400078ce  call    cs:__imp_KeEnterCriticalRegion
0x1400078d5  nop     dword ptr [rax+rax+00h]
0x1400078da  lea     rcx, gBfsRundownProtection; RunRef
0x1400078e1  call    cs:__imp_ExReleaseRundownProtection
0x1400078e8  nop     dword ptr [rax+rax+00h]
0x1400078ed  call    cs:__imp_KeLeaveCriticalRegion
0x1400078f4  nop     dword ptr [rax+rax+00h]
0x1400078f9  mov     rcx, rdi; IoWorkItem
0x1400078fc  call    cs:__imp_IoFreeWorkItem
0x140007903  nop     dword ptr [rax+rax+00h]
0x140007908  mov     rbx, [rsp+28h+arg_0]
0x14000790d  mov     rsi, [rsp+28h+arg_8]
0x140007912  add     rsp, 20h
0x140007916  pop     rdi
0x140007917  retn
```
