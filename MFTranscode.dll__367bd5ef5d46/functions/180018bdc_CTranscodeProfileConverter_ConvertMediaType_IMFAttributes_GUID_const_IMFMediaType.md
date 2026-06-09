# CTranscodeProfileConverter::ConvertMediaType(IMFAttributes *,_GUID const &,IMFMediaType * *)

- ea: `0x180018bdc`
- end: `0x180018f83`
- name: `?ConvertMediaType@CTranscodeProfileConverter@@QEAAJPEAUIMFAttributes@@AEBU_GUID@@PEAPEAUIMFMediaType@@@Z`
- size: `935`
- prototype: `__int64 __fastcall(CTranscodeProfileConverter *__hidden this, struct IMFAttributes *, const struct _GUID *, struct IMFMediaType **)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180018f9c`
- `0x180032b10`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800174c0`
- `0x180018bdc`
- `0x180019558`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x1800594b0`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018c82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018d3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018de6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018eb6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018c82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018d3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018de6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018eb6`
- `MFPlat!MFCreateMediaType` at `0x180018d23`
- `MFPlat!MFCreateMediaType` at `0x180018d23`

## pseudocode

```c
__int64 __fastcall CTranscodeProfileConverter::ConvertMediaType(
        CTranscodeProfileConverter *this,
        struct IMFAttributes *a2,
        const struct _GUID *a3,
        struct IMFMediaType **a4)
{
  struct IMFAttributesVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetGUID)(IMFAttributes *, const GUID *const, GUID *); // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 *v12; // rcx
  HRESULT v13; // ebx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  _BYTE v30[8]; // [rsp+30h] [rbp-30h] BYREF
  IMFMediaType *ppMFType; // [rsp+38h] [rbp-28h] BYREF
  GUID Buf2; // [rsp+40h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v30,
    "CTranscodeProfileConverter::ConvertMediaType",
    626);
  lpVtbl = a2->lpVtbl;
  ppMFType = 0;
  GetGUID = lpVtbl->GetGUID;
  Buf2 = GUID_00000000_0000_0000_0000_000000000000;
  if ( ((int (__fastcall *)(struct IMFAttributes *, const GUID *, GUID *))GetGUID)(a2, &MF_MT_MAJOR_TYPE, &Buf2) < 0 )
    goto LABEL_16;
  v11 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&Buf2.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&Buf2.Data1 )
    v11 = *(_QWORD *)a3->Data4 - *(_QWORD *)Buf2.Data4;
  if ( v11 )
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    v13 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CTranscodeProfileConverter::ConvertMediaType",
          635,
          -2147024809);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v16 = 78;
LABEL_15:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids, this, v13);
    }
  }
  else
  {
LABEL_16:
    v13 = MFCreateMediaType(&ppMFType);
    if ( v13 >= 0 )
    {
      v13 = CTranscodeProfileConverter::CopyMediaTypeAttributes(this, a3, a2, (struct IMFAttributes *)ppMFType);
      if ( v13 >= 0 )
      {
        if ( !memcmp_0(&GUID_00000000_0000_0000_0000_000000000000, &Buf2, 0x10u)
          && (v13 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const struct _GUID *))ppMFType->lpVtbl->SetGUID)(
                      ppMFType,
                      &MF_MT_MAJOR_TYPE,
                      a3),
              v13 < 0) )
        {
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
            if ( *((_DWORD *)v28 + 499) != v13 )
              CallStackContext::TraceFailure(v28, "CTranscodeProfileConverter::ConvertMediaType", 650, v13);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v16 = 81;
            goto LABEL_15;
          }
        }
        else
        {
          *a4 = ppMFType;
          ppMFType = 0;
        }
      }
      else
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
          CallStackTracing::s_wpInstance = v23;
          if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
          {
            v22 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v22 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v22 + 8) )
        {
          v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
          if ( *((_DWORD *)v24 + 499) != v13 )
            CallStackContext::TraceFailure(v24, "CTranscodeProfileConverter::ConvertMediaType", 645, v13);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v16 = 80;
          goto LABEL_15;
        }
      }
    }
    else
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v20 + 499) != v13 )
          CallStackContext::TraceFailure(v20, "CTranscodeProfileConverter::ConvertMediaType", 638, v13);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v16 = 79;
        goto LABEL_15;
      }
    }
  }
  if ( ppMFType )
  {
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
    ppMFType = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v30);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180018bdc  push    rbp
