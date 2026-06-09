# CWMProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x1802da0b0`
- end: `0x1802da663`
- name: `?SetNativeValue@CWMProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1459`
- prototype: `__int64 __fastcall(CWMProperty *__hidden this, PROPVARIANT *pvarSrc)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18019c810`
- `0x180206f70`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x1802467d4`
- `0x1802da0b0`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1802da241`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1802da465`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1802da241`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1802da465`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1802da0e7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1802da193`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1802da0e7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1802da193`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da109`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da1b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da263`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da349`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da487`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da519`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da5ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da109`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da1b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da263`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da349`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da487`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da519`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da5ab`
- `PROPSYS!StgDeserializePropVariant` at `0x1802da431`
- `PROPSYS!StgDeserializePropVariant` at `0x1802da431`

## pseudocode

```c
__int64 __fastcall CWMProperty::SetNativeValue(PROPVARIANT *this, PROPVARIANT *pvarSrc)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  __int64 v6; // r8
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  struct _GUID v38; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID v39; // [rsp+40h] [rbp-48h] BYREF
  char v40; // [rsp+90h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v40, "CWMProperty::SetNativeValue", 145);
  v5 = PropVariantClear(this + 12);
  if ( v5 >= 0 )
  {
    v5 = PropVariantClear(this + 15);
    if ( v5 >= 0 )
    {
      v5 = PropVariantCopy(this + 15, pvarSrc);
      if ( v5 >= 0 )
      {
        if ( (*(_WORD *)pvarSrc & 0xEFFF) == 8
          || (*(_WORD *)pvarSrc & 0xEFFF) == 0xB
          || (*(_WORD *)pvarSrc & 0xEFFF) == 0x12
          || (*(_WORD *)pvarSrc & 0xEFFF) == 0x13
          || (*(_WORD *)pvarSrc & 0xEFFF) == 0x15
          || (*(_WORD *)pvarSrc & 0xEFFF) == 0x1F
          || (*(_WORD *)pvarSrc & 0xEFFF) == 0x41
          || (*(_WORD *)pvarSrc & 0xEFFF) == 0x48 )
        {
          v38 = (struct _GUID)MF_MD_SHELLMULTI;
          v39 = (struct _GUID)MF_MD_SHELLTYPE;
          v5 = CWMProperty::TranslateValue(
                 (CWMProperty *)this,
                 (const struct tagPROPVARIANT *)this + 5,
                 (struct tagPROPVARIANT *)this + 4,
                 &v39,
                 &v38);
          if ( v5 < 0 )
          {
            if ( *(_WORD *)pvarSrc == 65 && (v24 = *((unsigned int *)pvarSrc + 2), (_DWORD)v24) )
            {
              if ( (unsigned int)v24 < 8
                || (v5 = StgDeserializePropVariant((const SERIALIZEDPROPERTYVALUE *)pvarSrc[2], v24, this + 12), v5 < 0) )
              {
                if ( v5 == -2147024882 || v5 == -2147287035 )
                {
                  v31 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25);
                    CallStackTracing::s_wpInstance = v32;
                    if ( v32
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
                    {
                      v31 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v31 = &qword_1803CE250;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v31 + 8) )
                  {
                    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
                    if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                      CallStackContext::TraceFailure(ThreadRelativeContext, "CWMProperty::SetNativeValue", 177, v5);
                  }
                  if ( g_wppLevels )
                  {
                    v10 = 21;
                    goto LABEL_90;
                  }
                }
                else
                {
                  v5 = PropVariantCopy(this + 12, pvarSrc);
                  if ( v5 < 0 )
                  {
                    v28 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27);
                      CallStackTracing::s_wpInstance = v29;
                      if ( v29
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(
                             v29,
                             2032) )
                      {
                        v28 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v28 = &qword_1803CE250;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                      }
                    }
                    if ( *((_BYTE *)v28 + 8) )
                    {
                      v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
                      if ( *((_DWORD *)v30 + 499) != v5 )
                        CallStackContext::TraceFailure(v30, "CWMProperty::SetNativeValue", 175, v5);
                    }
                    if ( g_wppLevels )
                    {
                      v10 = 20;
                      goto LABEL_90;
                    }
                  }
                }
              }
            }
            else
            {
              v34 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25);
                CallStackTracing::s_wpInstance = v35;
                if ( v35
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
                {
                  v34 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v34 = &qword_1803CE250;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v34 + 8) )
              {
                v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
                if ( *((_DWORD *)v36 + 499) != v5 )
                  CallStackContext::TraceFailure(v36, "CWMProperty::SetNativeValue", 181, v5);
              }
              if ( g_wppLevels )
              {
                v10 = 22;
                goto LABEL_90;
              }
            }
          }
        }
        else
        {
          v21 = (__int64 *)CallStackTracing::s_wpInstance;
          v5 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17);
            CallStackTracing::s_wpInstance = v22;
            if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
            {
              v21 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v21 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v21 + 8) )
          {
            v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
            if ( *((_DWORD *)v23 + 499) != -2147418113 )
              CallStackContext::TraceFailure(v23, "CWMProperty::SetNativeValue", 189, -2147418113);
          }
          if ( g_wppLevels )
          {
            v10 = 23;
            goto LABEL_90;
          }
        }
      }
      else
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17);
          CallStackTracing::s_wpInstance = v19;
          if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
          {
            v18 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v18 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)v20 + 499) != v5 )
            CallStackContext::TraceFailure(v20, "CWMProperty::SetNativeValue", 148, v5);
        }
        if ( g_wppLevels )
        {
          v10 = 19;
          goto LABEL_90;
        }
      }
    }
    else
    {
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12);
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
        if ( *((_DWORD *)v15 + 499) != v5 )
          CallStackContext::TraceFailure(v15, "CWMProperty::SetNativeValue", 146, v5);
      }
      if ( g_wppLevels )
      {
        v10 = 18;
        goto LABEL_90;
      }
    }
  }
  else
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v9 + 499) != v5 )
        CallStackContext::TraceFailure(v9, "CWMProperty::SetNativeValue", 145, v5);
    }
    if ( g_wppLevels )
    {
      v10 = 17;
LABEL_90:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v40);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1802da0b0  mov     rax, rsp
0x1802da0b3  push    rbx
0x1802da0b4  push    rbp
0x1802da0b5  push    rsi
0x1802da0b6  push    rdi
0x1802da0b7  push    r12
0x1802da0b9  push    r14
0x1802da0bb  sub     rsp, 58h
0x1802da0bf  mov     rdi, rdx
0x1802da0c2  lea     r12, aCwmpropertySet; "CWMProperty::SetNativeValue"
0x1802da0c9  mov     rsi, rcx
0x1802da0cc  mov     ebp, 91h
0x1802da0d1  mov     r8d, ebp; int
0x1802da0d4  lea     rcx, [rax+8]; this
0x1802da0d8  mov     rdx, r12; char *
0x1802da0db  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1802da0e0  lea     r14, [rsi+60h]
0x1802da0e4  mov     rcx, r14; pvar
0x1802da0e7  call    cs:__imp_PropVariantClear
0x1802da0ee  nop     dword ptr [rax+rax+00h]
0x1802da0f3  mov     ebx, eax
0x1802da0f5  test    eax, eax
0x1802da0f7  jns     loc_1802DA18C
0x1802da0fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da104  test    rcx, rcx
0x1802da107  jnz     short loc_1802DA151
0x1802da109  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802da110  nop     dword ptr [rax+rax+00h]
0x1802da115  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da11c  mov     rcx, rax
0x1802da11f  test    rax, rax
0x1802da122  jz      short loc_1802DA143
0x1802da124  mov     rax, [rax]
0x1802da127  mov     edx, 7F0h
0x1802da12c  mov     rax, [rax+8]
0x1802da130  call    cs:__guard_dispatch_icall_fptr
0x1802da136  test    eax, eax
0x1802da138  jz      short loc_1802DA143
0x1802da13a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da141  jmp     short loc_1802DA151
0x1802da143  lea     rcx, qword_1803CE250; this
0x1802da14a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da151  cmp     byte ptr [rcx+8], 0
0x1802da155  jz      short loc_1802DA175
0x1802da157  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802da15c  cmp     [rax+7CCh], ebx
0x1802da162  jz      short loc_1802DA175
0x1802da164  mov     r9d, ebx; int
0x1802da167  mov     r8d, ebp; int
0x1802da16a  mov     rdx, r12; char *
0x1802da16d  mov     rcx, rax; this
0x1802da170  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802da175  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802da17c  jb      loc_1802DA646
0x1802da182  mov     edx, 11h
0x1802da187  jmp     loc_1802DA628
0x1802da18c  lea     rbp, [rsi+78h]
0x1802da190  mov     rcx, rbp; pvar
0x1802da193  call    cs:__imp_PropVariantClear
0x1802da19a  nop     dword ptr [rax+rax+00h]
0x1802da19f  mov     ebx, eax
0x1802da1a1  test    eax, eax
0x1802da1a3  jns     loc_1802DA23B
0x1802da1a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da1b0  test    rcx, rcx
0x1802da1b3  jnz     short loc_1802DA1FD
0x1802da1b5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802da1bc  nop     dword ptr [rax+rax+00h]
0x1802da1c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da1c8  mov     rcx, rax
0x1802da1cb  test    rax, rax
0x1802da1ce  jz      short loc_1802DA1EF
0x1802da1d0  mov     rax, [rax]
0x1802da1d3  mov     edx, 7F0h
0x1802da1d8  mov     rax, [rax+8]
0x1802da1dc  call    cs:__guard_dispatch_icall_fptr
0x1802da1e2  test    eax, eax
0x1802da1e4  jz      short loc_1802DA1EF
0x1802da1e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da1ed  jmp     short loc_1802DA1FD
0x1802da1ef  lea     rcx, qword_1803CE250; this
0x1802da1f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da1fd  cmp     byte ptr [rcx+8], 0
0x1802da201  jz      short loc_1802DA224
0x1802da203  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802da208  cmp     [rax+7CCh], ebx
0x1802da20e  jz      short loc_1802DA224
0x1802da210  mov     r9d, ebx; int
0x1802da213  mov     r8d, 92h; int
0x1802da219  mov     rdx, r12; char *
0x1802da21c  mov     rcx, rax; this
0x1802da21f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802da224  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802da22b  jb      loc_1802DA646
0x1802da231  mov     edx, 12h
0x1802da236  jmp     loc_1802DA628
0x1802da23b  mov     rdx, rdi; pvarSrc
0x1802da23e  mov     rcx, rbp; pvarDest
0x1802da241  call    cs:__imp_PropVariantCopy
0x1802da248  nop     dword ptr [rax+rax+00h]
0x1802da24d  mov     ebx, eax
0x1802da24f  test    eax, eax
0x1802da251  jns     loc_1802DA2E9
0x1802da257  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da25e  test    rcx, rcx
0x1802da261  jnz     short loc_1802DA2AB
0x1802da263  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802da26a  nop     dword ptr [rax+rax+00h]
0x1802da26f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da276  mov     rcx, rax
0x1802da279  test    rax, rax
0x1802da27c  jz      short loc_1802DA29D
0x1802da27e  mov     rax, [rax]
0x1802da281  mov     edx, 7F0h
0x1802da286  mov     rax, [rax+8]
0x1802da28a  call    cs:__guard_dispatch_icall_fptr
0x1802da290  test    eax, eax
0x1802da292  jz      short loc_1802DA29D
0x1802da294  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da29b  jmp     short loc_1802DA2AB
0x1802da29d  lea     rcx, qword_1803CE250; this
0x1802da2a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da2ab  cmp     byte ptr [rcx+8], 0
0x1802da2af  jz      short loc_1802DA2D2
0x1802da2b1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802da2b6  cmp     [rax+7CCh], ebx
0x1802da2bc  jz      short loc_1802DA2D2
0x1802da2be  mov     r9d, ebx; int
0x1802da2c1  mov     r8d, 94h; int
0x1802da2c7  mov     rdx, r12; char *
0x1802da2ca  mov     rcx, rax; this
0x1802da2cd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802da2d2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802da2d9  jb      loc_1802DA646
0x1802da2df  mov     edx, 13h
0x1802da2e4  jmp     loc_1802DA628
0x1802da2e9  movzx   ecx, word ptr [rdi]
0x1802da2ec  btr     ecx, 0Ch
0x1802da2f0  sub     ecx, 8
0x1802da2f3  jz      loc_1802DA3CF
0x1802da2f9  sub     ecx, 3
0x1802da2fc  jz      loc_1802DA3CF
0x1802da302  sub     ecx, 7
0x1802da305  jz      loc_1802DA3CF
0x1802da30b  sub     ecx, 1
0x1802da30e  jz      loc_1802DA3CF
0x1802da314  sub     ecx, 2
0x1802da317  jz      loc_1802DA3CF
0x1802da31d  sub     ecx, 0Ah
0x1802da320  jz      loc_1802DA3CF
0x1802da326  sub     ecx, 22h ; '"'
0x1802da329  jz      loc_1802DA3CF
0x1802da32f  cmp     ecx, 7
0x1802da332  jz      loc_1802DA3CF
0x1802da338  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da33f  mov     ebx, 8000FFFFh
0x1802da344  test    rcx, rcx
0x1802da347  jnz     short loc_1802DA391
0x1802da349  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802da350  nop     dword ptr [rax+rax+00h]
0x1802da355  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da35c  mov     rcx, rax
0x1802da35f  test    rax, rax
0x1802da362  jz      short loc_1802DA383
0x1802da364  mov     rax, [rax]
0x1802da367  mov     edx, 7F0h
0x1802da36c  mov     rax, [rax+8]
0x1802da370  call    cs:__guard_dispatch_icall_fptr
0x1802da376  test    eax, eax
0x1802da378  jz      short loc_1802DA383
0x1802da37a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da381  jmp     short loc_1802DA391
0x1802da383  lea     rcx, qword_1803CE250; this
0x1802da38a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da391  cmp     byte ptr [rcx+8], 0
0x1802da395  jz      short loc_1802DA3B8
0x1802da397  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802da39c  cmp     [rax+7CCh], ebx
0x1802da3a2  jz      short loc_1802DA3B8
0x1802da3a4  mov     r9d, ebx; int
0x1802da3a7  mov     r8d, 0BDh; int
0x1802da3ad  mov     rdx, r12; char *
0x1802da3b0  mov     rcx, rax; this
0x1802da3b3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802da3b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802da3bf  jb      loc_1802DA646
0x1802da3c5  mov     edx, 17h
0x1802da3ca  jmp     loc_1802DA628
0x1802da3cf  movups  xmm0, cs:MF_MD_SHELLMULTI
0x1802da3d6  lea     rax, [rsp+88h+var_58]
0x1802da3db  mov     r8, r14; struct tagPROPVARIANT *
0x1802da3de  movups  xmm1, cs:MF_MD_SHELLTYPE
0x1802da3e5  lea     r9, [rsp+88h+var_48]; struct _GUID
0x1802da3ea  mov     [rsp+88h+var_68], rax; struct _GUID
0x1802da3ef  mov     rdx, rbp; struct tagPROPVARIANT *
0x1802da3f2  mov     rcx, rsi; this
0x1802da3f5  movdqu  xmmword ptr [rsp+88h+var_58.Data1], xmm0
0x1802da3fb  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm1
0x1802da401  call    ?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z; CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)
0x1802da406  mov     ebx, eax
0x1802da408  test    eax, eax
0x1802da40a  jns     loc_1802DA646
0x1802da410  cmp     word ptr [rdi], 41h ; 'A'
0x1802da414  jnz     loc_1802DA59F
0x1802da41a  mov     edx, [rdi+8]; cbMax
0x1802da41d  test    edx, edx
0x1802da41f  jz      loc_1802DA59F
0x1802da425  cmp     edx, 8
0x1802da428  jb      short loc_1802DA447
0x1802da42a  mov     rcx, [rdi+10h]; pprop
0x1802da42e  mov     r8, r14; ppropvar
0x1802da431  call    cs:__imp_StgDeserializePropVariant
0x1802da438  nop     dword ptr [rax+rax+00h]
0x1802da43d  mov     ebx, eax
0x1802da43f  test    eax, eax
0x1802da441  jns     loc_1802DA646
0x1802da447  cmp     ebx, 8007000Eh
0x1802da44d  jz      loc_1802DA50D
0x1802da453  cmp     ebx, 80030005h
0x1802da459  jz      loc_1802DA50D
0x1802da45f  mov     rdx, rdi; pvarSrc
0x1802da462  mov     rcx, r14; pvarDest
0x1802da465  call    cs:__imp_PropVariantCopy
0x1802da46c  nop     dword ptr [rax+rax+00h]
0x1802da471  mov     ebx, eax
0x1802da473  test    eax, eax
0x1802da475  jns     loc_1802DA646
0x1802da47b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da482  test    rcx, rcx
0x1802da485  jnz     short loc_1802DA4CF
0x1802da487  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802da48e  nop     dword ptr [rax+rax+00h]
0x1802da493  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da49a  mov     rcx, rax
0x1802da49d  test    rax, rax
0x1802da4a0  jz      short loc_1802DA4C1
0x1802da4a2  mov     rax, [rax]
0x1802da4a5  mov     edx, 7F0h
0x1802da4aa  mov     rax, [rax+8]
0x1802da4ae  call    cs:__guard_dispatch_icall_fptr
0x1802da4b4  test    eax, eax
0x1802da4b6  jz      short loc_1802DA4C1
0x1802da4b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da4bf  jmp     short loc_1802DA4CF
0x1802da4c1  lea     rcx, qword_1803CE250; this
0x1802da4c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da4cf  cmp     byte ptr [rcx+8], 0
0x1802da4d3  jz      short loc_1802DA4F6
0x1802da4d5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802da4da  cmp     [rax+7CCh], ebx
0x1802da4e0  jz      short loc_1802DA4F6
0x1802da4e2  mov     r9d, ebx; int
0x1802da4e5  mov     r8d, 0AFh; int
0x1802da4eb  mov     rdx, r12; char *
0x1802da4ee  mov     rcx, rax; this
0x1802da4f1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802da4f6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802da4fd  jb      loc_1802DA646
0x1802da503  mov     edx, 14h
0x1802da508  jmp     loc_1802DA628
0x1802da50d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da514  test    rcx, rcx
0x1802da517  jnz     short loc_1802DA561
0x1802da519  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802da520  nop     dword ptr [rax+rax+00h]
0x1802da525  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da52c  mov     rcx, rax
0x1802da52f  test    rax, rax
0x1802da532  jz      short loc_1802DA553
0x1802da534  mov     rax, [rax]
0x1802da537  mov     edx, 7F0h
0x1802da53c  mov     rax, [rax+8]
0x1802da540  call    cs:__guard_dispatch_icall_fptr
0x1802da546  test    eax, eax
0x1802da548  jz      short loc_1802DA553
0x1802da54a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da551  jmp     short loc_1802DA561
0x1802da553  lea     rcx, qword_1803CE250; this
0x1802da55a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da561  cmp     byte ptr [rcx+8], 0
0x1802da565  jz      short loc_1802DA588
0x1802da567  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802da56c  cmp     [rax+7CCh], ebx
0x1802da572  jz      short loc_1802DA588
0x1802da574  mov     r9d, ebx; int
0x1802da577  mov     r8d, 0B1h; int
0x1802da57d  mov     rdx, r12; char *
0x1802da580  mov     rcx, rax; this
0x1802da583  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802da588  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802da58f  jb      loc_1802DA646
0x1802da595  mov     edx, 15h
0x1802da59a  jmp     loc_1802DA628
0x1802da59f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da5a6  test    rcx, rcx
0x1802da5a9  jnz     short loc_1802DA5F3
0x1802da5ab  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802da5b2  nop     dword ptr [rax+rax+00h]
0x1802da5b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da5be  mov     rcx, rax
  ... truncated ...
```
