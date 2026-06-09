# RdpCacheMan::ProcessPendingImportOffer(IRdpPipeProtocol *)

- ea: `0x180040880`
- end: `0x180040fca`
- name: `?ProcessPendingImportOffer@RdpCacheMan@@UEAAJPEAVIRdpPipeProtocol@@@Z`
- size: `1866`
- prototype: `__int64 __fastcall(RdpCacheMan *__hidden this, struct IRdpPipeProtocol *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002aafc`
- `0x18002b14c`
- `0x180040880`
- `0x180077aa0`
- `0x180079724`
- `0x180079770`
- `0x18007a1d4`
- `0x18007a404`
- `0x18007f6f0`
- `0x18007f6fc`
- `0x180158180`
- `0x18019c010`

## import_xrefs

- `RDPBASE!?InsertEntry@Evict@@QEAAXPEAU_SCORE_ENTRY@@K@Z` at `0x180040aec`
- `RDPBASE!?InsertEntry@Evict@@QEAAXPEAU_SCORE_ENTRY@@K@Z` at `0x180040aec`
- `RDPBASE!?GetFreeEntry@Evict@@QEAAPEAU_SCORE_ENTRY@@XZ` at `0x180040a5e`
- `RDPBASE!?GetFreeEntry@Evict@@QEAAPEAU_SCORE_ENTRY@@XZ` at `0x180040a5e`

## string_xrefs

- `0x180040b89`: `IID_IRdpCacheMan`
- `0x180040c1e`: `IID_IRdpCacheMan`
- `0x180040d75`: `IID_IRdpCacheMan`
- `0x180040ed8`: `IID_IRdpCacheMan`
- `0x180040f3d`: `IID_IRdpCacheMan`
- `0x180040b7c`: `RdpCacheManError_ProcessPendingImportOfferCacheBucketInsertFail`
- `0x180040c59`: `pProtocol`
- `0x180040c14`: `RdpCacheManError_ProcessPendingImportOfferNullPointer`
- `0x180040d68`: `RdpCacheManError_ProcessPendingImportOfferAllocationFail`
- `0x180040ecb`: `RdpCacheManError_ProcessPendingImportOfferCacheImportReplyFail`
- `0x180040f30`: `RdpCacheManError_ProcessPendingImportOfferFlushCommandsFail`

## pseudocode

