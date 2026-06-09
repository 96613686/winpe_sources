# CmsVolumeContainer::DeleteContainer(CmsTransactionContext *,unsigned __int64)

- ea: `0x1400c3ac0`
- end: `0x1400c3fb3`
- name: `?DeleteContainer@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_K@Z`
- size: `1267`
- prototype: `__int64 __fastcall(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, unsigned __int64)`
- caller_count: `2`
- callee_count: `25`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400c0f98`
- `0x1400c665c`

## callees

- `0x140004870`
- `0x14007e584`
- `0x14007e594`
- `0x14007e5a4`
- `0x1400838b4`
- `0x14008c618`
- `0x14008c930`
- `0x14008d430`
- `0x14008e220`
- `0x140095090`
- `0x1400a8c50`
- `0x1400aca98`
- `0x1400c14dc`
- `0x1400c1db0`
- `0x1400c1e1c`
- `0x1400c3ac0`
- `0x1400c3fbc`
- `0x1400c4790`
- `0x1400c47c8`
- `0x1400c70a8`
- `0x1400c8b24`
- `0x1400cce70`
- `0x1400ccee0`
- `0x1400ccfa0`
- `0x1400f233c`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x1400c3e64`
- `ntdll!RtlRemoveEntryHashTable` at `0x1400c3e64`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400c3b96`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400c3b96`

## pseudocode

