# CRawImageReader::InitializeRawProcessorForDecodeImage(uchar * *)

- ea: `0x1800abf54`
- end: `0x1800ac55e`
- name: `?InitializeRawProcessorForDecodeImage@CRawImageReader@@AEAAJPEAPEAE@Z`
- size: `1546`
- prototype: `__int64 __fastcall(CRawImageReader *__hidden this, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800a8588`

## callees

- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x180003044`
- `0x180006094`
- `0x180006710`
- `0x180006bc0`
- `0x18000acb0`
- `0x18000de10`
- `0x18009b9e4`
- `0x18009c44c`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800abf54`
- `0x1800b0b00`
- `0x1800b4010`

## string_xrefs

- `0x1800abf91`: `CRawImageReader::InitializeRawProcessorForDecodeImage`
- `0x1800ac328`: `CRawImageReader::InitializeRawProcessorForDecodeImage`

## pseudocode

```c
__int64 __fastcall CRawImageReader::InitializeRawProcessorForDecodeImage(CRawImageReader *this, unsigned __int8 **a2)
{
  int *v4; // r9
  struct CallStackContext *ThreadRelativeContext; // rbx
  int v6; // esi
  __int64 v7; // rcx
  LibRaw *v8; // rax
  int v9; // ebx
  __int64 v10; // rcx
  void ***v11; // rcx
  struct CallStackContext *v12; // rax
  int v13; // r8d
  int v14; // eax
  void ***v15; // rcx
  int v16; // eax
  void ***v17; // rcx
  unsigned int v18; // r15d
  __int64 v19; // r9
  void ***v20; // rcx
  unsigned __int8 *v21; // rax
  int v22; // eax
  void ***v23; // rcx
  int v24; // eax
  PVOID *v25; // rcx
  void ***v26; // rcx
  const char *v27; // r9
  __int64 result; // rax
  int v29; // [rsp+20h] [rbp-D8h]
  _BYTE v30[4]; // [rsp+30h] [rbp-C8h] BYREF
  _DWORD v31[3]; // [rsp+34h] [rbp-C4h] BYREF
  _BYTE v32[32]; // [rsp+40h] [rbp-B8h] BYREF
  LibRaw *v33; // [rsp+60h] [rbp-98h] BYREF
  unsigned __int64 v34[10]; // [rsp+70h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  *(_QWORD *)&v31[1] = -2;
  try
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v30,
      "CRawImageReader::InitializeRawProcessorForDecodeImage",
      1622);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
      *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, LibRaw **))(**((_QWORD **)this + 34) + 280LL))(
                                                              *((_QWORD *)this + 34),
                                                              &v33);
      *((_DWORD *)ThreadRelativeContext + 504) = v6;
    }
    CTraceBase::CAutoTrace::CAutoTrace(
      (CTraceBase::CAutoTrace *)v32,
      (struct CTraceBase *)(((unsigned __int64)this + 56) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
      "CRawImageReader::InitializeRawProcessorForDecodeImage",
      v4,
      v29);
    LibRaw::recycle(*((LibRaw **)this + 18));
    v7 = *((_QWORD *)this + 18);
    if ( v7 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 32LL))(v7, 1);
    Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((char *)this + 264);
    v33 = (LibRaw *)operator new(0xBB520u);
    v8 = LibRaw::LibRaw(v33, 0);
    *((_QWORD *)this + 18) = v8;
    if ( v8 )
    {
      *((_QWORD *)v8 + 95881) = this;
      *((_QWORD *)v8 + 95880) = CRawImageReader::libraw_dataerror_callback;
      v10 = *((_QWORD *)this + 32);
      if ( v10 )
      {
        v33 = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v10 + 40LL))(v10, 0, 0, 0);
        v9 = v14;
        if ( v14 >= 0 )
        {
          memset(v34, 0, sizeof(v34));
          v16 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *, __int64))(**((_QWORD **)this + 32) + 96LL))(
                  *((_QWORD *)this + 32),
                  v34,
                  1);
          v9 = v16;
          if ( v16 >= 0 )
          {
            v18 = v34[2];
            if ( v34[2] > 0xFFFFFFFF )
            {
              v18 = -1;
              v9 = -2147024362;
            }
            else
            {
              v9 = 0;
            }
            v19 = *((unsigned int *)this + 14);
            if ( v9 >= 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  147,
                  &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                  v19,
                  v18);
              }
              v21 = (unsigned __int8 *)operator new[](v18);
              *a2 = v21;
              v31[0] = 0;
              v22 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, _DWORD *))(**((_QWORD **)this + 32)
                                                                                           + 24LL))(
                      *((_QWORD *)this + 32),
                      v21,
                      v18,
                      v31);
              v9 = v22;
              if ( v22 >= 0 )
              {
                *(_DWORD *)(*((_QWORD *)this + 18) + 5248LL) = 0;
                *(_DWORD *)(*((_QWORD *)this + 18) + 5244LL) = 0;
                *(_DWORD *)(*((_QWORD *)this + 18) + 5184LL) = 1;
                v24 = LibRaw::open_buffer(*((LibRaw **)this + 18), *a2, v31[0]);
                if ( !v24 )
                {
                  LibRaw::raw2image_start(*((LibRaw **)this + 18));
                  goto LABEL_82;
                }
                v25 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    149,
                    &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                    *((unsigned int *)this + 14),
                    v24);
                  v25 = (PVOID *)WPP_GLOBAL_Control;
                }
                v9 = -2003292320;
                if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 && *((_BYTE *)v25 + 25) >= 4u )
                  WPP_SF_Dd(
                    v25[2],
                    150,
                    &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                    *((unsigned int *)this + 14),
                    -2003292320);
                v26 = (void ***)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v26 = &off_1800E5190;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
                }
                if ( !*((_BYTE *)v26 + 8) )
                  goto LABEL_82;
                v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
                if ( *((_DWORD *)v12 + 499) == -2003292320 )
                  goto LABEL_82;
                v13 = 1658;
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    148,
                    &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                    *((unsigned int *)this + 14),
                    v22);
                }
                v23 = (void ***)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v23 = &off_1800E5190;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
                }
                if ( !*((_BYTE *)v23 + 8) )
                  goto LABEL_82;
                v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
                if ( *((_DWORD *)v12 + 499) == v9 )
                  goto LABEL_82;
                v13 = 1646;
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  146,
                  &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                  v19,
                  v9);
              }
              v20 = (void ***)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v20 = &off_1800E5190;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
              }
              if ( !*((_BYTE *)v20 + 8) )
                goto LABEL_82;
              v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
              if ( *((_DWORD *)v12 + 499) == v9 )
                goto LABEL_82;
              v13 = 1639;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                145,
                &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                *((unsigned int *)this + 14),
                v16);
            }
            v17 = (void ***)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v17 = &off_1800E5190;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
            }
            if ( !*((_BYTE *)v17 + 8) )
              goto LABEL_82;
            v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
            if ( *((_DWORD *)v12 + 499) == v9 )
              goto LABEL_82;
            v13 = 1637;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              144,
              &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
              *((unsigned int *)this + 14),
              v14);
          }
          v15 = (void ***)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v15 = &off_1800E5190;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
          }
          if ( !*((_BYTE *)v15 + 8) )
            goto LABEL_82;
          v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)v12 + 499) == v9 )
            goto LABEL_82;
          v13 = 1634;
        }
      }
      else
      {
        v9 = -2147418113;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            143,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *((unsigned int *)this + 14),
            -2147418113);
        }
        v11 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v11 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v11 + 8) )
          goto LABEL_82;
        v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v12 + 499) == -2147418113 )
          goto LABEL_82;
        v13 = 1632;
      }
      CallStackContext::TraceFailure(v12, "CRawImageReader::InitializeRawProcessorForDecodeImage", v13, v9);
    }
    else
    {
      v9 = -2147024882;
    }
LABEL_82:
    CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v32);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v30);
    result = (unsigned int)v9;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x680,
                           (unsigned int)"avcore\\mf\\rawimage\\rawimagereader\\rawimagereader.cpp",
                           v27);
  }
  return result;
}

```

