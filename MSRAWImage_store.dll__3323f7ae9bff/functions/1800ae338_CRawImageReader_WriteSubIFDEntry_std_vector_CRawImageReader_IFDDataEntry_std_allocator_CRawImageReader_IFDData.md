# CRawImageReader::WriteSubIFDEntry(std::vector<CRawImageReader::IFDDataEntry,std::allocator<CRawImageReader::IFDDataEntry>> &,_LARGE_INTEGER *,uint *)

- ea: `0x1800ae338`
- end: `0x1800ae6b1`
- name: `?WriteSubIFDEntry@CRawImageReader@@AEAAJAEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@PEAT_LARGE_INTEGER@@PEAI@Z`
- size: `889`
- prototype: `__int64 __fastcall(CRawImageReader *this)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800a98c0`

## callees

- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009b9e4`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800adcb0`
- `0x1800ae338`
- `0x1800af388`
- `0x1800b4010`

## string_xrefs

- `0x1800ae37d`: `CRawImageReader::WriteSubIFDEntry`
- `0x1800ae400`: `CRawImageReader::WriteSubIFDEntry`
- `0x1800ae4f3`: `CRawImageReader::WriteSubIFDEntry`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRawImageReader::WriteSubIFDEntry(
        CRawImageReader *this,
        _QWORD *a2,
        union _LARGE_INTEGER *a3,
        unsigned int *a4)
{
  int *v8; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v10; // ebx
  unsigned int *v11; // r14
  unsigned __int64 v12; // rdi
  int v13; // ebx
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  int v16; // r8d
  unsigned int v17; // r13d
  unsigned int i; // edi
  struct CRawImageReader::IFDDataEntry *v19; // rax
  CallStackTracing *v20; // rcx
  CallStackTracing *v21; // rcx
  int v23; // [rsp+20h] [rbp-49h]
  __int16 v24; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v25[4]; // [rsp+34h] [rbp-35h] BYREF
  int v26; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v27; // [rsp+3Ch] [rbp-2Dh] BYREF
  _QWORD *v28; // [rsp+40h] [rbp-29h]
  __int64 v29; // [rsp+48h] [rbp-21h]
  _BYTE v30[32]; // [rsp+50h] [rbp-19h] BYREF

  v29 = -2;
  v28 = a2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v25, "CRawImageReader::WriteSubIFDEntry", 1446);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            v30);
    *((_DWORD *)ThreadRelativeContext + 504) = v10;
  }
  v11 = (unsigned int *)((char *)this + 56);
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v30,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    "CRawImageReader::WriteSubIFDEntry",
    v8,
    v23);
  v27 = 0;
  v12 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a2[1] - *a2) >> 3);
  if ( *((_BYTE *)this + 107) )
  {
    LOBYTE(v24) = (unsigned __int16)(-13107 * ((__int64)(a2[1] - *a2) >> 3)) >> 8;
    HIBYTE(v24) = v12;
  }
  else
  {
    v24 = -13107 * ((__int64)(a2[1] - *a2) >> 3);
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, __int16 *, __int64, unsigned int *))(**((_QWORD **)this + 31) + 32LL))(
          *((_QWORD *)this + 31),
          &v24,
          2,
          &v27);
  if ( v13 >= 0 )
  {
    a3->QuadPart += v27;
    v17 = (unsigned __int16)v12;
    *a4 += 12 * (unsigned __int16)v12 + 6;
    for ( i = 0; i < v17; ++i )
    {
      v19 = (struct CRawImageReader::IFDDataEntry *)std::vector<CRawImageReader::IFDDataEntry>::at(v28, i);
      v13 = CRawImageReader::WriteOneIFDEntryToStream(this, v19, a3, a4);
      if ( v13 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            127,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *v11,
            v13);
        }
        v20 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)&off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          v15 = CallStackTracing::GetThreadRelativeContext(v20);
          if ( *((_DWORD *)v15 + 499) != v13 )
          {
            v16 = 1458;
            goto LABEL_17;
          }
        }
        goto LABEL_42;
      }
    }
    v26 = 0;
    v13 = (*(__int64 (__fastcall **)(_QWORD, int *, __int64, unsigned int *))(**((_QWORD **)this + 31) + 32LL))(
            *((_QWORD *)this + 31),
            &v26,
            4,
            &v27);
    if ( v13 >= 0 )
    {
      a3->QuadPart = *a4;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v11, v13);
      }
      v21 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)&off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v15 = CallStackTracing::GetThreadRelativeContext(v21);
        if ( *((_DWORD *)v15 + 499) != v13 )
        {
          v16 = 1462;
          goto LABEL_17;
        }
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v11, v13);
    }
    v14 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)&off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext(v14);
      if ( *((_DWORD *)v15 + 499) != v13 )
      {
        v16 = 1451;
LABEL_17:
        CallStackContext::TraceFailure(v15, "CRawImageReader::WriteSubIFDEntry", v16, v13);
      }
    }
  }
