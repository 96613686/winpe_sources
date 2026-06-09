# CWMThumbnailStreamProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x18000f4a0`
- end: `0x18000faec`
- name: `?SetNativeValue@CWMThumbnailStreamProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1612`
- prototype: `__int64 __fastcall(PROPVARIANT *this, PROPVARIANT *pvarSrc)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800085a0`
- `0x18000a3f4`
- `0x18000f4a0`
- `0x18001a330`
- `0x18001c280`
- `0x18004a9f4`
- `0x18004f410`
- `0x180057904`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000f73f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000f73f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f4de`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f67f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f4de`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f67f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000f53e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000f5fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000f69b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000f75b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000f80b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000f8bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000f96a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000fa2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000f53e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000f5fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000f69b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000f75b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000f80b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000f8bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000f96a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000fa2d`

## pseudocode

```c
__int64 __fastcall CWMThumbnailStreamProperty::SetNativeValue(PROPVARIANT *this, PROPVARIANT *pvarSrc)
{
  void *v4; // rax
  BYTE *pData; // r15
  CallStackTracing *v6; // rcx
  HRESULT ImageDataPtrAndSize; // ebx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  unsigned int v11; // r13d
  CallStackTracing *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  CallStackTracing *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  BYTE *v18; // xmm1_8
  CallStackTracing *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  CallStackTracing *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  CallStackTracing *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  CallStackTracing *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  CallStackTracing *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned __int8 *v35; // [rsp+30h] [rbp-28h] BYREF
  PROPVARIANT pvarDest; // [rsp+38h] [rbp-20h] BYREF
  char v37; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v38; // [rsp+A8h] [rbp+50h] BYREF
  int v39; // [rsp+B0h] [rbp+58h] BYREF
  LPSTREAM ppstm; // [rsp+B8h] [rbp+60h] BYREF

  ppstm = 0;
  v39 = 0;
  v35 = 0;
  v38 = 0;
  memset(&pvarDest, 0, sizeof(pvarDest));
  PropVariantClear(this + 4);
  if ( (pvarSrc->vt & 0x41) == 0 )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v37,
      "CWMThumbnailStreamProperty::SetNativeValue",
      617);
    v31 = CallStackTracing::s_wpInstance;
    ImageDataPtrAndSize = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v32;
      if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
      {
        v31 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v31 = (CallStackTracing *)&qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v31 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v31);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWMThumbnailStreamProperty::SetNativeValue",
          617,
          -2147418113);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 59;
      goto LABEL_93;
    }
    goto LABEL_94;
  }
  v4 = &pvarSrc->decVal.8;
  if ( (pvarSrc->vt & 0x1000) == 0 )
  {
    pData = pvarSrc->bstrblobVal.pData;
LABEL_16:
    v11 = *(_DWORD *)v4;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v37,
      "CWMThumbnailStreamProperty::SetNativeValue",
      584);
    ImageDataPtrAndSize = CMFPropVariant::Copy(&pvarDest, pvarSrc);
    if ( ImageDataPtrAndSize >= 0 )
    {
      ImageDataPtrAndSize = PropVariantClear(this + 5);
      if ( ImageDataPtrAndSize >= 0 )
      {
        v18 = pvarDest.bstrblobVal.pData;
        *(_OWORD *)&this[5].vt = *(_OWORD *)&pvarDest.vt;
        pvarDest.vt = 0;
        this[5].bstrblobVal.pData = v18;
        ImageDataPtrAndSize = CreateStreamOnHGlobal(0, 1, &ppstm);
        if ( ImageDataPtrAndSize >= 0 )
        {
          ImageDataPtrAndSize = CWMThumbnailStreamProperty::GetImageDataPtrAndSize(
                                  (CWMThumbnailStreamProperty *)this,
                                  pData,
                                  v11,
                                  &v35,
                                  &v38);
          if ( ImageDataPtrAndSize >= 0 )
          {
            ImageDataPtrAndSize = ((__int64 (__fastcall *)(LPSTREAM, unsigned __int8 *, _QWORD, int *))ppstm->lpVtbl->Write)(
                                    ppstm,
                                    v35,
                                    v38,
                                    &v39);
            if ( ImageDataPtrAndSize >= 0 )
            {
              ImageDataPtrAndSize = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(
                                      ppstm,
                                      0,
                                      0,
                                      0);
              if ( ImageDataPtrAndSize >= 0 )
              {
                this[4].hVal.QuadPart = (LONGLONG)ppstm;
                this[4].vt = 66;
                ppstm = 0;
              }
              else
              {
                v28 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v29;
                  if ( v29
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
                  {
                    v28 = CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v28 = (CallStackTracing *)&qword_180069A90;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                  }
                }
                if ( *((_BYTE *)v28 + 8) )
                {
                  v30 = CallStackTracing::GetThreadRelativeContext(v28);
                  if ( *((_DWORD *)v30 + 499) != ImageDataPtrAndSize )
                    CallStackContext::TraceFailure(
                      v30,
                      "CWMThumbnailStreamProperty::SetNativeValue",
                      606,
                      ImageDataPtrAndSize);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v10 = 58;
                  goto LABEL_93;
                }
              }
            }
            else
            {
              v25 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v26;
                if ( v26
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
                {
                  v25 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v25 = (CallStackTracing *)&qword_180069A90;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                }
              }
              if ( *((_BYTE *)v25 + 8) )
              {
                v27 = CallStackTracing::GetThreadRelativeContext(v25);
                if ( *((_DWORD *)v27 + 499) != ImageDataPtrAndSize )
                  CallStackContext::TraceFailure(
                    v27,
                    "CWMThumbnailStreamProperty::SetNativeValue",
                    604,
                    ImageDataPtrAndSize);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v10 = 57;
                goto LABEL_93;
              }
            }
          }
          else
          {
            v22 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v23;
              if ( v23
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
              {
                v22 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v22 = (CallStackTracing *)&qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v22 + 8) )
            {
              v24 = CallStackTracing::GetThreadRelativeContext(v22);
              if ( *((_DWORD *)v24 + 499) != ImageDataPtrAndSize )
                CallStackContext::TraceFailure(
                  v24,
                  "CWMThumbnailStreamProperty::SetNativeValue",
                  602,
                  ImageDataPtrAndSize);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v10 = 56;
              goto LABEL_93;
            }
          }
        }
        else
        {
          v19 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v20;
            if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
            {
              v19 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v19 = (CallStackTracing *)&qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v19 + 8) )
          {
            v21 = CallStackTracing::GetThreadRelativeContext(v19);
            if ( *((_DWORD *)v21 + 499) != ImageDataPtrAndSize )
              CallStackContext::TraceFailure(
                v21,
                "CWMThumbnailStreamProperty::SetNativeValue",
                600,
                ImageDataPtrAndSize);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v10 = 55;
            goto LABEL_93;
          }
        }
      }
      else
      {
        v15 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = (CallStackTracing *)&qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext(v15);
          if ( *((_DWORD *)v17 + 499) != ImageDataPtrAndSize )
            CallStackContext::TraceFailure(v17, "CWMThumbnailStreamProperty::SetNativeValue", 585, ImageDataPtrAndSize);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 54;
          goto LABEL_93;
        }
      }
    }
    else
    {
      v12 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = (CallStackTracing *)&qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext(v12);
        if ( *((_DWORD *)v14 + 499) != ImageDataPtrAndSize )
          CallStackContext::TraceFailure(v14, "CWMThumbnailStreamProperty::SetNativeValue", 584, ImageDataPtrAndSize);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 53;
        goto LABEL_93;
      }
    }
    goto LABEL_94;
  }
  if ( *(_DWORD *)v4 )
  {
    v4 = pvarSrc->bstrblobVal.pData;
    pData = (BYTE *)*((_QWORD *)v4 + 1);
    goto LABEL_16;
  }
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v37,
    "CWMThumbnailStreamProperty::SetNativeValue",
    570);
  v6 = CallStackTracing::s_wpInstance;
  ImageDataPtrAndSize = -2147024809;
  if ( !CallStackTracing::s_wpInstance )
  {
    v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v8;
    if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
    {
      v6 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v6 = (CallStackTracing *)&qword_180069A90;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
  }
  if ( *((_BYTE *)v6 + 8) )
  {
    v9 = CallStackTracing::GetThreadRelativeContext(v6);
    if ( *((_DWORD *)v9 + 499) != -2147024809 )
      CallStackContext::TraceFailure(v9, "CWMThumbnailStreamProperty::SetNativeValue", 570, -2147024809);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v10 = 52;
LABEL_93:
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
      this,
      ImageDataPtrAndSize);
  }
