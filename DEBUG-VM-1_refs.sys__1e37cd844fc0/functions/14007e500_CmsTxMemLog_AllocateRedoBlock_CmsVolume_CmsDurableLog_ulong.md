# CmsTxMemLog::AllocateRedoBlock(CmsVolume *,CmsDurableLog *,ulong)

- ea: `0x14007e500`
- end: `0x14007e6b4`
- name: `?AllocateRedoBlock@CmsTxMemLog@@SAPEAU_SmsRedoBlock@@PEAVCmsVolume@@PEAVCmsDurableLog@@K@Z`
- size: `436`
- prototype: `struct _SmsRedoBlock *__fastcall(struct CmsVolume *, struct CmsDurableLog *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140159964`

## callees

- `0x14007e500`
- `0x14007e6bc`
- `0x1400ceda0`
- `0x14017cc0c`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007e689`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007e689`
- `ntoskrnl!ExAllocatePool2` at `0x14007e525`
- `ntoskrnl!ExAllocatePool2` at `0x14007e59a`
- `ntoskrnl!ExAllocatePool2` at `0x14007e525`
- `ntoskrnl!ExAllocatePool2` at `0x14007e59a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007e562`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007e562`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140200412`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140200412`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007e6a3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007e6a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e5fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e5fe`

## string_xrefs

- `0x14007e5aa`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
struct _SmsRedoBlock *__fastcall CmsTxMemLog::AllocateRedoBlock(
        struct CmsVolume *a1,
        struct CmsDurableLog *a2,
        int a3,
        __int64 a4)
{
  struct _SmsRedoBlock *result; // rax
  struct _SmsRedoBlock *v7; // rbx
  __int64 EntryHeaderSize; // rsi
  __int64 v9; // rdi
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 Pool2; // rax
  int v13; // ecx
  __int64 LogMetadataAddress; // rax
  int v15; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v16; // rcx

  result = (struct _SmsRedoBlock *)ExAllocatePool2(66, 72, 1766871885, a4);
  v7 = result;
  if ( !result )
    return result;
  memset(result, 0, 0x48u);
  EntryHeaderSize = (unsigned int)LogGetEntryHeaderSize(*((_QWORD *)a2 + 9), (unsigned int)(a3 + 8));
  v9 = qword_140269440 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( (unsigned int)EntryHeaderSize > *(_DWORD *)v9 )
  {
    v9 = 0;
    v11 = EntryHeaderSize + 16;
    goto LABEL_4;
  }
  if ( !*(_BYTE *)(v9 + 8) )
  {
    if ( (int)*(_QWORD *)(v9 + 88) > (int)HIDWORD(*(_QWORD *)(v9 + 88)) )
    {
      v13 = _InterlockedDecrement((volatile signed __int32 *)(v9 + 88));
      if ( v13 >= *(_DWORD *)(v9 + 92) && v13 >= 0 )
      {
        Pool2 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v9 + 64));
        goto LABEL_13;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 88));
    }
LABEL_10:
    v11 = *(unsigned int *)(v9 + 4);
LABEL_4:
    Pool2 = ExAllocatePool2(66, v11, 1766871885, v10);
    if ( (Pool2 & 0xF) != 0 )
      MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
    if ( !Pool2 )
      goto LABEL_12;
    goto LABEL_14;
  }
  v16 = (struct _NPAGED_LOOKASIDE_LIST *)(v9 + 64);
  if ( *(_BYTE *)(v9 + 9) )
    Pool2 = (__int64)ExAllocateFromNPagedLookasideList(v16);
  else
    Pool2 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v16);
LABEL_13:
  if ( !Pool2 )
    goto LABEL_10;
LABEL_14:
  *(_QWORD *)Pool2 = v9;
  if ( Pool2 == -16 )
  {
LABEL_12:
    ExFreePoolWithTag(v7, 0);
    return 0;
  }
  *(_QWORD *)v7 = Pool2 + 16;
  LogMetadataAddress = MlLogGetLogMetadataAddress(*((_QWORD *)a2 + 9));
  *((_QWORD *)v7 + 1) = LogMetadataAddress;
  LogMetadataAddress += 8;
  *((_QWORD *)v7 + 2) = LogMetadataAddress;
  *(_OWORD *)LogMetadataAddress = 0;
  *(_OWORD *)(LogMetadataAddress + 16) = 0;
  *(_OWORD *)(LogMetadataAddress + 32) = 0;
  *(_QWORD *)(LogMetadataAddress + 48) = 0;
  result = v7;
  v15 = *(_DWORD *)v7 - *((_DWORD *)v7 + 2);
  *(_QWORD *)((char *)v7 + 28) = 8;
  *((_DWORD *)v7 + 6) = EntryHeaderSize + v15;
  *((_DWORD *)v7 + 9) = EntryHeaderSize;
  return result;
}