## disassembly

```asm
0x1800abf54  mov     rax, rsp
0x1800abf57  push    rsi
0x1800abf58  push    rdi
0x1800abf59  push    r12
0x1800abf5b  push    r13
0x1800abf5d  push    r15
0x1800abf5f  sub     rsp, 0D0h
0x1800abf66  mov     qword ptr [rsp+0F8h+var_C4+4], 0FFFFFFFFFFFFFFFEh
0x1800abf6f  mov     [rax+18h], rbx
0x1800abf73  mov     rax, cs:__security_cookie
0x1800abf7a  xor     rax, rsp
0x1800abf7d  mov     [rsp+0F8h+var_38], rax
0x1800abf85  mov     r12, rdx
0x1800abf88  mov     rdi, rcx
0x1800abf8b  mov     r8d, 656h; int
0x1800abf91  lea     r15, aCrawimagereade_0; "CRawImageReader::InitializeRawProcessor"...
0x1800abf98  mov     rdx, r15; char *
0x1800abf9b  lea     rcx, [rsp+0F8h+var_C8]; this
0x1800abfa0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800abfa5  nop
0x1800abfa6  xor     r13d, r13d
0x1800abfa9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800abfb0  cmp     [rcx+8], r13b
0x1800abfb4  jz      short loc_1800AC00B
0x1800abfb6  cmp     [rdi+110h], r13
0x1800abfbd  jz      short loc_1800AC00B
0x1800abfbf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800abfc4  mov     rbx, rax
0x1800abfc7  mov     rcx, [rdi+110h]
0x1800abfce  mov     rdx, [rcx]
0x1800abfd1  mov     rax, [rdx+128h]
0x1800abfd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abfdd  mov     esi, eax
0x1800abfdf  mov     rcx, [rdi+110h]
0x1800abfe6  mov     rdx, [rcx]
0x1800abfe9  mov     rax, [rdx+118h]
0x1800abff0  lea     rdx, [rsp+0F8h+var_98]
0x1800abff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abffa  movups  xmm0, xmmword ptr [rax]
0x1800abffd  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x1800ac005  mov     [rbx+7E0h], esi
0x1800ac00b  mov     rax, rdi
0x1800ac00e  lea     rcx, [rdi+38h]
0x1800ac012  neg     rax
0x1800ac015  sbb     rdx, rdx
0x1800ac018  and     rdx, rcx; struct CTraceBase *
0x1800ac01b  mov     r8, r15; char *
0x1800ac01e  lea     rcx, [rsp+0F8h+var_B8]; this
0x1800ac023  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800ac028  nop
0x1800ac029  mov     rcx, [rdi+90h]; this
0x1800ac030  call    ?recycle@LibRaw@@QEAAXXZ; LibRaw::recycle(void)
0x1800ac035  mov     rcx, [rdi+90h]
0x1800ac03c  test    rcx, rcx
0x1800ac03f  jz      short loc_1800AC052
0x1800ac041  mov     rax, [rcx]
0x1800ac044  mov     edx, 1
0x1800ac049  mov     rax, [rax+20h]
0x1800ac04d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac052  lea     rcx, [rdi+108h]
0x1800ac059  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800ac05e  mov     ecx, 0BB520h; Size
0x1800ac063  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ac068  mov     [rsp+0F8h+var_98], rax
0x1800ac06d  xor     edx, edx; unsigned int
0x1800ac06f  mov     rcx, rax; this
0x1800ac072  call    ??0LibRaw@@QEAA@I@Z; LibRaw::LibRaw(uint)
0x1800ac077  nop
0x1800ac078  mov     [rdi+90h], rax
0x1800ac07f  test    rax, rax
0x1800ac082  jnz     short loc_1800AC08E
0x1800ac084  mov     ebx, 8007000Eh
0x1800ac089  jmp     loc_1800AC518
0x1800ac08e  mov     [rax+0BB448h], rdi
0x1800ac095  lea     rcx, ?libraw_dataerror_callback@CRawImageReader@@SAXPEAXPEBDH@Z; CRawImageReader::libraw_dataerror_callback(void *,char const *,int)
0x1800ac09c  mov     [rax+0BB440h], rcx
0x1800ac0a3  mov     rcx, [rdi+100h]
0x1800ac0aa  test    rcx, rcx
0x1800ac0ad  jnz     loc_1800AC142
0x1800ac0b3  mov     ebx, 8000FFFFh
0x1800ac0b8  lea     rsi, WPP_GLOBAL_Control
0x1800ac0bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac0c6  cmp     rcx, rsi
0x1800ac0c9  jz      short loc_1800AC0F4
0x1800ac0cb  test    byte ptr [rcx+1Ch], 1
0x1800ac0cf  jz      short loc_1800AC0F4
0x1800ac0d1  cmp     byte ptr [rcx+19h], 4
0x1800ac0d5  jb      short loc_1800AC0F4
0x1800ac0d7  mov     edx, 8Fh
0x1800ac0dc  mov     [rsp+0F8h+var_D8], ebx
0x1800ac0e0  mov     r9d, [rdi+38h]
0x1800ac0e4  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ac0eb  mov     rcx, [rcx+10h]
0x1800ac0ef  call    WPP_SF_Dd
0x1800ac0f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac0fb  test    rcx, rcx
0x1800ac0fe  jnz     short loc_1800AC10E
0x1800ac100  lea     rcx, off_1800E5190; this
0x1800ac107  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac10e  cmp     [rcx+8], r13b
0x1800ac112  jz      loc_1800AC518
0x1800ac118  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ac11d  cmp     [rax+7CCh], ebx
0x1800ac123  jz      loc_1800AC518
0x1800ac129  mov     r8d, 660h; int
0x1800ac12f  mov     rdx, r15; char *
0x1800ac132  mov     r9d, ebx; int
0x1800ac135  mov     rcx, rax; this
0x1800ac138  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ac13d  jmp     loc_1800AC518
0x1800ac142  mov     [rsp+0F8h+var_98], r13
0x1800ac147  mov     rax, [rcx]
0x1800ac14a  xor     r9d, r9d
0x1800ac14d  xor     r8d, r8d
0x1800ac150  mov     rdx, r13
0x1800ac153  mov     rax, [rax+28h]
0x1800ac157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac15c  mov     ebx, eax
0x1800ac15e  test    eax, eax
0x1800ac160  jns     short loc_1800AC1DE
0x1800ac162  lea     rsi, WPP_GLOBAL_Control
0x1800ac169  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac170  cmp     rcx, rsi
0x1800ac173  jz      short loc_1800AC19E
0x1800ac175  test    byte ptr [rcx+1Ch], 1
0x1800ac179  jz      short loc_1800AC19E
0x1800ac17b  cmp     byte ptr [rcx+19h], 4
0x1800ac17f  jb      short loc_1800AC19E
0x1800ac181  mov     edx, 90h
0x1800ac186  mov     [rsp+0F8h+var_D8], eax
0x1800ac18a  mov     r9d, [rdi+38h]
0x1800ac18e  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ac195  mov     rcx, [rcx+10h]
0x1800ac199  call    WPP_SF_Dd
0x1800ac19e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac1a5  test    rcx, rcx
0x1800ac1a8  jnz     short loc_1800AC1B8
0x1800ac1aa  lea     rcx, off_1800E5190; this
0x1800ac1b1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac1b8  cmp     [rcx+8], r13b
0x1800ac1bc  jz      loc_1800AC518
0x1800ac1c2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ac1c7  cmp     [rax+7CCh], ebx
0x1800ac1cd  jz      loc_1800AC518
0x1800ac1d3  mov     r8d, 662h
0x1800ac1d9  jmp     loc_1800AC12F
0x1800ac1de  xor     edx, edx; Val
0x1800ac1e0  lea     r8d, [rdx+50h]; Size
0x1800ac1e4  lea     rcx, [rsp+0F8h+var_88]; void *
0x1800ac1e9  call    memset
0x1800ac1ee  mov     rcx, [rdi+100h]
0x1800ac1f5  mov     rax, [rcx]
0x1800ac1f8  mov     r8d, 1
0x1800ac1fe  lea     rdx, [rsp+0F8h+var_88]
0x1800ac203  mov     rax, [rax+60h]
0x1800ac207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac20c  mov     ebx, eax
0x1800ac20e  test    eax, eax
0x1800ac210  jns     short loc_1800AC28E
0x1800ac212  lea     rsi, WPP_GLOBAL_Control
0x1800ac219  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac220  cmp     rcx, rsi
0x1800ac223  jz      short loc_1800AC24E
0x1800ac225  test    byte ptr [rcx+1Ch], 1
0x1800ac229  jz      short loc_1800AC24E
0x1800ac22b  cmp     byte ptr [rcx+19h], 4
0x1800ac22f  jb      short loc_1800AC24E
0x1800ac231  mov     edx, 91h
0x1800ac236  mov     [rsp+0F8h+var_D8], eax
0x1800ac23a  mov     r9d, [rdi+38h]
0x1800ac23e  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ac245  mov     rcx, [rcx+10h]
0x1800ac249  call    WPP_SF_Dd
0x1800ac24e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac255  test    rcx, rcx
0x1800ac258  jnz     short loc_1800AC268
0x1800ac25a  lea     rcx, off_1800E5190; this
0x1800ac261  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac268  cmp     [rcx+8], r13b
0x1800ac26c  jz      loc_1800AC518
0x1800ac272  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ac277  cmp     [rax+7CCh], ebx
0x1800ac27d  jz      loc_1800AC518
0x1800ac283  mov     r8d, 665h
0x1800ac289  jmp     loc_1800AC12F
0x1800ac28e  mov     eax, 0FFFFFFFFh
0x1800ac293  mov     r15, [rsp+0F8h+var_78]
0x1800ac29b  cmp     r15, rax
0x1800ac29e  ja      short loc_1800AC2A5
0x1800ac2a0  mov     ebx, r13d
0x1800ac2a3  jmp     short loc_1800AC2AD
0x1800ac2a5  mov     r15d, eax
0x1800ac2a8  mov     ebx, 80070216h
0x1800ac2ad  mov     r9d, [rdi+38h]
0x1800ac2b1  test    ebx, ebx
0x1800ac2b3  jns     short loc_1800AC334
0x1800ac2b5  lea     rsi, WPP_GLOBAL_Control
0x1800ac2bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac2c3  cmp     rcx, rsi
0x1800ac2c6  jz      short loc_1800AC2ED
0x1800ac2c8  test    byte ptr [rcx+1Ch], 1
0x1800ac2cc  jz      short loc_1800AC2ED
0x1800ac2ce  cmp     byte ptr [rcx+19h], 4
0x1800ac2d2  jb      short loc_1800AC2ED
0x1800ac2d4  mov     edx, 92h
0x1800ac2d9  mov     [rsp+0F8h+var_D8], ebx
0x1800ac2dd  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ac2e4  mov     rcx, [rcx+10h]
0x1800ac2e8  call    WPP_SF_Dd
0x1800ac2ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac2f4  test    rcx, rcx
0x1800ac2f7  jnz     short loc_1800AC307
0x1800ac2f9  lea     rcx, off_1800E5190; this
0x1800ac300  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac307  cmp     [rcx+8], r13b
0x1800ac30b  jz      loc_1800AC518
0x1800ac311  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ac316  cmp     [rax+7CCh], ebx
0x1800ac31c  jz      loc_1800AC518
0x1800ac322  mov     r8d, 667h
0x1800ac328  lea     rdx, aCrawimagereade_0; "CRawImageReader::InitializeRawProcessor"...
0x1800ac32f  jmp     loc_1800AC132
0x1800ac334  lea     rsi, WPP_GLOBAL_Control
0x1800ac33b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac342  cmp     rcx, rsi
0x1800ac345  jz      short loc_1800AC36D
0x1800ac347  test    byte ptr [rcx+1Ch], 1
0x1800ac34b  jz      short loc_1800AC36D
0x1800ac34d  cmp     byte ptr [rcx+19h], 4
0x1800ac351  jb      short loc_1800AC36D
0x1800ac353  mov     edx, 93h
0x1800ac358  mov     [rsp+0F8h+var_D8], r15d
0x1800ac35d  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ac364  mov     rcx, [rcx+10h]
0x1800ac368  call    WPP_SF_Dd
0x1800ac36d  mov     ecx, r15d; unsigned __int64
0x1800ac370  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ac375  mov     r10, rax
0x1800ac378  mov     [r12], rax
0x1800ac37c  mov     dword ptr [rsp+0F8h+var_C4], r13d
0x1800ac381  mov     rcx, [rdi+100h]
0x1800ac388  mov     rdx, [rcx]
0x1800ac38b  mov     rax, [rdx+18h]
0x1800ac38f  lea     r9, [rsp+0F8h+var_C4]
0x1800ac394  mov     r8d, r15d
0x1800ac397  mov     rdx, r10
0x1800ac39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac39f  mov     ebx, eax
0x1800ac3a1  test    eax, eax
0x1800ac3a3  jns     short loc_1800AC41A
0x1800ac3a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac3ac  cmp     rcx, rsi
0x1800ac3af  jz      short loc_1800AC3DA
0x1800ac3b1  test    byte ptr [rcx+1Ch], 1
0x1800ac3b5  jz      short loc_1800AC3DA
0x1800ac3b7  cmp     byte ptr [rcx+19h], 4
0x1800ac3bb  jb      short loc_1800AC3DA
0x1800ac3bd  mov     edx, 94h
0x1800ac3c2  mov     [rsp+0F8h+var_D8], eax
0x1800ac3c6  mov     r9d, [rdi+38h]
0x1800ac3ca  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ac3d1  mov     rcx, [rcx+10h]
0x1800ac3d5  call    WPP_SF_Dd
0x1800ac3da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac3e1  test    rcx, rcx
0x1800ac3e4  jnz     short loc_1800AC3F4
0x1800ac3e6  lea     rcx, off_1800E5190; this
0x1800ac3ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac3f4  cmp     [rcx+8], r13b
0x1800ac3f8  jz      loc_1800AC518
0x1800ac3fe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ac403  cmp     [rax+7CCh], ebx
0x1800ac409  jz      loc_1800AC518
0x1800ac40f  mov     r8d, 66Eh
0x1800ac415  jmp     loc_1800AC328
0x1800ac41a  mov     rax, [rdi+90h]
0x1800ac421  mov     [rax+1480h], r13d
0x1800ac428  mov     rax, [rdi+90h]
0x1800ac42f  mov     [rax+147Ch], r13d
0x1800ac436  mov     rax, [rdi+90h]
0x1800ac43d  mov     dword ptr [rax+1440h], 1
0x1800ac447  mov     r8d, dword ptr [rsp+0F8h+var_C4]; unsigned __int64
0x1800ac44c  mov     rdx, [r12]; void *
0x1800ac450  mov     rcx, [rdi+90h]; this
0x1800ac457  call    ?open_buffer@LibRaw@@QEAAHPEBX_K@Z; LibRaw::open_buffer(void const *,unsigned __int64)
0x1800ac45c  test    eax, eax
0x1800ac45e  jz      loc_1800AC50B
0x1800ac464  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac46b  cmp     rcx, rsi
0x1800ac46e  jz      short loc_1800AC4A0
0x1800ac470  test    byte ptr [rcx+1Ch], 1
0x1800ac474  jz      short loc_1800AC4A0
0x1800ac476  cmp     byte ptr [rcx+19h], 4
0x1800ac47a  jb      short loc_1800AC4A0
0x1800ac47c  mov     edx, 95h
0x1800ac481  mov     [rsp+0F8h+var_D8], eax
0x1800ac485  mov     r9d, [rdi+38h]
0x1800ac489  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ac490  mov     rcx, [rcx+10h]
0x1800ac494  call    WPP_SF_Dd
  ... truncated ...
```
