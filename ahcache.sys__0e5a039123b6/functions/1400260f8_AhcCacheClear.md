# AhcCacheClear

- ea: `0x1400260f8`
- end: `0x14002616a`
- name: `AhcCacheClear`
- size: `114`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14002a3dc`
- `0x14002b128`
- `0x1400438c4`

## callees

- `0x14003e364`
- `0x140055038`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14002612a`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14002612a`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140026150`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140026150`

## string_xrefs

- `0x140026115`: `AhcCacheClear`

## pseudocode

```c
__int64 __fastcall AhcCacheClear(__int64 a1, int a2)
{
  unsigned int v3; // ebx
  int v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = a2;
  AslLogCallPrintf(3, "AhcCacheClear", 2101, "Enter.");
  ExEnterCriticalRegionAndAcquireResourceExclusive(*(PERESOURCE *)a1);
  v3 = AhcStoreEnum(*(_QWORD *)(a1 + 8), AhcpCacheEnumEntryClear, &v5);
  ExReleaseResourceAndLeaveCriticalRegion(*(PERESOURCE *)a1);
  return v3;
}

```

## disassembly

```asm
0x1400260f8  mov     [rsp+arg_0], rbx
0x1400260fd  mov     [rsp+arg_8], edx
0x140026101  push    rdi
0x140026102  sub     rsp, 20h
0x140026106  mov     rdi, rcx
0x140026109  lea     r9, aEnter; "Enter."
0x140026110  mov     ecx, 3
0x140026115  lea     rdx, aAhccacheclear; "AhcCacheClear"
0x14002611c  mov     r8d, 835h
0x140026122  call    AslLogCallPrintf
0x140026127  mov     rcx, [rdi]; Resource
0x14002612a  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140026131  nop     dword ptr [rax+rax+00h]
0x140026136  mov     rcx, [rdi+8]
0x14002613a  lea     r8, [rsp+28h+arg_8]
0x14002613f  lea     rdx, AhcpCacheEnumEntryClear
0x140026146  call    AhcStoreEnum
0x14002614b  mov     rcx, [rdi]; Resource
0x14002614e  mov     ebx, eax
0x140026150  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140026157  nop     dword ptr [rax+rax+00h]
0x14002615c  mov     eax, ebx
0x14002615e  mov     rbx, [rsp+28h+arg_0]
0x140026163  add     rsp, 20h
0x140026167  pop     rdi
0x140026168  retn
```
