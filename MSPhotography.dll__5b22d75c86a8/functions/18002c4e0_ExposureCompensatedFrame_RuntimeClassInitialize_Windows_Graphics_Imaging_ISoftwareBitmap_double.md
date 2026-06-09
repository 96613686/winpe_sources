# ExposureCompensatedFrame::RuntimeClassInitialize(Windows::Graphics::Imaging::ISoftwareBitmap *,double)

- ea: `0x18002c4e0`
- end: `0x18002ca85`
- name: `?RuntimeClassInitialize@ExposureCompensatedFrame@@QEAAJPEAUISoftwareBitmap@Imaging@Graphics@Windows@@N@Z`
- size: `1445`
- prototype: `__int64 __fastcall(ExposureCompensatedFrame *__hidden this, struct Windows::Graphics::Imaging::ISoftwareBitmap *, double)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18002abc8`

## callees

- `0x180002420`
- `0x18000b490`
- `0x18000c0f8`
- `0x18002a9bc`
- `0x18002aa84`
- `0x18002ae0c`
- `0x18002afd0`
- `0x18002bb98`
- `0x18002c134`
- `0x18002c220`
- `0x18002c4e0`
- `0x18012f850`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18002c6cf`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18002c6cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c569`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c633`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c6e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c79c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c846`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c8f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c99c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c569`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c633`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c6e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c79c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c846`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c8f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c99c`

## string_xrefs

