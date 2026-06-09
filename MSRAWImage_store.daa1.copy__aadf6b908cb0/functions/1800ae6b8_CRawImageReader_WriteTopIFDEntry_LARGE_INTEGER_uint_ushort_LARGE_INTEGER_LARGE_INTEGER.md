# CRawImageReader::WriteTopIFDEntry(_LARGE_INTEGER *,uint *,ushort,_LARGE_INTEGER *,_LARGE_INTEGER *)

- ea: `0x1800ae6b8`
- end: `0x1800aed92`
- name: `?WriteTopIFDEntry@CRawImageReader@@AEAAJPEAT_LARGE_INTEGER@@PEAIG00@Z`
- size: `1754`
- prototype: `__int64 __usercall@<rax>(CRawImageReader *__hidden this@<rcx>, union _LARGE_INTEGER *@<rdx>, unsigned int *@<r8>, unsigned __int16@<r9w>, union _LARGE_INTEGER *, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `15`
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
- `0x1800a713c`
- `0x1800adcb0`
- `0x1800ae6b8`
- `0x1800af278`
- `0x1800af388`
- `0x1800af3f0`
- `0x1800b4010`

## string_xrefs

- `0x1800ae70e`: `CRawImageReader::WriteTopIFDEntry`
- `0x1800ae791`: `CRawImageReader::WriteTopIFDEntry`
- `0x1800ae86e`: `CRawImageReader::WriteTopIFDEntry`
- `0x1800aea4b`: `CRawImageReader::WriteTopIFDEntry`
- `0x1800aebf5`: `CRawImageReader::WriteTopIFDEntry`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRawImageReader::WriteTopIFDEntry(
        CRawImageReader *this,
        union _LARGE_INTEGER *a2,
        unsigned int *a3,
        unsigned __int16 a4,
        union _LARGE_INTEGER *a5,
        union _LARGE_INTEGER *a6)
{
  int v6; // r13d
  int *v10; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v12; // ebx
  unsigned int *v13; // r14
  int OneIFDEntry; // ebx
  void ***v15; // rcx
  struct CallStackContext *v16; // rax
  int v17; // r8d
  unsigned int i; // r13d
  struct CRawImageReader::IFDDataEntry *v19; // rax
  void ***v20; // rcx
  void ***v21; // rcx
  struct CallStackContext *v22; // rax
  int v23; // r8d
  void ***v24; // rcx
  void ***v25; // rcx
  struct CallStackContext *v26; // rax
  int v27; // r8d
  void ***v28; // rcx
  void ***v29; // rcx
  int v31; // [rsp+28h] [rbp-89h]
  size_t Size; // [rsp+38h] [rbp-79h]
  __int16 v33; // [rsp+48h] [rbp-69h] BYREF
  _BYTE v34[4]; // [rsp+4Ch] [rbp-65h] BYREF
  int v35; // [rsp+50h] [rbp-61h] BYREF
  int v36; // [rsp+54h] [rbp-5Dh] BYREF
  union _LARGE_INTEGER *v37; // [rsp+58h] [rbp-59h]
  union _LARGE_INTEGER *v38; // [rsp+60h] [rbp-51h]
  __int64 v39; // [rsp+68h] [rbp-49h]
  _BYTE v40[8]; // [rsp+70h] [rbp-41h] BYREF
  int v41; // [rsp+78h] [rbp-39h]
  __int128 v42; // [rsp+80h] [rbp-31h] BYREF
  __int64 v43; // [rsp+90h] [rbp-21h]
  _BYTE v44[32]; // [rsp+98h] [rbp-19h] BYREF

  v39 = -2;
  v6 = a4;
  v38 = a6;
  v37 = a5;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v34, "CRawImageReader::WriteTopIFDEntry", 1268);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            v44);
    *((_DWORD *)ThreadRelativeContext + 504) = v12;
  }
  v13 = (unsigned int *)((char *)this + 56);
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v44,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    "CRawImageReader::WriteTopIFDEntry",
    v10,
    v31);
  if ( *((_BYTE *)this + 107) )
  {
    LOBYTE(v33) = BYTE1(v6);
    HIBYTE(v33) = v6;
  }
  else
  {
    v33 = v6;
  }
  v36 = 0;
  OneIFDEntry = (*(__int64 (__fastcall **)(_QWORD, __int16 *, __int64, int *))(**((_QWORD **)this + 31) + 32LL))(
                  *((_QWORD *)this + 31),
                  &v33,
                  2,
                  &v36);
  if ( OneIFDEntry < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        109,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *v13,
        OneIFDEntry);
    }
    v15 = (void ***)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( !*((_BYTE *)v15 + 8) )
      goto LABEL_90;
    v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
    if ( *((_DWORD *)v16 + 499) == OneIFDEntry )
      goto LABEL_90;
    v17 = 1273;
LABEL_17:
    CallStackContext::TraceFailure(v16, "CRawImageReader::WriteTopIFDEntry", v17, OneIFDEntry);
    goto LABEL_90;
  }
  a2->QuadPart += 2LL;
  *a3 += 12 * v6 + 6;
  for ( i = 0; i < 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 26) - *((_QWORD *)this + 25)) >> 3); ++i )
  {
    v19 = (struct CRawImageReader::IFDDataEntry *)std::vector<CRawImageReader::IFDDataEntry>::at();
    OneIFDEntry = CRawImageReader::WriteOneIFDEntryToStream(this, v19, a2, a3);
    if ( OneIFDEntry < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          110,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *v13,
          OneIFDEntry);
      }
      v20 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v16 + 499) != OneIFDEntry )
        {
          v17 = 1283;
          goto LABEL_17;
        }
      }
      goto LABEL_90;
    }
  }
  std::vector<CRawImageReader::IFDDataEntry>::clear((char *)this + 200);
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 20) - *((_QWORD *)this + 19)) >> 3) )
  {
    v41 = 0;
    v42 = 0;
    v43 = 0;
    LODWORD(Size) = 0;
    OneIFDEntry = CRawImageReader::CreateOneIFDEntry(
                    this,
                    34665,
                    4u,
                    1,
                    0,
                    (struct CRawImageReader::IFDDataEntry *)v40,
                    Size,
                    0);
    if ( OneIFDEntry < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          111,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *v13,
          OneIFDEntry);
      }
      v21 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v21 + 8) )
        goto LABEL_43;
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
      if ( *((_DWORD *)v22 + 499) == OneIFDEntry )
        goto LABEL_43;
      v23 = 1294;
      goto LABEL_42;
    }
    OneIFDEntry = CRawImageReader::WriteOneIFDEntryToStream(this, (struct CRawImageReader::IFDDataEntry *)v40, a2, a3);
    if ( OneIFDEntry < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          112,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *v13,
          OneIFDEntry);
      }
      v24 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v24 + 8) )
        goto LABEL_43;
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
      if ( *((_DWORD *)v22 + 499) == OneIFDEntry )
        goto LABEL_43;
      v23 = 1295;
LABEL_42:
      CallStackContext::TraceFailure(v22, "CRawImageReader::WriteTopIFDEntry", v23, OneIFDEntry);
LABEL_43:
      std::vector<unsigned char>::_Tidy(&v42);
      goto LABEL_90;
    }
    v37->QuadPart = a2->QuadPart - 4;
    std::vector<unsigned char>::_Tidy(&v42);
  }
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 23) - *((_QWORD *)this + 22)) >> 3) )
  {
    v41 = 0;
    v42 = 0;
    v43 = 0;
    LODWORD(Size) = 0;
    OneIFDEntry = CRawImageReader::CreateOneIFDEntry(
                    this,
                    34853,
                    4u,
                    1,
                    0,
                    (struct CRawImageReader::IFDDataEntry *)v40,
                    Size,
                    0);
    if ( OneIFDEntry < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          113,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *v13,
          OneIFDEntry);
      }
      v25 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v25 + 8) )
        goto LABEL_43;
      v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
      if ( *((_DWORD *)v26 + 499) == OneIFDEntry )
        goto LABEL_43;
      v27 = 1306;
      goto LABEL_66;
    }
    OneIFDEntry = CRawImageReader::WriteOneIFDEntryToStream(this, (struct CRawImageReader::IFDDataEntry *)v40, a2, a3);
    if ( OneIFDEntry < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          114,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *v13,
          OneIFDEntry);
      }
      v28 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v28 + 8) )
        goto LABEL_43;
      v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
      if ( *((_DWORD *)v26 + 499) == OneIFDEntry )
        goto LABEL_43;
      v27 = 1307;
LABEL_66:
      CallStackContext::TraceFailure(v26, "CRawImageReader::WriteTopIFDEntry", v27, OneIFDEntry);
      goto LABEL_43;
    }
    v38->QuadPart = a2->QuadPart - 4;
    std::vector<unsigned char>::_Tidy(&v42);
  }
  v35 = 0;
  OneIFDEntry = (*(__int64 (__fastcall **)(_QWORD, int *, __int64, int *))(**((_QWORD **)this + 31) + 32LL))(
                  *((_QWORD *)this + 31),
                  &v35,
                  4,
                  &v36);
  if ( OneIFDEntry >= 0 )
  {
    a2->QuadPart = *a3;
    goto LABEL_90;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      115,
      &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
      *v13,
      OneIFDEntry);
  }
  v29 = (void ***)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v29 = &off_1800E5190;
    CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
  }
  if ( *((_BYTE *)v29 + 8) )
  {
    v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
    if ( *((_DWORD *)v16 + 499) != OneIFDEntry )
    {
      v17 = 1313;
      goto LABEL_17;
    }
  }
LABEL_90:
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v44);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v34);
  return (unsigned int)OneIFDEntry;
}

```

