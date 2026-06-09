# CWMThumbnailStreamProperty::FormatAsNativeBlob(IStream *)

- ea: `0x18004a510`
- end: `0x18004a9ec`
- name: `?FormatAsNativeBlob@CWMThumbnailStreamProperty@@MEAAJPEAUIStream@@@Z`
- size: `1244`
- prototype: `__int64 __fastcall(PROPVARIANT *this, struct IStream *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800174c0`
- `0x180017e20`
- `0x18001a330`
- `0x18001c280`
- `0x18004a510`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004a9b2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004a9b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a774`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a774`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a5a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a646`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a6e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a79e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a880`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a91c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a5a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a646`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a6e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a79e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a880`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a91c`

## pseudocode

```c
__int64 __fastcall CWMThumbnailStreamProperty::FormatAsNativeBlob(PROPVARIANT *this, struct IStream *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  CallStackTracing *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  unsigned int v10; // edi
  CallStackTracing *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  unsigned int v15; // eax
  CallStackTracing *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  char *v19; // rax
  CallStackTracing *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  CallStackTracing *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  _BYTE v30[4]; // [rsp+30h] [rbp-98h] BYREF
  _DWORD v31[3]; // [rsp+34h] [rbp-94h] BYREF
  _BYTE v32[16]; // [rsp+40h] [rbp-88h] BYREF
  unsigned __int64 v33; // [rsp+50h] [rbp-78h]

  memset_0(v32, 0, 0x50u);
  v31[0] = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v30,
    "CWMThumbnailStreamProperty::FormatAsNativeBlob",
    640);
  v5 = ((__int64 (__fastcall *)(struct IStream *, _BYTE *, __int64))a2->lpVtbl->Stat)(a2, v32, 1);
  if ( v5 < 0 )
  {
    v6 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = (CallStackTracing *)&qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 640, v5);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_69;
    v9 = 60;
    goto LABEL_12;
  }
  v10 = v33;
  if ( v33 >= 0xFFFFFFFF )
  {
    v11 = CallStackTracing::s_wpInstance;
    v5 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = (CallStackTracing *)&qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext(v11);
      if ( *((_DWORD *)v13 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v13, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 649, -2147418113);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_69;
    v14 = 61;
    goto LABEL_68;
  }
  v15 = v33 + 47;
  if ( (unsigned int)v33 >= 0xFFFFFFD1 )
  {
    v16 = CallStackTracing::s_wpInstance;
    v5 = -2147024362;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = (CallStackTracing *)&qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext(v16);
      if ( *((_DWORD *)v18 + 499) != -2147024362 )
        CallStackContext::TraceFailure(v18, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 654, -2147024362);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_69;
    v9 = 62;
    goto LABEL_12;
  }
  this[5].vt = 65;
  this[5].lVal = v15;
  v19 = (char *)CoTaskMemAlloc(v15);
  this[5].bstrblobVal.pData = (BYTE *)v19;
  if ( !v19 )
  {
    v20 = CallStackTracing::s_wpInstance;
    v5 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0);
      CallStackTracing::s_wpInstance = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = (CallStackTracing *)&qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v22 = CallStackTracing::GetThreadRelativeContext(v20);
      if ( *((_DWORD *)v22 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v22, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 664, -2147024882);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_69;
    v9 = 63;
    goto LABEL_12;
  }
  *v19 = 3;
  *(_DWORD *)(v19 + 1) = v10;
  *(_OWORD *)(v19 + 5) = *(_OWORD *)L"image/jpeg";
  *(_QWORD *)(v19 + 19) = *(_QWORD *)L"peg";
  *(_OWORD *)(v19 + 27) = *(_OWORD *)L"thumbnail";
  *(_DWORD *)(v19 + 43) = *(_DWORD *)L"l";
  v5 = ((__int64 (__fastcall *)(struct IStream *, char *, _QWORD, _DWORD *))a2->lpVtbl->Read)(a2, v19 + 47, v10, v31);
  if ( v5 < 0 )
  {
    v23 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)((__int64 (*)(void))MFGetCallStackTracingWeakReference)();
      CallStackTracing::s_wpInstance = v24;
      if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
      {
        v23 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v23 = (CallStackTracing *)&qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v23 + 8) )
    {
      v25 = CallStackTracing::GetThreadRelativeContext(v23);
      if ( *((_DWORD *)v25 + 499) != v5 )
        CallStackContext::TraceFailure(v25, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 685, v5);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_69;
    v9 = 64;
LABEL_12:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
LABEL_69:
    PropVariantClear(this + 5);
    goto LABEL_70;
  }
  if ( v31[0] != v10 )
  {
    v26 = CallStackTracing::s_wpInstance;
    v5 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v27 = (CallStackTracing *)((__int64 (*)(void))MFGetCallStackTracingWeakReference)();
      CallStackTracing::s_wpInstance = v27;
      if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
      {
        v26 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v26 = (CallStackTracing *)&qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v26 + 8) )
    {
      v28 = CallStackTracing::GetThreadRelativeContext(v26);
      if ( *((_DWORD *)v28 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v28, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 689, -2147418113);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_69;
    v14 = 65;
LABEL_68:
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
      this,
      -2147418113);
    goto LABEL_69;
  }
