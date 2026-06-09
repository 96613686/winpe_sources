# CmsTxMemLog::DiscardPendingRecords(CmsDurableLog *)

- ea: `0x14005c510`
- end: `0x14005c6ba`
- name: `?DiscardPendingRecords@CmsTxMemLog@@QEAAXPEAVCmsDurableLog@@@Z`
- size: `426`
- prototype: `void __fastcall(CmsTxMemLog *__hidden this, struct CmsDurableLog *)`
- caller_count: `16`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140012c34`
- `0x140012ec0`
- `0x1400130c0`
- `0x140014d60`
- `0x140018a00`
- `0x14002c480`
- `0x14002d430`
- `0x14002e990`
- `0x140040610`
- `0x1400568e0`
- `0x14005bdb8`
- `0x14005d060`
- `0x1400600d4`
- `0x140062700`
- `0x14006dad0`
- `0x1400bff94`

## callees

- `0x14005c510`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005c56b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005c5e7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005c56b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005c5e7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005c637`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005c648`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005c637`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005c648`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fdd21`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fdd3f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fdd21`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fdd3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c581`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c5fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c677`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c6a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c581`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c5fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c677`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c6a9`

## pseudocode

```c
void __fastcall CmsTxMemLog::DiscardPendingRecords(CmsTxMemLog *this, struct CmsDurableLog *a2)
{
  __int64 *v2; // rbx
  __int64 v5; // r8
  __int64 *v6; // rdi
  __int64 v7; // rsi
  struct _SLIST_ENTRY *v8; // r8
  struct _NPAGED_LOOKASIDE_LIST *v9; // rcx
  __int64 *v10; // rbx
  __int64 v11; // rcx
  __int64 *v12; // rdi
  __int64 v13; // rsi
  struct _SLIST_ENTRY *v14; // r8
  struct _NPAGED_LOOKASIDE_LIST *v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx

  v2 = (__int64 *)*((_QWORD *)this + 3);
  while ( v2 )
  {
    v5 = *v2;
    v6 = v2;
    v2 = (__int64 *)v2[6];
    if ( v5 )
    {
      v7 = *(_QWORD *)(v5 - 16);
      v8 = (struct _SLIST_ENTRY *)(v5 - 16);
      if ( !v7 )
        goto LABEL_20;
      if ( *(_BYTE *)(v7 + 8) )
      {
        v9 = (struct _NPAGED_LOOKASIDE_LIST *)(v7 + 64);
        if ( *(_BYTE *)(v7 + 9) )
          ExFreeToNPagedLookasideList(v9, v8);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v9, v8);
        goto LABEL_7;
      }
      v17 = *(_QWORD *)(v7 + 88);
      if ( (int)v17 < *(_DWORD *)(v7 + 80) || SHIDWORD(v17) >= (int)v17 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v7 + 64), v8);
        _InterlockedIncrement((volatile signed __int32 *)(v7 + 88));
      }
      else
      {
LABEL_20:
        ExFreePoolWithTag(v8, 0);
      }
    }
LABEL_7:
    ExFreePoolWithTag(v6, 0);
  }
  v10 = (__int64 *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  while ( v10 )
  {
    v11 = *v10;
    v12 = v10;
    v10 = (__int64 *)v10[6];
    if ( v11 )
    {
      v13 = *(_QWORD *)(v11 - 16);
      v14 = (struct _SLIST_ENTRY *)(v11 - 16);
      if ( !v13 )
        goto LABEL_23;
      if ( *(_BYTE *)(v13 + 8) )
      {
        v15 = (struct _NPAGED_LOOKASIDE_LIST *)(v13 + 64);
        if ( *(_BYTE *)(v13 + 9) )
          ExFreeToNPagedLookasideList(v15, v14);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v15, v14);
        goto LABEL_14;
      }
      v18 = *(_QWORD *)(v13 + 88);
      if ( (int)v18 < *(_DWORD *)(v13 + 80) || SHIDWORD(v18) >= (int)v18 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v13 + 64), v14);
        _InterlockedIncrement((volatile signed __int32 *)(v13 + 88));
      }
      else
      {
LABEL_23:
        ExFreePoolWithTag(v14, 0);
      }
    }
LABEL_14:
    ExFreePoolWithTag(v12, 0);
  }
  v16 = *((_DWORD *)this + 12);
  *((_QWORD *)this + 2) = 0;
  _InterlockedAdd((volatile signed __int32 *)a2 + 72, -v16);
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 5) = 0;
}

```

## disassembly