0x180018bde  push    rbx
0x180018bdf  push    rsi
0x180018be0  push    rdi
0x180018be1  push    r13
0x180018be3  push    r14
0x180018be5  push    r15
0x180018be7  mov     rbp, rsp
0x180018bea  sub     rsp, 60h
0x180018bee  mov     rax, cs:__security_cookie
0x180018bf5  xor     rax, rsp
0x180018bf8  mov     [rbp+var_10], rax
0x180018bfc  mov     rdi, r8
0x180018bff  lea     r13, aCtranscodeprof_20; "CTranscodeProfileConverter::ConvertMedi"...
0x180018c06  mov     r14, rdx
0x180018c09  mov     rsi, rcx
0x180018c0c  mov     rdx, r13; char *
0x180018c0f  lea     rcx, [rbp+var_30]; this
0x180018c13  mov     r8d, 272h; int
0x180018c19  mov     r15, r9
0x180018c1c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180018c21  mov     rax, [r14]
0x180018c24  lea     r8, [rbp+Buf2]
0x180018c28  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180018c2f  lea     rdx, MF_MT_MAJOR_TYPE
0x180018c36  mov     [rbp+ppMFType], 0
0x180018c3e  mov     rcx, r14
0x180018c41  mov     rax, [rax+50h]
0x180018c45  movdqu  [rbp+Buf2], xmm0
0x180018c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c4f  test    eax, eax
0x180018c51  js      loc_180018D1F
0x180018c57  mov     rax, [rdi]
0x180018c5a  sub     rax, qword ptr [rbp+Buf2]
0x180018c5e  jnz     short loc_180018C68
0x180018c60  mov     rax, [rdi+8]
0x180018c64  sub     rax, qword ptr [rbp+Buf2+8]
0x180018c68  test    rax, rax
0x180018c6b  jz      loc_180018D1F
0x180018c71  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018c78  mov     ebx, 80070057h
0x180018c7d  test    rcx, rcx
0x180018c80  jnz     short loc_180018CC3
0x180018c82  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018c88  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018c8f  mov     rcx, rax
0x180018c92  test    rax, rax
0x180018c95  jz      short loc_180018CB5
0x180018c97  mov     rax, [rax]
0x180018c9a  mov     edx, 7F0h
0x180018c9f  mov     rax, [rax+8]
0x180018ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ca8  test    eax, eax
0x180018caa  jz      short loc_180018CB5
0x180018cac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018cb3  jmp     short loc_180018CC3
0x180018cb5  lea     rcx, qword_180069A90; this
0x180018cbc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018cc3  cmp     byte ptr [rcx+8], 0
0x180018cc7  jz      short loc_180018CEA
0x180018cc9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018cce  cmp     [rax+7CCh], ebx
0x180018cd4  jz      short loc_180018CEA
0x180018cd6  mov     r9d, ebx; int
0x180018cd9  mov     r8d, 27Bh; int
0x180018cdf  mov     rdx, r13; char *
0x180018ce2  mov     rcx, rax; this
0x180018ce5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018cea  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180018cef  cmp     al, 1
0x180018cf1  jb      loc_180018F40
0x180018cf7  mov     edx, 4Eh ; 'N'
0x180018cfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d03  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x180018d0a  mov     r9, rsi
0x180018d0d  mov     [rsp+60h+var_40], ebx
0x180018d11  mov     rcx, [rcx+10h]
0x180018d15  call    WPP_SF_qd
0x180018d1a  jmp     loc_180018F40
0x180018d1f  lea     rcx, [rbp+ppMFType]; ppMFType
0x180018d23  call    cs:__imp_MFCreateMediaType
0x180018d29  mov     ebx, eax
0x180018d2b  test    eax, eax
0x180018d2d  jns     loc_180018DBE
0x180018d33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018d3a  test    rcx, rcx
0x180018d3d  jnz     short loc_180018D80
0x180018d3f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018d45  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018d4c  mov     rcx, rax
0x180018d4f  test    rax, rax
0x180018d52  jz      short loc_180018D72
0x180018d54  mov     rax, [rax]
0x180018d57  mov     edx, 7F0h
0x180018d5c  mov     rax, [rax+8]
0x180018d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d65  test    eax, eax
0x180018d67  jz      short loc_180018D72
0x180018d69  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018d70  jmp     short loc_180018D80
0x180018d72  lea     rcx, qword_180069A90; this
0x180018d79  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018d80  cmp     byte ptr [rcx+8], 0
0x180018d84  jz      short loc_180018DA7
0x180018d86  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018d8b  cmp     [rax+7CCh], ebx
0x180018d91  jz      short loc_180018DA7
0x180018d93  mov     r9d, ebx; int
0x180018d96  mov     r8d, 27Eh; int
0x180018d9c  mov     rdx, r13; char *
0x180018d9f  mov     rcx, rax; this
0x180018da2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018da7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180018dac  cmp     al, 1
0x180018dae  jb      loc_180018F40
0x180018db4  mov     edx, 4Fh ; 'O'
0x180018db9  jmp     loc_180018CFC
0x180018dbe  mov     r9, [rbp+ppMFType]; struct IMFAttributes *
0x180018dc2  mov     r8, r14; struct IMFAttributes *
0x180018dc5  mov     rdx, rdi; struct _GUID *
0x180018dc8  mov     rcx, rsi; this
0x180018dcb  call    ?CopyMediaTypeAttributes@CTranscodeProfileConverter@@IEAAJAEBU_GUID@@PEAUIMFAttributes@@1@Z; CTranscodeProfileConverter::CopyMediaTypeAttributes(_GUID const &,IMFAttributes *,IMFAttributes *)
0x180018dd0  mov     ebx, eax
0x180018dd2  test    eax, eax
0x180018dd4  jns     loc_180018E65
0x180018dda  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018de1  test    rcx, rcx
0x180018de4  jnz     short loc_180018E27
0x180018de6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018dec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018df3  mov     rcx, rax
0x180018df6  test    rax, rax
0x180018df9  jz      short loc_180018E19
0x180018dfb  mov     rax, [rax]
0x180018dfe  mov     edx, 7F0h
0x180018e03  mov     rax, [rax+8]
0x180018e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e0c  test    eax, eax
0x180018e0e  jz      short loc_180018E19
0x180018e10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018e17  jmp     short loc_180018E27
0x180018e19  lea     rcx, qword_180069A90; this
0x180018e20  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018e27  cmp     byte ptr [rcx+8], 0
0x180018e2b  jz      short loc_180018E4E
0x180018e2d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018e32  cmp     [rax+7CCh], ebx
0x180018e38  jz      short loc_180018E4E
0x180018e3a  mov     r9d, ebx; int
0x180018e3d  mov     r8d, 285h; int
0x180018e43  mov     rdx, r13; char *
0x180018e46  mov     rcx, rax; this
0x180018e49  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018e4e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180018e53  cmp     al, 1
0x180018e55  jb      loc_180018F40
0x180018e5b  mov     edx, 50h ; 'P'
0x180018e60  jmp     loc_180018CFC
0x180018e65  mov     r8d, 10h; Size
0x180018e6b  lea     rdx, [rbp+Buf2]; Buf2
0x180018e6f  lea     rcx, _GUID_00000000_0000_0000_0000_000000000000; Buf1
0x180018e76  call    memcmp_0
0x180018e7b  test    eax, eax
0x180018e7d  jnz     loc_180018F31
0x180018e83  mov     rcx, [rbp+ppMFType]
0x180018e87  lea     rdx, MF_MT_MAJOR_TYPE
0x180018e8e  mov     r8, rdi
0x180018e91  mov     rax, [rcx]
0x180018e94  mov     rax, [rax+0C0h]
0x180018e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ea0  mov     ebx, eax
0x180018ea2  test    eax, eax
0x180018ea4  jns     loc_180018F31
0x180018eaa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018eb1  test    rcx, rcx
0x180018eb4  jnz     short loc_180018EF7
0x180018eb6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018ebc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018ec3  mov     rcx, rax
0x180018ec6  test    rax, rax
0x180018ec9  jz      short loc_180018EE9
0x180018ecb  mov     rax, [rax]
0x180018ece  mov     edx, 7F0h
0x180018ed3  mov     rax, [rax+8]
0x180018ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018edc  test    eax, eax
0x180018ede  jz      short loc_180018EE9
0x180018ee0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018ee7  jmp     short loc_180018EF7
0x180018ee9  lea     rcx, qword_180069A90; this
0x180018ef0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018ef7  cmp     byte ptr [rcx+8], 0
0x180018efb  jz      short loc_180018F1E
0x180018efd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018f02  cmp     [rax+7CCh], ebx
0x180018f08  jz      short loc_180018F1E
0x180018f0a  mov     r9d, ebx; int
0x180018f0d  mov     r8d, 28Ah; int
0x180018f13  mov     rdx, r13; char *
0x180018f16  mov     rcx, rax; this
0x180018f19  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018f1e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180018f23  cmp     al, 1
0x180018f25  jb      short loc_180018F40
0x180018f27  mov     edx, 51h ; 'Q'
0x180018f2c  jmp     loc_180018CFC
0x180018f31  mov     rax, [rbp+ppMFType]
0x180018f35  mov     [r15], rax
0x180018f38  mov     [rbp+ppMFType], 0
0x180018f40  mov     rcx, [rbp+ppMFType]
0x180018f44  test    rcx, rcx
0x180018f47  jz      short loc_180018F5D
0x180018f49  mov     rax, [rcx]
0x180018f4c  mov     rax, [rax+10h]
0x180018f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f55  mov     [rbp+ppMFType], 0
0x180018f5d  lea     rcx, [rbp+var_30]; this
0x180018f61  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180018f66  mov     eax, ebx
0x180018f68  mov     rcx, [rbp+var_10]
0x180018f6c  xor     rcx, rsp; StackCookie
0x180018f6f  call    __security_check_cookie
0x180018f74  add     rsp, 60h
0x180018f78  pop     r15
0x180018f7a  pop     r14
0x180018f7c  pop     r13
0x180018f7e  pop     rdi
0x180018f7f  pop     rsi
0x180018f80  pop     rbx
0x180018f81  pop     rbp
0x180018f82  retn
```
