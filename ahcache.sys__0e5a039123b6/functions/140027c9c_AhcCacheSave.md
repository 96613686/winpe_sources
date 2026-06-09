# AhcCacheSave

- ea: `0x140027c9c`
- end: `0x140027d2e`
- name: `AhcCacheSave`
- size: `146`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140027d34`
- `0x14002b950`

## callees

- `0x140027c9c`
- `0x14003e364`
- `0x14005344c`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140027ccd`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140027ccd`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140027cea`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140027cea`

## string_xrefs

- `0x140027cb3`: `AhcCacheSave`
- `0x140027d0b`: `AhcCacheSave`

## pseudocode

```c
__int64 __fastcall AhcCacheSave(__int64 a1, __int64 a2)
{
  int v4; // ebx

  AslLogCallPrintf(3, "AhcCacheSave", 3613, "Enter.");
  ExEnterCriticalRegionAndAcquireResourceExclusive(*(PERESOURCE *)a1);
  v4 = AhcStoreSave(*(_QWORD *)(a1 + 8), a2);
  ExReleaseResourceAndLeaveCriticalRegion(*(PERESOURCE *)a1);
  if ( v4 >= 0 )
    return 0;
  else
    AslLogCallPrintf(1, "AhcCacheSave", 3628, "Failed to save stream buffer to store [%x]", v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140027c9c  mov     [rsp+arg_0], rbx
0x140027ca1  push    rdi
0x140027ca2  sub     rsp, 30h
0x140027ca6  mov     rbx, rdx
0x140027ca9  lea     r9, aEnter; "Enter."
0x140027cb0  mov     rdi, rcx
0x140027cb3  lea     rdx, aAhccachesave; "AhcCacheSave"
0x140027cba  mov     ecx, 3
0x140027cbf  mov     r8d, 0E1Dh
0x140027cc5  call    AslLogCallPrintf
0x140027cca  mov     rcx, [rdi]; Resource
0x140027ccd  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140027cd4  nop     dword ptr [rax+rax+00h]
0x140027cd9  mov     rcx, [rdi+8]
0x140027cdd  mov     rdx, rbx
0x140027ce0  call    AhcStoreSave
0x140027ce5  mov     rcx, [rdi]; Resource
0x140027ce8  mov     ebx, eax
0x140027cea  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140027cf1  nop     dword ptr [rax+rax+00h]
0x140027cf6  test    ebx, ebx
0x140027cf8  jns     short loc_140027D1E
0x140027cfa  lea     r9, aFailedToSaveSt; "Failed to save stream buffer to store ["...
0x140027d01  mov     [rsp+38h+var_18], ebx
0x140027d05  mov     r8d, 0E2Ch
0x140027d0b  lea     rdx, aAhccachesave; "AhcCacheSave"
0x140027d12  mov     ecx, 1
0x140027d17  call    AslLogCallPrintf
0x140027d1c  jmp     short loc_140027D20
0x140027d1e  xor     ebx, ebx
0x140027d20  mov     eax, ebx
0x140027d22  mov     rbx, [rsp+38h+arg_0]
0x140027d27  add     rsp, 30h
0x140027d2b  pop     rdi
0x140027d2c  retn
```
