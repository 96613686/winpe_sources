# CMPEG2Controller::MapStream(ulong,CMPEG2DemuxOutputPin *,ulong,void *,int,int)

- ea: `0x18000b21c`
- end: `0x18000b8b8`
- name: `?MapStream@CMPEG2Controller@@QEAAJKPEAVCMPEG2DemuxOutputPin@@KPEAXHH@Z`
- size: `1692`
- prototype: `__int64 __fastcall(CMPEG2Controller *__hidden this, unsigned int, struct CMPEG2DemuxOutputPin *, unsigned int, void *, int, int)`
- caller_count: `1`
- callee_count: `26`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fa00`

## callees

- `0x180002820`
- `0x18000afc8`
- `0x18000b21c`
- `0x18000b8c0`
- `0x18000d010`
- `0x18001956c`
- `0x18001a100`
- `0x18001a180`
- `0x18001a97c`
- `0x18001aa48`
- `0x18001b624`
- `0x180023738`
- `0x180023af8`
- `0x18004329c`
- `0x18004384c`
- `0x180051ce4`
- `0x180073d0c`
- `0x180073d58`
- `0x180074160`
- `0x180074a06`
- `0x180074a12`
- `0x1800a4118`
- `0x1800a4448`
- `0x1800a4544`
- `0x1800a9838`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18000b4f7`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18000b4f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b382`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b55d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b382`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b55d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b2d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b335`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b2d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b335`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b57d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b57d`

## pseudocode

```c
__int64 __fastcall CMPEG2Controller::MapStream(
        CMPEG2Controller *this,
        unsigned int a2,
        struct CMPEG2DemuxOutputPin *a3,
        unsigned int a4,
        void *a5,
        int a6,
        int a7)
{
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // eax
  int v14; // esi
  struct _RTL_CRITICAL_SECTION *v15; // rsi
  int PayloadParser; // ebx
  CMediaSampleCopyBuffer *v17; // rax
  struct CBufferSource *v18; // rsi
  volatile signed __int32 *v19; // rsi
  _DWORD *v20; // rax
  __int64 v21; // r14
  unsigned int v22; // edx
  int v23; // r13d
  unsigned __int64 v24; // r13
  void *v25; // rax
  int v26; // eax
  __int64 v27; // rax
  CMediaSampleWrapperPool *v29; // rax
  int v30; // r9d
  int v31; // r8d
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  int v35; // ecx
  CMediaSampleWrapperPool *v36; // rax
  HKEY v37; // [rsp+28h] [rbp-B9h]
  HKEY v38; // [rsp+30h] [rbp-B1h]
  _BYTE v39[4]; // [rsp+50h] [rbp-91h] BYREF
  unsigned int v40; // [rsp+54h] [rbp-8Dh] BYREF
  int v41; // [rsp+58h] [rbp-89h] BYREF
  unsigned int v42; // [rsp+5Ch] [rbp-85h]
  CDemuxBaseParser *v43; // [rsp+60h] [rbp-81h] BYREF
  void *Src; // [rsp+68h] [rbp-79h]
  struct _AMMediaType v45; // [rsp+70h] [rbp-71h] BYREF

  v42 = a4;
  Src = a5;
  v40 = 0;
  memset_0(&v45, 0, sizeof(v45));
  v45.lSampleSize = 1;
  v45.bFixedSizeSamples = 1;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v39, "CMPEG2Controller::MapStream", 1538);
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
  {
    LODWORD(v38) = a4;
    LODWORD(v37) = a2;
    WPP_SF_qqDD(*((_QWORD *)WPP_GLOBAL_Control + 17), v11, v12, this, a3);
  }
  if ( !(*(unsigned int (__fastcall **)(CMPEG2Controller *, _QWORD))(*(_QWORD *)this + 32LL))(this, a2) )
  {
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v39);
    FreeMediaType(&v45);
    return 2147942487LL;
  }
  CMPEG2Controller::StreamMapEvent(this, a2, a4);
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 23));
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v39,
    "CMPEG2Controller::FindPinStreamMapRecordLocked_",
    1949);
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
  {
    v38 = (HKEY)&v40;
    LODWORD(v37) = a2;
    WPP_SF_qqDq(*((_QWORD *)WPP_GLOBAL_Control + 17), 47, &WPP_98b8cb87168e318df77c5ab37b34c3c5_Traceguids, this, a3);
  }
  v13 = *((_DWORD *)this + 6);
  if ( v13 )
  {
    v30 = 0;
LABEL_35:
    v31 = v13 - 1;
    while ( v30 <= v31 )
    {
      v13 = (v31 + v30) / 2;
      v32 = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * v13);
      if ( *(_QWORD *)(v32 + 16) > (unsigned __int64)a3 )
        goto LABEL_35;
      if ( *(_QWORD *)(v32 + 16) >= (unsigned __int64)a3 && *(_DWORD *)(v32 + 8) >= a2 )
      {
        if ( *(_DWORD *)(v32 + 8) > a2 )
          goto LABEL_35;
        v40 = (v31 + v30) / 2;
        v14 = 0;
        goto LABEL_8;
      }
      v30 = v13 + 1;
    }
  }
  v14 = -2147467259;
