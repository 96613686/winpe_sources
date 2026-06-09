# AhcCacheLoad

- ea: `0x140027b3c`
- end: `0x140027bbf`
- name: `AhcCacheLoad`
- size: `131`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140025054`

## callees

- `0x140027b3c`
- `0x14003e364`
- `0x14004b014`
- `0x140055038`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140027b4f`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140027b4f`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140027b7f`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140027b7f`

## string_xrefs

- `0x140027ba0`: `AhcCacheLoad`

## pseudocode

```c
__int64 __fastcall AhcCacheLoad(__int64 a1, __int64 a2)
{
  int v4; // ebx

  ExEnterCriticalRegionAndAcquireResourceExclusive(*(PERESOURCE *)a1);
  AhcStoreEnum(*(_QWORD *)(a1 + 8), AhcpStoreEnumEntryClear, 0);
  v4 = AhcStoreLoad(*(_QWORD *)(a1 + 8), a2);
  ExReleaseResourceAndLeaveCriticalRegion(*(PERESOURCE *)a1);
  if ( v4 < 0 )
    AslLogCallPrintf(1, "AhcCacheLoad", 3686, "Failed to load bits from stream to store [%x]", v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140027b3c  mov     [rsp+arg_0], rbx
0x140027b41  push    rdi
0x140027b42  sub     rsp, 30h
0x140027b46  mov     rdi, rcx
0x140027b49  mov     rbx, rdx
0x140027b4c  mov     rcx, [rcx]; Resource
0x140027b4f  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140027b56  nop     dword ptr [rax+rax+00h]
0x140027b5b  mov     rcx, [rdi+8]
0x140027b5f  lea     rdx, AhcpStoreEnumEntryClear
0x140027b66  xor     r8d, r8d
0x140027b69  call    AhcStoreEnum
0x140027b6e  mov     rcx, [rdi+8]
0x140027b72  mov     rdx, rbx
0x140027b75  call    AhcStoreLoad
0x140027b7a  mov     rcx, [rdi]; Resource
0x140027b7d  mov     ebx, eax
0x140027b7f  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140027b86  nop     dword ptr [rax+rax+00h]
0x140027b8b  test    ebx, ebx
0x140027b8d  jns     short loc_140027BB1
0x140027b8f  lea     r9, aFailedToLoadBi; "Failed to load bits from stream to stor"...
0x140027b96  mov     [rsp+38h+var_18], ebx
0x140027b9a  mov     r8d, 0E66h
0x140027ba0  lea     rdx, aAhccacheload; "AhcCacheLoad"
0x140027ba7  mov     ecx, 1
0x140027bac  call    AslLogCallPrintf
0x140027bb1  mov     eax, ebx
0x140027bb3  mov     rbx, [rsp+38h+arg_0]
0x140027bb8  add     rsp, 30h
0x140027bbc  pop     rdi
0x140027bbd  retn
```
