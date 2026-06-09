# PrjfClearNegativePathCache

- ea: `0x140006834`
- end: `0x140006932`
- name: `PrjfClearNegativePathCache`
- size: `254`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003e6c`
- `0x14002f134`

## callees

- `0x140006834`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400068c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400068d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400068c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400068d6`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140006906`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140006906`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400068a8`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400068a8`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1400068ea`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1400068ea`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140006894`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140006894`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140006853`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140006853`
- `FLTMGR!FltReleaseResource` at `0x140006915`
- `FLTMGR!FltReleaseResource` at `0x140006915`

## pseudocode

```c
void __fastcall PrjfClearNegativePathCache(__int64 a1, ULONG *a2)
{
  struct _ERESOURCE *v2; // rsi
  struct _RTL_DYNAMIC_HASH_TABLE *v5; // rbx
  ULONG NumEntries; // eax
  struct _LIST_ENTRY *Blink; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v8; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v9; // rdi
  _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+20h] [rbp-38h] BYREF

  v2 = (struct _ERESOURCE *)(a1 + 544);
  FltAcquireResourceExclusive((PERESOURCE)(a1 + 544));
  v5 = (struct _RTL_DYNAMIC_HASH_TABLE *)(a1 + 648);
  NumEntries = v5->NumEntries;
  if ( a2 )
    *a2 = NumEntries;
  if ( NumEntries )
  {
    memset(&Enumerator, 0, sizeof(Enumerator));
    RtlInitEnumerationHashTable(v5, &Enumerator);
    while ( 1 )
    {
      v8 = RtlEnumerateEntryHashTable(v5, &Enumerator);
      v9 = v8;
      if ( !v8 )
        break;
      RtlRemoveEntryHashTable(v5, v8, 0);
      Blink = v9[1].Linkage.Blink;
      if ( Blink )
        ExFreePoolWithTag(Blink, 0x6E664A50u);
      ExFreePoolWithTag(v9, 0x74684A50u);
    }
    RtlEndEnumerationHashTable(v5, &Enumerator);
  }
  FltReleaseResource(v2);
}

```

## disassembly

```asm
0x140006834  mov     [rsp+arg_0], rbx
0x140006839  mov     [rsp+arg_8], rsi
0x14000683e  push    rdi
0x14000683f  sub     rsp, 50h
0x140006843  lea     rsi, [rcx+220h]
0x14000684a  mov     rbx, rcx
0x14000684d  mov     rcx, rsi; Resource
0x140006850  mov     rdi, rdx
0x140006853  call    cs:__imp_FltAcquireResourceExclusive
0x14000685a  nop     dword ptr [rax+rax+00h]
0x14000685f  add     rbx, 288h
0x140006866  mov     eax, [rbx+14h]
0x140006869  test    rdi, rdi
0x14000686c  jz      short loc_140006870
0x14000686e  mov     [rdi], eax
0x140006870  test    eax, eax
0x140006872  jz      loc_140006912
0x140006878  xorps   xmm0, xmm0
0x14000687b  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x140006880  xor     eax, eax
0x140006882  mov     rcx, rbx; HashTable
0x140006885  movups  xmmword ptr [rsp+58h+Enumerator], xmm0
0x14000688a  mov     qword ptr [rsp+58h+Enumerator.BucketIndex], rax
0x14000688f  movups  xmmword ptr [rsp+58h+Enumerator+10h], xmm0
0x140006894  call    cs:__imp_RtlInitEnumerationHashTable
0x14000689b  nop     dword ptr [rax+rax+00h]
0x1400068a0  jmp     short loc_1400068E2
0x1400068a2  xor     r8d, r8d; Context
0x1400068a5  mov     rdx, rdi; Entry
0x1400068a8  call    cs:__imp_RtlRemoveEntryHashTable
0x1400068af  nop     dword ptr [rax+rax+00h]
0x1400068b4  mov     rcx, [rdi+20h]; P
0x1400068b8  test    rcx, rcx
0x1400068bb  jz      short loc_1400068CE
0x1400068bd  mov     edx, 6E664A50h; Tag
0x1400068c2  call    cs:__imp_ExFreePoolWithTag
0x1400068c9  nop     dword ptr [rax+rax+00h]
0x1400068ce  mov     edx, 74684A50h; Tag
0x1400068d3  mov     rcx, rdi; P
0x1400068d6  call    cs:__imp_ExFreePoolWithTag
0x1400068dd  nop     dword ptr [rax+rax+00h]
0x1400068e2  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x1400068e7  mov     rcx, rbx; HashTable
0x1400068ea  call    cs:__imp_RtlEnumerateEntryHashTable
0x1400068f1  nop     dword ptr [rax+rax+00h]
0x1400068f6  mov     rdi, rax
0x1400068f9  mov     rcx, rbx; HashTable
0x1400068fc  test    rax, rax
0x1400068ff  jnz     short loc_1400068A2
0x140006901  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x140006906  call    cs:__imp_RtlEndEnumerationHashTable
0x14000690d  nop     dword ptr [rax+rax+00h]
0x140006912  mov     rcx, rsi; Resource
0x140006915  call    cs:__imp_FltReleaseResource
0x14000691c  nop     dword ptr [rax+rax+00h]
0x140006921  mov     rbx, [rsp+58h+arg_0]
0x140006926  mov     rsi, [rsp+58h+arg_8]
0x14000692b  add     rsp, 50h
0x14000692f  pop     rdi
0x140006930  retn
```
