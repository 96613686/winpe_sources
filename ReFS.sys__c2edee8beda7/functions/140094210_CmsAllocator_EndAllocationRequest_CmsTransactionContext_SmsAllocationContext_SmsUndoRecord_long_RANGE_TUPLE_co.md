# CmsAllocator::EndAllocationRequest(CmsTransactionContext *,SmsAllocationContext *,SmsUndoRecord * &,long *,_RANGE_TUPLE const *,CmsStream *)

- ea: `0x140094210`
- end: `0x1400946b5`
- name: `?EndAllocationRequest@CmsAllocator@@AEAAXPEAVCmsTransactionContext@@PEAUSmsAllocationContext@@AEAPEAUSmsUndoRecord@@PEAJPEBU_RANGE_TUPLE@@PEAVCmsStream@@@Z`
- size: `1189`
- prototype: `void __usercall(CmsAllocator *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, struct SmsAllocationContext *@<r8>, struct SmsUndoRecord **@<r9>, int *, const struct _RANGE_TUPLE *, struct CmsStream *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14006e060`
- `0x1401658c0`

## callees

- `0x140012c34`
- `0x14002dd70`
- `0x140049014`
- `0x140077af0`
- `0x140078ce0`
- `0x140094210`
- `0x140094900`
- `0x1400a889c`
- `0x1400b14c8`
- `0x1400cbe48`
- `0x1400d3348`
- `0x1401f3fc0`
- `0x1401f4100`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140094583`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14009437e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14009437e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140094552`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140094552`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1400943e6`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1400944a6`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1400943e6`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1400944a6`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140094409`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400944d2`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140094409`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400944d2`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140201f7a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140201f7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094692`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094692`

## pseudocode

```c
void __fastcall CmsAllocator::EndAllocationRequest(
        CmsAllocator *this,
        struct CmsTransactionContext *a2,
        struct SmsAllocationContext *a3,
        struct SmsUndoRecord **a4,
        int *a5,
        const struct _RANGE_TUPLE *a6,
        struct CmsStream *a7)
{
  struct CmsTransactionContext *v7; // r12
  __int64 v8; // r13
  __int64 v11; // r9
  struct CmsStream *v12; // r11
  const struct _RANGE_TUPLE *v14; // rcx
  __int64 v15; // rax
  __int128 v16; // xmm0
  __int64 v17; // rcx
  __int128 v18; // xmm0
  struct SmsUndoRecord *v19; // rcx
  __int64 v20; // rbx
  struct _SLIST_ENTRY *v21; // r8
  struct _NPAGED_LOOKASIDE_LIST *v22; // rcx
  SmsAllocationRegionEx *v23; // rcx
  __int64 v24; // rbx
  __int64 v25; // r8
  int v26; // eax
  __int64 v27; // r12
  _QWORD *v28; // r10
  _QWORD *v29; // rdx
  _QWORD *v30; // rcx
  __int64 v31; // rbx
  __int64 v32; // r8
  struct SmsUndoRecord *v33; // rbx
  unsigned int v34; // eax
  _OWORD *v35; // rcx
  int v36; // eax
  __int64 v37; // rbx
  __int64 v38; // r8
  __int64 v39; // rcx
  struct CmsTransactionContext *v40; // rdx
  struct CmsTransactionContext *v41; // [rsp+58h] [rbp-B0h]
  _BYTE v42[16]; // [rsp+60h] [rbp-A8h] BYREF
  __int16 v43; // [rsp+78h] [rbp-90h]
  char v44; // [rsp+7Ah] [rbp-8Eh]
  int v45; // [rsp+88h] [rbp-80h]
  _OWORD Src[4]; // [rsp+98h] [rbp-70h] BYREF
  __int128 v47; // [rsp+D8h] [rbp-30h]
  __int128 i; // [rsp+E8h] [rbp-20h]
  __int64 v49; // [rsp+F8h] [rbp-10h]

