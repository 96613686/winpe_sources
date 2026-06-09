# CMFPropVariant::CreateString(ushort,void const *)

- ea: `0x18000faf4`
- end: `0x18001003e`
- name: `?CreateString@CMFPropVariant@@QEAAJGPEBX@Z`
- size: `1354`
- prototype: `int(CMFPropVariant *__hidden this, unsigned __int16, const void *)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180047880`
- `0x18004b900`
- `0x180055d04`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000faf4`
- `0x18001a330`
- `0x18001c280`
- `0x180022064`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff62`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000fd1d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000fd1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fc29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fc29`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ff3a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ff3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000fb77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000fc63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000fd69`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000fdef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000feb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ff8b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000fb77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000fc63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000fd69`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000fdef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000feb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ff8b`

## string_xrefs

- `0x18000fb4b`: `CMFPropVariant::CreateString`
- `0x18000fc09`: `CMFPropVariant::CreateString`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::CreateString(CMFPropVariant *this, __int16 a2, const CHAR *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 *v8; // rcx
  signed int v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  _WORD *v14; // rax
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  signed int LastError; // eax
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  BSTR v29; // rax
  signed int v30; // eax
  __int64 v31; // rdx
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  WCHAR *lpWideCharStr; // [rsp+20h] [rbp-10h]
  unsigned int v37; // [rsp+60h] [rbp+30h]
  char v38; // [rsp+68h] [rbp+38h] BYREF

  *(_WORD *)this = a2;
  if ( a2 == 30 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
  }
  else
  {
    if ( a2 != 31 && a2 != 8 )
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1854);
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
      v9 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v8 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::CreateString", 1854, -2147024809);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_83;
      v12 = 123;
      goto LABEL_82;
    }
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)&a3[2 * v6] );
  }
  if ( (unsigned __int16)(a2 - 30) <= 1u )
  {
    v37 = 2 * v6 + 2;
    *((_QWORD *)this + 1) = CoTaskMemAlloc(v37);
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1861);
    v14 = (_WORD *)*((_QWORD *)this + 1);
    if ( !v14 )
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      v9 = -2147024882;
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
        if ( *((_DWORD *)v17 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v17, "CMFPropVariant::CreateString", 1861, -2147024882);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_83;
      v12 = 124;
LABEL_82:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, this, v9);
LABEL_83:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
      return (unsigned int)v9;
    }
    *v14 = 0;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
    if ( a2 == 30 )
    {
      lpWideCharStr = (WCHAR *)*((_QWORD *)this + 1);
      v9 = 0;
      *(_WORD *)this = 31;
      if ( !MultiByteToWideChar(0, 0, a3, -1, lpWideCharStr, v37 >> 1) )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1881);
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( v9 >= 0 )
        {
          v9 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
            CallStackTracing::s_wpInstance = v23;
            if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
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
            v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)v24 + 499) != -2147418113 )
              CallStackContext::TraceFailure(v24, "CMFPropVariant::CreateString", 1882, -2147418113);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_83;
          v12 = 126;
        }
        else
        {
          if ( !CallStackTracing::s_wpInstance )
          {
            v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
            CallStackTracing::s_wpInstance = v21;
            if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
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
            v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)v22 + 499) != v9 )
              CallStackContext::TraceFailure(v22, "CMFPropVariant::CreateString", 1881, v9);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_83;
          v12 = 125;
        }
        goto LABEL_82;
      }
      return (unsigned int)v9;
    }
    if ( a2 == 31 )
    {
      v9 = StringCchCopyW(*((unsigned __int16 **)this + 1), (unsigned __int64)v37 >> 1, (const unsigned __int16 *)a3);
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1888);
      if ( v9 >= 0 )
        goto LABEL_83;
      v26 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
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
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != v9 )
          CallStackContext::TraceFailure(v28, "CMFPropVariant::CreateString", 1888, v9);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_83;
      v12 = 127;
      goto LABEL_82;
    }
  }
  v9 = 0;
  v29 = SysAllocString((const OLECHAR *)a3);
  *((_QWORD *)this + 1) = v29;
  if ( !v29 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1895);
    v30 = GetLastError();
    v9 = v30;
    if ( v30 > 0 )
      v9 = (unsigned __int16)v30 | 0x80070000;
    if ( v9 >= 0 )
      goto LABEL_83;
    v32 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
      CallStackTracing::s_wpInstance = v33;
      if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
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
      if ( *((_DWORD *)v34 + 499) != v9 )
        CallStackContext::TraceFailure(v34, "CMFPropVariant::CreateString", 1895, v9);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v12 = 128;
    goto LABEL_82;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000faf4  mov     [rsp-28h+arg_10], rbx
