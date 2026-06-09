# CmsKeyRange::EnsureBuffersAreNotTransactionPrivate(void)

- ea: `0x14008d210`
- end: `0x14008d3f7`
- name: `?EnsureBuffersAreNotTransactionPrivate@CmsKeyRange@@QEAAJXZ`
- size: `487`
- prototype: `__int64 __fastcall(CmsKeyRange *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140052030`

## callees

- `0x14008d210`
- `0x1400ceda0`
- `0x1401f4100`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008d338`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008d338`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008d39b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008d39b`
- `ntoskrnl!ExAllocatePool2` at `0x14008d26b`
- `ntoskrnl!ExAllocatePool2` at `0x14008d26b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008d22f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008d22f`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1402013f0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1402013f0`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008d325`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008d325`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140201417`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140201417`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008d3b4`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008d3b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008d3e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008d3e6`

## string_xrefs

- `0x14008d27f`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsKeyRange::EnsureBuffersAreNotTransactionPrivate(CmsKeyRange *this)
{
  __int64 v2; // rbp
  __int64 v3; // rdi
  __int64 v4; // r9
  __int64 v5; // rdx
  __int64 Pool2; // rax
  __int64 result; // rax
  __int64 v8; // rdi
  __int64 v9; // rcx
  struct _SLIST_ENTRY *v10; // r8
  __int64 v11; // rsi
  struct _NPAGED_LOOKASIDE_LIST *v12; // rcx
  int v13; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v14; // rcx
  __int64 v15; // rcx

  if ( (*((_DWORD *)this + 6) & 8) == 0 )
    return 0;
  v2 = *((unsigned int *)this + 2);
  v3 = qword_140269420 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( (unsigned int)v2 > *(_DWORD *)v3 )
  {
    v3 = 0;
    v5 = v2 + 16;
    goto LABEL_4;
  }
  if ( *(_BYTE *)(v3 + 8) )
  {
    v14 = (struct _NPAGED_LOOKASIDE_LIST *)(v3 + 64);
    if ( *(_BYTE *)(v3 + 9) )
      Pool2 = (__int64)ExAllocateFromNPagedLookasideList(v14);
    else
      Pool2 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v14);
LABEL_7:
    if ( Pool2 )
      goto LABEL_8;
    goto LABEL_25;
  }
  if ( (int)*(_QWORD *)(v3 + 88) > (int)HIDWORD(*(_QWORD *)(v3 + 88)) )
  {
    v13 = _InterlockedDecrement((volatile signed __int32 *)(v3 + 88));
    if ( v13 >= *(_DWORD *)(v3 + 92) && v13 >= 0 )
    {
      Pool2 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v3 + 64));
      goto LABEL_7;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 88));
  }
LABEL_25:
  v5 = *(unsigned int *)(v3 + 4);
LABEL_4:
  Pool2 = ExAllocatePool2(66, v5, 1766871885, v4);
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( !Pool2 )
    return 3221225626LL;
LABEL_8:
  *(_QWORD *)Pool2 = v3;
  v8 = Pool2 + 16;
  if ( Pool2 == -16 )
    return 3221225626LL;
  if ( *(_QWORD *)this )
  {
    memmove((void *)(Pool2 + 16), *(const void **)this, *((unsigned int *)this + 2));
    v9 = *(_QWORD *)this;
    if ( (*((_DWORD *)this + 6) & 8) != 0 )
    {
      *(_BYTE *)(v9 - 2431) = 0;
      *((_DWORD *)this + 6) &= ~8u;
    }
    else if ( v9 )
    {
      v10 = (struct _SLIST_ENTRY *)(v9 - 16);
      v11 = *(_QWORD *)(v9 - 16);
      if ( !v11 )
        goto LABEL_33;
      if ( *(_BYTE *)(v11 + 8) )
      {
        v12 = (struct _NPAGED_LOOKASIDE_LIST *)(v11 + 64);
        if ( *(_BYTE *)(v11 + 9) )
          ExFreeToNPagedLookasideList(v12, v10);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v12, v10);
        goto LABEL_12;
      }
      v15 = *(_QWORD *)(v11 + 88);
      if ( (int)v15 < *(_DWORD *)(v11 + 80) || SHIDWORD(v15) >= (int)v15 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v11 + 64), v10);
        _InterlockedIncrement((volatile signed __int32 *)(v11 + 88));
      }
      else
      {
LABEL_33:
        ExFreePoolWithTag(v10, 0);
      }
    }
  }