LABEL_8:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v39);
  if ( v14 >= 0 )
  {
    if ( v40 < *((_DWORD *)this + 6) )
    {
      v34 = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * v40);
      v35 = 0;
    }
    else
    {
      v34 = 0;
      v35 = -2147024809;
    }
    if ( v35 < 0 )
      v34 = 0;
    if ( *(_DWORD *)(v34 + 12) == a4 )
    {
      PayloadParser = 0;
      goto LABEL_29;
    }
    PayloadParser = CMPEG2Controller::UnmapStream(this, a2, a3);
    if ( PayloadParser < 0 )
      goto LABEL_29;
  }
  v15 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a3 + 8);
  PayloadParser = 0;
  v41 = 0;
  v43 = 0;
  EnterCriticalSection(v15);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v39, "CMPEG2DemuxOutputPin::GetMediaType", 350);
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 17), 16, &WPP_89c6d11f487739c3770de58ece25afb2_Traceguids, a3, 0, &v45);
  CMediaType::Set((CMediaType *)&v45, (const struct _AMMediaType *)((char *)a3 + 272));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v39);
  LeaveCriticalSection(v15);
  if ( (*(unsigned int (__fastcall **)(CMPEG2Controller *, _QWORD, struct _AMMediaType *))(*(_QWORD *)this + 24LL))(
         this,
         a4,
         &v45) )
  {
    v17 = (CMediaSampleCopyBuffer *)operator new(0x58u);
    if ( !v17 )
    {
      v18 = 0;
      goto LABEL_14;
    }
    v29 = CMediaSampleCopyBuffer::CMediaSampleCopyBuffer(
            v17,
            a3,
            *((_DWORD *)this + 36),
            *((_DWORD *)this + 37),
            *((struct CRefCountedCritSec **)this + 23),
            v37,
            a2,
            *((struct CMpeg2Stats **)this + 12));
  }
  else
  {
    v36 = (CMediaSampleWrapperPool *)operator new(0x88u);
    if ( !v36 )
      goto LABEL_66;
    v29 = CMediaSampleWrapperPool::CMediaSampleWrapperPool(
            v36,
            a3,
            *((_DWORD *)this + 36),
            *((_DWORD *)this + 37),
            *((struct CRefCountedCritSec **)this + 23),
            *((_DWORD *)this + 38),
            v38,
            *((struct CMpeg2Stats **)this + 12),
            &v41);
    PayloadParser = v41;
  }
  v18 = v29;
