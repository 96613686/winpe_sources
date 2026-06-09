# CmsHashTable::DeleteAll<`CmsHashTable::DeleteAll(void)'::`2'::_lambda_1_>(CmsTransactionCore *,`CmsHashTable::DeleteAll(void)'::`2'::_lambda_1_ &&)

- ea: `0x140054558`
- end: `0x140054883`
- name: `??$DeleteAll@V_lambda_1_@?1??0CmsHashTable@@QEAAXXZ@@CmsHashTable@@QEAAXPEAVCmsTransactionCore@@$$QEAV_lambda_1_@?1??DeleteAll@0@QEAAXXZ@@Z`
- size: `811`
- prototype: `__int64 __fastcall(CmsHashTable *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14015250c`

## callees

- `0x140020450`
- `0x140021720`
- `0x140049050`
- `0x140053fe0`
- `0x140054558`
- `0x140055a30`
- `0x14008f270`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14005479a`
- `ntoskrnl!KeSetEvent` at `0x14005479a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400547ed`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400547ed`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400547fb`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400547fb`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140054821`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140054821`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400547c0`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400547c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054847`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054847`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140054744`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140054744`

## pseudocode

```c
__int64 __fastcall ___DeleteAll_V_lambda_1___1__0CmsHashTable__QEAAXXZ__CmsHashTable__QEAAXPEAVCmsTransactionCore____QEAV_lambda_1___1__DeleteAll_0_QEAAXXZ__Z(
        CmsHashTable *this,
        __int64 a2,
        struct SmsHashEntry *a3)
{
  int v3; // esi
  __int64 result; // rax
  unsigned int v6; // edx
  unsigned int v7; // r13d
  unsigned __int64 v8; // r15
  unsigned int v9; // edi
  struct SmsHashEntry *v10; // rbx
  signed __int64 v11; // rcx
  struct SmsHashEntry *v12; // rdx
  __int64 v13; // r15
  void *v14; // r12
  __int64 v15; // rax
  __int64 v17; // rax
  __int64 *v18; // rdi
  __int64 **v19; // rcx
  struct _KEVENT *v20; // rcx
  struct _SLIST_ENTRY *v21; // rdx
  __int64 v22; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v23; // rcx
  __int64 v24; // rcx
  struct _SmsHashLocation *v25; // [rsp+38h] [rbp-81h]
  struct SmsHashEntry **v26; // [rsp+40h] [rbp-79h]
  signed __int64 v27; // [rsp+50h] [rbp-69h] BYREF
  __int64 v28; // [rsp+58h] [rbp-61h]
  int v29; // [rsp+60h] [rbp-59h]
  int v30; // [rsp+64h] [rbp-55h]
  __int128 v31; // [rsp+68h] [rbp-51h] BYREF
  __int128 v32; // [rsp+78h] [rbp-41h]
  __int128 v33; // [rsp+88h] [rbp-31h] BYREF
  int v34; // [rsp+98h] [rbp-21h]
  __int64 v35; // [rsp+A0h] [rbp-19h]
  int v36; // [rsp+A8h] [rbp-11h] BYREF
  struct SmsHashEntry *v37; // [rsp+B0h] [rbp-9h]
  __int64 v38; // [rsp+B8h] [rbp-1h]
  __int64 v39; // [rsp+C0h] [rbp+7h]
  struct SmsHashEntry *v40; // [rsp+130h] [rbp+77h] BYREF

