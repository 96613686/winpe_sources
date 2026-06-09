# CMFPropVariant::CreateString(ushort,void const *)

- ea: `0x1801a7850`
- end: `0x1801a7de3`
- name: `?CreateString@CMFPropVariant@@QEAAJGPEBX@Z`
- size: `1427`
- prototype: `int(CMFPropVariant *__hidden this, unsigned __int16, const void *)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18020b3d0`
- `0x180277678`
- `0x1802d96d0`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x18017d0d8`
- `0x1801a7850`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a7ab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a7cf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a7ab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a7cf9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1801a7a8d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1801a7a8d`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a7ccb`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a7ccb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a798c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a798c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a78d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a79cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a7ae5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a7b72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a7c43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a7d28`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a78d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a79cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a7ae5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a7b72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a7c43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a7d28`

## string_xrefs

- `0x1801a78a7`: `CMFPropVariant::CreateString`
- `0x1801a796c`: `CMFPropVariant::CreateString`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::CreateString(CMFPropVariant *this, __int16 a2, const CHAR *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 *v9; // rcx
  signed int v10; // ebx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  _WORD *v16; // rax
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  signed int LastError; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  BSTR v33; // rax
  signed int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  WCHAR *lpWideCharStr; // [rsp+20h] [rbp-10h]
  unsigned int v42; // [rsp+60h] [rbp+30h]
  char v43; // [rsp+68h] [rbp+38h] BYREF

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
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v43, "CMFPropVariant::CreateString", 1854);
      v9 = (__int64 *)CallStackTracing::s_wpInstance;
      v10 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v8);
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v9 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::CreateString", 1854, -2147024809);
      }
      if ( !g_wppLevels )
        goto LABEL_83;
      v13 = 123;
      goto LABEL_82;
    }
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)&a3[2 * v6] );
  }
  if ( (unsigned __int16)(a2 - 30) <= 1u )
  {
    v42 = 2 * v6 + 2;
    *((_QWORD *)this + 1) = CoTaskMemAlloc(v42);
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v43, "CMFPropVariant::CreateString", 1861);
    v16 = (_WORD *)*((_QWORD *)this + 1);
    if ( !v16 )
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
      v10 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v19, "CMFPropVariant::CreateString", 1861, -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_83;
      v13 = 124;
LABEL_82:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, this, v10);
LABEL_83:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v43);
      return (unsigned int)v10;
    }
    *v16 = 0;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v43);
    if ( a2 == 30 )
    {
      lpWideCharStr = (WCHAR *)*((_QWORD *)this + 1);
      v10 = 0;
      *(_WORD *)this = 31;
      if ( !MultiByteToWideChar(0, 0, a3, -1, lpWideCharStr, v42 >> 1) )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v43, "CMFPropVariant::CreateString", 1881);
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( v10 >= 0 )
        {
          v10 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
            CallStackTracing::s_wpInstance = v26;
            if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
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
            v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
            if ( *((_DWORD *)v27 + 499) != -2147418113 )
              CallStackContext::TraceFailure(v27, "CMFPropVariant::CreateString", 1882, -2147418113);
          }
          if ( !g_wppLevels )
            goto LABEL_83;
          v13 = 126;
        }
        else
        {
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
            CallStackTracing::s_wpInstance = v24;
            if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
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
            v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
            if ( *((_DWORD *)v25 + 499) != v10 )
              CallStackContext::TraceFailure(v25, "CMFPropVariant::CreateString", 1881, v10);
          }
          if ( !g_wppLevels )
            goto LABEL_83;
          v13 = 125;
        }
        goto LABEL_82;
      }
      return (unsigned int)v10;
    }
    if ( a2 == 31 )
    {
      v10 = StringCchCopyW(*((unsigned __int16 **)this + 1), (unsigned __int64)v42 >> 1, (const unsigned __int16 *)a3);
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v43, "CMFPropVariant::CreateString", 1888);
      if ( v10 >= 0 )
        goto LABEL_83;
      v30 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29);
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
        {
          v30 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
        if ( *((_DWORD *)v32 + 499) != v10 )
          CallStackContext::TraceFailure(v32, "CMFPropVariant::CreateString", 1888, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_83;
      v13 = 127;
      goto LABEL_82;
    }
  }
  v10 = 0;
  v33 = SysAllocString((const OLECHAR *)a3);
  *((_QWORD *)this + 1) = v33;
  if ( !v33 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v43, "CMFPropVariant::CreateString", 1895);
    v34 = GetLastError();
    v10 = v34;
    if ( v34 > 0 )
      v10 = (unsigned __int16)v34 | 0x80070000;
    if ( v10 >= 0 )
      goto LABEL_83;
    v37 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36);
      CallStackTracing::s_wpInstance = v38;
      if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
      {
        v37 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v37 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v37 + 8) )
    {
      v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
      if ( *((_DWORD *)v39 + 499) != v10 )
        CallStackContext::TraceFailure(v39, "CMFPropVariant::CreateString", 1895, v10);
    }
    if ( !g_wppLevels )
      goto LABEL_83;
    v13 = 128;
    goto LABEL_82;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1801a7850  mov     [rsp-28h+arg_10], rbx
0x1801a7855  mov     [rsp-28h+arg_18], rsi
0x1801a785a  push    rbp
0x1801a785b  push    rdi
0x1801a785c  push    r12
0x1801a785e  push    r13
0x1801a7860  push    r15
0x1801a7862  mov     rbp, rsp
0x1801a7865  sub     rsp, 30h
0x1801a7869  mov     [rcx], dx
0x1801a786c  mov     r12, r8
0x1801a786f  movzx   ebx, dx
0x1801a7872  mov     r15, rcx
0x1801a7875  mov     eax, 1Fh
0x1801a787a  cmp     dx, 1Eh
0x1801a787e  jnz     short loc_1801A7894
0x1801a7880  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1801a7884  xor     edi, edi
0x1801a7886  inc     rdx
0x1801a7889  cmp     [r8+rdx], dil
0x1801a788d  jnz     short loc_1801A7886
0x1801a788f  jmp     loc_1801A7969
0x1801a7894  cmp     bx, ax
0x1801a7897  jz      loc_1801A7959
0x1801a789d  cmp     bx, 8
0x1801a78a1  jz      loc_1801A7959
0x1801a78a7  lea     rsi, aCmfpropvariant_11; "CMFPropVariant::CreateString"
0x1801a78ae  mov     r8d, 73Eh; int
0x1801a78b4  mov     rdx, rsi; char *
0x1801a78b7  lea     rcx, [rbp+arg_8]; this
0x1801a78bb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801a78c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a78c7  xor     edi, edi
0x1801a78c9  mov     ebx, 80070057h
0x1801a78ce  test    rcx, rcx
0x1801a78d1  jnz     short loc_1801A791B
0x1801a78d3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801a78da  nop     dword ptr [rax+rax+00h]
0x1801a78df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a78e6  mov     rcx, rax
0x1801a78e9  test    rax, rax
0x1801a78ec  jz      short loc_1801A790D
0x1801a78ee  mov     rax, [rax]
0x1801a78f1  mov     edx, 7F0h
0x1801a78f6  mov     rax, [rax+8]
0x1801a78fa  call    cs:__guard_dispatch_icall_fptr
0x1801a7900  test    eax, eax
0x1801a7902  jz      short loc_1801A790D
0x1801a7904  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a790b  jmp     short loc_1801A791B
0x1801a790d  lea     rcx, qword_1803CE250; this
0x1801a7914  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a791b  cmp     [rcx+8], dil
0x1801a791f  jz      short loc_1801A7942
0x1801a7921  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801a7926  cmp     [rax+7CCh], ebx
0x1801a792c  jz      short loc_1801A7942
0x1801a792e  mov     r9d, ebx; int
0x1801a7931  mov     r8d, 73Eh; int
0x1801a7937  mov     rdx, rsi; char *
0x1801a793a  mov     rcx, rax; this
0x1801a793d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801a7942  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801a7949  jb      loc_1801A7DC0
0x1801a794f  mov     edx, 7Bh ; '{'
0x1801a7954  jmp     loc_1801A7DA2
0x1801a7959  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1801a795d  xor     edi, edi
0x1801a795f  inc     rdx
0x1801a7962  cmp     [r8+rdx*2], di
0x1801a7967  jnz     short loc_1801A795F
0x1801a7969  lea     eax, [rbx-1Eh]
0x1801a796c  lea     rsi, aCmfpropvariant_11; "CMFPropVariant::CreateString"
0x1801a7973  cmp     ax, 1
0x1801a7977  ja      loc_1801A7CC6
0x1801a797d  lea     edx, ds:2[rdx*2]
0x1801a7984  mov     ecx, edx; cb
0x1801a7986  mov     [rbp+arg_0], edx
0x1801a7989  mov     r13d, edx
0x1801a798c  call    cs:__imp_CoTaskMemAlloc
0x1801a7993  nop     dword ptr [rax+rax+00h]
0x1801a7998  mov     r8d, 745h; int
0x1801a799e  lea     rcx, [rbp+arg_8]; this
0x1801a79a2  mov     rdx, rsi; char *
0x1801a79a5  mov     [r15+8], rax
0x1801a79a9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801a79ae  mov     rax, [r15+8]
0x1801a79b2  test    rax, rax
0x1801a79b5  jnz     loc_1801A7A52
0x1801a79bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a79c2  mov     ebx, 8007000Eh
0x1801a79c7  test    rcx, rcx
0x1801a79ca  jnz     short loc_1801A7A14
0x1801a79cc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801a79d3  nop     dword ptr [rax+rax+00h]
0x1801a79d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a79df  mov     rcx, rax
0x1801a79e2  test    rax, rax
0x1801a79e5  jz      short loc_1801A7A06
0x1801a79e7  mov     rax, [rax]
0x1801a79ea  mov     edx, 7F0h
0x1801a79ef  mov     rax, [rax+8]
0x1801a79f3  call    cs:__guard_dispatch_icall_fptr
0x1801a79f9  test    eax, eax
0x1801a79fb  jz      short loc_1801A7A06
0x1801a79fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a7a04  jmp     short loc_1801A7A14
0x1801a7a06  lea     rcx, qword_1803CE250; this
0x1801a7a0d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a7a14  cmp     [rcx+8], dil
0x1801a7a18  jz      short loc_1801A7A3B
0x1801a7a1a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801a7a1f  cmp     [rax+7CCh], ebx
0x1801a7a25  jz      short loc_1801A7A3B
0x1801a7a27  mov     r9d, ebx; int
0x1801a7a2a  mov     r8d, 745h; int
0x1801a7a30  mov     rdx, rsi; char *
0x1801a7a33  mov     rcx, rax; this
0x1801a7a36  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801a7a3b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801a7a42  jb      loc_1801A7DC0
0x1801a7a48  mov     edx, 7Ch ; '|'
0x1801a7a4d  jmp     loc_1801A7DA2
0x1801a7a52  lea     rcx, [rbp+arg_8]; this
0x1801a7a56  mov     [rax], di
0x1801a7a59  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1801a7a5e  cmp     bx, 1Eh
0x1801a7a62  jnz     loc_1801A7BF8
0x1801a7a68  mov     eax, [rbp+arg_0]
0x1801a7a6b  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1801a7a6f  shr     eax, 1
0x1801a7a71  mov     r8, r12; lpMultiByteStr
0x1801a7a74  mov     [rsp+30h+cchWideChar], eax; cchWideChar
0x1801a7a78  xor     edx, edx; dwFlags
0x1801a7a7a  mov     rax, [r15+8]
0x1801a7a7e  xor     ecx, ecx; CodePage
0x1801a7a80  mov     [rsp+30h+lpWideCharStr], rax; lpWideCharStr
0x1801a7a85  mov     ebx, edi
0x1801a7a87  mov     word ptr [r15], 1Fh
0x1801a7a8d  call    cs:__imp_MultiByteToWideChar
0x1801a7a94  nop     dword ptr [rax+rax+00h]
0x1801a7a99  test    eax, eax
0x1801a7a9b  jnz     loc_1801A7DC9
0x1801a7aa1  mov     r12d, 759h
0x1801a7aa7  lea     rcx, [rbp+arg_8]; this
0x1801a7aab  mov     r8d, r12d; int
0x1801a7aae  mov     rdx, rsi; char *
0x1801a7ab1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801a7ab6  call    cs:__imp_GetLastError
0x1801a7abd  nop     dword ptr [rax+rax+00h]
0x1801a7ac2  mov     ebx, eax
0x1801a7ac4  test    eax, eax
0x1801a7ac6  jle     short loc_1801A7AD1
0x1801a7ac8  movzx   ebx, ax
0x1801a7acb  or      ebx, 80070000h
0x1801a7ad1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a7ad8  test    ebx, ebx
0x1801a7ada  jns     loc_1801A7B68
0x1801a7ae0  test    rcx, rcx
0x1801a7ae3  jnz     short loc_1801A7B2D
0x1801a7ae5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801a7aec  nop     dword ptr [rax+rax+00h]
0x1801a7af1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a7af8  mov     rcx, rax
0x1801a7afb  test    rax, rax
0x1801a7afe  jz      short loc_1801A7B1F
0x1801a7b00  mov     rax, [rax]
0x1801a7b03  mov     edx, 7F0h
0x1801a7b08  mov     rax, [rax+8]
0x1801a7b0c  call    cs:__guard_dispatch_icall_fptr
0x1801a7b12  test    eax, eax
0x1801a7b14  jz      short loc_1801A7B1F
0x1801a7b16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a7b1d  jmp     short loc_1801A7B2D
0x1801a7b1f  lea     rcx, qword_1803CE250; this
0x1801a7b26  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a7b2d  cmp     [rcx+8], dil
0x1801a7b31  jz      short loc_1801A7B51
0x1801a7b33  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801a7b38  cmp     [rax+7CCh], ebx
0x1801a7b3e  jz      short loc_1801A7B51
0x1801a7b40  mov     r9d, ebx; int
0x1801a7b43  mov     r8d, r12d; int
0x1801a7b46  mov     rdx, rsi; char *
0x1801a7b49  mov     rcx, rax; this
0x1801a7b4c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801a7b51  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801a7b58  jb      loc_1801A7DC0
0x1801a7b5e  mov     edx, 7Dh ; '}'
0x1801a7b63  jmp     loc_1801A7DA2
0x1801a7b68  mov     ebx, 8000FFFFh
0x1801a7b6d  test    rcx, rcx
0x1801a7b70  jnz     short loc_1801A7BBA
0x1801a7b72  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801a7b79  nop     dword ptr [rax+rax+00h]
0x1801a7b7e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a7b85  mov     rcx, rax
0x1801a7b88  test    rax, rax
0x1801a7b8b  jz      short loc_1801A7BAC
0x1801a7b8d  mov     rax, [rax]
0x1801a7b90  mov     edx, 7F0h
0x1801a7b95  mov     rax, [rax+8]
0x1801a7b99  call    cs:__guard_dispatch_icall_fptr
0x1801a7b9f  test    eax, eax
0x1801a7ba1  jz      short loc_1801A7BAC
0x1801a7ba3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a7baa  jmp     short loc_1801A7BBA
0x1801a7bac  lea     rcx, qword_1803CE250; this
0x1801a7bb3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a7bba  cmp     [rcx+8], dil
0x1801a7bbe  jz      short loc_1801A7BE1
0x1801a7bc0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801a7bc5  cmp     [rax+7CCh], ebx
0x1801a7bcb  jz      short loc_1801A7BE1
0x1801a7bcd  mov     r9d, ebx; int
0x1801a7bd0  mov     r8d, 75Ah; int
0x1801a7bd6  mov     rdx, rsi; char *
0x1801a7bd9  mov     rcx, rax; this
0x1801a7bdc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801a7be1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801a7be8  jb      loc_1801A7DC0
0x1801a7bee  mov     edx, 7Eh ; '~'
0x1801a7bf3  jmp     loc_1801A7DA2
0x1801a7bf8  mov     eax, 1Fh
0x1801a7bfd  cmp     bx, ax
0x1801a7c00  jnz     loc_1801A7CC6
0x1801a7c06  mov     rcx, [r15+8]; unsigned __int16 *
0x1801a7c0a  mov     r8, r12; unsigned __int16 *
0x1801a7c0d  shr     r13, 1
0x1801a7c10  mov     rdx, r13; unsigned __int64
0x1801a7c13  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801a7c18  mov     r12d, 760h
0x1801a7c1e  lea     rcx, [rbp+arg_8]; this
0x1801a7c22  mov     r8d, r12d; int
0x1801a7c25  mov     rdx, rsi; char *
0x1801a7c28  mov     ebx, eax
0x1801a7c2a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801a7c2f  test    ebx, ebx
0x1801a7c31  jns     loc_1801A7DC0
0x1801a7c37  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a7c3e  test    rcx, rcx
0x1801a7c41  jnz     short loc_1801A7C8B
0x1801a7c43  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801a7c4a  nop     dword ptr [rax+rax+00h]
0x1801a7c4f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a7c56  mov     rcx, rax
0x1801a7c59  test    rax, rax
0x1801a7c5c  jz      short loc_1801A7C7D
0x1801a7c5e  mov     rax, [rax]
0x1801a7c61  mov     edx, 7F0h
0x1801a7c66  mov     rax, [rax+8]
0x1801a7c6a  call    cs:__guard_dispatch_icall_fptr
0x1801a7c70  test    eax, eax
0x1801a7c72  jz      short loc_1801A7C7D
0x1801a7c74  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a7c7b  jmp     short loc_1801A7C8B
0x1801a7c7d  lea     rcx, qword_1803CE250; this
0x1801a7c84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a7c8b  cmp     [rcx+8], dil
0x1801a7c8f  jz      short loc_1801A7CAF
0x1801a7c91  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801a7c96  cmp     [rax+7CCh], ebx
0x1801a7c9c  jz      short loc_1801A7CAF
0x1801a7c9e  mov     r9d, ebx; int
0x1801a7ca1  mov     r8d, r12d; int
0x1801a7ca4  mov     rdx, rsi; char *
0x1801a7ca7  mov     rcx, rax; this
0x1801a7caa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801a7caf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801a7cb6  jb      loc_1801A7DC0
0x1801a7cbc  mov     edx, 7Fh
0x1801a7cc1  jmp     loc_1801A7DA2
0x1801a7cc6  mov     rcx, r12; psz
0x1801a7cc9  mov     ebx, edi
0x1801a7ccb  call    cs:__imp_SysAllocString
0x1801a7cd2  nop     dword ptr [rax+rax+00h]
0x1801a7cd7  mov     [r15+8], rax
0x1801a7cdb  test    rax, rax
0x1801a7cde  jnz     loc_1801A7DC9
0x1801a7ce4  mov     r12d, 767h
0x1801a7cea  lea     rcx, [rbp+arg_8]; this
0x1801a7cee  mov     r8d, r12d; int
0x1801a7cf1  mov     rdx, rsi; char *
0x1801a7cf4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801a7cf9  call    cs:__imp_GetLastError
0x1801a7d00  nop     dword ptr [rax+rax+00h]
0x1801a7d05  mov     ebx, eax
0x1801a7d07  test    eax, eax
0x1801a7d09  jle     short loc_1801A7D14
0x1801a7d0b  movzx   ebx, ax
0x1801a7d0e  or      ebx, 80070000h
0x1801a7d14  test    ebx, ebx
0x1801a7d16  jns     loc_1801A7DC0
0x1801a7d1c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a7d23  test    rcx, rcx
0x1801a7d26  jnz     short loc_1801A7D70
0x1801a7d28  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801a7d2f  nop     dword ptr [rax+rax+00h]
0x1801a7d34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a7d3b  mov     rcx, rax
  ... truncated ...
```
