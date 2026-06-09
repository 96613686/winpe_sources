# CRawImageReader::GetImage(tagRECT *,uint,uint,uchar *)

- ea: `0x1800aa7f0`
- end: `0x1800aac8a`
- name: `?GetImage@CRawImageReader@@UEAAJPEAUtagRECT@@IIPEAE@Z`
- size: `1178`
- prototype: `__int64 __fastcall(CRawImageReader *this, struct tagRECT *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x180001220`
- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009b9e4`
- `0x18009e8b8`
- `0x1800a2db4`
- `0x1800a34f8`
- `0x1800a6d94`
- `0x1800a8588`
- `0x1800aa7f0`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aaada`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aab7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aaada`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aab7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aa8fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aa8fe`
- `MFPlat!MFGetSystemTime` at `0x1800aa83e`
- `MFPlat!MFGetSystemTime` at `0x1800aabab`
- `MFPlat!MFGetSystemTime` at `0x1800aa83e`
- `MFPlat!MFGetSystemTime` at `0x1800aabab`

## string_xrefs

- `0x1800aa855`: `CRawImageReader::GetImage`
- `0x1800aa8dd`: `CRawImageReader::GetImage`
- `0x1800aaa08`: `CRawImageReader::GetImage`
- `0x1800aab68`: `CRawImageReader::GetImage`

## pseudocode

```c
__int64 __fastcall CRawImageReader::GetImage(
        CRawImageReader *this,
        struct tagRECT *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  int *v9; // r9
  struct CallStackContext *ThreadRelativeContext; // rbx
  int v11; // edi
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  unsigned int *v15; // r15
  int v16; // eax
  int v17; // edi
  void ***v18; // rcx
  struct CallStackContext *v19; // rax
  int v20; // r8d
  unsigned __int64 v21; // r8
  int v22; // eax
  void ***v23; // rcx
  void ***v24; // rcx
  struct CallStackContext *v25; // rax
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  MFTIME v29; // rax
  MFTIME v30; // rbx
  const char *v31; // r9
  __int64 result; // rax
  int v33; // [rsp+20h] [rbp-A8h]
  unsigned int v34; // [rsp+28h] [rbp-A0h]
  _BYTE v35[8]; // [rsp+40h] [rbp-88h] BYREF
  CRawImageReader *v36; // [rsp+48h] [rbp-80h] BYREF
  unsigned __int8 *v37; // [rsp+50h] [rbp-78h] BYREF
  MFTIME v38; // [rsp+58h] [rbp-70h]
  __int64 v39; // [rsp+60h] [rbp-68h]
  _BYTE v40[32]; // [rsp+68h] [rbp-60h] BYREF
  char *v41; // [rsp+88h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v39 = -2;
  v37 = a5;
  try
  {
    v38 = MFGetSystemTime();
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v35, "CRawImageReader::GetImage", 529);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
      *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, char **))(**((_QWORD **)this + 34) + 280LL))(
                                                              *((_QWORD *)this + 34),
                                                              &v41);
      *((_DWORD *)ThreadRelativeContext + 504) = v11;
    }
    CTraceBase::CAutoTrace::CAutoTrace(
      (CTraceBase::CAutoTrace *)v40,
      (struct CTraceBase *)(((unsigned __int64)this + 56) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
      "CRawImageReader::GetImage",
      v9,
      v33);
    v41 = (char *)this + 64;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    v14 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v15 = (unsigned int *)((char *)this + 56);
    }
    else
    {
      v34 = a4;
      v15 = (unsigned int *)((char *)this + 56);
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *((unsigned int *)this + 14),
        a3);
    }
    if ( (unsigned int)dword_1800E50F0 > 4 )
    {
      v36 = this;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        v14,
        (unsigned int)&byte_1800D7547,
        v12,
        v13,
        (__int64)&v36);
    }
    v16 = CRawImageReader::DecodeImage(this);
    v17 = v16;
    if ( v16 >= 0 )
    {
      v21 = 3LL * *((unsigned int *)this + 28);
      if ( v21 > 0xFFFFFFFF )
      {
        v17 = -2147024362;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *v15,
            -2147024362);
        }
        v24 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)v25 + 499) != -2147024362 )
            CallStackContext::TraceFailure(v25, "CRawImageReader::GetImage", 544, -2147024362);
        }
        goto LABEL_43;
      }
      v22 = CRawImageReader::CopyBuffer(this, (unsigned __int8 *)(*((_QWORD *)this + 17) + 16LL), v21, a2, a3, v34, v37);
      v17 = v22;
      if ( v22 >= 0 )
        goto LABEL_43;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v15, v22);
      }
      v23 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v23 + 8)
        || (v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23), *((_DWORD *)v19 + 499) == v17) )
      {
LABEL_43:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
        if ( (unsigned int)dword_1800E50F0 > 4 )
        {
          v37 = (unsigned __int8 *)this;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
            v26,
            (unsigned int)byte_1800D7515,
            v27,
            v28,
            (__int64)&v37);
        }
        v29 = MFGetSystemTime();
        v30 = v29 - v38;
        if ( v17 >= 0 )
        {
          (*(void (__fastcall **)(char *, MFTIME))(*((_QWORD *)this + 75) + 16LL))((char *)this + 600, v29 - v38);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_DDD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              35,
              &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
              *v15,
              v17);
          }
          (*(void (__fastcall **)(char *, MFTIME))(*((_QWORD *)this + 84) + 16LL))((char *)this + 672, v30);
          if ( *((int *)this + 146) >= 0 )
            *((_DWORD *)this + 146) = v17;
        }
        CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v40);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v35);
        return (unsigned int)v17;
      }
      v20 = 545;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v15, v16);
      }
      v18 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v18 + 8) )
        goto LABEL_43;
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)v19 + 499) == v17 )
        goto LABEL_43;
      v20 = 541;
    }
    CallStackContext::TraceFailure(v19, "CRawImageReader::GetImage", v20, v17);
    goto LABEL_43;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x23F,
                           (unsigned int)"avcore\\mf\\rawimage\\rawimagereader\\rawimagereader.cpp",
                           v31);
  }
  return result;
}

```

