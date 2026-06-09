# CmsBlockRefcount::PersistCacheEntry(CmsTransactionContext *,CmsRefcountCacheEntry *)

- ea: `0x1400d04d4`
- end: `0x1400d0a2e`
- name: `?PersistCacheEntry@CmsBlockRefcount@@AEAAJPEAVCmsTransactionContext@@PEAVCmsRefcountCacheEntry@@@Z`
- size: `1370`
- prototype: `int(CmsBlockRefcount *__hidden this, struct CmsTransactionContext *, struct CmsRefcountCacheEntry *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400d03dc`

## callees

- `0x140004870`
- `0x1400057f8`
- `0x14007ec4c`
- `0x1400854bc`
- `0x14008c930`
- `0x14008d430`
- `0x14008e220`
- `0x1400a2a8c`
- `0x1400a8c50`
- `0x1400a9624`
- `0x1400a9fa4`
- `0x1400aa998`
- `0x1400ac748`
- `0x1400d04d4`
- `0x1400d1ac0`

## import_xrefs

- `ntdll!RtlCopyMemoryNonTemporal` at `0x1400d0740`
- `ntdll!RtlCopyMemoryNonTemporal` at `0x1400d0740`
- `ntdll!RtlFillMemoryNonTemporal` at `0x1400d0756`
- `ntdll!RtlFillMemoryNonTemporal` at `0x1400d0756`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400d0992`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400d0992`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400d09a0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400d09a0`

## pseudocode

```c
__int64 __fastcall CmsBlockRefcount::PersistCacheEntry(
        CmsBlockRefcount *this,
        CmsVolume **a2,
        struct CmsRefcountCacheEntry *a3)
{
  struct CmsRefcountCacheEntry *v3; // r13
  char v6; // r14
  char *v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  int inserted; // edi
  unsigned __int64 *v12; // rbx
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  __int64 v15; // rdx
  int updated; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  struct SmsPage *v19; // r8
  CmsVolume *v20; // r12
  unsigned int v21; // r9d
  struct SmsPage *v22; // r14
  unsigned int v23; // ebx
  int *v24; // rdx
  int v25; // r10d
  int *v26; // rcx
  int v27; // eax
  struct _SmsTriageContext *v28; // rbx
  char v30; // [rsp+40h] [rbp-C0h]
  char v31; // [rsp+41h] [rbp-BFh]
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v33; // [rsp+50h] [rbp-B0h]
  int v34; // [rsp+58h] [rbp-A8h]
  __int64 *v35; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v36; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v37; // [rsp+78h] [rbp-88h]
  char v38; // [rsp+80h] [rbp-80h]
  __int64 v39; // [rsp+84h] [rbp-7Ch]
  __int16 v40; // [rsp+8Ch] [rbp-74h]
  unsigned __int64 v41; // [rsp+90h] [rbp-70h] BYREF
  __int64 v42; // [rsp+98h] [rbp-68h]
  char v43; // [rsp+A0h] [rbp-60h]
  __int64 v44; // [rsp+A4h] [rbp-5Ch]
  __int16 v45; // [rsp+ACh] [rbp-54h]
  __int64 v46; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v47; // [rsp+B8h] [rbp-48h]
  struct SmsPage *v48[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v49; // [rsp+D0h] [rbp-30h]
  __int64 v50; // [rsp+E0h] [rbp-20h]
  struct CmsRefcountCacheEntry *v51; // [rsp+E8h] [rbp-18h]
  _QWORD *v52; // [rsp+F0h] [rbp-10h] BYREF
  int v53; // [rsp+F8h] [rbp-8h] BYREF
  __int16 v54; // [rsp+FCh] [rbp-4h]
  __int64 *v55; // [rsp+100h] [rbp+0h]
  __int128 v56; // [rsp+108h] [rbp+8h] BYREF
  int v57; // [rsp+118h] [rbp+18h]
  unsigned __int64 *v58; // [rsp+120h] [rbp+20h]
  _BYTE v59[24]; // [rsp+128h] [rbp+28h] BYREF
  __int16 v60; // [rsp+140h] [rbp+40h]
  char v61; // [rsp+142h] [rbp+42h]
  int v62; // [rsp+150h] [rbp+50h]
  __int64 v63; // [rsp+160h] [rbp+60h] BYREF
  __int64 v64; // [rsp+168h] [rbp+68h]
  char v65; // [rsp+170h] [rbp+70h]
  __int64 v66; // [rsp+174h] [rbp+74h]
  _BYTE v67[4]; // [rsp+17Ch] [rbp+7Ch] BYREF
  _BYTE v68[2046]; // [rsp+180h] [rbp+80h] BYREF
  __int16 v69; // [rsp+97Eh] [rbp+87Eh]

  v51 = a3;
  v46 = 0;
  v3 = a3;
  v47 = 0;
  v57 = 0;
  v58 = 0;
  v63 = 0;
  v50 = 0;
  v64 = 0;
  v65 = 0;
  v56 = 0;
  v66 = 0;
  *(_OWORD *)v48 = 0;
  v49 = 0;
  memset_0(v68, 0, sizeof(v68));
  v36 = 0;
  v69 = 0;
  v6 = 0;
  v7 = (char *)this + 96;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v31 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v30 = 0;
  do
  {
    SmsAEPushLock::LockShared(v7, &v52);
    v8 = *((_QWORD *)this + 1);
    v46 = *((_QWORD *)v3 + 2);
    v55 = &v46;
    v47 = 1024;
    v50 = 0;
    v53 = 16;
    v54 = 0;
    *(_OWORD *)v48 = 0;
    v49 = 0;
    v9 = CmsTable::PinRow(v8, a2, &v53, 1, &v56, v48, 0);
    inserted = v9;
    if ( v9 < 0 )
    {
      if ( v9 != -1073741772 )
        goto LABEL_31;
      if ( v48[0] )
        CmsBPlusTable::AddPageToDelayedProcessList(
          *((CmsBPlusTable **)this + 1),
          (struct CmsTransactionContext *)a2,
          v48[0],
          1);
      v12 = 0;
LABEL_10:
      v37 = 0;
      v42 = 0;
      if ( v12 )
      {
        v13 = *((_QWORD *)v3 + 2);
        if ( *v12 < v13 )
        {
          v36 = *v12;
          v6 = 1;
          v31 = 1;
          v37 = v13 - *v12;
          v38 = 1;
          v39 = 0;
          v40 = *((_WORD *)v12 + 14);
        }
        v14 = v13 + 1024;
        if ( *v12 + v12[1] > v14 )
        {
          v41 = v14;
          v6 = 1;
          v31 = 1;
          v42 = *v12 + v12[1] - v14;
          v43 = 1;
          v44 = 0;
          v45 = *((_WORD *)v12 + 14);
        }
      }
      CmsVolume::BeginTopLevelActionInternal(v10, a2, v59);
      v15 = *((_QWORD *)v3 + 9);
      v63 = *((_QWORD *)v3 + 2);
      HIDWORD(v66) = *((_DWORD *)v3 + 16);
      v30 = 1;
      v64 = 1024;
      v65 = 1;
      LODWORD(v66) = 1;
      if ( v15 )
        RtlCopyMemoryNonTemporal(v67, v15, 2048);
      else
        RtlFillMemoryNonTemporal(v67, 2048, 0);
      LODWORD(v32) = 16;
      v33 = &v63;
      v35 = &v63;
      WORD2(v32) = 0;
      v34 = 2080;
      if ( v12 )
      {
        if ( !v6 )
        {
          updated = CmsTable::UpdateRow(
                      *((CmsTable **)this + 1),
                      (struct CmsTransactionContext *)a2,
                      (const struct _CmsRow *)&v32,
                      0,
                      0);
          goto LABEL_24;
        }
      }
      else if ( !v6 )
      {
        goto LABEL_23;
      }
      inserted = CmsTable::DeleteRow(*((_QWORD *)this + 1), a2, &v32);
      if ( inserted < 0 )
        goto LABEL_31;
LABEL_23:
      updated = CmsTable::InsertRow(*((_QWORD *)this + 1), a2, &v32, 50);
LABEL_24:
      inserted = updated;
      if ( updated >= 0 )
      {
        if ( !v37
          || (v17 = *((_QWORD *)this + 1),
              v33 = (__int64 *)&v36,
              v35 = (__int64 *)&v36,
              v32 = 16,
              v34 = 32,
              inserted = CmsTable::InsertRow(v17, a2, &v32, 50),
              inserted >= 0) )
        {
          if ( !v42
            || (v18 = *((_QWORD *)this + 1),
                v33 = (__int64 *)&v41,
                v35 = (__int64 *)&v41,
                v32 = 16,
                v34 = 32,
                inserted = CmsTable::InsertRow(v18, a2, &v32, 50),
                inserted >= 0) )
          {
            CmsVolume::CommitTopLevelAction(
              *(CmsVolume **)this,
              (struct CmsTransactionContext *)a2,
              (struct _SmsTopLevelAction *)v59,
              0);
            v30 = 0;
            if ( (*((_BYTE *)v3 + 50) & 4) != 0 )
              _InterlockedAnd16((volatile signed __int16 *)v3 + 25, 0xFFFBu);
          }
        }
      }
      goto LABEL_31;
    }
    v12 = v58;
    if ( *((_BYTE *)v58 + 16) == 1 )
    {
      CmsBPlusTable::AddPageToDelayedProcessList(
        *((CmsBPlusTable **)this + 1),
        (struct CmsTransactionContext *)a2,
        v48[0],
        1);
      goto LABEL_10;
    }
    inserted = -1073741637;
LABEL_31:
    v19 = v48[0];
    if ( !v48[0] )
      goto LABEL_47;
    v20 = a2[1];
    v21 = 3;
    do
    {
      v22 = 0;
      v23 = v21;
      if ( !*((_QWORD *)v19 + 38) )
        goto LABEL_45;
      v24 = (int *)((char *)v19 + 312);
      if ( (v21 & 1) != 0 && (v25 = *v24, *((_DWORD *)v19 + 96) == *v24) )
      {
        v26 = (int *)((char *)v19 + 316);
        v22 = (struct SmsPage *)*((_QWORD *)v19 + 38);
        if ( (v21 & 4) == 0 )
          goto LABEL_43;
        v27 = *v26;
        if ( *((_DWORD *)v19 + 97) != *v26 )
        {
          v23 = v21 & 0xFFFFFFFB;
          goto LABEL_43;
        }
      }
      else
      {
        if ( (v21 & 4) == 0 )
          goto LABEL_45;
        v26 = (int *)((char *)v19 + 316);
        v27 = *((_DWORD *)v19 + 79);
        if ( *((_DWORD *)v19 + 97) != v27 )
          goto LABEL_45;
        v25 = *v24;
        v22 = (struct SmsPage *)*((_QWORD *)v19 + 38);
      }
      *v26 = v27 - 1;
LABEL_43:
      *v24 = v25 - 1;
      if ( v25 == 1 )
        *((_QWORD *)v19 + 38) = 0;
LABEL_45:
      CmsVolume::UnpinInternal(v20, (struct CmsTransactionCore *)a2, v19, v21);
      v19 = v22;
      v21 = v23;
    }
    while ( v22 );
    v3 = v51;
    v48[0] = 0;
LABEL_47:
    if ( *v52 < 0x10u )
      RtlReleaseSRWLockExclusive(v52);
    else
      RtlReleaseSRWLockShared(v52);
    if ( v30 )
      CmsVolume::AbortTopLevelAction(
        *(CmsVolume **)this,
        (struct CmsTransactionContext *)a2,
        (struct _SmsTopLevelAction *)v59);
    if ( inserted != -1073741400 )
      break;
    v28 = a2[23];
    a2[23] = 0;
    inserted = CmsBlockRefcount::TriageCorruptChildRef(this, (struct CmsTransactionContext *)a2, v28);
    MsTriageDeleteContext(v28);
    v6 = v31;
    v7 = (char *)this + 96;
  }
  while ( inserted >= 0 );
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1400d04d4  mov     [rsp-8+arg_18], rbx
0x1400d04d9  push    rbp
0x1400d04da  push    rsi
0x1400d04db  push    rdi
0x1400d04dc  push    r12
0x1400d04de  push    r13
0x1400d04e0  push    r14
0x1400d04e2  push    r15
0x1400d04e4  lea     rbp, [rsp-890h]
0x1400d04ec  sub     rsp, 990h
0x1400d04f3  mov     rax, cs:__security_cookie
0x1400d04fa  xor     rax, rsp
0x1400d04fd  mov     [rbp+8C0h+var_40], rax
0x1400d0504  xor     r12d, r12d
0x1400d0507  mov     [rbp+8C0h+var_8D8], r8
0x1400d050b  xorps   xmm0, xmm0
0x1400d050e  mov     [rbp+8C0h+var_910], r12
0x1400d0512  mov     r13, r8
0x1400d0515  mov     [rbp+8C0h+var_908], r12
0x1400d0519  mov     rsi, rdx
0x1400d051c  mov     [rbp+8C0h+var_8A8], r12d
0x1400d0520  mov     r15, rcx
0x1400d0523  mov     [rbp+8C0h+var_8A0], r12
0x1400d0527  xor     eax, eax
0x1400d0529  mov     [rbp+8C0h+var_860], r12
0x1400d052d  xor     edx, edx; Val
0x1400d052f  mov     [rbp+8C0h+var_8E0], rax
0x1400d0533  mov     r8d, 7FEh; Size
0x1400d0539  mov     [rbp+8C0h+var_858], r12
0x1400d053d  lea     rcx, [rbp+8C0h+var_840]; void *
0x1400d0544  mov     [rbp+8C0h+var_850], r12b
0x1400d0548  movups  [rbp+8C0h+var_8B8], xmm0
0x1400d054c  mov     [rbp+8C0h+var_84C], r12
0x1400d0550  movups  xmmword ptr [rbp+8C0h+var_900], xmm0
0x1400d0554  movups  [rbp+8C0h+var_8F0], xmm0
0x1400d0558  call    memset_0
0x1400d055d  xor     eax, eax
0x1400d055f  mov     [rsp+9C0h+var_950], r12
0x1400d0564  mov     [rbp+8C0h+var_42], ax
0x1400d056b  mov     r14b, r12b
0x1400d056e  lea     rax, [r15+60h]
0x1400d0572  mov     [rsp+9C0h+var_948], r12
0x1400d0577  mov     [rbp+8C0h+var_940], r12b
0x1400d057b  mov     [rbp+8C0h+var_93C], r12
0x1400d057f  mov     [rbp+8C0h+var_930], r12
0x1400d0583  mov     [rbp+8C0h+var_928], r12
0x1400d0587  mov     [rbp+8C0h+var_920], r12b
0x1400d058b  mov     [rbp+8C0h+var_91C], r12
0x1400d058f  mov     [rsp+9C0h+var_97F], r12b
0x1400d0594  mov     [rbp+8C0h+var_880], r12w
0x1400d0599  mov     [rbp+8C0h+var_87E], r12b
0x1400d059d  mov     [rbp+8C0h+var_870], r12d
0x1400d05a1  mov     [rsp+9C0h+var_980], r12b
0x1400d05a6  lea     rdx, [rbp+8C0h+var_8D0]
0x1400d05aa  mov     rcx, rax
0x1400d05ad  call    ?LockShared@SmsAEPushLock@@QEAA?AUContext@1@XZ; SmsAEPushLock::LockShared(void)
0x1400d05b2  mov     rax, [r13+10h]
0x1400d05b6  lea     r8, [rbp+8C0h+var_8C8]
0x1400d05ba  mov     rcx, [r15+8]
0x1400d05be  xorps   xmm0, xmm0
0x1400d05c1  mov     [rbp+8C0h+var_910], rax
0x1400d05c5  mov     r9d, 1
0x1400d05cb  lea     rax, [rbp+8C0h+var_910]
0x1400d05cf  mov     [rsp+9C0h+var_990], r12
0x1400d05d4  mov     [rbp+8C0h+var_8C0], rax
0x1400d05d8  mov     rdx, rsi
0x1400d05db  xor     eax, eax
0x1400d05dd  mov     [rbp+8C0h+var_908], 400h
0x1400d05e5  mov     [rbp+8C0h+var_8E0], rax
0x1400d05e9  lea     rax, [rbp+8C0h+var_900]
0x1400d05ed  mov     [rsp+9C0h+var_998], rax
0x1400d05f2  lea     rax, [rbp+8C0h+var_8B8]
0x1400d05f6  mov     [rsp+9C0h+var_9A0], rax
0x1400d05fb  mov     [rbp+8C0h+var_8C8], 10h
0x1400d0602  mov     [rbp+8C0h+var_8C4], r12w
0x1400d0607  movups  xmmword ptr [rbp+8C0h+var_900], xmm0
0x1400d060b  movups  [rbp+8C0h+var_8F0], xmm0
0x1400d060f  call    ?PinRow@CmsTable@@QEAAJPEAVCmsTransactionContext@@AEBU_CmsKey@@W4EmsPinRowFlags@@PEAU_CmsRow@@PEAUSmsLookupStack@@PEAU_SmsQuickIndex@@@Z; CmsTable::PinRow(CmsTransactionContext *,_CmsKey const &,EmsPinRowFlags,_CmsRow *,SmsLookupStack *,_SmsQuickIndex *)
0x1400d0614  mov     edi, eax
0x1400d0616  test    eax, eax
0x1400d0618  js      short loc_1400D0643
0x1400d061a  mov     rbx, [rbp+8C0h+var_8A0]
0x1400d061e  cmp     byte ptr [rbx+10h], 1
0x1400d0622  jz      short loc_1400D062E
0x1400d0624  mov     edi, 0C00000BBh
0x1400d0629  jmp     loc_1400D08C8
0x1400d062e  mov     r8, [rbp+8C0h+var_900]; struct SmsPage *
0x1400d0632  mov     r9b, 1; bool
0x1400d0635  mov     rcx, [r15+8]; this
0x1400d0639  mov     rdx, rsi; struct CmsTransactionContext *
0x1400d063c  call    ?AddPageToDelayedProcessList@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@PEAUSmsPage@@_N@Z; CmsBPlusTable::AddPageToDelayedProcessList(CmsTransactionContext *,SmsPage *,bool)
0x1400d0641  jmp     short loc_1400D0669
0x1400d0643  cmp     eax, 0C0000034h
0x1400d0648  jnz     loc_1400D08C8
0x1400d064e  mov     r8, [rbp+8C0h+var_900]; struct SmsPage *
0x1400d0652  test    r8, r8
0x1400d0655  jz      short loc_1400D0666
0x1400d0657  mov     rcx, [r15+8]; this
0x1400d065b  mov     r9b, 1; bool
0x1400d065e  mov     rdx, rsi; struct CmsTransactionContext *
0x1400d0661  call    ?AddPageToDelayedProcessList@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@PEAUSmsPage@@_N@Z; CmsBPlusTable::AddPageToDelayedProcessList(CmsTransactionContext *,SmsPage *,bool)
0x1400d0666  mov     rbx, r12
0x1400d0669  mov     [rsp+9C0h+var_948], r12
0x1400d066e  mov     [rbp+8C0h+var_928], r12
0x1400d0672  test    rbx, rbx
0x1400d0675  jz      short loc_1400D06F0
0x1400d0677  mov     rdx, [r13+10h]
0x1400d067b  mov     rax, [rbx]
0x1400d067e  cmp     rax, rdx
0x1400d0681  jnb     short loc_1400D06AF
0x1400d0683  mov     [rsp+9C0h+var_950], rax
0x1400d0688  mov     r14b, 1
0x1400d068b  mov     rax, rdx
0x1400d068e  mov     [rsp+9C0h+var_97F], r14b
0x1400d0693  sub     rax, [rbx]
0x1400d0696  mov     [rsp+9C0h+var_948], rax
0x1400d069b  mov     [rbp+8C0h+var_940], 1
0x1400d069f  mov     [rbp+8C0h+var_93C], 0
0x1400d06a7  movzx   eax, word ptr [rbx+1Ch]
0x1400d06ab  mov     [rbp+8C0h+var_934], ax
0x1400d06af  mov     rax, [rbx+8]
0x1400d06b3  add     rdx, 400h
0x1400d06ba  add     rax, [rbx]
0x1400d06bd  cmp     rax, rdx
0x1400d06c0  jbe     short loc_1400D06F0
0x1400d06c2  mov     [rbp+8C0h+var_930], rdx
0x1400d06c6  mov     r14b, 1
0x1400d06c9  mov     rax, [rbx+8]
0x1400d06cd  sub     rax, rdx
0x1400d06d0  mov     [rsp+9C0h+var_97F], r14b
0x1400d06d5  add     rax, [rbx]
0x1400d06d8  mov     [rbp+8C0h+var_928], rax
0x1400d06dc  mov     [rbp+8C0h+var_920], 1
0x1400d06e0  mov     [rbp+8C0h+var_91C], 0
0x1400d06e8  movzx   eax, word ptr [rbx+1Ch]
0x1400d06ec  mov     [rbp+8C0h+var_914], ax
0x1400d06f0  mov     byte ptr [rsp+9C0h+var_998], r12b
0x1400d06f5  lea     r8, [rbp+8C0h+var_898]
0x1400d06f9  mov     rdx, rsi
0x1400d06fc  mov     byte ptr [rsp+9C0h+var_9A0], r12b
0x1400d0701  call    ?BeginTopLevelActionInternal@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@EEW4FoldOnlyTla@@@Z; CmsVolume::BeginTopLevelActionInternal(CmsTransactionContext *,_SmsTopLevelAction *,uchar,uchar,FoldOnlyTla)
0x1400d0706  mov     rax, [r13+10h]
0x1400d070a  lea     rcx, [rbp+8C0h+var_844]
0x1400d070e  mov     rdx, [r13+48h]
0x1400d0712  mov     [rbp+8C0h+var_860], rax
0x1400d0716  mov     eax, [r13+40h]
0x1400d071a  mov     dword ptr [rbp+8C0h+var_84C+4], eax
0x1400d071d  mov     [rsp+9C0h+var_980], 1
0x1400d0722  mov     [rbp+8C0h+var_858], 400h
0x1400d072a  mov     [rbp+8C0h+var_850], 1
0x1400d072e  mov     dword ptr [rbp+8C0h+var_84C], 1
0x1400d0735  test    rdx, rdx
0x1400d0738  jz      short loc_1400D074E
0x1400d073a  mov     r8d, 800h
0x1400d0740  call    cs:__imp_RtlCopyMemoryNonTemporal
0x1400d0747  nop     dword ptr [rax+rax+00h]
0x1400d074c  jmp     short loc_1400D0762
0x1400d074e  xor     r8d, r8d
0x1400d0751  mov     edx, 800h
0x1400d0756  call    cs:__imp_RtlFillMemoryNonTemporal
0x1400d075d  nop     dword ptr [rax+rax+00h]
0x1400d0762  mov     dword ptr [rsp+9C0h+var_978], 10h
0x1400d076a  lea     rax, [rbp+8C0h+var_860]
0x1400d076e  mov     [rsp+9C0h+var_970], rax
0x1400d0773  lea     rax, [rbp+8C0h+var_860]
0x1400d0777  mov     [rsp+9C0h+var_960], rax
0x1400d077c  mov     word ptr [rsp+9C0h+var_978+4], r12w
0x1400d0782  mov     [rsp+9C0h+var_968], 820h
0x1400d078a  test    rbx, rbx
0x1400d078d  jz      short loc_1400D07AF
0x1400d078f  test    r14b, r14b
0x1400d0792  jnz     short loc_1400D07B4
0x1400d0794  mov     rcx, [r15+8]; this
0x1400d0798  lea     r8, [rsp+9C0h+var_978]; struct _CmsRow *
0x1400d079d  xor     r9d, r9d; struct SmsLookupStack *
0x1400d07a0  mov     [rsp+9C0h+var_9A0], r12; unsigned int *
0x1400d07a5  mov     rdx, rsi; struct CmsTransactionContext *
0x1400d07a8  call    ?UpdateRow@CmsTable@@QEAAJPEAVCmsTransactionContext@@AEBU_CmsRow@@PEAUSmsLookupStack@@PEAK@Z; CmsTable::UpdateRow(CmsTransactionContext *,_CmsRow const &,SmsLookupStack *,ulong *)
0x1400d07ad  jmp     short loc_1400D07F0
0x1400d07af  test    r14b, r14b
0x1400d07b2  jz      short loc_1400D07CF
0x1400d07b4  mov     rcx, [r15+8]
0x1400d07b8  lea     r8, [rsp+9C0h+var_978]
0x1400d07bd  mov     rdx, rsi
0x1400d07c0  call    ?DeleteRow@CmsTable@@QEAAJPEAVCmsTransactionContext@@AEBU_CmsKey@@W4EmsPinRowFlags@@@Z; CmsTable::DeleteRow(CmsTransactionContext *,_CmsKey const &,EmsPinRowFlags)
0x1400d07c5  mov     edi, eax
0x1400d07c7  test    eax, eax
0x1400d07c9  js      loc_1400D08C8
0x1400d07cf  mov     rcx, [r15+8]
0x1400d07d3  lea     r8, [rsp+9C0h+var_978]
0x1400d07d8  mov     [rsp+9C0h+var_988], r12
0x1400d07dd  mov     r9d, 32h ; '2'
0x1400d07e3  mov     rdx, rsi
0x1400d07e6  mov     [rsp+9C0h+var_998], r12
0x1400d07eb  call    ?InsertRow@CmsTable@@QEAAJPEAVCmsTransactionContext@@AEBU_CmsRow@@KKPEAU_SmsQuickIndex@@W4EmsPinRowFlags@@PEA_K@Z; CmsTable::InsertRow(CmsTransactionContext *,_CmsRow const &,ulong,ulong,_SmsQuickIndex *,EmsPinRowFlags,unsigned __int64 *)
0x1400d07f0  mov     edi, eax
0x1400d07f2  test    eax, eax
0x1400d07f4  js      loc_1400D08C8
0x1400d07fa  cmp     [rsp+9C0h+var_948], r12
0x1400d07ff  jbe     short loc_1400D084D
0x1400d0801  mov     rcx, [r15+8]
0x1400d0805  lea     rax, [rsp+9C0h+var_950]
0x1400d080a  mov     [rsp+9C0h+var_970], rax
0x1400d080f  lea     r8, [rsp+9C0h+var_978]
0x1400d0814  lea     rax, [rsp+9C0h+var_950]
0x1400d0819  mov     [rsp+9C0h+var_988], r12
0x1400d081e  mov     r9d, 32h ; '2'
0x1400d0824  mov     [rsp+9C0h+var_960], rax
0x1400d0829  mov     rdx, rsi
0x1400d082c  mov     [rsp+9C0h+var_978], 10h
0x1400d0835  mov     [rsp+9C0h+var_968], 20h ; ' '
0x1400d083d  mov     [rsp+9C0h+var_998], r12
0x1400d0842  call    ?InsertRow@CmsTable@@QEAAJPEAVCmsTransactionContext@@AEBU_CmsRow@@KKPEAU_SmsQuickIndex@@W4EmsPinRowFlags@@PEA_K@Z; CmsTable::InsertRow(CmsTransactionContext *,_CmsRow const &,ulong,ulong,_SmsQuickIndex *,EmsPinRowFlags,unsigned __int64 *)
0x1400d0847  mov     edi, eax
0x1400d0849  test    eax, eax
0x1400d084b  js      short loc_1400D08C8
0x1400d084d  cmp     [rbp+8C0h+var_928], r12
0x1400d0851  jbe     short loc_1400D089D
0x1400d0853  mov     rcx, [r15+8]
0x1400d0857  lea     rax, [rbp+8C0h+var_930]
0x1400d085b  mov     [rsp+9C0h+var_970], rax
0x1400d0860  lea     r8, [rsp+9C0h+var_978]
0x1400d0865  lea     rax, [rbp+8C0h+var_930]
0x1400d0869  mov     [rsp+9C0h+var_988], r12
0x1400d086e  mov     r9d, 32h ; '2'
0x1400d0874  mov     [rsp+9C0h+var_960], rax
0x1400d0879  mov     rdx, rsi
0x1400d087c  mov     [rsp+9C0h+var_978], 10h
0x1400d0885  mov     [rsp+9C0h+var_968], 20h ; ' '
0x1400d088d  mov     [rsp+9C0h+var_998], r12
0x1400d0892  call    ?InsertRow@CmsTable@@QEAAJPEAVCmsTransactionContext@@AEBU_CmsRow@@KKPEAU_SmsQuickIndex@@W4EmsPinRowFlags@@PEA_K@Z; CmsTable::InsertRow(CmsTransactionContext *,_CmsRow const &,ulong,ulong,_SmsQuickIndex *,EmsPinRowFlags,unsigned __int64 *)
0x1400d0897  mov     edi, eax
0x1400d0899  test    eax, eax
0x1400d089b  js      short loc_1400D08C8
0x1400d089d  mov     rcx, [r15]; this
0x1400d08a0  lea     r8, [rbp+8C0h+var_898]; struct _SmsTopLevelAction *
0x1400d08a4  xor     r9d, r9d; unsigned __int8
0x1400d08a7  mov     rdx, rsi; struct CmsTransactionContext *
0x1400d08aa  call    ?CommitTopLevelAction@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@E@Z; CmsVolume::CommitTopLevelAction(CmsTransactionContext *,_SmsTopLevelAction *,uchar)
0x1400d08af  test    byte ptr [r13+32h], 4
0x1400d08b4  mov     [rsp+9C0h+var_980], r12b
0x1400d08b9  jz      short loc_1400D08C8
0x1400d08bb  nop
0x1400d08bc  mov     eax, 0FFFFFFFBh
0x1400d08c1  lock and [r13+32h], ax
0x1400d08c7  nop
0x1400d08c8  mov     r8, [rbp+8C0h+var_900]; struct SmsPage *
0x1400d08cc  test    r8, r8
0x1400d08cf  jz      loc_1400D0988
0x1400d08d5  mov     r12, [rsi+8]
0x1400d08d9  mov     r9d, 3; unsigned int
0x1400d08df  mov     r11, [r8+130h]
0x1400d08e6  xor     r14d, r14d
0x1400d08e9  mov     ebx, r9d
0x1400d08ec  test    r11, r11
0x1400d08ef  jz      short loc_1400D0963
0x1400d08f1  lea     rdx, [r8+138h]
0x1400d08f8  test    r9b, 1
0x1400d08fc  jz      short loc_1400D092B
0x1400d08fe  mov     r10d, [rdx]
0x1400d0901  cmp     [r8+180h], r10d
0x1400d0908  jnz     short loc_1400D092B
0x1400d090a  lea     rcx, [r8+13Ch]
0x1400d0911  mov     r14, r11
0x1400d0914  bt      r9d, 2
0x1400d0919  jnb     short loc_1400D094E
0x1400d091b  mov     eax, [rcx]
0x1400d091d  cmp     [r8+184h], eax
0x1400d0924  jz      short loc_1400D094A
0x1400d0926  and     ebx, 0FFFFFFFBh
0x1400d0929  jmp     short loc_1400D094E
0x1400d092b  bt      r9d, 2
0x1400d0930  jnb     short loc_1400D0963
0x1400d0932  lea     rcx, [r8+13Ch]
0x1400d0939  mov     eax, [rcx]
0x1400d093b  cmp     [r8+184h], eax
0x1400d0942  jnz     short loc_1400D0963
0x1400d0944  mov     r10d, [rdx]
0x1400d0947  mov     r14, r11
0x1400d094a  dec     eax
0x1400d094c  mov     [rcx], eax
0x1400d094e  lea     eax, [r10-1]
0x1400d0952  mov     [rdx], eax
0x1400d0954  test    eax, eax
0x1400d0956  jnz     short loc_1400D0963
0x1400d0958  mov     qword ptr [r8+130h], 0
0x1400d0963  mov     rdx, rsi; struct CmsTransactionCore *
0x1400d0966  mov     rcx, r12; this
0x1400d0969  call    ?UnpinInternal@CmsVolume@@AEAAXPEAVCmsTransactionCore@@PEAUSmsPage@@K@Z; CmsVolume::UnpinInternal(CmsTransactionCore *,SmsPage *,ulong)
0x1400d096e  mov     r8, r14
0x1400d0971  mov     r9d, ebx
0x1400d0974  test    r14, r14
0x1400d0977  jnz     loc_1400D08DF
0x1400d097d  mov     r13, [rbp+8C0h+var_8D8]
0x1400d0981  xor     r12d, r12d
0x1400d0984  mov     [rbp+8C0h+var_900], r12
0x1400d0988  mov     rcx, [rbp+8C0h+var_8D0]
0x1400d098c  cmp     qword ptr [rcx], 10h
0x1400d0990  jb      short loc_1400D09A0
0x1400d0992  call    cs:__imp_RtlReleaseSRWLockShared
  ... truncated ...
```
