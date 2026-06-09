# IndexHashFree

- ea: `0x1400451d0`
- end: `0x14004523c`
- name: `IndexHashFree`
- size: `108`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140006c40`
- `0x1400451d0`
- `0x14006b4f4`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x1400451ed`
- `ntoskrnl!RtlDeleteHashTable` at `0x1400451ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045222`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045222`
- `NDIS!NdisFreeRWLock` at `0x1400451fc`
- `NDIS!NdisFreeRWLock` at `0x1400451fc`

## pseudocode

```c
__int64 __fastcall IndexHashFree(PRTL_DYNAMIC_HASH_TABLE *P, __int64 a2, int a3)
{
  IndexHashEmpty(P[2]);
  RtlDeleteHashTable(P[2]);
  NdisFreeRWLock((PNDIS_RW_LOCK_EX)*P);
  *P = 0;
  if ( a3 != -1 )
    WfpPoolFree(P + 1);
  ExFreePoolWithTag(P, 0);
  return 0;
}

```

## disassembly

```asm
0x1400451d0  mov     [rsp+arg_0], rbx
0x1400451d5  push    rdi
0x1400451d6  sub     rsp, 20h
0x1400451da  mov     rdi, rcx
0x1400451dd  mov     ebx, r8d
0x1400451e0  mov     rcx, [rcx+10h]; HashTable
0x1400451e4  call    IndexHashEmpty
0x1400451e9  mov     rcx, [rdi+10h]; HashTable
0x1400451ed  call    cs:__imp_RtlDeleteHashTable
0x1400451f4  nop     dword ptr [rax+rax+00h]
0x1400451f9  mov     rcx, [rdi]; Lock
0x1400451fc  call    cs:__imp_NdisFreeRWLock
0x140045203  nop     dword ptr [rax+rax+00h]
0x140045208  mov     qword ptr [rdi], 0
0x14004520f  cmp     ebx, 0FFFFFFFFh
0x140045212  jz      short loc_14004521D
0x140045214  lea     rcx, [rdi+8]
0x140045218  call    WfpPoolFree
0x14004521d  xor     edx, edx; Tag
0x14004521f  mov     rcx, rdi; P
0x140045222  call    cs:__imp_ExFreePoolWithTag
0x140045229  nop     dword ptr [rax+rax+00h]
0x14004522e  mov     rbx, [rsp+28h+arg_0]
0x140045233  xor     eax, eax
0x140045235  add     rsp, 20h
0x140045239  pop     rdi
0x14004523a  retn
```