  v40 = a3;
  v33 = 0;
  v34 = 0;
  v3 = 0;
  v35 = 0;
  v31 = 0;
  v32 = 0;
  while ( 1 )
  {
    do
    {
      if ( v3 == 1 )
      {
        result = CmsHashTable::PinNextInIndex(
                   this,
                   0,
                   5u,
                   (struct _CmsRow *)&v33,
                   (struct _SmsQuickIndex *)&v31,
                   0,
                   0,
                   0xFFFFFFFF);
      }
      else
      {
        result = *((unsigned int *)this + 7);
        if ( !((_DWORD)result + *((_DWORD *)this + 3)) )
          return result;
        v25 = 0;
        v3 = 1;
        result = CmsHashTable::PinInIndex(this, 0, 0, 2, 0, &v33, &v31);
      }
    }
    while ( (_DWORD)result == -1073739772 );
    if ( (_DWORD)result )
      return result;
    v7 = DWORD2(v31);
    v8 = **((_QWORD **)&v33 + 1);
    v27 = 0;
    v30 = 0;
    v9 = v32;
    v28 = *((_QWORD *)&v31 + 1);
    v10 = (struct SmsHashEntry *)(16LL * HIDWORD(v31) + *((_QWORD *)this + 2 * DWORD2(v31)));
    v29 = v32;
    v37 = v10;
    v36 = 0;
    v38 = -2;
    v39 = -3;
    do
    {
      while ( 1 )
      {
        v11 = *(_QWORD *)v10;
        if ( (unsigned __int64)(*(_QWORD *)v10 + 3LL) > 1 )
          break;
        if ( !MsBackoff((struct _SmsBackoff *)&v36, v6) )
          SmsHashEntry::WaitExtended(v10);
      }
    }
    while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)v10, -2, v11) );
    v27 = v11;
    if ( v11 == -1 )
      v12 = (struct SmsHashEntry *)(*(_QWORD *)(*((_QWORD *)v10 + 1) + 8LL) + 16LL * v9);
    else
      v12 = v10;
    v40 = v10;
    if ( v12 )
    {
LABEL_19:
      v13 = *((_QWORD *)v12 + 1);
      v14 = 0;
      *((_QWORD *)v12 + 1) = 0;
      if ( v11 == -1 )
      {
        *(_QWORD *)v12 = 0;
        v15 = *((_QWORD *)v10 + 1);
        if ( (*(_DWORD *)(v15 + 4))-- != 1 )
          goto LABEL_23;
        v14 = (void *)*((_QWORD *)v10 + 1);
        *((_QWORD *)v10 + 1) = 0;
      }
      v11 = 0;
LABEL_23:
      if ( _InterlockedExchange64((volatile __int64 *)v10, v11) == -3 )
      {
        ExAcquirePushLockExclusiveEx(&qword_14026C3C0, 0);
        v17 = qword_14026C3C8;
        if ( (__int64 *)qword_14026C3C8 != &qword_14026C3C8 )
        {
          do
          {
            v18 = *(__int64 **)v17;
            if ( *(struct SmsHashEntry **)(v17 + 24) == v10 )
            {
              if ( v18[1] != v17 || (v19 = *(__int64 ***)(v17 + 8), *v19 != (__int64 *)v17) )
                __fastfail(3u);
              *v19 = v18;
              v18[1] = (__int64)v19;
              v20 = *(struct _KEVENT **)(v17 + 16);
              *(_QWORD *)v17 = 0;
              KeSetEvent(v20, 0, 0);
            }
            v17 = (__int64)v18;
          }
          while ( v18 != &qword_14026C3C8 );
        }
        ExReleasePushLockEx(&qword_14026C3C0, 0);
      }
      if ( v13 )
      {
        v21 = (struct _SLIST_ENTRY *)(v13 - 16);
        v22 = *(_QWORD *)(v13 - 16);
        if ( !v22 )
          goto LABEL_40;
        if ( *(_BYTE *)(v22 + 8) )
        {
          v23 = (struct _NPAGED_LOOKASIDE_LIST *)(v22 + 64);
          if ( *(_BYTE *)(v22 + 9) )
            ExFreeToNPagedLookasideList(v23, v21);
          else
            ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v23, v21);
          goto LABEL_41;
        }
        v24 = *(_QWORD *)(v22 + 88);
        if ( (int)v24 < *(_DWORD *)(v22 + 80) || SHIDWORD(v24) >= (int)v24 )
        {
          ExpInterlockedPushEntrySList((PSLIST_HEADER)(v22 + 64), v21);
          _InterlockedIncrement((volatile signed __int32 *)(v22 + 88));
        }
        else
        {
LABEL_40:
          operator delete((void *)(v13 - 16));
        }
      }
LABEL_41:
      if ( v14 )
        ExFreePoolWithTag(v14, 0);
      _InterlockedDecrement((volatile signed __int32 *)this + 4 * v7 + 3);
    }
    else
    {
      v12 = CmsHashTable::FindAndLockEntryInternal(
              this,
              v8,
              0,
              1u,
              *((_QWORD *)this + 2) != 0,
              (struct _SmsHashLocation *)&v27,
              &v40,
              v25,
              v26);
      if ( v12 )
      {
        v10 = v40;
        v7 = v28;
        v11 = v27;
        goto LABEL_19;
      }
    }
  }
}

