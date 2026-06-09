# CMFPropVariant::Copy(tagPROPVARIANT const *)

- ea: `0x180057904`
- end: `0x180057d84`
- name: `?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z`
- size: `1152`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarDest, PROPVARIANT *pvarSrc)`
- caller_count: `10`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000f4a0`
- `0x180015fe8`
- `0x180046fb0`
- `0x1800488b0`
- `0x180048db8`
- `0x18004a398`
- `0x18004b900`
- `0x18004d62c`
- `0x180055d04`
- `0x180057fe4`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x180057904`
- `0x1800594bc`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057a9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057b60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057a9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057b60`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800579d8`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800579d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005794c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057a0c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057acc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057ba2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057c3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057cd4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005794c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057a0c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057acc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057ba2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057c3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057cd4`

## string_xrefs

- `0x18005791b`: `CMFPropVariant::Copy`
- `0x1800579a6`: `CMFPropVariant::Copy`
- `0x180057a5a`: `CMFPropVariant::Copy`
- `0x180057b1a`: `CMFPropVariant::Copy`
- `0x180057bf0`: `CMFPropVariant::Copy`
- `0x180057c89`: `CMFPropVariant::Copy`
- `0x180057d22`: `CMFPropVariant::Copy`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::Copy(PROPVARIANT *pvarDest, PROPVARIANT *pvarSrc)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 *v6; // rdi
  HRESULT v7; // esi
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  BYTE *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  BYTE *v20; // r14
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  BYTE *pData; // r15
  unsigned int i; // ebp
  void *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  _BYTE v38[56]; // [rsp+30h] [rbp-38h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v38, "CMFPropVariant::Copy", 181);
  if ( pvarDest == pvarSrc )
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v5, v4);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::Copy", 190, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 15;
LABEL_65:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, pvarDest, v7);
    }
  }
  else
  {
    v7 = PropVariantCopy(pvarDest, pvarSrc);
    if ( v7 >= 0 )
      goto LABEL_66;
    if ( pvarSrc->vt == 4161 )
    {
      pvarDest->vt = 4161;
      pvarDest->lVal = pvarSrc->lVal;
      v17 = (BYTE *)CoTaskMemAlloc(16LL * pvarSrc->ulVal);
      pvarDest->bstrblobVal.pData = v17;
      v20 = v17;
      if ( v17 )
      {
        pData = pvarSrc->bstrblobVal.pData;
        v7 = 0;
        for ( i = 0; pvarSrc->lVal > i; ++i )
        {
          *(_DWORD *)v20 = *(_DWORD *)pData;
          v26 = CoTaskMemAlloc(*(unsigned int *)pData);
          *((_QWORD *)v20 + 1) = v26;
          if ( !v26 )
          {
            v7 = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v28, v27);
              CallStackTracing::s_wpInstance = v29;
              if ( !v29
                || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
              {
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
            {
              v30 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
              if ( *((_DWORD *)v30 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v30, "CMFPropVariant::Copy", 231, -2147024882);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              WPP_SF_qd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                17,
                WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
                pvarDest,
                -2147024882);
            if ( !CallStackTracing::s_wpInstance )
            {
              v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v32, v31);
              CallStackTracing::s_wpInstance = v33;
              if ( !v33
                || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
              {
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
            {
              v34 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
              if ( *((_DWORD *)v34 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v34, "CMFPropVariant::Copy", 236, -2147024882);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v23 = 18;
              goto LABEL_55;
            }
            goto LABEL_56;
          }
          memcpy_0(v26, *((const void **)pData + 1), *(unsigned int *)pData);
          v20 += 16;
          pData += 16;
        }
        goto LABEL_66;
      }
      v7 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v19, v18);
        CallStackTracing::s_wpInstance = v21;
        if ( !v21 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v22 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v22, "CMFPropVariant::Copy", 224, -2147024882);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v23 = 16;
LABEL_55:
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v23,
          WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
          pvarDest,
          -2147024882);
      }
    }
    else
    {
      v7 = -1072875800;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v12, v11);
        CallStackTracing::s_wpInstance = v13;
        if ( !v13 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v14 + 499) != -1072875800 )
          CallStackContext::TraceFailure(v14, "CMFPropVariant::Copy", 241, -1072875800);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
          pvarDest,
          -1072875800);
    }
