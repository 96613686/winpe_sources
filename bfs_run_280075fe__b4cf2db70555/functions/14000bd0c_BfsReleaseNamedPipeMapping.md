# BfsReleaseNamedPipeMapping

- ea: `0x14000bd0c`
- end: `0x14000bdde`
- name: `BfsReleaseNamedPipeMapping`
- size: `210`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001460`
- `0x140002a30`
- `0x140003e40`
- `0x14000b790`

## callees

- `0x14000bd0c`
- `0x140012b9c`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000bd2d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000bd2d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000bdba`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000bdba`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000bd88`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000bd98`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000bd88`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000bd98`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bd66`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bd78`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bda9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bd66`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bd78`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bda9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bd1c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bd1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bdc6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bdc6`

## pseudocode

```c
void __fastcall BfsReleaseNamedPipeMapping(__int64 a1, __int64 a2)
{
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1, 0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 24), 0xFFFFFFFF) == 1 && !*(_DWORD *)(a2 + 24) )
  {
    if ( (*(_DWORD *)(a2 + 28) & 1) != 0 )
      BfsRemoveEntryHashTable(*(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 8), (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)a2);
    ExFreePoolWithTag(*(PVOID *)(a2 + 32), 0);
    ExFreePoolWithTag(*(PVOID *)(a2 + 40), 0);
    RtlFreeUnicodeString((PUNICODE_STRING)(a2 + 48));
    RtlFreeUnicodeString((PUNICODE_STRING)(a2 + 64));
    ExFreePoolWithTag((PVOID)a2, 0);
  }
  ExReleasePushLockExclusiveEx(a1, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14000bd0c  mov     [rsp+arg_0], rbx
0x14000bd11  push    rdi
0x14000bd12  sub     rsp, 20h
0x14000bd16  mov     rbx, rdx
0x14000bd19  mov     rdi, rcx
0x14000bd1c  call    cs:__imp_KeEnterCriticalRegion
0x14000bd23  nop     dword ptr [rax+rax+00h]
0x14000bd28  xor     edx, edx
0x14000bd2a  mov     rcx, rdi
0x14000bd2d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000bd34  nop     dword ptr [rax+rax+00h]
0x14000bd39  or      eax, 0FFFFFFFFh
0x14000bd3c  lock xadd [rbx+18h], eax
0x14000bd41  cmp     eax, 1
0x14000bd44  jnz     short loc_14000BDB5
0x14000bd46  mov     eax, [rbx+18h]
0x14000bd49  test    eax, eax
0x14000bd4b  jnz     short loc_14000BDB5
0x14000bd4d  mov     eax, [rbx+1Ch]
0x14000bd50  test    al, 1
0x14000bd52  jz      short loc_14000BD60
0x14000bd54  mov     rcx, [rdi+8]
0x14000bd58  mov     rdx, rbx
0x14000bd5b  call    BfsRemoveEntryHashTable
0x14000bd60  mov     rcx, [rbx+20h]; P
0x14000bd64  xor     edx, edx; Tag
0x14000bd66  call    cs:__imp_ExFreePoolWithTag
0x14000bd6d  nop     dword ptr [rax+rax+00h]
0x14000bd72  mov     rcx, [rbx+28h]; P
0x14000bd76  xor     edx, edx; Tag
0x14000bd78  call    cs:__imp_ExFreePoolWithTag
0x14000bd7f  nop     dword ptr [rax+rax+00h]
0x14000bd84  lea     rcx, [rbx+30h]; UnicodeString
0x14000bd88  call    cs:__imp_RtlFreeUnicodeString
0x14000bd8f  nop     dword ptr [rax+rax+00h]
0x14000bd94  lea     rcx, [rbx+40h]; UnicodeString
0x14000bd98  call    cs:__imp_RtlFreeUnicodeString
0x14000bd9f  nop     dword ptr [rax+rax+00h]
0x14000bda4  xor     edx, edx; Tag
0x14000bda6  mov     rcx, rbx; P
0x14000bda9  call    cs:__imp_ExFreePoolWithTag
0x14000bdb0  nop     dword ptr [rax+rax+00h]
0x14000bdb5  xor     edx, edx
0x14000bdb7  mov     rcx, rdi
0x14000bdba  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000bdc1  nop     dword ptr [rax+rax+00h]
0x14000bdc6  call    cs:__imp_KeLeaveCriticalRegion
0x14000bdcd  nop     dword ptr [rax+rax+00h]
0x14000bdd2  mov     rbx, [rsp+28h+arg_0]
0x14000bdd7  add     rsp, 20h
0x14000bddb  pop     rdi
0x14000bddc  retn
```
