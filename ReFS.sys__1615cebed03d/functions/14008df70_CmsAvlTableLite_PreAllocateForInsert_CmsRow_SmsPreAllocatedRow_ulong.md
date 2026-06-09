# CmsAvlTableLite::PreAllocateForInsert(_CmsRow *,_SmsPreAllocatedRow *,ulong)

- ea: `0x14008df70`
- end: `0x14008e21f`
- name: `?PreAllocateForInsert@CmsAvlTableLite@@SAJPEAU_CmsRow@@PEAU_SmsPreAllocatedRow@@K@Z`
- size: `687`
- prototype: `__int64 __fastcall(struct _CmsRow *, struct _SmsPreAllocatedRow *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14008df1c`

## callees

- `0x14008df70`
- `0x1400ceda0`
- `0x1401f4100`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008e1be`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008e1f4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008e1be`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008e1f4`
- `ntoskrnl!ExAllocatePool2` at `0x14008dfea`
- `ntoskrnl!ExAllocatePool2` at `0x14008e03e`
- `ntoskrnl!ExAllocatePool2` at `0x14008e0b1`
- `ntoskrnl!ExAllocatePool2` at `0x14008dfea`
- `ntoskrnl!ExAllocatePool2` at `0x14008e03e`
- `ntoskrnl!ExAllocatePool2` at `0x14008e0b1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008dfab`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008e00f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008dfab`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008e00f`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1402014b0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1402014c2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1402014b0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1402014c2`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008e1d8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008e20e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008e1d8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008e20e`

## string_xrefs

- `0x1402014d4`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsAvlTableLite::PreAllocateForInsert(
        struct _CmsRow *a1,
        struct _SmsPreAllocatedRow *a2,
        __int64 a3,
        __int64 a4)
{
  int v4; // ebp
  char v6; // r15
  unsigned int v8; // eax
  unsigned __int64 v9; // rbx
  unsigned int *v10; // rsi
  __int64 v11; // r9
  unsigned __int64 v12; // rdx
  __int64 Pool2; // rax
  __int64 v14; // rbx
  __int64 v15; // r9
  __int64 v16; // rsi
  unsigned __int64 v17; // rdx
  __int64 v18; // rax
  int v19; // ecx
  __int16 v20; // si
  int v22; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v23; // rcx
  void *v24; // rax
  struct _NPAGED_LOOKASIDE_LIST *v25; // rcx
  void *v26; // rax

  v4 = *((_DWORD *)a1 + 4);
  v6 = *(_BYTE *)a1;
  v8 = ((v4 + 7) & 0xFFFFFFF8) + 32;
  v9 = v8;
  if ( v8 <= CmsAvlTableLite::SizeOfAllocationsOnLookaside2 )
  {
    if ( v8 <= CmsAvlTableLite::SizeOfAllocationsOnLookaside1 )
    {
      v10 = (unsigned int *)(qword_140269458 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
      if ( v9 > *v10 )
      {
        v10 = 0;
        v12 = v9 + 16;
        goto LABEL_5;
      }
      if ( !*((_BYTE *)v10 + 8) )
      {
        if ( (int)*((_QWORD *)v10 + 11) > (int)HIDWORD(*((_QWORD *)v10 + 11)) )
        {
          v19 = _InterlockedDecrement((volatile signed __int32 *)v10 + 22);
          if ( v19 >= (int)v10[23] && v19 >= 0 )
          {
            v24 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v10 + 4);
            goto LABEL_26;
          }
          _InterlockedIncrement((volatile signed __int32 *)v10 + 22);
        }
LABEL_17:
        v12 = v10[1];
LABEL_5:
        Pool2 = ExAllocatePool2(66, v12, 1766871885, v11);
        v14 = Pool2;
        if ( (Pool2 & 0xF) == 0 )
        {
          if ( !Pool2 )
          {
LABEL_28:
            v20 = 0x2000;
            goto LABEL_29;
          }
LABEL_27:
          *(_QWORD *)v14 = v10;
          v14 += 16;
          goto LABEL_28;
        }
LABEL_44:
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      }
      v23 = (struct _NPAGED_LOOKASIDE_LIST *)(v10 + 16);
      if ( *((_BYTE *)v10 + 9) )
        v24 = ExAllocateFromNPagedLookasideList(v23);
      else
        v24 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v23);
LABEL_26:
      v14 = (__int64)v24;
      if ( v24 )
        goto LABEL_27;
      goto LABEL_17;
    }
    KeGetCurrentProcessorNumberEx(0);
    v16 = qword_140269460;
    if ( v9 > *(unsigned int *)qword_140269460 )
    {
      v16 = 0;
      v17 = v9 + 16;
      goto LABEL_10;
    }
    if ( !*(_BYTE *)(qword_140269460 + 8) )
    {
      if ( (int)*(_QWORD *)(qword_140269460 + 88) > (int)HIDWORD(*(_QWORD *)(qword_140269460 + 88)) )
      {
        v22 = _InterlockedDecrement((volatile signed __int32 *)(qword_140269460 + 88));
        if ( v22 >= *(_DWORD *)(v16 + 92) && v22 >= 0 )
        {
          v26 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v16 + 64));
          goto LABEL_31;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v16 + 88));
      }
LABEL_25:
      v17 = *(unsigned int *)(v16 + 4);
LABEL_10:
      v18 = ExAllocatePool2(66, v17, 1766871885, v15);
      v14 = v18;
      if ( (v18 & 0xF) != 0 )
        goto LABEL_44;
      if ( !v18 )
      {
LABEL_33:
        v20 = 0x4000;
LABEL_29:
        if ( !v14 )
          return 3221225626LL;
LABEL_20:
        *(_WORD *)(v14 + 28) = 0;
        memmove((void *)(v14 + 32), *((const void **)a1 + 3), *((unsigned int *)a1 + 4));
        *(_BYTE *)(v14 + 26) = 32;
        *(_WORD *)(v14 + 28) |= v20;
        *(_WORD *)(v14 + 30) = v4;
        *(_BYTE *)(v14 + 27) = v6;
        *((_QWORD *)a2 + 4) = v14;
        *(_DWORD *)a2 = *(unsigned __int8 *)(v14 + 27);
        *((_QWORD *)a2 + 1) = v14 + *(unsigned __int8 *)(v14 + 26);
        *((_WORD *)a2 + 2) = 0;
        *((_DWORD *)a2 + 4) = *(unsigned __int16 *)(v14 + 30);
        *((_QWORD *)a2 + 3) = v14 + *(unsigned __int8 *)(v14 + 26);
        return 0;
      }
LABEL_32:
      *(_QWORD *)v14 = v16;
      v14 += 16;
      goto LABEL_33;
    }
    v25 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_140269460 + 64);
    if ( *(_BYTE *)(qword_140269460 + 9) )
      v26 = ExAllocateFromNPagedLookasideList(v25);
    else
      v26 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v25);
LABEL_31:
    v14 = (__int64)v26;
    if ( v26 )
      goto LABEL_32;
    goto LABEL_25;
  }
  v14 = ExAllocatePool2(66, ((v4 + 7) & 0xFFFFFFF8) + 32, 1766871885, a4);
  if ( v14 )
  {
    v20 = 0x8000;
    goto LABEL_20;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14008df70  push    rbx
0x14008df72  push    rbp
0x14008df73  push    rsi
0x14008df74  push    rdi
0x14008df75  push    r14
0x14008df77  push    r15
0x14008df79  sub     rsp, 28h
0x14008df7d  mov     ebp, [rcx+10h]
0x14008df80  mov     rdi, rdx
0x14008df83  movzx   r15d, byte ptr [rcx]
0x14008df87  mov     r14, rcx
0x14008df8a  lea     eax, [rbp+7]
0x14008df8d  and     eax, 0FFFFFFF8h
0x14008df90  add     eax, 20h ; ' '
0x14008df93  cmp     eax, cs:?SizeOfAllocationsOnLookaside2@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside2
0x14008df99  mov     ebx, eax
0x14008df9b  ja      loc_14008E0A3
0x14008dfa1  xor     ecx, ecx; ProcNumber
0x14008dfa3  cmp     eax, cs:?SizeOfAllocationsOnLookaside1@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside1
0x14008dfa9  ja      short loc_14008E00F
0x14008dfab  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008dfb2  nop     dword ptr [rax+rax+00h]
0x14008dfb7  xor     edx, edx
0x14008dfb9  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14008dfbf  lea     rsi, [rdx+rdx*2]
0x14008dfc3  shl     rsi, 6
0x14008dfc7  add     rsi, cs:qword_140269458
0x14008dfce  mov     eax, [rsi]
0x14008dfd0  cmp     rbx, rax
0x14008dfd3  jbe     loc_14008E063
0x14008dfd9  xor     esi, esi
0x14008dfdb  lea     rdx, [rbx+10h]
0x14008dfdf  mov     ecx, 42h ; 'B'
0x14008dfe4  mov     r8d, 6950534Dh
0x14008dfea  call    cs:__imp_ExAllocatePool2
0x14008dff1  nop     dword ptr [rax+rax+00h]
0x14008dff6  mov     rbx, rax
0x14008dff9  test    al, 0Fh
0x14008dffb  jnz     loc_1402014D4
0x14008e001  test    rax, rax
0x14008e004  jz      loc_14008E185
0x14008e00a  jmp     loc_14008E17E
0x14008e00f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008e016  nop     dword ptr [rax+rax+00h]
0x14008e01b  mov     rsi, cs:qword_140269460
0x14008e022  mov     eax, [rsi]
0x14008e024  cmp     rbx, rax
0x14008e027  jbe     loc_14008E132
0x14008e02d  xor     esi, esi
0x14008e02f  lea     rdx, [rbx+10h]
0x14008e033  mov     ecx, 42h ; 'B'
0x14008e038  mov     r8d, 6950534Dh
0x14008e03e  call    cs:__imp_ExAllocatePool2
0x14008e045  nop     dword ptr [rax+rax+00h]
0x14008e04a  mov     rbx, rax
0x14008e04d  test    al, 0Fh
0x14008e04f  jnz     loc_1402014D4
0x14008e055  test    rax, rax
0x14008e058  jz      loc_14008E1A9
0x14008e05e  jmp     loc_14008E1A2
0x14008e063  cmp     byte ptr [rsi+8], 0
0x14008e067  jnz     loc_14008E1B0
0x14008e06d  mov     rcx, [rsi+58h]
0x14008e071  mov     rax, rcx
0x14008e074  shr     rax, 20h
0x14008e078  cmp     ecx, eax
0x14008e07a  jle     short loc_14008E09B
0x14008e07c  nop
0x14008e07d  mov     ecx, 0FFFFFFFFh
0x14008e082  lock xadd [rsi+58h], ecx
0x14008e087  nop
0x14008e088  dec     ecx
0x14008e08a  mov     eax, [rsi+5Ch]
0x14008e08d  cmp     ecx, eax
0x14008e08f  jge     loc_14008E1CC
0x14008e095  nop
0x14008e096  lock inc dword ptr [rsi+58h]
0x14008e09a  nop
0x14008e09b  mov     edx, [rsi+4]
0x14008e09e  jmp     loc_14008DFDF
0x14008e0a3  mov     r8d, 6950534Dh
0x14008e0a9  mov     rdx, rbx
0x14008e0ac  mov     ecx, 42h ; 'B'
0x14008e0b1  call    cs:__imp_ExAllocatePool2
0x14008e0b8  nop     dword ptr [rax+rax+00h]
0x14008e0bd  mov     rbx, rax
0x14008e0c0  test    rax, rax
0x14008e0c3  jz      loc_14008E193
0x14008e0c9  mov     esi, 8000h
0x14008e0ce  xor     eax, eax
0x14008e0d0  lea     rcx, [rbx+20h]; void *
0x14008e0d4  mov     [rbx+1Ch], ax
0x14008e0d8  mov     r8d, [r14+10h]; Size
0x14008e0dc  mov     rdx, [r14+18h]; Src
0x14008e0e0  call    memmove
0x14008e0e5  mov     byte ptr [rbx+1Ah], 20h ; ' '
0x14008e0e9  or      [rbx+1Ch], si
0x14008e0ed  mov     [rbx+1Eh], bp
0x14008e0f1  mov     [rbx+1Bh], r15b
0x14008e0f5  mov     [rdi+20h], rbx
0x14008e0f9  movzx   eax, byte ptr [rbx+1Bh]
0x14008e0fd  mov     [rdi], eax
0x14008e0ff  movzx   eax, byte ptr [rbx+1Ah]
0x14008e103  add     rax, rbx
0x14008e106  mov     [rdi+8], rax
0x14008e10a  xor     eax, eax
0x14008e10c  mov     [rdi+4], ax
0x14008e110  movzx   eax, word ptr [rbx+1Eh]
0x14008e114  mov     [rdi+10h], eax
0x14008e117  movzx   eax, byte ptr [rbx+1Ah]
0x14008e11b  add     rax, rbx
0x14008e11e  mov     [rdi+18h], rax
0x14008e122  xor     eax, eax
0x14008e124  add     rsp, 28h
0x14008e128  pop     r15
0x14008e12a  pop     r14
0x14008e12c  pop     rdi
0x14008e12d  pop     rsi
0x14008e12e  pop     rbp
0x14008e12f  pop     rbx
0x14008e130  retn
0x14008e132  cmp     byte ptr [rsi+8], 0
0x14008e136  jnz     loc_14008E1E6
0x14008e13c  mov     rcx, [rsi+58h]
0x14008e140  mov     rax, rcx
0x14008e143  shr     rax, 20h
0x14008e147  cmp     ecx, eax
0x14008e149  jle     short loc_14008E16A
0x14008e14b  nop
0x14008e14c  mov     ecx, 0FFFFFFFFh
0x14008e151  lock xadd [rsi+58h], ecx
0x14008e156  nop
0x14008e157  dec     ecx
0x14008e159  mov     eax, [rsi+5Ch]
0x14008e15c  cmp     ecx, eax
0x14008e15e  jge     loc_14008E202
0x14008e164  nop
0x14008e165  lock inc dword ptr [rsi+58h]
0x14008e169  nop
0x14008e16a  mov     edx, [rsi+4]
0x14008e16d  jmp     loc_14008E033
0x14008e172  mov     rbx, rax
0x14008e175  test    rax, rax
0x14008e178  jz      loc_14008E09B
0x14008e17e  mov     [rbx], rsi
0x14008e181  add     rbx, 10h
0x14008e185  mov     esi, 2000h
0x14008e18a  test    rbx, rbx
0x14008e18d  jnz     loc_14008E0CE
0x14008e193  mov     eax, 0C000009Ah
0x14008e198  jmp     short loc_14008E124
0x14008e19a  mov     rbx, rax
0x14008e19d  test    rax, rax
0x14008e1a0  jz      short loc_14008E16A
0x14008e1a2  mov     [rbx], rsi
0x14008e1a5  add     rbx, 10h
0x14008e1a9  mov     esi, 4000h
0x14008e1ae  jmp     short loc_14008E18A
0x14008e1b0  cmp     byte ptr [rsi+9], 0
0x14008e1b4  lea     rcx, [rsi+40h]; Lookaside
0x14008e1b8  jz      loc_1402014B0
0x14008e1be  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008e1c5  nop     dword ptr [rax+rax+00h]
0x14008e1ca  jmp     short loc_14008E172
0x14008e1cc  test    ecx, ecx
0x14008e1ce  js      loc_14008E095
0x14008e1d4  lea     rcx, [rsi+40h]; ListHead
0x14008e1d8  call    cs:__imp_ExpInterlockedPopEntrySList
0x14008e1df  nop     dword ptr [rax+rax+00h]
0x14008e1e4  jmp     short loc_14008E172
0x14008e1e6  cmp     byte ptr [rsi+9], 0
0x14008e1ea  lea     rcx, [rsi+40h]; Lookaside
0x14008e1ee  jz      loc_1402014C2
0x14008e1f4  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008e1fb  nop     dword ptr [rax+rax+00h]
0x14008e200  jmp     short loc_14008E19A
0x14008e202  test    ecx, ecx
0x14008e204  js      loc_14008E164
0x14008e20a  lea     rcx, [rsi+40h]; ListHead
0x14008e20e  call    cs:__imp_ExpInterlockedPopEntrySList
0x14008e215  nop     dword ptr [rax+rax+00h]
0x14008e21a  jmp     loc_14008E19A
0x1402014b0  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1402014b7  nop     dword ptr [rax+rax+00h]
0x1402014bc  nop
0x1402014bd  jmp     loc_14008E172
0x1402014c2  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1402014c9  nop     dword ptr [rax+rax+00h]
0x1402014ce  nop
0x1402014cf  jmp     loc_14008E19A
0x1402014d4  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1402014db  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
```