LABEL_14:
  if ( !v18 )
  {
LABEL_66:
    if ( PayloadParser >= 0 )
      PayloadParser = -2147024882;
    if ( !byte_1800EACCB )
      goto LABEL_29;
    v33 = 39;
    goto LABEL_70;
  }
  if ( PayloadParser < 0 )
  {
    (**(void (__fastcall ***)(struct CBufferSource *, __int64))v18)(v18, 1);
    goto LABEL_66;
  }
  PayloadParser = CMPEG2Controller::GetPayloadParser_(this, a2, a4, a3, v18, (unsigned int *)a5, a7, &v43);
  (*(void (__fastcall **)(struct CBufferSource *))(*(_QWORD *)v18 + 16LL))(v18);
  if ( PayloadParser < 0 )
  {
    if ( byte_1800EACCB )
    {
      v33 = 40;
      goto LABEL_70;
    }
  }
  else
  {
    v19 = (volatile signed __int32 *)v43;
    PayloadParser = CStreamMapper::MapStream(*((CStreamMapper **)this + 1), a2, v43, 0);
    if ( PayloadParser >= 0 )
    {
      v20 = operator new(0x30u);
      v21 = (__int64)v20;
      if ( v20 )
      {
        *(_QWORD *)v20 = v19;
        PayloadParser = 0;
        v20[2] = a2;
        v20[3] = v42;
        *((_QWORD *)v20 + 2) = a3;
        *((_QWORD *)v20 + 3) = 0;
        _InterlockedIncrement(v19 + 6);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a3 + 1) + 8LL))(*((_QWORD *)a3 + 1));
        v23 = 0;
        if ( Src )
        {
          v24 = *(_DWORD *)(v21 + 12) == 0 ? 8 : 0;
          v25 = operator new[](v24);
          *(_QWORD *)(v21 + 24) = v25;
          if ( v25 )
          {
            memcpy_0(v25, Src, v24);
            v23 = 0;
          }
          else
          {
            PayloadParser = -2147024882;
            v23 = -2147024882;
          }
        }
        if ( v23 >= 0 )
        {
          CDemuxBaseParser::Release((CDemuxBaseParser *)v19);
          v26 = TSimpleVector<CStreamToPinMap *>::Insert((__int64)this + 16, *((_DWORD *)this + 6), v21);
          PayloadParser = v26;
          if ( !v26 )
            goto LABEL_24;
          if ( byte_1800EACCB )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 17),
              42,
              &WPP_98b8cb87168e318df77c5ab37b34c3c5_Traceguids,
              this,
              v26);
          if ( PayloadParser < 0 )
          {
            CStreamMapper::UnmapStream(*((CStreamMapper **)this + 1), a2, (struct CDemuxBaseParser *)v19);
            CDemuxBaseParser::Release((CDemuxBaseParser *)v19);
          }
          else
          {
LABEL_24:
            qsort(*((void **)this + 2), *((unsigned int *)this + 6), 8u, CStreamToPinMap::Compare);
            if ( !v42 )
            {
              v27 = *((_QWORD *)this + 20);
              *(_QWORD *)(v21 + 32) = v27;
              *(_QWORD *)(v21 + 40) = (char *)this + 160;
              *(_QWORD *)(v27 + 8) = v21 + 32;
              *((_QWORD *)this + 20) = v21 + 32;
              CMPEG2Controller::AVStreamsResetAll_(this, a6);
            }
          }
          goto LABEL_29;
        }
        CStreamToPinMap::`scalar deleting destructor'((CStreamToPinMap *)v21, v22);
      }
      else
      {
        v23 = PayloadParser;
      }
      CStreamMapper::UnmapStream(*((CStreamMapper **)this + 1), a2, (struct CDemuxBaseParser *)v19);
      CDemuxBaseParser::Release((CDemuxBaseParser *)v19);
      if ( v23 >= 0 )
        PayloadParser = -2147024882;
      goto LABEL_29;
    }
    CDemuxBaseParser::Release((CDemuxBaseParser *)v19);
    if ( byte_1800EACCB )
    {
      v33 = 41;
LABEL_70:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        v33,
        &WPP_98b8cb87168e318df77c5ab37b34c3c5_Traceguids,
        this,
        PayloadParser);
    }
  }
LABEL_29:
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 23));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v39);
  if ( v45.cbFormat )
    CoTaskMemFree(v45.pbFormat);
  return (unsigned int)PayloadParser;
}

```

## disassembly