  v7 = a2;
  v8 = *((_QWORD *)this + 57);
  v11 = 0;
  v12 = a7;
  v41 = a2;
  LODWORD(a2) = (_DWORD)a6;
  v47 = 0;
  v49 = 0;
  v14 = a6;
  for ( i = 0; v14 < (const struct _RANGE_TUPLE *)((char *)a6 + 64); v14 = (const struct _RANGE_TUPLE *)((char *)v14 + 16) )
  {
    v15 = *((_QWORD *)v14 + 1);
    if ( !v15 )
      break;
    v11 += v15;
  }
  v16 = *(_OWORD *)a6;
  v17 = *((unsigned int *)a3 + 17);
  *(_QWORD *)&i = this;
  Src[0] = v16;
  v18 = *((_OWORD *)a6 + 2);
  Src[1] = *((_OWORD *)a6 + 1);
  Src[2] = v18;
  Src[3] = *((_OWORD *)a6 + 3);
  LOBYTE(v47) = (v17 & 0x10) != 0 || *((_BYTE *)this + 492) == 2;
  *((_QWORD *)&v47 + 1) = a7;
  LODWORD(v49) = 0;
  BYTE3(v47) = v17 & 1;
  *(_WORD *)((char *)&v47 + 1) = (unsigned __int8)v17 >> 7;
  *((_QWORD *)&i + 1) = v11;
  if ( *a5 >= 0 )
  {
    if ( *((_BYTE *)this + 492) == 3 )
    {
      if ( (v17 & 4) != 0 )
      {
        BYTE2(v47) = 1;
        CmsAllocator::AdjustAllocatorSummary(this, 0, 0, v11, 0);
      }
      v26 = *((_DWORD *)a3 + 17);
      if ( (v26 & 0x21) != 0 )
      {
        if ( (v26 & 1) != 0 )
        {
          *((_DWORD *)a3 + 14) |= 0x100u;
          LODWORD(v49) = 512;
          CmsStream::IncrementStreamReserveClusters(v12, v7, v11);
        }
        else
        {
          v27 = v11;
          if ( (v26 & 0x1000) == 0 )
          {
            v36 = *((_DWORD *)a3 + 14);
            if ( (v36 & 0x100) != 0 && *((_QWORD *)a3 + 6) == v11 )
            {
              v27 = 0;
              *((_DWORD *)a3 + 14) = v36 & 0xFFFFFEFF;
            }
          }
          v28 = (_QWORD *)(*((_QWORD *)v12 + 2) + 16LL);
          if ( (_QWORD *)*v28 == v28 )
          {
            v29 = 0;
          }
          else
          {
            v29 = (_QWORD *)(*v28 - 32LL);
            do
            {
              if ( v29[2] == *((_QWORD *)v12 + 3) )
                break;
              v30 = (_QWORD *)v29[4];
              v29 = 0;
              if ( v30 != v28 )
                v29 = v30 - 4;
            }
            while ( v29 );
          }
          if ( (*(_BYTE *)(*(_QWORD *)(*v29 + 88LL) + 8LL) & 8) != 0 )
          {
            v37 = *((_QWORD *)v41 + 1);
            if ( (int)CmsStream::UpdateStreamSummary((__int64)v12, v41, 0, -v11, 0, 0, 0, 0, 0, 0) < 0 )
            {
              if ( (_BYTE)KdDebuggerEnabled )
                __debugbreak();
              LOBYTE(v38) = 1;
              CmsVolume::ChangeVolumeOptionDynamically(v37, 0x20000000, v38);
            }
          }
          v31 = ExAcquireAutoExpandPushLockShared(v8 + 3856, 2);
          CmsVolume::ProcessReservationUndo((CmsVolume *)v8, (struct SmsAllocationContext *)((char *)a3 + 48));
          if ( v27 )
            CmsVolume::RemoveReservationForGlobalStreamReserve((CmsVolume *)v8, v27);
          ExReleaseAutoExpandPushLockShared(v31, 2, v32);
          v7 = v41;
          LODWORD(v49) = 256;
        }
      }
      else if ( (v26 & 0x40) != 0 && (*(_DWORD *)(v8 + 3396) & 0x800000) == 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v8 + 3768));
      }
    }
    v33 = *a4;
    *((_QWORD *)v33 + 5) = *(_QWORD *)this;
    *((_DWORD *)v33 + 2) = 104;
    *((_DWORD *)v33 + 8) = 0;
    *((_OWORD *)v33 + 3) = 0;
    *((_OWORD *)v33 + 4) = 0;
    *((_QWORD *)v33 + 10) = 0;
    v34 = *((_DWORD *)v33 + 2);
    if ( v34 )
    {
      v35 = (_OWORD *)*((_QWORD *)v33 + 3);
      a2 = (struct CmsTransactionContext *)Src;
      if ( Src != v35 )
        memmove(v35, Src, v34);
    }
    *(_QWORD *)v33 = *((_QWORD *)v7 + 18);
    *((_QWORD *)v7 + 18) = v33;
    *a4 = 0;
  }
  else if ( v11 )
  {
    LOBYTE(v11) = 1;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    CmsVolume::BeginTopLevelActionInternal(v17, v7, v42, v11, 0, 0);
    CmsBPlusTable::FormatUndoRecord(*(CmsBPlusTable **)this, v40, *a4, 0, Src, 0x68u, 0);
    *a4 = 0;
    CmsVolume::AbortTopLevelAction((CmsVolume *)v8, v7, (struct _SmsTopLevelAction *)v42);
  }
  if ( *((_DWORD *)a3 + 14) && (*((_DWORD *)a3 + 17) & 0x1000) == 0 )
  {
    v24 = ExAcquireAutoExpandPushLockShared(v8 + 3856, 2);
    CmsVolume::ProcessReservationUndo((CmsVolume *)v8, (struct SmsAllocationContext *)((char *)a3 + 48));
    ExReleaseAutoExpandPushLockShared(v24, 2, v25);
  }
  v19 = *a4;
  if ( *a4 && (*((_BYTE *)v19 + 20) & 4) == 0 )
  {
    v20 = *((_QWORD *)v19 - 2);
    v21 = (struct _SLIST_ENTRY *)((char *)v19 - 16);
    if ( !v20 )
      goto LABEL_60;
    if ( *(_BYTE *)(v20 + 8) )
    {
      v22 = (struct _NPAGED_LOOKASIDE_LIST *)(v20 + 64);
      if ( *(_BYTE *)(v20 + 9) )
        ExFreeToNPagedLookasideList(v22, v21);
      else
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v22, v21);
      goto LABEL_16;
    }
    v39 = *(_QWORD *)(v20 + 88);
    if ( (int)v39 < *(_DWORD *)(v20 + 80) || SHIDWORD(v39) >= (int)v39 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v20 + 64), v21);
      _InterlockedIncrement((volatile signed __int32 *)(v20 + 88));
    }
    else
    {
LABEL_60:
      ExFreePoolWithTag(v21, 0);
    }
  }