- `0x18002c50c`: `ExposureCompensatedFrame::RuntimeClassInitialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ExposureCompensatedFrame::RuntimeClassInitialize(
        ExposureCompensatedFrame *this,
        struct Windows::Graphics::Imaging::ISoftwareBitmap *a2,
        double a3)
{
  int v5; // edx
  int v6; // eax
  __int64 *v7; // rcx
  int Buffer; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  struct IInspectable **v18; // r14
  __int64 (__fastcall *v19)(struct Windows::Graphics::Imaging::ISoftwareBitmap *, __int64, char *); // rbx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v33[4]; // [rsp+30h] [rbp-50h] BYREF
  int v34; // [rsp+34h] [rbp-4Ch] BYREF
  unsigned __int8 *v35; // [rsp+38h] [rbp-48h] BYREF
  __int128 v36; // [rsp+40h] [rbp-40h] BYREF
  __int128 v37; // [rsp+50h] [rbp-30h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v33,
    "ExposureCompensatedFrame::RuntimeClassInitialize",
    35);
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  if ( a2 )
  {
    Buffer = (*(__int64 (__fastcall **)(struct Windows::Graphics::Imaging::ISoftwareBitmap *, int *))(*(_QWORD *)a2 + 48LL))(
               a2,
               &v34);
    if ( Buffer >= 0 )
    {
      if ( v34 == 103 )
      {
        v18 = (struct IInspectable **)((char *)this + 40);
        v19 = *(__int64 (__fastcall **)(struct Windows::Graphics::Imaging::ISoftwareBitmap *, __int64, char *))(*(_QWORD *)a2 + 120LL);
        Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease((char *)this + 40);
        Buffer = v19(a2, 1, (char *)this + 40);
        if ( Buffer >= 0 )
        {
          Buffer = ((__int64 (__fastcall *)(struct IInspectable *, _QWORD, __int128 *))(*v18)->lpVtbl[1].AddRef)(
                     *v18,
                     0,
                     &v36);
          if ( Buffer >= 0 )
          {
            Buffer = ((__int64 (__fastcall *)(struct IInspectable *, __int64, __int128 *))(*v18)->lpVtbl[1].AddRef)(
                       *v18,
                       1,
                       &v37);
            if ( Buffer >= 0 )
            {
              Buffer = MemoryBufferByteAccess::GetBuffer(
                         (ExposureCompensatedFrame *)((char *)this + 48),
                         *v18,
                         &v35,
                         (unsigned int *)this + 18);
              if ( Buffer >= 0 )
              {
                *(_QWORD *)((char *)this + 76) = *(_QWORD *)((char *)&v36 + 4);
                *((_DWORD *)this + 21) = HIDWORD(v36);
                Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>::operator=((char *)this + 32, a2);
                *((_QWORD *)this + 7) = &v35[(int)v36];
                *((_QWORD *)this + 8) = &v35[(int)v37];
                *((double *)this + 11) = a3;
                goto LABEL_81;
              }
              v29 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v30;
                if ( v30
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
                {
                  v29 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v29 = &qword_18015FF10;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
                }
              }
              if ( *((_BYTE *)v29 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != Buffer )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "ExposureCompensatedFrame::RuntimeClassInitialize",
                    53,
                    Buffer);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v11 = 17;
                goto LABEL_13;
              }
            }
            else
            {
              v26 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v27;
                if ( v27
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
                {
                  v26 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v26 = &qword_18015FF10;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
                }
              }
              if ( *((_BYTE *)v26 + 8) )
              {
                v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
                if ( *((_DWORD *)v28 + 499) != Buffer )
                  CallStackContext::TraceFailure(v28, "ExposureCompensatedFrame::RuntimeClassInitialize", 52, Buffer);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v11 = 16;
                goto LABEL_13;
              }
            }
          }
          else
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v24;
              if ( v24
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
              {
                v23 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v23 = &qword_18015FF10;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
              }
            }
            if ( *((_BYTE *)v23 + 8) )
            {
              v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
              if ( *((_DWORD *)v25 + 499) != Buffer )
                CallStackContext::TraceFailure(v25, "ExposureCompensatedFrame::RuntimeClassInitialize", 51, Buffer);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v11 = 15;
              goto LABEL_13;
            }
          }
        }
        else
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v21;
            if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
            {
              v20 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v20 = &qword_18015FF10;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
            }
          }
          if ( *((_BYTE *)v20 + 8) )
          {
            v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)v22 + 499) != Buffer )
              CallStackContext::TraceFailure(v22, "ExposureCompensatedFrame::RuntimeClassInitialize", 50, Buffer);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v11 = 14;
            goto LABEL_13;
          }
        }
      }
      else
      {
        Buffer = -2147024809;
        RoOriginateErrorW(2147942487LL, 63, L"HighDynamicRangeFusion::AddFrame expects NV12 BitmapPixelFormat");
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = &qword_18015FF10;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
          }
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)v17 + 499) != -2147024809 )
            CallStackContext::TraceFailure(v17, "ExposureCompensatedFrame::RuntimeClassInitialize", 46, -2147024809);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 13;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_18015FF10;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)v14 + 499) != Buffer )
          CallStackContext::TraceFailure(v14, "ExposureCompensatedFrame::RuntimeClassInitialize", 43, Buffer);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v11 = 12;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v6 = MF::OriginateError((MF *)0x80004003LL, v5);
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    Buffer = v6;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_18015FF10;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( Buffer < 0 && *((_DWORD *)v10 + 499) != Buffer )
        CallStackContext::TraceFailure(v10, "ExposureCompensatedFrame::RuntimeClassInitialize", 40, Buffer);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 11;
LABEL_13:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_20add21d00883791bc3e32820add1df0_Traceguids, this, Buffer);
    }
  }
LABEL_81:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v33);
  return (unsigned int)Buffer;
}

```

## disassembly

