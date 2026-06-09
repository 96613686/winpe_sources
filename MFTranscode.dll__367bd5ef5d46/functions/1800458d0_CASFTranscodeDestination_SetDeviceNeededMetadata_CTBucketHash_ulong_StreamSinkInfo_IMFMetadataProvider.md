# CASFTranscodeDestination::SetDeviceNeededMetadata(CTBucketHash<ulong,StreamSinkInfo> &,IMFMetadataProvider *)

- ea: `0x1800458d0`
- end: `0x180045c32`
- name: `?SetDeviceNeededMetadata@CASFTranscodeDestination@@IEAAJAEAV?$CTBucketHash@KUStreamSinkInfo@@@@PEAUIMFMetadataProvider@@@Z`
- size: `866`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1800451f0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x1800458d0`
- `0x180045c38`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004593f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800459ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045a98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045b48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004593f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800459ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045a98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045b48`

## pseudocode

```c
__int64 __fastcall CASFTranscodeDestination::SetDeviceNeededMetadata(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // rdx
  int v8; // ebx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v26; // [rsp+30h] [rbp-10h] BYREF
  char v27; // [rsp+70h] [rbp+30h] BYREF
  __int64 v28; // [rsp+88h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v27,
    "CASFTranscodeDestination::SetDeviceNeededMetadata",
    276);
  v6 = *(_QWORD *)(a1 + 8);
  v28 = 0;
  v26 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 32LL))(v6, &v28);
  if ( v8 >= 0 )
  {
    v8 = CASFTranscodeDestination::SetDeviceNeededMetadataOnStream(a1, a2, &MFMediaType_Audio, v28, a3);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 8) + 48LL))(*(_QWORD *)(a1 + 8), &v26);
      if ( v8 >= 0 )
      {
        v8 = CASFTranscodeDestination::SetDeviceNeededMetadataOnStream(a1, a2, &MFMediaType_Video, v26, a3);
        if ( v8 < 0 )
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
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CASFTranscodeDestination::SetDeviceNeededMetadata",
                285,
                v8);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v12 = 31;
            goto LABEL_45;
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
          if ( *((_DWORD *)v20 + 499) != v8 )
            CallStackContext::TraceFailure(v20, "CASFTranscodeDestination::SetDeviceNeededMetadata", 284, v8);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v12 = 30;
          goto LABEL_45;
        }
      }
    }
    else
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
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
        if ( *((_DWORD *)v16 + 499) != v8 )
          CallStackContext::TraceFailure(v16, "CASFTranscodeDestination::SetDeviceNeededMetadata", 283, v8);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 29;
        goto LABEL_45;
      }
    }
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v11 + 499) != v8 )
        CallStackContext::TraceFailure(v11, "CASFTranscodeDestination::SetDeviceNeededMetadata", 282, v8);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 28;
LABEL_45:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_0a758c1def7e3974366218a1d0d46647_Traceguids, a1, v8);
    }
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800458d0  mov     [rsp-28h+arg_8], rbx
0x1800458d5  push    rbp
0x1800458d6  push    rsi
0x1800458d7  push    rdi
0x1800458d8  push    r12
0x1800458da  push    r14
0x1800458dc  mov     rbp, rsp
0x1800458df  sub     rsp, 40h
0x1800458e3  mov     rsi, r8
0x1800458e6  lea     r12, aCasftranscoded_7; "CASFTranscodeDestination::SetDeviceNeed"...
0x1800458ed  mov     r14, rdx
0x1800458f0  mov     rdi, rcx
0x1800458f3  mov     rdx, r12; char *
0x1800458f6  lea     rcx, [rbp+arg_0]; this
0x1800458fa  mov     r8d, 114h; int
0x180045900  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180045905  mov     rcx, [rdi+8]
0x180045909  lea     rdx, [rbp+arg_18]
0x18004590d  mov     [rbp+arg_18], 0
0x180045915  mov     [rbp+var_10], 0
0x18004591d  mov     rax, [rcx]
0x180045920  mov     rax, [rax+20h]
0x180045924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045929  mov     ebx, eax
0x18004592b  test    eax, eax
0x18004592d  jns     loc_1800459BE
0x180045933  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004593a  test    rcx, rcx
0x18004593d  jnz     short loc_180045980
0x18004593f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045945  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004594c  mov     rcx, rax
0x18004594f  test    rax, rax
0x180045952  jz      short loc_180045972
0x180045954  mov     rax, [rax]
0x180045957  mov     edx, 7F0h
0x18004595c  mov     rax, [rax+8]
0x180045960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045965  test    eax, eax
0x180045967  jz      short loc_180045972
0x180045969  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045970  jmp     short loc_180045980
0x180045972  lea     rcx, qword_180069A90; this
0x180045979  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045980  cmp     byte ptr [rcx+8], 0
0x180045984  jz      short loc_1800459A7
0x180045986  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004598b  cmp     [rax+7CCh], ebx
0x180045991  jz      short loc_1800459A7
0x180045993  mov     r9d, ebx; int
0x180045996  mov     r8d, 11Ah; int
0x18004599c  mov     rdx, r12; char *
0x18004599f  mov     rcx, rax; this
0x1800459a2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800459a7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800459ac  cmp     al, 1
0x1800459ae  jb      loc_180045BDC
0x1800459b4  mov     edx, 1Ch
0x1800459b9  jmp     loc_180045BBE
0x1800459be  mov     r9, [rbp+arg_18]
0x1800459c2  lea     r8, MFMediaType_Audio
0x1800459c9  mov     rdx, r14
0x1800459cc  mov     [rsp+40h+var_20], rsi
0x1800459d1  mov     rcx, rdi
0x1800459d4  call    ?SetDeviceNeededMetadataOnStream@CASFTranscodeDestination@@IEAAJAEAV?$CTBucketHash@KUStreamSinkInfo@@@@AEBU_GUID@@PEAUIMFAttributes@@PEAUIMFMetadataProvider@@@Z; CASFTranscodeDestination::SetDeviceNeededMetadataOnStream(CTBucketHash<ulong,StreamSinkInfo> &,_GUID const &,IMFAttributes *,IMFMetadataProvider *)
0x1800459d9  mov     ebx, eax
0x1800459db  test    eax, eax
0x1800459dd  jns     loc_180045A6E
0x1800459e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800459ea  test    rcx, rcx
0x1800459ed  jnz     short loc_180045A30
0x1800459ef  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800459f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800459fc  mov     rcx, rax
0x1800459ff  test    rax, rax
0x180045a02  jz      short loc_180045A22
0x180045a04  mov     rax, [rax]
0x180045a07  mov     edx, 7F0h
0x180045a0c  mov     rax, [rax+8]
0x180045a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a15  test    eax, eax
0x180045a17  jz      short loc_180045A22
0x180045a19  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045a20  jmp     short loc_180045A30
0x180045a22  lea     rcx, qword_180069A90; this
0x180045a29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045a30  cmp     byte ptr [rcx+8], 0
0x180045a34  jz      short loc_180045A57
0x180045a36  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045a3b  cmp     [rax+7CCh], ebx
0x180045a41  jz      short loc_180045A57
0x180045a43  mov     r9d, ebx; int
0x180045a46  mov     r8d, 11Bh; int
0x180045a4c  mov     rdx, r12; char *
0x180045a4f  mov     rcx, rax; this
0x180045a52  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045a57  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045a5c  cmp     al, 1
0x180045a5e  jb      loc_180045BDC
0x180045a64  mov     edx, 1Dh
0x180045a69  jmp     loc_180045BBE
0x180045a6e  mov     rcx, [rdi+8]
0x180045a72  lea     rdx, [rbp+var_10]
0x180045a76  mov     rax, [rcx]
0x180045a79  mov     rax, [rax+30h]
0x180045a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a82  mov     ebx, eax
0x180045a84  test    eax, eax
0x180045a86  jns     loc_180045B17
0x180045a8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045a93  test    rcx, rcx
0x180045a96  jnz     short loc_180045AD9
0x180045a98  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045a9e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045aa5  mov     rcx, rax
0x180045aa8  test    rax, rax
0x180045aab  jz      short loc_180045ACB
0x180045aad  mov     rax, [rax]
0x180045ab0  mov     edx, 7F0h
0x180045ab5  mov     rax, [rax+8]
0x180045ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045abe  test    eax, eax
0x180045ac0  jz      short loc_180045ACB
0x180045ac2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045ac9  jmp     short loc_180045AD9
0x180045acb  lea     rcx, qword_180069A90; this
0x180045ad2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045ad9  cmp     byte ptr [rcx+8], 0
0x180045add  jz      short loc_180045B00
0x180045adf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045ae4  cmp     [rax+7CCh], ebx
0x180045aea  jz      short loc_180045B00
0x180045aec  mov     r9d, ebx; int
0x180045aef  mov     r8d, 11Ch; int
0x180045af5  mov     rdx, r12; char *
0x180045af8  mov     rcx, rax; this
0x180045afb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045b00  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045b05  cmp     al, 1
0x180045b07  jb      loc_180045BDC
0x180045b0d  mov     edx, 1Eh
0x180045b12  jmp     loc_180045BBE
0x180045b17  mov     r9, [rbp+var_10]
0x180045b1b  lea     r8, MFMediaType_Video
0x180045b22  mov     rdx, r14
0x180045b25  mov     [rsp+40h+var_20], rsi
0x180045b2a  mov     rcx, rdi
0x180045b2d  call    ?SetDeviceNeededMetadataOnStream@CASFTranscodeDestination@@IEAAJAEAV?$CTBucketHash@KUStreamSinkInfo@@@@AEBU_GUID@@PEAUIMFAttributes@@PEAUIMFMetadataProvider@@@Z; CASFTranscodeDestination::SetDeviceNeededMetadataOnStream(CTBucketHash<ulong,StreamSinkInfo> &,_GUID const &,IMFAttributes *,IMFMetadataProvider *)
0x180045b32  mov     ebx, eax
0x180045b34  test    eax, eax
0x180045b36  jns     loc_180045BDC
0x180045b3c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045b43  test    rcx, rcx
0x180045b46  jnz     short loc_180045B89
0x180045b48  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045b4e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045b55  mov     rcx, rax
0x180045b58  test    rax, rax
0x180045b5b  jz      short loc_180045B7B
0x180045b5d  mov     rax, [rax]
0x180045b60  mov     edx, 7F0h
0x180045b65  mov     rax, [rax+8]
0x180045b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b6e  test    eax, eax
0x180045b70  jz      short loc_180045B7B
0x180045b72  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045b79  jmp     short loc_180045B89
0x180045b7b  lea     rcx, qword_180069A90; this
0x180045b82  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045b89  cmp     byte ptr [rcx+8], 0
0x180045b8d  jz      short loc_180045BB0
0x180045b8f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045b94  cmp     [rax+7CCh], ebx
0x180045b9a  jz      short loc_180045BB0
0x180045b9c  mov     r9d, ebx; int
0x180045b9f  mov     r8d, 11Dh; int
0x180045ba5  mov     rdx, r12; char *
0x180045ba8  mov     rcx, rax; this
0x180045bab  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045bb0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045bb5  cmp     al, 1
0x180045bb7  jb      short loc_180045BDC
0x180045bb9  mov     edx, 1Fh
0x180045bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180045bc5  lea     r8, WPP_0a758c1def7e3974366218a1d0d46647_Traceguids
0x180045bcc  mov     r9, rdi
0x180045bcf  mov     dword ptr [rsp+40h+var_20], ebx
0x180045bd3  mov     rcx, [rcx+10h]
0x180045bd7  call    WPP_SF_qd
0x180045bdc  mov     rcx, [rbp+arg_18]
0x180045be0  test    rcx, rcx
0x180045be3  jz      short loc_180045BF9
0x180045be5  mov     rax, [rcx]
0x180045be8  mov     rax, [rax+10h]
0x180045bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045bf1  mov     [rbp+arg_18], 0
0x180045bf9  mov     rcx, [rbp+var_10]
0x180045bfd  test    rcx, rcx
0x180045c00  jz      short loc_180045C16
0x180045c02  mov     rax, [rcx]
0x180045c05  mov     rax, [rax+10h]
0x180045c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c0e  mov     [rbp+var_10], 0
0x180045c16  lea     rcx, [rbp+arg_0]; this
0x180045c1a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180045c1f  mov     eax, ebx
0x180045c21  mov     rbx, [rsp+40h+arg_8]
0x180045c26  add     rsp, 40h
0x180045c2a  pop     r14
0x180045c2c  pop     r12
0x180045c2e  pop     rdi
0x180045c2f  pop     rsi
0x180045c30  pop     rbp
0x180045c31  retn
```
