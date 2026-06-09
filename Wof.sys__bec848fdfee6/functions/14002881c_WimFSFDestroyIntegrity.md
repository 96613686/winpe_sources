# WimFSFDestroyIntegrity

- ea: `0x14002881c`
- end: `0x1400288d4`
- name: `WimFSFDestroyIntegrity`
- size: `184`
- prototype: `void __fastcall(char *P)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140022e2c`
- `0x1400276d0`
- `0x1400284d8`
- `0x140029130`
- `0x140029910`

## callees

- `0x14002881c`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400288ad`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400288ad`
- `ntoskrnl!PsInitialSystemProcess` at `0x140028856`
- `ntoskrnl!MmUnmapViewOfSection` at `0x140028860`
- `ntoskrnl!MmUnmapViewOfSection` at `0x140028860`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028836`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400288c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028836`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400288c1`
- `ntoskrnl!ObfDereferenceObject` at `0x14002887d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002889d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002887d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002889d`

## pseudocode

```c
void __fastcall WimFSFDestroyIntegrity(char *P)
{
  void *v2; // rcx
  __int64 v3; // rdx
  void *v4; // rcx
  void *v5; // rcx

  v2 = (void *)*((_QWORD *)P + 22);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0x69637077u);
    *((_QWORD *)P + 22) = 0;
  }
  v3 = *((_QWORD *)P + 3);
  if ( v3 )
  {
    MmUnmapViewOfSection(PsInitialSystemProcess, v3);
    *((_QWORD *)P + 3) = 0;
  }
  v4 = (void *)*((_QWORD *)P + 2);
  if ( v4 )
  {
    ObfDereferenceObject(v4);
    *((_QWORD *)P + 2) = 0;
  }
  v5 = (void *)*((_QWORD *)P + 20);
  if ( v5 )
    ObfDereferenceObject(v5);
  ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)(P + 64));
  ExFreePoolWithTag(P, 0x69637077u);
}

```

## disassembly

```asm
0x14002881c  push    rbx
0x14002881e  sub     rsp, 20h
0x140028822  mov     rbx, rcx
0x140028825  mov     rcx, [rcx+0B0h]; P
0x14002882c  test    rcx, rcx
0x14002882f  jz      short loc_14002884D
0x140028831  mov     edx, 69637077h; Tag
0x140028836  call    cs:__imp_ExFreePoolWithTag
0x14002883d  nop     dword ptr [rax+rax+00h]
0x140028842  mov     qword ptr [rbx+0B0h], 0
0x14002884d  mov     rdx, [rbx+18h]
0x140028851  test    rdx, rdx
0x140028854  jz      short loc_140028874
0x140028856  mov     rcx, cs:__imp_PsInitialSystemProcess
0x14002885d  mov     rcx, [rcx]
0x140028860  call    cs:__imp_MmUnmapViewOfSection
0x140028867  nop     dword ptr [rax+rax+00h]
0x14002886c  mov     qword ptr [rbx+18h], 0
0x140028874  mov     rcx, [rbx+10h]; Object
0x140028878  test    rcx, rcx
0x14002887b  jz      short loc_140028891
0x14002887d  call    cs:__imp_ObfDereferenceObject
0x140028884  nop     dword ptr [rax+rax+00h]
0x140028889  mov     qword ptr [rbx+10h], 0
0x140028891  mov     rcx, [rbx+0A0h]; Object
0x140028898  test    rcx, rcx
0x14002889b  jz      short loc_1400288A9
0x14002889d  call    cs:__imp_ObfDereferenceObject
0x1400288a4  nop     dword ptr [rax+rax+00h]
0x1400288a9  lea     rcx, [rbx+40h]; Lookaside
0x1400288ad  call    cs:__imp_ExDeleteLookasideListEx
0x1400288b4  nop     dword ptr [rax+rax+00h]
0x1400288b9  mov     edx, 69637077h; Tag
0x1400288be  mov     rcx, rbx; P
0x1400288c1  call    cs:__imp_ExFreePoolWithTag
0x1400288c8  nop     dword ptr [rax+rax+00h]
0x1400288cd  add     rsp, 20h
0x1400288d1  pop     rbx
0x1400288d2  retn
```
