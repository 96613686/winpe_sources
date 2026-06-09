# CSyncChangeWrapper::Replace(CSyncChangeWrapper *,ISyncKnowledge *,uchar *)

- ea: `0x18006c5a4`
- end: `0x18006c97a`
- name: `?Replace@CSyncChangeWrapper@@QEAAJPEAV1@PEAUISyncKnowledge@@PEAE@Z`
- size: `982`
- prototype: `__int64 __fastcall(CSyncChangeWrapper *__hidden this, struct CSyncChangeWrapper *, struct ISyncKnowledge *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x1800338a0`
- `0x1800428f0`

## callees

- `0x18000e81c`
- `0x18001a038`
- `0x18001ae20`
- `0x18001fc38`
- `0x18002ebe8`
- `0x18003b3b0`
- `0x180066b18`
- `0x1800678a0`
- `0x18006a71c`
- `0x18006c0f0`
- `0x18006c5a4`
- `0x1800709c0`
- `0x180071f70`
- `0x180093270`
- `0x180094010`

## string_xrefs

- `0x18006c5fa`: `CSyncChangeWrapper::Replace`
- `0x18006c93f`: `CSyncChangeWrapper::Replace`

## pseudocode

```c
__int64 __fastcall CSyncChangeWrapper::Replace(
        CSyncChangeWrapper *this,
        struct CSyncChangeWrapper *a2,
        struct ISyncKnowledge *a3,
        unsigned __int8 *a4)
{
  struct ISyncKnowledge *v4; // r12
  IdParameterPair *v7; // rcx
  int WinnerItemIdInternal; // ebx
  unsigned int *v9; // r13
  unsigned __int8 **v10; // r14
  unsigned __int8 *v11; // rdx
  int v12; // ebx
  int v13; // eax
  __int64 v14; // rdx
  char *v15; // r15
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  char *v22; // rcx
  __int64 v23; // rbx
  CEnumSyncChangeUnitWrappers *v24; // r12
  unsigned int v25; // edx
  unsigned int *v26; // r9
  int v27; // eax
  CSyncChangeUnitWrapper *v28; // r15
  int v29; // ecx
  CEnumSyncChangeUnitWrappers *v31; // [rsp+30h] [rbp-48h] BYREF
  CSyncChangeUnitWrapper *v32; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int8 *v33; // [rsp+40h] [rbp-38h]
  __int128 v34; // [rsp+48h] [rbp-30h] BYREF
  __int128 v35; // [rsp+58h] [rbp-20h] BYREF

  v33 = a4;
  v4 = a3;
  *(_QWORD *)&v34 = a3;
  v7 = (IdParameterPair *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      111,
      WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      "CSyncChangeWrapper::Replace");
    v7 = (IdParameterPair *)WPP_GLOBAL_Control;
  }
  WinnerItemIdInternal = -2147467261;
  if ( a2 )
  {
    v9 = (unsigned int *)((char *)this + 168);
    *((_DWORD *)this + 45) = 0;
    *((_DWORD *)this + 42) &= 0xFFFFFFFA;
    v10 = (unsigned __int8 **)((char *)this + 448);
    v11 = (unsigned __int8 *)*((_QWORD *)this + 56);
    *((_QWORD *)this + 38) = 0;
    IdParameterPair::FreeId(v7, v11);
    v12 = *((_DWORD *)this + 42);
    *((_QWORD *)this + 56) = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
        "CSyncChangeWrapper::AddFlags");
    }
    if ( (v12 & 4) != 0 )
    {
      v13 = *((_DWORD *)a2 + 42);
      if ( (v13 & 2) != 0 )
      {
        v13 &= ~2u;
        *((_DWORD *)a2 + 42) = v13;
      }
      if ( (v13 & 1) != 0 )
        *((_DWORD *)a2 + 42) = v13 & 0xFFFFFFFE;
    }
    *((_DWORD *)a2 + 42) |= v12;
    WinnerItemIdInternal = CSyncChangeWrapper::Remap(
                             a2,
                             v4,
                             *((struct ISyncKnowledge **)this + 41),
                             *((unsigned __int8 **)this + 13),
                             0);
    if ( WinnerItemIdInternal >= 0 )
    {
      v14 = *((_QWORD *)this + 13);
      v15 = (char *)a2 + 8;
      v16 = *((_QWORD *)a2 + 1);
      v35 = 0;
      WinnerItemIdInternal = (*(__int64 (__fastcall **)(char *, __int64, __int128 *))(v16 + 48))(
                               (char *)a2 + 8,
                               v14,
                               &v35);
      if ( WinnerItemIdInternal >= 0 )
      {
        v31 = 0;
        v17 = CSyncChangeWrapper::CloneChangeUnitWrapperEnum(a2, &v31, this);
        WinnerItemIdInternal = v17;
        if ( v17 == -2147217393 )
        {
          v18 = *(_QWORD *)v15;
          v19 = *((_QWORD *)this + 13);
          v34 = 0;
          WinnerItemIdInternal = (*(__int64 (__fastcall **)(char *, __int64, __int128 *))(v18 + 40))(
                                   (char *)a2 + 8,
                                   v19,
                                   &v34);
          if ( WinnerItemIdInternal >= 0 )
          {
            v20 = *((_QWORD *)this + 25);
            *((_OWORD *)this + 7) = v34;
            if ( v20 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
              *((_QWORD *)this + 25) = 0;
            }
LABEL_35:
            WinnerItemIdInternal = (*(__int64 (__fastcall **)(char *, char *))(*(_QWORD *)v15 + 56LL))(
                                     v15,
                                     (char *)this + 168);
            if ( WinnerItemIdInternal >= 0 )
            {
              if ( (*v9 & 2) != 0 )
                *v9 = *v9 & 0xFFFFFFFC | 1;
              else
                *((_OWORD *)this + 9) = v35;
              v29 = *((_DWORD *)a2 + 76);
              *((_DWORD *)this + 76) = v29;
              *((_DWORD *)this + 77) = *((_DWORD *)a2 + 77);
              if ( !v29
                || (WinnerItemIdInternal = CSyncChangeWrapper::GetWinnerItemIdInternal(a2, v10),
                    WinnerItemIdInternal >= 0) )
              {
                WinnerItemIdInternal = CSyncChangeWrapper::Remap(a2, *((struct ISyncKnowledge **)this + 41), v4, v33, 0);
              }
            }
          }
        }
        else if ( v17 >= 0 )
        {
          v21 = *((_QWORD *)this + 25);
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          v22 = (char *)this + 208;
          if ( *((_DWORD *)this + 56) )
          {
            HashTable<unsigned char *,_SYNC_CHANGE_UNIT_EXCLUSION *,IdParameterPair *>::FreeHashTable(v22);
          }
          else
          {
            v23 = *((_QWORD *)this + 53) + 32LL;
            HashTable<unsigned char *,_SYNC_CHANGE_UNIT_EXCLUSION *,IdParameterPair *>::FreeHashTable(v22);
            *((_DWORD *)this + 52) = GetNextPrimeNumber(0xBu);
            *((_QWORD *)this + 29) = v23;
          }
          v24 = v31;
          WinnerItemIdInternal = (*(__int64 (__fastcall **)(CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v31 + 40LL))(v31);
          while ( WinnerItemIdInternal >= 0 )
          {
            v32 = 0;
            v27 = CEnumSyncChangeUnitWrappers::Next(v24, v25, &v32, v26);
            WinnerItemIdInternal = v27;
            if ( v27 == 1 )
            {
              *((_QWORD *)this + 25) = v24;
              v15 = (char *)a2 + 8;
              v4 = (struct ISyncKnowledge *)v34;
              v10 = (unsigned __int8 **)((char *)this + 448);
              *((_OWORD *)this + 7) = 0;
              *((_OWORD *)this + 8) = 0;
              goto LABEL_35;
            }
            v28 = v32;
            v31 = 0;
            if ( v27 >= 0 )
            {
              WinnerItemIdInternal = CSyncChangeUnitWrapper::GetChangeUnitIdInternal(v32, (unsigned __int8 **)&v31);
              if ( WinnerItemIdInternal >= 0 )
                WinnerItemIdInternal = HashTable<unsigned char *,CSyncChangeUnitWrapper *,IdParameterPair *>::AddItem(
                                         (char *)this + 208,
                                         &v31,
                                         &v32);
            }
            (*(void (__fastcall **)(CSyncChangeUnitWrapper *))(*(_QWORD *)v28 + 16LL))(v28);
            IdParameters::FreeId((unsigned __int8 *)v31);
          }
        }
      }
    }
    v7 = (IdParameterPair *)WPP_GLOBAL_Control;
  }
  if ( v7 != (IdParameterPair *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 && *((_BYTE *)v7 + 25) >= 5u )
    WPP_SF_sD(
      *((_QWORD *)v7 + 2),
      112,
      (unsigned int)WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      (unsigned int)"CSyncChangeWrapper::Replace",
      WinnerItemIdInternal);
  return (unsigned int)WinnerItemIdInternal;
}

```