```asm
0x18002c4e0  mov     [rsp-28h+arg_10], rbx
0x18002c4e5  push    rbp
0x18002c4e6  push    rsi
0x18002c4e7  push    rdi
0x18002c4e8  push    r12
0x18002c4ea  push    r14
0x18002c4ec  mov     rbp, rsp
0x18002c4ef  sub     rsp, 80h
0x18002c4f6  movaps  [rsp+80h+var_10], xmm6
0x18002c4fb  mov     rax, cs:__security_cookie
0x18002c502  xor     rax, rsp
0x18002c505  mov     [rbp+var_20], rax
0x18002c509  mov     rsi, rdx
0x18002c50c  lea     r12, aExposurecompen; "ExposureCompensatedFrame::RuntimeClassI"...
0x18002c513  mov     rdi, rcx
0x18002c516  mov     rdx, r12; char *
0x18002c519  mov     r8d, 23h ; '#'; int
0x18002c51f  lea     rcx, [rbp+var_50]; this
0x18002c523  movaps  xmm6, xmm2
0x18002c526  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002c52b  mov     [rbp+var_4C], 0
0x18002c532  xorps   xmm0, xmm0
0x18002c535  mov     [rbp+var_48], 0
0x18002c53d  xorps   xmm1, xmm1
0x18002c540  movups  [rbp+var_40], xmm0
0x18002c544  movups  [rbp+var_30], xmm1
0x18002c548  test    rsi, rsi
0x18002c54b  jnz     loc_18002C60A
0x18002c551  mov     ecx, 80004003h; this
0x18002c556  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x18002c55b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c562  mov     ebx, eax
0x18002c564  test    rcx, rcx
0x18002c567  jnz     short loc_18002C5AA
0x18002c569  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c56f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c576  mov     rcx, rax
0x18002c579  test    rax, rax
0x18002c57c  jz      short loc_18002C59C
0x18002c57e  mov     rax, [rax]
0x18002c581  mov     edx, 7F0h
0x18002c586  mov     rax, [rax+8]
0x18002c58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c58f  test    eax, eax
0x18002c591  jz      short loc_18002C59C
0x18002c593  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c59a  jmp     short loc_18002C5AA
0x18002c59c  lea     rcx, qword_18015FF10; this
0x18002c5a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c5aa  cmp     byte ptr [rcx+8], 0
0x18002c5ae  jz      short loc_18002C5D5
0x18002c5b0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c5b5  test    ebx, ebx
0x18002c5b7  jns     short loc_18002C5D5
0x18002c5b9  cmp     [rax+7CCh], ebx
0x18002c5bf  jz      short loc_18002C5D5
0x18002c5c1  mov     r9d, ebx; int
0x18002c5c4  mov     r8d, 28h ; '('; int
0x18002c5ca  mov     rdx, r12; char *
0x18002c5cd  mov     rcx, rax; this
0x18002c5d0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002c5d5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002c5da  cmp     al, 1
0x18002c5dc  jb      loc_18002CA52
0x18002c5e2  mov     edx, 0Bh
0x18002c5e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c5ee  lea     r8, WPP_20add21d00883791bc3e32820add1df0_Traceguids
0x18002c5f5  mov     r9, rdi
0x18002c5f8  mov     [rsp+80h+var_60], ebx
0x18002c5fc  mov     rcx, [rcx+10h]
0x18002c600  call    WPP_SF_qD
0x18002c605  jmp     loc_18002CA52
0x18002c60a  mov     rax, [rsi]
0x18002c60d  lea     rdx, [rbp+var_4C]
0x18002c611  mov     rcx, rsi
0x18002c614  mov     rax, [rax+30h]
0x18002c618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c61d  mov     ebx, eax
0x18002c61f  test    eax, eax
0x18002c621  jns     loc_18002C6B2
0x18002c627  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c62e  test    rcx, rcx
0x18002c631  jnz     short loc_18002C674
0x18002c633  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c639  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c640  mov     rcx, rax
0x18002c643  test    rax, rax
0x18002c646  jz      short loc_18002C666
0x18002c648  mov     rax, [rax]
0x18002c64b  mov     edx, 7F0h
0x18002c650  mov     rax, [rax+8]
0x18002c654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c659  test    eax, eax
0x18002c65b  jz      short loc_18002C666
0x18002c65d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c664  jmp     short loc_18002C674
0x18002c666  lea     rcx, qword_18015FF10; this
0x18002c66d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c674  cmp     byte ptr [rcx+8], 0
0x18002c678  jz      short loc_18002C69B
0x18002c67a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c67f  cmp     [rax+7CCh], ebx
0x18002c685  jz      short loc_18002C69B
0x18002c687  mov     r9d, ebx; int
0x18002c68a  mov     r8d, 2Bh ; '+'; int
0x18002c690  mov     rdx, r12; char *
0x18002c693  mov     rcx, rax; this
0x18002c696  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002c69b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002c6a0  cmp     al, 1
0x18002c6a2  jb      loc_18002CA52
0x18002c6a8  mov     edx, 0Ch
0x18002c6ad  jmp     loc_18002C5E7
0x18002c6b2  cmp     [rbp+var_4C], 67h ; 'g'
0x18002c6b6  jz      loc_18002C760
0x18002c6bc  mov     ebx, 80070057h
0x18002c6c1  lea     r8, aHighdynamicran_5; "HighDynamicRangeFusion::AddFrame expect"...
0x18002c6c8  mov     ecx, ebx
0x18002c6ca  mov     edx, 3Fh ; '?'
0x18002c6cf  call    cs:__imp_RoOriginateErrorW
0x18002c6d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c6dc  test    rcx, rcx
0x18002c6df  jnz     short loc_18002C722
0x18002c6e1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c6e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c6ee  mov     rcx, rax
0x18002c6f1  test    rax, rax
0x18002c6f4  jz      short loc_18002C714
0x18002c6f6  mov     rax, [rax]
0x18002c6f9  mov     edx, 7F0h
0x18002c6fe  mov     rax, [rax+8]
0x18002c702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c707  test    eax, eax
0x18002c709  jz      short loc_18002C714
0x18002c70b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c712  jmp     short loc_18002C722
0x18002c714  lea     rcx, qword_18015FF10; this
0x18002c71b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c722  cmp     byte ptr [rcx+8], 0
0x18002c726  jz      short loc_18002C749
0x18002c728  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c72d  cmp     [rax+7CCh], ebx
0x18002c733  jz      short loc_18002C749
0x18002c735  mov     r9d, ebx; int
0x18002c738  mov     r8d, 2Eh ; '.'; int
0x18002c73e  mov     rdx, r12; char *
0x18002c741  mov     rcx, rax; this
0x18002c744  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002c749  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002c74e  cmp     al, 1
0x18002c750  jb      loc_18002CA52
0x18002c756  mov     edx, 0Dh
0x18002c75b  jmp     loc_18002C5E7
0x18002c760  mov     rax, [rsi]
0x18002c763  lea     r14, [rdi+28h]
0x18002c767  mov     rcx, r14
0x18002c76a  mov     rbx, [rax+78h]
0x18002c76e  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x18002c773  mov     r8, r14
0x18002c776  mov     edx, 1
0x18002c77b  mov     rcx, rsi
0x18002c77e  mov     rax, rbx
0x18002c781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c786  mov     ebx, eax
0x18002c788  test    eax, eax
0x18002c78a  jns     loc_18002C81B
0x18002c790  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c797  test    rcx, rcx
0x18002c79a  jnz     short loc_18002C7DD
0x18002c79c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c7a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c7a9  mov     rcx, rax
0x18002c7ac  test    rax, rax
0x18002c7af  jz      short loc_18002C7CF
0x18002c7b1  mov     rax, [rax]
0x18002c7b4  mov     edx, 7F0h
0x18002c7b9  mov     rax, [rax+8]
0x18002c7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7c2  test    eax, eax
0x18002c7c4  jz      short loc_18002C7CF
0x18002c7c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c7cd  jmp     short loc_18002C7DD
0x18002c7cf  lea     rcx, qword_18015FF10; this
0x18002c7d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c7dd  cmp     byte ptr [rcx+8], 0
0x18002c7e1  jz      short loc_18002C804
0x18002c7e3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c7e8  cmp     [rax+7CCh], ebx
0x18002c7ee  jz      short loc_18002C804
0x18002c7f0  mov     r9d, ebx; int
0x18002c7f3  mov     r8d, 32h ; '2'; int
0x18002c7f9  mov     rdx, r12; char *
0x18002c7fc  mov     rcx, rax; this
0x18002c7ff  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002c804  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002c809  cmp     al, 1
0x18002c80b  jb      loc_18002CA52
0x18002c811  mov     edx, 0Eh
0x18002c816  jmp     loc_18002C5E7
0x18002c81b  mov     rcx, [r14]
0x18002c81e  lea     r8, [rbp+var_40]
0x18002c822  xor     edx, edx
0x18002c824  mov     rax, [rcx]
0x18002c827  mov     rax, [rax+38h]
0x18002c82b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c830  mov     ebx, eax
0x18002c832  test    eax, eax
0x18002c834  jns     loc_18002C8C5
0x18002c83a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c841  test    rcx, rcx
0x18002c844  jnz     short loc_18002C887
0x18002c846  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c84c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c853  mov     rcx, rax
0x18002c856  test    rax, rax
0x18002c859  jz      short loc_18002C879
0x18002c85b  mov     rax, [rax]
0x18002c85e  mov     edx, 7F0h
0x18002c863  mov     rax, [rax+8]
0x18002c867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c86c  test    eax, eax
0x18002c86e  jz      short loc_18002C879
0x18002c870  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c877  jmp     short loc_18002C887
0x18002c879  lea     rcx, qword_18015FF10; this
0x18002c880  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c887  cmp     byte ptr [rcx+8], 0
0x18002c88b  jz      short loc_18002C8AE
0x18002c88d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c892  cmp     [rax+7CCh], ebx
0x18002c898  jz      short loc_18002C8AE
0x18002c89a  mov     r9d, ebx; int
0x18002c89d  mov     r8d, 33h ; '3'; int
0x18002c8a3  mov     rdx, r12; char *
0x18002c8a6  mov     rcx, rax; this
0x18002c8a9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002c8ae  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002c8b3  cmp     al, 1
0x18002c8b5  jb      loc_18002CA52
0x18002c8bb  mov     edx, 0Fh
0x18002c8c0  jmp     loc_18002C5E7
0x18002c8c5  mov     rcx, [r14]
0x18002c8c8  lea     r8, [rbp+var_30]
0x18002c8cc  mov     edx, 1
0x18002c8d1  mov     rax, [rcx]
0x18002c8d4  mov     rax, [rax+38h]
0x18002c8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8dd  mov     ebx, eax
0x18002c8df  test    eax, eax
0x18002c8e1  jns     loc_18002C972
0x18002c8e7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c8ee  test    rcx, rcx
0x18002c8f1  jnz     short loc_18002C934
0x18002c8f3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c8f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c900  mov     rcx, rax
0x18002c903  test    rax, rax
0x18002c906  jz      short loc_18002C926
0x18002c908  mov     rax, [rax]
0x18002c90b  mov     edx, 7F0h
0x18002c910  mov     rax, [rax+8]
0x18002c914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c919  test    eax, eax
0x18002c91b  jz      short loc_18002C926
0x18002c91d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c924  jmp     short loc_18002C934
0x18002c926  lea     rcx, qword_18015FF10; this
0x18002c92d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c934  cmp     byte ptr [rcx+8], 0
0x18002c938  jz      short loc_18002C95B
0x18002c93a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c93f  cmp     [rax+7CCh], ebx
0x18002c945  jz      short loc_18002C95B
0x18002c947  mov     r9d, ebx; int
0x18002c94a  mov     r8d, 34h ; '4'; int
0x18002c950  mov     rdx, r12; char *
0x18002c953  mov     rcx, rax; this
0x18002c956  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002c95b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002c960  cmp     al, 1
0x18002c962  jb      loc_18002CA52
0x18002c968  mov     edx, 10h
0x18002c96d  jmp     loc_18002C5E7
0x18002c972  mov     rdx, [r14]; struct IInspectable *
0x18002c975  lea     r9, [rdi+48h]; unsigned int *
0x18002c979  lea     rcx, [rdi+30h]; this
0x18002c97d  lea     r8, [rbp+var_48]; unsigned __int8 **
0x18002c981  call    ?GetBuffer@MemoryBufferByteAccess@@QEAAJPEAUIInspectable@@PEAPEAEPEAI@Z; MemoryBufferByteAccess::GetBuffer(IInspectable *,uchar * *,uint *)
0x18002c986  mov     ebx, eax
0x18002c988  test    eax, eax
0x18002c98a  jns     loc_18002CA17
0x18002c990  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c997  test    rcx, rcx
0x18002c99a  jnz     short loc_18002C9DD
0x18002c99c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c9a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c9a9  mov     rcx, rax
0x18002c9ac  test    rax, rax
0x18002c9af  jz      short loc_18002C9CF
0x18002c9b1  mov     rax, [rax]
  ... truncated ...
```
