# CmsRangeAndCountMap::PreAllocateRangeEntry(_SmsPreAllocatedRow *)

- ea: `0x1400883fc`
- end: `0x14008868e`
- name: `?PreAllocateRangeEntry@CmsRangeAndCountMap@@QEAAJPEAU_SmsPreAllocatedRow@@@Z`
- size: `658`
- prototype: `__int64 __fastcall(CmsRangeAndCountMap *__hidden this, struct _SmsPreAllocatedRow *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400cd694`

## callees

- `0x1400883fc`
- `0x140088930`
- `0x1400ceda0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400885d6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140088639`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400885d6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140088639`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140088433`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140088467`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140088433`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140088467`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140200e68`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140200e7a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140200e68`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140200e7a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400885f3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140088656`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400885f3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140088656`

## string_xrefs

- `0x140200e8c`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsRangeAndCountMap::PreAllocateRangeEntry(
        CmsRangeAndCountMap *this,
        struct _SmsPreAllocatedRow *a2)
{
  const struct std::nothrow_t *v3; // rdx
  __int64 v4; // rbx
  unsigned __int64 v5; // rcx
  const struct std::nothrow_t *v6; // rdx
  __int64 v7; // rbx
  unsigned __int64 v8; // rcx
  int v9; // ecx
  __m256i *v10; // rax
  __int16 v11; // bx
  int v13; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v14; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v15; // rcx
  __m256i v16; // [rsp+20h] [rbp-28h] BYREF

  memset(&v16, 0, 24);
  if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside2 < 0x40 )
  {
    v11 = 0x8000;
    v10 = (__m256i *)operator new(0x40u, a2);
    goto LABEL_16;
  }
  if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside1 >= 0x40 )
  {
    v3 = (const struct std::nothrow_t *)(KeGetCurrentProcessorNumberEx(0) % NumProcessors);
    v4 = qword_140269458 + 192LL * (_QWORD)v3;
    if ( *(_DWORD *)v4 < 0x40u )
    {
      v4 = 0;
      goto LABEL_5;
    }
    if ( *(_BYTE *)(v4 + 8) )
    {
      v14 = (struct _NPAGED_LOOKASIDE_LIST *)(v4 + 64);
      if ( *(_BYTE *)(v4 + 9) )
        v10 = (__m256i *)ExAllocateFromNPagedLookasideList(v14);
      else
        v10 = (__m256i *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v14);
    }
    else
    {
      if ( (int)*(_QWORD *)(v4 + 88) <= (int)HIDWORD(*(_QWORD *)(v4 + 88)) )
        goto LABEL_31;
      v9 = _InterlockedDecrement((volatile signed __int32 *)(v4 + 88));
      if ( v9 < *(_DWORD *)(v4 + 92) || v9 < 0 )
      {
        v10 = 0;
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 88));
      }
      else
      {
        v10 = (__m256i *)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v4 + 64));
      }
    }
    if ( v10 )
    {
LABEL_14:
      v10->m256i_i64[0] = v4;
      v10 = (__m256i *)((char *)v10 + 16);
LABEL_15:
      v11 = 0x2000;
      goto LABEL_16;
    }
LABEL_31:
    if ( v4 )
    {
      v5 = *(unsigned int *)(v4 + 4);
LABEL_33:
      v10 = (__m256i *)operator new(v5, v3);
      if ( ((unsigned __int8)v10 & 0xF) == 0 )
      {
        if ( !v10 )
          goto LABEL_15;
        goto LABEL_14;
      }
LABEL_47:
      MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
    }
LABEL_5:
    v5 = 80;
    goto LABEL_33;
  }
  KeGetCurrentProcessorNumberEx(0);
  v7 = qword_140269460;
  if ( *(_DWORD *)qword_140269460 < 0x40u )
  {
    v7 = 0;
    goto LABEL_8;
  }
  if ( *(_BYTE *)(qword_140269460 + 8) )
  {
    v15 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_140269460 + 64);
    if ( *(_BYTE *)(qword_140269460 + 9) )
      v10 = (__m256i *)ExAllocateFromNPagedLookasideList(v15);
    else
      v10 = (__m256i *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v15);
  }
  else
  {
    if ( (int)*(_QWORD *)(qword_140269460 + 88) <= (int)HIDWORD(*(_QWORD *)(qword_140269460 + 88)) )
      goto LABEL_40;
    v13 = _InterlockedDecrement((volatile signed __int32 *)(qword_140269460 + 88));
    if ( v13 < *(_DWORD *)(v7 + 92) || v13 < 0 )
    {
      v10 = 0;
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 88));
    }
    else
    {
      v10 = (__m256i *)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v7 + 64));
    }
  }
  if ( !v10 )
  {
LABEL_40:
    if ( v7 )
    {
      v8 = *(unsigned int *)(v7 + 4);
LABEL_42:
      v10 = (__m256i *)operator new(v8, v6);
      if ( ((unsigned __int8)v10 & 0xF) != 0 )
        goto LABEL_47;
      if ( !v10 )
        goto LABEL_25;
      goto LABEL_24;
    }
LABEL_8:
    v8 = 80;
    goto LABEL_42;
  }
LABEL_24:
  v10->m256i_i64[0] = v7;
  v10 = (__m256i *)((char *)v10 + 16);
LABEL_25:
  v11 = 0x4000;
LABEL_16:
  if ( !v10 )
    return 3221225626LL;
  v10->m256i_i16[14] = 0;
  v10[1] = v16;
  v10->m256i_i16[13] = 4128;
  v10->m256i_i16[14] |= v11;
  v10->m256i_i16[15] = 32;
  *((_QWORD *)a2 + 4) = v10;
  *(_DWORD *)a2 = v10->m256i_u8[27];
  *((_QWORD *)a2 + 1) = (char *)v10 + v10->m256i_u8[26];
  *((_WORD *)a2 + 2) = 0;
  *((_DWORD *)a2 + 4) = v10->m256i_u16[15];
  *((_QWORD *)a2 + 3) = (char *)v10 + v10->m256i_u8[26];
  return 0;
}

```

