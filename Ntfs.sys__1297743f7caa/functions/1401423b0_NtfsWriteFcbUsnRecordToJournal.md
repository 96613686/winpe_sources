# NtfsWriteFcbUsnRecordToJournal

- ea: `0x1401423b0`
- end: `0x140142c55`
- name: `NtfsWriteFcbUsnRecordToJournal`
- size: `2213`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140141400`
- `0x140190bd0`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000d510`
- `0x1400410a8`
- `0x140059740`
- `0x140125100`
- `0x1401423b0`
- `0x140142c60`
- `0x140143730`
- `0x140162110`
- `0x1401e06b0`
- `0x14026e630`
- `0x14029b5a8`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140142afa`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402a7550`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140142afa`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402a7550`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401424fd`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401424fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140142adf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a7539`
- `ntoskrnl!ExFreePoolWithTag` at `0x140142adf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a7539`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401427cc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401427cc`
- `ntoskrnl!CcUnpinData` at `0x140142bf3`
- `ntoskrnl!CcUnpinData` at `0x140142c14`
- `ntoskrnl!CcUnpinData` at `0x140142c35`
- `ntoskrnl!CcUnpinData` at `0x140142bf3`
- `ntoskrnl!CcUnpinData` at `0x140142c14`
- `ntoskrnl!CcUnpinData` at `0x140142c35`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401424b4`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401424b4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140142940`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402a7507`
- `ntoskrnl!ExReleaseFastMutex` at `0x140142940`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402a7507`

## pseudocode

```c
void __fastcall NtfsWriteFcbUsnRecordToJournal(__int64 a1, __int64 a2, int *Src, __int64 a4, __int64 a5, __int64 a6)
{
  bool v10; // si
  __int64 v11; // rcx
  unsigned int v12; // r14d
  __int64 v13; // rdx
  unsigned int *v14; // r9
  int v15; // eax
  unsigned int *v16; // rax
  _DWORD *v17; // rax
  int v18; // eax
  unsigned int v19; // ecx
  int v20; // eax
  PVOID PoolWithTag; // rax
  unsigned int *v22; // r8
  __int64 v23; // r8
  unsigned int v24; // eax
  unsigned __int64 v25; // rcx
  unsigned int v26; // eax
  void *v27; // rcx
  int v28; // eax
  int v29; // r9d
  unsigned int *v30; // r8
  void *Srca; // [rsp+20h] [rbp-128h]
  int v32; // [rsp+30h] [rbp-118h]
  unsigned int *Entry; // [rsp+58h] [rbp-F0h]
  __int64 v34; // [rsp+68h] [rbp-E0h]
  __int64 v35; // [rsp+70h] [rbp-D8h]
  _DWORD *v36; // [rsp+80h] [rbp-C8h]
  unsigned int *v37; // [rsp+80h] [rbp-C8h]
  PVOID v38[19]; // [rsp+B0h] [rbp-98h] BYREF
  __int64 v39; // [rsp+158h] [rbp+10h] BYREF
  int *v40; // [rsp+160h] [rbp+18h]

  v40 = Src;
  v39 = a2;
  memset(v38, 0, 0x58u);
  if ( (*(_DWORD *)(*(_QWORD *)(a2 + 96) + 4LL) & 0x80000) == 0 )
    return;
  v10 = Src[10] < 0;
  if ( !*(_QWORD *)(a4 + 496) )
    NtfsSnapshotScb(a1, a4);
  v11 = *(_QWORD *)(a4 + 32);
  v34 = v11;
  v12 = 4096 - (v11 & 0xFFF);
  if ( a5 && *(int *)(a5 + 248) < 0 )
  {
    Entry = 0;
    v35 = *(_QWORD *)(a6 + 16);
    if ( !v35 )
      v35 = *(_QWORD *)(a5 + 48);
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 104) + 8LL));
    v13 = v35;
    if ( !v35
      || (*(_DWORD *)(*(_QWORD *)(a2 + 96) + 8008LL) & 1) == 0
      || (v15 = *(_DWORD *)(v35 + 144), (v15 & 5) == 0)
      || (v15 & 2) != 0 )
    {
      v14 = 0;
      goto LABEL_46;
    }
    v16 = (unsigned int *)ExAllocateFromLookasideListEx(&NtfsRangeTrackLocalStructLookasideList);
    v14 = v16;
    Entry = v16;
    if ( !v16 )
    {
LABEL_32:
      v13 = v35;
LABEL_46:
      if ( v14 )
      {
        *(_QWORD *)(a6 + 16) = v13;
        *(_DWORD *)(v13 + 144) |= 0x10u;
        *(_DWORD *)(v13 + 144) |= 0x20u;
        if ( v13 == *(_QWORD *)(a5 + 48) )
          *(_QWORD *)(a5 + 48) = 0;
      }
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 104) + 8LL));
      v27 = Entry;
      if ( Entry )
      {
        v30 = (unsigned int *)*((_QWORD *)Entry + 18);
        if ( v30 && v30 != Entry + 4 )
        {
          ExFreePoolWithTag(*((PVOID *)Entry + 18), 0);
          v27 = Entry;
        }
        ExFreeToLookasideListEx(&NtfsRangeTrackLocalStructLookasideList, v27);
        v11 = v34;
      }
      else
      {
        v11 = v34;
      }
      goto LABEL_49;
    }
    *((_QWORD *)v16 + 18) = 0;
    *((_QWORD *)v16 + 17) = v35;
    v17 = v16 + 2;
    v36 = v17;
    if ( *(_QWORD *)(v35 + 136) )
    {
      v22 = v14 + 18;
      v14[18] = 0;
      *((_WORD *)v14 + 38) = 1;
      *v14 = 80;
      *v17 = 0;
      *((_QWORD *)v14 + 10) = 0;
      *((_QWORD *)v14 + 11) = -*(_QWORD *)(*(_QWORD *)(a2 + 96) + 8016LL)
                            & (*(_QWORD *)(*(_QWORD *)(a2 + 96) + 8016LL) + *(_QWORD *)(v35 + 136) - 1LL);
      PoolWithTag = v14 + 4;
      *((_QWORD *)v14 + 18) = v14 + 4;
    }
    else
    {
      *((_OWORD *)v14 + 6) = 0;
      *((_OWORD *)v14 + 7) = 0;
      *((_QWORD *)v14 + 16) = 0;
      *((_QWORD *)v14 + 13) = 1;
      v32 = (int)v14;
      v18 = FsLibRangeTrackBufferExtents(*((_QWORD *)v14 + 17), v14 + 4, 64);
      *v36 = v18;
      if ( (int)(v18 + 0x80000000) >= 0 && v18 != -1073741789 )
      {
        v14 = Entry;
        goto LABEL_32;
      }
      v14 = Entry;
      v19 = *Entry;
      if ( !*Entry && !v18 )
        goto LABEL_32;
      v37 = Entry + 18;
      if ( Entry[18] == 1 )
      {
        v32 = (int)Entry;
        v20 = FsLibRangeTrackBufferExtents(*((_QWORD *)Entry + 17), Entry + 4, 80);
        v14 = Entry;
        Entry[2] = v20;
        if ( v20 < 0 || !*((_QWORD *)Entry + 10) && *((_QWORD *)Entry + 11) == -1 )
          goto LABEL_32;
        PoolWithTag = Entry + 4;
        *((_QWORD *)Entry + 18) = Entry + 4;
        v22 = Entry + 18;
LABEL_23:
        if ( v12 < 0x50 )
        {
          *(_QWORD *)(a1 + 16) |= 0x80000uLL;
          NtOfsPutData(a1, a4, -1, v12, 0);
          *(_QWORD *)(a1 + 16) &= ~0x80000uLL;
          v34 += v12;
          v12 = 0;
          v14 = Entry;
          PoolWithTag = (PVOID)*((_QWORD *)Entry + 18);
          v22 = v37;
        }
        if ( *v22 )
        {
          v23 = v14[1];
          if ( v12 && (unsigned int)v23 >= v12 )
            v23 = v12;
          v32 = (int)v14;
          v24 = FsLibRangeTrackBufferExtents(*((_QWORD *)v14 + 17), PoolWithTag, v23);
          v14 = Entry;
          Entry[2] = v24;
        }
        *(_WORD *)(*((_QWORD *)v14 + 18) + 4LL) = 4;
        *(_WORD *)(*((_QWORD *)v14 + 18) + 6LL) = 0;
        *(_DWORD *)(*((_QWORD *)v14 + 18) + 48LL) = Src[10];
        *(_DWORD *)(*((_QWORD *)v14 + 18) + 52LL) = Src[11];
        *(_QWORD *)(*((_QWORD *)v14 + 18) + 16LL) = 0;
        *(_QWORD *)(*((_QWORD *)v14 + 18) + 8LL) = *((_QWORD *)Src + 1);
        *(_QWORD *)(*((_QWORD *)v14 + 18) + 32LL) = 0;
        *(_QWORD *)(*((_QWORD *)v14 + 18) + 24LL) = *((_QWORD *)Src + 2);
        while ( (v14[2] & 0x80000000) == 0 )
        {
          **((_DWORD **)v14 + 18) = *v14;
          *(_QWORD *)(*((_QWORD *)v14 + 18) + 40LL) = v34;
          *(_WORD *)(*((_QWORD *)v14 + 18) + 62LL) = 16;
          *(_QWORD *)(a1 + 16) |= 0x80000uLL;
          NtOfsPutData(a1, a4, -1, *v14, *((void **)v14 + 18));
          v25 = *(_QWORD *)(a1 + 16) & 0xFFFFFFFFFFF7FFFFuLL;
          *(_QWORD *)(a1 + 16) = v25;
          v14 = Entry;
          v34 += *Entry;
          v12 = 4096 - (v34 & 0xFFF);
          if ( !Entry[2] )
            break;
          if ( v12 < 0x50 )
          {
            *(_QWORD *)(a1 + 16) = v25 | 0x80000;
            NtOfsPutData(a1, a4, -1, v12, 0);
            *(_QWORD *)(a1 + 16) &= ~0x80000uLL;
            v34 += v12;
            v14 = Entry;
          }
          v32 = (int)v14;
          v26 = FsLibRangeTrackBufferExtents(*((_QWORD *)v14 + 17), *((_QWORD *)v14 + 18), v14[1]);
          v14 = Entry;
          Entry[2] = v26;
        }
        goto LABEL_32;
      }
      if ( v19 > 0x1000 )
        v19 = 4096;
      Entry[1] = v19;
      PoolWithTag = ExAllocatePoolWithTag(PoolType, v19, 0x5546744Eu);
      v14 = Entry;
      *((_QWORD *)Entry + 18) = PoolWithTag;
      if ( !PoolWithTag )
        goto LABEL_32;
      v22 = Entry + 18;
    }
    v37 = v22;
    goto LABEL_23;
  }