```c
__int64 __fastcall CmsVolumeContainer::DeleteContainer(CmsBPlusTable **this, CmsVolume **a2, unsigned __int64 a3)
{
  unsigned __int64 v5; // r11
  int ContainerReference; // eax
  struct CmsTransactionContext *v7; // rdx
  CmsVolumeContainer *v8; // rcx
  struct SmsContainer *v9; // rbx
  int v10; // edi
  char v11; // di
  CmsVolumeContainer *v12; // rcx
  __int64 v13; // rdx
  struct SmsContainer *v14; // rdx
  unsigned __int16 i; // r15
  __int64 v16; // rax
  __int64 v17; // r12
  CmsBPlusTable *v18; // rcx
  __int128 v19; // xmm0
  CmsBPlusTable *v20; // rcx
  __int128 v21; // xmm0
  int ContainerRangesCountFromContainerEntry; // eax
  unsigned __int8 v23; // r9
  struct SmsContainer *v24; // r13
  unsigned int j; // r15d
  CmsBPlusTable *v26; // rcx
  __int128 v27; // xmm0
  struct CmsTransactionContext *v28; // rdx
  CmsVolumeHeatEngine *v29; // rcx
  __int64 v30; // rax
  CmsVolumeContainer *k; // rcx
  __int64 v32; // rdx
  unsigned __int16 m; // r14
  __int64 v34; // r8
  CmsVolume *v35; // rcx
  unsigned int v36; // edx
  CmsVolumeContainer *v37; // rcx
  unsigned int v39; // [rsp+48h] [rbp-91h]
  __int128 v40; // [rsp+60h] [rbp-79h] BYREF
  struct SmsContainer *v41; // [rsp+70h] [rbp-69h] BYREF
  unsigned __int64 v42; // [rsp+78h] [rbp-61h]
  __int64 v43; // [rsp+80h] [rbp-59h]
  _BYTE v44[24]; // [rsp+88h] [rbp-51h] BYREF
  __int16 v45; // [rsp+A0h] [rbp-39h]
  char v46; // [rsp+A2h] [rbp-37h]
  int v47; // [rsp+B0h] [rbp-29h]
  __int128 v48; // [rsp+C0h] [rbp-19h] BYREF
  _OWORD v49[2]; // [rsp+D0h] [rbp-9h] BYREF

  v42 = a3;
  v45 = 0;
  memset(v49, 0, sizeof(v49));
  v46 = 0;
  v47 = 0;
  CmsVolume::BeginTopLevelActionInternal(this, a2, v44);
  v43 = operator|(0x4000, 0x4000000);
  operator|=(a2, v43);
  v41 = 0;
  ContainerReference = CmsVolumeContainer::GetContainerReference(
                         (CmsVolumeContainer *)this,
                         (struct CmsTransactionContext *)a2,
                         v5,
                         &v41,
                         0,
                         1u);
  v9 = v41;
  v10 = ContainerReference;
  if ( ContainerReference >= 0 )
  {
    v11 = 10;
    while ( !CmsVolumeContainer::TryLockContainerExclusive(v8, v7, v9) )
    {
      if ( !--v11 )
      {
        CmsVolumeContainer::ReleaseContainerReference(v12, (struct CmsTransactionContext *)a2, v9);
        v9 = 0;
        v10 = -1073739772;
        goto LABEL_34;
      }
      Sleep(0xAu);
    }
    if ( *((int *)v9 + 22) > 1 )
    {
      v10 = -1073741253;
      goto LABEL_34;
    }
    v13 = (unsigned int)(16 * *((_DWORD *)this + 95)) + 672LL;
    *(_QWORD *)&v48 = *((_QWORD *)v9 + 74);
    v14 = (struct SmsContainer *)((char *)v9 + v13);
    v41 = v14;
    for ( i = 0; (unsigned int)i < *((_DWORD *)v9 + 167); ++i )
    {
      v10 = CmsVolumeContainer::PinContainer(
              (CmsVolumeContainer *)this,
              (struct CmsTransactionContext *)a2,
              *((_QWORD *)v14 + 2 * i) >> ((unsigned __int8)*((_DWORD *)this[1] + 20) + 1),
              (struct SmsContainer **)v49 + i,
              0,
              0);
      if ( v10 < 0 )
        goto LABEL_34;
      v16 = *((_QWORD *)v49 + i);
      *(_BYTE *)(v16 + 24) |= 1u;
      _InterlockedAdd16((volatile signed __int16 *)(v16 + 648), 0xFFFFu);
      v14 = v41;
    }
    v17 = v48;
    v18 = this[8];
    *(_QWORD *)&v40 = v48;
    *((_QWORD *)&v40 + 1) = 0x300000000LL;
    v19 = v40;
    WORD2(v40) = 0;
    *((_QWORD *)&v40 + 1) = &v48;
    v48 = v19;
    LODWORD(v40) = 16;
    v10 = CmsTable::DeleteRow(v18, a2, &v40);
    if ( (int)(v10 + 0x80000000) < 0 || v10 == -1073741772 )
    {
      v20 = this[8];
      *(_QWORD *)&v40 = v17;
      *((_QWORD *)&v40 + 1) = 0x500000000LL;
      v21 = v40;
      WORD2(v40) = 0;
      *((_QWORD *)&v40 + 1) = &v48;
      v48 = v21;
      LODWORD(v40) = 16;
      v10 = CmsTable::DeleteRow(v20, a2, &v40);
      if ( (int)(v10 + 0x80000000) < 0 || v10 == -1073741772 )
      {
        if ( (*((_BYTE *)v9 + 612) & 2) != 0 )
        {
          v10 = CmsVolumeContainer::DeleteContainerCompressionHeaders(
                  (CmsVolumeContainer *)this,
                  (struct CmsTransactionContext *)a2,
                  v9);
          if ( (int)(v10 + 0x80000000) >= 0 && v10 != -1073741772 )
            goto LABEL_34;
          ContainerRangesCountFromContainerEntry = CmsVolumeContainer::GetContainerRangesCountFromContainerEntry(
                                                     (CmsVolumeContainer *)this,
                                                     (struct SmsContainer *)((char *)v9 + 592));
          v10 = CmsVolumeContainer::AdjustCompressedContainerCounts(
                  (CmsVolumeContainer *)this,
                  (struct CmsTransactionContext *)a2,
                  -1,
                  -*((_DWORD *)v9 + 157),
                  -*((_DWORD *)v9 + 156),
                  -ContainerRangesCountFromContainerEntry);
          if ( v10 < 0 )
            goto LABEL_34;
          if ( (*((_BYTE *)v9 + 612) & 2) != 0 )
          {
            v24 = v41;
            for ( j = 0; j < *((_DWORD *)v9 + 167); ++j )
            {
              v10 = CmsBPlusTable::AddToDeleteQueue(
                      this[8],
                      (struct CmsTransactionContext *)a2,
                      (struct SmsContainer *)((char *)v24 + 16 * j),
                      v23,
                      0,
                      0,
                      0,
                      0,
                      0,
                      v39,
                      0);
              if ( v10 < 0 )
                goto LABEL_34;
            }
          }
        }
        v26 = this[2];
        *(_QWORD *)&v40 = v17;
        *((_QWORD *)&v40 + 1) = 0x100000000LL;
        v27 = v40;
        WORD2(v40) = 0;
        *((_QWORD *)&v40 + 1) = &v48;
        v48 = v27;
        LODWORD(v40) = 16;
        v10 = CmsTable::DeleteRow(v26, a2, &v40);
        if ( (int)(v10 + 0x80000000) < 0 || v10 == -1073741772 )
        {
          SmsPushLockNoDtor::LockExclusive((SmsPushLockNoDtor *)(this + 7));
          if ( *((_DWORD *)v9 + 22) == 1 )
          {
            v10 = 0;
            RtlRemoveEntryHashTable(this[6], v9, 0);
            SmsPushLockNoDtor::UnlockExclusive((SmsPushLockNoDtor *)(this + 7));
            v29 = (CmsVolumeHeatEngine *)*((_QWORD *)this[1] + 400);
            if ( v29 )
              CmsVolumeHeatEngine::RemoveContainerIfTracked(v29, v28, v9, 0);
            if ( (*((_DWORD *)v9 + 153) & 0x800) == 0 )
              CmsVolumeContainer::AddUnusedContainerIdForReusage((CmsVolumeContainer *)this, v28, v42);
          }
          else
          {
            v10 = -1073741253;
            SmsPushLockNoDtor::UnlockExclusive((SmsPushLockNoDtor *)(this + 7));
          }
        }
      }
    }
  }
LABEL_34:
  v30 = operator~(v43);
  operator&=(a2, v30);
  if ( v9 )
  {
    if ( v10 < 0 )
    {
      for ( k = 0; (unsigned int)(unsigned __int16)k < *((_DWORD *)v9 + 167); LOWORD(k) = (_WORD)k + 1 )
      {
        v32 = *((_QWORD *)v49 + (unsigned __int16)k);
        if ( v32 )
          _InterlockedAdd16((volatile signed __int16 *)(v32 + 648), 1u);
      }
    }
    for ( m = 0; (unsigned int)m < *((_DWORD *)v9 + 167); ++m )
    {
      v34 = *((_QWORD *)v49 + m);
      if ( v34 )
        CmsVolumeContainer::UnpinContainer(k, (struct CmsTransactionContext *)a2, *(_QWORD *)(v34 + 592), 0);
    }
  }
  v35 = a2[1];
  if ( v10 < 0 )
    CmsVolume::AbortTopLevelAction(v35, (struct CmsTransactionContext *)a2, (struct _SmsTopLevelAction *)v44);
  else
    CmsVolume::CommitTopLevelAction(v35, (struct CmsTransactionContext *)a2, (struct _SmsTopLevelAction *)v44, 0);
  if ( v9 )
    CmsVolumeContainer::UnpinContainerExclusive(v37, (struct CmsTransactionContext *)a2, v9);
  if ( v10 >= 0 && v9 )
    SmsContainer::`scalar deleting destructor'(v9, v36);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400c3ac0  mov     [rsp-8+arg_18], rbx