LABEL_94:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v37);
  CMFPropVariant::Clear(&pvarDest);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppstm);
  return (unsigned int)ImageDataPtrAndSize;
}

```

## disassembly

```asm
0x18000f4a0  push    rbp
0x18000f4a2  push    rbx
0x18000f4a3  push    rsi
0x18000f4a4  push    rdi
0x18000f4a5  push    r12
0x18000f4a7  push    r13
0x18000f4a9  push    r14
0x18000f4ab  push    r15
0x18000f4ad  mov     rbp, rsp
0x18000f4b0  sub     rsp, 58h
0x18000f4b4  xor     r14d, r14d
0x18000f4b7  mov     rsi, rcx
0x18000f4ba  xorps   xmm0, xmm0
0x18000f4bd  mov     [rbp+ppstm], r14
0x18000f4c1  xor     eax, eax
0x18000f4c3  mov     [rbp+arg_10], r14d
0x18000f4c7  add     rcx, 60h ; '`'; pvar
0x18000f4cb  mov     [rbp+var_28], r14
0x18000f4cf  mov     [rbp+arg_8], r14d
0x18000f4d3  mov     rbx, rdx
0x18000f4d6  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18000f4da  mov     qword ptr [rbp+pvarDest+10h], rax
0x18000f4de  call    cs:__imp_PropVariantClear
0x18000f4e4  test    byte ptr [rbx], 41h
0x18000f4e7  jz      loc_18000FA00
0x18000f4ed  mov     ecx, 1000h
0x18000f4f2  lea     rax, [rbx+8]
0x18000f4f6  test    [rbx], cx
0x18000f4f9  jz      loc_18000F5BA
0x18000f4ff  cmp     [rax], r14d
0x18000f502  jbe     short loc_18000F511
0x18000f504  mov     rax, [rbx+10h]
0x18000f508  mov     r15, [rax+8]
0x18000f50c  jmp     loc_18000F5BE
0x18000f511  mov     r15d, 23Ah
0x18000f517  lea     rdi, aCwmthumbnailst_2; "CWMThumbnailStreamProperty::SetNativeVa"...
0x18000f51e  mov     r8d, r15d; int
0x18000f521  lea     rcx, [rbp+arg_0]; this
0x18000f525  mov     rdx, rdi; char *
0x18000f528  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000f52d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f534  mov     ebx, 80070057h
0x18000f539  test    rcx, rcx
0x18000f53c  jnz     short loc_18000F57F
0x18000f53e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000f544  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f54b  mov     rcx, rax
0x18000f54e  test    rax, rax
0x18000f551  jz      short loc_18000F571
0x18000f553  mov     rax, [rax]
0x18000f556  mov     edx, 7F0h
0x18000f55b  mov     rax, [rax+8]
0x18000f55f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f564  test    eax, eax
0x18000f566  jz      short loc_18000F571
0x18000f568  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f56f  jmp     short loc_18000F57F
0x18000f571  lea     rcx, qword_180069A90; this
0x18000f578  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f57f  cmp     [rcx+8], r14b
0x18000f583  jz      short loc_18000F5A3
0x18000f585  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000f58a  cmp     [rax+7CCh], ebx
0x18000f590  jz      short loc_18000F5A3
0x18000f592  mov     r9d, ebx; int
0x18000f595  mov     r8d, r15d; int
0x18000f598  mov     rdx, rdi; char *
0x18000f59b  mov     rcx, rax; this
0x18000f59e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000f5a3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000f5a8  cmp     al, 1
0x18000f5aa  jb      loc_18000FABE
0x18000f5b0  mov     edx, 34h ; '4'
0x18000f5b5  jmp     loc_18000FAA0
0x18000f5ba  mov     r15, [rbx+10h]
0x18000f5be  mov     r13d, [rax]
0x18000f5c1  lea     rdi, aCwmthumbnailst_2; "CWMThumbnailStreamProperty::SetNativeVa"...
0x18000f5c8  mov     rdx, rdi; char *
0x18000f5cb  lea     rcx, [rbp+arg_0]; this
0x18000f5cf  mov     r8d, 248h; int
0x18000f5d5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000f5da  mov     rdx, rbx; pvarSrc
0x18000f5dd  lea     rcx, [rbp+pvarDest]; pvarDest
0x18000f5e1  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x18000f5e6  mov     ebx, eax
0x18000f5e8  test    eax, eax
0x18000f5ea  jns     loc_18000F67B
0x18000f5f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f5f7  test    rcx, rcx
0x18000f5fa  jnz     short loc_18000F63D
0x18000f5fc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000f602  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f609  mov     rcx, rax
0x18000f60c  test    rax, rax
0x18000f60f  jz      short loc_18000F62F
0x18000f611  mov     rax, [rax]
0x18000f614  mov     edx, 7F0h
0x18000f619  mov     rax, [rax+8]
0x18000f61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f622  test    eax, eax
0x18000f624  jz      short loc_18000F62F
0x18000f626  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f62d  jmp     short loc_18000F63D
0x18000f62f  lea     rcx, qword_180069A90; this
0x18000f636  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f63d  cmp     [rcx+8], r14b
0x18000f641  jz      short loc_18000F664
0x18000f643  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000f648  cmp     [rax+7CCh], ebx
0x18000f64e  jz      short loc_18000F664
0x18000f650  mov     r9d, ebx; int
0x18000f653  mov     r8d, 248h; int
0x18000f659  mov     rdx, rdi; char *
0x18000f65c  mov     rcx, rax; this
0x18000f65f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000f664  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000f669  cmp     al, 1
0x18000f66b  jb      loc_18000FABE
0x18000f671  mov     edx, 35h ; '5'
0x18000f676  jmp     loc_18000FAA0
0x18000f67b  lea     rcx, [rsi+78h]; pvar
0x18000f67f  call    cs:__imp_PropVariantClear
0x18000f685  mov     ebx, eax
0x18000f687  test    eax, eax
0x18000f689  jns     loc_18000F71A
0x18000f68f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f696  test    rcx, rcx
0x18000f699  jnz     short loc_18000F6DC
0x18000f69b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000f6a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f6a8  mov     rcx, rax
0x18000f6ab  test    rax, rax
0x18000f6ae  jz      short loc_18000F6CE
0x18000f6b0  mov     rax, [rax]
0x18000f6b3  mov     edx, 7F0h
0x18000f6b8  mov     rax, [rax+8]
0x18000f6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6c1  test    eax, eax
0x18000f6c3  jz      short loc_18000F6CE
0x18000f6c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f6cc  jmp     short loc_18000F6DC
0x18000f6ce  lea     rcx, qword_180069A90; this
0x18000f6d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f6dc  cmp     [rcx+8], r14b
0x18000f6e0  jz      short loc_18000F703
0x18000f6e2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000f6e7  cmp     [rax+7CCh], ebx
0x18000f6ed  jz      short loc_18000F703
0x18000f6ef  mov     r9d, ebx; int
0x18000f6f2  mov     r8d, 249h; int
0x18000f6f8  mov     rdx, rdi; char *
0x18000f6fb  mov     rcx, rax; this
0x18000f6fe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000f703  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000f708  cmp     al, 1
0x18000f70a  jb      loc_18000FABE
0x18000f710  mov     edx, 36h ; '6'
0x18000f715  jmp     loc_18000FAA0
0x18000f71a  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x18000f71e  lea     r8, [rbp+ppstm]; ppstm
0x18000f722  mov     edx, 1; fDeleteOnRelease
0x18000f727  movsd   xmm1, qword ptr [rbp+pvarDest+10h]
0x18000f72c  xor     ecx, ecx; hGlobal
0x18000f72e  movups  xmmword ptr [rsi+78h], xmm0
0x18000f732  mov     word ptr [rbp+pvarDest], r14w
0x18000f737  movsd   qword ptr [rsi+88h], xmm1
0x18000f73f  call    cs:__imp_CreateStreamOnHGlobal
0x18000f745  mov     ebx, eax
0x18000f747  test    eax, eax
0x18000f749  jns     loc_18000F7DA
0x18000f74f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f756  test    rcx, rcx
0x18000f759  jnz     short loc_18000F79C
0x18000f75b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000f761  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f768  mov     rcx, rax
0x18000f76b  test    rax, rax
0x18000f76e  jz      short loc_18000F78E
0x18000f770  mov     rax, [rax]
0x18000f773  mov     edx, 7F0h
0x18000f778  mov     rax, [rax+8]
0x18000f77c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f781  test    eax, eax
0x18000f783  jz      short loc_18000F78E
0x18000f785  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f78c  jmp     short loc_18000F79C
0x18000f78e  lea     rcx, qword_180069A90; this
0x18000f795  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f79c  cmp     [rcx+8], r14b
0x18000f7a0  jz      short loc_18000F7C3
0x18000f7a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000f7a7  cmp     [rax+7CCh], ebx
0x18000f7ad  jz      short loc_18000F7C3
0x18000f7af  mov     r9d, ebx; int
0x18000f7b2  mov     r8d, 258h; int
0x18000f7b8  mov     rdx, rdi; char *
0x18000f7bb  mov     rcx, rax; this
0x18000f7be  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000f7c3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000f7c8  cmp     al, 1
0x18000f7ca  jb      loc_18000FABE
0x18000f7d0  mov     edx, 37h ; '7'
0x18000f7d5  jmp     loc_18000FAA0
0x18000f7da  lea     rax, [rbp+arg_8]
0x18000f7de  mov     r8d, r13d; unsigned int
0x18000f7e1  lea     r9, [rbp+var_28]; unsigned __int8 **
0x18000f7e5  mov     [rsp+58h+var_38], rax; unsigned int *
0x18000f7ea  mov     rdx, r15; unsigned __int8 *
0x18000f7ed  mov     rcx, rsi; this
0x18000f7f0  call    ?GetImageDataPtrAndSize@CWMThumbnailStreamProperty@@AEAAJPEBEKPEAPEAEPEAK@Z; CWMThumbnailStreamProperty::GetImageDataPtrAndSize(uchar const *,ulong,uchar * *,ulong *)
0x18000f7f5  mov     ebx, eax
0x18000f7f7  test    eax, eax
0x18000f7f9  jns     loc_18000F88A
0x18000f7ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f806  test    rcx, rcx
0x18000f809  jnz     short loc_18000F84C
0x18000f80b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000f811  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f818  mov     rcx, rax
0x18000f81b  test    rax, rax
0x18000f81e  jz      short loc_18000F83E
0x18000f820  mov     rax, [rax]
0x18000f823  mov     edx, 7F0h
0x18000f828  mov     rax, [rax+8]
0x18000f82c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f831  test    eax, eax
0x18000f833  jz      short loc_18000F83E
0x18000f835  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f83c  jmp     short loc_18000F84C
0x18000f83e  lea     rcx, qword_180069A90; this
0x18000f845  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f84c  cmp     [rcx+8], r14b
0x18000f850  jz      short loc_18000F873
0x18000f852  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000f857  cmp     [rax+7CCh], ebx
0x18000f85d  jz      short loc_18000F873
0x18000f85f  mov     r9d, ebx; int
0x18000f862  mov     r8d, 25Ah; int
0x18000f868  mov     rdx, rdi; char *
0x18000f86b  mov     rcx, rax; this
0x18000f86e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000f873  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000f878  cmp     al, 1
0x18000f87a  jb      loc_18000FABE
0x18000f880  mov     edx, 38h ; '8'
0x18000f885  jmp     loc_18000FAA0
0x18000f88a  mov     rcx, [rbp+ppstm]
0x18000f88e  lea     r9, [rbp+arg_10]
0x18000f892  mov     r8d, [rbp+arg_8]
0x18000f896  mov     rdx, [rbp+var_28]
0x18000f89a  mov     rax, [rcx]
0x18000f89d  mov     rax, [rax+20h]
0x18000f8a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8a6  mov     ebx, eax
0x18000f8a8  test    eax, eax
0x18000f8aa  jns     loc_18000F93B
0x18000f8b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f8b7  test    rcx, rcx
0x18000f8ba  jnz     short loc_18000F8FD
0x18000f8bc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000f8c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f8c9  mov     rcx, rax
0x18000f8cc  test    rax, rax
0x18000f8cf  jz      short loc_18000F8EF
0x18000f8d1  mov     rax, [rax]
0x18000f8d4  mov     edx, 7F0h
0x18000f8d9  mov     rax, [rax+8]
0x18000f8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8e2  test    eax, eax
0x18000f8e4  jz      short loc_18000F8EF
0x18000f8e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f8ed  jmp     short loc_18000F8FD
0x18000f8ef  lea     rcx, qword_180069A90; this
0x18000f8f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f8fd  cmp     [rcx+8], r14b
0x18000f901  jz      short loc_18000F924
0x18000f903  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000f908  cmp     [rax+7CCh], ebx
0x18000f90e  jz      short loc_18000F924
0x18000f910  mov     r9d, ebx; int
0x18000f913  mov     r8d, 25Ch; int
0x18000f919  mov     rdx, rdi; char *
0x18000f91c  mov     rcx, rax; this
0x18000f91f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000f924  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000f929  cmp     al, 1
0x18000f92b  jb      loc_18000FABE
0x18000f931  mov     edx, 39h ; '9'
0x18000f936  jmp     loc_18000FAA0
0x18000f93b  mov     rcx, [rbp+ppstm]
0x18000f93f  mov     rdx, r14
0x18000f942  xor     r9d, r9d
0x18000f945  xor     r8d, r8d
0x18000f948  mov     rax, [rcx]
0x18000f94b  mov     rax, [rax+28h]
0x18000f94f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f954  mov     ebx, eax
0x18000f956  test    eax, eax
0x18000f958  jns     loc_18000F9E9
0x18000f95e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