LABEL_49:
  if ( v12 < *Src )
  {
    *(_QWORD *)(a1 + 16) |= 0x80000uLL;
    NtOfsPutData(a1, a4, -1, v12, 0);
    *(_QWORD *)(a1 + 16) &= ~0x80000uLL;
    v11 = v12 + v34;
    v34 = v11;
  }
  *((_QWORD *)Src + 3) = v11;
  *((_QWORD *)Src + 4) = MEMORY[0xFFFFF78000000014];
  *(_QWORD *)(a1 + 16) |= 0x80000uLL;
  NtOfsPutData(a1, a4, -1, *Src, Src);
  *(_QWORD *)(a1 + 16) &= ~0x80000uLL;
  if ( (Src[10] & 0x200) == 0 )
  {
    v28 = *(_DWORD *)(a2 + 4);
    if ( (v28 & 1) == 0 )
    {
      if ( (v28 & 0x800) == 0 )
        NtfsGrowStandardInformation(a1, a2);
      if ( Src[10] < 0 )
      {
        v39 = v34;
        LOBYTE(v32) = 0;
        if ( !(unsigned __int8)NtfsLookupInFileRecord(a1, a2, a2 + 8, 16, 0, 0, v32, 0, 0, v38) )
        {
          NtfsAttachCorruption_BadOrOrphanFRS(a1, 2, 2824709, v29, a2 + 8, a2, 0);
          NtfsAttachRepairInfoPriv(a1, 256, 0, 0xA3002B1A05LL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 2824709);
          NtfsRaiseStatusInternal(a1, -1073741566, a2 + 8, a2, 2824709);
          __debugbreak();
        }
        LODWORD(Srca) = 8;
        NtfsChangeAttributeValue(a1, a2, 64, (int)&v39, (SIZE_T)Srca, 0, 0, 0, 0, v38);
      }
    }
  }
  if ( v10 )
  {
    if ( v38[2] )
    {
      CcUnpinData(v38[2]);
      v38[2] = 0;
    }
    if ( v38[5] )
    {
      CcUnpinData(v38[5]);
      v38[5] = 0;
    }
    if ( v38[9] )
      CcUnpinData(v38[9]);
  }
}

