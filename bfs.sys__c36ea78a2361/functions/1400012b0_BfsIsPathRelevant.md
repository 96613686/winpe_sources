# BfsIsPathRelevant

- ea: `0x1400012b0`
- end: `0x14000131a`
- name: `BfsIsPathRelevant`
- size: `106`
- prototype: `bool __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002620`

## callees

- `0x140001320`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400012ce`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400012ce`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400012f5`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400012f5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400012b9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400012b9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001301`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001301`

## pseudocode

```c
bool __fastcall BfsIsPathRelevant(__int64 a1)
{
  __int64 GlobalFileEntry; // rbx

  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&gBfsGlobalFileTable, 0);
  GlobalFileEntry = BfsGetGlobalFileEntry(&gBfsGlobalFileTable, a1);
  ExReleasePushLockSharedEx(&gBfsGlobalFileTable, 0);
  KeLeaveCriticalRegion();
  return GlobalFileEntry != 0;
}

```

## disassembly

```asm
0x1400012b0  push    rbx
0x1400012b2  sub     rsp, 20h
0x1400012b6  mov     rbx, rcx
0x1400012b9  call    cs:__imp_KeEnterCriticalRegion
0x1400012c0  nop     dword ptr [rax+rax+00h]
0x1400012c5  xor     edx, edx
0x1400012c7  lea     rcx, gBfsGlobalFileTable
0x1400012ce  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400012d5  nop     dword ptr [rax+rax+00h]
0x1400012da  mov     rdx, rbx
0x1400012dd  lea     rcx, gBfsGlobalFileTable
0x1400012e4  call    BfsGetGlobalFileEntry
0x1400012e9  xor     edx, edx
0x1400012eb  lea     rcx, gBfsGlobalFileTable
0x1400012f2  mov     rbx, rax
0x1400012f5  call    cs:__imp_ExReleasePushLockSharedEx
0x1400012fc  nop     dword ptr [rax+rax+00h]
0x140001301  call    cs:__imp_KeLeaveCriticalRegion
0x140001308  nop     dword ptr [rax+rax+00h]
0x14000130d  test    rbx, rbx
0x140001310  setnz   al
0x140001313  add     rsp, 20h
0x140001317  pop     rbx
0x140001318  retn
```
