# CWMMCDIProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x180012ed0`
- end: `0x18001326f`
- name: `?SetNativeValue@CWMMCDIProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `927`
- prototype: `int(CWMMCDIProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180012ed0`
- `0x18001a330`
- `0x18001c280`
- `0x180022064`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012ee8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012f16`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012ee8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012f16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001305c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001305c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180012fb8`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180012fb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012f32`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012fd4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013080`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013127`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800131c4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012f32`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012fd4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013080`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013127`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800131c4`

## pseudocode

```c
__int64 __fastcall CWMMCDIProperty::SetNativeValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // edi
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  unsigned __int16 *v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  char v28; // [rsp+70h] [rbp+8h] BYREF

  PropVariantClear(this + 4);
  if ( a2->vt == 65 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v28, "CWMMCDIProperty::SetNativeValue", 423);
    v5 = PropVariantClear(this + 5);
    if ( v5 >= 0 )
    {
      v5 = PropVariantCopy(this + 5, a2);
      if ( v5 >= 0 )
      {
        this[4].vt = 31;
        v14 = (unsigned __int16 *)CoTaskMemAlloc(a2->ulVal);
        this[4].hVal.QuadPart = (LONGLONG)v14;
        if ( v14 )
        {
          v5 = StringCchCopyW(v14, (unsigned __int64)a2->ulVal >> 1, a2->caui.pElems);
          if ( v5 < 0 )
          {
            v20 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
              CallStackTracing::s_wpInstance = v21;
              if ( v21
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
              {
                v20 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v20 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v20 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMMCDIProperty::SetNativeValue", 446, v5);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v9 = 38;
              goto LABEL_56;
            }
          }
        }
        else
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
          v5 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
            CallStackTracing::s_wpInstance = v17;
            if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
            {
              v16 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v16 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v16 + 8) )
          {
            v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
            if ( *((_DWORD *)v18 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v18, "CWMMCDIProperty::SetNativeValue", 438, -2147024882);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 37;
            goto LABEL_56;
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
            CallStackContext::TraceFailure(v13, "CWMMCDIProperty::SetNativeValue", 425, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 36;
          goto LABEL_56;
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
          CallStackContext::TraceFailure(v8, "CWMMCDIProperty::SetNativeValue", 423, v5);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 35;
LABEL_56:
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v28, "CWMMCDIProperty::SetNativeValue", 451);
    v24 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
      CallStackTracing::s_wpInstance = v25;
      if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
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
      if ( *((_DWORD *)v26 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v26, "CWMMCDIProperty::SetNativeValue", 451, -2147418113);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 39;
      goto LABEL_56;
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v28);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180012ed0  push    rbp
0x180012ed2  push    rsi
0x180012ed3  push    rdi
0x180012ed4  push    r12
0x180012ed6  push    r14
0x180012ed8  push    r15
0x180012eda  sub     rsp, 38h
0x180012ede  mov     rbp, rcx
0x180012ee1  mov     rsi, rdx
0x180012ee4  add     rcx, 60h ; '`'; pvar
0x180012ee8  call    cs:__imp_PropVariantClear
0x180012eee  cmp     word ptr [rsi], 41h ; 'A'
0x180012ef2  lea     r14, aCwmmcdipropert_0; "CWMMCDIProperty::SetNativeValue"
0x180012ef9  mov     rdx, r14; char *
0x180012efc  lea     rcx, [rsp+68h+arg_0]; this
0x180012f01  jnz     loc_1800131A6
0x180012f07  mov     r8d, 1A7h; int
0x180012f0d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180012f12  lea     rcx, [rbp+78h]; pvar
0x180012f16  call    cs:__imp_PropVariantClear
0x180012f1c  mov     edi, eax
0x180012f1e  test    eax, eax
0x180012f20  jns     loc_180012FB1
0x180012f26  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012f2d  test    rcx, rcx
0x180012f30  jnz     short loc_180012F73
0x180012f32  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012f38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012f3f  mov     rcx, rax
0x180012f42  test    rax, rax
0x180012f45  jz      short loc_180012F65
0x180012f47  mov     rax, [rax]
0x180012f4a  mov     edx, 7F0h
0x180012f4f  mov     rax, [rax+8]
0x180012f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f58  test    eax, eax
0x180012f5a  jz      short loc_180012F65
0x180012f5c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012f63  jmp     short loc_180012F73
0x180012f65  lea     rcx, qword_180069A90; this
0x180012f6c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012f73  cmp     byte ptr [rcx+8], 0
0x180012f77  jz      short loc_180012F9A
0x180012f79  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012f7e  cmp     [rax+7CCh], edi
0x180012f84  jz      short loc_180012F9A
0x180012f86  mov     r9d, edi; int
0x180012f89  mov     r8d, 1A7h; int
0x180012f8f  mov     rdx, r14; char *
0x180012f92  mov     rcx, rax; this
0x180012f95  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012f9a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180012f9f  cmp     al, 1
0x180012fa1  jb      loc_180013255
0x180012fa7  mov     edx, 23h ; '#'
0x180012fac  jmp     loc_180013237
0x180012fb1  mov     rdx, rsi; pvarSrc
0x180012fb4  lea     rcx, [rbp+78h]; pvarDest
0x180012fb8  call    cs:__imp_PropVariantCopy
0x180012fbe  mov     edi, eax
0x180012fc0  test    eax, eax
0x180012fc2  jns     loc_180013053
0x180012fc8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012fcf  test    rcx, rcx
0x180012fd2  jnz     short loc_180013015
0x180012fd4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012fda  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012fe1  mov     rcx, rax
0x180012fe4  test    rax, rax
0x180012fe7  jz      short loc_180013007
0x180012fe9  mov     rax, [rax]
0x180012fec  mov     edx, 7F0h
0x180012ff1  mov     rax, [rax+8]
0x180012ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ffa  test    eax, eax
0x180012ffc  jz      short loc_180013007
0x180012ffe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013005  jmp     short loc_180013015
0x180013007  lea     rcx, qword_180069A90; this
0x18001300e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180013015  cmp     byte ptr [rcx+8], 0
0x180013019  jz      short loc_18001303C
0x18001301b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013020  cmp     [rax+7CCh], edi
0x180013026  jz      short loc_18001303C
0x180013028  mov     r9d, edi; int
0x18001302b  mov     r8d, 1A9h; int
0x180013031  mov     rdx, r14; char *
0x180013034  mov     rcx, rax; this
0x180013037  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001303c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180013041  cmp     al, 1
0x180013043  jb      loc_180013255
0x180013049  mov     edx, 24h ; '$'
0x18001304e  jmp     loc_180013237
0x180013053  mov     word ptr [rbp+60h], 1Fh
0x180013059  mov     ecx, [rsi+8]; cb
0x18001305c  call    cs:__imp_CoTaskMemAlloc
0x180013062  mov     [rbp+68h], rax
0x180013066  test    rax, rax
0x180013069  jnz     loc_1800130FF
0x18001306f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013076  mov     edi, 8007000Eh
0x18001307b  test    rcx, rcx
0x18001307e  jnz     short loc_1800130C1
0x180013080  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180013086  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001308d  mov     rcx, rax
0x180013090  test    rax, rax
0x180013093  jz      short loc_1800130B3
0x180013095  mov     rax, [rax]
0x180013098  mov     edx, 7F0h
0x18001309d  mov     rax, [rax+8]
0x1800130a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130a6  test    eax, eax
0x1800130a8  jz      short loc_1800130B3
0x1800130aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800130b1  jmp     short loc_1800130C1
0x1800130b3  lea     rcx, qword_180069A90; this
0x1800130ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800130c1  cmp     byte ptr [rcx+8], 0
0x1800130c5  jz      short loc_1800130E8
0x1800130c7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800130cc  cmp     [rax+7CCh], edi
0x1800130d2  jz      short loc_1800130E8
0x1800130d4  mov     r9d, edi; int
0x1800130d7  mov     r8d, 1B6h; int
0x1800130dd  mov     rdx, r14; char *
0x1800130e0  mov     rcx, rax; this
0x1800130e3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800130e8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800130ed  cmp     al, 1
0x1800130ef  jb      loc_180013255
0x1800130f5  mov     edx, 25h ; '%'
0x1800130fa  jmp     loc_180013237
0x1800130ff  mov     edx, [rsi+8]
0x180013102  mov     rcx, rax; unsigned __int16 *
0x180013105  mov     r8, [rsi+10h]; unsigned __int16 *
0x180013109  shr     rdx, 1; unsigned __int64
0x18001310c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013111  mov     edi, eax
0x180013113  test    eax, eax
0x180013115  jns     loc_180013255
0x18001311b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013122  test    rcx, rcx
0x180013125  jnz     short loc_180013168
0x180013127  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001312d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180013134  mov     rcx, rax
0x180013137  test    rax, rax
0x18001313a  jz      short loc_18001315A
0x18001313c  mov     rax, [rax]
0x18001313f  mov     edx, 7F0h
0x180013144  mov     rax, [rax+8]
0x180013148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001314d  test    eax, eax
0x18001314f  jz      short loc_18001315A
0x180013151  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013158  jmp     short loc_180013168
0x18001315a  lea     rcx, qword_180069A90; this
0x180013161  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180013168  cmp     byte ptr [rcx+8], 0
0x18001316c  jz      short loc_18001318F
0x18001316e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013173  cmp     [rax+7CCh], edi
0x180013179  jz      short loc_18001318F
0x18001317b  mov     r9d, edi; int
0x18001317e  mov     r8d, 1BEh; int
0x180013184  mov     rdx, r14; char *
0x180013187  mov     rcx, rax; this
0x18001318a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001318f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180013194  cmp     al, 1
0x180013196  jb      loc_180013255
0x18001319c  mov     edx, 26h ; '&'
0x1800131a1  jmp     loc_180013237
0x1800131a6  mov     esi, 1C3h
0x1800131ab  mov     r8d, esi; int
0x1800131ae  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800131b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800131ba  mov     edi, 8000FFFFh
0x1800131bf  test    rcx, rcx
0x1800131c2  jnz     short loc_180013205
0x1800131c4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800131ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800131d1  mov     rcx, rax
0x1800131d4  test    rax, rax
0x1800131d7  jz      short loc_1800131F7
0x1800131d9  mov     rax, [rax]
0x1800131dc  mov     edx, 7F0h
0x1800131e1  mov     rax, [rax+8]
0x1800131e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131ea  test    eax, eax
0x1800131ec  jz      short loc_1800131F7
0x1800131ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800131f5  jmp     short loc_180013205
0x1800131f7  lea     rcx, qword_180069A90; this
0x1800131fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180013205  cmp     byte ptr [rcx+8], 0
0x180013209  jz      short loc_180013229
0x18001320b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013210  cmp     [rax+7CCh], edi
0x180013216  jz      short loc_180013229
0x180013218  mov     r9d, edi; int
0x18001321b  mov     r8d, esi; int
0x18001321e  mov     rdx, r14; char *
0x180013221  mov     rcx, rax; this
0x180013224  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180013229  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001322e  cmp     al, 1
0x180013230  jb      short loc_180013255
0x180013232  mov     edx, 27h ; '''
0x180013237  mov     rcx, cs:WPP_GLOBAL_Control
0x18001323e  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x180013245  mov     r9, rbp
0x180013248  mov     [rsp+68h+var_48], edi
0x18001324c  mov     rcx, [rcx+10h]
0x180013250  call    WPP_SF_qd
0x180013255  lea     rcx, [rsp+68h+arg_0]; this
0x18001325a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001325f  mov     eax, edi
0x180013261  add     rsp, 38h
0x180013265  pop     r15
0x180013267  pop     r14
0x180013269  pop     r12
0x18001326b  pop     rdi
0x18001326c  pop     rsi
0x18001326d  pop     rbp
0x18001326e  retn
```