```

## disassembly

```asm
0x1401423b0  mov     [rsp+arg_10], r8
0x1401423b5  mov     [rsp+arg_8], rdx
0x1401423ba  mov     [rsp+arg_0], rcx
0x1401423bf  push    rbx
0x1401423c0  push    rsi
0x1401423c1  push    rdi
0x1401423c2  push    r12
0x1401423c4  push    r13
0x1401423c6  push    r14
0x1401423c8  push    r15
0x1401423ca  sub     rsp, 110h
0x1401423d1  mov     r12, r9
0x1401423d4  mov     rbx, r8
0x1401423d7  mov     r13, rdx
0x1401423da  mov     rdi, rcx
0x1401423dd  xor     edx, edx; Val
0x1401423df  mov     r8d, 58h ; 'X'; Size
0x1401423e5  lea     rcx, [rsp+148h+var_98]; void *
0x1401423ed  call    memset
0x1401423f2  mov     rax, [r13+60h]
0x1401423f6  test    dword ptr [rax+4], 80000h
0x1401423fd  jz      loc_140142C41
0x140142403  mov     [rsp+148h+var_B0], 0FFFFFFFFFFFFFFFFh
0x14014240f  xor     al, al
0x140142411  mov     [rsp+148h+var_F8], al
0x140142415  movzx   esi, al
0x140142418  mov     eax, 1
0x14014241d  cmp     dword ptr [rbx+28h], 0
0x140142421  cmovl   esi, eax
0x140142424  mov     [rsp+148h+var_E8], sil
0x140142429  cmp     qword ptr [r12+1F0h], 0
0x140142432  jz      loc_140142B84
0x140142438  mov     rcx, [r12+20h]
0x14014243d  mov     [rsp+148h+var_E0], rcx
0x140142442  mov     [rsp+148h+var_C0], rcx
0x14014244a  mov     eax, ecx
0x14014244c  and     eax, 0FFFh
0x140142451  mov     r14d, 1000h
0x140142457  sub     r14d, eax
0x14014245a  mov     [rsp+148h+var_D0], r14d
0x14014245f  mov     rax, [rsp+148h+arg_20]
0x140142467  test    rax, rax
0x14014246a  jz      loc_140142961
0x140142470  cmp     dword ptr [rax+0F8h], 0
0x140142477  jge     loc_140142961
0x14014247d  xor     r15d, r15d
0x140142480  mov     [rsp+148h+Entry], r15
0x140142485  mov     rcx, [rsp+148h+arg_28]
0x14014248d  mov     rcx, [rcx+10h]
0x140142491  mov     [rsp+148h+var_D8], rcx
0x140142496  test    rcx, rcx
0x140142499  jnz     short loc_1401424A4
0x14014249b  mov     rcx, [rax+30h]
0x14014249f  mov     [rsp+148h+var_D8], rcx
0x1401424a4  mov     [rsp+148h+var_A8], rcx
0x1401424ac  mov     rcx, [r13+68h]
0x1401424b0  add     rcx, 8; FastMutex
0x1401424b4  call    cs:__imp_ExAcquireFastMutex
0x1401424bb  nop     dword ptr [rax+rax+00h]
0x1401424c0  mov     [rsp+148h+var_F8], 1
0x1401424c5  mov     rdx, [rsp+148h+var_D8]
0x1401424ca  test    rdx, rdx
0x1401424cd  jz      short loc_1401424DE
0x1401424cf  mov     rax, [r13+60h]
0x1401424d3  mov     ecx, [rax+1F48h]
0x1401424d9  test    cl, 1
0x1401424dc  jnz     short loc_1401424E8
0x1401424de  mov     r9, [rsp+148h+Entry]
0x1401424e3  jmp     loc_14014292F
0x1401424e8  mov     eax, [rdx+90h]
0x1401424ee  test    al, 5
0x1401424f0  jz      short loc_1401424DE
0x1401424f2  test    al, 2
0x1401424f4  jnz     short loc_1401424DE
0x1401424f6  lea     rcx, NtfsRangeTrackLocalStructLookasideList; Lookaside
0x1401424fd  call    cs:__imp_ExAllocateFromLookasideListEx
0x140142504  nop     dword ptr [rax+rax+00h]
0x140142509  mov     r9, rax
0x14014250c  mov     [rsp+148h+Entry], rax
0x140142511  test    rax, rax
0x140142514  jz      loc_140142746
0x14014251a  mov     [rax+90h], r15
0x140142521  mov     rcx, [rsp+148h+var_D8]
0x140142526  mov     [rax+88h], rcx
0x14014252d  add     rax, 8
0x140142531  mov     [rsp+148h+var_C8], rax
0x140142539  mov     edx, 1
0x14014253e  cmp     qword ptr [rcx+88h], 0
0x140142546  jnz     loc_140142750
0x14014254c  lea     rcx, [r9+60h]
0x140142550  mov     [rsp+148h+var_B8], rcx
0x140142558  xorps   xmm0, xmm0
0x14014255b  xor     eax, eax
0x14014255d  movups  xmmword ptr [rcx], xmm0
0x140142560  movups  xmmword ptr [rcx+10h], xmm0
0x140142564  mov     [rcx+20h], rax
0x140142568  mov     [r9+68h], rdx
0x14014256c  lea     rdx, [r9+10h]
0x140142570  mov     qword ptr [rsp+148h+var_118], r9
0x140142575  mov     qword ptr [rsp+148h+var_120], rcx
0x14014257a  mov     r8d, 40h ; '@'
0x140142580  mov     rcx, [r9+88h]
0x140142587  call    FsLibRangeTrackBufferExtents
0x14014258c  mov     rcx, [rsp+148h+var_C8]
0x140142594  mov     [rcx], eax
0x140142596  mov     edx, 80000000h
0x14014259b  lea     ecx, [rax+rdx]
0x14014259e  test    edx, ecx
0x1401425a0  jz      loc_14014291A
0x1401425a6  mov     r9, [rsp+148h+Entry]
0x1401425ab  mov     ecx, [r9]
0x1401425ae  test    ecx, ecx
0x1401425b0  jnz     short loc_1401425BA
0x1401425b2  test    eax, eax
0x1401425b4  jz      loc_140142746
0x1401425ba  lea     rax, [r9+48h]
0x1401425be  mov     [rsp+148h+var_C8], rax
0x1401425c6  cmp     dword ptr [rax], 1
0x1401425c9  jnz     loc_1401427B0
0x1401425cf  mov     qword ptr [rsp+148h+var_118], r9
0x1401425d4  lea     rcx, [r9+60h]
0x1401425d8  mov     qword ptr [rsp+148h+var_120], rcx
0x1401425dd  mov     r8d, 50h ; 'P'
0x1401425e3  lea     rdx, [r9+10h]
0x1401425e7  mov     rcx, [r9+88h]
0x1401425ee  call    FsLibRangeTrackBufferExtents
0x1401425f3  mov     r9, [rsp+148h+Entry]
0x1401425f8  mov     [r9+8], eax
0x1401425fc  test    eax, eax
0x1401425fe  js      loc_140142746
0x140142604  cmp     qword ptr [r9+50h], 0
0x140142609  jnz     short loc_140142616
0x14014260b  cmp     qword ptr [r9+58h], 0FFFFFFFFFFFFFFFFh
0x140142610  jz      loc_140142746
0x140142616  lea     rax, [r9+10h]
0x14014261a  mov     [r9+90h], rax
0x140142621  lea     r8, [r9+48h]
0x140142625  cmp     r14d, 50h ; 'P'
0x140142629  jnb     short loc_14014268A
0x14014262b  or      qword ptr [rdi+10h], 80000h
0x140142633  mov     [rsp+148h+Src], r15; Src
0x140142638  mov     r9d, r14d; int
0x14014263b  mov     r8, 0FFFFFFFFFFFFFFFFh; int
0x140142642  mov     rdx, r12; int
0x140142645  mov     rcx, rdi; int
0x140142648  call    NtOfsPutData
0x14014264d  nop
0x14014264e  and     qword ptr [rdi+10h], 0FFFFFFFFFFF7FFFFh
0x140142656  mov     eax, r14d
0x140142659  mov     rcx, [rsp+148h+var_E0]
0x14014265e  add     rcx, rax
0x140142661  mov     [rsp+148h+var_E0], rcx
0x140142666  mov     [rsp+148h+var_C0], rcx
0x14014266e  mov     r14d, r15d
0x140142671  mov     [rsp+148h+var_D0], r15d
0x140142676  mov     r9, [rsp+148h+Entry]
0x14014267b  mov     rax, [r9+90h]
0x140142682  mov     r8, [rsp+148h+var_C8]
0x14014268a  cmp     dword ptr [r8], 0
0x14014268e  jz      short loc_1401426CB
0x140142690  mov     r8d, [r9+4]
0x140142694  test    r14d, r14d
0x140142697  jz      loc_14014290D
0x14014269d  cmp     r8d, r14d
0x1401426a0  jb      short loc_1401426A5
0x1401426a2  mov     r8d, r14d
0x1401426a5  lea     rcx, [r9+60h]
0x1401426a9  mov     qword ptr [rsp+148h+var_118], r9
0x1401426ae  mov     qword ptr [rsp+148h+var_120], rcx
0x1401426b3  mov     rdx, rax
0x1401426b6  mov     rcx, [r9+88h]
0x1401426bd  call    FsLibRangeTrackBufferExtents
0x1401426c2  mov     r9, [rsp+148h+Entry]
0x1401426c7  mov     [r9+8], eax
0x1401426cb  mov     rax, [r9+90h]
0x1401426d2  mov     ecx, 4
0x1401426d7  mov     [rax+4], cx
0x1401426db  mov     rax, [r9+90h]
0x1401426e2  mov     [rax+6], r15w
0x1401426e7  mov     rcx, [r9+90h]
0x1401426ee  mov     eax, [rbx+28h]
0x1401426f1  mov     [rcx+30h], eax
0x1401426f4  mov     rcx, [r9+90h]
0x1401426fb  mov     eax, [rbx+2Ch]
0x1401426fe  mov     [rcx+34h], eax
0x140142701  mov     rax, [r9+90h]
0x140142708  mov     [rax+10h], r15
0x14014270c  mov     rcx, [r9+90h]
0x140142713  mov     rax, [rbx+8]
0x140142717  mov     [rcx+8], rax
0x14014271b  mov     rax, [r9+90h]
0x140142722  mov     [rax+20h], r15
0x140142726  mov     rcx, [r9+90h]
0x14014272d  mov     rax, [rbx+10h]
0x140142731  mov     [rcx+18h], rax
0x140142735  mov     r8d, 10h
0x14014273b  cmp     dword ptr [r9+8], 0
0x140142740  jge     loc_1401427F3
0x140142746  mov     rdx, [rsp+148h+var_D8]
0x14014274b  jmp     loc_14014292F
0x140142750  lea     r8, [r9+48h]
0x140142754  mov     [r8], r15d
0x140142757  mov     [r9+4Ch], dx
0x14014275c  mov     dword ptr [r9], 50h ; 'P'
0x140142763  mov     [rax], r15d
0x140142766  mov     [r9+50h], r15
0x14014276a  mov     rax, [r13+60h]
0x14014276e  mov     rdx, [rax+1F50h]
0x140142775  mov     rcx, [rcx+88h]
0x14014277c  dec     rcx
0x14014277f  add     rcx, rdx
0x140142782  neg     rdx
0x140142785  and     rcx, rdx
0x140142788  mov     [r9+58h], rcx
0x14014278c  lea     rax, [r9+10h]
0x140142790  mov     [r9+90h], rax
0x140142797  lea     rcx, [r9+60h]
0x14014279b  mov     [rsp+148h+var_C8], r8
0x1401427a3  mov     [rsp+148h+var_B8], rcx
0x1401427ab  jmp     loc_140142625
0x1401427b0  mov     eax, 1000h
0x1401427b5  cmp     ecx, eax
0x1401427b7  cmova   ecx, eax
0x1401427ba  mov     edx, ecx; NumberOfBytes
0x1401427bc  mov     [r9+4], edx
0x1401427c0  mov     ecx, cs:PoolType; PoolType
0x1401427c6  mov     r8d, 5546744Eh; Tag
0x1401427cc  call    cs:__imp_ExAllocatePoolWithTag
0x1401427d3  nop     dword ptr [rax+rax+00h]
0x1401427d8  mov     r9, [rsp+148h+Entry]
0x1401427dd  mov     [r9+90h], rax
0x1401427e4  test    rax, rax
0x1401427e7  jz      loc_140142746
0x1401427ed  lea     r8, [r9+48h]
0x1401427f1  jmp     short loc_140142797
0x1401427f3  mov     rcx, [r9+90h]
0x1401427fa  mov     eax, [r9]
0x1401427fd  mov     [rcx], eax
0x1401427ff  mov     rax, [r9+90h]
0x140142806  mov     r14, [rsp+148h+var_E0]
0x14014280b  mov     [rax+28h], r14
0x14014280f  mov     rax, [r9+90h]
0x140142816  mov     [rax+3Eh], r8w
0x14014281b  or      qword ptr [rdi+10h], 80000h
0x140142823  mov     rax, [r9+90h]
0x14014282a  mov     [rsp+148h+Src], rax; Src
0x14014282f  mov     r9d, [r9]; int
0x140142832  mov     r8, 0FFFFFFFFFFFFFFFFh; int
0x140142839  mov     rdx, r12; int
0x14014283c  mov     rcx, rdi; int
0x14014283f  call    NtOfsPutData
0x140142844  nop
0x140142845  mov     rcx, [rdi+10h]
0x140142849  btr     rcx, 13h
0x14014284e  mov     [rdi+10h], rcx
0x140142852  mov     r9, [rsp+148h+Entry]
0x140142857  mov     eax, [r9]
0x14014285a  add     r14, rax
0x14014285d  mov     [rsp+148h+var_E0], r14
0x140142862  mov     [rsp+148h+var_C0], r14
0x14014286a  mov     eax, r14d
0x14014286d  and     eax, 0FFFh
0x140142872  mov     r14d, 1000h
0x140142878  sub     r14d, eax
0x14014287b  mov     [rsp+148h+var_D0], r14d
0x140142880  cmp     dword ptr [r9+8], 0
0x140142885  jz      loc_140142746
0x14014288b  cmp     r14d, 50h ; 'P'
0x14014288f  jnb     short loc_1401428DA
0x140142891  bts     rcx, 13h
0x140142896  mov     [rdi+10h], rcx
0x14014289a  mov     [rsp+148h+Src], r15; Src
0x14014289f  mov     r9d, r14d; int
0x1401428a2  mov     r8, 0FFFFFFFFFFFFFFFFh; int
0x1401428a9  mov     rdx, r12; int
0x1401428ac  mov     rcx, rdi; int
0x1401428af  call    NtOfsPutData
0x1401428b4  nop
0x1401428b5  and     qword ptr [rdi+10h], 0FFFFFFFFFFF7FFFFh
0x1401428bd  mov     eax, r14d
0x1401428c0  mov     rcx, [rsp+148h+var_E0]
0x1401428c5  add     rcx, rax
0x1401428c8  mov     [rsp+148h+var_E0], rcx
0x1401428cd  mov     [rsp+148h+var_C0], rcx
0x1401428d5  mov     r9, [rsp+148h+Entry]
0x1401428da  lea     rax, [r9+60h]
0x1401428de  mov     qword ptr [rsp+148h+var_118], r9
0x1401428e3  mov     qword ptr [rsp+148h+var_120], rax
0x1401428e8  mov     r8d, [r9+4]
0x1401428ec  mov     rdx, [r9+90h]
0x1401428f3  mov     rcx, [r9+88h]
0x1401428fa  call    FsLibRangeTrackBufferExtents
0x1401428ff  mov     r9, [rsp+148h+Entry]
0x140142904  mov     [r9+8], eax
0x140142908  jmp     loc_140142735
0x14014290d  mov     rcx, [rsp+148h+var_B8]
0x140142915  jmp     loc_1401426A9
0x14014291a  cmp     eax, 0C0000023h
0x14014291f  jz      loc_1401425A6
0x140142925  mov     r9, [rsp+148h+Entry]
  ... truncated ...
```