```asm
0x18000b21c  push    rbp
0x18000b21e  push    rbx
0x18000b21f  push    rsi
0x18000b220  push    rdi
0x18000b221  push    r12
0x18000b223  push    r13
0x18000b225  push    r14
0x18000b227  push    r15
0x18000b229  lea     rbp, [rsp-7]
0x18000b22e  sub     rsp, 0E8h
0x18000b235  mov     rax, cs:__security_cookie
0x18000b23c  xor     rax, rsp
0x18000b23f  mov     [rbp+3Fh+var_50], rax
0x18000b243  mov     r12, [rbp+3Fh+arg_20]
0x18000b247  mov     r15d, edx
0x18000b24a  xor     edx, edx; Val
0x18000b24c  mov     [rsp+120h+var_C4], r9d
0x18000b251  mov     r13, r8
0x18000b254  mov     [rbp+3Fh+Src], r12
0x18000b258  mov     rdi, rcx
0x18000b25b  mov     [rsp+120h+var_CC], 0
0x18000b263  lea     rcx, [rbp+3Fh+var_B0]; void *
0x18000b267  mov     r14d, r9d
0x18000b26a  lea     r8d, [rdx+58h]; Size
0x18000b26e  call    memset_0
0x18000b273  mov     eax, 1
0x18000b278  lea     rdx, aCmpeg2controll_13; "CMPEG2Controller::MapStream"
0x18000b27f  mov     r8d, 602h; int
0x18000b285  mov     [rbp+3Fh+var_B0.lSampleSize], eax
0x18000b288  lea     rcx, [rsp+120h+var_D0]; this
0x18000b28d  mov     [rbp+3Fh+var_B0.bFixedSizeSamples], eax
0x18000b290  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000b295  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18000b29c  jnb     loc_18000B6C2
0x18000b2a2  mov     rax, [rdi]
0x18000b2a5  mov     edx, r15d
0x18000b2a8  mov     rcx, rdi
0x18000b2ab  mov     rax, [rax+20h]
0x18000b2af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2b4  test    eax, eax
0x18000b2b6  jz      loc_18000B6EC
0x18000b2bc  mov     r8d, r14d; unsigned int
0x18000b2bf  mov     edx, r15d; unsigned int
0x18000b2c2  mov     rcx, rdi; this
0x18000b2c5  call    ?StreamMapEvent@CMPEG2Controller@@AEAAXKK@Z; CMPEG2Controller::StreamMapEvent(ulong,ulong)
0x18000b2ca  mov     rcx, [rdi+0B8h]; lpCriticalSection
0x18000b2d1  call    cs:__imp_EnterCriticalSection
0x18000b2d8  nop     dword ptr [rax+rax+00h]
0x18000b2dd  mov     r8d, 79Dh; int
0x18000b2e3  lea     rdx, aCmpeg2controll_1; "CMPEG2Controller::FindPinStreamMapRecor"...
0x18000b2ea  lea     rcx, [rsp+120h+var_D0]; this
0x18000b2ef  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000b2f4  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18000b2fb  jnb     loc_18000B709
0x18000b301  mov     eax, [rdi+18h]
0x18000b304  test    eax, eax
0x18000b306  jnz     loc_18000B5E7
0x18000b30c  mov     esi, 80004005h
0x18000b311  lea     rcx, [rsp+120h+var_D0]; this
0x18000b316  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000b31b  test    esi, esi
0x18000b31d  jns     loc_18000B650
0x18000b323  mov     rsi, [r13+40h]
0x18000b327  xor     ebx, ebx
0x18000b329  mov     rcx, rsi; lpCriticalSection
0x18000b32c  mov     [rsp+120h+var_C8], ebx
0x18000b330  mov     [rsp+120h+var_C0], rbx
0x18000b335  call    cs:__imp_EnterCriticalSection
0x18000b33c  nop     dword ptr [rax+rax+00h]
0x18000b341  mov     r8d, 15Eh; int
0x18000b347  lea     rdx, aCmpeg2demuxout_22; "CMPEG2DemuxOutputPin::GetMediaType"
0x18000b34e  lea     rcx, [rsp+120h+var_D0]; this
0x18000b353  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000b358  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18000b35f  jnb     loc_18000B754
0x18000b365  lea     rdx, [r13+110h]; struct _AMMediaType *
0x18000b36c  lea     rcx, [rbp+3Fh+var_B0]; this
0x18000b370  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x18000b375  lea     rcx, [rsp+120h+var_D0]; this
0x18000b37a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000b37f  mov     rcx, rsi; lpCriticalSection
0x18000b382  call    cs:__imp_LeaveCriticalSection
0x18000b389  nop     dword ptr [rax+rax+00h]
0x18000b38e  mov     rax, [rdi]
0x18000b391  lea     r8, [rbp+3Fh+var_B0]
0x18000b395  mov     edx, r14d
0x18000b398  mov     rcx, rdi
0x18000b39b  mov     rax, [rax+18h]
0x18000b39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3a4  test    eax, eax
0x18000b3a6  jz      loc_18000B788
0x18000b3ac  mov     ecx, 58h ; 'X'; Size
0x18000b3b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b3b6  test    rax, rax
0x18000b3b9  jnz     loc_18000B5AC
0x18000b3bf  xor     esi, esi
0x18000b3c1  test    rsi, rsi
0x18000b3c4  jz      loc_18000B874
0x18000b3ca  test    ebx, ebx
0x18000b3cc  js      loc_18000B861
0x18000b3d2  lea     rax, [rsp+120h+var_C0]
0x18000b3d7  mov     r9, r13; struct CMPEG2DemuxOutputPin *
0x18000b3da  mov     [rsp+120h+var_E8], rax; struct CDemuxBaseParser **
0x18000b3df  mov     r8d, r14d; unsigned int
0x18000b3e2  mov     eax, [rbp+3Fh+arg_30]
0x18000b3e5  mov     edx, r15d; unsigned int
0x18000b3e8  mov     [rsp+120h+var_F0], eax; int
0x18000b3ec  mov     rcx, rdi; this
0x18000b3ef  mov     [rsp+120h+var_F8], r12; void *
0x18000b3f4  mov     [rsp+120h+var_100], rsi; struct CBufferSource *
0x18000b3f9  call    ?GetPayloadParser_@CMPEG2Controller@@AEAAJKKPEAVCMPEG2DemuxOutputPin@@PEAVCBufferSource@@PEAXHPEAPEAVCDemuxBaseParser@@@Z; CMPEG2Controller::GetPayloadParser_(ulong,ulong,CMPEG2DemuxOutputPin *,CBufferSource *,void *,int,CDemuxBaseParser * *)
0x18000b3fe  mov     ebx, eax
0x18000b400  mov     rcx, rsi
0x18000b403  mov     rax, [rsi]
0x18000b406  mov     rax, [rax+10h]
0x18000b40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b40f  test    ebx, ebx
0x18000b411  js      loc_18000B7E6
0x18000b417  mov     rsi, [rsp+120h+var_C0]
0x18000b41c  xor     r9d, r9d; int
0x18000b41f  mov     rcx, [rdi+8]; this
0x18000b423  mov     r8, rsi; struct CDemuxBaseParser *
0x18000b426  mov     edx, r15d; unsigned int
0x18000b429  call    ?MapStream@CStreamMapper@@QEAAJKPEAVCDemuxBaseParser@@H@Z; CStreamMapper::MapStream(ulong,CDemuxBaseParser *,int)
0x18000b42e  mov     ebx, eax
0x18000b430  test    eax, eax
0x18000b432  js      loc_18000B631
0x18000b438  mov     ecx, 30h ; '0'; Size
0x18000b43d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b442  mov     r14, rax
0x18000b445  mov     r12d, 8007000Eh
0x18000b44b  test    rax, rax
0x18000b44e  jz      loc_18000B533
0x18000b454  mov     [rax], rsi
0x18000b457  xor     ebx, ebx
0x18000b459  mov     [rax+8], r15d
0x18000b45d  mov     eax, [rsp+120h+var_C4]
0x18000b461  mov     [r14+0Ch], eax
0x18000b465  mov     [r14+10h], r13
0x18000b469  mov     qword ptr [r14+18h], 0
0x18000b471  lock inc dword ptr [rsi+18h]
0x18000b475  mov     rcx, [r13+8]
0x18000b479  mov     rax, [rcx]
0x18000b47c  mov     rax, [rax+8]
0x18000b480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b485  xor     r13d, r13d
0x18000b488  cmp     [rbp+3Fh+Src], rbx
0x18000b48c  jz      short loc_18000B4B9
0x18000b48e  mov     eax, [r14+0Ch]
0x18000b492  neg     eax
0x18000b494  sbb     r13, r13
0x18000b497  not     r13
0x18000b49a  and     r13d, 8
0x18000b49e  mov     ecx, r13d; unsigned __int64
0x18000b4a1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000b4a6  mov     [r14+18h], rax
0x18000b4aa  test    rax, rax
0x18000b4ad  jnz     loc_18000B7FD
0x18000b4b3  mov     ebx, r12d
0x18000b4b6  mov     r13d, r12d
0x18000b4b9  test    r13d, r13d
0x18000b4bc  js      loc_18000B84C
0x18000b4c2  mov     rcx, rsi; this
0x18000b4c5  call    ?Release@CDemuxBaseParser@@QEAAKXZ; CDemuxBaseParser::Release(void)
0x18000b4ca  mov     edx, [rdi+18h]
0x18000b4cd  lea     rcx, [rdi+10h]
0x18000b4d1  mov     r8, r14
0x18000b4d4  call    ?Insert@?$TSimpleVector@PEAVCStreamToPinMap@@@@QEAAJKPEAVCStreamToPinMap@@PEAK@Z; TSimpleVector<CStreamToPinMap *>::Insert(ulong,CStreamToPinMap *,ulong *)
0x18000b4d9  mov     ebx, eax
0x18000b4db  test    eax, eax
0x18000b4dd  jnz     loc_18000B814
0x18000b4e3  mov     edx, [rdi+18h]; NumOfElements
0x18000b4e6  lea     r9, ?Compare@CStreamToPinMap@@SAHPEBX0@Z; CompareFunction
0x18000b4ed  mov     rcx, [rdi+10h]; Base
0x18000b4f1  mov     r8d, 8; SizeOfElements
0x18000b4f7  call    cs:__imp_qsort
0x18000b4fe  nop     dword ptr [rax+rax+00h]
0x18000b503  cmp     [rsp+120h+var_C4], 0
0x18000b508  jnz     short loc_18000B556
0x18000b50a  lea     rdx, [rdi+0A0h]
0x18000b511  mov     rax, [rdx]
0x18000b514  lea     rcx, [r14+20h]
0x18000b518  mov     [rcx], rax
0x18000b51b  mov     [r14+28h], rdx
0x18000b51f  mov     [rax+8], rcx
0x18000b523  mov     [rdx], rcx
0x18000b526  mov     rcx, rdi; this
0x18000b529  mov     edx, [rbp+3Fh+arg_28]; int
0x18000b52c  call    ?AVStreamsResetAll_@CMPEG2Controller@@AEAAXH@Z; CMPEG2Controller::AVStreamsResetAll_(int)
0x18000b531  jmp     short loc_18000B556
0x18000b533  mov     r13d, ebx
0x18000b536  mov     rcx, [rdi+8]; this
0x18000b53a  mov     r8, rsi; struct CDemuxBaseParser *
0x18000b53d  mov     edx, r15d; unsigned int
0x18000b540  call    ?UnmapStream@CStreamMapper@@QEAAJKPEAVCDemuxBaseParser@@@Z; CStreamMapper::UnmapStream(ulong,CDemuxBaseParser *)
0x18000b545  mov     rcx, rsi; this
0x18000b548  call    ?Release@CDemuxBaseParser@@QEAAKXZ; CDemuxBaseParser::Release(void)
0x18000b54d  test    r13d, r13d
0x18000b550  jns     loc_18000B859
0x18000b556  mov     rcx, [rdi+0B8h]; lpCriticalSection
0x18000b55d  call    cs:__imp_LeaveCriticalSection
0x18000b564  nop     dword ptr [rax+rax+00h]
0x18000b569  lea     rcx, [rsp+120h+var_D0]; this
0x18000b56e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000b573  cmp     [rbp+3Fh+var_B0.cbFormat], 0
0x18000b577  jz      short loc_18000B589
0x18000b579  mov     rcx, [rbp+3Fh+var_B0.pbFormat]; pv
0x18000b57d  call    cs:__imp_CoTaskMemFree
0x18000b584  nop     dword ptr [rax+rax+00h]
0x18000b589  mov     eax, ebx
0x18000b58b  mov     rcx, [rbp+3Fh+var_50]
0x18000b58f  xor     rcx, rsp; StackCookie
0x18000b592  call    __security_check_cookie
0x18000b597  add     rsp, 0E8h
0x18000b59e  pop     r15
0x18000b5a0  pop     r14
0x18000b5a2  pop     r13
0x18000b5a4  pop     r12
0x18000b5a6  pop     rdi
0x18000b5a7  pop     rsi
0x18000b5a8  pop     rbx
0x18000b5a9  pop     rbp
0x18000b5aa  retn
0x18000b5ac  mov     rcx, [rdi+60h]
0x18000b5b0  mov     rdx, r13; struct CMPEG2DemuxOutputPin *
0x18000b5b3  mov     r9d, [rdi+94h]; int
0x18000b5ba  mov     r8d, [rdi+90h]; int
0x18000b5c1  mov     [rsp+120h+var_E8], rcx; struct CMpeg2Stats *
0x18000b5c6  mov     rcx, [rdi+0B8h]
0x18000b5cd  mov     [rsp+120h+var_F0], r15d; unsigned int
0x18000b5d2  mov     [rsp+120h+var_100], rcx; struct CRefCountedCritSec *
0x18000b5d7  mov     rcx, rax; this
0x18000b5da  call    ??0CMediaSampleCopyBuffer@@QEAA@PEAVCMPEG2DemuxOutputPin@@HHPEAVCRefCountedCritSec@@PEAUHKEY__@@KPEAVCMpeg2Stats@@@Z; CMediaSampleCopyBuffer::CMediaSampleCopyBuffer(CMPEG2DemuxOutputPin *,int,int,CRefCountedCritSec *,HKEY__ *,ulong,CMpeg2Stats *)
0x18000b5df  mov     rsi, rax
0x18000b5e2  jmp     loc_18000B3C1
0x18000b5e7  mov     r10, [rdi+10h]
0x18000b5eb  xor     r9d, r9d
0x18000b5ee  lea     r8d, [rax-1]
0x18000b5f2  cmp     r9d, r8d
0x18000b5f5  jg      loc_18000B30C
0x18000b5fb  mov     ecx, 2
0x18000b600  lea     eax, [r8+r9]
0x18000b604  cdq
0x18000b605  idiv    ecx
0x18000b607  movsxd  rcx, eax
0x18000b60a  mov     rdx, [r10+rcx*8]
0x18000b60e  cmp     [rdx+10h], r13
0x18000b612  ja      short loc_18000B5EE
0x18000b614  jb      loc_18000B744
0x18000b61a  cmp     [rdx+8], r15d
0x18000b61e  jb      loc_18000B744
0x18000b624  ja      short loc_18000B5EE
0x18000b626  mov     [rsp+120h+var_CC], eax
0x18000b62a  xor     esi, esi
0x18000b62c  jmp     loc_18000B311
0x18000b631  mov     rcx, rsi; this
0x18000b634  call    ?Release@CDemuxBaseParser@@QEAAKXZ; CDemuxBaseParser::Release(void)
0x18000b639  cmp     cs:byte_1800EACCB, 1
0x18000b640  jb      loc_18000B556
0x18000b646  mov     edx, 29h ; ')'
0x18000b64b  jmp     loc_18000B892
0x18000b650  mov     eax, [rsp+120h+var_CC]
0x18000b654  cmp     eax, [rdi+18h]
0x18000b657  jb      short loc_18000B68F
0x18000b659  xor     edx, edx
0x18000b65b  mov     ecx, 80070057h
0x18000b660  xor     eax, eax
0x18000b662  test    ecx, ecx
0x18000b664  cmovs   rdx, rax
0x18000b668  cmp     [rdx+0Ch], r14d
0x18000b66c  jz      loc_18000B74D
0x18000b672  mov     r8, r13; struct CMPEG2DemuxOutputPin *
0x18000b675  mov     edx, r15d; unsigned int
0x18000b678  mov     rcx, rdi; this
0x18000b67b  call    ?UnmapStream@CMPEG2Controller@@QEAAJKPEAVCMPEG2DemuxOutputPin@@@Z; CMPEG2Controller::UnmapStream(ulong,CMPEG2DemuxOutputPin *)
0x18000b680  mov     ebx, eax
0x18000b682  test    eax, eax
0x18000b684  jns     loc_18000B323
0x18000b68a  jmp     loc_18000B556
0x18000b68f  mov     rcx, rax
0x18000b692  mov     rax, [rdi+10h]
0x18000b696  mov     rdx, [rax+rcx*8]
0x18000b69a  xor     ecx, ecx
0x18000b69c  jmp     short loc_18000B660
0x18000b69e  test    ebx, ebx
0x18000b6a0  jns     loc_18000B4E3
0x18000b6a6  mov     rcx, [rdi+8]; this
0x18000b6aa  mov     r8, rsi; struct CDemuxBaseParser *
0x18000b6ad  mov     edx, r15d; unsigned int
0x18000b6b0  call    ?UnmapStream@CStreamMapper@@QEAAJKPEAVCDemuxBaseParser@@@Z; CStreamMapper::UnmapStream(ulong,CDemuxBaseParser *)
0x18000b6b5  mov     rcx, rsi; this
0x18000b6b8  call    ?Release@CDemuxBaseParser@@QEAAKXZ; CDemuxBaseParser::Release(void)
0x18000b6bd  jmp     loc_18000B556
0x18000b6c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6c9  mov     r9, rdi
0x18000b6cc  mov     [rsp+120h+var_F0], r14d
0x18000b6d1  mov     dword ptr [rsp+120h+var_F8], r15d
0x18000b6d6  mov     [rsp+120h+var_100], r13
0x18000b6db  mov     rcx, [rcx+88h]
0x18000b6e2  call    WPP_SF_qqDD
  ... truncated ...
```