LABEL_56:
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v16, v15);
      CallStackTracing::s_wpInstance = v35;
      if ( !v35 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v36 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v36 + 499) != v7 )
        CallStackContext::TraceFailure(v36, "CMFPropVariant::Copy", 247, v7);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 20;
      goto LABEL_65;
    }
  }
LABEL_66:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v38);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180057904  mov     [rsp+arg_10], rbp
0x180057909  push    rsi
0x18005790a  push    rdi
0x18005790b  push    r12
0x18005790d  push    r14
0x18005790f  push    r15
0x180057911  sub     rsp, 40h
0x180057915  mov     rdi, rdx
0x180057918  mov     r12, rcx
0x18005791b  lea     rdx, aCmfpropvariant_9; "CMFPropVariant::Copy"
0x180057922  mov     r8d, 0B5h; int
0x180057928  lea     rcx, [rsp+68h+var_38]; this
0x18005792d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180057932  cmp     r12, rdi
0x180057935  jnz     loc_1800579D2
0x18005793b  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057942  mov     esi, 80004003h
0x180057947  test    rdi, rdi
0x18005794a  jnz     short loc_18005798D
0x18005794c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180057952  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057959  mov     rcx, rax
0x18005795c  test    rax, rax
0x18005795f  jz      short loc_18005797F
0x180057961  mov     rax, [rax]
0x180057964  mov     edx, 7F0h
0x180057969  mov     rax, [rax+8]
0x18005796d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057972  test    eax, eax
0x180057974  jz      short loc_18005797F
0x180057976  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005797d  jmp     short loc_18005798D
0x18005797f  lea     rdi, qword_180069A90
0x180057986  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18005798d  cmp     byte ptr [rdi+8], 0
0x180057991  jz      short loc_1800579BB
0x180057993  mov     rcx, rdi; this
0x180057996  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005799b  cmp     [rax+7CCh], esi
0x1800579a1  jz      short loc_1800579BB
0x1800579a3  mov     r9d, esi; int
0x1800579a6  lea     rdx, aCmfpropvariant_9; "CMFPropVariant::Copy"
0x1800579ad  mov     r8d, 0BEh; int
0x1800579b3  mov     rcx, rax; this
0x1800579b6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800579bb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800579c0  cmp     al, 1
0x1800579c2  jb      loc_180057D63
0x1800579c8  mov     edx, 0Fh
0x1800579cd  jmp     loc_180057D45
0x1800579d2  mov     rdx, rdi; pvarSrc
0x1800579d5  mov     rcx, r12; pvarDest
0x1800579d8  call    cs:__imp_PropVariantCopy
0x1800579de  mov     esi, eax
0x1800579e0  test    eax, eax
0x1800579e2  jns     loc_180057D63
0x1800579e8  mov     eax, 1041h
0x1800579ed  cmp     [rdi], ax
0x1800579f0  jz      loc_180057A8A
0x1800579f6  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x1800579fe  lea     rdi, qword_180069A90
0x180057a05  mov     esi, 0C00D36E8h
0x180057a0a  jnz     short loc_180057A3D
0x180057a0c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180057a12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057a19  mov     rcx, rax
0x180057a1c  test    rax, rax
0x180057a1f  jz      short loc_180057A36
0x180057a21  mov     rax, [rax]
0x180057a24  mov     edx, 7F0h
0x180057a29  mov     rax, [rax+8]
0x180057a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a32  test    eax, eax
0x180057a34  jnz     short loc_180057A3D
0x180057a36  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180057a3d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180057a44  cmp     byte ptr [rcx+8], 0
0x180057a48  jz      short loc_180057A6F
0x180057a4a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057a4f  cmp     [rax+7CCh], esi
0x180057a55  jz      short loc_180057A6F
0x180057a57  mov     r9d, esi; int
0x180057a5a  lea     rdx, aCmfpropvariant_9; "CMFPropVariant::Copy"
0x180057a61  mov     r8d, 0F1h; int
0x180057a67  mov     rcx, rax; this
0x180057a6a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180057a6f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180057a74  cmp     al, 1
0x180057a76  jb      loc_180057CCA
0x180057a7c  mov     edx, 13h
0x180057a81  mov     [rsp+68h+var_48], esi
0x180057a85  jmp     loc_180057CB0
0x180057a8a  mov     [r12], ax
0x180057a8f  mov     eax, [rdi+8]
0x180057a92  mov     [r12+8], eax
0x180057a97  mov     ecx, [rdi+8]
0x180057a9a  shl     rcx, 4; cb
0x180057a9e  call    cs:__imp_CoTaskMemAlloc
0x180057aa4  mov     [r12+10h], rax
0x180057aa9  mov     r14, rax
0x180057aac  test    rax, rax
0x180057aaf  jnz     loc_180057B46
0x180057ab5  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057abc  lea     rdi, qword_180069A90
0x180057ac3  mov     ebp, 8007000Eh
0x180057ac8  mov     esi, ebp
0x180057aca  jnz     short loc_180057AFD
0x180057acc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180057ad2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057ad9  mov     rcx, rax
0x180057adc  test    rax, rax
0x180057adf  jz      short loc_180057AF6
0x180057ae1  mov     rax, [rax]
0x180057ae4  mov     edx, 7F0h
0x180057ae9  mov     rax, [rax+8]
0x180057aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057af2  test    eax, eax
0x180057af4  jnz     short loc_180057AFD
0x180057af6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180057afd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180057b04  cmp     byte ptr [rcx+8], 0
0x180057b08  jz      short loc_180057B2F
0x180057b0a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057b0f  cmp     [rax+7CCh], ebp
0x180057b15  jz      short loc_180057B2F
0x180057b17  mov     r9d, ebp; int
0x180057b1a  lea     rdx, aCmfpropvariant_9; "CMFPropVariant::Copy"
0x180057b21  mov     r8d, 0E0h; int
0x180057b27  mov     rcx, rax; this
0x180057b2a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180057b2f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180057b34  cmp     al, 1
0x180057b36  jb      loc_180057CCA
0x180057b3c  mov     edx, 10h
0x180057b41  jmp     loc_180057CAC
0x180057b46  mov     r15, [rdi+10h]
0x180057b4a  xor     esi, esi
0x180057b4c  xor     ebp, ebp
0x180057b4e  cmp     [rdi+8], ebp
0x180057b51  jbe     loc_180057D63
0x180057b57  mov     eax, [r15]
0x180057b5a  mov     [r14], eax
0x180057b5d  mov     ecx, [r15]; cb
0x180057b60  call    cs:__imp_CoTaskMemAlloc
0x180057b66  mov     [r14+8], rax
0x180057b6a  test    rax, rax
0x180057b6d  jz      short loc_180057B8A
0x180057b6f  mov     r8d, [r15]; Size
0x180057b72  mov     rcx, rax; void *
0x180057b75  mov     rdx, [r15+8]; Src
0x180057b79  call    memcpy_0
0x180057b7e  add     r14, 10h
0x180057b82  add     r15, 10h
0x180057b86  inc     ebp
0x180057b88  jmp     short loc_180057B4E
0x180057b8a  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180057b92  lea     rdi, qword_180069A90
0x180057b99  mov     ebp, 8007000Eh
0x180057b9e  mov     esi, ebp
0x180057ba0  jnz     short loc_180057BD3
0x180057ba2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180057ba8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057baf  mov     rcx, rax
0x180057bb2  test    rax, rax
0x180057bb5  jz      short loc_180057BCC
0x180057bb7  mov     rax, [rax]
0x180057bba  mov     edx, 7F0h
0x180057bbf  mov     rax, [rax+8]
0x180057bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057bc8  test    eax, eax
0x180057bca  jnz     short loc_180057BD3
0x180057bcc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180057bd3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180057bda  cmp     byte ptr [rcx+8], 0
0x180057bde  jz      short loc_180057C05
0x180057be0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057be5  cmp     [rax+7CCh], ebp
0x180057beb  jz      short loc_180057C05
0x180057bed  mov     r9d, ebp; int
0x180057bf0  lea     rdx, aCmfpropvariant_9; "CMFPropVariant::Copy"
0x180057bf7  mov     r8d, 0E7h; int
0x180057bfd  mov     rcx, rax; this
0x180057c00  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180057c05  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180057c0a  cmp     al, 1
0x180057c0c  jb      short loc_180057C31
0x180057c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180057c15  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180057c1c  mov     edx, 11h
0x180057c21  mov     [rsp+68h+var_48], ebp
0x180057c25  mov     r9, r12
0x180057c28  mov     rcx, [rcx+10h]
0x180057c2c  call    WPP_SF_qd
0x180057c31  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180057c39  jnz     short loc_180057C6C
0x180057c3b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180057c41  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057c48  mov     rcx, rax
0x180057c4b  test    rax, rax
0x180057c4e  jz      short loc_180057C65
0x180057c50  mov     rax, [rax]
0x180057c53  mov     edx, 7F0h
0x180057c58  mov     rax, [rax+8]
0x180057c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c61  test    eax, eax
0x180057c63  jnz     short loc_180057C6C
0x180057c65  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180057c6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180057c73  cmp     byte ptr [rcx+8], 0
0x180057c77  jz      short loc_180057C9E
0x180057c79  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057c7e  cmp     [rax+7CCh], ebp
0x180057c84  jz      short loc_180057C9E
0x180057c86  mov     r9d, ebp; int
0x180057c89  lea     rdx, aCmfpropvariant_9; "CMFPropVariant::Copy"
0x180057c90  mov     r8d, 0ECh; int
0x180057c96  mov     rcx, rax; this
0x180057c99  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180057c9e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180057ca3  cmp     al, 1
0x180057ca5  jb      short loc_180057CCA
0x180057ca7  mov     edx, 12h
0x180057cac  mov     [rsp+68h+var_48], ebp
0x180057cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180057cb7  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180057cbe  mov     r9, r12
0x180057cc1  mov     rcx, [rcx+10h]
0x180057cc5  call    WPP_SF_qd
0x180057cca  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180057cd2  jnz     short loc_180057D05
0x180057cd4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180057cda  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057ce1  mov     rcx, rax
0x180057ce4  test    rax, rax
0x180057ce7  jz      short loc_180057CFE
0x180057ce9  mov     rax, [rax]
0x180057cec  mov     edx, 7F0h
0x180057cf1  mov     rax, [rax+8]
0x180057cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057cfa  test    eax, eax
0x180057cfc  jnz     short loc_180057D05
0x180057cfe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180057d05  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180057d0c  cmp     byte ptr [rcx+8], 0
0x180057d10  jz      short loc_180057D37
0x180057d12  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057d17  cmp     [rax+7CCh], esi
0x180057d1d  jz      short loc_180057D37
0x180057d1f  mov     r9d, esi; int
0x180057d22  lea     rdx, aCmfpropvariant_9; "CMFPropVariant::Copy"
0x180057d29  mov     r8d, 0F7h; int
0x180057d2f  mov     rcx, rax; this
0x180057d32  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180057d37  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180057d3c  cmp     al, 1
0x180057d3e  jb      short loc_180057D63
0x180057d40  mov     edx, 14h
0x180057d45  mov     rcx, cs:WPP_GLOBAL_Control
0x180057d4c  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180057d53  mov     r9, r12
0x180057d56  mov     [rsp+68h+var_48], esi
0x180057d5a  mov     rcx, [rcx+10h]
0x180057d5e  call    WPP_SF_qd
0x180057d63  lea     rcx, [rsp+68h+var_38]; this
0x180057d68  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180057d6d  mov     rbp, [rsp+68h+arg_10]
0x180057d75  mov     eax, esi
0x180057d77  add     rsp, 40h
0x180057d7b  pop     r15
0x180057d7d  pop     r14
0x180057d7f  pop     r12
0x180057d81  pop     rdi
0x180057d82  pop     rsi
0x180057d83  retn
```
