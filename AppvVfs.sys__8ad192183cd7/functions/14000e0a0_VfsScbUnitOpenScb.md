# VfsScbUnitOpenScb

- ea: `0x14000e0a0`
- end: `0x14000e109`
- name: `VfsScbUnitOpenScb`
- size: `105`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400037ac`
- `0x14000f188`

## callees

- `0x14000e0a0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000e0c2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000e0c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e0ee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e0ee`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e0e2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e0e2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e0b1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e0b1`

## pseudocode

```c
__int64 __fastcall VfsScbUnitOpenScb(__int64 a1)
{
  struct _ERESOURCE *v1; // rbx
  __int64 v3; // rbx

  v1 = *(struct _ERESOURCE **)(a1 + 8);
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite(v1, 1u);
  v3 = *(_QWORD *)(a1 + 16);
  if ( v3 )
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 276));
  ExReleaseResourceLite(*(PERESOURCE *)(a1 + 8));
  KeLeaveCriticalRegion();
  return v3;
}

```

## disassembly

```asm
0x14000e0a0  mov     [rsp+arg_0], rbx
0x14000e0a5  push    rdi
0x14000e0a6  sub     rsp, 20h
0x14000e0aa  mov     rbx, [rcx+8]
0x14000e0ae  mov     rdi, rcx
0x14000e0b1  call    cs:__imp_KeEnterCriticalRegion
0x14000e0b8  nop     dword ptr [rax+rax+00h]
0x14000e0bd  mov     dl, 1; Wait
0x14000e0bf  mov     rcx, rbx; Resource
0x14000e0c2  call    cs:__imp_ExAcquireResourceSharedLite
0x14000e0c9  nop     dword ptr [rax+rax+00h]
0x14000e0ce  mov     rbx, [rdi+10h]
0x14000e0d2  test    rbx, rbx
0x14000e0d5  jz      short loc_14000E0DE
0x14000e0d7  lock inc dword ptr [rbx+114h]
0x14000e0de  mov     rcx, [rdi+8]; Resource
0x14000e0e2  call    cs:__imp_ExReleaseResourceLite
0x14000e0e9  nop     dword ptr [rax+rax+00h]
0x14000e0ee  call    cs:__imp_KeLeaveCriticalRegion
0x14000e0f5  nop     dword ptr [rax+rax+00h]
0x14000e0fa  mov     rax, rbx
0x14000e0fd  mov     rbx, [rsp+28h+arg_0]
0x14000e102  add     rsp, 20h
0x14000e106  pop     rdi
0x14000e107  retn
```
