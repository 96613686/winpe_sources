# CMFPropVariant::Copy(tagPROPVARIANT const *)

- ea: `0x18019d300`
- end: `0x18019d7be`
- name: `?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z`
- size: `1214`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarDest, PROPVARIANT *pvarSrc)`
- caller_count: `12`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1801a1ae0`
- `0x1801a2940`
- `0x1801aa704`
- `0x1801d7a38`
- `0x18021cf40`
- `0x180245bc8`
- `0x1802467d4`
- `0x180277678`
- `0x180279370`
- `0x18029e6a4`
- `0x1802d85dc`
- `0x1802d96d0`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x18019d300`
- `0x180344ce4`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18019d3db`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18019d3db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18019d4ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18019d57c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18019d4ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18019d57c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019d348`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019d415`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019d4df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019d5c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019d666`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019d706`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019d348`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019d415`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019d4df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019d5c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019d666`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019d706`

## string_xrefs

- `0x18019d317`: `CMFPropVariant::Copy`
- `0x18019d3a9`: `CMFPropVariant::Copy`
- `0x18019d46a`: `CMFPropVariant::Copy`
- `0x18019d534`: `CMFPropVariant::Copy`
- `0x18019d61b`: `CMFPropVariant::Copy`
- `0x18019d6bb`: `CMFPropVariant::Copy`
- `0x18019d75b`: `CMFPropVariant::Copy`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::Copy(PROPVARIANT *pvarDest, PROPVARIANT *pvarSrc)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 *v7; // rdi
  HRESULT v8; // esi
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  CallStackTracing *v15; // rax
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  void *v18; // rax
  __int64 v19; // rcx
  _QWORD *v20; // r14
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  const void **v24; // rbp
  unsigned int i; // r12d
  void *v26; // rax
  __int64 v27; // rcx
  CallStackTracing *v28; // rax
  CallStackTracing *v29; // rcx
  struct CallStackContext *v30; // rax
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  _BYTE v36[56]; // [rsp+30h] [rbp-38h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v36, "CMFPropVariant::Copy", 181);
  if ( pvarDest == pvarSrc )
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v5, v4, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::Copy", 190, -2147467261);
    }
    if ( g_wppLevels )
    {
      v11 = 15;
LABEL_65:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        pvarDest,
        v8);
    }
  }
  else
  {
    v8 = PropVariantCopy(pvarDest, pvarSrc);
    if ( v8 >= 0 )
      goto LABEL_66;
    if ( *(_WORD *)pvarSrc == 4161 )
    {
      *(_WORD *)pvarDest = 4161;
      *((_DWORD *)pvarDest + 2) = *((_DWORD *)pvarSrc + 2);
      v18 = CoTaskMemAlloc(16LL * *((unsigned int *)pvarSrc + 2));
      pvarDest[2] = v18;
      v20 = v18;
      if ( v18 )
      {
        v24 = (const void **)pvarSrc[2];
        v8 = 0;
        for ( i = 0; *((_DWORD *)pvarSrc + 2) > i; ++i )
        {
          *(_DWORD *)v20 = *(_DWORD *)v24;
          v26 = CoTaskMemAlloc(*(unsigned int *)v24);
          v20[1] = v26;
          if ( !v26 )
          {
            v8 = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v27, v12, v14);
              CallStackTracing::s_wpInstance = v28;
              if ( !v28
                || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
              {
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            v29 = CallStackTracing::s_wpInstance;
            if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
            {
              v30 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
              if ( *((_DWORD *)v30 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v30, "CMFPropVariant::Copy", 231, -2147024882);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                17,
                &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
                pvarDest,
                -2147024882);
            if ( !CallStackTracing::s_wpInstance )
            {
              v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v29, v12, v14);
              CallStackTracing::s_wpInstance = v31;
              if ( !v31
                || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
              {
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            v16 = CallStackTracing::s_wpInstance;
            if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
            {
              v32 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
              if ( *((_DWORD *)v32 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v32, "CMFPropVariant::Copy", 236, -2147024882);
            }
            if ( g_wppLevels )
            {
              v23 = 18;
              goto LABEL_55;
            }
            goto LABEL_56;
          }
          memcpy_0(v26, v24[1], *(unsigned int *)v24);
          v20 += 2;
          v24 += 2;
        }
        goto LABEL_66;
      }
      v8 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v19, v12, v14);
        CallStackTracing::s_wpInstance = v21;
        if ( !v21 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
      v16 = CallStackTracing::s_wpInstance;
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v22 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v22, "CMFPropVariant::Copy", 224, -2147024882);
      }
      if ( g_wppLevels )
      {
        v23 = 16;
LABEL_55:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v23,
          &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
          pvarDest,
          -2147024882);
      }
    }
    else
    {
      v8 = -1072875800;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v13, v12, v14);
        CallStackTracing::s_wpInstance = v15;
        if ( !v15 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
      v16 = CallStackTracing::s_wpInstance;
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v17 + 499) != -1072875800 )
          CallStackContext::TraceFailure(v17, "CMFPropVariant::Copy", 241, -1072875800);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
          pvarDest,
          -1072875800);
    }
