# AhcpCacheFilterForReboot

- ea: `0x140028bfc`
- end: `0x140028c92`
- name: `AhcpCacheFilterForReboot`
- size: `150`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140027d34`

## callees

- `0x140028bfc`
- `0x14003e364`
- `0x140055038`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140028c2a`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140028c2a`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140028c4e`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140028c4e`

## string_xrefs

- `0x140028c15`: `AhcpCacheFilterForReboot`
- `0x140028c6f`: `AhcpCacheFilterForReboot`
- `0x140028c5e`: `Failed to filter cache data for reboot [%x]`

## pseudocode

```c
__int64 __fastcall AhcpCacheFilterForReboot(__int64 a1)
{
  int v2; // edi

  AslLogCallPrintf(3, "AhcpCacheFilterForReboot", 3558, "Enter.");
  ExEnterCriticalRegionAndAcquireResourceExclusive(*(PERESOURCE *)a1);
  v2 = AhcStoreEnum(*(_QWORD *)(a1 + 8), AhcpCacheEnumEntryClearForReboot, 0);
  ExReleaseResourceAndLeaveCriticalRegion(*(PERESOURCE *)a1);
  if ( v2 >= 0 )
    return 0;
  else
    AslLogCallPrintf(1, "AhcpCacheFilterForReboot", 3573, "Failed to filter cache data for reboot [%x]", v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140028bfc  mov     [rsp+arg_0], rbx
0x140028c01  push    rdi
0x140028c02  sub     rsp, 30h
0x140028c06  mov     rbx, rcx
0x140028c09  lea     r9, aEnter; "Enter."
0x140028c10  mov     ecx, 3
0x140028c15  lea     rdx, aAhcpcachefilte; "AhcpCacheFilterForReboot"
0x140028c1c  mov     r8d, 0DE6h
0x140028c22  call    AslLogCallPrintf
0x140028c27  mov     rcx, [rbx]; Resource
0x140028c2a  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140028c31  nop     dword ptr [rax+rax+00h]
0x140028c36  mov     rcx, [rbx+8]
0x140028c3a  lea     rdx, AhcpCacheEnumEntryClearForReboot
0x140028c41  xor     r8d, r8d
0x140028c44  call    AhcStoreEnum
0x140028c49  mov     rcx, [rbx]; Resource
0x140028c4c  mov     edi, eax
0x140028c4e  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140028c55  nop     dword ptr [rax+rax+00h]
0x140028c5a  test    edi, edi
0x140028c5c  jns     short loc_140028C82
0x140028c5e  lea     r9, aFailedToFilter_0; "Failed to filter cache data for reboot "...
0x140028c65  mov     [rsp+38h+var_18], edi
0x140028c69  mov     r8d, 0DF5h
0x140028c6f  lea     rdx, aAhcpcachefilte; "AhcpCacheFilterForReboot"
0x140028c76  mov     ecx, 1
0x140028c7b  call    AslLogCallPrintf
0x140028c80  jmp     short loc_140028C84
0x140028c82  xor     edi, edi
0x140028c84  mov     rbx, [rsp+38h+arg_0]
0x140028c89  mov     eax, edi
0x140028c8b  add     rsp, 30h
0x140028c8f  pop     rdi
0x140028c90  retn
```