LABEL_42:
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v30);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v25);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800ae338  push    rbp
0x1800ae33a  push    rbx
0x1800ae33b  push    rsi
0x1800ae33c  push    rdi
0x1800ae33d  push    r12
0x1800ae33f  push    r13
0x1800ae341  push    r14
0x1800ae343  push    r15
0x1800ae345  lea     rbp, [rsp-1Fh]
0x1800ae34a  sub     rsp, 88h
0x1800ae351  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFEh
0x1800ae359  mov     rax, cs:__security_cookie
0x1800ae360  xor     rax, rsp
0x1800ae363  mov     [rbp+57h+var_50], rax
0x1800ae367  mov     r12, r9
0x1800ae36a  mov     r15, r8
0x1800ae36d  mov     r13, rdx
0x1800ae370  mov     [rbp+57h+var_80], rdx
0x1800ae374  mov     rsi, rcx
0x1800ae377  mov     r8d, 5A6h; int
0x1800ae37d  lea     rdx, aCrawimagereade; "CRawImageReader::WriteSubIFDEntry"
0x1800ae384  lea     rcx, [rbp+57h+var_8C]; this
0x1800ae388  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ae38d  nop
0x1800ae38e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ae395  cmp     byte ptr [rcx+8], 0
0x1800ae399  jz      short loc_1800AE3F0
0x1800ae39b  cmp     qword ptr [rsi+110h], 0
0x1800ae3a3  jz      short loc_1800AE3F0
0x1800ae3a5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae3aa  mov     rdi, rax
0x1800ae3ad  mov     rcx, [rsi+110h]
0x1800ae3b4  mov     rdx, [rcx]
0x1800ae3b7  mov     rax, [rdx+128h]
0x1800ae3be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae3c3  mov     ebx, eax
0x1800ae3c5  mov     rcx, [rsi+110h]
0x1800ae3cc  mov     rdx, [rcx]
0x1800ae3cf  mov     rax, [rdx+118h]
0x1800ae3d6  lea     rdx, [rbp+57h+var_70]
0x1800ae3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae3df  movups  xmm0, xmmword ptr [rax]
0x1800ae3e2  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800ae3ea  mov     [rdi+7E0h], ebx
0x1800ae3f0  lea     r14, [rsi+38h]
0x1800ae3f4  mov     rax, rsi
0x1800ae3f7  neg     rax
0x1800ae3fa  sbb     rdx, rdx
0x1800ae3fd  and     rdx, r14; struct CTraceBase *
0x1800ae400  lea     r8, aCrawimagereade; "CRawImageReader::WriteSubIFDEntry"
0x1800ae407  lea     rcx, [rbp+57h+var_70]; this
0x1800ae40b  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800ae410  nop
0x1800ae411  mov     [rbp+57h+var_84], 0
0x1800ae418  mov     rdi, [r13+8]
0x1800ae41c  sub     rdi, [r13+0]
0x1800ae420  sar     rdi, 3
0x1800ae424  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800ae42e  imul    rdi, rax
0x1800ae432  movzx   eax, di
0x1800ae435  shr     ax, 8
0x1800ae439  cmp     byte ptr [rsi+6Bh], 0
0x1800ae43d  jnz     short loc_1800AE448
0x1800ae43f  mov     [rbp+57h+var_8F], al
0x1800ae442  mov     [rbp+57h+var_90], dil
0x1800ae446  jmp     short loc_1800AE44F
0x1800ae448  mov     [rbp+57h+var_90], al
0x1800ae44b  mov     [rbp+57h+var_8F], dil
0x1800ae44f  mov     rcx, [rsi+0F8h]
0x1800ae456  mov     rax, [rcx]
0x1800ae459  lea     r9, [rbp+57h+var_84]
0x1800ae45d  mov     r8d, 2
0x1800ae463  lea     rdx, [rbp+57h+var_90]
0x1800ae467  mov     rax, [rax+20h]
0x1800ae46b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae470  mov     ebx, eax
0x1800ae472  test    eax, eax
0x1800ae474  jns     loc_1800AE507
0x1800ae47a  lea     rax, WPP_GLOBAL_Control
0x1800ae481  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae488  cmp     rcx, rax
0x1800ae48b  jz      short loc_1800AE4B5
0x1800ae48d  test    byte ptr [rcx+1Ch], 1
0x1800ae491  jz      short loc_1800AE4B5
0x1800ae493  cmp     byte ptr [rcx+19h], 4
0x1800ae497  jb      short loc_1800AE4B5
0x1800ae499  mov     edx, 7Eh ; '~'
0x1800ae49e  mov     [rsp+0C0h+var_A0], ebx
0x1800ae4a2  mov     r9d, [r14]
0x1800ae4a5  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ae4ac  mov     rcx, [rcx+10h]
0x1800ae4b0  call    WPP_SF_Dd
0x1800ae4b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae4bc  test    rcx, rcx
0x1800ae4bf  jnz     short loc_1800AE4CF
0x1800ae4c1  lea     rcx, off_1800E5190; this
0x1800ae4c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae4cf  cmp     byte ptr [rcx+8], 0
0x1800ae4d3  jz      loc_1800AE67B
0x1800ae4d9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae4de  cmp     [rax+7CCh], ebx
0x1800ae4e4  jz      loc_1800AE67B
0x1800ae4ea  mov     r8d, 5ABh; int
0x1800ae4f0  mov     r9d, ebx; int
0x1800ae4f3  lea     rdx, aCrawimagereade; "CRawImageReader::WriteSubIFDEntry"
0x1800ae4fa  mov     rcx, rax; this
0x1800ae4fd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ae502  jmp     loc_1800AE67B
0x1800ae507  mov     eax, [rbp+57h+var_84]
0x1800ae50a  add     [r15], rax
0x1800ae50d  movzx   r13d, di
0x1800ae511  lea     eax, ds:0[r13*2]
0x1800ae519  add     eax, r13d
0x1800ae51c  lea     eax, ds:6[rax*4]
0x1800ae523  add     [r12], eax
0x1800ae527  xor     edi, edi
0x1800ae529  cmp     edi, r13d
0x1800ae52c  jnb     loc_1800AE5D3
0x1800ae532  mov     edx, edi
0x1800ae534  mov     rcx, [rbp+57h+var_80]
0x1800ae538  call    ?at@?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@QEAAAEAUIFDDataEntry@CRawImageReader@@_K@Z; std::vector<CRawImageReader::IFDDataEntry>::at(unsigned __int64)
0x1800ae53d  mov     r9, r12; unsigned int *
0x1800ae540  mov     r8, r15; union _LARGE_INTEGER *
0x1800ae543  mov     rdx, rax; struct CRawImageReader::IFDDataEntry *
0x1800ae546  mov     rcx, rsi; this
0x1800ae549  call    ?WriteOneIFDEntryToStream@CRawImageReader@@AEAAJAEAUIFDDataEntry@1@PEAT_LARGE_INTEGER@@PEAI@Z; CRawImageReader::WriteOneIFDEntryToStream(CRawImageReader::IFDDataEntry &,_LARGE_INTEGER *,uint *)
0x1800ae54e  mov     ebx, eax
0x1800ae550  test    eax, eax
0x1800ae552  js      short loc_1800AE558
0x1800ae554  inc     edi
0x1800ae556  jmp     short loc_1800AE529
0x1800ae558  lea     rax, WPP_GLOBAL_Control
0x1800ae55f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae566  cmp     rcx, rax
0x1800ae569  jz      short loc_1800AE593
0x1800ae56b  test    byte ptr [rcx+1Ch], 1
0x1800ae56f  jz      short loc_1800AE593
0x1800ae571  cmp     byte ptr [rcx+19h], 4
0x1800ae575  jb      short loc_1800AE593
0x1800ae577  mov     edx, 7Fh
0x1800ae57c  mov     [rsp+0C0h+var_A0], ebx
0x1800ae580  mov     r9d, [r14]
0x1800ae583  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ae58a  mov     rcx, [rcx+10h]
0x1800ae58e  call    WPP_SF_Dd
0x1800ae593  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae59a  test    rcx, rcx
0x1800ae59d  jnz     short loc_1800AE5AD
0x1800ae59f  lea     rcx, off_1800E5190; this
0x1800ae5a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae5ad  cmp     byte ptr [rcx+8], 0
0x1800ae5b1  jz      loc_1800AE67B
0x1800ae5b7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae5bc  cmp     [rax+7CCh], ebx
0x1800ae5c2  jz      loc_1800AE67B
0x1800ae5c8  mov     r8d, 5B2h
0x1800ae5ce  jmp     loc_1800AE4F0
0x1800ae5d3  mov     [rbp+57h+var_88], 0
0x1800ae5da  mov     rcx, [rsi+0F8h]
0x1800ae5e1  mov     rax, [rcx]
0x1800ae5e4  lea     r9, [rbp+57h+var_84]
0x1800ae5e8  mov     r8d, 4
0x1800ae5ee  lea     rdx, [rbp+57h+var_88]
0x1800ae5f2  mov     rax, [rax+20h]
0x1800ae5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae5fb  mov     ebx, eax
0x1800ae5fd  test    eax, eax
0x1800ae5ff  jns     short loc_1800AE674
0x1800ae601  lea     rax, WPP_GLOBAL_Control
0x1800ae608  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae60f  cmp     rcx, rax
0x1800ae612  jz      short loc_1800AE63C
0x1800ae614  test    byte ptr [rcx+1Ch], 1
0x1800ae618  jz      short loc_1800AE63C
0x1800ae61a  cmp     byte ptr [rcx+19h], 4
0x1800ae61e  jb      short loc_1800AE63C
0x1800ae620  mov     edx, 80h
0x1800ae625  mov     [rsp+0C0h+var_A0], ebx
0x1800ae629  mov     r9d, [r14]
0x1800ae62c  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ae633  mov     rcx, [rcx+10h]
0x1800ae637  call    WPP_SF_Dd
0x1800ae63c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae643  test    rcx, rcx
0x1800ae646  jnz     short loc_1800AE656
0x1800ae648  lea     rcx, off_1800E5190; this
0x1800ae64f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae656  cmp     byte ptr [rcx+8], 0
0x1800ae65a  jz      short loc_1800AE67B
0x1800ae65c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae661  cmp     [rax+7CCh], ebx
0x1800ae667  jz      short loc_1800AE67B
0x1800ae669  mov     r8d, 5B6h
0x1800ae66f  jmp     loc_1800AE4F0
0x1800ae674  mov     eax, [r12]
0x1800ae678  mov     [r15], rax
0x1800ae67b  lea     rcx, [rbp+57h+var_70]; this
0x1800ae67f  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800ae684  nop
0x1800ae685  lea     rcx, [rbp+57h+var_8C]; this
0x1800ae689  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ae68e  mov     eax, ebx
0x1800ae690  mov     rcx, [rbp+57h+var_50]
0x1800ae694  xor     rcx, rsp; StackCookie
0x1800ae697  call    __security_check_cookie
0x1800ae69c  add     rsp, 88h
0x1800ae6a3  pop     r15
0x1800ae6a5  pop     r14
0x1800ae6a7  pop     r13
0x1800ae6a9  pop     r12
0x1800ae6ab  pop     rdi
0x1800ae6ac  pop     rsi
0x1800ae6ad  pop     rbx
0x1800ae6ae  pop     rbp
0x1800ae6af  retn
```