LABEL_16:
  v23 = (SmsAllocationRegionEx *)*((_QWORD *)a3 + 3);
  if ( v23 )
  {
    SmsAllocationRegionEx::`scalar deleting destructor'(v23, (unsigned int)a2);
    *((_QWORD *)a3 + 3) = 0;
  }
}

```

## disassembly

```asm
0x140094210  mov     r11, rsp
0x140094213  push    rbp
0x140094214  push    rdi
0x140094215  lea     rbp, [r11-58h]
0x140094219  sub     rsp, 148h
0x140094220  mov     rax, cs:__security_cookie
0x140094227  xor     rax, rsp
0x14009422a  mov     [rbp+50h+var_50], rax
0x14009422e  mov     [r11-20h], rsi
0x140094232  xor     eax, eax
0x140094234  mov     [r11-28h], r12
0x140094238  xorps   xmm0, xmm0
0x14009423b  mov     [r11-30h], r13
0x14009423f  mov     r12, rdx
0x140094242  mov     r13, [rcx+1C8h]
0x140094249  mov     rdi, r8
0x14009424c  mov     [r11-38h], r14
0x140094250  mov     r14, r9
0x140094253  mov     [r11-40h], r15
0x140094257  xor     r9d, r9d
0x14009425a  mov     r11, [rbp+50h+arg_30]
0x140094261  mov     r15, rcx
0x140094264  mov     [rsp+150h+var_100], rdx
0x140094269  mov     rdx, [rbp+50h+arg_28]
0x140094270  movups  [rbp+50h+var_80], xmm0
0x140094274  mov     [rbp+50h+var_60], rax
0x140094278  mov     rcx, rdx
0x14009427b  movups  [rbp+50h+var_70], xmm0
0x14009427f  lea     r8, [rdx+40h]
0x140094283  cmp     rdx, r8
0x140094286  jnb     short loc_14009429D
0x140094288  mov     rax, [rcx+8]
0x14009428c  test    rax, rax
0x14009428f  jz      short loc_14009429D
0x140094291  add     r9, rax; __int64
0x140094294  add     rcx, 10h
0x140094298  cmp     rcx, r8
0x14009429b  jb      short loc_140094288
0x14009429d  movups  xmm0, xmmword ptr [rdx]
0x1400942a0  mov     ecx, [rdi+44h]
0x1400942a3  mov     qword ptr [rbp+50h+var_70], r15
0x1400942a7  movaps  [rbp+50h+Src], xmm0
0x1400942ab  movups  xmm1, xmmword ptr [rdx+10h]
0x1400942af  movups  xmm0, xmmword ptr [rdx+20h]
0x1400942b3  movaps  [rbp+50h+var_B0], xmm1
0x1400942b7  movaps  [rbp+50h+var_A0], xmm0
0x1400942bb  movups  xmm1, xmmword ptr [rdx+30h]
0x1400942bf  movaps  [rbp+50h+var_90], xmm1
0x1400942c3  test    cl, 10h
0x1400942c6  jz      loc_1400943B6
0x1400942cc  mov     byte ptr [rbp+50h+var_80], 1
0x1400942d0  xor     esi, esi
0x1400942d2  mov     [rsp+140h], rbx
0x1400942da  movzx   eax, cl
0x1400942dd  mov     qword ptr [rbp+50h+var_80+8], r11
0x1400942e1  and     al, 1
0x1400942e3  mov     dword ptr [rbp+50h+var_60], esi
0x1400942e6  mov     byte ptr [rbp+50h+var_80+3], al
0x1400942e9  movzx   eax, cl
0x1400942ec  shr     al, 7
0x1400942ef  mov     byte ptr [rbp+50h+var_80+1], al
0x1400942f2  mov     rax, [rbp+50h+arg_20]
0x1400942f9  mov     qword ptr [rbp+50h+var_70+8], r9
0x1400942fd  mov     byte ptr [rbp+50h+var_80+2], sil
0x140094301  cmp     [rax], esi
0x140094303  jge     loc_14009441A
0x140094309  test    r9, r9
0x14009430c  jnz     loc_140201F10
0x140094312  cmp     dword ptr [rdi+38h], 0
0x140094316  mov     r15, [rsp+150h+var_38]
0x14009431e  mov     r12, [rsp+150h+var_20]
0x140094326  jnz     loc_1400943CD
0x14009432c  mov     rcx, [r14]
0x14009432f  mov     r14, [rsp+150h+var_30]
0x140094337  mov     r13, [rsp+150h+var_28]
0x14009433f  mov     rsi, [rsp+150h+var_18]
0x140094347  test    rcx, rcx
0x14009434a  jz      short loc_14009438A
0x14009434c  test    byte ptr [rcx+14h], 4
0x140094350  jnz     short loc_14009438A
0x140094352  mov     rbx, [rcx-10h]
0x140094356  lea     r8, [rcx-10h]
0x14009435a  test    rbx, rbx
0x14009435d  jz      loc_14009468D
0x140094363  cmp     byte ptr [rbx+8], 0
0x140094367  jz      loc_140094671
0x14009436d  cmp     byte ptr [rbx+9], 0
0x140094371  lea     rcx, [rbx+40h]; Lookaside
0x140094375  mov     rdx, r8; Entry
0x140094378  jz      loc_140094552
0x14009437e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140094385  nop     dword ptr [rax+rax+00h]
0x14009438a  mov     rcx, [rdi+18h]; this
0x14009438e  mov     rbx, [rsp+140h]
0x140094396  test    rcx, rcx
0x140094399  jnz     loc_1400946A3
0x14009439f  mov     rcx, [rbp+50h+var_50]
0x1400943a3  xor     rcx, rsp; StackCookie
0x1400943a6  call    __security_check_cookie
0x1400943ab  add     rsp, 148h
0x1400943b2  pop     rdi
0x1400943b3  pop     rbp
0x1400943b4  retn
0x1400943b6  cmp     byte ptr [r15+1ECh], 2
0x1400943be  jz      loc_1400942CC
0x1400943c4  mov     byte ptr [rbp+50h+var_80], 0
0x1400943c8  jmp     loc_1400942D0
0x1400943cd  test    dword ptr [rdi+44h], 1000h
0x1400943d4  jnz     loc_14009432C
0x1400943da  lea     rcx, [r13+0F10h]
0x1400943e1  mov     edx, 2
0x1400943e6  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x1400943ed  nop     dword ptr [rax+rax+00h]
0x1400943f2  lea     rdx, [rdi+30h]; struct SmsReservationUndoRecord *
0x1400943f6  mov     rcx, r13; this
0x1400943f9  mov     rbx, rax
0x1400943fc  call    ?ProcessReservationUndo@CmsVolume@@QEAAXPEAUSmsReservationUndoRecord@@@Z; CmsVolume::ProcessReservationUndo(SmsReservationUndoRecord *)
0x140094401  mov     edx, 2
0x140094406  mov     rcx, rbx
0x140094409  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x140094410  nop     dword ptr [rax+rax+00h]
0x140094415  jmp     loc_14009432C
0x14009441a  cmp     byte ptr [r15+1ECh], 3
0x140094422  jnz     loc_1400944EA
0x140094428  test    cl, 4
0x14009442b  jnz     loc_1400945A8
0x140094431  mov     eax, [rdi+44h]
0x140094434  test    al, 21h
0x140094436  jz      loc_140094664
0x14009443c  test    al, 1
0x14009443e  jnz     loc_1400945C3
0x140094444  mov     r12, r9
0x140094447  bt      eax, 0Ch
0x14009444b  jnb     loc_1400945E4
0x140094451  mov     r10, [r11+10h]
0x140094455  add     r10, 10h
0x140094459  mov     rdx, [r10]
0x14009445c  cmp     rdx, r10
0x14009445f  jz      short loc_140094487
0x140094461  mov     r8, [r11+18h]
0x140094465  add     rdx, 0FFFFFFFFFFFFFFE0h
0x140094469  cmp     [rdx+10h], r8
0x14009446d  jz      short loc_140094489
0x14009446f  mov     rcx, [rdx+20h]
0x140094473  xor     edx, edx
0x140094475  cmp     rcx, r10
0x140094478  lea     rax, [rcx-20h]
0x14009447c  cmovnz  rdx, rax
0x140094480  test    rdx, rdx
0x140094483  jnz     short loc_140094469
0x140094485  jmp     short loc_140094489
0x140094487  xor     edx, edx
0x140094489  mov     rax, [rdx]
0x14009448c  mov     rcx, [rax+58h]
0x140094490  test    byte ptr [rcx+8], 8
0x140094494  jnz     loc_14009460A
0x14009449a  lea     rcx, [r13+0F10h]
0x1400944a1  mov     edx, 2
0x1400944a6  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x1400944ad  nop     dword ptr [rax+rax+00h]
0x1400944b2  lea     rdx, [rdi+30h]; struct SmsReservationUndoRecord *
0x1400944b6  mov     rcx, r13; this
0x1400944b9  mov     rbx, rax
0x1400944bc  call    ?ProcessReservationUndo@CmsVolume@@QEAAXPEAUSmsReservationUndoRecord@@@Z; CmsVolume::ProcessReservationUndo(SmsReservationUndoRecord *)
0x1400944c1  test    r12, r12
0x1400944c4  jnz     loc_140094654
0x1400944ca  mov     edx, 2
0x1400944cf  mov     rcx, rbx
0x1400944d2  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x1400944d9  nop     dword ptr [rax+rax+00h]
0x1400944de  mov     r12, [rsp+150h+var_100]
0x1400944e3  bts     esi, 8
0x1400944e7  mov     dword ptr [rbp+50h+var_60], esi
0x1400944ea  mov     rbx, [r14]
0x1400944ed  xorps   xmm0, xmm0
0x1400944f0  mov     rax, [r15]
0x1400944f3  mov     [rbx+28h], rax
0x1400944f7  xor     eax, eax
0x1400944f9  mov     dword ptr [rbx+8], 68h ; 'h'
0x140094500  mov     dword ptr [rbx+20h], 0
0x140094507  movups  xmmword ptr [rbx+30h], xmm0
0x14009450b  movups  xmmword ptr [rbx+40h], xmm0
0x14009450f  mov     [rbx+50h], rax
0x140094513  mov     eax, [rbx+8]
0x140094516  test    eax, eax
0x140094518  jz      short loc_140094533
0x14009451a  mov     rcx, [rbx+18h]; void *
0x14009451e  lea     rdx, [rbp+50h+Src]
0x140094522  cmp     rdx, rcx
0x140094525  jz      short loc_140094533
0x140094527  mov     r8d, eax; Size
0x14009452a  lea     rdx, [rbp+50h+Src]; Src
0x14009452e  call    memmove
0x140094533  mov     rax, [r12+90h]
0x14009453b  mov     [rbx], rax
0x14009453e  mov     [r12+90h], rbx
0x140094546  mov     qword ptr [r14], 0
0x14009454d  jmp     loc_140094312
0x140094552  call    cs:__imp_ExFreeToPagedLookasideList
0x140094559  nop     dword ptr [rax+rax+00h]
0x14009455e  jmp     loc_14009438A
0x140094563  test    dword ptr [r13+0D44h], 800000h
0x14009456e  jnz     loc_1400944EA
0x140094574  nop
0x140094575  lock inc dword ptr [r13+0EB8h]
0x14009457d  nop
0x14009457e  jmp     loc_1400944EA
0x140094583  mov     rax, cs:KdDebuggerEnabled
0x14009458a  cmp     [rax], sil
0x14009458d  jnz     loc_14009464E
0x140094593  mov     r8b, 1
0x140094596  mov     edx, 20000000h
0x14009459b  mov     rcx, rbx
0x14009459e  call    ?ChangeVolumeOptionDynamically@CmsVolume@@QEAAXW4_EMS_VOLUME_FLAGS@@E@Z; CmsVolume::ChangeVolumeOptionDynamically(_EMS_VOLUME_FLAGS,uchar)
0x1400945a3  jmp     loc_14009449A
0x1400945a8  xor     r8d, r8d; __int64
0x1400945ab  mov     byte ptr [rbp+50h+var_80+2], 1
0x1400945af  xor     edx, edx; __int64
0x1400945b1  mov     [rsp+150h+var_130], rsi; __int64
0x1400945b6  mov     rcx, r15; this
0x1400945b9  call    ?AdjustAllocatorSummary@CmsAllocator@@QEAAX_J000@Z; CmsAllocator::AdjustAllocatorSummary(__int64,__int64,__int64,__int64)
0x1400945be  jmp     loc_140094431
0x1400945c3  or      dword ptr [rdi+38h], 100h
0x1400945ca  mov     r8, r9; __int64
0x1400945cd  mov     rdx, r12; struct CmsTransactionContext *
0x1400945d0  mov     dword ptr [rbp+50h+var_60], 200h
0x1400945d7  mov     rcx, r11; this
0x1400945da  call    ?IncrementStreamReserveClusters@CmsStream@@QEAAXAEAVCmsTransactionContext@@_J@Z; CmsStream::IncrementStreamReserveClusters(CmsTransactionContext &,__int64)
0x1400945df  jmp     loc_1400944EA
0x1400945e4  mov     eax, [rdi+38h]
0x1400945e7  bt      eax, 8
0x1400945eb  jnb     loc_140094451
0x1400945f1  cmp     [rdi+30h], r9
0x1400945f5  jnz     loc_140094451
0x1400945fb  xor     r12d, r12d
0x1400945fe  btr     eax, 8
0x140094602  mov     [rdi+38h], eax
0x140094605  jmp     loc_140094451
0x14009460a  mov     rdx, [rsp+150h+var_100]
0x14009460f  xor     eax, eax
0x140094611  mov     word ptr [rsp+150h+var_108], ax
0x140094616  xor     ecx, ecx
0x140094618  mov     [rsp+150h+var_110], cx
0x14009461d  neg     r9
0x140094620  mov     qword ptr [rsp+150h+var_118], rax
0x140094625  xor     r8d, r8d
0x140094628  mov     rbx, [rdx+8]
0x14009462c  mov     rcx, r11
0x14009462f  mov     qword ptr [rsp+150h+var_120], rax
0x140094634  mov     byte ptr [rsp+150h+var_128], al
0x140094638  mov     byte ptr [rsp+150h+var_130], al
0x14009463c  call    ?UpdateStreamSummary@CmsStream@@QEAAJPEAVCmsTransactionContext@@_J1W4LogUndoUpdateStreamSummary@@W4LogRedoUpdateStreamSummary@@PEA_J4W4EMS_STREAM_SUMMARY_FLAGS@@5@Z; CmsStream::UpdateStreamSummary(CmsTransactionContext *,__int64,__int64,LogUndoUpdateStreamSummary,LogRedoUpdateStreamSummary,__int64 *,__int64 *,EMS_STREAM_SUMMARY_FLAGS,EMS_STREAM_SUMMARY_FLAGS)
0x140094641  test    eax, eax
0x140094643  jns     loc_14009449A
0x140094649  jmp     loc_140094583
0x14009464e  int     3; Trap to Debugger
0x14009464f  jmp     loc_140094593
0x140094654  mov     rdx, r12; __int64
0x140094657  mov     rcx, r13; this
0x14009465a  call    ?RemoveReservationForGlobalStreamReserve@CmsVolume@@QEAAX_J@Z; CmsVolume::RemoveReservationForGlobalStreamReserve(__int64)
0x14009465f  jmp     loc_1400944CA
0x140094664  test    al, 40h
0x140094666  jz      loc_1400944EA
0x14009466c  jmp     loc_140094563
0x140094671  mov     rcx, [rbx+58h]
0x140094675  cmp     ecx, [rbx+50h]
0x140094678  jl      loc_140201F73
0x14009467e  mov     rax, rcx
0x140094681  shr     rax, 20h
0x140094685  cmp     eax, ecx
0x140094687  jge     loc_140201F73
0x14009468d  xor     edx, edx; Tag
0x14009468f  mov     rcx, r8; P
0x140094692  call    cs:__imp_ExFreePoolWithTag
0x140094699  nop     dword ptr [rax+rax+00h]
0x14009469e  jmp     loc_14009438A
0x1400946a3  call    ??_GSmsAllocationRegionEx@@QEAAPEAXI@Z; SmsAllocationRegionEx::`scalar deleting destructor'(uint)
0x1400946a8  mov     qword ptr [rdi+18h], 0
0x1400946b0  jmp     loc_14009439F
0x140201f10  mov     byte ptr [rsp+150h+var_128], sil
0x140201f15  lea     r8, [rsp+150h+var_F8]
0x140201f1a  mov     r9b, 1
0x140201f1d  mov     byte ptr [rsp+150h+var_130], sil
0x140201f22  mov     rdx, r12
0x140201f25  mov     [rsp+150h+var_E0], si
0x140201f2a  mov     [rsp+150h+var_DE], sil
0x140201f2f  mov     [rbp+50h+var_D0], esi
0x140201f32  call    ?BeginTopLevelActionInternal@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@EEW4FoldOnlyTla@@@Z; CmsVolume::BeginTopLevelActionInternal(CmsTransactionContext *,_SmsTopLevelAction *,uchar,uchar,FoldOnlyTla)
0x140201f37  mov     r8, [r14]; struct SmsUndoRecord *
0x140201f3a  lea     rax, [rbp+50h+Src]
0x140201f3e  mov     rcx, [r15]; this
0x140201f41  xor     r9d, r9d; struct SmsLookupStack *
0x140201f44  mov     [rsp+150h+var_120], esi; int
0x140201f48  mov     [rsp+150h+var_128], 68h ; 'h'; unsigned int
0x140201f50  mov     [rsp+150h+var_130], rax; void *
0x140201f55  call    ?FormatUndoRecord@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@PEAUSmsUndoRecord@@PEBUSmsLookupStack@@PEAXKJ@Z; CmsBPlusTable::FormatUndoRecord(CmsTransactionContext *,SmsUndoRecord *,SmsLookupStack const *,void *,ulong,long)
0x140201f5a  lea     r8, [rsp+150h+var_F8]; struct _SmsTopLevelAction *
0x140201f5f  mov     [r14], rsi
0x140201f62  mov     rdx, r12; struct CmsTransactionContext *
0x140201f65  mov     rcx, r13; this
  ... truncated ...
```