```

## disassembly

```asm
0x140054558  mov     [rsp-8+arg_10], r8
0x14005455d  push    rbp
0x14005455e  push    rbx
0x14005455f  push    rsi
0x140054560  push    rdi
0x140054561  push    r12
0x140054563  push    r13
0x140054565  push    r14
0x140054567  push    r15
0x140054569  lea     rbp, [rsp-1Fh]
0x14005456e  sub     rsp, 0D8h
0x140054575  xorps   xmm0, xmm0
0x140054578  xor     edi, edi
0x14005457a  movups  [rbp+57h+var_88], xmm0
0x14005457e  mov     [rbp+57h+var_78], edi
0x140054581  mov     esi, edi
0x140054583  mov     [rbp+57h+var_70], rdi
0x140054587  mov     r14, rcx
0x14005458a  movups  [rbp+57h+var_A8], xmm0
0x14005458e  movups  [rbp+57h+var_98], xmm0
0x140054592  mov     r12, 0FFFFFFFFFFFFFFFEh
0x140054599  cmp     esi, 1
0x14005459c  jnz     short loc_1400545CD
0x14005459e  mov     dword ptr [rsp+110h+var_D8], 0FFFFFFFFh; unsigned int
0x1400545a6  lea     rax, [rbp+57h+var_A8]
0x1400545aa  mov     [rsp+110h+var_E0], rdi; void *
0x1400545af  lea     r9, [rbp+57h+var_88]; struct _CmsRow *
0x1400545b3  mov     [rsp+110h+var_E8], rdi; int (*)(struct CmsTransactionCore *, struct _CmsRow *, void *)
0x1400545b8  lea     r8d, [rsi+4]; unsigned int
0x1400545bc  xor     edx, edx; struct CmsTransactionCore *
0x1400545be  mov     [rsp+110h+var_F0], rax; struct _SmsQuickIndex *
0x1400545c3  mov     rcx, r14; this
0x1400545c6  call    ?PinNextInIndex@CmsHashTable@@QEAAJPEAVCmsTransactionCore@@KPEAU_CmsRow@@PEAU_SmsQuickIndex@@P6AJ01PEAX@Z3K@Z; CmsHashTable::PinNextInIndex(CmsTransactionCore *,ulong,_CmsRow *,_SmsQuickIndex *,long (*)(CmsTransactionCore *,_CmsRow *,void *),void *,ulong)
0x1400545cb  jmp     short loc_14005460F
0x1400545cd  mov     ecx, [r14+0Ch]
0x1400545d1  mov     eax, [r14+1Ch]
0x1400545d5  add     ecx, eax
0x1400545d7  jz      loc_14005486E
0x1400545dd  mov     [rsp+110h+var_D8], rdi; struct _SmsHashLocation *
0x1400545e2  lea     rax, [rbp+57h+var_A8]
0x1400545e6  mov     [rsp+110h+var_E0], rax
0x1400545eb  mov     esi, 1
0x1400545f0  lea     rax, [rbp+57h+var_88]
0x1400545f4  xor     r8d, r8d
0x1400545f7  mov     [rsp+110h+var_E8], rax
0x1400545fc  xor     edx, edx
0x1400545fe  mov     rcx, r14
0x140054601  mov     [rsp+110h+var_F0], rdi
0x140054606  lea     r9d, [rsi+1]
0x14005460a  call    ?PinInIndex@CmsHashTable@@QEAAJPEAVCmsTransactionCore@@_KW4EMS_SPECIAL_KEY@@P6AJ0PEAU_CmsRow@@PEAX@Z3PEAU_SmsQuickIndex@@4W4EmsHashTableFlags@@@Z; CmsHashTable::PinInIndex(CmsTransactionCore *,unsigned __int64,EMS_SPECIAL_KEY,long (*)(CmsTransactionCore *,_CmsRow *,void *),_CmsRow *,_SmsQuickIndex *,void *,EmsHashTableFlags)
0x14005460f  cmp     eax, 0C0000804h
0x140054614  jz      short loc_140054599
0x140054616  test    eax, eax
0x140054618  jnz     loc_14005486E
0x14005461e  mov     rax, qword ptr [rbp+57h+var_88+8]
0x140054622  mov     r13, qword ptr [rbp+57h+var_A8+8]
0x140054626  mov     ecx, dword ptr [rbp+57h+var_A8+0Ch]
0x140054629  mov     dword ptr [rbp+57h+var_B8+4], ecx
0x14005462c  mov     r15, [rax]
0x14005462f  shl     rcx, 4
0x140054633  mov     eax, r13d
0x140054636  add     rax, rax
0x140054639  mov     [rbp+57h+var_C0], rdi
0x14005463d  mov     [rbp+57h+var_AC], edi
0x140054640  mov     rdi, qword ptr [rbp+57h+var_98]
0x140054644  mov     dword ptr [rbp+57h+var_B8], r13d
0x140054648  mov     rbx, [r14+rax*8]
0x14005464c  add     rbx, rcx
0x14005464f  mov     [rbp+57h+var_B0], edi
0x140054652  xor     eax, eax
0x140054654  mov     [rbp+57h+var_60], rbx
0x140054658  mov     [rbp+57h+var_68], eax
0x14005465b  mov     [rbp+57h+var_58], r12
0x14005465f  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFDh
0x140054667  mov     rcx, [rbx]
0x14005466a  lea     rax, [rcx+3]
0x14005466e  cmp     rax, 1
0x140054672  jbe     short loc_14005469A
0x140054674  nop
0x140054675  mov     rax, rcx
0x140054678  lock cmpxchg [rbx], r12
0x14005467d  nop
0x14005467e  jnz     short loc_140054667
0x140054680  mov     [rbp+57h+var_C0], rcx
0x140054684  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140054688  jnz     short loc_1400546B1
0x14005468a  mov     rax, [rbx+8]
0x14005468e  mov     edx, edi
0x140054690  shl     rdx, 4
0x140054694  add     rdx, [rax+8]
0x140054698  jmp     short loc_1400546B4
0x14005469a  lea     rcx, [rbp+57h+var_68]; struct _SmsBackoff *
0x14005469e  call    ?MsBackoff@@YAEPEAU_SmsBackoff@@K@Z; MsBackoff(_SmsBackoff *,ulong)
0x1400546a3  test    al, al
0x1400546a5  jnz     short loc_140054667
0x1400546a7  mov     rcx, rbx; this
0x1400546aa  call    ?WaitExtended@SmsHashEntry@@AEAAXXZ; SmsHashEntry::WaitExtended(void)
0x1400546af  jmp     short loc_140054667
0x1400546b1  mov     rdx, rbx
0x1400546b4  xor     edi, edi
0x1400546b6  mov     [rbp+57h+arg_10], rbx
0x1400546ba  test    rdx, rdx
0x1400546bd  jnz     short loc_140054705
0x1400546bf  cmp     [r14+10h], rdi
0x1400546c3  lea     rcx, [rbp+57h+arg_10]
0x1400546c7  mov     [rsp+110h+var_E0], rcx; struct SmsHashEntry **
0x1400546cc  mov     r9b, 1; unsigned __int8
0x1400546cf  setnz   al
0x1400546d2  lea     rcx, [rbp+57h+var_C0]
0x1400546d6  mov     [rsp+110h+var_E8], rcx; struct _SmsHashLocation *
0x1400546db  xor     r8d, r8d; unsigned __int8
0x1400546de  mov     rcx, r14; this
0x1400546e1  mov     byte ptr [rsp+110h+var_F0], al; char
0x1400546e5  mov     rdx, r15; unsigned __int64
0x1400546e8  call    ?FindAndLockEntryInternal@CmsHashTable@@AEAAPEAUSmsHashEntry@@_KEEEPEAU_SmsHashLocation@@PEAPEAU2@12@Z; CmsHashTable::FindAndLockEntryInternal(unsigned __int64,uchar,uchar,uchar,_SmsHashLocation *,SmsHashEntry * *,_SmsHashLocation *,SmsHashEntry * *)
0x1400546ed  mov     rdx, rax
0x1400546f0  test    rax, rax
0x1400546f3  jz      loc_140054599
0x1400546f9  mov     rbx, [rbp+57h+arg_10]
0x1400546fd  mov     r13d, dword ptr [rbp+57h+var_B8]
0x140054701  mov     rcx, [rbp+57h+var_C0]
0x140054705  mov     r15, [rdx+8]
0x140054709  mov     r12, rdi
0x14005470c  mov     [rdx+8], rdi
0x140054710  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140054714  jnz     short loc_14005472B
0x140054716  mov     [rdx], rdi
0x140054719  mov     rax, [rbx+8]
0x14005471d  add     dword ptr [rax+4], 0FFFFFFFFh
0x140054721  jnz     short loc_14005472E
0x140054723  mov     r12, [rbx+8]
0x140054727  mov     [rbx+8], rdi
0x14005472b  mov     rcx, rdi
0x14005472e  xchg    rcx, [rbx]
0x140054731  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140054735  jnz     loc_1400547CC
0x14005473b  xor     edx, edx
0x14005473d  lea     rcx, qword_14026C3C0
0x140054744  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005474b  nop     dword ptr [rax+rax+00h]
0x140054750  mov     rax, cs:qword_14026C3C8
0x140054757  lea     rcx, qword_14026C3C8
0x14005475e  cmp     rax, rcx
0x140054761  jz      short loc_1400547B7
0x140054763  mov     rdi, [rax]
0x140054766  cmp     [rax+18h], rbx
0x14005476a  jnz     short loc_1400547AD
0x14005476c  cmp     [rdi+8], rax
0x140054770  jnz     loc_140054867
0x140054776  mov     rcx, [rax+8]
0x14005477a  cmp     [rcx], rax
0x14005477d  jnz     loc_140054867
0x140054783  mov     [rcx], rdi
0x140054786  xor     r8d, r8d; Wait
0x140054789  mov     [rdi+8], rcx
0x14005478d  xor     edx, edx; Increment
0x14005478f  mov     rcx, [rax+10h]; Event
0x140054793  mov     qword ptr [rax], 0
0x14005479a  call    cs:__imp_KeSetEvent
0x1400547a1  nop     dword ptr [rax+rax+00h]
0x1400547a6  lea     rcx, qword_14026C3C8
0x1400547ad  mov     rax, rdi
0x1400547b0  cmp     rdi, rcx
0x1400547b3  jnz     short loc_140054763
0x1400547b5  xor     edi, edi
0x1400547b7  xor     edx, edx
0x1400547b9  lea     rcx, qword_14026C3C0
0x1400547c0  call    cs:__imp_ExReleasePushLockEx
0x1400547c7  nop     dword ptr [rax+rax+00h]
0x1400547cc  test    r15, r15
0x1400547cf  jz      short loc_14005483D
0x1400547d1  lea     rdx, [r15-10h]; ListEntry
0x1400547d5  mov     rbx, [rdx]
0x1400547d8  test    rbx, rbx
0x1400547db  jz      short loc_140054835
0x1400547dd  cmp     [rbx+8], dil
0x1400547e1  jz      short loc_140054809
0x1400547e3  lea     rcx, [rbx+40h]; Lookaside
0x1400547e7  cmp     [rbx+9], dil
0x1400547eb  jz      short loc_1400547FB
0x1400547ed  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400547f4  nop     dword ptr [rax+rax+00h]
0x1400547f9  jmp     short loc_14005483D
0x1400547fb  call    cs:__imp_ExFreeToPagedLookasideList
0x140054802  nop     dword ptr [rax+rax+00h]
0x140054807  jmp     short loc_14005483D
0x140054809  mov     rcx, [rbx+58h]
0x14005480d  cmp     ecx, [rbx+50h]
0x140054810  jl      short loc_14005481D
0x140054812  mov     rax, rcx
0x140054815  sar     rax, 20h
0x140054819  cmp     eax, ecx
0x14005481b  jl      short loc_140054835
0x14005481d  lea     rcx, [rbx+40h]; ListHead
0x140054821  call    cs:__imp_ExpInterlockedPushEntrySList
0x140054828  nop     dword ptr [rax+rax+00h]
0x14005482d  nop
0x14005482e  lock inc dword ptr [rbx+58h]
0x140054832  nop
0x140054833  jmp     short loc_14005483D
0x140054835  mov     rcx, rdx; void *
0x140054838  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005483d  test    r12, r12
0x140054840  jz      short loc_140054853
0x140054842  xor     edx, edx; Tag
0x140054844  mov     rcx, r12; P
0x140054847  call    cs:__imp_ExFreePoolWithTag
0x14005484e  nop     dword ptr [rax+rax+00h]
0x140054853  nop
0x140054854  mov     eax, r13d
0x140054857  shl     rax, 4
0x14005485b  lock dec dword ptr [rax+r14+0Ch]
0x140054861  nop
0x140054862  jmp     loc_140054592
0x140054867  mov     ecx, 3
0x14005486c  int     29h; Win8: RtlFailFast(ecx)
0x14005486e  add     rsp, 0D8h
0x140054875  pop     r15
0x140054877  pop     r14
0x140054879  pop     r13
0x14005487b  pop     r12
0x14005487d  pop     rdi
0x14005487e  pop     rsi
0x14005487f  pop     rbx
0x140054880  pop     rbp
0x140054881  retn
```