## disassembly

```asm
0x1400883fc  mov     [rsp+arg_0], rbx
0x140088401  push    rdi
0x140088402  sub     rsp, 40h
0x140088406  cmp     cs:?SizeOfAllocationsOnLookaside2@CmsAvlTableLite@@2KA, 40h ; '@'; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside2
0x14008840d  xorps   xmm0, xmm0
0x140088410  movdqu  xmmword ptr [rsp+48h+var_28+8], xmm0
0x140088416  mov     rdi, rdx
0x140088419  mov     qword ptr [rsp+48h+var_28], 0
0x140088422  jb      loc_140088557
0x140088428  xor     ecx, ecx; ProcNumber
0x14008842a  cmp     cs:?SizeOfAllocationsOnLookaside1@CmsAvlTableLite@@2KA, 40h ; '@'; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside1
0x140088431  jb      short loc_140088467
0x140088433  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008843a  nop     dword ptr [rax+rax+00h]
0x14008843f  xor     edx, edx; struct std::nothrow_t *
0x140088441  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140088447  lea     rbx, [rdx+rdx*2]
0x14008844b  shl     rbx, 6
0x14008844f  add     rbx, cs:qword_140269458
0x140088456  cmp     dword ptr [rbx], 40h ; '@'
0x140088459  jnb     short loc_14008848F
0x14008845b  xor     ebx, ebx
0x14008845d  mov     ecx, 50h ; 'P'
0x140088462  jmp     loc_140088610
0x140088467  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008846e  nop     dword ptr [rax+rax+00h]
0x140088473  mov     rbx, cs:qword_140269460
0x14008847a  cmp     dword ptr [rbx], 40h ; '@'
0x14008847d  jnb     loc_14008856B
0x140088483  xor     ebx, ebx
0x140088485  mov     ecx, 50h ; 'P'
0x14008848a  jmp     loc_140088673
0x14008848f  cmp     byte ptr [rbx+8], 0
0x140088493  jnz     loc_1400885C8
0x140088499  mov     rcx, [rbx+58h]
0x14008849d  mov     rax, rcx
0x1400884a0  sar     rax, 20h
0x1400884a4  cmp     ecx, eax
0x1400884a6  jle     loc_140088604
0x1400884ac  nop
0x1400884ad  or      ecx, 0FFFFFFFFh
0x1400884b0  lock xadd [rbx+58h], ecx
0x1400884b5  nop
0x1400884b6  dec     ecx
0x1400884b8  mov     eax, [rbx+5Ch]
0x1400884bb  cmp     ecx, eax
0x1400884bd  jge     loc_1400885E7
0x1400884c3  xor     eax, eax
0x1400884c5  nop
0x1400884c6  lock inc dword ptr [rbx+58h]
0x1400884ca  nop
0x1400884cb  test    rax, rax
0x1400884ce  jz      loc_140088604
0x1400884d4  mov     [rax], rbx
0x1400884d7  add     rax, 10h
0x1400884db  mov     ebx, 2000h
0x1400884e0  mov     rcx, rax
0x1400884e3  test    rax, rax
0x1400884e6  jz      short loc_1400884EE
0x1400884e8  xor     eax, eax
0x1400884ea  mov     [rcx+1Ch], ax
0x1400884ee  test    rcx, rcx
0x1400884f1  jz      loc_1400885C1
0x1400884f7  movups  xmm0, xmmword ptr [rsp+48h+var_28]
0x1400884fc  mov     eax, 20h ; ' '
0x140088501  movups  xmmword ptr [rcx+20h], xmm0
0x140088505  movups  xmm1, xmmword ptr [rsp+48h+var_28+10h]
0x14008850a  movups  xmmword ptr [rcx+30h], xmm1
0x14008850e  mov     word ptr [rcx+1Ah], 1020h
0x140088514  or      [rcx+1Ch], bx
0x140088518  mov     [rcx+1Eh], ax
0x14008851c  mov     [rdi+20h], rcx
0x140088520  movzx   eax, byte ptr [rcx+1Bh]
0x140088524  mov     [rdi], eax
0x140088526  movzx   eax, byte ptr [rcx+1Ah]
0x14008852a  add     rax, rcx
0x14008852d  mov     [rdi+8], rax
0x140088531  xor     eax, eax
0x140088533  mov     [rdi+4], ax
0x140088537  movzx   eax, word ptr [rcx+1Eh]
0x14008853b  mov     [rdi+10h], eax
0x14008853e  movzx   eax, byte ptr [rcx+1Ah]
0x140088542  add     rax, rcx
0x140088545  mov     [rdi+18h], rax
0x140088549  xor     eax, eax
0x14008854b  mov     rbx, [rsp+48h+arg_0]
0x140088550  add     rsp, 40h
0x140088554  pop     rdi
0x140088555  retn
0x140088557  mov     ecx, 40h ; '@'; unsigned __int64
0x14008855c  mov     ebx, 8000h
0x140088561  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140088566  jmp     loc_1400884E0
0x14008856b  cmp     byte ptr [rbx+8], 0
0x14008856f  jnz     loc_14008862B
0x140088575  mov     rcx, [rbx+58h]
0x140088579  mov     rax, rcx
0x14008857c  sar     rax, 20h
0x140088580  cmp     ecx, eax
0x140088582  jle     loc_140088667
0x140088588  nop
0x140088589  or      ecx, 0FFFFFFFFh
0x14008858c  lock xadd [rbx+58h], ecx
0x140088591  nop
0x140088592  dec     ecx
0x140088594  mov     eax, [rbx+5Ch]
0x140088597  cmp     ecx, eax
0x140088599  jge     loc_14008864A
0x14008859f  xor     eax, eax
0x1400885a1  nop
0x1400885a2  lock inc dword ptr [rbx+58h]
0x1400885a6  nop
0x1400885a7  test    rax, rax
0x1400885aa  jz      loc_140088667
0x1400885b0  mov     [rax], rbx
0x1400885b3  add     rax, 10h
0x1400885b7  mov     ebx, 4000h
0x1400885bc  jmp     loc_1400884E0
0x1400885c1  mov     eax, 0C000009Ah
0x1400885c6  jmp     short loc_14008854B
0x1400885c8  cmp     byte ptr [rbx+9], 0
0x1400885cc  lea     rcx, [rbx+40h]; Lookaside
0x1400885d0  jz      loc_140200E68
0x1400885d6  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400885dd  nop     dword ptr [rax+rax+00h]
0x1400885e2  jmp     loc_1400884CB
0x1400885e7  test    ecx, ecx
0x1400885e9  js      loc_1400884C3
0x1400885ef  lea     rcx, [rbx+40h]; ListHead
0x1400885f3  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400885fa  nop     dword ptr [rax+rax+00h]
0x1400885ff  jmp     loc_1400884CB
0x140088604  test    rbx, rbx
0x140088607  jz      loc_14008845D
0x14008860d  mov     ecx, [rbx+4]; unsigned __int64
0x140088610  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140088615  test    al, 0Fh
0x140088617  jnz     loc_140200E8C
0x14008861d  test    rax, rax
0x140088620  jz      loc_1400884DB
0x140088626  jmp     loc_1400884D4
0x14008862b  cmp     byte ptr [rbx+9], 0
0x14008862f  lea     rcx, [rbx+40h]; Lookaside
0x140088633  jz      loc_140200E7A
0x140088639  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140088640  nop     dword ptr [rax+rax+00h]
0x140088645  jmp     loc_1400885A7
0x14008864a  test    ecx, ecx
0x14008864c  js      loc_14008859F
0x140088652  lea     rcx, [rbx+40h]; ListHead
0x140088656  call    cs:__imp_ExpInterlockedPopEntrySList
0x14008865d  nop     dword ptr [rax+rax+00h]
0x140088662  jmp     loc_1400885A7
0x140088667  test    rbx, rbx
0x14008866a  jz      loc_140088485
0x140088670  mov     ecx, [rbx+4]; unsigned __int64
0x140088673  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140088678  test    al, 0Fh
0x14008867a  jnz     loc_140200E8C
0x140088680  test    rax, rax
0x140088683  jz      loc_1400885B7
0x140088689  jmp     loc_1400885B0
0x140200e68  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140200e6f  nop     dword ptr [rax+rax+00h]
0x140200e74  nop
0x140200e75  jmp     loc_1400884CB
0x140200e7a  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140200e81  nop     dword ptr [rax+rax+00h]
0x140200e86  nop
0x140200e87  jmp     loc_1400885A7
0x140200e8c  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140200e93  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
```