## disassembly

```asm
0x1800aa7f0  mov     rax, rsp
0x1800aa7f3  push    rdi
0x1800aa7f4  push    r12
0x1800aa7f6  push    r13
0x1800aa7f8  push    r14
0x1800aa7fa  push    r15
0x1800aa7fc  sub     rsp, 0A0h
0x1800aa803  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x1800aa80b  mov     [rax+18h], rbx
0x1800aa80f  mov     [rax+20h], rsi
0x1800aa813  mov     rax, cs:__security_cookie
0x1800aa81a  xor     rax, rsp
0x1800aa81d  mov     [rsp+0C8h+var_30], rax
0x1800aa825  mov     r15d, r9d
0x1800aa828  mov     r12d, r8d
0x1800aa82b  mov     r13, rdx
0x1800aa82e  mov     rsi, rcx
0x1800aa831  mov     rax, [rsp+0C8h+arg_20]
0x1800aa839  mov     [rsp+0C8h+var_78], rax
0x1800aa83e  call    cs:__imp_MFGetSystemTime
0x1800aa845  nop     dword ptr [rax+rax+00h]
0x1800aa84a  mov     [rsp+0C8h+var_70], rax
0x1800aa84f  mov     r8d, 211h; int
0x1800aa855  lea     rdx, aCrawimagereade_5; "CRawImageReader::GetImage"
0x1800aa85c  lea     rcx, [rsp+0C8h+var_88]; this
0x1800aa861  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800aa866  nop
0x1800aa867  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800aa86e  cmp     byte ptr [rcx+8], 0
0x1800aa872  jz      short loc_1800AA8CD
0x1800aa874  cmp     qword ptr [rsi+110h], 0
0x1800aa87c  jz      short loc_1800AA8CD
0x1800aa87e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aa883  mov     rbx, rax
0x1800aa886  mov     rcx, [rsi+110h]
0x1800aa88d  mov     rdx, [rcx]
0x1800aa890  mov     rax, [rdx+128h]
0x1800aa897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa89c  mov     edi, eax
0x1800aa89e  mov     rcx, [rsi+110h]
0x1800aa8a5  mov     rdx, [rcx]
0x1800aa8a8  mov     rax, [rdx+118h]
0x1800aa8af  lea     rdx, [rsp+0C8h+var_40]
0x1800aa8b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa8bc  movups  xmm0, xmmword ptr [rax]
0x1800aa8bf  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x1800aa8c7  mov     [rbx+7E0h], edi
0x1800aa8cd  lea     rcx, [rsi+38h]
0x1800aa8d1  mov     rax, rsi
0x1800aa8d4  neg     rax
0x1800aa8d7  sbb     rdx, rdx
0x1800aa8da  and     rdx, rcx; struct CTraceBase *
0x1800aa8dd  lea     r8, aCrawimagereade_5; "CRawImageReader::GetImage"
0x1800aa8e4  lea     rcx, [rsp+0C8h+var_60]; this
0x1800aa8e9  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800aa8ee  nop
0x1800aa8ef  lea     rbx, [rsi+40h]
0x1800aa8f3  mov     [rsp+0C8h+var_40], rbx
0x1800aa8fb  mov     rcx, rbx; lpCriticalSection
0x1800aa8fe  call    cs:__imp_EnterCriticalSection
0x1800aa905  nop     dword ptr [rax+rax+00h]
0x1800aa90a  nop
0x1800aa90b  lea     rax, WPP_GLOBAL_Control
0x1800aa912  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa919  mov     r14b, 1
0x1800aa91c  cmp     rcx, rax
0x1800aa91f  jz      short loc_1800AA955
0x1800aa921  test    [rcx+1Ch], r14b
0x1800aa925  jz      short loc_1800AA955
0x1800aa927  cmp     byte ptr [rcx+19h], 4
0x1800aa92b  jb      short loc_1800AA955
0x1800aa92d  mov     edx, 1Fh
0x1800aa932  mov     [rsp+0C8h+var_A0], r15d
0x1800aa937  mov     [rsp+0C8h+var_A8], r12d
0x1800aa93c  lea     r15, [rsi+38h]
0x1800aa940  mov     r9d, [r15]
0x1800aa943  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800aa94a  mov     rcx, [rcx+10h]
0x1800aa94e  call    WPP_SF_DDD
0x1800aa953  jmp     short loc_1800AA959
0x1800aa955  lea     r15, [rsi+38h]
0x1800aa959  cmp     cs:dword_1800E50F0, 4
0x1800aa960  jbe     short loc_1800AA97D
0x1800aa962  mov     [rsp+0C8h+var_80], rsi
0x1800aa967  lea     rax, [rsp+0C8h+var_80]
0x1800aa96c  mov     qword ptr [rsp+0C8h+var_A8], rax
0x1800aa971  lea     rdx, byte_1800D7547
0x1800aa978  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800aa97d  mov     rcx, rsi; this
0x1800aa980  call    ?DecodeImage@CRawImageReader@@AEAAJXZ; CRawImageReader::DecodeImage(void)
0x1800aa985  mov     edi, eax
0x1800aa987  test    eax, eax
0x1800aa989  jns     loc_1800AAA1C
0x1800aa98f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa996  lea     r12, WPP_GLOBAL_Control
0x1800aa99d  cmp     rcx, r12
0x1800aa9a0  jz      short loc_1800AA9CA
0x1800aa9a2  test    [rcx+1Ch], r14b
0x1800aa9a6  jz      short loc_1800AA9CA
0x1800aa9a8  cmp     byte ptr [rcx+19h], 4
0x1800aa9ac  jb      short loc_1800AA9CA
0x1800aa9ae  mov     edx, 20h ; ' '
0x1800aa9b3  mov     [rsp+0C8h+var_A8], eax
0x1800aa9b7  mov     r9d, [r15]
0x1800aa9ba  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800aa9c1  mov     rcx, [rcx+10h]
0x1800aa9c5  call    WPP_SF_Dd
0x1800aa9ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aa9d1  test    rcx, rcx
0x1800aa9d4  jnz     short loc_1800AA9E4
0x1800aa9d6  lea     rcx, off_1800E5190; this
0x1800aa9dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aa9e4  cmp     byte ptr [rcx+8], 0
0x1800aa9e8  jz      loc_1800AAB78
0x1800aa9ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aa9f3  cmp     [rax+7CCh], edi
0x1800aa9f9  jz      loc_1800AAB78
0x1800aa9ff  mov     r8d, 21Dh; int
0x1800aaa05  mov     r9d, edi; int
0x1800aaa08  lea     rdx, aCrawimagereade_5; "CRawImageReader::GetImage"
0x1800aaa0f  mov     rcx, rax; this
0x1800aaa12  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aaa17  jmp     loc_1800AAB78
0x1800aaa1c  mov     eax, [rsi+70h]
0x1800aaa1f  lea     r8, [rax+rax*2]; unsigned int
0x1800aaa23  mov     eax, 0FFFFFFFFh
0x1800aaa28  cmp     r8, rax
0x1800aaa2b  ja      loc_1800AAAF2
0x1800aaa31  mov     rdx, [rsi+88h]
0x1800aaa38  add     rdx, 10h; unsigned __int8 *
0x1800aaa3c  mov     rax, [rsp+0C8h+var_78]
0x1800aaa41  mov     [rsp+0C8h+var_98], rax; unsigned __int8 *
0x1800aaa46  mov     [rsp+0C8h+var_A8], r12d; unsigned int
0x1800aaa4b  mov     r9, r13; struct tagRECT *
0x1800aaa4e  mov     rcx, rsi; this
0x1800aaa51  call    ?CopyBuffer@CRawImageReader@@AEAAJPEAEIPEAUtagRECT@@II0@Z; CRawImageReader::CopyBuffer(uchar *,uint,tagRECT *,uint,uint,uchar *)
0x1800aaa56  mov     edi, eax
0x1800aaa58  test    eax, eax
0x1800aaa5a  jns     short loc_1800AAAD7
0x1800aaa5c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaa63  lea     r12, WPP_GLOBAL_Control
0x1800aaa6a  cmp     rcx, r12
0x1800aaa6d  jz      short loc_1800AAA97
0x1800aaa6f  test    [rcx+1Ch], r14b
0x1800aaa73  jz      short loc_1800AAA97
0x1800aaa75  cmp     byte ptr [rcx+19h], 4
0x1800aaa79  jb      short loc_1800AAA97
0x1800aaa7b  mov     edx, 22h ; '"'
0x1800aaa80  mov     [rsp+0C8h+var_A8], eax
0x1800aaa84  mov     r9d, [r15]
0x1800aaa87  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800aaa8e  mov     rcx, [rcx+10h]
0x1800aaa92  call    WPP_SF_Dd
0x1800aaa97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aaa9e  test    rcx, rcx
0x1800aaaa1  jnz     short loc_1800AAAB1
0x1800aaaa3  lea     rcx, off_1800E5190; this
0x1800aaaaa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aaab1  cmp     byte ptr [rcx+8], 0
0x1800aaab5  jz      loc_1800AAB78
0x1800aaabb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aaac0  cmp     [rax+7CCh], edi
0x1800aaac6  jz      loc_1800AAB78
0x1800aaacc  mov     r8d, 221h
0x1800aaad2  jmp     loc_1800AAA05
0x1800aaad7  mov     rcx, rbx; lpCriticalSection
0x1800aaada  call    cs:__imp_LeaveCriticalSection
0x1800aaae1  nop     dword ptr [rax+rax+00h]
0x1800aaae6  lea     r12, WPP_GLOBAL_Control
0x1800aaaed  jmp     loc_1800AAB87
0x1800aaaf2  mov     edi, 80070216h
0x1800aaaf7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaafe  lea     r12, WPP_GLOBAL_Control
0x1800aab05  cmp     rcx, r12
0x1800aab08  jz      short loc_1800AAB32
0x1800aab0a  test    [rcx+1Ch], r14b
0x1800aab0e  jz      short loc_1800AAB32
0x1800aab10  cmp     byte ptr [rcx+19h], 4
0x1800aab14  jb      short loc_1800AAB32
0x1800aab16  mov     edx, 21h ; '!'
0x1800aab1b  mov     [rsp+0C8h+var_A8], edi
0x1800aab1f  mov     r9d, [r15]
0x1800aab22  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800aab29  mov     rcx, [rcx+10h]
0x1800aab2d  call    WPP_SF_Dd
0x1800aab32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aab39  test    rcx, rcx
0x1800aab3c  jnz     short loc_1800AAB4C
0x1800aab3e  lea     rcx, off_1800E5190; this
0x1800aab45  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aab4c  cmp     byte ptr [rcx+8], 0
0x1800aab50  jz      short loc_1800AAB78
0x1800aab52  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aab57  cmp     [rax+7CCh], edi
0x1800aab5d  jz      short loc_1800AAB78
0x1800aab5f  mov     r9d, edi; int
0x1800aab62  mov     r8d, 220h; int
0x1800aab68  lea     rdx, aCrawimagereade_5; "CRawImageReader::GetImage"
0x1800aab6f  mov     rcx, rax; this
0x1800aab72  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aab77  nop
0x1800aab78  mov     rcx, rbx; lpCriticalSection
0x1800aab7b  call    cs:__imp_LeaveCriticalSection
0x1800aab82  nop     dword ptr [rax+rax+00h]
0x1800aab87  cmp     cs:dword_1800E50F0, 4
0x1800aab8e  jbe     short loc_1800AABAB
0x1800aab90  mov     [rsp+0C8h+var_78], rsi
0x1800aab95  lea     rax, [rsp+0C8h+var_78]
0x1800aab9a  mov     qword ptr [rsp+0C8h+var_A8], rax
0x1800aab9f  lea     rdx, byte_1800D7515
0x1800aaba6  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800aabab  call    cs:__imp_MFGetSystemTime
0x1800aabb2  nop     dword ptr [rax+rax+00h]
0x1800aabb7  mov     rbx, rax
0x1800aabba  sub     rbx, [rsp+0C8h+var_70]
0x1800aabbf  test    edi, edi
0x1800aabc1  jns     short loc_1800AAC28
0x1800aabc3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aabca  cmp     rcx, r12
0x1800aabcd  jz      short loc_1800AAC01
0x1800aabcf  test    [rcx+1Ch], r14b
0x1800aabd3  jz      short loc_1800AAC01
0x1800aabd5  cmp     byte ptr [rcx+19h], 4
0x1800aabd9  jb      short loc_1800AAC01
0x1800aabdb  mov     edx, 23h ; '#'
0x1800aabe0  mov     eax, [rsi+248h]
0x1800aabe6  mov     [rsp+0C8h+var_A0], eax
0x1800aabea  mov     [rsp+0C8h+var_A8], edi
0x1800aabee  mov     r9d, [r15]
0x1800aabf1  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800aabf8  mov     rcx, [rcx+10h]
0x1800aabfc  call    WPP_SF_DDD
0x1800aac01  lea     rcx, [rsi+2A0h]
0x1800aac08  mov     rax, [rcx]
0x1800aac0b  mov     rdx, rbx
0x1800aac0e  mov     rax, [rax+10h]
0x1800aac12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aac17  cmp     dword ptr [rsi+248h], 0
0x1800aac1e  jl      short loc_1800AAC3F
0x1800aac20  mov     [rsi+248h], edi
0x1800aac26  jmp     short loc_1800AAC3F
0x1800aac28  lea     rcx, [rsi+258h]
0x1800aac2f  mov     rax, [rcx]
0x1800aac32  mov     rdx, rbx
0x1800aac35  mov     rax, [rax+10h]
0x1800aac39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aac3e  nop
0x1800aac3f  lea     rcx, [rsp+0C8h+var_60]; this
0x1800aac44  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800aac49  nop
0x1800aac4a  lea     rcx, [rsp+0C8h+var_88]; this
0x1800aac4f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800aac54  mov     eax, edi
0x1800aac56  jmp     short loc_1800AAC5C
0x1800aac58  mov     eax, dword ptr [rsp+0C8h+var_80]
0x1800aac5c  mov     rcx, [rsp+0C8h+var_30]
0x1800aac64  xor     rcx, rsp; StackCookie
0x1800aac67  call    __security_check_cookie
0x1800aac6c  lea     r11, [rsp+0C8h+var_28]
0x1800aac74  mov     rbx, [r11+40h]
0x1800aac78  mov     rsi, [r11+48h]
0x1800aac7c  mov     rsp, r11
0x1800aac7f  pop     r15
0x1800aac81  pop     r14
0x1800aac83  pop     r13
0x1800aac85  pop     r12
0x1800aac87  pop     rdi
0x1800aac88  retn
```
