# BfsDereferenceTableEntry

- ea: `0x140011404`
- end: `0x1400114e0`
- name: `BfsDereferenceTableEntry`
- size: `220`
- prototype: `void __fastcall(volatile signed __int32 *Buffer)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140006330`
- `0x140006fa4`
- `0x1400104ec`
- `0x1400107ec`
- `0x140011194`
- `0x140011cd4`
- `0x140012608`

## callees

- `0x140011404`
- `0x140011994`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001143c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001143c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400114ac`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400114ac`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14001145d`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14001145d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001146c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001146c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001147d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001149b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001147d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001149b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001142b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001142b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400114b8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400114b8`

## pseudocode

```c
void __fastcall BfsDereferenceTableEntry(volatile signed __int32 *Buffer)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  struct _UNICODE_STRING *v4; // rbx
  void *v5; // rbp

  do
  {
    if ( _InterlockedExchangeAdd(Buffer + 38, 0xFFFFFFFF) != 1 )
      break;
    v2 = *((_QWORD *)Buffer + 18);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v2, 0);
    v3 = *((_QWORD *)Buffer + 18);
    v4 = *(struct _UNICODE_STRING **)Buffer;
    v5 = (void *)*((_QWORD *)Buffer + 3);
    RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(v3 + 32), (PVOID)Buffer);
    RtlFreeUnicodeString(v4);
    ExFreePoolWithTag(v4, 0);
    if ( v5 )
    {
      BfsFreeDirectoryBlockList(v5);
      ExFreePoolWithTag(v5, 0);
    }
    ExReleasePushLockExclusiveEx(v3, 0);
    KeLeaveCriticalRegion();
    Buffer = (volatile signed __int32 *)(v3 - 8);
  }
  while ( *(_QWORD *)(v3 - 8 + 144) );
}

```

## disassembly

```asm
0x140011404  push    rbx
0x140011406  push    rbp
0x140011407  push    rsi
0x140011408  push    rdi
0x140011409  sub     rsp, 28h
0x14001140d  mov     rdi, rcx
0x140011410  or      eax, 0FFFFFFFFh
0x140011413  lock xadd [rdi+98h], eax
0x14001141b  cmp     eax, 1
0x14001141e  jnz     loc_1400114D6
0x140011424  mov     rbx, [rdi+90h]
0x14001142b  call    cs:__imp_KeEnterCriticalRegion
0x140011432  nop     dword ptr [rax+rax+00h]
0x140011437  xor     edx, edx
0x140011439  mov     rcx, rbx
0x14001143c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140011443  nop     dword ptr [rax+rax+00h]
0x140011448  mov     rsi, [rdi+90h]
0x14001144f  mov     rdx, rdi; Buffer
0x140011452  mov     rbx, [rdi]
0x140011455  mov     rbp, [rdi+18h]
0x140011459  lea     rcx, [rsi+20h]; Table
0x14001145d  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140011464  nop     dword ptr [rax+rax+00h]
0x140011469  mov     rcx, rbx; UnicodeString
0x14001146c  call    cs:__imp_RtlFreeUnicodeString
0x140011473  nop     dword ptr [rax+rax+00h]
0x140011478  xor     edx, edx; Tag
0x14001147a  mov     rcx, rbx; P
0x14001147d  call    cs:__imp_ExFreePoolWithTag
0x140011484  nop     dword ptr [rax+rax+00h]
0x140011489  test    rbp, rbp
0x14001148c  jz      short loc_1400114A7
0x14001148e  mov     rcx, rbp
0x140011491  call    BfsFreeDirectoryBlockList
0x140011496  xor     edx, edx; Tag
0x140011498  mov     rcx, rbp; P
0x14001149b  call    cs:__imp_ExFreePoolWithTag
0x1400114a2  nop     dword ptr [rax+rax+00h]
0x1400114a7  xor     edx, edx
0x1400114a9  mov     rcx, rsi
0x1400114ac  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400114b3  nop     dword ptr [rax+rax+00h]
0x1400114b8  call    cs:__imp_KeLeaveCriticalRegion
0x1400114bf  nop     dword ptr [rax+rax+00h]
0x1400114c4  lea     rdi, [rsi-8]
0x1400114c8  cmp     qword ptr [rdi+90h], 0
0x1400114d0  jnz     loc_140011410
0x1400114d6  add     rsp, 28h
0x1400114da  pop     rdi
0x1400114db  pop     rsi
0x1400114dc  pop     rbp
0x1400114dd  pop     rbx
0x1400114de  retn
```
