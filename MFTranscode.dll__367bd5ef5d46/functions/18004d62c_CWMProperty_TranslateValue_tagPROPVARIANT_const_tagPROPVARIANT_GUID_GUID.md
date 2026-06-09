# CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)

- ea: `0x18004d62c`
- end: `0x18004daf4`
- name: `?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z`
- size: `1224`
- prototype: `int(CWMProperty *__hidden this, const struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004c280`
- `0x18004ca40`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800085a0`
- `0x1800153ac`
- `0x18001a330`
- `0x18001c280`
- `0x18004a398`
- `0x18004d62c`
- `0x18004dafc`
- `0x18004f410`
- `0x180057904`
- `0x180057fe4`
- `0x180058310`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004d955`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004d955`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d6fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d7ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d8ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d971`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004da3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d6fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d7ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d8ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d971`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004da3a`

## pseudocode

```c
__int64 __fastcall CWMProperty::TranslateValue(
        CWMProperty *this,
        struct tagPROPVARIANT *a2,
        struct tagPROPVARIANT *a3,
        struct _GUID *a4,
        struct _GUID *a5)
{
  VARTYPE vt; // r12
  unsigned int v9; // r12d
  int v10; // edi
  int v11; // eax
  int v12; // r15d
  __int64 v13; // rdx
  HRESULT Element; // ebx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  CWMProperty *v31; // rcx
  __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  _BYTE v37[4]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v38; // [rsp+34h] [rbp-44h]
  PROPVARIANT pvarSrc; // [rsp+38h] [rbp-40h] BYREF
  PROPVARIANT pvar; // [rsp+50h] [rbp-28h] BYREF

  vt = a2->vt;
  v38 = a2->vt & 0xEFFF;
  v9 = vt & 0x1000;
  memset(&pvarSrc, 0, sizeof(pvarSrc));
  v10 = MFGetAttributeUINT32(this, a4, v38);
  v11 = MFGetAttributeUINT32(this, a5, v9);
  v12 = v11;
  if ( !v9 || v11 )
  {
    CMFPropVariant::Copy(&pvarSrc, a2);
LABEL_28:
    if ( a2->vt == 65 )
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v37, "CWMProperty::TranslateValue", 277);
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      Element = -1072875854;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CWMProperty::TranslateValue", 277, -1072875854);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
          this,
          -1072875854);
    }
    else
    {
      if ( v38 == v10 )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v37, "CWMProperty::TranslateValue", 286);
        Element = PropVariantCopy(a3, &pvarSrc);
        if ( Element >= 0 )
          goto LABEL_66;
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
          CallStackTracing::s_wpInstance = v28;
          if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          {
            v27 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v27 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v27 + 8) )
        {
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
          if ( *((_DWORD *)v29 + 499) != Element )
            CallStackContext::TraceFailure(v29, "CWMProperty::TranslateValue", 286, Element);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_66;
        v30 = 27;
      }
      else
      {
        if ( v9 && v12 )
          LOWORD(v10) = v10 | 0x1000;
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v37, "CWMProperty::TranslateValue", 297);
        Element = CWMProperty::WMPropVariantChangeType(v31, a3, &pvarSrc, v10);
        if ( Element >= 0 )
          goto LABEL_66;
        v33 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v33 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v33 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v33 + 8) )
        {
          v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
          if ( *((_DWORD *)v35 + 499) != Element )
            CallStackContext::TraceFailure(v35, "CWMProperty::TranslateValue", 297, Element);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_66;
        v30 = 28;
      }
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v30,
        WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
        this,
        Element);
    }
LABEL_66:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v37);
    goto LABEL_67;
  }
  CMFPropVariant::CMFPropVariant(&pvar, a2);
  if ( !CMFPropVariant::GetElementCount((CMFPropVariant *)&pvar) )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v37, "CWMProperty::TranslateValue", 263);
    v19 = (__int64 *)CallStackTracing::s_wpInstance;
    Element = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
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
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != -1072875854 )
        CallStackContext::TraceFailure(v21, "CWMProperty::TranslateValue", 263, -1072875854);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
        this,
        -1072875854);
    goto LABEL_15;
  }
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v37, "CWMProperty::TranslateValue", 254);
  Element = CMFPropVariant::GetElement((CMFPropVariant *)&pvar, 0, &pvarSrc);
  if ( Element >= 0 )
  {
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v37);
    CMFPropVariant::Clear(&pvar);
    goto LABEL_28;
  }
  v15 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
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
    if ( *((_DWORD *)v17 + 499) != Element )
      CallStackContext::TraceFailure(v17, "CWMProperty::TranslateValue", 254, Element);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, Element);
LABEL_15:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v37);
  CMFPropVariant::Clear(&pvar);
LABEL_67:
  CMFPropVariant::Clear(&pvarSrc);
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x18004d62c  push    rbp
0x18004d62e  push    rbx
0x18004d62f  push    rsi
0x18004d630  push    rdi
0x18004d631  push    r12
0x18004d633  push    r13
0x18004d635  push    r14
0x18004d637  push    r15
0x18004d639  mov     rbp, rsp
0x18004d63c  sub     rsp, 78h
0x18004d640  movzx   r12d, word ptr [rdx]
0x18004d644  mov     rsi, rcx
0x18004d647  mov     rbx, [rbp+arg_20]
0x18004d64b  mov     eax, r12d
0x18004d64e  xor     ecx, ecx
0x18004d650  btr     eax, 0Ch
0x18004d654  mov     r13, r8
0x18004d657  mov     qword ptr [rbp+pvarSrc+10h], rcx
0x18004d65b  mov     r14, rdx
0x18004d65e  mov     [rbp+var_44], eax
0x18004d661  xorps   xmm0, xmm0
0x18004d664  mov     r8d, eax
0x18004d667  mov     rdx, r9
0x18004d66a  mov     rcx, rsi
0x18004d66d  and     r12d, 1000h
0x18004d674  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x18004d678  call    MFGetAttributeUINT32
0x18004d67d  mov     r8d, r12d
0x18004d680  mov     rdx, rbx
0x18004d683  mov     rcx, rsi
0x18004d686  mov     edi, eax
0x18004d688  call    MFGetAttributeUINT32
0x18004d68d  lea     rbx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x18004d694  mov     r15d, eax
0x18004d697  test    r12d, r12d
0x18004d69a  jz      loc_18004D86E
0x18004d6a0  test    eax, eax
0x18004d6a2  jnz     loc_18004D86E
0x18004d6a8  mov     rdx, r14; pvarSrc
0x18004d6ab  lea     rcx, [rbp+pvar]; pvarDest
0x18004d6af  call    ??0CMFPropVariant@@QEAA@AEBUtagPROPVARIANT@@@Z; CMFPropVariant::CMFPropVariant(tagPROPVARIANT const &)
0x18004d6b4  lea     rcx, [rbp+pvar]; this
0x18004d6b8  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x18004d6bd  lea     rcx, [rbp+var_48]; this
0x18004d6c1  mov     rdx, rbx; char *
0x18004d6c4  test    eax, eax
0x18004d6c6  jz      loc_18004D7C9
0x18004d6cc  mov     r8d, 0FEh; int
0x18004d6d2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004d6d7  lea     r8, [rbp+pvarSrc]; struct tagPROPVARIANT *
0x18004d6db  xor     edx, edx; unsigned int
0x18004d6dd  lea     rcx, [rbp+pvar]; this
0x18004d6e1  call    ?GetElement@CMFPropVariant@@QEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElement(ulong,tagPROPVARIANT *)
0x18004d6e6  mov     ebx, eax
0x18004d6e8  test    eax, eax
0x18004d6ea  jns     loc_18004D7AB
0x18004d6f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d6f7  test    rcx, rcx
0x18004d6fa  jnz     short loc_18004D73D
0x18004d6fc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d702  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d709  mov     rcx, rax
0x18004d70c  test    rax, rax
0x18004d70f  jz      short loc_18004D72F
0x18004d711  mov     rax, [rax]
0x18004d714  mov     edx, 7F0h
0x18004d719  mov     rax, [rax+8]
0x18004d71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d722  test    eax, eax
0x18004d724  jz      short loc_18004D72F
0x18004d726  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d72d  jmp     short loc_18004D73D
0x18004d72f  lea     rcx, qword_180069A90; this
0x18004d736  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d73d  cmp     byte ptr [rcx+8], 0
0x18004d741  jz      short loc_18004D768
0x18004d743  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d748  cmp     [rax+7CCh], ebx
0x18004d74e  jz      short loc_18004D768
0x18004d750  mov     r9d, ebx; int
0x18004d753  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x18004d75a  mov     r8d, 0FEh; int
0x18004d760  mov     rcx, rax; this
0x18004d763  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d768  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004d76d  cmp     al, 1
0x18004d76f  jb      short loc_18004D794
0x18004d771  mov     edx, 18h
0x18004d776  mov     [rsp+78h+var_58], ebx
0x18004d77a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d781  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x18004d788  mov     r9, rsi
0x18004d78b  mov     rcx, [rcx+10h]
0x18004d78f  call    WPP_SF_qd
0x18004d794  lea     rcx, [rbp+var_48]; this
0x18004d798  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004d79d  lea     rcx, [rbp+pvar]; pvar
0x18004d7a1  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18004d7a6  jmp     loc_18004DAD8
0x18004d7ab  lea     rcx, [rbp+var_48]; this
0x18004d7af  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004d7b4  lea     rcx, [rbp+pvar]; pvar
0x18004d7b8  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18004d7bd  lea     rbx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x18004d7c4  jmp     loc_18004D87A
0x18004d7c9  mov     r14d, 107h
0x18004d7cf  mov     r8d, r14d; int
0x18004d7d2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004d7d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d7de  mov     edi, 0C00D36B2h
0x18004d7e3  mov     ebx, edi
0x18004d7e5  test    rcx, rcx
0x18004d7e8  jnz     short loc_18004D82B
0x18004d7ea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d7f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d7f7  mov     rcx, rax
0x18004d7fa  test    rax, rax
0x18004d7fd  jz      short loc_18004D81D
0x18004d7ff  mov     rax, [rax]
0x18004d802  mov     edx, 7F0h
0x18004d807  mov     rax, [rax+8]
0x18004d80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d810  test    eax, eax
0x18004d812  jz      short loc_18004D81D
0x18004d814  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d81b  jmp     short loc_18004D82B
0x18004d81d  lea     rcx, qword_180069A90; this
0x18004d824  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d82b  cmp     byte ptr [rcx+8], 0
0x18004d82f  jz      short loc_18004D853
0x18004d831  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d836  cmp     [rax+7CCh], edi
0x18004d83c  jz      short loc_18004D853
0x18004d83e  mov     r9d, edi; int
0x18004d841  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x18004d848  mov     r8d, r14d; int
0x18004d84b  mov     rcx, rax; this
0x18004d84e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d853  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004d858  cmp     al, 1
0x18004d85a  jb      loc_18004D794
0x18004d860  mov     edx, 19h
0x18004d865  mov     [rsp+78h+var_58], edi
0x18004d869  jmp     loc_18004D77A
0x18004d86e  mov     rdx, r14; pvarSrc
0x18004d871  lea     rcx, [rbp+pvarSrc]; pvarDest
0x18004d875  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x18004d87a  cmp     word ptr [r14], 41h ; 'A'
0x18004d87f  jnz     loc_18004D931
0x18004d885  mov     r14d, 115h
0x18004d88b  lea     rcx, [rbp+var_48]; this
0x18004d88f  mov     r8d, r14d; int
0x18004d892  mov     rdx, rbx; char *
0x18004d895  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004d89a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d8a1  mov     edi, 0C00D36B2h
0x18004d8a6  mov     ebx, edi
0x18004d8a8  test    rcx, rcx
0x18004d8ab  jnz     short loc_18004D8EE
0x18004d8ad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d8b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d8ba  mov     rcx, rax
0x18004d8bd  test    rax, rax
0x18004d8c0  jz      short loc_18004D8E0
0x18004d8c2  mov     rax, [rax]
0x18004d8c5  mov     edx, 7F0h
0x18004d8ca  mov     rax, [rax+8]
0x18004d8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8d3  test    eax, eax
0x18004d8d5  jz      short loc_18004D8E0
0x18004d8d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d8de  jmp     short loc_18004D8EE
0x18004d8e0  lea     rcx, qword_180069A90; this
0x18004d8e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d8ee  cmp     byte ptr [rcx+8], 0
0x18004d8f2  jz      short loc_18004D916
0x18004d8f4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d8f9  cmp     [rax+7CCh], edi
0x18004d8ff  jz      short loc_18004D916
0x18004d901  mov     r9d, edi; int
0x18004d904  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x18004d90b  mov     r8d, r14d; int
0x18004d90e  mov     rcx, rax; this
0x18004d911  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d916  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004d91b  cmp     al, 1
0x18004d91d  jb      loc_18004DACF
0x18004d923  mov     edx, 1Ah
0x18004d928  mov     [rsp+78h+var_58], edi
0x18004d92c  jmp     loc_18004DAB5
0x18004d931  cmp     [rbp+var_44], edi
0x18004d934  jnz     loc_18004D9F1
0x18004d93a  mov     edi, 11Eh
0x18004d93f  lea     rcx, [rbp+var_48]; this
0x18004d943  mov     r8d, edi; int
0x18004d946  mov     rdx, rbx; char *
0x18004d949  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004d94e  lea     rdx, [rbp+pvarSrc]; pvarSrc
0x18004d952  mov     rcx, r13; pvarDest
0x18004d955  call    cs:__imp_PropVariantCopy
0x18004d95b  mov     ebx, eax
0x18004d95d  test    eax, eax
0x18004d95f  jns     loc_18004DACF
0x18004d965  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d96c  test    rcx, rcx
0x18004d96f  jnz     short loc_18004D9B2
0x18004d971  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d977  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d97e  mov     rcx, rax
0x18004d981  test    rax, rax
0x18004d984  jz      short loc_18004D9A4
0x18004d986  mov     rax, [rax]
0x18004d989  mov     edx, 7F0h
0x18004d98e  mov     rax, [rax+8]
0x18004d992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d997  test    eax, eax
0x18004d999  jz      short loc_18004D9A4
0x18004d99b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d9a2  jmp     short loc_18004D9B2
0x18004d9a4  lea     rcx, qword_180069A90; this
0x18004d9ab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d9b2  cmp     byte ptr [rcx+8], 0
0x18004d9b6  jz      short loc_18004D9DA
0x18004d9b8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d9bd  cmp     [rax+7CCh], ebx
0x18004d9c3  jz      short loc_18004D9DA
0x18004d9c5  mov     r9d, ebx; int
0x18004d9c8  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x18004d9cf  mov     r8d, edi; int
0x18004d9d2  mov     rcx, rax; this
0x18004d9d5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d9da  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004d9df  cmp     al, 1
0x18004d9e1  jb      loc_18004DACF
0x18004d9e7  mov     edx, 1Bh
0x18004d9ec  jmp     loc_18004DAB1
0x18004d9f1  test    r12d, r12d
0x18004d9f4  jz      short loc_18004D9FF
0x18004d9f6  test    r15d, r15d
0x18004d9f9  jz      short loc_18004D9FF
0x18004d9fb  bts     edi, 0Ch
0x18004d9ff  mov     r14d, 129h
0x18004da05  lea     rcx, [rbp+var_48]; this
0x18004da09  mov     r8d, r14d; int
0x18004da0c  mov     rdx, rbx; char *
0x18004da0f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004da14  movzx   r9d, di; unsigned __int16
0x18004da18  lea     r8, [rbp+pvarSrc]; struct tagPROPVARIANT *
0x18004da1c  mov     rdx, r13; struct tagPROPVARIANT *
0x18004da1f  call    ?WMPropVariantChangeType@CWMProperty@@IEAAJPEAUtagPROPVARIANT@@AEBU2@G@Z; CWMProperty::WMPropVariantChangeType(tagPROPVARIANT *,tagPROPVARIANT const &,ushort)
0x18004da24  mov     ebx, eax
0x18004da26  test    eax, eax
0x18004da28  jns     loc_18004DACF
0x18004da2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004da35  test    rcx, rcx
0x18004da38  jnz     short loc_18004DA7B
0x18004da3a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004da40  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004da47  mov     rcx, rax
0x18004da4a  test    rax, rax
0x18004da4d  jz      short loc_18004DA6D
0x18004da4f  mov     rax, [rax]
0x18004da52  mov     edx, 7F0h
0x18004da57  mov     rax, [rax+8]
0x18004da5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da60  test    eax, eax
0x18004da62  jz      short loc_18004DA6D
0x18004da64  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004da6b  jmp     short loc_18004DA7B
0x18004da6d  lea     rcx, qword_180069A90; this
0x18004da74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004da7b  cmp     byte ptr [rcx+8], 0
0x18004da7f  jz      short loc_18004DAA3
0x18004da81  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004da86  cmp     [rax+7CCh], ebx
0x18004da8c  jz      short loc_18004DAA3
0x18004da8e  mov     r9d, ebx; int
0x18004da91  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x18004da98  mov     r8d, r14d; int
0x18004da9b  mov     rcx, rax; this
0x18004da9e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004daa3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004daa8  cmp     al, 1
0x18004daaa  jb      short loc_18004DACF
0x18004daac  mov     edx, 1Ch
0x18004dab1  mov     [rsp+78h+var_58], ebx
0x18004dab5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dabc  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x18004dac3  mov     r9, rsi
0x18004dac6  mov     rcx, [rcx+10h]
0x18004daca  call    WPP_SF_qd
0x18004dacf  lea     rcx, [rbp+var_48]; this
0x18004dad3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004dad8  lea     rcx, [rbp+pvarSrc]; pvar
0x18004dadc  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18004dae1  mov     eax, ebx
0x18004dae3  add     rsp, 78h
0x18004dae7  pop     r15
0x18004dae9  pop     r14
0x18004daeb  pop     r13
  ... truncated ...
```
