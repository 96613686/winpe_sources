# CTranscodeDestination::GetMediaTypeByStreamSinkId(ulong,IMFMediaType * *)

- ea: `0x1800428c0`
- end: `0x180042bc3`
- name: `?GetMediaTypeByStreamSinkId@CTranscodeDestination@@MEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `771`
- prototype: `__int64 __fastcall(CTranscodeDestination *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x1800428c0`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004291b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800429c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042a80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042b10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004291b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800429c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042a80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042b10`

## string_xrefs

- `0x1800428d5`: `CTranscodeDestination::GetMediaTypeByStreamSinkId`

## pseudocode

```c
__int64 __fastcall CTranscodeDestination::GetMediaTypeByStreamSinkId(
        CTranscodeDestination *this,
        int a2,
        struct IMFMediaType **a3)
{
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 *v8; // rcx
  unsigned int v9; // edi
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  struct IMFMediaType *v13; // rcx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  char v24; // [rsp+50h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v24,
    "CTranscodeDestination::GetMediaTypeByStreamSinkId",
    367);
  *a3 = 0;
  v7 = *((_QWORD *)this + 8);
  if ( !v7 )
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    v9 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CTranscodeDestination::GetMediaTypeByStreamSinkId",
          372,
          -2147418113);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 64;
LABEL_12:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        WPP_82ede244afe43de52d63f347cb6083ad_Traceguids,
        this,
        -2147418113);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  v9 = 0;
  if ( a2 != *(_DWORD *)(v7 + 16) )
  {
    if ( a2 != *(_DWORD *)v7 )
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      v9 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
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
        if ( *((_DWORD *)v22 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v22, "CTranscodeDestination::GetMediaTypeByStreamSinkId", 392, -2147024809);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          WPP_82ede244afe43de52d63f347cb6083ad_Traceguids,
          this,
          -2147024809);
      goto LABEL_48;
    }
    v13 = *(struct IMFMediaType **)(v7 + 8);
    if ( !v13 )
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
      v9 = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != -2147418113 )
          CallStackContext::TraceFailure(v19, "CTranscodeDestination::GetMediaTypeByStreamSinkId", 385, -2147418113);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 66;
        goto LABEL_12;
      }
      goto LABEL_48;
    }
LABEL_25:
    *a3 = v13;
    ((void (__fastcall *)(struct IMFMediaType *))v13->lpVtbl->AddRef)(v13);
    goto LABEL_48;
  }
  v13 = *(struct IMFMediaType **)(v7 + 24);
  if ( v13 )
    goto LABEL_25;
  v14 = (__int64 *)CallStackTracing::s_wpInstance;
  v9 = -2147418113;
  if ( !CallStackTracing::s_wpInstance )
  {
    v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
    CallStackTracing::s_wpInstance = v15;
    if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v14 = &qword_180069A90;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
  }
  if ( *((_BYTE *)v14 + 8) )
  {
    v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
    if ( *((_DWORD *)v16 + 499) != -2147418113 )
      CallStackContext::TraceFailure(v16, "CTranscodeDestination::GetMediaTypeByStreamSinkId", 376, -2147418113);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v12 = 65;
    goto LABEL_12;
  }
LABEL_48:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v24);
  return v9;
}

```

## disassembly

```asm
0x1800428c0  mov     [rsp+arg_8], rbx
0x1800428c5  mov     [rsp+arg_10], rbp
0x1800428ca  push    rsi
0x1800428cb  push    rdi
0x1800428cc  push    r15
0x1800428ce  sub     rsp, 30h
0x1800428d2  mov     rbx, r8
0x1800428d5  lea     r15, aCtranscodedest_5; "CTranscodeDestination::GetMediaTypeBySt"...
0x1800428dc  mov     esi, edx
0x1800428de  mov     rbp, rcx
0x1800428e1  mov     rdx, r15; char *
0x1800428e4  lea     rcx, [rsp+48h+arg_0]; this
0x1800428e9  mov     r8d, 16Fh; int
0x1800428ef  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800428f4  mov     qword ptr [rbx], 0
0x1800428fb  mov     rax, [rbp+40h]
0x1800428ff  test    rax, rax
0x180042902  jnz     loc_18004299E
0x180042908  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004290f  mov     ebx, 8000FFFFh
0x180042914  mov     edi, ebx
0x180042916  test    rcx, rcx
0x180042919  jnz     short loc_18004295C
0x18004291b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042921  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042928  mov     rcx, rax
0x18004292b  test    rax, rax
0x18004292e  jz      short loc_18004294E
0x180042930  mov     rax, [rax]
0x180042933  mov     edx, 7F0h
0x180042938  mov     rax, [rax+8]
0x18004293c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042941  test    eax, eax
0x180042943  jz      short loc_18004294E
0x180042945  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004294c  jmp     short loc_18004295C
0x18004294e  lea     rcx, qword_180069A90; this
0x180042955  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004295c  cmp     byte ptr [rcx+8], 0
0x180042960  jz      short loc_180042983
0x180042962  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042967  cmp     [rax+7CCh], ebx
0x18004296d  jz      short loc_180042983
0x18004296f  mov     r9d, ebx; int
0x180042972  mov     r8d, 174h; int
0x180042978  mov     rdx, r15; char *
0x18004297b  mov     rcx, rax; this
0x18004297e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042983  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042988  cmp     al, 1
0x18004298a  jb      loc_180042BA4
0x180042990  mov     edx, 40h ; '@'
0x180042995  mov     [rsp+48h+var_28], ebx
0x180042999  jmp     loc_180042B8A
0x18004299e  xor     edi, edi
0x1800429a0  cmp     esi, [rax+10h]
0x1800429a3  jnz     loc_180042A5C
0x1800429a9  mov     rcx, [rax+18h]
0x1800429ad  test    rcx, rcx
0x1800429b0  jnz     loc_180042A48
0x1800429b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800429bd  mov     ebx, 8000FFFFh
0x1800429c2  mov     edi, ebx
0x1800429c4  test    rcx, rcx
0x1800429c7  jnz     short loc_180042A0A
0x1800429c9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800429cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800429d6  mov     rcx, rax
0x1800429d9  test    rax, rax
0x1800429dc  jz      short loc_1800429FC
0x1800429de  mov     rax, [rax]
0x1800429e1  mov     edx, 7F0h
0x1800429e6  mov     rax, [rax+8]
0x1800429ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800429ef  test    eax, eax
0x1800429f1  jz      short loc_1800429FC
0x1800429f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800429fa  jmp     short loc_180042A0A
0x1800429fc  lea     rcx, qword_180069A90; this
0x180042a03  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042a0a  cmp     byte ptr [rcx+8], 0
0x180042a0e  jz      short loc_180042A31
0x180042a10  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042a15  cmp     [rax+7CCh], ebx
0x180042a1b  jz      short loc_180042A31
0x180042a1d  mov     r9d, ebx; int
0x180042a20  mov     r8d, 178h; int
0x180042a26  mov     rdx, r15; char *
0x180042a29  mov     rcx, rax; this
0x180042a2c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042a31  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042a36  cmp     al, 1
0x180042a38  jb      loc_180042BA4
0x180042a3e  mov     edx, 41h ; 'A'
0x180042a43  jmp     loc_180042995
0x180042a48  mov     [rbx], rcx
0x180042a4b  mov     rax, [rcx]
0x180042a4e  mov     rax, [rax+8]
0x180042a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a57  jmp     loc_180042BA4
0x180042a5c  cmp     esi, [rax]
0x180042a5e  jnz     loc_180042AFF
0x180042a64  mov     rcx, [rax+8]
0x180042a68  test    rcx, rcx
0x180042a6b  jnz     short loc_180042A48
0x180042a6d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042a74  mov     ebx, 8000FFFFh
0x180042a79  mov     edi, ebx
0x180042a7b  test    rcx, rcx
0x180042a7e  jnz     short loc_180042AC1
0x180042a80  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042a86  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042a8d  mov     rcx, rax
0x180042a90  test    rax, rax
0x180042a93  jz      short loc_180042AB3
0x180042a95  mov     rax, [rax]
0x180042a98  mov     edx, 7F0h
0x180042a9d  mov     rax, [rax+8]
0x180042aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042aa6  test    eax, eax
0x180042aa8  jz      short loc_180042AB3
0x180042aaa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042ab1  jmp     short loc_180042AC1
0x180042ab3  lea     rcx, qword_180069A90; this
0x180042aba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042ac1  cmp     byte ptr [rcx+8], 0
0x180042ac5  jz      short loc_180042AE8
0x180042ac7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042acc  cmp     [rax+7CCh], ebx
0x180042ad2  jz      short loc_180042AE8
0x180042ad4  mov     r9d, ebx; int
0x180042ad7  mov     r8d, 181h; int
0x180042add  mov     rdx, r15; char *
0x180042ae0  mov     rcx, rax; this
0x180042ae3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042ae8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042aed  cmp     al, 1
0x180042aef  jb      loc_180042BA4
0x180042af5  mov     edx, 42h ; 'B'
0x180042afa  jmp     loc_180042995
0x180042aff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042b06  mov     edi, 80070057h
0x180042b0b  test    rcx, rcx
0x180042b0e  jnz     short loc_180042B51
0x180042b10  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042b16  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042b1d  mov     rcx, rax
0x180042b20  test    rax, rax
0x180042b23  jz      short loc_180042B43
0x180042b25  mov     rax, [rax]
0x180042b28  mov     edx, 7F0h
0x180042b2d  mov     rax, [rax+8]
0x180042b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b36  test    eax, eax
0x180042b38  jz      short loc_180042B43
0x180042b3a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042b41  jmp     short loc_180042B51
0x180042b43  lea     rcx, qword_180069A90; this
0x180042b4a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042b51  cmp     byte ptr [rcx+8], 0
0x180042b55  jz      short loc_180042B78
0x180042b57  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042b5c  cmp     [rax+7CCh], edi
0x180042b62  jz      short loc_180042B78
0x180042b64  mov     r9d, edi; int
0x180042b67  mov     r8d, 188h; int
0x180042b6d  mov     rdx, r15; char *
0x180042b70  mov     rcx, rax; this
0x180042b73  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042b78  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042b7d  cmp     al, 1
0x180042b7f  jb      short loc_180042BA4
0x180042b81  mov     edx, 43h ; 'C'
0x180042b86  mov     [rsp+48h+var_28], edi
0x180042b8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180042b91  lea     r8, WPP_82ede244afe43de52d63f347cb6083ad_Traceguids
0x180042b98  mov     r9, rbp
0x180042b9b  mov     rcx, [rcx+10h]
0x180042b9f  call    WPP_SF_qd
0x180042ba4  lea     rcx, [rsp+48h+arg_0]; this
0x180042ba9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180042bae  mov     rbx, [rsp+48h+arg_8]
0x180042bb3  mov     eax, edi
0x180042bb5  mov     rbp, [rsp+48h+arg_10]
0x180042bba  add     rsp, 30h
0x180042bbe  pop     r15
0x180042bc0  pop     rdi
0x180042bc1  pop     rsi
0x180042bc2  retn
```