LABEL_12:
  *((_DWORD *)this + 6) &= ~8u;
  result = 0;
  *(_QWORD *)this = v8;
  *((_DWORD *)this + 2) = v2;
  return result;
}

```

## disassembly

```asm
0x14008d210  push    rbx
0x14008d212  sub     rsp, 20h
0x14008d216  mov     eax, [rcx+18h]
0x14008d219  mov     rbx, rcx
0x14008d21c  test    al, 8
0x14008d21e  jz      short loc_14008D28C
0x14008d220  mov     [rsp+28h+arg_0], rbp
0x14008d225  mov     ebp, [rcx+8]
0x14008d228  xor     ecx, ecx; ProcNumber
0x14008d22a  mov     [rsp+28h+arg_10], rdi
0x14008d22f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008d236  nop     dword ptr [rax+rax+00h]
0x14008d23b  xor     edx, edx
0x14008d23d  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14008d243  lea     rdi, [rdx+rdx*2]
0x14008d247  shl     rdi, 6
0x14008d24b  add     rdi, cs:qword_140269420
0x14008d252  cmp     ebp, [rdi]
0x14008d254  jbe     loc_14008D34B
0x14008d25a  xor     edi, edi
0x14008d25c  lea     rdx, [rbp+10h]
0x14008d260  mov     ecx, 42h ; 'B'
0x14008d265  mov     r8d, 6950534Dh
0x14008d26b  call    cs:__imp_ExAllocatePool2
0x14008d272  nop     dword ptr [rax+rax+00h]
0x14008d277  test    al, 0Fh
0x14008d279  jz      loc_140201402
0x14008d27f  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x14008d286  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x14008d28c  xor     eax, eax
0x14008d28e  add     rsp, 20h
0x14008d292  pop     rbx
0x14008d293  retn
0x14008d295  test    rax, rax
0x14008d298  jz      loc_14008D37B
0x14008d29e  mov     [rax], rdi
0x14008d2a1  lea     rdi, [rax+10h]
0x14008d2a5  test    rdi, rdi
0x14008d2a8  jz      loc_14008D383
0x14008d2ae  mov     rdx, [rbx]; Src
0x14008d2b1  test    rdx, rdx
0x14008d2b4  jz      short loc_14008D2D7
0x14008d2b6  mov     r8d, [rbx+8]; Size
0x14008d2ba  mov     rcx, rdi; void *
0x14008d2bd  call    memmove
0x14008d2c2  mov     eax, [rbx+18h]
0x14008d2c5  mov     rcx, [rbx]
0x14008d2c8  test    al, 8
0x14008d2ca  jz      short loc_14008D2F4
0x14008d2cc  mov     byte ptr [rcx-97Fh], 0
0x14008d2d3  and     dword ptr [rbx+18h], 0FFFFFFF7h
0x14008d2d7  and     dword ptr [rbx+18h], 0FFFFFFF7h
0x14008d2db  xor     eax, eax
0x14008d2dd  mov     [rbx], rdi
0x14008d2e0  mov     [rbx+8], ebp
0x14008d2e3  mov     rbp, [rsp+28h+arg_0]
0x14008d2e8  mov     rdi, [rsp+28h+arg_10]
0x14008d2ed  add     rsp, 20h
0x14008d2f1  pop     rbx
0x14008d2f2  retn
0x14008d2f4  test    rcx, rcx
0x14008d2f7  jz      short loc_14008D2D7
0x14008d2f9  lea     r8, [rcx-10h]
0x14008d2fd  mov     [rsp+28h+arg_8], rsi
0x14008d302  mov     rsi, [r8]
0x14008d305  test    rsi, rsi
0x14008d308  jz      loc_14008D3E1
0x14008d30e  cmp     byte ptr [rsi+8], 0
0x14008d312  jz      loc_14008D3C5
0x14008d318  cmp     byte ptr [rsi+9], 0
0x14008d31c  lea     rcx, [rsi+40h]; Lookaside
0x14008d320  mov     rdx, r8; Entry
0x14008d323  jnz     short loc_14008D338
0x14008d325  call    cs:__imp_ExFreeToPagedLookasideList
0x14008d32c  nop     dword ptr [rax+rax+00h]
0x14008d331  mov     rsi, [rsp+28h+arg_8]
0x14008d336  jmp     short loc_14008D2D7
0x14008d338  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008d33f  nop     dword ptr [rax+rax+00h]
0x14008d344  mov     rsi, [rsp+28h+arg_8]
0x14008d349  jmp     short loc_14008D2D7
0x14008d34b  cmp     byte ptr [rdi+8], 0
0x14008d34f  jnz     short loc_14008D38D
0x14008d351  mov     rcx, [rdi+58h]
0x14008d355  mov     rax, rcx
0x14008d358  shr     rax, 20h
0x14008d35c  cmp     ecx, eax
0x14008d35e  jle     short loc_14008D37B
0x14008d360  nop
0x14008d361  mov     ecx, 0FFFFFFFFh
0x14008d366  lock xadd [rdi+58h], ecx
0x14008d36b  nop
0x14008d36c  dec     ecx
0x14008d36e  mov     eax, [rdi+5Ch]
0x14008d371  cmp     ecx, eax
0x14008d373  jge     short loc_14008D3AC
0x14008d375  nop
0x14008d376  lock inc dword ptr [rdi+58h]
0x14008d37a  nop
0x14008d37b  mov     edx, [rdi+4]
0x14008d37e  jmp     loc_14008D260
0x14008d383  mov     eax, 0C000009Ah
0x14008d388  jmp     loc_14008D2E3
0x14008d38d  cmp     byte ptr [rdi+9], 0
0x14008d391  lea     rcx, [rdi+40h]; Lookaside
0x14008d395  jz      loc_1402013F0
0x14008d39b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008d3a2  nop     dword ptr [rax+rax+00h]
0x14008d3a7  jmp     loc_14008D295
0x14008d3ac  test    ecx, ecx
0x14008d3ae  js      short loc_14008D375
0x14008d3b0  lea     rcx, [rdi+40h]; ListHead
0x14008d3b4  call    cs:__imp_ExpInterlockedPopEntrySList
0x14008d3bb  nop     dword ptr [rax+rax+00h]
0x14008d3c0  jmp     loc_14008D295
0x14008d3c5  mov     rcx, [rsi+58h]
0x14008d3c9  cmp     ecx, [rsi+50h]
0x14008d3cc  jl      loc_140201410
0x14008d3d2  mov     rax, rcx
0x14008d3d5  shr     rax, 20h
0x14008d3d9  cmp     eax, ecx
0x14008d3db  jge     loc_140201410
0x14008d3e1  xor     edx, edx; Tag
0x14008d3e3  mov     rcx, r8; P
0x14008d3e6  call    cs:__imp_ExFreePoolWithTag
0x14008d3ed  nop     dword ptr [rax+rax+00h]
0x14008d3f2  jmp     loc_14008D331
0x1402013f0  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1402013f7  nop     dword ptr [rax+rax+00h]
0x1402013fc  nop
0x1402013fd  jmp     loc_14008D295
0x140201402  test    rax, rax
0x140201405  jz      loc_14008D383
0x14020140b  jmp     loc_14008D29E
0x140201410  lea     rcx, [rsi+40h]; ListHead
0x140201414  mov     rdx, r8; ListEntry
0x140201417  call    cs:__imp_ExpInterlockedPushEntrySList
0x14020141e  nop     dword ptr [rax+rax+00h]
0x140201423  nop
0x140201424  lock inc dword ptr [rsi+58h]
0x140201428  nop
0x140201429  jmp     loc_14008D331
```