```

## disassembly

```asm
0x14007e500  mov     [rsp+arg_8], rbx
0x14007e505  mov     [rsp+arg_10], rbp
0x14007e50a  push    rdi
0x14007e50b  sub     rsp, 20h
0x14007e50f  mov     edi, r8d
0x14007e512  mov     rbp, rdx
0x14007e515  mov     edx, 48h ; 'H'
0x14007e51a  mov     r8d, 6950534Dh
0x14007e520  mov     ecx, 42h ; 'B'
0x14007e525  call    cs:__imp_ExAllocatePool2
0x14007e52c  nop     dword ptr [rax+rax+00h]
0x14007e531  mov     rbx, rax
0x14007e534  test    rax, rax
0x14007e537  jz      loc_14007E679
0x14007e53d  xor     edx, edx; Val
0x14007e53f  mov     [rsp+28h+arg_0], rsi
0x14007e544  mov     r8d, 48h ; 'H'; Size
0x14007e54a  mov     rcx, rax; void *
0x14007e54d  call    memset
0x14007e552  mov     rcx, [rbp+48h]
0x14007e556  lea     edx, [rdi+8]
0x14007e559  call    LogGetEntryHeaderSize
0x14007e55e  xor     ecx, ecx; ProcNumber
0x14007e560  mov     esi, eax
0x14007e562  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14007e569  nop     dword ptr [rax+rax+00h]
0x14007e56e  xor     edx, edx
0x14007e570  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14007e576  lea     rdi, [rdx+rdx*2]
0x14007e57a  shl     rdi, 6
0x14007e57e  add     rdi, cs:qword_140269440
0x14007e585  cmp     esi, [rdi]
0x14007e587  jbe     short loc_14007E5B7
0x14007e589  xor     edi, edi
0x14007e58b  lea     rdx, [rsi+10h]
0x14007e58f  mov     ecx, 42h ; 'B'
0x14007e594  mov     r8d, 6950534Dh
0x14007e59a  call    cs:__imp_ExAllocatePool2
0x14007e5a1  nop     dword ptr [rax+rax+00h]
0x14007e5a6  test    al, 0Fh
0x14007e5a8  jz      short loc_14007E5F4
0x14007e5aa  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x14007e5b1  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x14007e5b7  cmp     byte ptr [rdi+8], 0
0x14007e5bb  jnz     loc_14007E67B
0x14007e5c1  mov     rcx, [rdi+58h]
0x14007e5c5  mov     rax, rcx
0x14007e5c8  shr     rax, 20h
0x14007e5cc  cmp     ecx, eax
0x14007e5ce  jle     short loc_14007E5EF
0x14007e5d0  nop
0x14007e5d1  mov     ecx, 0FFFFFFFFh
0x14007e5d6  lock xadd [rdi+58h], ecx
0x14007e5db  nop
0x14007e5dc  dec     ecx
0x14007e5de  mov     eax, [rdi+5Ch]
0x14007e5e1  cmp     ecx, eax
0x14007e5e3  jge     loc_14007E697
0x14007e5e9  nop
0x14007e5ea  lock inc dword ptr [rdi+58h]
0x14007e5ee  nop
0x14007e5ef  mov     edx, [rdi+4]
0x14007e5f2  jmp     short loc_14007E58F
0x14007e5f4  test    rax, rax
0x14007e5f7  jnz     short loc_14007E627
0x14007e5f9  xor     edx, edx; Tag
0x14007e5fb  mov     rcx, rbx; P
0x14007e5fe  call    cs:__imp_ExFreePoolWithTag
0x14007e605  nop     dword ptr [rax+rax+00h]
0x14007e60a  xor     eax, eax
0x14007e60c  mov     rsi, [rsp+28h+arg_0]
0x14007e611  mov     rbx, [rsp+28h+arg_8]
0x14007e616  mov     rbp, [rsp+28h+arg_10]
0x14007e61b  add     rsp, 20h
0x14007e61f  pop     rdi
0x14007e620  retn
0x14007e622  test    rax, rax
0x14007e625  jz      short loc_14007E5EF
0x14007e627  lea     rdx, [rax+10h]
0x14007e62b  mov     [rax], rdi
0x14007e62e  test    rdx, rdx
0x14007e631  jz      short loc_14007E5F9
0x14007e633  mov     [rbx], rdx
0x14007e636  mov     rcx, [rbp+48h]
0x14007e63a  call    MlLogGetLogMetadataAddress
0x14007e63f  mov     [rbx+8], rax
0x14007e643  xor     ecx, ecx
0x14007e645  add     rax, 8
0x14007e649  xorps   xmm0, xmm0
0x14007e64c  mov     [rbx+10h], rax
0x14007e650  movups  xmmword ptr [rax], xmm0
0x14007e653  movups  xmmword ptr [rax+10h], xmm0
0x14007e657  movups  xmmword ptr [rax+20h], xmm0
0x14007e65b  mov     [rax+30h], rcx
0x14007e65f  mov     rax, rbx
0x14007e662  mov     ecx, [rbx]
0x14007e664  sub     ecx, [rbx+8]
0x14007e667  add     ecx, esi
0x14007e669  mov     qword ptr [rbx+1Ch], 8
0x14007e671  mov     [rbx+18h], ecx
0x14007e674  mov     [rbx+24h], esi
0x14007e677  jmp     short loc_14007E60C
0x14007e679  jmp     short loc_14007E611
0x14007e67b  cmp     byte ptr [rdi+9], 0
0x14007e67f  lea     rcx, [rdi+40h]; Lookaside
0x14007e683  jz      loc_140200412
0x14007e689  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007e690  nop     dword ptr [rax+rax+00h]
0x14007e695  jmp     short loc_14007E622
0x14007e697  test    ecx, ecx
0x14007e699  js      loc_14007E5E9
0x14007e69f  lea     rcx, [rdi+40h]; ListHead
0x14007e6a3  call    cs:__imp_ExpInterlockedPopEntrySList
0x14007e6aa  nop     dword ptr [rax+rax+00h]
0x14007e6af  jmp     loc_14007E622
0x140200412  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140200419  nop     dword ptr [rax+rax+00h]
0x14020041e  nop
0x14020041f  jmp     loc_14007E622
```
