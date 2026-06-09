# CitmShutdown

- ea: `0x14002bd74`
- end: `0x14002be1b`
- name: `CitmShutdown`
- size: `167`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002a3dc`
- `0x14002a764`

## callees

- `0x14002bd74`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002bdd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bde8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bdd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bde8`
- `ntoskrnl!PsRemoveLoadImageNotifyRoutine` at `0x14002bd8d`
- `ntoskrnl!PsRemoveLoadImageNotifyRoutine` at `0x14002bd8d`

## pseudocode

```c
void __fastcall CitmShutdown(__int64 a1)
{
  NTSTATUS v2; // eax
  void *v3; // rcx

  if ( !*(_DWORD *)(a1 + 704) )
  {
    v2 = PsRemoveLoadImageNotifyRoutine((PLOAD_IMAGE_NOTIFY_ROUTINE)CitmpLoadImageCallback);
    if ( v2 < 0 )
      AslLogCallPrintf(1, "CitmShutdown", 465, "Failed to unregister callback [%x]", v2);
  }
  v3 = *(void **)(a1 + 664);
  if ( v3 )
    ExFreePoolWithTag(v3, 0x6D746943u);
  ExFreePoolWithTag(*(PVOID *)(a1 + 648), 0x6D746943u);
  *(_QWORD *)(a1 + 664) = 0;
  *(_QWORD *)(a1 + 648) = 0;
  *(_DWORD *)(a1 + 656) = 0;
}

```

## disassembly

```asm
0x14002bd74  push    rbx
0x14002bd76  sub     rsp, 30h
0x14002bd7a  cmp     dword ptr [rcx+2C0h], 0
0x14002bd81  mov     rbx, rcx
0x14002bd84  jnz     short loc_14002BDBF
0x14002bd86  lea     rcx, CitmpLoadImageCallback; NotifyRoutine
0x14002bd8d  call    cs:__imp_PsRemoveLoadImageNotifyRoutine
0x14002bd94  nop     dword ptr [rax+rax+00h]
0x14002bd99  test    eax, eax
0x14002bd9b  jns     short loc_14002BDBF
0x14002bd9d  lea     r9, aFailedToUnregi; "Failed to unregister callback [%x]"
0x14002bda4  mov     [rsp+38h+var_18], eax
0x14002bda8  mov     r8d, 1D1h
0x14002bdae  lea     rdx, aCitmshutdown; "CitmShutdown"
0x14002bdb5  mov     ecx, 1
0x14002bdba  call    AslLogCallPrintf
0x14002bdbf  mov     rcx, [rbx+298h]; P
0x14002bdc6  test    rcx, rcx
0x14002bdc9  jz      short loc_14002BDDC
0x14002bdcb  mov     edx, 6D746943h; Tag
0x14002bdd0  call    cs:__imp_ExFreePoolWithTag
0x14002bdd7  nop     dword ptr [rax+rax+00h]
0x14002bddc  mov     rcx, [rbx+288h]; P
0x14002bde3  mov     edx, 6D746943h; Tag
0x14002bde8  call    cs:__imp_ExFreePoolWithTag
0x14002bdef  nop     dword ptr [rax+rax+00h]
0x14002bdf4  mov     qword ptr [rbx+298h], 0
0x14002bdff  mov     qword ptr [rbx+288h], 0
0x14002be0a  mov     dword ptr [rbx+290h], 0
0x14002be14  add     rsp, 30h
0x14002be18  pop     rbx
0x14002be19  retn
```
