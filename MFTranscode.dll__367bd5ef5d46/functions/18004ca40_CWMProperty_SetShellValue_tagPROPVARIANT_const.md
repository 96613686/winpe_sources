# CWMProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x18004ca40`
- end: `0x18004cf85`
- name: `?SetShellValue@CWMProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1349`
- prototype: `int(CWMProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180016720`
- `0x18004cf90`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800153ac`
- `0x18001a330`
- `0x18001c280`
- `0x18004ca40`
- `0x18004d62c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ca77`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004cb16`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ca77`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004cb16`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004cbb7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004cded`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004cbb7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004cded`
- `PROPSYS!StgSerializePropVariant` at `0x18004cc7c`
- `PROPSYS!StgSerializePropVariant` at `0x18004cc7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ca93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cb32`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cbd3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cc98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cd56`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ce09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ced5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ca93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cb32`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cbd3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cc98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cd56`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ce09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ced5`

## pseudocode

```c
__int64 __fastcall CWMProperty::SetShellValue(CWMProperty *this, const struct tagPROPVARIANT *a2)
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
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  struct _GUID v36; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID v37; // [rsp+40h] [rbp-48h] BYREF
  int v38; // [rsp+90h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CWMProperty::SetShellValue", 89);
  v5 = PropVariantClear((PROPVARIANT *)this + 4);
  if ( v5 >= 0 )
  {
    v5 = PropVariantClear((PROPVARIANT *)this + 5);
    if ( v5 >= 0 )
    {
      v5 = PropVariantCopy((PROPVARIANT *)this + 4, a2);
      if ( v5 >= 0 )
      {
        if ( (unsigned int)MFGetAttributeUINT32(this, MF_MD_EXTENDEDPROP, 0) )
        {
          *((_WORD *)this + 60) = 65;
          v5 = StgSerializePropVariant(a2, (SERIALIZEDPROPERTYVALUE **)this + 17, (ULONG *)this + 32);
          if ( v5 < 0 )
          {
            v19 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
              CallStackTracing::s_wpInstance = v20;
              if ( v20
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
              {
                v19 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v19 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v19 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMProperty::SetShellValue", 108, v5);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v9 = 13;
              goto LABEL_80;
            }
          }
        }
        else
        {
          v22 = *(_QWORD *)this;
          v38 = 0;
          v5 = (*(__int64 (__fastcall **)(CWMProperty *, __int128 *, int *))(v22 + 56))(this, &MF_MD_FSDKTYPE, &v38);
          if ( v5 >= 0 )
          {
            if ( a2->vt == (_WORD)v38 )
            {
              v5 = PropVariantCopy((PROPVARIANT *)this + 5, a2);
              if ( v5 < 0 )
              {
                v28 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
                  CallStackTracing::s_wpInstance = v29;
                  if ( v29
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
                  {
                    v28 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v28 = &qword_180069A90;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                  }
                }
                if ( *((_BYTE *)v28 + 8) )
                {
                  v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
                  if ( *((_DWORD *)v30 + 499) != v5 )
                    CallStackContext::TraceFailure(v30, "CWMProperty::SetShellValue", 127, v5);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v9 = 15;
                  goto LABEL_80;
                }
              }
            }
            else
            {
              v36 = (struct _GUID)MF_MD_FSDKMULTI;
              v37 = (struct _GUID)MF_MD_FSDKTYPE;
              v5 = CWMProperty::TranslateValue(
                     this,
                     (const struct tagPROPVARIANT *)this + 4,
                     (struct tagPROPVARIANT *)this + 5,
                     &v37,
                     &v36);
              if ( v5 < 0 )
              {
                v32 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
                  CallStackTracing::s_wpInstance = v33;
                  if ( v33
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
                  {
                    v32 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v32 = &qword_180069A90;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                  }
                }
                if ( *((_BYTE *)v32 + 8) )
                {
                  v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
                  if ( *((_DWORD *)v34 + 499) != v5 )
                    CallStackContext::TraceFailure(v34, "CWMProperty::SetShellValue", 131, v5);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v9 = 16;
                  goto LABEL_80;
                }
              }
            }
          }
          else
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
              CallStackTracing::s_wpInstance = v25;
              if ( v25
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
              {
                v24 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v24 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v24 + 8) )
            {
              v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
              if ( *((_DWORD *)v26 + 499) != v5 )
                CallStackContext::TraceFailure(v26, "CWMProperty::SetShellValue", 120, v5);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v9 = 14;
              goto LABEL_80;
            }
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
            CallStackContext::TraceFailure(v17, "CWMProperty::SetShellValue", 92, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 12;
          goto LABEL_80;
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
          CallStackContext::TraceFailure(v13, "CWMProperty::SetShellValue", 90, v5);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 11;
        goto LABEL_80;
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
        CallStackContext::TraceFailure(v8, "CWMProperty::SetShellValue", 89, v5);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 10;
LABEL_80:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004ca40  mov     rax, rsp
0x18004ca43  push    rbx
0x18004ca44  push    rbp
0x18004ca45  push    rsi
0x18004ca46  push    rdi
0x18004ca47  push    r12
0x18004ca49  push    r14
0x18004ca4b  sub     rsp, 58h
0x18004ca4f  mov     rbp, rdx
0x18004ca52  lea     r12, aCwmpropertySet_0; "CWMProperty::SetShellValue"
0x18004ca59  mov     rdi, rcx
0x18004ca5c  mov     esi, 59h ; 'Y'
0x18004ca61  mov     r8d, esi; int
0x18004ca64  lea     rcx, [rax+8]; this
0x18004ca68  mov     rdx, r12; char *
0x18004ca6b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004ca70  lea     r14, [rdi+60h]
0x18004ca74  mov     rcx, r14; pvar
0x18004ca77  call    cs:__imp_PropVariantClear
0x18004ca7d  mov     ebx, eax
0x18004ca7f  test    eax, eax
0x18004ca81  jns     loc_18004CB0F
0x18004ca87  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ca8e  test    rcx, rcx
0x18004ca91  jnz     short loc_18004CAD4
0x18004ca93  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004ca99  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004caa0  mov     rcx, rax
0x18004caa3  test    rax, rax
0x18004caa6  jz      short loc_18004CAC6
0x18004caa8  mov     rax, [rax]
0x18004caab  mov     edx, 7F0h
0x18004cab0  mov     rax, [rax+8]
0x18004cab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cab9  test    eax, eax
0x18004cabb  jz      short loc_18004CAC6
0x18004cabd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cac4  jmp     short loc_18004CAD4
0x18004cac6  lea     rcx, qword_180069A90; this
0x18004cacd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cad4  cmp     byte ptr [rcx+8], 0
0x18004cad8  jz      short loc_18004CAF8
0x18004cada  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004cadf  cmp     [rax+7CCh], ebx
0x18004cae5  jz      short loc_18004CAF8
0x18004cae7  mov     r9d, ebx; int
0x18004caea  mov     r8d, esi; int
0x18004caed  mov     rdx, r12; char *
0x18004caf0  mov     rcx, rax; this
0x18004caf3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004caf8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004cafd  cmp     al, 1
0x18004caff  jb      loc_18004CF69
0x18004cb05  mov     edx, 0Ah
0x18004cb0a  jmp     loc_18004CF4B
0x18004cb0f  lea     rsi, [rdi+78h]
0x18004cb13  mov     rcx, rsi; pvar
0x18004cb16  call    cs:__imp_PropVariantClear
0x18004cb1c  mov     ebx, eax
0x18004cb1e  test    eax, eax
0x18004cb20  jns     loc_18004CBB1
0x18004cb26  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cb2d  test    rcx, rcx
0x18004cb30  jnz     short loc_18004CB73
0x18004cb32  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004cb38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cb3f  mov     rcx, rax
0x18004cb42  test    rax, rax
0x18004cb45  jz      short loc_18004CB65
0x18004cb47  mov     rax, [rax]
0x18004cb4a  mov     edx, 7F0h
0x18004cb4f  mov     rax, [rax+8]
0x18004cb53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb58  test    eax, eax
0x18004cb5a  jz      short loc_18004CB65
0x18004cb5c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cb63  jmp     short loc_18004CB73
0x18004cb65  lea     rcx, qword_180069A90; this
0x18004cb6c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cb73  cmp     byte ptr [rcx+8], 0
0x18004cb77  jz      short loc_18004CB9A
0x18004cb79  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004cb7e  cmp     [rax+7CCh], ebx
0x18004cb84  jz      short loc_18004CB9A
0x18004cb86  mov     r9d, ebx; int
0x18004cb89  mov     r8d, 5Ah ; 'Z'; int
0x18004cb8f  mov     rdx, r12; char *
0x18004cb92  mov     rcx, rax; this
0x18004cb95  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004cb9a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004cb9f  cmp     al, 1
0x18004cba1  jb      loc_18004CF69
0x18004cba7  mov     edx, 0Bh
0x18004cbac  jmp     loc_18004CF4B
0x18004cbb1  mov     rdx, rbp; pvarSrc
0x18004cbb4  mov     rcx, r14; pvarDest
0x18004cbb7  call    cs:__imp_PropVariantCopy
0x18004cbbd  mov     ebx, eax
0x18004cbbf  test    eax, eax
0x18004cbc1  jns     loc_18004CC52
0x18004cbc7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cbce  test    rcx, rcx
0x18004cbd1  jnz     short loc_18004CC14
0x18004cbd3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004cbd9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cbe0  mov     rcx, rax
0x18004cbe3  test    rax, rax
0x18004cbe6  jz      short loc_18004CC06
0x18004cbe8  mov     rax, [rax]
0x18004cbeb  mov     edx, 7F0h
0x18004cbf0  mov     rax, [rax+8]
0x18004cbf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbf9  test    eax, eax
0x18004cbfb  jz      short loc_18004CC06
0x18004cbfd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cc04  jmp     short loc_18004CC14
0x18004cc06  lea     rcx, qword_180069A90; this
0x18004cc0d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cc14  cmp     byte ptr [rcx+8], 0
0x18004cc18  jz      short loc_18004CC3B
0x18004cc1a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004cc1f  cmp     [rax+7CCh], ebx
0x18004cc25  jz      short loc_18004CC3B
0x18004cc27  mov     r9d, ebx; int
0x18004cc2a  mov     r8d, 5Ch ; '\'; int
0x18004cc30  mov     rdx, r12; char *
0x18004cc33  mov     rcx, rax; this
0x18004cc36  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004cc3b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004cc40  cmp     al, 1
0x18004cc42  jb      loc_18004CF69
0x18004cc48  mov     edx, 0Ch
0x18004cc4d  jmp     loc_18004CF4B
0x18004cc52  xor     r8d, r8d
0x18004cc55  lea     rdx, MF_MD_EXTENDEDPROP
0x18004cc5c  mov     rcx, rdi
0x18004cc5f  call    MFGetAttributeUINT32
0x18004cc64  test    eax, eax
0x18004cc66  jz      loc_18004CD17
0x18004cc6c  lea     r8, [rsi+8]; pcb
0x18004cc70  mov     word ptr [rsi], 41h ; 'A'
0x18004cc75  lea     rdx, [r8+8]; ppProp
0x18004cc79  mov     rcx, rbp; ppropvar
0x18004cc7c  call    cs:__imp_StgSerializePropVariant
0x18004cc82  mov     ebx, eax
0x18004cc84  test    eax, eax
0x18004cc86  jns     loc_18004CF69
0x18004cc8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cc93  test    rcx, rcx
0x18004cc96  jnz     short loc_18004CCD9
0x18004cc98  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004cc9e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cca5  mov     rcx, rax
0x18004cca8  test    rax, rax
0x18004ccab  jz      short loc_18004CCCB
0x18004ccad  mov     rax, [rax]
0x18004ccb0  mov     edx, 7F0h
0x18004ccb5  mov     rax, [rax+8]
0x18004ccb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ccbe  test    eax, eax
0x18004ccc0  jz      short loc_18004CCCB
0x18004ccc2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ccc9  jmp     short loc_18004CCD9
0x18004cccb  lea     rcx, qword_180069A90; this
0x18004ccd2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ccd9  cmp     byte ptr [rcx+8], 0
0x18004ccdd  jz      short loc_18004CD00
0x18004ccdf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004cce4  cmp     [rax+7CCh], ebx
0x18004ccea  jz      short loc_18004CD00
0x18004ccec  mov     r9d, ebx; int
0x18004ccef  mov     r8d, 6Ch ; 'l'; int
0x18004ccf5  mov     rdx, r12; char *
0x18004ccf8  mov     rcx, rax; this
0x18004ccfb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004cd00  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004cd05  cmp     al, 1
0x18004cd07  jb      loc_18004CF69
0x18004cd0d  mov     edx, 0Dh
0x18004cd12  jmp     loc_18004CF4B
0x18004cd17  mov     rax, [rdi]
0x18004cd1a  lea     r8, [rsp+88h+arg_0]
0x18004cd22  lea     rdx, MF_MD_FSDKTYPE
0x18004cd29  mov     [rsp+88h+arg_0], 0
0x18004cd34  mov     rcx, rdi
0x18004cd37  mov     rax, [rax+38h]
0x18004cd3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd40  mov     ebx, eax
0x18004cd42  test    eax, eax
0x18004cd44  jns     loc_18004CDD5
0x18004cd4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cd51  test    rcx, rcx
0x18004cd54  jnz     short loc_18004CD97
0x18004cd56  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004cd5c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cd63  mov     rcx, rax
0x18004cd66  test    rax, rax
0x18004cd69  jz      short loc_18004CD89
0x18004cd6b  mov     rax, [rax]
0x18004cd6e  mov     edx, 7F0h
0x18004cd73  mov     rax, [rax+8]
0x18004cd77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd7c  test    eax, eax
0x18004cd7e  jz      short loc_18004CD89
0x18004cd80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cd87  jmp     short loc_18004CD97
0x18004cd89  lea     rcx, qword_180069A90; this
0x18004cd90  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cd97  cmp     byte ptr [rcx+8], 0
0x18004cd9b  jz      short loc_18004CDBE
0x18004cd9d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004cda2  cmp     [rax+7CCh], ebx
0x18004cda8  jz      short loc_18004CDBE
0x18004cdaa  mov     r9d, ebx; int
0x18004cdad  mov     r8d, 78h ; 'x'; int
0x18004cdb3  mov     rdx, r12; char *
0x18004cdb6  mov     rcx, rax; this
0x18004cdb9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004cdbe  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004cdc3  cmp     al, 1
0x18004cdc5  jb      loc_18004CF69
0x18004cdcb  mov     edx, 0Eh
0x18004cdd0  jmp     loc_18004CF4B
0x18004cdd5  movzx   eax, word ptr [rsp+88h+arg_0]
0x18004cddd  cmp     [rbp+0], ax
0x18004cde1  jnz     loc_18004CE88
0x18004cde7  mov     rdx, rbp; pvarSrc
0x18004cdea  mov     rcx, rsi; pvarDest
0x18004cded  call    cs:__imp_PropVariantCopy
0x18004cdf3  mov     ebx, eax
0x18004cdf5  test    eax, eax
0x18004cdf7  jns     loc_18004CF69
0x18004cdfd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ce04  test    rcx, rcx
0x18004ce07  jnz     short loc_18004CE4A
0x18004ce09  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004ce0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ce16  mov     rcx, rax
0x18004ce19  test    rax, rax
0x18004ce1c  jz      short loc_18004CE3C
0x18004ce1e  mov     rax, [rax]
0x18004ce21  mov     edx, 7F0h
0x18004ce26  mov     rax, [rax+8]
0x18004ce2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce2f  test    eax, eax
0x18004ce31  jz      short loc_18004CE3C
0x18004ce33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ce3a  jmp     short loc_18004CE4A
0x18004ce3c  lea     rcx, qword_180069A90; this
0x18004ce43  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ce4a  cmp     byte ptr [rcx+8], 0
0x18004ce4e  jz      short loc_18004CE71
0x18004ce50  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ce55  cmp     [rax+7CCh], ebx
0x18004ce5b  jz      short loc_18004CE71
0x18004ce5d  mov     r9d, ebx; int
0x18004ce60  mov     r8d, 7Fh; int
0x18004ce66  mov     rdx, r12; char *
0x18004ce69  mov     rcx, rax; this
0x18004ce6c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ce71  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004ce76  cmp     al, 1
0x18004ce78  jb      loc_18004CF69
0x18004ce7e  mov     edx, 0Fh
0x18004ce83  jmp     loc_18004CF4B
0x18004ce88  movups  xmm0, cs:MF_MD_FSDKMULTI
0x18004ce8f  lea     rax, [rsp+88h+var_58]
0x18004ce94  mov     r8, rsi; struct tagPROPVARIANT *
0x18004ce97  movups  xmm1, cs:MF_MD_FSDKTYPE
0x18004ce9e  lea     r9, [rsp+88h+var_48]; struct _GUID
0x18004cea3  mov     [rsp+88h+var_68], rax; struct _GUID
0x18004cea8  mov     rdx, r14; struct tagPROPVARIANT *
0x18004ceab  mov     rcx, rdi; this
0x18004ceae  movdqu  xmmword ptr [rsp+88h+var_58.Data1], xmm0
0x18004ceb4  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm1
0x18004ceba  call    ?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z; CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)
0x18004cebf  mov     ebx, eax
0x18004cec1  test    eax, eax
0x18004cec3  jns     loc_18004CF69
0x18004cec9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ced0  test    rcx, rcx
0x18004ced3  jnz     short loc_18004CF16
0x18004ced5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004cedb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cee2  mov     rcx, rax
0x18004cee5  test    rax, rax
0x18004cee8  jz      short loc_18004CF08
0x18004ceea  mov     rax, [rax]
0x18004ceed  mov     edx, 7F0h
0x18004cef2  mov     rax, [rax+8]
0x18004cef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cefb  test    eax, eax
0x18004cefd  jz      short loc_18004CF08
0x18004ceff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cf06  jmp     short loc_18004CF16
0x18004cf08  lea     rcx, qword_180069A90; this
0x18004cf0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cf16  cmp     byte ptr [rcx+8], 0
0x18004cf1a  jz      short loc_18004CF3D
0x18004cf1c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
  ... truncated ...
```
