# CRawImageReader::WriteOneIFDEntryToStream(CRawImageReader::IFDDataEntry &,_LARGE_INTEGER *,uint *)

- ea: `0x1800adcb0`
- end: `0x1800ae32f`
- name: `?WriteOneIFDEntryToStream@CRawImageReader@@AEAAJAEAUIFDDataEntry@1@PEAT_LARGE_INTEGER@@PEAI@Z`
- size: `1663`
- prototype: `__int64 __fastcall(CRawImageReader *__hidden this, struct CRawImageReader::IFDDataEntry *, union _LARGE_INTEGER *, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800ae338`
- `0x1800ae6b8`

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
- `0x1800b4010`

## string_xrefs

- `0x1800adcec`: `CRawImageReader::WriteOneIFDEntryToStream`
- `0x1800add6f`: `CRawImageReader::WriteOneIFDEntryToStream`
- `0x1800ade2f`: `CRawImageReader::WriteOneIFDEntryToStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRawImageReader::WriteOneIFDEntryToStream(
        CRawImageReader *this,
        struct CRawImageReader::IFDDataEntry *a2,
        union _LARGE_INTEGER *a3,
        unsigned int *a4)
{
  int *v8; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v10; // ebx
  unsigned int *v11; // rsi
  int v12; // ebx
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  int v15; // r8d
  CallStackTracing *v16; // rcx
  CallStackTracing *v17; // rcx
  int v18; // eax
  unsigned int v19; // edx
  unsigned int v20; // r8d
  CallStackTracing *v21; // rcx
  CallStackTracing *v22; // rcx
  CallStackTracing *v23; // rcx
  CallStackTracing *v24; // rcx
  CallStackTracing *v25; // rcx
  int v27; // [rsp+20h] [rbp-58h]
  unsigned int v28; // [rsp+30h] [rbp-48h] BYREF
  char v29; // [rsp+34h] [rbp-44h] BYREF
  char v30; // [rsp+35h] [rbp-43h]
  char v31; // [rsp+36h] [rbp-42h]
  char v32; // [rsp+37h] [rbp-41h]
  _BYTE v33[8]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v34; // [rsp+40h] [rbp-38h]
  _BYTE v35[32]; // [rsp+48h] [rbp-30h] BYREF

  v34 = -2;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v33,
    "CRawImageReader::WriteOneIFDEntryToStream",
    1333);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            v35);
    *((_DWORD *)ThreadRelativeContext + 504) = v10;
  }
  v11 = (unsigned int *)((char *)this + 56);
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v35,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    "CRawImageReader::WriteOneIFDEntryToStream",
    v8,
    v27);
  v28 = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD, struct CRawImageReader::IFDDataEntry *, __int64, unsigned int *))(**((_QWORD **)this + 31) + 32LL))(
          *((_QWORD *)this + 31),
          a2,
          2,
          &v28);
  if ( v12 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, unsigned int *))(**((_QWORD **)this + 31) + 32LL))(
            *((_QWORD *)this + 31),
            (char *)a2 + 2,
            2,
            &v28);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, unsigned int *))(**((_QWORD **)this + 31) + 32LL))(
              *((_QWORD *)this + 31),
              (char *)a2 + 4,
              4,
              &v28);
      if ( v12 >= 0 )
      {
        a3->QuadPart += 8LL;
        if ( *((_QWORD *)a2 + 3) == *((_QWORD *)a2 + 2) )
        {
          v12 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, unsigned int *))(**((_QWORD **)this + 31) + 32LL))(
                  *((_QWORD *)this + 31),
                  (char *)a2 + 8,
                  4,
                  &v28);
          if ( v12 >= 0 )
          {
            a3->QuadPart += v28;
            goto LABEL_90;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              123,
              &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
              *v11,
              v12);
          }
          v25 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v25 = (CallStackTracing *)&off_1800E5190;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
          }
          if ( *((_BYTE *)v25 + 8) )
          {
            v14 = CallStackTracing::GetThreadRelativeContext(v25);
            if ( *((_DWORD *)v14 + 499) != v12 )
            {
              v15 = 1364;
              goto LABEL_14;
            }
          }
        }
        else
        {
          v18 = *a4;
          v19 = HIWORD(*a4);
          v20 = *a4 >> 8;
          if ( *((_BYTE *)this + 107) )
          {
            v29 = HIBYTE(*a4);
            v30 = v19;
            v31 = v20;
            v32 = v18;
          }
          else
          {
            v32 = HIBYTE(*a4);
            v31 = v19;
            v30 = v20;
            v29 = v18;
          }
          v12 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, unsigned int *))(**((_QWORD **)this + 31) + 32LL))(
                  *((_QWORD *)this + 31),
                  &v29,
                  4,
                  &v28);
          if ( v12 >= 0 )
          {
            a3->QuadPart += v28;
            v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 31) + 40LL))(
                    *((_QWORD *)this + 31),
                    *a4,
                    0,
                    0);
            if ( v12 >= 0 )
            {
              v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned int *))(**((_QWORD **)this + 31) + 32LL))(
                      *((_QWORD *)this + 31),
                      *((_QWORD *)a2 + 2),
                      *((_DWORD *)a2 + 6) - (unsigned int)*((_QWORD *)a2 + 2),
                      &v28);
              if ( v12 >= 0 )
              {
                *a4 += v28;
                v12 = (*(__int64 (__fastcall **)(_QWORD, LONGLONG, _QWORD, _QWORD))(**((_QWORD **)this + 31) + 40LL))(
                        *((_QWORD *)this + 31),
                        a3->QuadPart,
                        0,
                        0);
                if ( v12 < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  {
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      122,
                      &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                      *v11,
                      v12);
                  }
                  v24 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v24 = (CallStackTracing *)&off_1800E5190;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
                  }
                  if ( *((_BYTE *)v24 + 8) )
                  {
                    v14 = CallStackTracing::GetThreadRelativeContext(v24);
                    if ( *((_DWORD *)v14 + 499) != v12 )
                    {
                      v15 = 1359;
                      goto LABEL_14;
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
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    121,
                    &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                    *v11,
                    v12);
                }
                v23 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v23 = (CallStackTracing *)&off_1800E5190;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
                }
                if ( *((_BYTE *)v23 + 8) )
                {
                  v14 = CallStackTracing::GetThreadRelativeContext(v23);
                  if ( *((_DWORD *)v14 + 499) != v12 )
                  {
                    v15 = 1354;
                    goto LABEL_14;
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
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  120,
                  &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                  *v11,
                  v12);
              }
              v22 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v22 = (CallStackTracing *)&off_1800E5190;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
              }
              if ( *((_BYTE *)v22 + 8) )
              {
                v14 = CallStackTracing::GetThreadRelativeContext(v22);
                if ( *((_DWORD *)v14 + 499) != v12 )
                {
                  v15 = 1352;
                  goto LABEL_14;
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
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                119,
                &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                *v11,
                v12);
            }
            v21 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v21 = (CallStackTracing *)&off_1800E5190;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
            }
            if ( *((_BYTE *)v21 + 8) )
            {
              v14 = CallStackTracing::GetThreadRelativeContext(v21);
              if ( *((_DWORD *)v14 + 499) != v12 )
              {
                v15 = 1346;
                goto LABEL_14;
              }
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
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            118,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *v11,
            v12);
        }
        v17 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)&off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          v14 = CallStackTracing::GetThreadRelativeContext(v17);
          if ( *((_DWORD *)v14 + 499) != v12 )
          {
            v15 = 1338;
            goto LABEL_14;
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
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v11, v12);
      }
      v16 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)&off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext(v16);
        if ( *((_DWORD *)v14 + 499) != v12 )
        {
          v15 = 1337;
          goto LABEL_14;
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
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v11, v12);
    }
    v13 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)&off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext(v13);
      if ( *((_DWORD *)v14 + 499) != v12 )
      {
        v15 = 1336;
LABEL_14:
        CallStackContext::TraceFailure(v14, "CRawImageReader::WriteOneIFDEntryToStream", v15, v12);
      }
    }
  }
LABEL_90:
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v35);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v33);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800adcb0  push    rbp
0x1800adcb2  push    rbx
0x1800adcb3  push    rsi
0x1800adcb4  push    rdi
0x1800adcb5  push    r12
0x1800adcb7  push    r13
0x1800adcb9  push    r14
0x1800adcbb  push    r15
0x1800adcbd  mov     rbp, rsp
0x1800adcc0  sub     rsp, 78h
0x1800adcc4  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x1800adccc  mov     rax, cs:__security_cookie
0x1800adcd3  xor     rax, rsp
0x1800adcd6  mov     [rbp+var_10], rax
0x1800adcda  mov     r12, r9
0x1800adcdd  mov     r15, r8
0x1800adce0  mov     r13, rdx
0x1800adce3  mov     r14, rcx
0x1800adce6  mov     r8d, 535h; int
0x1800adcec  lea     rdx, aCrawimagereade_2; "CRawImageReader::WriteOneIFDEntryToStre"...
0x1800adcf3  lea     rcx, [rbp+var_40]; this
0x1800adcf7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800adcfc  nop
0x1800adcfd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800add04  cmp     byte ptr [rcx+8], 0
0x1800add08  jz      short loc_1800ADD5F
0x1800add0a  cmp     qword ptr [r14+110h], 0
0x1800add12  jz      short loc_1800ADD5F
0x1800add14  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800add19  mov     rdi, rax
0x1800add1c  mov     rcx, [r14+110h]
0x1800add23  mov     rdx, [rcx]
0x1800add26  mov     rax, [rdx+128h]
0x1800add2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800add32  mov     ebx, eax
0x1800add34  mov     rcx, [r14+110h]
0x1800add3b  mov     rdx, [rcx]
0x1800add3e  mov     rax, [rdx+118h]
0x1800add45  lea     rdx, [rbp+var_30]
0x1800add49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800add4e  movups  xmm0, xmmword ptr [rax]
0x1800add51  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800add59  mov     [rdi+7E0h], ebx
0x1800add5f  lea     rsi, [r14+38h]
0x1800add63  mov     rax, r14
0x1800add66  neg     rax
0x1800add69  sbb     rdx, rdx
0x1800add6c  and     rdx, rsi; struct CTraceBase *
0x1800add6f  lea     r8, aCrawimagereade_2; "CRawImageReader::WriteOneIFDEntryToStre"...
0x1800add76  lea     rcx, [rbp+var_30]; this
0x1800add7a  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800add7f  nop
0x1800add80  mov     [rbp+var_48], 0
0x1800add87  mov     rcx, [r14+0F8h]
0x1800add8e  mov     rax, [rcx]
0x1800add91  lea     r9, [rbp+var_48]
0x1800add95  mov     edi, 2
0x1800add9a  mov     r8d, edi
0x1800add9d  mov     rdx, r13
0x1800adda0  mov     rax, [rax+20h]
0x1800adda4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adda9  mov     ebx, eax
0x1800addab  test    eax, eax
0x1800addad  jns     loc_1800ADE43
0x1800addb3  lea     rax, WPP_GLOBAL_Control
0x1800addba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800addc1  cmp     rcx, rax
0x1800addc4  jz      short loc_1800ADDF1
0x1800addc6  test    byte ptr [rcx+1Ch], 1
0x1800addca  jz      short loc_1800ADDF1
0x1800addcc  mov     edi, 4
0x1800addd1  cmp     [rcx+19h], dil
0x1800addd5  jb      short loc_1800ADDF1
0x1800addd7  lea     edx, [rdi+70h]
0x1800addda  mov     [rsp+78h+var_58], ebx
0x1800addde  mov     r9d, [rsi]
0x1800adde1  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800adde8  mov     rcx, [rcx+10h]
0x1800addec  call    WPP_SF_Dd
0x1800addf1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800addf8  test    rcx, rcx
0x1800addfb  jnz     short loc_1800ADE0B
0x1800addfd  lea     rcx, off_1800E5190; this
0x1800ade04  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ade0b  cmp     byte ptr [rcx+8], 0
0x1800ade0f  jz      loc_1800AE2FC
0x1800ade15  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ade1a  cmp     [rax+7CCh], ebx
0x1800ade20  jz      loc_1800AE2FC
0x1800ade26  mov     r8d, 538h; int
0x1800ade2c  mov     r9d, ebx; int
0x1800ade2f  lea     rdx, aCrawimagereade_2; "CRawImageReader::WriteOneIFDEntryToStre"...
0x1800ade36  mov     rcx, rax; this
0x1800ade39  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ade3e  jmp     loc_1800AE2FC
0x1800ade43  mov     rcx, [r14+0F8h]
0x1800ade4a  lea     rdx, [r13+2]
0x1800ade4e  mov     rax, [rcx]
0x1800ade51  lea     r9, [rbp+var_48]
0x1800ade55  mov     r8d, edi
0x1800ade58  mov     rax, [rax+20h]
0x1800ade5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ade61  mov     ebx, eax
0x1800ade63  test    eax, eax
0x1800ade65  jns     short loc_1800ADEE5
0x1800ade67  lea     rax, WPP_GLOBAL_Control
0x1800ade6e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ade75  cmp     rcx, rax
0x1800ade78  jz      short loc_1800ADEA5
0x1800ade7a  test    byte ptr [rcx+1Ch], 1
0x1800ade7e  jz      short loc_1800ADEA5
0x1800ade80  mov     edi, 4
0x1800ade85  cmp     [rcx+19h], dil
0x1800ade89  jb      short loc_1800ADEA5
0x1800ade8b  lea     edx, [rdi+71h]
0x1800ade8e  mov     [rsp+78h+var_58], ebx
0x1800ade92  mov     r9d, [rsi]
0x1800ade95  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ade9c  mov     rcx, [rcx+10h]
0x1800adea0  call    WPP_SF_Dd
0x1800adea5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adeac  test    rcx, rcx
0x1800adeaf  jnz     short loc_1800ADEBF
0x1800adeb1  lea     rcx, off_1800E5190; this
0x1800adeb8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adebf  cmp     byte ptr [rcx+8], 0
0x1800adec3  jz      loc_1800AE2FC
0x1800adec9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800adece  cmp     [rax+7CCh], ebx
0x1800aded4  jz      loc_1800AE2FC
0x1800adeda  mov     r8d, 539h
0x1800adee0  jmp     loc_1800ADE2C
0x1800adee5  mov     rcx, [r14+0F8h]
0x1800adeec  lea     rdx, [r13+4]
0x1800adef0  mov     rax, [rcx]
0x1800adef3  lea     r9, [rbp+var_48]
0x1800adef7  mov     edi, 4
0x1800adefc  mov     r8d, edi
0x1800adeff  mov     rax, [rax+20h]
0x1800adf03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adf08  mov     ebx, eax
0x1800adf0a  test    eax, eax
0x1800adf0c  jns     short loc_1800ADF87
0x1800adf0e  lea     rax, WPP_GLOBAL_Control
0x1800adf15  mov     rcx, cs:WPP_GLOBAL_Control
0x1800adf1c  cmp     rcx, rax
0x1800adf1f  jz      short loc_1800ADF47
0x1800adf21  test    byte ptr [rcx+1Ch], 1
0x1800adf25  jz      short loc_1800ADF47
0x1800adf27  cmp     [rcx+19h], dil
0x1800adf2b  jb      short loc_1800ADF47
0x1800adf2d  lea     edx, [rdi+72h]
0x1800adf30  mov     [rsp+78h+var_58], ebx
0x1800adf34  mov     r9d, [rsi]
0x1800adf37  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800adf3e  mov     rcx, [rcx+10h]
0x1800adf42  call    WPP_SF_Dd
0x1800adf47  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adf4e  test    rcx, rcx
0x1800adf51  jnz     short loc_1800ADF61
0x1800adf53  lea     rcx, off_1800E5190; this
0x1800adf5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adf61  cmp     byte ptr [rcx+8], 0
0x1800adf65  jz      loc_1800AE2FC
0x1800adf6b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800adf70  cmp     [rax+7CCh], ebx
0x1800adf76  jz      loc_1800AE2FC
0x1800adf7c  mov     r8d, 53Ah
0x1800adf82  jmp     loc_1800ADE2C
0x1800adf87  add     qword ptr [r15], 8
0x1800adf8b  mov     rax, [r13+18h]
0x1800adf8f  cmp     rax, [r13+10h]
0x1800adf93  jz      loc_1800AE25F
0x1800adf99  mov     eax, [r12]
0x1800adf9d  mov     ecx, eax
0x1800adf9f  shr     ecx, 18h
0x1800adfa2  mov     edx, eax
0x1800adfa4  shr     edx, 10h
0x1800adfa7  mov     r8d, eax
0x1800adfaa  shr     r8d, 8
0x1800adfae  cmp     byte ptr [r14+6Bh], 0
0x1800adfb3  jnz     short loc_1800ADFC4
0x1800adfb5  mov     [rbp+var_41], cl
0x1800adfb8  mov     [rbp+var_42], dl
0x1800adfbb  mov     [rbp+var_43], r8b
0x1800adfbf  mov     [rbp+var_44], al
0x1800adfc2  jmp     short loc_1800ADFD1
0x1800adfc4  mov     [rbp+var_44], cl
0x1800adfc7  mov     [rbp+var_43], dl
0x1800adfca  mov     [rbp+var_42], r8b
0x1800adfce  mov     [rbp+var_41], al
0x1800adfd1  mov     rcx, [r14+0F8h]
0x1800adfd8  mov     rax, [rcx]
0x1800adfdb  lea     r9, [rbp+var_48]
0x1800adfdf  mov     r8d, edi
0x1800adfe2  lea     rdx, [rbp+var_44]
0x1800adfe6  mov     rax, [rax+20h]
0x1800adfea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adfef  mov     ebx, eax
0x1800adff1  test    eax, eax
0x1800adff3  jns     short loc_1800AE070
0x1800adff5  lea     rax, WPP_GLOBAL_Control
0x1800adffc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae003  cmp     rcx, rax
0x1800ae006  jz      short loc_1800AE030
0x1800ae008  test    byte ptr [rcx+1Ch], 1
0x1800ae00c  jz      short loc_1800AE030
0x1800ae00e  cmp     [rcx+19h], dil
0x1800ae012  jb      short loc_1800AE030
0x1800ae014  mov     edx, 77h ; 'w'
0x1800ae019  mov     [rsp+78h+var_58], ebx
0x1800ae01d  mov     r9d, [rsi]
0x1800ae020  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ae027  mov     rcx, [rcx+10h]
0x1800ae02b  call    WPP_SF_Dd
0x1800ae030  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae037  test    rcx, rcx
0x1800ae03a  jnz     short loc_1800AE04A
0x1800ae03c  lea     rcx, off_1800E5190; this
0x1800ae043  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae04a  cmp     byte ptr [rcx+8], 0
0x1800ae04e  jz      loc_1800AE2FC
0x1800ae054  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae059  cmp     [rax+7CCh], ebx
0x1800ae05f  jz      loc_1800AE2FC
0x1800ae065  mov     r8d, 542h
0x1800ae06b  jmp     loc_1800ADE2C
0x1800ae070  mov     eax, [rbp+var_48]
0x1800ae073  add     [r15], rax
0x1800ae076  mov     edx, [r12]
0x1800ae07a  mov     rcx, [r14+0F8h]
0x1800ae081  mov     rax, [rcx]
0x1800ae084  xor     r9d, r9d
0x1800ae087  xor     r8d, r8d
0x1800ae08a  mov     rax, [rax+28h]
0x1800ae08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae093  mov     ebx, eax
0x1800ae095  test    eax, eax
0x1800ae097  jns     short loc_1800AE114
0x1800ae099  lea     rax, WPP_GLOBAL_Control
0x1800ae0a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae0a7  cmp     rcx, rax
0x1800ae0aa  jz      short loc_1800AE0D4
0x1800ae0ac  test    byte ptr [rcx+1Ch], 1
0x1800ae0b0  jz      short loc_1800AE0D4
0x1800ae0b2  cmp     [rcx+19h], dil
0x1800ae0b6  jb      short loc_1800AE0D4
0x1800ae0b8  mov     edx, 78h ; 'x'
0x1800ae0bd  mov     [rsp+78h+var_58], ebx
0x1800ae0c1  mov     r9d, [rsi]
0x1800ae0c4  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ae0cb  mov     rcx, [rcx+10h]
0x1800ae0cf  call    WPP_SF_Dd
0x1800ae0d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae0db  test    rcx, rcx
0x1800ae0de  jnz     short loc_1800AE0EE
0x1800ae0e0  lea     rcx, off_1800E5190; this
0x1800ae0e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae0ee  cmp     byte ptr [rcx+8], 0
0x1800ae0f2  jz      loc_1800AE2FC
0x1800ae0f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae0fd  cmp     [rax+7CCh], ebx
0x1800ae103  jz      loc_1800AE2FC
0x1800ae109  mov     r8d, 548h
0x1800ae10f  jmp     loc_1800ADE2C
0x1800ae114  mov     rcx, [r14+0F8h]
0x1800ae11b  mov     rdx, [r13+10h]
0x1800ae11f  mov     r8d, [r13+18h]
0x1800ae123  sub     r8d, edx
0x1800ae126  mov     rax, [rcx]
0x1800ae129  lea     r9, [rbp+var_48]
0x1800ae12d  mov     rax, [rax+20h]
0x1800ae131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae136  mov     ebx, eax
0x1800ae138  test    eax, eax
0x1800ae13a  jns     short loc_1800AE1B7
0x1800ae13c  lea     rax, WPP_GLOBAL_Control
0x1800ae143  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae14a  cmp     rcx, rax
0x1800ae14d  jz      short loc_1800AE177
0x1800ae14f  test    byte ptr [rcx+1Ch], 1
0x1800ae153  jz      short loc_1800AE177
0x1800ae155  cmp     [rcx+19h], dil
0x1800ae159  jb      short loc_1800AE177
0x1800ae15b  mov     edx, 79h ; 'y'
0x1800ae160  mov     [rsp+78h+var_58], ebx
0x1800ae164  mov     r9d, [rsi]
0x1800ae167  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ae16e  mov     rcx, [rcx+10h]
0x1800ae172  call    WPP_SF_Dd
0x1800ae177  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae17e  test    rcx, rcx
0x1800ae181  jnz     short loc_1800AE191
0x1800ae183  lea     rcx, off_1800E5190; this
0x1800ae18a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae191  cmp     byte ptr [rcx+8], 0
0x1800ae195  jz      loc_1800AE2FC
0x1800ae19b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae1a0  cmp     [rax+7CCh], ebx
0x1800ae1a6  jz      loc_1800AE2FC
  ... truncated ...
```