LABEL_70:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v30);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004a510  mov     [rsp+arg_10], rbx
0x18004a515  push    rsi
0x18004a516  push    rdi
0x18004a517  push    r12
0x18004a519  push    r13
0x18004a51b  push    r14
0x18004a51d  sub     rsp, 0A0h
0x18004a524  mov     rax, cs:__security_cookie
0x18004a52b  xor     rax, rsp
0x18004a52e  mov     [rsp+0C8h+var_38], rax
0x18004a536  mov     r14, rdx
0x18004a539  mov     rsi, rcx
0x18004a53c  xor     edx, edx; Val
0x18004a53e  lea     rcx, [rsp+0C8h+var_88]; void *
0x18004a543  lea     r8d, [rdx+50h]; Size
0x18004a547  call    memset_0
0x18004a54c  mov     edi, 280h
0x18004a551  mov     [rsp+0C8h+var_94], 0
0x18004a559  lea     r12, aCwmthumbnailst_1; "CWMThumbnailStreamProperty::FormatAsNat"...
0x18004a560  mov     r8d, edi; int
0x18004a563  mov     rdx, r12; char *
0x18004a566  lea     rcx, [rsp+0C8h+var_98]; this
0x18004a56b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004a570  mov     rax, [r14]
0x18004a573  lea     rdx, [rsp+0C8h+var_88]
0x18004a578  mov     r8d, 1
0x18004a57e  mov     rcx, r14
0x18004a581  mov     rax, [rax+60h]
0x18004a585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a58a  mov     ebx, eax
0x18004a58c  test    eax, eax
0x18004a58e  jns     loc_18004A620
0x18004a594  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a59b  test    rcx, rcx
0x18004a59e  jnz     short loc_18004A5E1
0x18004a5a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a5a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a5ad  mov     rcx, rax
0x18004a5b0  test    rax, rax
0x18004a5b3  jz      short loc_18004A5D3
0x18004a5b5  mov     rax, [rax]
0x18004a5b8  mov     edx, 7F0h
0x18004a5bd  mov     rax, [rax+8]
0x18004a5c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a5c6  test    eax, eax
0x18004a5c8  jz      short loc_18004A5D3
0x18004a5ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a5d1  jmp     short loc_18004A5E1
0x18004a5d3  lea     rcx, qword_180069A90; this
0x18004a5da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a5e1  cmp     byte ptr [rcx+8], 0
0x18004a5e5  jz      short loc_18004A605
0x18004a5e7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a5ec  cmp     [rax+7CCh], ebx
0x18004a5f2  jz      short loc_18004A605
0x18004a5f4  mov     r9d, ebx; int
0x18004a5f7  mov     r8d, edi; int
0x18004a5fa  mov     rdx, r12; char *
0x18004a5fd  mov     rcx, rax; this
0x18004a600  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a605  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004a60a  cmp     al, 1
0x18004a60c  jb      loc_18004A9AE
0x18004a612  mov     edx, 3Ch ; '<'
0x18004a617  mov     [rsp+0C8h+var_A8], ebx
0x18004a61b  jmp     loc_18004A994
0x18004a620  mov     rdi, [rsp+0C8h+var_78]
0x18004a625  mov     eax, 0FFFFFFFFh
0x18004a62a  cmp     rdi, rax
0x18004a62d  jb      loc_18004A6C5
0x18004a633  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a63a  mov     edi, 8000FFFFh
0x18004a63f  mov     ebx, edi
0x18004a641  test    rcx, rcx
0x18004a644  jnz     short loc_18004A687
0x18004a646  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a64c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a653  mov     rcx, rax
0x18004a656  test    rax, rax
0x18004a659  jz      short loc_18004A679
0x18004a65b  mov     rax, [rax]
0x18004a65e  mov     edx, 7F0h
0x18004a663  mov     rax, [rax+8]
0x18004a667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a66c  test    eax, eax
0x18004a66e  jz      short loc_18004A679
0x18004a670  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a677  jmp     short loc_18004A687
0x18004a679  lea     rcx, qword_180069A90; this
0x18004a680  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a687  cmp     byte ptr [rcx+8], 0
0x18004a68b  jz      short loc_18004A6AE
0x18004a68d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a692  cmp     [rax+7CCh], edi
0x18004a698  jz      short loc_18004A6AE
0x18004a69a  mov     r9d, edi; int
0x18004a69d  mov     r8d, 289h; int
0x18004a6a3  mov     rdx, r12; char *
0x18004a6a6  mov     rcx, rax; this
0x18004a6a9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a6ae  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004a6b3  cmp     al, 1
0x18004a6b5  jb      loc_18004A9AE
0x18004a6bb  mov     edx, 3Dh ; '='
0x18004a6c0  jmp     loc_18004A990
0x18004a6c5  lea     eax, [rdi+2Fh]
0x18004a6c8  cmp     eax, 2Fh ; '/'
0x18004a6cb  jnb     loc_18004A761
0x18004a6d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a6d8  mov     ebx, 80070216h
0x18004a6dd  test    rcx, rcx
0x18004a6e0  jnz     short loc_18004A723
0x18004a6e2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a6e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a6ef  mov     rcx, rax
0x18004a6f2  test    rax, rax
0x18004a6f5  jz      short loc_18004A715
0x18004a6f7  mov     rax, [rax]
0x18004a6fa  mov     edx, 7F0h
0x18004a6ff  mov     rax, [rax+8]
0x18004a703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a708  test    eax, eax
0x18004a70a  jz      short loc_18004A715
0x18004a70c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a713  jmp     short loc_18004A723
0x18004a715  lea     rcx, qword_180069A90; this
0x18004a71c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a723  cmp     byte ptr [rcx+8], 0
0x18004a727  jz      short loc_18004A74A
0x18004a729  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a72e  cmp     [rax+7CCh], ebx
0x18004a734  jz      short loc_18004A74A
0x18004a736  mov     r9d, ebx; int
0x18004a739  mov     r8d, 28Eh; int
0x18004a73f  mov     rdx, r12; char *
0x18004a742  mov     rcx, rax; this
0x18004a745  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a74a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004a74f  cmp     al, 1
0x18004a751  jb      loc_18004A9AE
0x18004a757  mov     edx, 3Eh ; '>'
0x18004a75c  jmp     loc_18004A617
0x18004a761  mov     r13d, 41h ; 'A'
0x18004a767  mov     ecx, eax; cb
0x18004a769  mov     [rsi+78h], r13w
0x18004a76e  mov     [rsi+80h], eax
0x18004a774  call    cs:__imp_CoTaskMemAlloc
0x18004a77a  mov     [rsi+88h], rax
0x18004a781  mov     rdx, rax
0x18004a784  test    rax, rax
0x18004a787  jnz     loc_18004A81D
0x18004a78d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a794  mov     ebx, 8007000Eh
0x18004a799  test    rcx, rcx
0x18004a79c  jnz     short loc_18004A7DF
0x18004a79e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a7a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a7ab  mov     rcx, rax
0x18004a7ae  test    rax, rax
0x18004a7b1  jz      short loc_18004A7D1
0x18004a7b3  mov     rax, [rax]
0x18004a7b6  mov     edx, 7F0h
0x18004a7bb  mov     rax, [rax+8]
0x18004a7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7c4  test    eax, eax
0x18004a7c6  jz      short loc_18004A7D1
0x18004a7c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a7cf  jmp     short loc_18004A7DF
0x18004a7d1  lea     rcx, qword_180069A90; this
0x18004a7d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a7df  cmp     byte ptr [rcx+8], 0
0x18004a7e3  jz      short loc_18004A806
0x18004a7e5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a7ea  cmp     [rax+7CCh], ebx
0x18004a7f0  jz      short loc_18004A806
0x18004a7f2  mov     r9d, ebx; int
0x18004a7f5  mov     r8d, 298h; int
0x18004a7fb  mov     rdx, r12; char *
0x18004a7fe  mov     rcx, rax; this
0x18004a801  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a806  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004a80b  cmp     al, 1
0x18004a80d  jb      loc_18004A9AE
0x18004a813  mov     edx, 3Fh ; '?'
0x18004a818  jmp     loc_18004A617
0x18004a81d  mov     byte ptr [rax], 3
0x18004a820  lea     r9, [rsp+0C8h+var_94]
0x18004a825  mov     [rax+1], edi
0x18004a828  mov     r8d, edi
0x18004a82b  movups  xmm0, xmmword ptr cs:aImageJpeg; "image/jpeg"
0x18004a832  mov     rcx, r14
0x18004a835  movups  xmmword ptr [rax+5], xmm0
0x18004a839  movsd   xmm1, qword ptr cs:aImageJpeg+0Eh; "peg"
0x18004a841  movsd   qword ptr [rax+13h], xmm1
0x18004a846  movups  xmm0, xmmword ptr cs:aThumbnail; "thumbnail"
0x18004a84d  movups  xmmword ptr [rax+1Bh], xmm0
0x18004a851  mov     eax, dword ptr cs:aThumbnail+10h; "l"
0x18004a857  mov     [rdx+2Bh], eax
0x18004a85a  add     rdx, 2Fh ; '/'
0x18004a85e  mov     rax, [r14]
0x18004a861  mov     rax, [rax+18h]
0x18004a865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a86a  mov     ebx, eax
0x18004a86c  test    eax, eax
0x18004a86e  jns     loc_18004A8FF
0x18004a874  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a87b  test    rcx, rcx
0x18004a87e  jnz     short loc_18004A8C1
0x18004a880  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a886  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a88d  mov     rcx, rax
0x18004a890  test    rax, rax
0x18004a893  jz      short loc_18004A8B3
0x18004a895  mov     rax, [rax]
0x18004a898  mov     edx, 7F0h
0x18004a89d  mov     rax, [rax+8]
0x18004a8a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8a6  test    eax, eax
0x18004a8a8  jz      short loc_18004A8B3
0x18004a8aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a8b1  jmp     short loc_18004A8C1
0x18004a8b3  lea     rcx, qword_180069A90; this
0x18004a8ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a8c1  cmp     byte ptr [rcx+8], 0
0x18004a8c5  jz      short loc_18004A8E8
0x18004a8c7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a8cc  cmp     [rax+7CCh], ebx
0x18004a8d2  jz      short loc_18004A8E8
0x18004a8d4  mov     r9d, ebx; int
0x18004a8d7  mov     r8d, 2ADh; int
0x18004a8dd  mov     rdx, r12; char *
0x18004a8e0  mov     rcx, rax; this
0x18004a8e3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a8e8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004a8ed  cmp     al, 1
0x18004a8ef  jb      loc_18004A9AE
0x18004a8f5  mov     edx, 40h ; '@'
0x18004a8fa  jmp     loc_18004A617
0x18004a8ff  cmp     [rsp+0C8h+var_94], edi
0x18004a903  jz      loc_18004A9B8
0x18004a909  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a910  mov     edi, 8000FFFFh
0x18004a915  mov     ebx, edi
0x18004a917  test    rcx, rcx
0x18004a91a  jnz     short loc_18004A95D
0x18004a91c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a922  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a929  mov     rcx, rax
0x18004a92c  test    rax, rax
0x18004a92f  jz      short loc_18004A94F
0x18004a931  mov     rax, [rax]
0x18004a934  mov     edx, 7F0h
0x18004a939  mov     rax, [rax+8]
0x18004a93d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a942  test    eax, eax
0x18004a944  jz      short loc_18004A94F
0x18004a946  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a94d  jmp     short loc_18004A95D
0x18004a94f  lea     rcx, qword_180069A90; this
0x18004a956  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a95d  cmp     byte ptr [rcx+8], 0
0x18004a961  jz      short loc_18004A984
0x18004a963  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a968  cmp     [rax+7CCh], edi
0x18004a96e  jz      short loc_18004A984
0x18004a970  mov     r9d, edi; int
0x18004a973  mov     r8d, 2B1h; int
0x18004a979  mov     rdx, r12; char *
0x18004a97c  mov     rcx, rax; this
0x18004a97f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a984  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004a989  cmp     al, 1
0x18004a98b  jb      short loc_18004A9AE
0x18004a98d  mov     edx, r13d
0x18004a990  mov     [rsp+0C8h+var_A8], edi
0x18004a994  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a99b  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x18004a9a2  mov     r9, rsi
0x18004a9a5  mov     rcx, [rcx+10h]
0x18004a9a9  call    WPP_SF_qd
0x18004a9ae  lea     rcx, [rsi+78h]; pvar
0x18004a9b2  call    cs:__imp_PropVariantClear
0x18004a9b8  lea     rcx, [rsp+0C8h+var_98]; this
0x18004a9bd  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004a9c2  mov     eax, ebx
0x18004a9c4  mov     rcx, [rsp+0C8h+var_38]
0x18004a9cc  xor     rcx, rsp; StackCookie
0x18004a9cf  call    __security_check_cookie
0x18004a9d4  mov     rbx, [rsp+0C8h+arg_10]
0x18004a9dc  add     rsp, 0A0h
0x18004a9e3  pop     r14
0x18004a9e5  pop     r13
0x18004a9e7  pop     r12
0x18004a9e9  pop     rdi
0x18004a9ea  pop     rsi
0x18004a9eb  retn
```