0x1400c3ac5  push    rbp
0x1400c3ac6  push    rsi
0x1400c3ac7  push    rdi
0x1400c3ac8  push    r12
0x1400c3aca  push    r13
0x1400c3acc  push    r14
0x1400c3ace  push    r15
0x1400c3ad0  lea     rbp, [rsp-27h]
0x1400c3ad5  sub     rsp, 100h
0x1400c3adc  mov     rax, cs:__security_cookie
0x1400c3ae3  xor     rax, rsp
0x1400c3ae6  mov     [rbp+57h+var_40], rax
0x1400c3aea  mov     r11, r8
0x1400c3aed  mov     [rbp+57h+var_B8], r8
0x1400c3af1  xorps   xmm0, xmm0
0x1400c3af4  mov     [rsp+130h+var_108], 0
0x1400c3af9  lea     r8, [rbp+57h+var_A8]
0x1400c3afd  mov     [rbp+57h+var_90], 0
0x1400c3b03  movups  [rbp+57h+var_60], xmm0
0x1400c3b07  mov     rsi, rdx
0x1400c3b0a  mov     r14, rcx
0x1400c3b0d  movups  [rbp+57h+var_50], xmm0
0x1400c3b11  mov     [rbp+57h+var_8E], 0
0x1400c3b15  mov     [rbp+57h+var_80], 0
0x1400c3b1c  mov     byte ptr [rsp+130h+var_110], 0
0x1400c3b21  call    ?BeginTopLevelActionInternal@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@EEW4FoldOnlyTla@@@Z; CmsVolume::BeginTopLevelActionInternal(CmsTransactionContext *,_SmsTopLevelAction *,uchar,uchar,FoldOnlyTla)
0x1400c3b26  mov     ecx, 4000h
0x1400c3b2b  mov     edx, 4000000h
0x1400c3b30  call    ??U@YA?AW4EmsTransactionFlags@@W40@0@Z; operator|(EmsTransactionFlags,EmsTransactionFlags)
0x1400c3b35  mov     rdx, rax
0x1400c3b38  mov     [rbp+57h+var_B0], rax
0x1400c3b3c  mov     rcx, rsi
0x1400c3b3f  call    ??_5@YAAEAW4EmsTransactionFlags@@AEAW40@W40@@Z; operator|=(EmsTransactionFlags &,EmsTransactionFlags)
0x1400c3b44  mov     r12d, 1
0x1400c3b4a  mov     [rbp+57h+var_C0], 0
0x1400c3b52  mov     [rsp+130h+var_108], r12b; unsigned __int8
0x1400c3b57  lea     r9, [rbp+57h+var_C0]; struct SmsContainer **
0x1400c3b5b  mov     r8, r11; unsigned __int64
0x1400c3b5e  mov     byte ptr [rsp+130h+var_110], 0; char
0x1400c3b63  mov     rdx, rsi; struct CmsTransactionContext *
0x1400c3b66  mov     rcx, r14; this
0x1400c3b69  call    ?GetContainerReference@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@EE@Z; CmsVolumeContainer::GetContainerReference(CmsTransactionContext *,unsigned __int64,SmsContainer * *,uchar,uchar)
0x1400c3b6e  mov     rbx, [rbp+57h+var_C0]
0x1400c3b72  mov     edi, eax
0x1400c3b74  test    eax, eax
0x1400c3b76  js      loc_1400C3EC2
0x1400c3b7c  mov     dil, 0Ah
0x1400c3b7f  mov     r8, rbx; struct SmsContainer *
0x1400c3b82  call    ?TryLockContainerExclusive@CmsVolumeContainer@@AEAAEPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::TryLockContainerExclusive(CmsTransactionContext *,SmsContainer *)
0x1400c3b87  test    al, al
0x1400c3b89  jnz     short loc_1400C3BBB
0x1400c3b8b  add     dil, 0FFh
0x1400c3b8f  jz      short loc_1400C3BA4
0x1400c3b91  mov     ecx, 0Ah; dwMilliseconds
0x1400c3b96  call    cs:__imp_Sleep
0x1400c3b9d  nop     dword ptr [rax+rax+00h]
0x1400c3ba2  jmp     short loc_1400C3B7F
0x1400c3ba4  mov     r8, rbx; struct SmsContainer *
0x1400c3ba7  mov     rdx, rsi; struct CmsTransactionContext *
0x1400c3baa  call    ?ReleaseContainerReference@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::ReleaseContainerReference(CmsTransactionContext *,SmsContainer *)
0x1400c3baf  xor     ebx, ebx
0x1400c3bb1  mov     edi, 0C0000804h
0x1400c3bb6  jmp     loc_1400C3EC2
0x1400c3bbb  cmp     [rbx+58h], r12d
0x1400c3bbf  jle     short loc_1400C3BCB
0x1400c3bc1  mov     edi, 0C000023Bh
0x1400c3bc6  jmp     loc_1400C3EC2
0x1400c3bcb  mov     edx, [r14+17Ch]
0x1400c3bd2  lea     r13, [rbx+250h]
0x1400c3bd9  mov     r12, [r13+0]
0x1400c3bdd  shl     edx, 4
0x1400c3be0  add     rdx, 2A0h
0x1400c3be7  mov     qword ptr [rbp+57h+var_70], r12
0x1400c3beb  add     rdx, rbx
0x1400c3bee  mov     [rbp+57h+var_C0], rdx
0x1400c3bf2  xor     r15d, r15d
0x1400c3bf5  movzx   eax, r15w
0x1400c3bf9  cmp     eax, [rbx+29Ch]
0x1400c3bff  jnb     short loc_1400C3C67
0x1400c3c01  mov     rax, [r14+8]
0x1400c3c05  lea     r12, [rbp+57h+var_60]
0x1400c3c09  movzx   r8d, r15w
0x1400c3c0d  mov     [rsp+130h+var_108], 0; unsigned __int8
0x1400c3c12  mov     [rsp+130h+var_110], 0; struct _SmsContainerOverflowPinList *
0x1400c3c1b  mov     ecx, [rax+50h]
0x1400c3c1e  lea     r12, [r12+r8*8]
0x1400c3c22  inc     ecx
0x1400c3c24  add     r8, r8
0x1400c3c27  mov     r9, r12; struct SmsContainer **
0x1400c3c2a  mov     r8, [rdx+r8*8]
0x1400c3c2e  mov     rdx, rsi; struct CmsTransactionContext *
0x1400c3c31  shr     r8, cl; unsigned __int64
0x1400c3c34  mov     rcx, r14; this
0x1400c3c37  call    ?PinContainer@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@PEAU_SmsContainerOverflowPinList@@E@Z; CmsVolumeContainer::PinContainer(CmsTransactionContext *,unsigned __int64,SmsContainer * *,_SmsContainerOverflowPinList *,uchar)
0x1400c3c3c  mov     edi, eax
0x1400c3c3e  test    eax, eax
0x1400c3c40  js      loc_1400C3EBC
0x1400c3c46  mov     rax, [r12]
0x1400c3c4a  mov     ecx, 1
0x1400c3c4f  or      [rax+18h], cl
0x1400c3c52  or      edx, 0FFFFFFFFh
0x1400c3c55  lock add [rax+288h], dx
0x1400c3c5d  mov     rdx, [rbp+57h+var_C0]
0x1400c3c61  add     r15w, cx
0x1400c3c65  jmp     short loc_1400C3BF5
0x1400c3c67  mov     r12, qword ptr [rbp+57h+var_70]
0x1400c3c6b  lea     r8, [rbp+57h+var_D0]
0x1400c3c6f  mov     rcx, [r14+40h]
0x1400c3c73  xor     eax, eax
0x1400c3c75  mov     qword ptr [rbp+57h+var_D0], r12
0x1400c3c79  mov     rdx, rsi
0x1400c3c7c  mov     dword ptr [rbp+57h+var_D0+8], 0
0x1400c3c83  mov     dword ptr [rbp+57h+var_D0+0Ch], 3
0x1400c3c8a  movaps  xmm0, [rbp+57h+var_D0]
0x1400c3c8e  mov     word ptr [rbp+57h+var_D0+4], ax
0x1400c3c92  lea     rax, [rbp+57h+var_70]
0x1400c3c96  mov     qword ptr [rbp+57h+var_D0+8], rax
0x1400c3c9a  movdqa  [rbp+57h+var_70], xmm0
0x1400c3c9f  mov     dword ptr [rbp+57h+var_D0], 10h
0x1400c3ca6  call    ?DeleteRow@CmsTable@@QEAAJPEAVCmsTransactionContext@@AEBU_CmsKey@@W4EmsPinRowFlags@@@Z; CmsTable::DeleteRow(CmsTransactionContext *,_CmsKey const &,EmsPinRowFlags)
0x1400c3cab  mov     ecx, 80000000h
0x1400c3cb0  mov     edi, eax
0x1400c3cb2  add     eax, ecx
0x1400c3cb4  mov     r15d, 0C0000034h
0x1400c3cba  test    ecx, eax
0x1400c3cbc  jnz     short loc_1400C3CC7
0x1400c3cbe  cmp     edi, r15d
0x1400c3cc1  jnz     loc_1400C3EBC
0x1400c3cc7  mov     rcx, [r14+40h]
0x1400c3ccb  lea     r8, [rbp+57h+var_D0]
0x1400c3ccf  mov     qword ptr [rbp+57h+var_D0], r12
0x1400c3cd3  xor     eax, eax
0x1400c3cd5  mov     dword ptr [rbp+57h+var_D0+8], 0
0x1400c3cdc  mov     rdx, rsi
0x1400c3cdf  mov     dword ptr [rbp+57h+var_D0+0Ch], 5
0x1400c3ce6  movaps  xmm0, [rbp+57h+var_D0]
0x1400c3cea  mov     word ptr [rbp+57h+var_D0+4], ax
0x1400c3cee  lea     rax, [rbp+57h+var_70]
0x1400c3cf2  mov     qword ptr [rbp+57h+var_D0+8], rax
0x1400c3cf6  movdqa  [rbp+57h+var_70], xmm0
0x1400c3cfb  mov     dword ptr [rbp+57h+var_D0], 10h
0x1400c3d02  call    ?DeleteRow@CmsTable@@QEAAJPEAVCmsTransactionContext@@AEBU_CmsKey@@W4EmsPinRowFlags@@@Z; CmsTable::DeleteRow(CmsTransactionContext *,_CmsKey const &,EmsPinRowFlags)
0x1400c3d07  mov     ecx, 80000000h
0x1400c3d0c  mov     edi, eax
0x1400c3d0e  add     eax, ecx
0x1400c3d10  test    ecx, eax
0x1400c3d12  jnz     short loc_1400C3D1D
0x1400c3d14  cmp     edi, r15d
0x1400c3d17  jnz     loc_1400C3EBC
0x1400c3d1d  test    byte ptr [rbx+264h], 2
0x1400c3d24  jz      loc_1400C3DF1
0x1400c3d2a  mov     r8, rbx; struct SmsContainer *
0x1400c3d2d  mov     rdx, rsi; struct CmsTransactionContext *
0x1400c3d30  mov     rcx, r14; this
0x1400c3d33  call    ?DeleteContainerCompressionHeaders@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::DeleteContainerCompressionHeaders(CmsTransactionContext *,SmsContainer *)
0x1400c3d38  mov     ecx, 80000000h
0x1400c3d3d  mov     edi, eax
0x1400c3d3f  add     eax, ecx
0x1400c3d41  test    ecx, eax
0x1400c3d43  jnz     short loc_1400C3D4E
0x1400c3d45  cmp     edi, r15d
0x1400c3d48  jnz     loc_1400C3EBC
0x1400c3d4e  mov     rdx, r13; struct _SmsContainerEntry *
0x1400c3d51  mov     rcx, r14; this
0x1400c3d54  call    ?GetContainerRangesCountFromContainerEntry@CmsVolumeContainer@@QEAA_KPEBU_SmsContainerEntry@@@Z; CmsVolumeContainer::GetContainerRangesCountFromContainerEntry(_SmsContainerEntry const *)
0x1400c3d59  mov     ecx, [rbx+270h]
0x1400c3d5f  neg     eax
0x1400c3d61  mov     r9d, [rbx+274h]
0x1400c3d68  neg     ecx
0x1400c3d6a  mov     dword ptr [rsp+130h+var_108], eax; int
0x1400c3d6e  neg     r9d; int
0x1400c3d71  mov     dword ptr [rsp+130h+var_110], ecx; int
0x1400c3d75  or      r8d, 0FFFFFFFFh; int
0x1400c3d79  mov     rcx, r14; this
0x1400c3d7c  mov     rdx, rsi; struct CmsTransactionContext *
0x1400c3d7f  call    ?AdjustCompressedContainerCounts@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@JJJJ@Z; CmsVolumeContainer::AdjustCompressedContainerCounts(CmsTransactionContext *,long,long,long,long)
0x1400c3d84  mov     edi, eax
0x1400c3d86  test    eax, eax
0x1400c3d88  js      loc_1400C3EBC
0x1400c3d8e  test    byte ptr [rbx+264h], 2
0x1400c3d95  jz      short loc_1400C3DF1
0x1400c3d97  mov     r13, [rbp+57h+var_C0]
0x1400c3d9b  xor     r15d, r15d
0x1400c3d9e  xor     eax, eax
0x1400c3da0  cmp     r15d, [rbx+29Ch]
0x1400c3da7  jnb     short loc_1400C3DEB
0x1400c3da9  mov     rcx, [r14+40h]; this
0x1400c3dad  mov     rdx, rsi; struct CmsTransactionContext *
0x1400c3db0  mov     [rsp+130h+var_E0], eax; unsigned int
0x1400c3db4  mov     [rsp+130h+var_F0], rax; struct SmsRun *
0x1400c3db9  mov     [rsp+130h+var_F8], rax; struct CmsStream *
0x1400c3dbe  mov     [rsp+130h+var_100], al; char
0x1400c3dc2  mov     [rsp+130h+var_108], al; char
0x1400c3dc6  mov     r8d, r15d
0x1400c3dc9  shl     r8, 4
0x1400c3dcd  add     r8, r13; struct _RANGE *
0x1400c3dd0  mov     [rsp+130h+var_110], rax; __int64 *
0x1400c3dd5  call    ?AddToDeleteQueue@CmsBPlusTable@@QEAAJPEAVCmsTransactionContext@@PEBU_RANGE@@EPEA_JEEPEAVCmsStream@@PEBUSmsRun@@KK@Z; CmsBPlusTable::AddToDeleteQueue(CmsTransactionContext *,_RANGE const *,uchar,__int64 *,uchar,uchar,CmsStream *,SmsRun const *,ulong,ulong)
0x1400c3dda  mov     edi, eax
0x1400c3ddc  xor     eax, eax
0x1400c3dde  test    edi, edi
0x1400c3de0  js      loc_1400C3EBC
0x1400c3de6  inc     r15d
0x1400c3de9  jmp     short loc_1400C3DA0
0x1400c3deb  mov     r15d, 0C0000034h
0x1400c3df1  mov     rcx, [r14+10h]
0x1400c3df5  lea     r8, [rbp+57h+var_D0]
0x1400c3df9  mov     qword ptr [rbp+57h+var_D0], r12
0x1400c3dfd  xor     eax, eax
0x1400c3dff  mov     dword ptr [rbp+57h+var_D0+8], 0
0x1400c3e06  mov     r12d, 1
0x1400c3e0c  mov     dword ptr [rbp+57h+var_D0+0Ch], r12d
0x1400c3e10  mov     rdx, rsi
0x1400c3e13  movaps  xmm0, [rbp+57h+var_D0]
0x1400c3e17  mov     word ptr [rbp+57h+var_D0+4], ax
0x1400c3e1b  lea     rax, [rbp+57h+var_70]
0x1400c3e1f  mov     qword ptr [rbp+57h+var_D0+8], rax
0x1400c3e23  movdqa  [rbp+57h+var_70], xmm0
0x1400c3e28  mov     dword ptr [rbp+57h+var_D0], 10h
0x1400c3e2f  call    ?DeleteRow@CmsTable@@QEAAJPEAVCmsTransactionContext@@AEBU_CmsKey@@W4EmsPinRowFlags@@@Z; CmsTable::DeleteRow(CmsTransactionContext *,_CmsKey const &,EmsPinRowFlags)
0x1400c3e34  mov     ecx, 80000000h
0x1400c3e39  mov     edi, eax
0x1400c3e3b  add     eax, ecx
0x1400c3e3d  test    ecx, eax
0x1400c3e3f  jnz     short loc_1400C3E46
0x1400c3e41  cmp     edi, r15d
0x1400c3e44  jnz     short loc_1400C3EC2
0x1400c3e46  lea     r15, [r14+38h]
0x1400c3e4a  mov     rcx, r15; this
0x1400c3e4d  call    ?LockExclusive@SmsPushLockNoDtor@@QEAAXXZ; SmsPushLockNoDtor::LockExclusive(void)
0x1400c3e52  cmp     [rbx+58h], r12d
0x1400c3e56  jnz     short loc_1400C3EAD
0x1400c3e58  mov     rcx, [r14+30h]
0x1400c3e5c  xor     r8d, r8d
0x1400c3e5f  mov     rdx, rbx
0x1400c3e62  xor     edi, edi
0x1400c3e64  call    cs:__imp_RtlRemoveEntryHashTable
0x1400c3e6b  nop     dword ptr [rax+rax+00h]
0x1400c3e70  mov     rcx, r15; this
0x1400c3e73  call    ?UnlockExclusive@SmsPushLockNoDtor@@QEAAXXZ; SmsPushLockNoDtor::UnlockExclusive(void)
0x1400c3e78  mov     rax, [r14+8]
0x1400c3e7c  mov     rcx, [rax+0C80h]; this
0x1400c3e83  test    rcx, rcx
0x1400c3e86  jz      short loc_1400C3E93
0x1400c3e88  xor     r9d, r9d; bool
0x1400c3e8b  mov     r8, rbx; struct SmsContainer *
0x1400c3e8e  call    ?RemoveContainerIfTracked@CmsVolumeHeatEngine@@QEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@_N@Z; CmsVolumeHeatEngine::RemoveContainerIfTracked(CmsTransactionContext *,SmsContainer *,bool)
0x1400c3e93  test    dword ptr [rbx+264h], 800h
0x1400c3e9d  jnz     short loc_1400C3EC2
0x1400c3e9f  mov     r8, [rbp+57h+var_B8]; unsigned __int64
0x1400c3ea3  mov     rcx, r14; this
0x1400c3ea6  call    ?AddUnusedContainerIdForReusage@CmsVolumeContainer@@AEAAXPEAVCmsTransactionContext@@_K@Z; CmsVolumeContainer::AddUnusedContainerIdForReusage(CmsTransactionContext *,unsigned __int64)
0x1400c3eab  jmp     short loc_1400C3EC2
0x1400c3ead  mov     rcx, r15; this
0x1400c3eb0  mov     edi, 0C000023Bh
0x1400c3eb5  call    ?UnlockExclusive@SmsPushLockNoDtor@@QEAAXXZ; SmsPushLockNoDtor::UnlockExclusive(void)
0x1400c3eba  jmp     short loc_1400C3EC2
0x1400c3ebc  mov     r12d, 1
0x1400c3ec2  mov     rcx, [rbp+57h+var_B0]
0x1400c3ec6  call    ??S@YA?AW4EmsTransactionFlags@@W40@@Z; operator~(EmsTransactionFlags)
0x1400c3ecb  mov     rdx, rax
0x1400c3ece  mov     rcx, rsi
0x1400c3ed1  call    ??_4@YAAEAW4EmsTransactionFlags@@AEAW40@W40@@Z; operator&=(EmsTransactionFlags &,EmsTransactionFlags)
0x1400c3ed6  test    rbx, rbx
0x1400c3ed9  jz      short loc_1400C3F4A
0x1400c3edb  test    edi, edi
0x1400c3edd  jns     short loc_1400C3F0E
0x1400c3edf  xor     ecx, ecx
0x1400c3ee1  cmp     [rbx+29Ch], ecx
0x1400c3ee7  jbe     short loc_1400C3F0E
0x1400c3ee9  movzx   eax, cx
0x1400c3eec  mov     rdx, qword ptr [rbp+rax*8+57h+var_60]
0x1400c3ef1  test    rdx, rdx
0x1400c3ef4  jz      short loc_1400C3EFF
0x1400c3ef6  lock add [rdx+288h], r12w
0x1400c3eff  add     cx, r12w; this
0x1400c3f03  movzx   eax, cx
0x1400c3f06  cmp     eax, [rbx+29Ch]
0x1400c3f0c  jb      short loc_1400C3EE9
0x1400c3f0e  xor     r14d, r14d
0x1400c3f11  cmp     [rbx+29Ch], r14d
0x1400c3f18  jbe     short loc_1400C3F4A
0x1400c3f1a  movzx   eax, r14w
0x1400c3f1e  mov     r8, qword ptr [rbp+rax*8+57h+var_60]
0x1400c3f23  test    r8, r8
0x1400c3f26  jz      short loc_1400C3F3A
0x1400c3f28  mov     r8, [r8+250h]; unsigned __int64
0x1400c3f2f  xor     r9d, r9d; struct _SmsContainerOverflowPinList *
0x1400c3f32  mov     rdx, rsi; struct CmsTransactionContext *
0x1400c3f35  call    ?UnpinContainer@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@_KPEAU_SmsContainerOverflowPinList@@@Z; CmsVolumeContainer::UnpinContainer(CmsTransactionContext *,unsigned __int64,_SmsContainerOverflowPinList *)
0x1400c3f3a  add     r14w, r12w
0x1400c3f3e  movzx   eax, r14w
0x1400c3f42  cmp     eax, [rbx+29Ch]
0x1400c3f48  jb      short loc_1400C3F1A
0x1400c3f4a  mov     rcx, [rsi+8]; this
0x1400c3f4e  lea     r8, [rbp+57h+var_A8]; struct _SmsTopLevelAction *
0x1400c3f52  mov     rdx, rsi; struct CmsTransactionContext *
0x1400c3f55  test    edi, edi
0x1400c3f57  js      short loc_1400C3F63
  ... truncated ...
```
