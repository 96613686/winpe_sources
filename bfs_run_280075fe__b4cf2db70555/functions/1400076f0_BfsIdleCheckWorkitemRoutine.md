# BfsIdleCheckWorkitemRoutine

- ea: `0x1400076f0`
- end: `0x140007789`
- name: `BfsIdleCheckWorkitemRoutine`
- size: `153`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callees

- `0x140005c0c`
- `0x1400076f0`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14000776c`
- `ntoskrnl!IoFreeWorkItem` at `0x14000776c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140007751`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140007751`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007705`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000773e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007705`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000773e`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140007718`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140007718`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007726`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000775d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007726`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000775d`

## pseudocode

```c
void __fastcall BfsIdleCheckWorkitemRoutine(PVOID IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)
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
0x1400076f0  mov     [rsp+arg_0], rbx
0x1400076f5  mov     [rsp+arg_8], rsi
0x1400076fa  push    rdi
0x1400076fb  sub     rsp, 20h
0x1400076ff  mov     rdi, r8
0x140007702  mov     rsi, rdx
0x140007705  call    cs:__imp_KeEnterCriticalRegion
0x14000770c  nop     dword ptr [rax+rax+00h]
0x140007711  lea     rcx, gBfsRundownProtection; RunRef
0x140007718  call    cs:__imp_ExAcquireRundownProtection
0x14000771f  nop     dword ptr [rax+rax+00h]
0x140007724  mov     bl, al
0x140007726  call    cs:__imp_KeLeaveCriticalRegion
0x14000772d  nop     dword ptr [rax+rax+00h]
0x140007732  test    bl, bl
0x140007734  jz      short loc_140007769
0x140007736  mov     rcx, rsi
0x140007739  call    BfsCheckAndReleaseIdlePolicy
0x14000773e  call    cs:__imp_KeEnterCriticalRegion
0x140007745  nop     dword ptr [rax+rax+00h]
0x14000774a  lea     rcx, gBfsRundownProtection; RunRef
0x140007751  call    cs:__imp_ExReleaseRundownProtection
0x140007758  nop     dword ptr [rax+rax+00h]
0x14000775d  call    cs:__imp_KeLeaveCriticalRegion
0x140007764  nop     dword ptr [rax+rax+00h]
0x140007769  mov     rcx, rdi; IoWorkItem
0x14000776c  call    cs:__imp_IoFreeWorkItem
0x140007773  nop     dword ptr [rax+rax+00h]
0x140007778  mov     rbx, [rsp+28h+arg_0]
0x14000777d  mov     rsi, [rsp+28h+arg_8]
0x140007782  add     rsp, 20h
0x140007786  pop     rdi
0x140007787  retn
```
