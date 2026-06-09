# CWMProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x18004c280`
- end: `0x18004c7e3`
- name: `?SetNativeValue@CWMProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1379`
- prototype: `int(CWMProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014a80`
- `0x18004c7f0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x18004c280`
- `0x18004d62c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004c2b7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004c356`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004c2b7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004c356`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004c3f7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004c601`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004c3f7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004c601`
- `PROPSYS!StgDeserializePropVariant` at `0x18004c5d3`
- `PROPSYS!StgDeserializePropVariant` at `0x18004c5d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c2d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c372`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c413`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c4f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c61d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c6a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c733`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c2d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c372`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c413`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c4f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c61d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c6a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c733`

## pseudocode

```c
__int64 __fastcall CWMProperty::SetNativeValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 ulVal; // rdx
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  struct _GUID v33; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID v34; // [rsp+40h] [rbp-48h] BYREF
  char v35; // [rsp+90h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v35, "CWMProperty::SetNativeValue", 145);
  v5 = PropVariantClear(this + 4);
  if ( v5 >= 0 )
  {
    v5 = PropVariantClear(this + 5);
    if ( v5 >= 0 )
    {
      v5 = PropVariantCopy(this + 5, a2);
      if ( v5 >= 0 )
      {
        if ( (a2->vt & 0xEFFF) == 8
          || (a2->vt & 0xEFFF) == 0xB
          || (a2->vt & 0xEFFF) == 0x12
          || (a2->vt & 0xEFFF) == 0x13
          || (a2->vt & 0xEFFF) == 0x15
          || (a2->vt & 0xEFFF) == 0x1F
          || (a2->vt & 0xEFFF) == 0x41
          || (a2->vt & 0xEFFF) == 0x48 )
        {
          v33 = (struct _GUID)MF_MD_SHELLMULTI;
          v34 = (struct _GUID)MF_MD_SHELLTYPE;
          v5 = CWMProperty::TranslateValue((CWMProperty *)this, this + 5, this + 4, &v34, &v33);
          if ( v5 < 0 )
          {
            if ( a2->vt == 65 && (ulVal = a2->ulVal, (_DWORD)ulVal) )
            {
              if ( (unsigned int)ulVal < 8
                || (v5 = StgDeserializePropVariant(
                           (const SERIALIZEDPROPERTYVALUE *)a2->bstrblobVal.pData,
                           ulVal,
                           this + 4),
                    v5 < 0) )
              {
                if ( v5 == -2147024882 || v5 == -2147287035 )
                {
                  v26 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, ulVal);
                    CallStackTracing::s_wpInstance = v27;
                    if ( v27
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
                    {
                      v26 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v26 = &qword_180069A90;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                    }
                  }
                  if ( *((_BYTE *)v26 + 8) )
                  {
                    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
                    if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                      CallStackContext::TraceFailure(ThreadRelativeContext, "CWMProperty::SetNativeValue", 177, v5);
                  }
                  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  {
                    v9 = 21;
                    goto LABEL_90;
                  }
                }
                else
                {
                  v5 = PropVariantCopy(this + 4, a2);
                  if ( v5 < 0 )
                  {
                    v23 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
                      CallStackTracing::s_wpInstance = v24;
                      if ( v24
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(
                             v24,
                             2032) )
                      {
                        v23 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v23 = &qword_180069A90;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                      }
                    }
                    if ( *((_BYTE *)v23 + 8) )
                    {
                      v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
                      if ( *((_DWORD *)v25 + 499) != v5 )
                        CallStackContext::TraceFailure(v25, "CWMProperty::SetNativeValue", 175, v5);
                    }
                    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    {
                      v9 = 20;
                      goto LABEL_90;
                    }
                  }
                }
              }
            }
            else
            {
              v29 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, ulVal);
                CallStackTracing::s_wpInstance = v30;
                if ( v30
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
                {
                  v29 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v29 = &qword_180069A90;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                }
              }
              if ( *((_BYTE *)v29 + 8) )
              {
                v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
                if ( *((_DWORD *)v31 + 499) != v5 )
                  CallStackContext::TraceFailure(v31, "CWMProperty::SetNativeValue", 181, v5);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v9 = 22;
                goto LABEL_90;
              }
            }
          }
        }
        else
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
          v5 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
            CallStackTracing::s_wpInstance = v19;
            if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
            {
              v18 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v18 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v18 + 8) )
          {
            v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
            if ( *((_DWORD *)v20 + 499) != -2147418113 )
              CallStackContext::TraceFailure(v20, "CWMProperty::SetNativeValue", 189, -2147418113);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 23;
            goto LABEL_90;
          }
        }
      }
      else
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)v17 + 499) != v5 )
            CallStackContext::TraceFailure(v17, "CWMProperty::SetNativeValue", 148, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 19;
          goto LABEL_90;
        }
      }
    }
    else
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != v5 )
          CallStackContext::TraceFailure(v13, "CWMProperty::SetNativeValue", 146, v5);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 18;
        goto LABEL_90;
      }
    }
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v8 + 499) != v5 )
        CallStackContext::TraceFailure(v8, "CWMProperty::SetNativeValue", 145, v5);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 17;
LABEL_90:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v35);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004c280  mov     rax, rsp
0x18004c283  push    rbx
0x18004c284  push    rbp
0x18004c285  push    rsi
0x18004c286  push    rdi
0x18004c287  push    r12
0x18004c289  push    r14
0x18004c28b  sub     rsp, 58h
0x18004c28f  mov     rdi, rdx
0x18004c292  lea     r12, aCwmpropertySet; "CWMProperty::SetNativeValue"
0x18004c299  mov     rsi, rcx
0x18004c29c  mov     ebp, 91h
0x18004c2a1  mov     r8d, ebp; int
0x18004c2a4  lea     rcx, [rax+8]; this
0x18004c2a8  mov     rdx, r12; char *
0x18004c2ab  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004c2b0  lea     r14, [rsi+60h]
0x18004c2b4  mov     rcx, r14; pvar
0x18004c2b7  call    cs:__imp_PropVariantClear
0x18004c2bd  mov     ebx, eax
0x18004c2bf  test    eax, eax
0x18004c2c1  jns     loc_18004C34F
0x18004c2c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c2ce  test    rcx, rcx
0x18004c2d1  jnz     short loc_18004C314
0x18004c2d3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c2d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c2e0  mov     rcx, rax
0x18004c2e3  test    rax, rax
0x18004c2e6  jz      short loc_18004C306
0x18004c2e8  mov     rax, [rax]
0x18004c2eb  mov     edx, 7F0h
0x18004c2f0  mov     rax, [rax+8]
0x18004c2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2f9  test    eax, eax
0x18004c2fb  jz      short loc_18004C306
0x18004c2fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c304  jmp     short loc_18004C314
0x18004c306  lea     rcx, qword_180069A90; this
0x18004c30d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c314  cmp     byte ptr [rcx+8], 0
0x18004c318  jz      short loc_18004C338
0x18004c31a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c31f  cmp     [rax+7CCh], ebx
0x18004c325  jz      short loc_18004C338
0x18004c327  mov     r9d, ebx; int
0x18004c32a  mov     r8d, ebp; int
0x18004c32d  mov     rdx, r12; char *
0x18004c330  mov     rcx, rax; this
0x18004c333  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c338  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004c33d  cmp     al, 1
0x18004c33f  jb      loc_18004C7C7
0x18004c345  mov     edx, 11h
0x18004c34a  jmp     loc_18004C7A9
0x18004c34f  lea     rbp, [rsi+78h]
0x18004c353  mov     rcx, rbp; pvar
0x18004c356  call    cs:__imp_PropVariantClear
0x18004c35c  mov     ebx, eax
0x18004c35e  test    eax, eax
0x18004c360  jns     loc_18004C3F1
0x18004c366  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c36d  test    rcx, rcx
0x18004c370  jnz     short loc_18004C3B3
0x18004c372  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c378  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c37f  mov     rcx, rax
0x18004c382  test    rax, rax
0x18004c385  jz      short loc_18004C3A5
0x18004c387  mov     rax, [rax]
0x18004c38a  mov     edx, 7F0h
0x18004c38f  mov     rax, [rax+8]
0x18004c393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c398  test    eax, eax
0x18004c39a  jz      short loc_18004C3A5
0x18004c39c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c3a3  jmp     short loc_18004C3B3
0x18004c3a5  lea     rcx, qword_180069A90; this
0x18004c3ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c3b3  cmp     byte ptr [rcx+8], 0
0x18004c3b7  jz      short loc_18004C3DA
0x18004c3b9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c3be  cmp     [rax+7CCh], ebx
0x18004c3c4  jz      short loc_18004C3DA
0x18004c3c6  mov     r9d, ebx; int
0x18004c3c9  mov     r8d, 92h; int
0x18004c3cf  mov     rdx, r12; char *
0x18004c3d2  mov     rcx, rax; this
0x18004c3d5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c3da  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004c3df  cmp     al, 1
0x18004c3e1  jb      loc_18004C7C7
0x18004c3e7  mov     edx, 12h
0x18004c3ec  jmp     loc_18004C7A9
0x18004c3f1  mov     rdx, rdi; pvarSrc
0x18004c3f4  mov     rcx, rbp; pvarDest
0x18004c3f7  call    cs:__imp_PropVariantCopy
0x18004c3fd  mov     ebx, eax
0x18004c3ff  test    eax, eax
0x18004c401  jns     loc_18004C492
0x18004c407  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c40e  test    rcx, rcx
0x18004c411  jnz     short loc_18004C454
0x18004c413  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c419  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c420  mov     rcx, rax
0x18004c423  test    rax, rax
0x18004c426  jz      short loc_18004C446
0x18004c428  mov     rax, [rax]
0x18004c42b  mov     edx, 7F0h
0x18004c430  mov     rax, [rax+8]
0x18004c434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c439  test    eax, eax
0x18004c43b  jz      short loc_18004C446
0x18004c43d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c444  jmp     short loc_18004C454
0x18004c446  lea     rcx, qword_180069A90; this
0x18004c44d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c454  cmp     byte ptr [rcx+8], 0
0x18004c458  jz      short loc_18004C47B
0x18004c45a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c45f  cmp     [rax+7CCh], ebx
0x18004c465  jz      short loc_18004C47B
0x18004c467  mov     r9d, ebx; int
0x18004c46a  mov     r8d, 94h; int
0x18004c470  mov     rdx, r12; char *
0x18004c473  mov     rcx, rax; this
0x18004c476  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c47b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004c480  cmp     al, 1
0x18004c482  jb      loc_18004C7C7
0x18004c488  mov     edx, 13h
0x18004c48d  jmp     loc_18004C7A9
0x18004c492  movzx   ecx, word ptr [rdi]
0x18004c495  btr     ecx, 0Ch
0x18004c499  sub     ecx, 8
0x18004c49c  jz      loc_18004C571
0x18004c4a2  sub     ecx, 3
0x18004c4a5  jz      loc_18004C571
0x18004c4ab  sub     ecx, 7
0x18004c4ae  jz      loc_18004C571
0x18004c4b4  sub     ecx, 1
0x18004c4b7  jz      loc_18004C571
0x18004c4bd  sub     ecx, 2
0x18004c4c0  jz      loc_18004C571
0x18004c4c6  sub     ecx, 0Ah
0x18004c4c9  jz      loc_18004C571
0x18004c4cf  sub     ecx, 22h ; '"'
0x18004c4d2  jz      loc_18004C571
0x18004c4d8  cmp     ecx, 7
0x18004c4db  jz      loc_18004C571
0x18004c4e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c4e8  mov     ebx, 8000FFFFh
0x18004c4ed  test    rcx, rcx
0x18004c4f0  jnz     short loc_18004C533
0x18004c4f2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c4f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c4ff  mov     rcx, rax
0x18004c502  test    rax, rax
0x18004c505  jz      short loc_18004C525
0x18004c507  mov     rax, [rax]
0x18004c50a  mov     edx, 7F0h
0x18004c50f  mov     rax, [rax+8]
0x18004c513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c518  test    eax, eax
0x18004c51a  jz      short loc_18004C525
0x18004c51c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c523  jmp     short loc_18004C533
0x18004c525  lea     rcx, qword_180069A90; this
0x18004c52c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c533  cmp     byte ptr [rcx+8], 0
0x18004c537  jz      short loc_18004C55A
0x18004c539  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c53e  cmp     [rax+7CCh], ebx
0x18004c544  jz      short loc_18004C55A
0x18004c546  mov     r9d, ebx; int
0x18004c549  mov     r8d, 0BDh; int
0x18004c54f  mov     rdx, r12; char *
0x18004c552  mov     rcx, rax; this
0x18004c555  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c55a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004c55f  cmp     al, 1
0x18004c561  jb      loc_18004C7C7
0x18004c567  mov     edx, 17h
0x18004c56c  jmp     loc_18004C7A9
0x18004c571  movups  xmm0, cs:MF_MD_SHELLMULTI
0x18004c578  lea     rax, [rsp+88h+var_58]
0x18004c57d  mov     r8, r14; struct tagPROPVARIANT *
0x18004c580  movups  xmm1, cs:MF_MD_SHELLTYPE
0x18004c587  lea     r9, [rsp+88h+var_48]; struct _GUID
0x18004c58c  mov     [rsp+88h+var_68], rax; struct _GUID
0x18004c591  mov     rdx, rbp; struct tagPROPVARIANT *
0x18004c594  mov     rcx, rsi; this
0x18004c597  movdqu  xmmword ptr [rsp+88h+var_58.Data1], xmm0
0x18004c59d  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm1
0x18004c5a3  call    ?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z; CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)
0x18004c5a8  mov     ebx, eax
0x18004c5aa  test    eax, eax
0x18004c5ac  jns     loc_18004C7C7
0x18004c5b2  cmp     word ptr [rdi], 41h ; 'A'
0x18004c5b6  jnz     loc_18004C727
0x18004c5bc  mov     edx, [rdi+8]; cbMax
0x18004c5bf  test    edx, edx
0x18004c5c1  jz      loc_18004C727
0x18004c5c7  cmp     edx, 8
0x18004c5ca  jb      short loc_18004C5E3
0x18004c5cc  mov     rcx, [rdi+10h]; pprop
0x18004c5d0  mov     r8, r14; ppropvar
0x18004c5d3  call    cs:__imp_StgDeserializePropVariant
0x18004c5d9  mov     ebx, eax
0x18004c5db  test    eax, eax
0x18004c5dd  jns     loc_18004C7C7
0x18004c5e3  cmp     ebx, 8007000Eh
0x18004c5e9  jz      loc_18004C69C
0x18004c5ef  cmp     ebx, 80030005h
0x18004c5f5  jz      loc_18004C69C
0x18004c5fb  mov     rdx, rdi; pvarSrc
0x18004c5fe  mov     rcx, r14; pvarDest
0x18004c601  call    cs:__imp_PropVariantCopy
0x18004c607  mov     ebx, eax
0x18004c609  test    eax, eax
0x18004c60b  jns     loc_18004C7C7
0x18004c611  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c618  test    rcx, rcx
0x18004c61b  jnz     short loc_18004C65E
0x18004c61d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c623  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c62a  mov     rcx, rax
0x18004c62d  test    rax, rax
0x18004c630  jz      short loc_18004C650
0x18004c632  mov     rax, [rax]
0x18004c635  mov     edx, 7F0h
0x18004c63a  mov     rax, [rax+8]
0x18004c63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c643  test    eax, eax
0x18004c645  jz      short loc_18004C650
0x18004c647  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c64e  jmp     short loc_18004C65E
0x18004c650  lea     rcx, qword_180069A90; this
0x18004c657  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c65e  cmp     byte ptr [rcx+8], 0
0x18004c662  jz      short loc_18004C685
0x18004c664  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c669  cmp     [rax+7CCh], ebx
0x18004c66f  jz      short loc_18004C685
0x18004c671  mov     r9d, ebx; int
0x18004c674  mov     r8d, 0AFh; int
0x18004c67a  mov     rdx, r12; char *
0x18004c67d  mov     rcx, rax; this
0x18004c680  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c685  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004c68a  cmp     al, 1
0x18004c68c  jb      loc_18004C7C7
0x18004c692  mov     edx, 14h
0x18004c697  jmp     loc_18004C7A9
0x18004c69c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c6a3  test    rcx, rcx
0x18004c6a6  jnz     short loc_18004C6E9
0x18004c6a8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c6ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c6b5  mov     rcx, rax
0x18004c6b8  test    rax, rax
0x18004c6bb  jz      short loc_18004C6DB
0x18004c6bd  mov     rax, [rax]
0x18004c6c0  mov     edx, 7F0h
0x18004c6c5  mov     rax, [rax+8]
0x18004c6c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c6ce  test    eax, eax
0x18004c6d0  jz      short loc_18004C6DB
0x18004c6d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c6d9  jmp     short loc_18004C6E9
0x18004c6db  lea     rcx, qword_180069A90; this
0x18004c6e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c6e9  cmp     byte ptr [rcx+8], 0
0x18004c6ed  jz      short loc_18004C710
0x18004c6ef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c6f4  cmp     [rax+7CCh], ebx
0x18004c6fa  jz      short loc_18004C710
0x18004c6fc  mov     r9d, ebx; int
0x18004c6ff  mov     r8d, 0B1h; int
0x18004c705  mov     rdx, r12; char *
0x18004c708  mov     rcx, rax; this
0x18004c70b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c710  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004c715  cmp     al, 1
0x18004c717  jb      loc_18004C7C7
0x18004c71d  mov     edx, 15h
0x18004c722  jmp     loc_18004C7A9
0x18004c727  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c72e  test    rcx, rcx
0x18004c731  jnz     short loc_18004C774
0x18004c733  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c739  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c740  mov     rcx, rax
0x18004c743  test    rax, rax
0x18004c746  jz      short loc_18004C766
0x18004c748  mov     rax, [rax]
0x18004c74b  mov     edx, 7F0h
0x18004c750  mov     rax, [rax+8]
0x18004c754  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