```asm
0x14005c510  push    rbx
0x14005c512  push    rbp
0x14005c513  push    rsi
0x14005c514  push    rdi
0x14005c515  push    r14
0x14005c517  push    r15
0x14005c519  sub     rsp, 28h
0x14005c51d  mov     rbx, [rcx+18h]
0x14005c521  mov     rbp, rdx
0x14005c524  mov     r14, rcx
0x14005c527  test    rbx, rbx
0x14005c52a  jz      short loc_14005C592
0x14005c52c  nop     dword ptr [rax+00h]
0x14005c530  mov     r8, [rbx]
0x14005c533  mov     rdi, rbx
0x14005c536  mov     rbx, [rbx+30h]
0x14005c53a  test    r8, r8
0x14005c53d  jz      short loc_14005C57C
0x14005c53f  mov     rsi, [r8-10h]
0x14005c543  add     r8, 0FFFFFFFFFFFFFFF0h
0x14005c547  test    rsi, rsi
0x14005c54a  jz      loc_14005C672
0x14005c550  cmp     byte ptr [rsi+8], 0
0x14005c554  jz      loc_14005C656
0x14005c55a  cmp     byte ptr [rsi+9], 0
0x14005c55e  lea     rcx, [rsi+40h]; Lookaside
0x14005c562  mov     rdx, r8; Entry
0x14005c565  jz      loc_14005C637
0x14005c56b  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005c572  nop     dword ptr [rax+rax+00h]
0x14005c577  test    rdi, rdi
0x14005c57a  jz      short loc_14005C58D
0x14005c57c  xor     edx, edx; Tag
0x14005c57e  mov     rcx, rdi; P
0x14005c581  call    cs:__imp_ExFreePoolWithTag
0x14005c588  nop     dword ptr [rax+rax+00h]
0x14005c58d  test    rbx, rbx
0x14005c590  jnz     short loc_14005C530
0x14005c592  mov     rbx, [r14+10h]
0x14005c596  xor     r15d, r15d
0x14005c599  mov     [r14+18h], r15
0x14005c59d  mov     [r14+20h], r15
0x14005c5a1  mov     [r14], r15
0x14005c5a4  mov     [r14+8], r15
0x14005c5a8  test    rbx, rbx
0x14005c5ab  jz      short loc_14005C60E
0x14005c5ad  nop     dword ptr [rax]
0x14005c5b0  mov     rcx, [rbx]
0x14005c5b3  mov     rdi, rbx
0x14005c5b6  mov     rbx, [rbx+30h]
0x14005c5ba  test    rcx, rcx
0x14005c5bd  jz      short loc_14005C5F8
0x14005c5bf  mov     rsi, [rcx-10h]
0x14005c5c3  lea     r8, [rcx-10h]
0x14005c5c7  test    rsi, rsi
0x14005c5ca  jz      loc_14005C6A4
0x14005c5d0  cmp     [rsi+8], r15b
0x14005c5d4  jz      loc_14005C688
0x14005c5da  lea     rcx, [rsi+40h]; Lookaside
0x14005c5de  mov     rdx, r8; Entry
0x14005c5e1  cmp     [rsi+9], r15b
0x14005c5e5  jz      short loc_14005C648
0x14005c5e7  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005c5ee  nop     dword ptr [rax+rax+00h]
0x14005c5f3  test    rdi, rdi
0x14005c5f6  jz      short loc_14005C609
0x14005c5f8  xor     edx, edx; Tag
0x14005c5fa  mov     rcx, rdi; P
0x14005c5fd  call    cs:__imp_ExFreePoolWithTag
0x14005c604  nop     dword ptr [rax+rax+00h]
0x14005c609  test    rbx, rbx
0x14005c60c  jnz     short loc_14005C5B0
0x14005c60e  mov     eax, [r14+30h]
0x14005c612  mov     [r14+10h], r15
0x14005c616  neg     eax
0x14005c618  nop
0x14005c619  lock add [rbp+120h], eax
0x14005c620  nop
0x14005c621  mov     [r14+30h], r15d
0x14005c625  mov     [r14+28h], r15
0x14005c629  add     rsp, 28h
0x14005c62d  pop     r15
0x14005c62f  pop     r14
0x14005c631  pop     rdi
0x14005c632  pop     rsi
0x14005c633  pop     rbp
0x14005c634  pop     rbx
0x14005c635  retn
0x14005c637  call    cs:__imp_ExFreeToPagedLookasideList
0x14005c63e  nop     dword ptr [rax+rax+00h]
0x14005c643  jmp     loc_14005C577
0x14005c648  call    cs:__imp_ExFreeToPagedLookasideList
0x14005c64f  nop     dword ptr [rax+rax+00h]
0x14005c654  jmp     short loc_14005C5F3
0x14005c656  mov     rcx, [rsi+58h]
0x14005c65a  cmp     ecx, [rsi+50h]
0x14005c65d  jl      loc_1401FDD1A
0x14005c663  mov     rax, rcx
0x14005c666  shr     rax, 20h
0x14005c66a  cmp     eax, ecx
0x14005c66c  jge     loc_1401FDD1A
0x14005c672  xor     edx, edx; Tag
0x14005c674  mov     rcx, r8; P
0x14005c677  call    cs:__imp_ExFreePoolWithTag
0x14005c67e  nop     dword ptr [rax+rax+00h]
0x14005c683  jmp     loc_14005C577
0x14005c688  mov     rcx, [rsi+58h]
0x14005c68c  cmp     ecx, [rsi+50h]
0x14005c68f  jl      loc_1401FDD38
0x14005c695  mov     rax, rcx
0x14005c698  shr     rax, 20h
0x14005c69c  cmp     eax, ecx
0x14005c69e  jge     loc_1401FDD38
0x14005c6a4  xor     edx, edx; Tag
0x14005c6a6  mov     rcx, r8; P
0x14005c6a9  call    cs:__imp_ExFreePoolWithTag
0x14005c6b0  nop     dword ptr [rax+rax+00h]
0x14005c6b5  jmp     loc_14005C5F3
0x1401fdd1a  lea     rcx, [rsi+40h]; ListHead
0x1401fdd1e  mov     rdx, r8; ListEntry
0x1401fdd21  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401fdd28  nop     dword ptr [rax+rax+00h]
0x1401fdd2d  nop
0x1401fdd2e  lock inc dword ptr [rsi+58h]
0x1401fdd32  nop
0x1401fdd33  jmp     loc_14005C577
0x1401fdd38  lea     rcx, [rsi+40h]; ListHead
0x1401fdd3c  mov     rdx, r8; ListEntry
0x1401fdd3f  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401fdd46  nop     dword ptr [rax+rax+00h]
0x1401fdd4b  nop
0x1401fdd4c  lock inc dword ptr [rsi+58h]
0x1401fdd50  nop
0x1401fdd51  jmp     loc_14005C5F3
```
