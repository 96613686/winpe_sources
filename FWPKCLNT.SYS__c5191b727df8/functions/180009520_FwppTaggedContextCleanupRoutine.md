# FwppTaggedContextCleanupRoutine

- ea: `0x180009520`
- end: `0x18000955c`
- name: `FwppTaggedContextCleanupRoutine`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180009520`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180009533`
- `ntoskrnl!ObfDereferenceObject` at `0x180009533`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180009549`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180009549`

## pseudocode

```c
void __fastcall FwppTaggedContextCleanupRoutine(__int64 a1)
{
  void *v1; // rbx
  void *v2; // rcx

  v1 = (void *)(a1 - 72);
  v2 = *(void **)(a1 - 72 + 40);
  if ( v2 )
    ObfDereferenceObject(v2);
  ExFreeToNPagedLookasideList(&stru_180048580, v1);
}

```

## disassembly

```asm
0x180009520  push    rbx
0x180009522  sub     rsp, 20h
0x180009526  lea     rbx, [rcx-48h]
0x18000952a  mov     rcx, [rbx+28h]; Object
0x18000952e  test    rcx, rcx
0x180009531  jz      short loc_18000953F
0x180009533  call    cs:__imp_ObfDereferenceObject
0x18000953a  nop     dword ptr [rax+rax+00h]
0x18000953f  mov     rdx, rbx; Entry
0x180009542  lea     rcx, stru_180048580; Lookaside
0x180009549  call    cs:__imp_ExFreeToNPagedLookasideList
0x180009550  nop     dword ptr [rax+rax+00h]
0x180009555  add     rsp, 20h
0x180009559  pop     rbx
0x18000955a  retn
```