0x18000faf9  mov     [rsp-28h+arg_18], rsi
0x18000fafe  push    rbp
0x18000faff  push    rdi
0x18000fb00  push    r12
0x18000fb02  push    r13
0x18000fb04  push    r15
0x18000fb06  mov     rbp, rsp
0x18000fb09  sub     rsp, 30h
0x18000fb0d  mov     [rcx], dx
0x18000fb10  mov     r12, r8
0x18000fb13  movzx   ebx, dx
0x18000fb16  mov     r15, rcx
0x18000fb19  mov     eax, 1Fh
0x18000fb1e  cmp     dx, 1Eh
0x18000fb22  jnz     short loc_18000FB38
0x18000fb24  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000fb28  xor     edi, edi
0x18000fb2a  inc     rdx
0x18000fb2d  cmp     [r8+rdx], dil
0x18000fb31  jnz     short loc_18000FB2A
0x18000fb33  jmp     loc_18000FC06
0x18000fb38  cmp     bx, ax
0x18000fb3b  jz      loc_18000FBF6
0x18000fb41  cmp     bx, 8
0x18000fb45  jz      loc_18000FBF6
0x18000fb4b  lea     rsi, aCmfpropvariant_7; "CMFPropVariant::CreateString"
0x18000fb52  mov     r8d, 73Eh; int
0x18000fb58  mov     rdx, rsi; char *
0x18000fb5b  lea     rcx, [rbp+arg_8]; this
0x18000fb5f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000fb64  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fb6b  xor     edi, edi
0x18000fb6d  mov     ebx, 80070057h
0x18000fb72  test    rcx, rcx
0x18000fb75  jnz     short loc_18000FBB8
0x18000fb77  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000fb7d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fb84  mov     rcx, rax
0x18000fb87  test    rax, rax
0x18000fb8a  jz      short loc_18000FBAA
0x18000fb8c  mov     rax, [rax]
0x18000fb8f  mov     edx, 7F0h
0x18000fb94  mov     rax, [rax+8]
0x18000fb98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb9d  test    eax, eax
0x18000fb9f  jz      short loc_18000FBAA
0x18000fba1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fba8  jmp     short loc_18000FBB8
0x18000fbaa  lea     rcx, qword_180069A90; this
0x18000fbb1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fbb8  cmp     [rcx+8], dil
0x18000fbbc  jz      short loc_18000FBDF
0x18000fbbe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000fbc3  cmp     [rax+7CCh], ebx
0x18000fbc9  jz      short loc_18000FBDF
0x18000fbcb  mov     r9d, ebx; int
0x18000fbce  mov     r8d, 73Eh; int
0x18000fbd4  mov     rdx, rsi; char *
0x18000fbd7  mov     rcx, rax; this
0x18000fbda  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000fbdf  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000fbe4  cmp     al, 1
0x18000fbe6  jb      loc_18001001C
0x18000fbec  mov     edx, 7Bh ; '{'
0x18000fbf1  jmp     loc_18000FFFE
0x18000fbf6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000fbfa  xor     edi, edi
0x18000fbfc  inc     rdx
0x18000fbff  cmp     [r8+rdx*2], di
0x18000fc04  jnz     short loc_18000FBFC
0x18000fc06  lea     eax, [rbx-1Eh]
0x18000fc09  lea     rsi, aCmfpropvariant_7; "CMFPropVariant::CreateString"
0x18000fc10  cmp     ax, 1
0x18000fc14  ja      loc_18000FF35
0x18000fc1a  lea     edx, ds:2[rdx*2]
0x18000fc21  mov     ecx, edx; cb
0x18000fc23  mov     [rbp+arg_0], edx
0x18000fc26  mov     r13d, edx
0x18000fc29  call    cs:__imp_CoTaskMemAlloc
0x18000fc2f  mov     r8d, 745h; int
0x18000fc35  lea     rcx, [rbp+arg_8]; this
0x18000fc39  mov     rdx, rsi; char *
0x18000fc3c  mov     [r15+8], rax
0x18000fc40  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000fc45  mov     rax, [r15+8]
0x18000fc49  test    rax, rax
0x18000fc4c  jnz     loc_18000FCE2
0x18000fc52  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fc59  mov     ebx, 8007000Eh
0x18000fc5e  test    rcx, rcx
0x18000fc61  jnz     short loc_18000FCA4
0x18000fc63  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000fc69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fc70  mov     rcx, rax
0x18000fc73  test    rax, rax
0x18000fc76  jz      short loc_18000FC96
0x18000fc78  mov     rax, [rax]
0x18000fc7b  mov     edx, 7F0h
0x18000fc80  mov     rax, [rax+8]
0x18000fc84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc89  test    eax, eax
0x18000fc8b  jz      short loc_18000FC96
0x18000fc8d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fc94  jmp     short loc_18000FCA4
0x18000fc96  lea     rcx, qword_180069A90; this
0x18000fc9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fca4  cmp     [rcx+8], dil
0x18000fca8  jz      short loc_18000FCCB
0x18000fcaa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000fcaf  cmp     [rax+7CCh], ebx
0x18000fcb5  jz      short loc_18000FCCB
0x18000fcb7  mov     r9d, ebx; int
0x18000fcba  mov     r8d, 745h; int
0x18000fcc0  mov     rdx, rsi; char *
0x18000fcc3  mov     rcx, rax; this
0x18000fcc6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000fccb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000fcd0  cmp     al, 1
0x18000fcd2  jb      loc_18001001C
0x18000fcd8  mov     edx, 7Ch ; '|'
0x18000fcdd  jmp     loc_18000FFFE
0x18000fce2  lea     rcx, [rbp+arg_8]; this
0x18000fce6  mov     [rax], di
0x18000fce9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000fcee  cmp     bx, 1Eh
0x18000fcf2  jnz     loc_18000FE6E
0x18000fcf8  mov     eax, [rbp+arg_0]
0x18000fcfb  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000fcff  shr     eax, 1
0x18000fd01  mov     r8, r12; lpMultiByteStr
0x18000fd04  mov     [rsp+30h+cchWideChar], eax; cchWideChar
0x18000fd08  xor     edx, edx; dwFlags
0x18000fd0a  mov     rax, [r15+8]
0x18000fd0e  xor     ecx, ecx; CodePage
0x18000fd10  mov     [rsp+30h+lpWideCharStr], rax; lpWideCharStr
0x18000fd15  mov     ebx, edi
0x18000fd17  mov     word ptr [r15], 1Fh
0x18000fd1d  call    cs:__imp_MultiByteToWideChar
0x18000fd23  test    eax, eax
0x18000fd25  jnz     loc_180010025
0x18000fd2b  mov     r12d, 759h
0x18000fd31  lea     rcx, [rbp+arg_8]; this
0x18000fd35  mov     r8d, r12d; int
0x18000fd38  mov     rdx, rsi; char *
0x18000fd3b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000fd40  call    cs:__imp_GetLastError
0x18000fd46  mov     ebx, eax
0x18000fd48  test    eax, eax
0x18000fd4a  jle     short loc_18000FD55
0x18000fd4c  movzx   ebx, ax
0x18000fd4f  or      ebx, 80070000h
0x18000fd55  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fd5c  test    ebx, ebx
0x18000fd5e  jns     loc_18000FDE5
0x18000fd64  test    rcx, rcx
0x18000fd67  jnz     short loc_18000FDAA
0x18000fd69  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000fd6f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fd76  mov     rcx, rax
0x18000fd79  test    rax, rax
0x18000fd7c  jz      short loc_18000FD9C
0x18000fd7e  mov     rax, [rax]
0x18000fd81  mov     edx, 7F0h
0x18000fd86  mov     rax, [rax+8]
0x18000fd8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd8f  test    eax, eax
0x18000fd91  jz      short loc_18000FD9C
0x18000fd93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fd9a  jmp     short loc_18000FDAA
0x18000fd9c  lea     rcx, qword_180069A90; this
0x18000fda3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fdaa  cmp     [rcx+8], dil
0x18000fdae  jz      short loc_18000FDCE
0x18000fdb0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000fdb5  cmp     [rax+7CCh], ebx
0x18000fdbb  jz      short loc_18000FDCE
0x18000fdbd  mov     r9d, ebx; int
0x18000fdc0  mov     r8d, r12d; int
0x18000fdc3  mov     rdx, rsi; char *
0x18000fdc6  mov     rcx, rax; this
0x18000fdc9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000fdce  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000fdd3  cmp     al, 1
0x18000fdd5  jb      loc_18001001C
0x18000fddb  mov     edx, 7Dh ; '}'
0x18000fde0  jmp     loc_18000FFFE
0x18000fde5  mov     ebx, 8000FFFFh
0x18000fdea  test    rcx, rcx
0x18000fded  jnz     short loc_18000FE30
0x18000fdef  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000fdf5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fdfc  mov     rcx, rax
0x18000fdff  test    rax, rax
0x18000fe02  jz      short loc_18000FE22
0x18000fe04  mov     rax, [rax]
0x18000fe07  mov     edx, 7F0h
0x18000fe0c  mov     rax, [rax+8]
0x18000fe10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe15  test    eax, eax
0x18000fe17  jz      short loc_18000FE22
0x18000fe19  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fe20  jmp     short loc_18000FE30
0x18000fe22  lea     rcx, qword_180069A90; this
0x18000fe29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fe30  cmp     [rcx+8], dil
0x18000fe34  jz      short loc_18000FE57
0x18000fe36  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000fe3b  cmp     [rax+7CCh], ebx
0x18000fe41  jz      short loc_18000FE57
0x18000fe43  mov     r9d, ebx; int
0x18000fe46  mov     r8d, 75Ah; int
0x18000fe4c  mov     rdx, rsi; char *
0x18000fe4f  mov     rcx, rax; this
0x18000fe52  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000fe57  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000fe5c  cmp     al, 1
0x18000fe5e  jb      loc_18001001C
0x18000fe64  mov     edx, 7Eh ; '~'
0x18000fe69  jmp     loc_18000FFFE
0x18000fe6e  mov     eax, 1Fh
0x18000fe73  cmp     bx, ax
0x18000fe76  jnz     loc_18000FF35
0x18000fe7c  mov     rcx, [r15+8]; unsigned __int16 *
0x18000fe80  mov     r8, r12; unsigned __int16 *
0x18000fe83  shr     r13, 1
0x18000fe86  mov     rdx, r13; unsigned __int64
0x18000fe89  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fe8e  mov     r12d, 760h
0x18000fe94  lea     rcx, [rbp+arg_8]; this
0x18000fe98  mov     r8d, r12d; int
0x18000fe9b  mov     rdx, rsi; char *
0x18000fe9e  mov     ebx, eax
0x18000fea0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000fea5  test    ebx, ebx
0x18000fea7  jns     loc_18001001C
0x18000fead  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000feb4  test    rcx, rcx
0x18000feb7  jnz     short loc_18000FEFA
0x18000feb9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000febf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fec6  mov     rcx, rax
0x18000fec9  test    rax, rax
0x18000fecc  jz      short loc_18000FEEC
0x18000fece  mov     rax, [rax]
0x18000fed1  mov     edx, 7F0h
0x18000fed6  mov     rax, [rax+8]
0x18000feda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fedf  test    eax, eax
0x18000fee1  jz      short loc_18000FEEC
0x18000fee3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000feea  jmp     short loc_18000FEFA
0x18000feec  lea     rcx, qword_180069A90; this
0x18000fef3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000fefa  cmp     [rcx+8], dil
0x18000fefe  jz      short loc_18000FF1E
0x18000ff00  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000ff05  cmp     [rax+7CCh], ebx
0x18000ff0b  jz      short loc_18000FF1E
0x18000ff0d  mov     r9d, ebx; int
0x18000ff10  mov     r8d, r12d; int
0x18000ff13  mov     rdx, rsi; char *
0x18000ff16  mov     rcx, rax; this
0x18000ff19  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000ff1e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000ff23  cmp     al, 1
0x18000ff25  jb      loc_18001001C
0x18000ff2b  mov     edx, 7Fh
0x18000ff30  jmp     loc_18000FFFE
0x18000ff35  mov     rcx, r12; psz
0x18000ff38  mov     ebx, edi
0x18000ff3a  call    cs:__imp_SysAllocString
0x18000ff40  mov     [r15+8], rax
0x18000ff44  test    rax, rax
0x18000ff47  jnz     loc_180010025
0x18000ff4d  mov     r12d, 767h
0x18000ff53  lea     rcx, [rbp+arg_8]; this
0x18000ff57  mov     r8d, r12d; int
0x18000ff5a  mov     rdx, rsi; char *
0x18000ff5d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000ff62  call    cs:__imp_GetLastError
0x18000ff68  mov     ebx, eax
0x18000ff6a  test    eax, eax
0x18000ff6c  jle     short loc_18000FF77
0x18000ff6e  movzx   ebx, ax
0x18000ff71  or      ebx, 80070000h
0x18000ff77  test    ebx, ebx
0x18000ff79  jns     loc_18001001C
0x18000ff7f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ff86  test    rcx, rcx
0x18000ff89  jnz     short loc_18000FFCC
0x18000ff8b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000ff91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ff98  mov     rcx, rax
0x18000ff9b  test    rax, rax
0x18000ff9e  jz      short loc_18000FFBE
0x18000ffa0  mov     rax, [rax]
0x18000ffa3  mov     edx, 7F0h
0x18000ffa8  mov     rax, [rax+8]
0x18000ffac  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