```c
__int64 __fastcall RdpCacheMan::ProcessPendingImportOffer(RdpCacheMan *this, struct IRdpPipeProtocol *a2)
{
  unsigned int v2; // esi
  int v3; // ebx
  _DWORD *v4; // r15
  unsigned __int64 v5; // r12
  __int64 v9; // rcx
  __int64 v10; // rbx
  PVOID *v11; // rcx
  int v12; // eax
  _WORD *v13; // rbx
  unsigned __int16 i; // r14
  __int64 v15; // rcx
  __int64 v16; // rdx
  struct _SCORE_ENTRY *FreeEntry; // rax
  struct _SCORE_ENTRY *v18; // r13
  __int64 v19; // r10
  __int64 v20; // rcx
  signed int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v31; // rdx
  unsigned int v32; // eax
  __int64 v33; // rdx
  signed int v34; // eax
  signed int v35; // eax
  unsigned int v36; // eax
  int v37; // [rsp+20h] [rbp-30h]
  __int64 v38; // [rsp+30h] [rbp-20h] BYREF
  _WORD *v39; // [rsp+38h] [rbp-18h]
  __int64 v40; // [rsp+40h] [rbp-10h]
  __int16 v41; // [rsp+90h] [rbp+40h] BYREF
  int v42; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v43; // [rsp+A8h] [rbp+58h]

  v2 = *((_DWORD *)this + 47);
  v3 = 0;
  v4 = 0;
  v5 = 0;
  if ( !v2 || *((_DWORD *)this + 45) != 1 )
    goto LABEL_2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      112,
      &WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids,
      CurrentThreadActivityIdPrefix,
      v2);
  }
  v38 = 0;
  if ( v2 >= 0xFFFF )
    v2 = 0xFFFF;
  if ( !a2 )
  {
    v3 = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
      "RdpCacheManError_ProcessPendingImportOfferNullPointer",
      (char *)0x97B,
      0x80004003,
      v37);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        113,
        (unsigned int)&WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids,
        v25,
        (__int64)"pProtocol");
    }
    goto LABEL_10;
  }
  v3 = (*(__int64 (__fastcall **)(struct IRdpPipeProtocol *, __int64 *))(*(_QWORD *)a2 + 136LL))(a2, &v38);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids, v26, v3);
    }
LABEL_10:
    v9 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    goto LABEL_2;
  }
  CTSCriticalSection::Lock((RdpCacheMan *)((char *)this + 24));
  v4 = (_DWORD *)*((_QWORD *)this + 24);
  *((_DWORD *)this + 47) = 0;
  *((_QWORD *)this + 24) = 0;
  if ( this != (RdpCacheMan *)-24LL )
    CTSCriticalSection::UnLock((RdpCacheMan *)((char *)this + 24));
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v27 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        115,
        (unsigned int)&WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids,
        v27,
        (__int64)"pEntries");
    }
    v3 = -2147467261;
    goto LABEL_10;
  }
  v10 = 0;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  do
  {
    if ( !*(_QWORD *)&v4[3 * v10] || (v12 = v4[3 * v10 + 2], (v12 & 3) != 0) || (unsigned int)(v12 - 4) > 0xFFFC )
    {
      if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x100) != 0 && *((_BYTE *)v11 + 25) >= 4u )
      {
        v28 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids, v28);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      v2 = 0;
    }
    v10 = (unsigned int)(v10 + 1);
  }
  while ( (unsigned int)v10 < v2 );
  v39 = operator new[](saturated_mul(v2, 2u));
  v13 = v39;
  if ( v39 )
  {
    for ( i = 0; ; ++i )
    {
      if ( (unsigned int)v5 >= v2 )
        goto LABEL_75;
      v15 = *((_QWORD *)this + 11);
      v16 = *(_QWORD *)&v4[3 * v5];
      v42 = 0;
      v40 = v16;
      if ( (*(int (__fastcall **)(__int64, __int64, int *, _QWORD))(*(_QWORD *)v15 + 24LL))(v15, v16, &v42, 0) >= 0 )
      {
        v13[i] = 0;
      }
      else
      {
        v43 = (unsigned int)(*((_DWORD *)this + 34) + v4[3 * v5 + 2] - 1) / *((_DWORD *)this + 34);
        if ( v43 > *((_DWORD *)this + 36) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v32 = RdpWppGetCurrentThreadActivityIdPrefix();
            v33 = 118;
            goto LABEL_70;
          }
LABEL_75:
          v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, _WORD *))(*(_QWORD *)v38 + 216LL))(v38, i, v13);
          v3 = v34;
          if ( v34 >= 0 )
          {
            v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 32LL))(v38);
            v3 = v35;
            if ( v35 >= 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v36 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Ddd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  123,
                  &WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids,
                  v36,
                  i,
                  v2);
              }
            }
            else
            {
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
                "RdpCacheManError_ProcessPendingImportOfferFlushCommandsFail",
                (char *)0x9CF,
                v35,
                v37);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v30 = RdpWppGetCurrentThreadActivityIdPrefix();
                v31 = 122;
                goto LABEL_65;
              }
            }
          }
          else
          {
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
              "RdpCacheManError_ProcessPendingImportOfferCacheImportReplyFail",
              (char *)0x9CB,
              v34,
              v37);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v30 = RdpWppGetCurrentThreadActivityIdPrefix();
              v31 = 121;
              goto LABEL_65;
            }
          }
LABEL_34:
          v23 = v38;
          if ( v38 )
          {
            v38 = 0;
            goto LABEL_31;
          }
          goto LABEL_32;
        }
        FreeEntry = Evict::GetFreeEntry(*((Evict **)this + 12));
        v18 = FreeEntry;
        if ( !FreeEntry )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v32 = RdpWppGetCurrentThreadActivityIdPrefix();
            v33 = 119;
LABEL_70:
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v33, &WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids, v32);
            goto LABEL_75;
          }
          goto LABEL_75;
        }
        v19 = v40;
        *(_QWORD *)FreeEntry = v40;
        *((_WORD *)FreeEntry + 9) = -1;
        *((_WORD *)FreeEntry + 4) = 0;
        *(_DWORD *)((char *)FreeEntry + 10) = -1;
        *(_DWORD *)((char *)FreeEntry + 14) = -1;
        *((_WORD *)FreeEntry + 10) = v43;
        v20 = *((_QWORD *)this + 11);
        v42 = ((unsigned __int64)FreeEntry - ***((_QWORD ***)this + 12))
            / *(unsigned int *)(**((_QWORD **)this + 12) + 12LL);
        v41 = 0;
        v21 = (*(__int64 (__fastcall **)(__int64, __int64, int *, __int16 *))(*(_QWORD *)v20 + 40LL))(
                v20,
                v19,
                &v42,
                &v41);
        v3 = v21;
        if ( v21 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
            "RdpCacheManError_ProcessPendingImportOfferCacheBucketInsertFail",
            (char *)0x9B8,
            v21,
            v37);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v30 = RdpWppGetCurrentThreadActivityIdPrefix();
            v31 = 120;
LABEL_65:
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v31,
              &WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids,
              v30,
              v3);
            goto LABEL_34;
          }
          goto LABEL_34;
        }
        *((_WORD *)v18 + 4) = v41;
        Evict::InsertEntry(*((Evict **)this + 12), v18, 0);
        *((_DWORD *)this + 36) -= v43;
        v13 = v39;
        v39[i] = v41 + 1;
        v22 = *((_QWORD *)this + 16);
        if ( v22 )
          (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v22 + 208LL))(v22, 0, v40, 0);
      }
      v5 = (unsigned int)(v5 + 1);
    }
  }
  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
    (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
    "RdpCacheManError_ProcessPendingImportOfferAllocationFail",
    (char *)0x997,
    0x80004003,
    v37);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      117,
      (unsigned int)&WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids,
      v29,
      (__int64)"UINT16");
  }
  v23 = v38;
  v3 = -2147024882;
  if ( v38 )
  {
    v38 = 0;
LABEL_31:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
LABEL_32:
  v5 = (unsigned __int64)v39;
LABEL_2:
  operator delete(v4);
  operator delete((void *)v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180040880  mov     [rsp-38h+arg_8], rbx
0x180040885  push    rbp
0x180040886  push    rsi
0x180040887  push    rdi
0x180040888  push    r12
0x18004088a  push    r13
0x18004088c  push    r14
0x18004088e  push    r15
0x180040890  mov     rbp, rsp
0x180040893  sub     rsp, 50h
0x180040897  mov     esi, [rcx+0BCh]
0x18004089d  xor     ebx, ebx
0x18004089f  xor     r15d, r15d
0x1800408a2  xor     r12d, r12d
0x1800408a5  mov     r14, rdx
0x1800408a8  mov     rdi, rcx
0x1800408ab  test    esi, esi
0x1800408ad  jnz     short loc_1800408D9
0x1800408af  mov     rcx, r15; Block
0x1800408b2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800408b7  mov     rcx, r12; Block
0x1800408ba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800408bf  mov     eax, ebx
0x1800408c1  mov     rbx, [rsp+50h+arg_8]
0x1800408c9  add     rsp, 50h
0x1800408cd  pop     r15
0x1800408cf  pop     r14
0x1800408d1  pop     r13
0x1800408d3  pop     r12
0x1800408d5  pop     rdi
0x1800408d6  pop     rsi
0x1800408d7  pop     rbp
0x1800408d8  retn
0x1800408d9  cmp     dword ptr [rcx+0B4h], 1
0x1800408e0  jnz     short loc_1800408AF
0x1800408e2  mov     rax, cs:WPP_GLOBAL_Control
0x1800408e9  lea     r13, WPP_GLOBAL_Control
0x1800408f0  cmp     rax, r13
0x1800408f3  jnz     loc_180040BCB
0x1800408f9  mov     eax, 0FFFFh
0x1800408fe  mov     [rbp+var_20], rbx
0x180040902  cmp     esi, eax
0x180040904  cmovnb  esi, eax
0x180040907  test    r14, r14
0x18004090a  jz      loc_180040C0F
0x180040910  mov     rax, [r14]
0x180040913  lea     rdx, [rbp+var_20]
0x180040917  mov     rcx, r14
0x18004091a  mov     rax, [rax+88h]
0x180040921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040926  mov     ebx, eax
0x180040928  test    eax, eax
0x18004092a  jns     short loc_18004095E
0x18004092c  mov     rax, cs:WPP_GLOBAL_Control
0x180040933  cmp     rax, r13
0x180040936  jnz     loc_180040C89
0x18004093c  mov     rcx, [rbp+var_20]
0x180040940  test    rcx, rcx
0x180040943  jz      loc_1800408AF
0x180040949  mov     [rbp+var_20], r12
0x18004094d  mov     rax, [rcx]
0x180040950  mov     rax, [rax+10h]
0x180040954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040959  jmp     loc_1800408AF
0x18004095e  lea     rbx, [rdi+18h]
0x180040962  mov     rcx, rbx; this
0x180040965  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18004096a  mov     r15, [rdi+0C0h]
0x180040971  mov     [rdi+0BCh], r12d
0x180040978  mov     [rdi+0C0h], r12
0x18004097f  test    rbx, rbx
0x180040982  jnz     loc_180040B4F
0x180040988  test    r15, r15
0x18004098b  jz      loc_180040CCA
0x180040991  xor     ebx, ebx
0x180040993  test    esi, esi
0x180040995  jz      short loc_1800409CD
0x180040997  mov     rcx, cs:WPP_GLOBAL_Control
0x18004099e  lea     rax, [rbx+rbx*2]
0x1800409a2  cmp     [r15+rax*4], r12
0x1800409a6  jz      loc_180040D1C
0x1800409ac  mov     eax, [r15+rax*4+8]
0x1800409b1  test    al, 3
0x1800409b3  jnz     loc_180040D1C
0x1800409b9  add     eax, 0FFFFFFFCh
0x1800409bc  cmp     eax, 0FFFCh
0x1800409c1  ja      loc_180040D1C
0x1800409c7  inc     ebx
0x1800409c9  cmp     ebx, esi
0x1800409cb  jb      short loc_18004099E
0x1800409cd  mov     ecx, esi
0x1800409cf  mov     eax, 2
0x1800409d4  mul     rcx
0x1800409d7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800409de  cmovb   rax, rcx
0x1800409e2  mov     rcx, rax; unsigned __int64
0x1800409e5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800409ea  mov     [rbp+var_18], rax
0x1800409ee  mov     rbx, rax
0x1800409f1  test    rax, rax
0x1800409f4  jz      loc_180040D62
0x1800409fa  xor     r14d, r14d
0x1800409fd  cmp     r12d, esi
0x180040a00  jnb     loc_180040E9F
0x180040a06  mov     rcx, [rdi+58h]
0x180040a0a  lea     r13, [r12+r12*2]
0x180040a0e  mov     rdx, [r15+r13*4]
0x180040a12  lea     r8, [rbp+arg_10]
0x180040a16  mov     [rbp+arg_10], 0
0x180040a1d  xor     r9d, r9d
0x180040a20  mov     [rbp+var_10], rdx
0x180040a24  mov     rax, [rcx]
0x180040a27  mov     rax, [rax+18h]
0x180040a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a30  test    eax, eax
0x180040a32  jns     loc_180040B43
0x180040a38  mov     ecx, [rdi+88h]
0x180040a3e  xor     edx, edx
0x180040a40  mov     eax, [r15+r13*4+8]
0x180040a45  dec     eax
0x180040a47  add     eax, ecx
0x180040a49  div     ecx
0x180040a4b  mov     [rbp+arg_18], eax
0x180040a4e  cmp     eax, [rdi+90h]
0x180040a54  ja      loc_180040E7B
0x180040a5a  mov     rcx, [rdi+60h]
0x180040a5e  call    cs:__imp_?GetFreeEntry@Evict@@QEAAPEAU_SCORE_ENTRY@@XZ; Evict::GetFreeEntry(void)
0x180040a64  mov     r13, rax
0x180040a67  test    rax, rax
0x180040a6a  jz      loc_180040E27
0x180040a70  mov     r10, [rbp+var_10]
0x180040a74  lea     r9, [rbp+arg_0]
0x180040a78  mov     [rax], r10
0x180040a7b  lea     r8, [rbp+arg_10]
0x180040a7f  mov     word ptr [rax+12h], 0FFFFh
0x180040a85  xor     ecx, ecx
0x180040a87  mov     [rax+8], cx
0x180040a8b  or      eax, 0FFFFFFFFh
0x180040a8e  mov     [r13+0Ah], eax
0x180040a92  mov     [r13+0Eh], eax
0x180040a96  mov     eax, [rbp+arg_18]
0x180040a99  mov     [r13+14h], ax
0x180040a9e  mov     rax, r13
0x180040aa1  mov     rcx, [rdi+60h]
0x180040aa5  mov     rdx, [rcx]
0x180040aa8  sub     rax, [rdx]
0x180040aab  mov     ecx, [rdx+0Ch]
0x180040aae  xor     edx, edx
0x180040ab0  div     rcx
0x180040ab3  mov     rcx, [rdi+58h]
0x180040ab7  mov     rdx, r10
0x180040aba  mov     [rbp+arg_10], eax
0x180040abd  xor     eax, eax
0x180040abf  mov     [rbp+arg_0], ax
0x180040ac3  mov     rax, [rcx]
0x180040ac6  mov     rax, [rax+28h]
0x180040aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040acf  mov     ebx, eax
0x180040ad1  test    eax, eax
0x180040ad3  js      loc_180040B79
0x180040ad9  movzx   eax, [rbp+arg_0]
0x180040add  xor     r8d, r8d
0x180040ae0  mov     [r13+8], ax
0x180040ae5  mov     rdx, r13
0x180040ae8  mov     rcx, [rdi+60h]
0x180040aec  call    cs:__imp_?InsertEntry@Evict@@QEAAXPEAU_SCORE_ENTRY@@K@Z; Evict::InsertEntry(_SCORE_ENTRY *,ulong)
0x180040af2  mov     eax, [rbp+arg_18]
0x180040af5  sub     [rdi+90h], eax
0x180040afb  movzx   ecx, [rbp+arg_0]
0x180040aff  mov     rbx, [rbp+var_18]
0x180040b03  inc     cx
0x180040b06  movzx   eax, r14w
0x180040b0a  mov     [rbx+rax*2], cx
0x180040b0e  mov     rcx, [rdi+80h]
0x180040b15  test    rcx, rcx
0x180040b18  jz      short loc_180040B32
0x180040b1a  mov     rax, [rcx]
0x180040b1d  xor     r9d, r9d
0x180040b20  mov     r8, [rbp+var_10]
0x180040b24  xor     edx, edx
0x180040b26  mov     rax, [rax+0D0h]
0x180040b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b32  mov     eax, 1
0x180040b37  add     r14w, ax
0x180040b3b  add     r12d, eax
0x180040b3e  jmp     loc_1800409FD
0x180040b43  movzx   ecx, r14w
0x180040b47  xor     eax, eax
0x180040b49  mov     [rbx+rcx*2], ax
0x180040b4d  jmp     short loc_180040B32
0x180040b4f  mov     rcx, rbx; this
0x180040b52  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x180040b57  jmp     loc_180040988
0x180040b5c  mov     [rbp+var_20], 0
0x180040b64  mov     rax, [rcx]
0x180040b67  mov     rax, [rax+10h]
0x180040b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b70  mov     r12, [rbp+var_18]
0x180040b74  jmp     loc_1800408AF
0x180040b79  mov     r9d, ebx; unsigned int
0x180040b7c  lea     rdx, aRdpcachemanerr_11; "RdpCacheManError_ProcessPendingImportOf"...
0x180040b83  mov     r8d, 9B8h; char *
0x180040b89  lea     rcx, aIidIrdpcachema; "IID_IRdpCacheMan"
0x180040b90  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180040b95  mov     rax, cs:WPP_GLOBAL_Control
0x180040b9c  lea     rcx, WPP_GLOBAL_Control
0x180040ba3  cmp     rax, rcx
0x180040ba6  jnz     loc_180040DDA
0x180040bac  mov     rcx, [rbp+var_20]
0x180040bb0  test    rcx, rcx
0x180040bb3  jz      short loc_180040B70
0x180040bb5  jmp     short loc_180040B5C
0x180040bb7  mov     rcx, [rbp+var_20]
0x180040bbb  mov     ebx, 8007000Eh
0x180040bc0  test    rcx, rcx
0x180040bc3  jz      short loc_180040B70
0x180040bc5  mov     [rbp+var_20], r12
0x180040bc9  jmp     short loc_180040B64
0x180040bcb  test    dword ptr [rax+1Ch], 100h
0x180040bd2  jz      loc_1800408F9
0x180040bd8  cmp     byte ptr [rax+19h], 4
0x180040bdc  jb      loc_1800408F9
0x180040be2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180040be7  mov     rcx, cs:WPP_GLOBAL_Control
0x180040bee  lea     r8, WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids
0x180040bf5  mov     edx, 70h ; 'p'
0x180040bfa  mov     dword ptr [rsp+50h+var_30], esi
0x180040bfe  mov     r9d, eax
0x180040c01  mov     rcx, [rcx+10h]
0x180040c05  call    WPP_SF_Dd
0x180040c0a  jmp     loc_1800408F9
0x180040c0f  mov     ebx, 80004003h
0x180040c14  lea     rdx, aRdpcachemanerr_21; "RdpCacheManError_ProcessPendingImportOf"...
0x180040c1b  mov     r9d, ebx; unsigned int
0x180040c1e  lea     rcx, aIidIrdpcachema; "IID_IRdpCacheMan"
0x180040c25  mov     r8d, 97Bh; char *
0x180040c2b  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180040c30  mov     rax, cs:WPP_GLOBAL_Control
0x180040c37  cmp     rax, r13
0x180040c3a  jz      loc_18004093C
0x180040c40  test    byte ptr [rax+1Ch], 8
0x180040c44  jz      loc_18004093C
0x180040c4a  cmp     byte ptr [rax+19h], 2
0x180040c4e  jb      loc_18004093C
0x180040c54  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180040c59  lea     rcx, aPprotocol; "pProtocol"
0x180040c60  mov     edx, 71h ; 'q'
0x180040c65  mov     [rsp+50h+var_30], rcx
0x180040c6a  lea     r8, WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids
0x180040c71  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c78  mov     r9d, eax
0x180040c7b  mov     rcx, [rcx+10h]
0x180040c7f  call    WPP_SF_Ds
0x180040c84  jmp     loc_18004093C
0x180040c89  test    byte ptr [rax+1Ch], 8
0x180040c8d  jz      loc_18004093C
0x180040c93  cmp     byte ptr [rax+19h], 2
0x180040c97  jb      loc_18004093C
0x180040c9d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180040ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ca9  lea     r8, WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids
0x180040cb0  mov     edx, 72h ; 'r'
0x180040cb5  mov     dword ptr [rsp+50h+var_30], ebx
0x180040cb9  mov     r9d, eax
0x180040cbc  mov     rcx, [rcx+10h]
0x180040cc0  call    WPP_SF_Dd
0x180040cc5  jmp     loc_18004093C
0x180040cca  mov     rax, cs:WPP_GLOBAL_Control
0x180040cd1  cmp     rax, r13
0x180040cd4  jz      short loc_180040D12
0x180040cd6  test    byte ptr [rax+1Ch], 8
0x180040cda  jz      short loc_180040D12
0x180040cdc  cmp     byte ptr [rax+19h], 2
0x180040ce0  jb      short loc_180040D12
0x180040ce2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180040ce7  lea     rcx, aPentries; "pEntries"
0x180040cee  mov     edx, 73h ; 's'
0x180040cf3  mov     [rsp+50h+var_30], rcx
0x180040cf8  lea     r8, WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids
0x180040cff  mov     rcx, cs:WPP_GLOBAL_Control
0x180040d06  mov     r9d, eax
0x180040d09  mov     rcx, [rcx+10h]
0x180040d0d  call    WPP_SF_Ds
0x180040d12  mov     ebx, 80004003h
0x180040d17  jmp     loc_18004093C
0x180040d1c  cmp     rcx, r13
0x180040d1f  jz      short loc_180040D5B
0x180040d21  test    dword ptr [rcx+1Ch], 100h
0x180040d28  jz      short loc_180040D5B
0x180040d2a  cmp     byte ptr [rcx+19h], 4
0x180040d2e  jb      short loc_180040D5B
0x180040d30  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180040d35  mov     rcx, cs:WPP_GLOBAL_Control
0x180040d3c  lea     r8, WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids
0x180040d43  mov     edx, 74h ; 't'
0x180040d48  mov     r9d, eax
0x180040d4b  mov     rcx, [rcx+10h]
0x180040d4f  call    WPP_SF_d
0x180040d54  mov     rcx, cs:WPP_GLOBAL_Control
0x180040d5b  xor     esi, esi
  ... truncated ...
```
