# CWMProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x1802da670`
- end: `0x1802dac06`
- name: `?SetShellValue@CWMProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1430`
- prototype: `__int64 __fastcall(CWMProperty *__hidden this, PROPVARIANT *pvarSrc)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180247350`
- `0x18024d0f0`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x18008b3a0`
- `0x1800ec0e0`
- `0x1802467d4`
- `0x1802da670`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1802da801`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1802daa59`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1802da801`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1802daa59`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1802da6a7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1802da753`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1802da6a7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1802da753`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da6c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da775`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da823`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da8f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da9bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802daa7b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802dab4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da6c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da775`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da823`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da8f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802da9bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802daa7b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802dab4e`
- `PROPSYS!StgSerializePropVariant` at `0x1802da8d3`
- `PROPSYS!StgSerializePropVariant` at `0x1802da8d3`

## pseudocode

```c
__int64 __fastcall CWMProperty::SetShellValue(CWMProperty *this, PROPVARIANT *pvarSrc)
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
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 (__fastcall **v26)(CWMProperty *, __int128 *, _DWORD *); // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  struct _GUID v43; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID v44; // [rsp+40h] [rbp-48h] BYREF
  int v45; // [rsp+90h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v45, "CWMProperty::SetShellValue", 89);
  v5 = PropVariantClear((PROPVARIANT *)this + 12);
  if ( v5 >= 0 )
  {
    v5 = PropVariantClear((PROPVARIANT *)this + 15);
    if ( v5 >= 0 )
    {
      v5 = PropVariantCopy((PROPVARIANT *)this + 12, pvarSrc);
      if ( v5 >= 0 )
      {
        if ( (unsigned int)MFGetAttributeUINT32(this, &MF_MD_EXTENDEDPROP, 0) )
        {
          *((_WORD *)this + 60) = 65;
          v5 = StgSerializePropVariant(pvarSrc, (SERIALIZEDPROPERTYVALUE **)this + 17, (ULONG *)this + 32);
          if ( v5 < 0 )
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
              CallStackTracing::s_wpInstance = v24;
              if ( v24
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
              {
                v23 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v23 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v23 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMProperty::SetShellValue", 108, v5);
            }
            if ( g_wppLevels )
            {
              v10 = 13;
              goto LABEL_80;
            }
          }
        }
        else
        {
          v26 = *(__int64 (__fastcall ***)(CWMProperty *, __int128 *, _DWORD *))this;
          v45 = 0;
          v5 = v26[7](this, &MF_MD_FSDKTYPE, &v45);
          if ( v5 >= 0 )
          {
            if ( *(_WORD *)pvarSrc == (_WORD)v45 )
            {
              v5 = PropVariantCopy((PROPVARIANT *)this + 15, pvarSrc);
              if ( v5 < 0 )
              {
                v34 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33);
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
                    CallStackContext::TraceFailure(v36, "CWMProperty::SetShellValue", 127, v5);
                }
                if ( g_wppLevels )
                {
                  v10 = 15;
                  goto LABEL_80;
                }
              }
            }
            else
            {
              v43 = (struct _GUID)MF_MD_FSDKMULTI;
              v44 = (struct _GUID)MF_MD_FSDKTYPE;
              v5 = CWMProperty::TranslateValue(
                     this,
                     (const struct tagPROPVARIANT *)this + 4,
                     (struct tagPROPVARIANT *)this + 5,
                     &v44,
                     &v43);
              if ( v5 < 0 )
              {
                v39 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38);
                  CallStackTracing::s_wpInstance = v40;
                  if ( v40
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
                  {
                    v39 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v39 = &qword_1803CE250;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                  }
                }
                if ( *((_BYTE *)v39 + 8) )
                {
                  v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
                  if ( *((_DWORD *)v41 + 499) != v5 )
                    CallStackContext::TraceFailure(v41, "CWMProperty::SetShellValue", 131, v5);
                }
                if ( g_wppLevels )
                {
                  v10 = 16;
                  goto LABEL_80;
                }
              }
            }
          }
          else
          {
            v29 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28);
              CallStackTracing::s_wpInstance = v30;
              if ( v30
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
              {
                v29 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v29 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v29 + 8) )
            {
              v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
              if ( *((_DWORD *)v31 + 499) != v5 )
                CallStackContext::TraceFailure(v31, "CWMProperty::SetShellValue", 120, v5);
            }
            if ( g_wppLevels )
            {
              v10 = 14;
              goto LABEL_80;
            }
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
            CallStackContext::TraceFailure(v20, "CWMProperty::SetShellValue", 92, v5);
        }
        if ( g_wppLevels )
        {
          v10 = 12;
          goto LABEL_80;
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
          CallStackContext::TraceFailure(v15, "CWMProperty::SetShellValue", 90, v5);
      }
      if ( g_wppLevels )
      {
        v10 = 11;
        goto LABEL_80;
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
        CallStackContext::TraceFailure(v9, "CWMProperty::SetShellValue", 89, v5);
    }
    if ( g_wppLevels )
    {
      v10 = 10;
LABEL_80:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v45);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1802da670  mov     rax, rsp
0x1802da673  push    rbx
0x1802da674  push    rbp
0x1802da675  push    rsi
0x1802da676  push    rdi
0x1802da677  push    r12
0x1802da679  push    r14
0x1802da67b  sub     rsp, 58h
0x1802da67f  mov     rbp, rdx
0x1802da682  lea     r12, aCwmpropertySet_0; "CWMProperty::SetShellValue"
0x1802da689  mov     rdi, rcx
0x1802da68c  mov     esi, 59h ; 'Y'
0x1802da691  mov     r8d, esi; int
0x1802da694  lea     rcx, [rax+8]; this
0x1802da698  mov     rdx, r12; char *
0x1802da69b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1802da6a0  lea     r14, [rdi+60h]
0x1802da6a4  mov     rcx, r14; pvar
0x1802da6a7  call    cs:__imp_PropVariantClear
0x1802da6ae  nop     dword ptr [rax+rax+00h]
0x1802da6b3  mov     ebx, eax
0x1802da6b5  test    eax, eax
0x1802da6b7  jns     loc_1802DA74C
0x1802da6bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da6c4  test    rcx, rcx
0x1802da6c7  jnz     short loc_1802DA711
0x1802da6c9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802da6d0  nop     dword ptr [rax+rax+00h]
0x1802da6d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da6dc  mov     rcx, rax
0x1802da6df  test    rax, rax
0x1802da6e2  jz      short loc_1802DA703
0x1802da6e4  mov     rax, [rax]
0x1802da6e7  mov     edx, 7F0h
0x1802da6ec  mov     rax, [rax+8]
0x1802da6f0  call    cs:__guard_dispatch_icall_fptr
0x1802da6f6  test    eax, eax
0x1802da6f8  jz      short loc_1802DA703
0x1802da6fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da701  jmp     short loc_1802DA711
0x1802da703  lea     rcx, qword_1803CE250; this
0x1802da70a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da711  cmp     byte ptr [rcx+8], 0
0x1802da715  jz      short loc_1802DA735
0x1802da717  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802da71c  cmp     [rax+7CCh], ebx
0x1802da722  jz      short loc_1802DA735
0x1802da724  mov     r9d, ebx; int
0x1802da727  mov     r8d, esi; int
0x1802da72a  mov     rdx, r12; char *
0x1802da72d  mov     rcx, rax; this
0x1802da730  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802da735  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802da73c  jb      loc_1802DABE9
0x1802da742  mov     edx, 0Ah
0x1802da747  jmp     loc_1802DABCB
0x1802da74c  lea     rsi, [rdi+78h]
0x1802da750  mov     rcx, rsi; pvar
0x1802da753  call    cs:__imp_PropVariantClear
0x1802da75a  nop     dword ptr [rax+rax+00h]
0x1802da75f  mov     ebx, eax
0x1802da761  test    eax, eax
0x1802da763  jns     loc_1802DA7FB
0x1802da769  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da770  test    rcx, rcx
0x1802da773  jnz     short loc_1802DA7BD
0x1802da775  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802da77c  nop     dword ptr [rax+rax+00h]
0x1802da781  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da788  mov     rcx, rax
0x1802da78b  test    rax, rax
0x1802da78e  jz      short loc_1802DA7AF
0x1802da790  mov     rax, [rax]
0x1802da793  mov     edx, 7F0h
0x1802da798  mov     rax, [rax+8]
0x1802da79c  call    cs:__guard_dispatch_icall_fptr
0x1802da7a2  test    eax, eax
0x1802da7a4  jz      short loc_1802DA7AF
0x1802da7a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da7ad  jmp     short loc_1802DA7BD
0x1802da7af  lea     rcx, qword_1803CE250; this
0x1802da7b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da7bd  cmp     byte ptr [rcx+8], 0
0x1802da7c1  jz      short loc_1802DA7E4
0x1802da7c3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802da7c8  cmp     [rax+7CCh], ebx
0x1802da7ce  jz      short loc_1802DA7E4
0x1802da7d0  mov     r9d, ebx; int
0x1802da7d3  mov     r8d, 5Ah ; 'Z'; int
0x1802da7d9  mov     rdx, r12; char *
0x1802da7dc  mov     rcx, rax; this
0x1802da7df  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802da7e4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802da7eb  jb      loc_1802DABE9
0x1802da7f1  mov     edx, 0Bh
0x1802da7f6  jmp     loc_1802DABCB
0x1802da7fb  mov     rdx, rbp; pvarSrc
0x1802da7fe  mov     rcx, r14; pvarDest
0x1802da801  call    cs:__imp_PropVariantCopy
0x1802da808  nop     dword ptr [rax+rax+00h]
0x1802da80d  mov     ebx, eax
0x1802da80f  test    eax, eax
0x1802da811  jns     loc_1802DA8A9
0x1802da817  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da81e  test    rcx, rcx
0x1802da821  jnz     short loc_1802DA86B
0x1802da823  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802da82a  nop     dword ptr [rax+rax+00h]
0x1802da82f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da836  mov     rcx, rax
0x1802da839  test    rax, rax
0x1802da83c  jz      short loc_1802DA85D
0x1802da83e  mov     rax, [rax]
0x1802da841  mov     edx, 7F0h
0x1802da846  mov     rax, [rax+8]
0x1802da84a  call    cs:__guard_dispatch_icall_fptr
0x1802da850  test    eax, eax
0x1802da852  jz      short loc_1802DA85D
0x1802da854  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da85b  jmp     short loc_1802DA86B
0x1802da85d  lea     rcx, qword_1803CE250; this
0x1802da864  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da86b  cmp     byte ptr [rcx+8], 0
0x1802da86f  jz      short loc_1802DA892
0x1802da871  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802da876  cmp     [rax+7CCh], ebx
0x1802da87c  jz      short loc_1802DA892
0x1802da87e  mov     r9d, ebx; int
0x1802da881  mov     r8d, 5Ch ; '\'; int
0x1802da887  mov     rdx, r12; char *
0x1802da88a  mov     rcx, rax; this
0x1802da88d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802da892  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802da899  jb      loc_1802DABE9
0x1802da89f  mov     edx, 0Ch
0x1802da8a4  jmp     loc_1802DABCB
0x1802da8a9  xor     r8d, r8d
0x1802da8ac  lea     rdx, MF_MD_EXTENDEDPROP
0x1802da8b3  mov     rcx, rdi
0x1802da8b6  call    MFGetAttributeUINT32
0x1802da8bb  test    eax, eax
0x1802da8bd  jz      loc_1802DA97B
0x1802da8c3  lea     r8, [rsi+8]; pcb
0x1802da8c7  mov     word ptr [rsi], 41h ; 'A'
0x1802da8cc  lea     rdx, [r8+8]; ppProp
0x1802da8d0  mov     rcx, rbp; ppropvar
0x1802da8d3  call    cs:__imp_StgSerializePropVariant
0x1802da8da  nop     dword ptr [rax+rax+00h]
0x1802da8df  mov     ebx, eax
0x1802da8e1  test    eax, eax
0x1802da8e3  jns     loc_1802DABE9
0x1802da8e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da8f0  test    rcx, rcx
0x1802da8f3  jnz     short loc_1802DA93D
0x1802da8f5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802da8fc  nop     dword ptr [rax+rax+00h]
0x1802da901  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da908  mov     rcx, rax
0x1802da90b  test    rax, rax
0x1802da90e  jz      short loc_1802DA92F
0x1802da910  mov     rax, [rax]
0x1802da913  mov     edx, 7F0h
0x1802da918  mov     rax, [rax+8]
0x1802da91c  call    cs:__guard_dispatch_icall_fptr
0x1802da922  test    eax, eax
0x1802da924  jz      short loc_1802DA92F
0x1802da926  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da92d  jmp     short loc_1802DA93D
0x1802da92f  lea     rcx, qword_1803CE250; this
0x1802da936  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da93d  cmp     byte ptr [rcx+8], 0
0x1802da941  jz      short loc_1802DA964
0x1802da943  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802da948  cmp     [rax+7CCh], ebx
0x1802da94e  jz      short loc_1802DA964
0x1802da950  mov     r9d, ebx; int
0x1802da953  mov     r8d, 6Ch ; 'l'; int
0x1802da959  mov     rdx, r12; char *
0x1802da95c  mov     rcx, rax; this
0x1802da95f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802da964  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802da96b  jb      loc_1802DABE9
0x1802da971  mov     edx, 0Dh
0x1802da976  jmp     loc_1802DABCB
0x1802da97b  mov     rax, [rdi]
0x1802da97e  lea     r8, [rsp+88h+arg_0]
0x1802da986  lea     rdx, MF_MD_FSDKTYPE
0x1802da98d  mov     [rsp+88h+arg_0], 0
0x1802da998  mov     rcx, rdi
0x1802da99b  mov     rax, [rax+38h]
0x1802da99f  call    cs:__guard_dispatch_icall_fptr
0x1802da9a5  mov     ebx, eax
0x1802da9a7  test    eax, eax
0x1802da9a9  jns     loc_1802DAA41
0x1802da9af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da9b6  test    rcx, rcx
0x1802da9b9  jnz     short loc_1802DAA03
0x1802da9bb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802da9c2  nop     dword ptr [rax+rax+00h]
0x1802da9c7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da9ce  mov     rcx, rax
0x1802da9d1  test    rax, rax
0x1802da9d4  jz      short loc_1802DA9F5
0x1802da9d6  mov     rax, [rax]
0x1802da9d9  mov     edx, 7F0h
0x1802da9de  mov     rax, [rax+8]
0x1802da9e2  call    cs:__guard_dispatch_icall_fptr
0x1802da9e8  test    eax, eax
0x1802da9ea  jz      short loc_1802DA9F5
0x1802da9ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802da9f3  jmp     short loc_1802DAA03
0x1802da9f5  lea     rcx, qword_1803CE250; this
0x1802da9fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802daa03  cmp     byte ptr [rcx+8], 0
0x1802daa07  jz      short loc_1802DAA2A
0x1802daa09  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802daa0e  cmp     [rax+7CCh], ebx
0x1802daa14  jz      short loc_1802DAA2A
0x1802daa16  mov     r9d, ebx; int
0x1802daa19  mov     r8d, 78h ; 'x'; int
0x1802daa1f  mov     rdx, r12; char *
0x1802daa22  mov     rcx, rax; this
0x1802daa25  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802daa2a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802daa31  jb      loc_1802DABE9
0x1802daa37  mov     edx, 0Eh
0x1802daa3c  jmp     loc_1802DABCB
0x1802daa41  movzx   eax, word ptr [rsp+88h+arg_0]
0x1802daa49  cmp     [rbp+0], ax
0x1802daa4d  jnz     loc_1802DAB01
0x1802daa53  mov     rdx, rbp; pvarSrc
0x1802daa56  mov     rcx, rsi; pvarDest
0x1802daa59  call    cs:__imp_PropVariantCopy
0x1802daa60  nop     dword ptr [rax+rax+00h]
0x1802daa65  mov     ebx, eax
0x1802daa67  test    eax, eax
0x1802daa69  jns     loc_1802DABE9
0x1802daa6f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802daa76  test    rcx, rcx
0x1802daa79  jnz     short loc_1802DAAC3
0x1802daa7b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802daa82  nop     dword ptr [rax+rax+00h]
0x1802daa87  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802daa8e  mov     rcx, rax
0x1802daa91  test    rax, rax
0x1802daa94  jz      short loc_1802DAAB5
0x1802daa96  mov     rax, [rax]
0x1802daa99  mov     edx, 7F0h
0x1802daa9e  mov     rax, [rax+8]
0x1802daaa2  call    cs:__guard_dispatch_icall_fptr
0x1802daaa8  test    eax, eax
0x1802daaaa  jz      short loc_1802DAAB5
0x1802daaac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802daab3  jmp     short loc_1802DAAC3
0x1802daab5  lea     rcx, qword_1803CE250; this
0x1802daabc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802daac3  cmp     byte ptr [rcx+8], 0
0x1802daac7  jz      short loc_1802DAAEA
0x1802daac9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802daace  cmp     [rax+7CCh], ebx
0x1802daad4  jz      short loc_1802DAAEA
0x1802daad6  mov     r9d, ebx; int
0x1802daad9  mov     r8d, 7Fh; int
0x1802daadf  mov     rdx, r12; char *
0x1802daae2  mov     rcx, rax; this
0x1802daae5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802daaea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802daaf1  jb      loc_1802DABE9
0x1802daaf7  mov     edx, 0Fh
0x1802daafc  jmp     loc_1802DABCB
0x1802dab01  movups  xmm0, cs:MF_MD_FSDKMULTI
0x1802dab08  lea     rax, [rsp+88h+var_58]
0x1802dab0d  mov     r8, rsi; struct tagPROPVARIANT *
0x1802dab10  movups  xmm1, cs:MF_MD_FSDKTYPE
0x1802dab17  lea     r9, [rsp+88h+var_48]; struct _GUID
0x1802dab1c  mov     [rsp+88h+var_68], rax; struct _GUID
0x1802dab21  mov     rdx, r14; struct tagPROPVARIANT *
0x1802dab24  mov     rcx, rdi; this
0x1802dab27  movdqu  xmmword ptr [rsp+88h+var_58.Data1], xmm0
0x1802dab2d  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm1
0x1802dab33  call    ?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z; CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)
0x1802dab38  mov     ebx, eax
0x1802dab3a  test    eax, eax
0x1802dab3c  jns     loc_1802DABE9
0x1802dab42  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dab49  test    rcx, rcx
0x1802dab4c  jnz     short loc_1802DAB96
0x1802dab4e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802dab55  nop     dword ptr [rax+rax+00h]
0x1802dab5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dab61  mov     rcx, rax
0x1802dab64  test    rax, rax
0x1802dab67  jz      short loc_1802DAB88
0x1802dab69  mov     rax, [rax]
0x1802dab6c  mov     edx, 7F0h
0x1802dab71  mov     rax, [rax+8]
0x1802dab75  call    cs:__guard_dispatch_icall_fptr
0x1802dab7b  test    eax, eax
0x1802dab7d  jz      short loc_1802DAB88
0x1802dab7f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
