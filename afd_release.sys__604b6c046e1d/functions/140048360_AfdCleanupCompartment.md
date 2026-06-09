# AfdCleanupCompartment

- ea: `0x140048360`
- end: `0x140048402`
- name: `AfdCleanupCompartment`
- size: `162`
- prototype: `void __fastcall(PVOID **P)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140015ae0`
- `0x140048410`

## callees

- `0x140048360`
- `0x140051834`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400483bc`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400483bc`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14004839c`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14004839c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140048370`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140048370`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400483d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400483e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400483d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400483e8`

## pseudocode

```c
void __fastcall AfdCleanupCompartment(PVOID **P)
{
  PVOID *v2; // rcx
  PVOID *v3; // rax
  struct _ERESOURCE *v4; // rcx

  ExEnterCriticalRegionAndAcquireResourceExclusive(AfdGlobalData);
  v2 = *P;
  if ( (*P)[1] != P || (v3 = P[1], *v3 != P) )
    __fastfail(3u);
  *v3 = v2;
  v2[1] = v3;
  ExReleaseResourceAndLeaveCriticalRegion(AfdGlobalData);
  AfdDeregisterPnPHandlers(P);
  v4 = (struct _ERESOURCE *)P[24];
  if ( v4 )
  {
    ExDeleteResourceLite(v4);
    ExFreePoolWithTag(P[24], 0x72646641u);
  }
  ExFreePoolWithTag(P, 0x72646641u);
}

```

## disassembly

```asm
0x140048360  push    rbx
0x140048362  sub     rsp, 20h
0x140048366  mov     rbx, rcx
0x140048369  mov     rcx, cs:AfdGlobalData; Resource
0x140048370  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140048377  nop     dword ptr [rax+rax+00h]
0x14004837c  mov     rcx, [rbx]
0x14004837f  cmp     [rcx+8], rbx
0x140048383  jnz     short loc_1400483FB
0x140048385  mov     rax, [rbx+8]
0x140048389  cmp     [rax], rbx
0x14004838c  jnz     short loc_1400483FB
0x14004838e  mov     [rax], rcx
0x140048391  mov     [rcx+8], rax
0x140048395  mov     rcx, cs:AfdGlobalData; Resource
0x14004839c  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400483a3  nop     dword ptr [rax+rax+00h]
0x1400483a8  mov     rcx, rbx
0x1400483ab  call    AfdDeregisterPnPHandlers
0x1400483b0  mov     rcx, [rbx+0C0h]; Resource
0x1400483b7  test    rcx, rcx
0x1400483ba  jz      short loc_1400483E0
0x1400483bc  call    cs:__imp_ExDeleteResourceLite
0x1400483c3  nop     dword ptr [rax+rax+00h]
0x1400483c8  mov     rcx, [rbx+0C0h]; P
0x1400483cf  mov     edx, 72646641h; Tag
0x1400483d4  call    cs:__imp_ExFreePoolWithTag
0x1400483db  nop     dword ptr [rax+rax+00h]
0x1400483e0  mov     edx, 72646641h; Tag
0x1400483e5  mov     rcx, rbx; P
0x1400483e8  call    cs:__imp_ExFreePoolWithTag
0x1400483ef  nop     dword ptr [rax+rax+00h]
0x1400483f4  add     rsp, 20h
0x1400483f8  pop     rbx
0x1400483f9  retn
0x1400483fb  mov     ecx, 3
0x140048400  int     29h; Win8: RtlFailFast(ecx)
```