## disassembly

```asm
0x1800ae6b8  mov     rax, rsp
0x1800ae6bb  push    rbp
0x1800ae6bc  push    rsi
0x1800ae6bd  push    rdi
0x1800ae6be  push    r12
0x1800ae6c0  push    r13
0x1800ae6c2  push    r14
0x1800ae6c4  push    r15
0x1800ae6c6  lea     rbp, [rax-4Fh]
0x1800ae6ca  sub     rsp, 0C0h
0x1800ae6d1  mov     [rbp+47h+var_90], 0FFFFFFFFFFFFFFFEh
0x1800ae6d9  mov     [rax+20h], rbx
0x1800ae6dd  mov     rax, cs:__security_cookie
0x1800ae6e4  xor     rax, rsp
0x1800ae6e7  mov     [rbp+47h+var_40], rax
0x1800ae6eb  movzx   r13d, r9w
0x1800ae6ef  mov     r12, r8
0x1800ae6f2  mov     r15, rdx
0x1800ae6f5  mov     rsi, rcx
0x1800ae6f8  mov     rax, [rbp+47h+arg_28]
0x1800ae6fc  mov     [rbp+47h+var_98], rax
0x1800ae700  mov     rax, [rbp+47h+arg_20]
0x1800ae704  mov     [rbp+47h+var_A0], rax
0x1800ae708  mov     r8d, 4F4h; int
0x1800ae70e  lea     rdx, aCrawimagereade_9; "CRawImageReader::WriteTopIFDEntry"
0x1800ae715  lea     rcx, [rbp+47h+var_AC]; this
0x1800ae719  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ae71e  nop
0x1800ae71f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ae726  cmp     byte ptr [rcx+8], 0
0x1800ae72a  jz      short loc_1800AE781
0x1800ae72c  cmp     qword ptr [rsi+110h], 0
0x1800ae734  jz      short loc_1800AE781
0x1800ae736  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae73b  mov     rdi, rax
0x1800ae73e  mov     rcx, [rsi+110h]
0x1800ae745  mov     rdx, [rcx]
0x1800ae748  mov     rax, [rdx+128h]
0x1800ae74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae754  mov     ebx, eax
0x1800ae756  mov     rcx, [rsi+110h]
0x1800ae75d  mov     rdx, [rcx]
0x1800ae760  mov     rax, [rdx+118h]
0x1800ae767  lea     rdx, [rbp+47h+var_60]
0x1800ae76b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae770  movups  xmm0, xmmword ptr [rax]
0x1800ae773  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800ae77b  mov     [rdi+7E0h], ebx
0x1800ae781  lea     r14, [rsi+38h]
0x1800ae785  mov     rax, rsi
0x1800ae788  neg     rax
0x1800ae78b  sbb     rdx, rdx
0x1800ae78e  and     rdx, r14; struct CTraceBase *
0x1800ae791  lea     r8, aCrawimagereade_9; "CRawImageReader::WriteTopIFDEntry"
0x1800ae798  lea     rcx, [rbp+47h+var_60]; this
0x1800ae79c  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800ae7a1  nop
0x1800ae7a2  movzx   eax, r13w
0x1800ae7a6  shr     ax, 8
0x1800ae7aa  cmp     byte ptr [rsi+6Bh], 0
0x1800ae7ae  jnz     short loc_1800AE7B9
0x1800ae7b0  mov     [rbp+47h+var_AF], al
0x1800ae7b3  mov     [rbp+47h+var_B0], r13b
0x1800ae7b7  jmp     short loc_1800AE7C0
0x1800ae7b9  mov     [rbp+47h+var_B0], al
0x1800ae7bc  mov     [rbp+47h+var_AF], r13b
0x1800ae7c0  mov     [rbp+47h+var_A4], 0
0x1800ae7c7  mov     rcx, [rsi+0F8h]
0x1800ae7ce  mov     rax, [rcx]
0x1800ae7d1  lea     r9, [rbp+47h+var_A4]
0x1800ae7d5  mov     r8d, 2
0x1800ae7db  lea     rdx, [rbp+47h+var_B0]
0x1800ae7df  mov     rax, [rax+20h]
0x1800ae7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae7e8  mov     ebx, eax
0x1800ae7ea  test    eax, eax
0x1800ae7ec  jns     loc_1800AE882
0x1800ae7f2  lea     rax, WPP_GLOBAL_Control
0x1800ae7f9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae800  cmp     rcx, rax
0x1800ae803  jz      short loc_1800AE830
0x1800ae805  mov     edi, 1
0x1800ae80a  test    [rcx+1Ch], dil
0x1800ae80e  jz      short loc_1800AE830
0x1800ae810  cmp     byte ptr [rcx+19h], 4
0x1800ae814  jb      short loc_1800AE830
0x1800ae816  lea     edx, [rdi+6Ch]
0x1800ae819  mov     [rsp+0F0h+var_D0], ebx
0x1800ae81d  mov     r9d, [r14]
0x1800ae820  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ae827  mov     rcx, [rcx+10h]
0x1800ae82b  call    WPP_SF_Dd
0x1800ae830  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae837  test    rcx, rcx
0x1800ae83a  jnz     short loc_1800AE84A
0x1800ae83c  lea     rcx, off_1800E5190; this
0x1800ae843  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae84a  cmp     byte ptr [rcx+8], 0
0x1800ae84e  jz      loc_1800AED55
0x1800ae854  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae859  cmp     [rax+7CCh], ebx
0x1800ae85f  jz      loc_1800AED55
0x1800ae865  mov     r8d, 4F9h; int
0x1800ae86b  mov     r9d, ebx; int
0x1800ae86e  lea     rdx, aCrawimagereade_9; "CRawImageReader::WriteTopIFDEntry"
0x1800ae875  mov     rcx, rax; this
0x1800ae878  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ae87d  jmp     loc_1800AED55
0x1800ae882  add     qword ptr [r15], 2
0x1800ae886  lea     ecx, ds:0[r13*2]
0x1800ae88e  add     ecx, r13d
0x1800ae891  lea     ecx, ds:6[rcx*4]
0x1800ae898  add     [r12], ecx
0x1800ae89c  xor     r13d, r13d
0x1800ae89f  lea     edi, [r13+1]
0x1800ae8a3  mov     rbx, 0CCCCCCCCCCCCCCCDh
0x1800ae8ad  lea     rcx, [rsi+0C8h]
0x1800ae8b4  mov     edx, r13d
0x1800ae8b7  mov     rax, [rsi+0D0h]
0x1800ae8be  sub     rax, [rcx]
0x1800ae8c1  sar     rax, 3
0x1800ae8c5  imul    rax, rbx
0x1800ae8c9  cmp     rdx, rax
0x1800ae8cc  jnb     loc_1800AE96E
0x1800ae8d2  call    ?at@?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@QEAAAEAUIFDDataEntry@CRawImageReader@@_K@Z; std::vector<CRawImageReader::IFDDataEntry>::at(unsigned __int64)
0x1800ae8d7  mov     r9, r12; unsigned int *
0x1800ae8da  mov     r8, r15; union _LARGE_INTEGER *
0x1800ae8dd  mov     rdx, rax; struct CRawImageReader::IFDDataEntry *
0x1800ae8e0  mov     rcx, rsi; this
0x1800ae8e3  call    ?WriteOneIFDEntryToStream@CRawImageReader@@AEAAJAEAUIFDDataEntry@1@PEAT_LARGE_INTEGER@@PEAI@Z; CRawImageReader::WriteOneIFDEntryToStream(CRawImageReader::IFDDataEntry &,_LARGE_INTEGER *,uint *)
0x1800ae8e8  mov     ebx, eax
0x1800ae8ea  test    eax, eax
0x1800ae8ec  js      short loc_1800AE8F3
0x1800ae8ee  add     r13d, edi
0x1800ae8f1  jmp     short loc_1800AE8A3
0x1800ae8f3  lea     rax, WPP_GLOBAL_Control
0x1800ae8fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae901  cmp     rcx, rax
0x1800ae904  jz      short loc_1800AE92E
0x1800ae906  test    [rcx+1Ch], dil
0x1800ae90a  jz      short loc_1800AE92E
0x1800ae90c  cmp     byte ptr [rcx+19h], 4
0x1800ae910  jb      short loc_1800AE92E
0x1800ae912  mov     edx, 6Eh ; 'n'
0x1800ae917  mov     [rsp+0F0h+var_D0], ebx
0x1800ae91b  mov     r9d, [r14]
0x1800ae91e  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ae925  mov     rcx, [rcx+10h]
0x1800ae929  call    WPP_SF_Dd
0x1800ae92e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae935  test    rcx, rcx
0x1800ae938  jnz     short loc_1800AE948
0x1800ae93a  lea     rcx, off_1800E5190; this
0x1800ae941  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae948  cmp     byte ptr [rcx+8], 0
0x1800ae94c  jz      loc_1800AED55
0x1800ae952  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae957  cmp     [rax+7CCh], ebx
0x1800ae95d  jz      loc_1800AED55
0x1800ae963  mov     r8d, 503h
0x1800ae969  jmp     loc_1800AE86B
0x1800ae96e  call    ?clear@?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@QEAAXXZ; std::vector<CRawImageReader::IFDDataEntry>::clear(void)
0x1800ae973  mov     rax, [rsi+0A0h]
0x1800ae97a  sub     rax, [rsi+98h]
0x1800ae981  sar     rax, 3
0x1800ae985  imul    rax, rbx
0x1800ae989  xor     r13d, r13d
0x1800ae98c  test    rax, rax
0x1800ae98f  jz      loc_1800AEB1D
0x1800ae995  mov     [rbp+47h+var_80], r13d
0x1800ae999  xorps   xmm0, xmm0
0x1800ae99c  movdqu  [rbp+47h+var_78], xmm0
0x1800ae9a1  mov     [rbp+47h+var_68], r13
0x1800ae9a5  mov     edx, 8769h; unsigned __int16
0x1800ae9aa  lea     r8d, [r13+4]; unsigned __int16
0x1800ae9ae  mov     [rsp+38h], r13; Src
0x1800ae9b3  mov     dword ptr [rsp+0F0h+Size], r13d; Size
0x1800ae9b8  lea     rax, [rbp+47h+var_88]
0x1800ae9bc  mov     [rsp+0F0h+var_C8], rax; struct CRawImageReader::IFDDataEntry *
0x1800ae9c1  mov     [rsp+0F0h+var_D0], r13d; unsigned int
0x1800ae9c6  mov     r9d, edi; unsigned int
0x1800ae9c9  mov     rcx, rsi; this
0x1800ae9cc  call    ?CreateOneIFDEntry@CRawImageReader@@AEAAJGGIIAEAUIFDDataEntry@1@IPEBE@Z; CRawImageReader::CreateOneIFDEntry(ushort,ushort,uint,uint,CRawImageReader::IFDDataEntry &,uint,uchar const *)
0x1800ae9d1  mov     ebx, eax
0x1800ae9d3  test    eax, eax
0x1800ae9d5  jns     loc_1800AEA69
0x1800ae9db  lea     rax, WPP_GLOBAL_Control
0x1800ae9e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae9e9  cmp     rcx, rax
0x1800ae9ec  jz      short loc_1800AEA15
0x1800ae9ee  test    [rcx+1Ch], dil
0x1800ae9f2  jz      short loc_1800AEA15
0x1800ae9f4  cmp     byte ptr [rcx+19h], 4
0x1800ae9f8  jb      short loc_1800AEA15
0x1800ae9fa  lea     edx, [r13+6Fh]
0x1800ae9fe  mov     [rsp+0F0h+var_D0], ebx
0x1800aea02  mov     r9d, [r14]
0x1800aea05  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800aea0c  mov     rcx, [rcx+10h]
0x1800aea10  call    WPP_SF_Dd
0x1800aea15  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aea1c  test    rcx, rcx
0x1800aea1f  jnz     short loc_1800AEA2F
0x1800aea21  lea     rcx, off_1800E5190; this
0x1800aea28  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aea2f  cmp     [rcx+8], r13b
0x1800aea33  jz      short loc_1800AEA5B
0x1800aea35  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aea3a  cmp     [rax+7CCh], ebx
0x1800aea40  jz      short loc_1800AEA5B
0x1800aea42  mov     r8d, 50Eh; int
0x1800aea48  mov     r9d, ebx; int
0x1800aea4b  lea     rdx, aCrawimagereade_9; "CRawImageReader::WriteTopIFDEntry"
0x1800aea52  mov     rcx, rax; this
0x1800aea55  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aea5a  nop
0x1800aea5b  lea     rcx, [rbp+47h+var_78]
0x1800aea5f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800aea64  jmp     loc_1800AED55
0x1800aea69  mov     r9, r12; unsigned int *
0x1800aea6c  mov     r8, r15; union _LARGE_INTEGER *
0x1800aea6f  lea     rdx, [rbp+47h+var_88]; struct CRawImageReader::IFDDataEntry *
0x1800aea73  mov     rcx, rsi; this
0x1800aea76  call    ?WriteOneIFDEntryToStream@CRawImageReader@@AEAAJAEAUIFDDataEntry@1@PEAT_LARGE_INTEGER@@PEAI@Z; CRawImageReader::WriteOneIFDEntryToStream(CRawImageReader::IFDDataEntry &,_LARGE_INTEGER *,uint *)
0x1800aea7b  mov     ebx, eax
0x1800aea7d  test    eax, eax
0x1800aea7f  jns     short loc_1800AEAFC
0x1800aea81  lea     rax, WPP_GLOBAL_Control
0x1800aea88  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aea8f  cmp     rcx, rax
0x1800aea92  jz      short loc_1800AEABC
0x1800aea94  test    [rcx+1Ch], dil
0x1800aea98  jz      short loc_1800AEABC
0x1800aea9a  cmp     byte ptr [rcx+19h], 4
0x1800aea9e  jb      short loc_1800AEABC
0x1800aeaa0  mov     edx, 70h ; 'p'
0x1800aeaa5  mov     [rsp+0F0h+var_D0], ebx
0x1800aeaa9  mov     r9d, [r14]
0x1800aeaac  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800aeab3  mov     rcx, [rcx+10h]
0x1800aeab7  call    WPP_SF_Dd
0x1800aeabc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aeac3  test    rcx, rcx
0x1800aeac6  jnz     short loc_1800AEAD6
0x1800aeac8  lea     rcx, off_1800E5190; this
0x1800aeacf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aead6  cmp     [rcx+8], r13b
0x1800aeada  jz      loc_1800AEA5B
0x1800aeae0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aeae5  cmp     [rax+7CCh], ebx
0x1800aeaeb  jz      loc_1800AEA5B
0x1800aeaf1  mov     r8d, 50Fh
0x1800aeaf7  jmp     loc_1800AEA48
0x1800aeafc  mov     rax, [r15]
0x1800aeaff  sub     rax, 4
0x1800aeb03  mov     rcx, [rbp+47h+var_A0]
0x1800aeb07  mov     [rcx], rax
0x1800aeb0a  lea     rcx, [rbp+47h+var_78]
0x1800aeb0e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800aeb13  mov     rbx, 0CCCCCCCCCCCCCCCDh
0x1800aeb1d  mov     rax, [rsi+0B8h]
0x1800aeb24  sub     rax, [rsi+0B0h]
0x1800aeb2b  sar     rax, 3
0x1800aeb2f  imul    rax, rbx
0x1800aeb33  test    rax, rax
0x1800aeb36  jz      loc_1800AECB0
0x1800aeb3c  mov     [rbp+47h+var_80], r13d
0x1800aeb40  xorps   xmm0, xmm0
0x1800aeb43  movdqu  [rbp+47h+var_78], xmm0
0x1800aeb48  mov     [rbp+47h+var_68], r13
0x1800aeb4c  mov     edx, 8825h; unsigned __int16
0x1800aeb51  mov     r8d, 4; unsigned __int16
0x1800aeb57  mov     [rsp+38h], r13; Src
0x1800aeb5c  mov     dword ptr [rsp+0F0h+Size], r13d; Size
0x1800aeb61  lea     rax, [rbp+47h+var_88]
0x1800aeb65  mov     [rsp+0F0h+var_C8], rax; struct CRawImageReader::IFDDataEntry *
0x1800aeb6a  mov     [rsp+0F0h+var_D0], r13d; unsigned int
0x1800aeb6f  mov     r9d, edi; unsigned int
0x1800aeb72  mov     rcx, rsi; this
0x1800aeb75  call    ?CreateOneIFDEntry@CRawImageReader@@AEAAJGGIIAEAUIFDDataEntry@1@IPEBE@Z; CRawImageReader::CreateOneIFDEntry(ushort,ushort,uint,uint,CRawImageReader::IFDDataEntry &,uint,uchar const *)
0x1800aeb7a  mov     ebx, eax
0x1800aeb7c  test    eax, eax
0x1800aeb7e  jns     loc_1800AEC0A
0x1800aeb84  lea     rax, WPP_GLOBAL_Control
0x1800aeb8b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aeb92  cmp     rcx, rax
0x1800aeb95  jz      short loc_1800AEBBF
0x1800aeb97  test    [rcx+1Ch], dil
0x1800aeb9b  jz      short loc_1800AEBBF
0x1800aeb9d  cmp     byte ptr [rcx+19h], 4
0x1800aeba1  jb      short loc_1800AEBBF
0x1800aeba3  mov     edx, 71h ; 'q'
0x1800aeba8  mov     [rsp+0F0h+var_D0], ebx
0x1800aebac  mov     r9d, [r14]
0x1800aebaf  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800aebb6  mov     rcx, [rcx+10h]
0x1800aebba  call    WPP_SF_Dd
0x1800aebbf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aebc6  test    rcx, rcx
0x1800aebc9  jnz     short loc_1800AEBD9
  ... truncated ...
```