## disassembly

```asm
0x18006c5a4  push    rbp
0x18006c5a6  push    rbx
0x18006c5a7  push    rsi
0x18006c5a8  push    rdi
0x18006c5a9  push    r12
0x18006c5ab  push    r13
0x18006c5ad  push    r14
0x18006c5af  push    r15
0x18006c5b1  mov     rbp, rsp
0x18006c5b4  sub     rsp, 78h
0x18006c5b8  mov     rax, cs:__security_cookie
0x18006c5bf  xor     rax, rsp
0x18006c5c2  mov     [rbp+var_10], rax
0x18006c5c6  mov     [rbp+var_38], r9
0x18006c5ca  mov     r12, r8
0x18006c5cd  mov     qword ptr [rbp+var_30], r8
0x18006c5d1  mov     rsi, rdx
0x18006c5d4  mov     rdi, rcx
0x18006c5d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c5de  lea     rax, WPP_GLOBAL_Control
0x18006c5e5  cmp     rcx, rax
0x18006c5e8  jz      short loc_18006C619
0x18006c5ea  test    byte ptr [rcx+1Ch], 8
0x18006c5ee  jz      short loc_18006C619
0x18006c5f0  cmp     byte ptr [rcx+19h], 5
0x18006c5f4  jb      short loc_18006C619
0x18006c5f6  mov     rcx, [rcx+10h]
0x18006c5fa  lea     r9, aCsyncchangewra_10; "CSyncChangeWrapper::Replace"
0x18006c601  mov     edx, 6Fh ; 'o'
0x18006c606  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x18006c60d  call    WPP_SF_s
0x18006c612  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18006c619  xor     r15d, r15d
0x18006c61c  mov     ebx, 80004003h
0x18006c621  test    rsi, rsi
0x18006c624  jz      loc_18006C923
0x18006c62a  lea     r13, [rdi+0A8h]
0x18006c631  mov     [rdi+0B4h], r15d
0x18006c638  and     dword ptr [r13+0], 0FFFFFFFAh
0x18006c63d  lea     r14, [rdi+1C0h]
0x18006c644  mov     rdx, [r14]; unsigned __int8 *
0x18006c647  mov     [rdi+130h], r15
0x18006c64e  call    ?FreeId@IdParameterPair@@QEBAXPEAE@Z; IdParameterPair::FreeId(uchar *)
0x18006c653  mov     ebx, [r13+0]
0x18006c657  mov     [r14], r15
0x18006c65a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c661  lea     rax, WPP_GLOBAL_Control
0x18006c668  cmp     rcx, rax
0x18006c66b  jz      short loc_18006C694
0x18006c66d  test    byte ptr [rcx+1Ch], 8
0x18006c671  jz      short loc_18006C694
0x18006c673  cmp     byte ptr [rcx+19h], 5
0x18006c677  jb      short loc_18006C694
0x18006c679  mov     rcx, [rcx+10h]
0x18006c67d  lea     edx, [r15+27h]
0x18006c681  lea     r9, aCsyncchangewra_4; "CSyncChangeWrapper::AddFlags"
0x18006c688  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x18006c68f  call    WPP_SF_s
0x18006c694  test    bl, 4
0x18006c697  jz      short loc_18006C6B9
0x18006c699  mov     eax, [rsi+0A8h]
0x18006c69f  test    al, 2
0x18006c6a1  jz      short loc_18006C6AC
0x18006c6a3  and     eax, 0FFFFFFFDh
0x18006c6a6  mov     [rsi+0A8h], eax
0x18006c6ac  test    al, 1
0x18006c6ae  jz      short loc_18006C6B9
0x18006c6b0  and     eax, 0FFFFFFFEh
0x18006c6b3  mov     [rsi+0A8h], eax
0x18006c6b9  or      [rsi+0A8h], ebx
0x18006c6bf  mov     rdx, r12; struct ISyncKnowledge *
0x18006c6c2  mov     r9, [rdi+68h]; unsigned __int8 *
0x18006c6c6  mov     rcx, rsi; this
0x18006c6c9  mov     r8, [rdi+148h]; struct ISyncKnowledge *
0x18006c6d0  mov     [rsp+78h+var_58], r15; struct CSyncChangeBatchWrapper *
0x18006c6d5  call    ?Remap@CSyncChangeWrapper@@QEAAJPEAUISyncKnowledge@@0PEAEPEAVCSyncChangeBatchWrapper@@@Z; CSyncChangeWrapper::Remap(ISyncKnowledge *,ISyncKnowledge *,uchar *,CSyncChangeBatchWrapper *)
0x18006c6da  mov     ebx, eax
0x18006c6dc  test    eax, eax
0x18006c6de  js      loc_18006C91C
0x18006c6e4  mov     rdx, [rdi+68h]
0x18006c6e8  lea     r15, [rsi+8]
0x18006c6ec  mov     rax, [r15]
0x18006c6ef  lea     r8, [rbp+var_20]
0x18006c6f3  xorps   xmm0, xmm0
0x18006c6f6  mov     rcx, r15
0x18006c6f9  movups  [rbp+var_20], xmm0
0x18006c6fd  mov     rax, [rax+30h]
0x18006c701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c706  mov     ebx, eax
0x18006c708  test    eax, eax
0x18006c70a  js      loc_18006C91C
0x18006c710  mov     r8, rdi; struct CSyncChangeWrapper *
0x18006c713  mov     [rbp+var_48], 0
0x18006c71b  lea     rdx, [rbp+var_48]; struct CEnumSyncChangeUnitWrappers **
0x18006c71f  mov     rcx, rsi; this
0x18006c722  call    ?CloneChangeUnitWrapperEnum@CSyncChangeWrapper@@QEAAJPEAPEAVCEnumSyncChangeUnitWrappers@@PEAV1@@Z; CSyncChangeWrapper::CloneChangeUnitWrapperEnum(CEnumSyncChangeUnitWrappers * *,CSyncChangeWrapper *)
0x18006c727  mov     ebx, eax
0x18006c729  cmp     eax, 8004100Fh
0x18006c72e  jnz     short loc_18006C78D
0x18006c730  mov     rax, [r15]
0x18006c733  lea     r8, [rbp+var_30]
0x18006c737  mov     rdx, [rdi+68h]
0x18006c73b  xorps   xmm0, xmm0
0x18006c73e  mov     rcx, r15
0x18006c741  movups  [rbp+var_30], xmm0
0x18006c745  mov     rax, [rax+28h]
0x18006c749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c74e  mov     ebx, eax
0x18006c750  test    eax, eax
0x18006c752  js      loc_18006C91C
0x18006c758  movups  xmm0, [rbp+var_30]
0x18006c75c  mov     rcx, [rdi+0C8h]
0x18006c763  movdqu  xmmword ptr [rdi+70h], xmm0
0x18006c768  test    rcx, rcx
0x18006c76b  jz      loc_18006C896
0x18006c771  mov     rax, [rcx]
0x18006c774  mov     rax, [rax+10h]
0x18006c778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c77d  mov     qword ptr [rdi+0C8h], 0
0x18006c788  jmp     loc_18006C896
0x18006c78d  test    eax, eax
0x18006c78f  js      loc_18006C91C
0x18006c795  mov     rcx, [rdi+0C8h]
0x18006c79c  test    rcx, rcx
0x18006c79f  jz      short loc_18006C7AD
0x18006c7a1  mov     rax, [rcx]
0x18006c7a4  mov     rax, [rax+10h]
0x18006c7a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c7ad  cmp     dword ptr [rdi+0E0h], 0
0x18006c7b4  lea     r14, [rdi+0D0h]
0x18006c7bb  mov     rcx, r14
0x18006c7be  jbe     short loc_18006C7C7
0x18006c7c0  call    ?FreeHashTable@?$HashTable@PEAEPEAU_SYNC_CHANGE_UNIT_EXCLUSION@@PEAUIdParameterPair@@@@AEAAXXZ; HashTable<uchar *,_SYNC_CHANGE_UNIT_EXCLUSION *,IdParameterPair *>::FreeHashTable(void)
0x18006c7c5  jmp     short loc_18006C7E8
0x18006c7c7  mov     rbx, [rdi+1A8h]
0x18006c7ce  add     rbx, 20h ; ' '
0x18006c7d2  call    ?FreeHashTable@?$HashTable@PEAEPEAU_SYNC_CHANGE_UNIT_EXCLUSION@@PEAUIdParameterPair@@@@AEAAXXZ; HashTable<uchar *,_SYNC_CHANGE_UNIT_EXCLUSION *,IdParameterPair *>::FreeHashTable(void)
0x18006c7d7  mov     ecx, 0Bh; unsigned int
0x18006c7dc  call    ?GetNextPrimeNumber@@YAKK@Z; GetNextPrimeNumber(ulong)
0x18006c7e1  mov     [r14], eax
0x18006c7e4  mov     [r14+18h], rbx
0x18006c7e8  mov     r12, [rbp+var_48]
0x18006c7ec  mov     rcx, r12
0x18006c7ef  mov     rax, [r12]
0x18006c7f3  mov     rax, [rax+28h]
0x18006c7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c7fc  mov     ebx, eax
0x18006c7fe  test    ebx, ebx
0x18006c800  js      loc_18006C91C
0x18006c806  lea     r8, [rbp+var_40]; struct CSyncChangeUnitWrapper **
0x18006c80a  mov     [rbp+var_40], 0
0x18006c812  mov     rcx, r12; this
0x18006c815  call    ?Next@CEnumSyncChangeUnitWrappers@@QEAAJKPEAPEAVCSyncChangeUnitWrapper@@PEAK@Z; CEnumSyncChangeUnitWrappers::Next(ulong,CSyncChangeUnitWrapper * *,ulong *)
0x18006c81a  mov     ebx, eax
0x18006c81c  cmp     eax, 1
0x18006c81f  jz      short loc_18006C86F
0x18006c821  mov     r15, [rbp+var_40]
0x18006c825  mov     [rbp+var_48], 0
0x18006c82d  test    eax, eax
0x18006c82f  js      short loc_18006C855
0x18006c831  lea     rdx, [rbp+var_48]; unsigned __int8 **
0x18006c835  mov     rcx, r15; this
0x18006c838  call    ?GetChangeUnitIdInternal@CSyncChangeUnitWrapper@@QEAAJPEAPEAE@Z; CSyncChangeUnitWrapper::GetChangeUnitIdInternal(uchar * *)
0x18006c83d  mov     ebx, eax
0x18006c83f  test    eax, eax
0x18006c841  js      short loc_18006C855
0x18006c843  lea     r8, [rbp+var_40]
0x18006c847  mov     rcx, r14
0x18006c84a  lea     rdx, [rbp+var_48]
0x18006c84e  call    ?AddItem@?$HashTable@PEAEPEAVCSyncChangeUnitWrapper@@PEAUIdParameterPair@@@@QEAAJAEBQEAEAEBQEAVCSyncChangeUnitWrapper@@@Z; HashTable<uchar *,CSyncChangeUnitWrapper *,IdParameterPair *>::AddItem(uchar * const &,CSyncChangeUnitWrapper * const &)
0x18006c853  mov     ebx, eax
0x18006c855  mov     rax, [r15]
0x18006c858  mov     rcx, r15
0x18006c85b  mov     rax, [rax+10h]
0x18006c85f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c864  mov     rcx, [rbp+var_48]; unsigned __int8 *
0x18006c868  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x18006c86d  jmp     short loc_18006C7FE
0x18006c86f  mov     [rdi+0C8h], r12
0x18006c876  lea     r15, [rsi+8]
0x18006c87a  mov     r12, qword ptr [rbp+var_30]
0x18006c87e  lea     r14, [rdi+1C0h]
0x18006c885  xorps   xmm0, xmm0
0x18006c888  xorps   xmm1, xmm1
0x18006c88b  movups  xmmword ptr [rdi+70h], xmm0
0x18006c88f  movups  xmmword ptr [rdi+80h], xmm1
0x18006c896  mov     rax, [r15]
0x18006c899  mov     rdx, r13
0x18006c89c  mov     rcx, r15
0x18006c89f  mov     rax, [rax+38h]
0x18006c8a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c8a8  mov     ebx, eax
0x18006c8aa  test    eax, eax
0x18006c8ac  js      short loc_18006C91C
0x18006c8ae  mov     eax, [r13+0]
0x18006c8b2  test    al, 2
0x18006c8b4  jz      short loc_18006C8C2
0x18006c8b6  and     eax, 0FFFFFFFDh
0x18006c8b9  or      eax, 1
0x18006c8bc  mov     [r13+0], eax
0x18006c8c0  jmp     short loc_18006C8CE
0x18006c8c2  movups  xmm0, [rbp+var_20]
0x18006c8c6  movdqu  xmmword ptr [rdi+90h], xmm0
0x18006c8ce  mov     ecx, [rsi+130h]
0x18006c8d4  mov     [rdi+130h], ecx
0x18006c8da  mov     eax, [rsi+134h]
0x18006c8e0  mov     [rdi+134h], eax
0x18006c8e6  test    ecx, ecx
0x18006c8e8  jz      short loc_18006C8FB
0x18006c8ea  mov     rdx, r14; unsigned __int8 **
0x18006c8ed  mov     rcx, rsi; this
0x18006c8f0  call    ?GetWinnerItemIdInternal@CSyncChangeWrapper@@QEAAJPEAPEAE@Z; CSyncChangeWrapper::GetWinnerItemIdInternal(uchar * *)
0x18006c8f5  mov     ebx, eax
0x18006c8f7  test    eax, eax
0x18006c8f9  js      short loc_18006C91C
0x18006c8fb  mov     r9, [rbp+var_38]; unsigned __int8 *
0x18006c8ff  mov     r8, r12; struct ISyncKnowledge *
0x18006c902  mov     rdx, [rdi+148h]; struct ISyncKnowledge *
0x18006c909  mov     rcx, rsi; this
0x18006c90c  mov     [rsp+78h+var_58], 0; struct CSyncChangeBatchWrapper *
0x18006c915  call    ?Remap@CSyncChangeWrapper@@QEAAJPEAUISyncKnowledge@@0PEAEPEAVCSyncChangeBatchWrapper@@@Z; CSyncChangeWrapper::Remap(ISyncKnowledge *,ISyncKnowledge *,uchar *,CSyncChangeBatchWrapper *)
0x18006c91a  mov     ebx, eax
0x18006c91c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c923  lea     rax, WPP_GLOBAL_Control
0x18006c92a  cmp     rcx, rax
0x18006c92d  jz      short loc_18006C95B
0x18006c92f  test    byte ptr [rcx+1Ch], 8
0x18006c933  jz      short loc_18006C95B
0x18006c935  cmp     byte ptr [rcx+19h], 5
0x18006c939  jb      short loc_18006C95B
0x18006c93b  mov     rcx, [rcx+10h]
0x18006c93f  lea     r9, aCsyncchangewra_10; "CSyncChangeWrapper::Replace"
0x18006c946  mov     edx, 70h ; 'p'
0x18006c94b  mov     dword ptr [rsp+78h+var_58], ebx
0x18006c94f  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x18006c956  call    WPP_SF_sD
0x18006c95b  mov     eax, ebx
0x18006c95d  mov     rcx, [rbp+var_10]
0x18006c961  xor     rcx, rsp; StackCookie
0x18006c964  call    __security_check_cookie
0x18006c969  add     rsp, 78h
0x18006c96d  pop     r15
0x18006c96f  pop     r14
0x18006c971  pop     r13
0x18006c973  pop     r12
0x18006c975  pop     rdi
0x18006c976  pop     rsi
0x18006c977  pop     rbx
0x18006c978  pop     rbp
0x18006c979  retn
```
