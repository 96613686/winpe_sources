# AfdCleanupCompartment

- ea: `0x1400483e0`
- end: `0x140048482`
- name: `AfdCleanupCompartment`
- size: `162`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140015ae0`
- `0x140048490`

## callees

- `0x1400483e0`
- `0x1400518d4`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14004843c`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004843c`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14004841c`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14004841c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400483f0`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400483f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048454`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048468`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048454`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048468`

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
  AfdDeregisterPnPHandlers((__int64)P);
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
0x1400483e0  push    rbx
0x1400483e2  sub     rsp, 20h
0x1400483e6  mov     rbx, rcx
0x1400483e9  mov     rcx, cs:AfdGlobalData; Resource
0x1400483f0  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1400483f7  nop     dword ptr [rax+rax+00h]
0x1400483fc  mov     rcx, [rbx]
0x1400483ff  cmp     [rcx+8], rbx
0x140048403  jnz     short loc_14004847B
0x140048405  mov     rax, [rbx+8]
0x140048409  cmp     [rax], rbx
0x14004840c  jnz     short loc_14004847B
0x14004840e  mov     [rax], rcx
0x140048411  mov     [rcx+8], rax
0x140048415  mov     rcx, cs:AfdGlobalData; Resource
0x14004841c  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140048423  nop     dword ptr [rax+rax+00h]
0x140048428  mov     rcx, rbx
0x14004842b  call    AfdDeregisterPnPHandlers
0x140048430  mov     rcx, [rbx+0C0h]; Resource
0x140048437  test    rcx, rcx
0x14004843a  jz      short loc_140048460
0x14004843c  call    cs:__imp_ExDeleteResourceLite
0x140048443  nop     dword ptr [rax+rax+00h]
0x140048448  mov     rcx, [rbx+0C0h]; P
0x14004844f  mov     edx, 72646641h; Tag
0x140048454  call    cs:__imp_ExFreePoolWithTag
0x14004845b  nop     dword ptr [rax+rax+00h]
0x140048460  mov     edx, 72646641h; Tag
0x140048465  mov     rcx, rbx; P
0x140048468  call    cs:__imp_ExFreePoolWithTag
0x14004846f  nop     dword ptr [rax+rax+00h]
0x140048474  add     rsp, 20h
0x140048478  pop     rbx
0x140048479  retn
0x14004847b  mov     ecx, 3
0x140048480  int     29h; Win8: RtlFailFast(ecx)
```