LABEL_56:
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v16, v12, v14);
      CallStackTracing::s_wpInstance = v33;
      if ( !v33 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v34 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v34 + 499) != v8 )
        CallStackContext::TraceFailure(v34, "CMFPropVariant::Copy", 247, v8);
    }
    if ( g_wppLevels )
    {
      v11 = 20;
      goto LABEL_65;
    }
  }
LABEL_66:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v36);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18019d300  mov     [rsp+arg_10], rbp
0x18019d305  push    rsi
0x18019d306  push    rdi
0x18019d307  push    r12
0x18019d309  push    r14
0x18019d30b  push    r15
0x18019d30d  sub     rsp, 40h
0x18019d311  mov     rdi, rdx
0x18019d314  mov     r15, rcx
0x18019d317  lea     rdx, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x18019d31e  mov     r8d, 0B5h; int
0x18019d324  lea     rcx, [rsp+68h+var_38]; this
0x18019d329  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18019d32e  cmp     r15, rdi
0x18019d331  jnz     loc_18019D3D5
0x18019d337  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d33e  mov     esi, 80004003h
0x18019d343  test    rdi, rdi
0x18019d346  jnz     short loc_18019D390
0x18019d348  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019d34f  nop     dword ptr [rax+rax+00h]
0x18019d354  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d35b  mov     rcx, rax
0x18019d35e  test    rax, rax
0x18019d361  jz      short loc_18019D382
0x18019d363  mov     rax, [rax]
0x18019d366  mov     edx, 7F0h
0x18019d36b  mov     rax, [rax+8]
0x18019d36f  call    cs:__guard_dispatch_icall_fptr
0x18019d375  test    eax, eax
0x18019d377  jz      short loc_18019D382
0x18019d379  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d380  jmp     short loc_18019D390
0x18019d382  lea     rdi, qword_1803CE250
0x18019d389  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d390  cmp     byte ptr [rdi+8], 0
0x18019d394  jz      short loc_18019D3BE
0x18019d396  mov     rcx, rdi; this
0x18019d399  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019d39e  cmp     [rax+7CCh], esi
0x18019d3a4  jz      short loc_18019D3BE
0x18019d3a6  mov     r9d, esi; int
0x18019d3a9  lea     rdx, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x18019d3b0  mov     r8d, 0BEh; int
0x18019d3b6  mov     rcx, rax; this
0x18019d3b9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019d3be  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019d3c5  jb      loc_18019D79C
0x18019d3cb  mov     edx, 0Fh
0x18019d3d0  jmp     loc_18019D77E
0x18019d3d5  mov     rdx, rdi; pvarSrc
0x18019d3d8  mov     rcx, r15; pvarDest
0x18019d3db  call    cs:__imp_PropVariantCopy
0x18019d3e2  nop     dword ptr [rax+rax+00h]
0x18019d3e7  mov     esi, eax
0x18019d3e9  test    eax, eax
0x18019d3eb  jns     loc_18019D79C
0x18019d3f1  mov     eax, 1041h
0x18019d3f6  cmp     [rdi], ax
0x18019d3f9  jz      loc_18019D49A
0x18019d3ff  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d407  lea     rdi, qword_1803CE250
0x18019d40e  mov     esi, 0C00D36E8h
0x18019d413  jnz     short loc_18019D44D
0x18019d415  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019d41c  nop     dword ptr [rax+rax+00h]
0x18019d421  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d428  mov     rcx, rax
0x18019d42b  test    rax, rax
0x18019d42e  jz      short loc_18019D446
0x18019d430  mov     rax, [rax]
0x18019d433  mov     edx, 7F0h
0x18019d438  mov     rax, [rax+8]
0x18019d43c  call    cs:__guard_dispatch_icall_fptr
0x18019d442  test    eax, eax
0x18019d444  jnz     short loc_18019D44D
0x18019d446  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d44d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18019d454  cmp     byte ptr [rcx+8], 0
0x18019d458  jz      short loc_18019D47F
0x18019d45a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019d45f  cmp     [rax+7CCh], esi
0x18019d465  jz      short loc_18019D47F
0x18019d467  mov     r9d, esi; int
0x18019d46a  lea     rdx, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x18019d471  mov     r8d, 0F1h; int
0x18019d477  mov     rcx, rax; this
0x18019d47a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019d47f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019d486  jb      loc_18019D6FC
0x18019d48c  mov     edx, 13h
0x18019d491  mov     [rsp+68h+var_48], esi
0x18019d495  jmp     loc_18019D6E2
0x18019d49a  mov     [r15], ax
0x18019d49e  mov     eax, [rdi+8]
0x18019d4a1  mov     [r15+8], eax
0x18019d4a5  mov     ecx, [rdi+8]
0x18019d4a8  shl     rcx, 4; cb
0x18019d4ac  call    cs:__imp_CoTaskMemAlloc
0x18019d4b3  nop     dword ptr [rax+rax+00h]
0x18019d4b8  mov     [r15+10h], rax
0x18019d4bc  mov     r14, rax
0x18019d4bf  test    rax, rax
0x18019d4c2  jnz     loc_18019D560
0x18019d4c8  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d4cf  lea     rdi, qword_1803CE250
0x18019d4d6  mov     ebp, 8007000Eh
0x18019d4db  mov     esi, ebp
0x18019d4dd  jnz     short loc_18019D517
0x18019d4df  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019d4e6  nop     dword ptr [rax+rax+00h]
0x18019d4eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d4f2  mov     rcx, rax
0x18019d4f5  test    rax, rax
0x18019d4f8  jz      short loc_18019D510
0x18019d4fa  mov     rax, [rax]
0x18019d4fd  mov     edx, 7F0h
0x18019d502  mov     rax, [rax+8]
0x18019d506  call    cs:__guard_dispatch_icall_fptr
0x18019d50c  test    eax, eax
0x18019d50e  jnz     short loc_18019D517
0x18019d510  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d517  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18019d51e  cmp     byte ptr [rcx+8], 0
0x18019d522  jz      short loc_18019D549
0x18019d524  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019d529  cmp     [rax+7CCh], ebp
0x18019d52f  jz      short loc_18019D549
0x18019d531  mov     r9d, ebp; int
0x18019d534  lea     rdx, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x18019d53b  mov     r8d, 0E0h; int
0x18019d541  mov     rcx, rax; this
0x18019d544  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019d549  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019d550  jb      loc_18019D6FC
0x18019d556  mov     edx, 10h
0x18019d55b  jmp     loc_18019D6DE
0x18019d560  mov     rbp, [rdi+10h]
0x18019d564  xor     esi, esi
0x18019d566  xor     r12d, r12d
0x18019d569  cmp     [rdi+8], r12d
0x18019d56d  jbe     loc_18019D79C
0x18019d573  mov     eax, [rbp+0]
0x18019d576  mov     [r14], eax
0x18019d579  mov     ecx, [rbp+0]; cb
0x18019d57c  call    cs:__imp_CoTaskMemAlloc
0x18019d583  nop     dword ptr [rax+rax+00h]
0x18019d588  mov     [r14+8], rax
0x18019d58c  test    rax, rax
0x18019d58f  jz      short loc_18019D5AE
0x18019d591  mov     r8d, [rbp+0]; Size
0x18019d595  mov     rcx, rax; void *
0x18019d598  mov     rdx, [rbp+8]; Src
0x18019d59c  call    memcpy_0
0x18019d5a1  add     r14, 10h
0x18019d5a5  add     rbp, 10h
0x18019d5a9  inc     r12d
0x18019d5ac  jmp     short loc_18019D569
0x18019d5ae  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d5b6  lea     rdi, qword_1803CE250
0x18019d5bd  mov     ebp, 8007000Eh
0x18019d5c2  mov     esi, ebp
0x18019d5c4  jnz     short loc_18019D5FE
0x18019d5c6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019d5cd  nop     dword ptr [rax+rax+00h]
0x18019d5d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d5d9  mov     rcx, rax
0x18019d5dc  test    rax, rax
0x18019d5df  jz      short loc_18019D5F7
0x18019d5e1  mov     rax, [rax]
0x18019d5e4  mov     edx, 7F0h
0x18019d5e9  mov     rax, [rax+8]
0x18019d5ed  call    cs:__guard_dispatch_icall_fptr
0x18019d5f3  test    eax, eax
0x18019d5f5  jnz     short loc_18019D5FE
0x18019d5f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d5fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18019d605  cmp     byte ptr [rcx+8], 0
0x18019d609  jz      short loc_18019D630
0x18019d60b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019d610  cmp     [rax+7CCh], ebp
0x18019d616  jz      short loc_18019D630
0x18019d618  mov     r9d, ebp; int
0x18019d61b  lea     rdx, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x18019d622  mov     r8d, 0E7h; int
0x18019d628  mov     rcx, rax; this
0x18019d62b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019d630  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019d637  jb      short loc_18019D65C
0x18019d639  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d640  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x18019d647  mov     edx, 11h
0x18019d64c  mov     [rsp+68h+var_48], ebp
0x18019d650  mov     r9, r15
0x18019d653  mov     rcx, [rcx+10h]
0x18019d657  call    WPP_SF_qD
0x18019d65c  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d664  jnz     short loc_18019D69E
0x18019d666  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019d66d  nop     dword ptr [rax+rax+00h]
0x18019d672  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d679  mov     rcx, rax
0x18019d67c  test    rax, rax
0x18019d67f  jz      short loc_18019D697
0x18019d681  mov     rax, [rax]
0x18019d684  mov     edx, 7F0h
0x18019d689  mov     rax, [rax+8]
0x18019d68d  call    cs:__guard_dispatch_icall_fptr
0x18019d693  test    eax, eax
0x18019d695  jnz     short loc_18019D69E
0x18019d697  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d69e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18019d6a5  cmp     byte ptr [rcx+8], 0
0x18019d6a9  jz      short loc_18019D6D0
0x18019d6ab  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019d6b0  cmp     [rax+7CCh], ebp
0x18019d6b6  jz      short loc_18019D6D0
0x18019d6b8  mov     r9d, ebp; int
0x18019d6bb  lea     rdx, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x18019d6c2  mov     r8d, 0ECh; int
0x18019d6c8  mov     rcx, rax; this
0x18019d6cb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019d6d0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019d6d7  jb      short loc_18019D6FC
0x18019d6d9  mov     edx, 12h
0x18019d6de  mov     [rsp+68h+var_48], ebp
0x18019d6e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d6e9  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x18019d6f0  mov     r9, r15
0x18019d6f3  mov     rcx, [rcx+10h]
0x18019d6f7  call    WPP_SF_qD
0x18019d6fc  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d704  jnz     short loc_18019D73E
0x18019d706  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019d70d  nop     dword ptr [rax+rax+00h]
0x18019d712  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d719  mov     rcx, rax
0x18019d71c  test    rax, rax
0x18019d71f  jz      short loc_18019D737
0x18019d721  mov     rax, [rax]
0x18019d724  mov     edx, 7F0h
0x18019d729  mov     rax, [rax+8]
0x18019d72d  call    cs:__guard_dispatch_icall_fptr
0x18019d733  test    eax, eax
0x18019d735  jnz     short loc_18019D73E
0x18019d737  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18019d73e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18019d745  cmp     byte ptr [rcx+8], 0
0x18019d749  jz      short loc_18019D770
0x18019d74b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019d750  cmp     [rax+7CCh], esi
0x18019d756  jz      short loc_18019D770
0x18019d758  mov     r9d, esi; int
0x18019d75b  lea     rdx, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x18019d762  mov     r8d, 0F7h; int
0x18019d768  mov     rcx, rax; this
0x18019d76b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019d770  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019d777  jb      short loc_18019D79C
0x18019d779  mov     edx, 14h
0x18019d77e  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d785  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x18019d78c  mov     r9, r15
0x18019d78f  mov     [rsp+68h+var_48], esi
0x18019d793  mov     rcx, [rcx+10h]
0x18019d797  call    WPP_SF_qD
0x18019d79c  lea     rcx, [rsp+68h+var_38]; this
0x18019d7a1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18019d7a6  mov     rbp, [rsp+68h+arg_10]
0x18019d7ae  mov     eax, esi
0x18019d7b0  add     rsp, 40h
0x18019d7b4  pop     r15
0x18019d7b6  pop     r14
0x18019d7b8  pop     r12
0x18019d7ba  pop     rdi
0x18019d7bb  pop     rsi
0x18019d7bc  retn
```
