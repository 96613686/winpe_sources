# CTranscodeProfileAdjuster::FindMatchedSrcStream(_GUID const &,CTPtrArray<IMFStreamDescriptor,20> const &,int *,ulong *)

- ea: `0x18000a940`
- end: `0x18000abc2`
- name: `?FindMatchedSrcStream@CTranscodeProfileAdjuster@@IEAAJAEBU_GUID@@AEBV?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@PEAHPEAK@Z`
- size: `642`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180039450`
- `0x180039a70`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18000a940`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x18001ce18`
- `0x180038974`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000aa5a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000aae9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000aa5a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000aae9`

## pseudocode

```c
__int64 __fastcall CTranscodeProfileAdjuster::FindMatchedSrcStream(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        _DWORD *a4,
        unsigned int *a5)
{
  int v9; // ebx
  unsigned int v10; // edi
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v23[8]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v24; // [rsp+38h] [rbp-28h] BYREF
  __int64 v25; // [rsp+40h] [rbp-20h] BYREF
  GUID v26; // [rsp+48h] [rbp-18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v23,
    "CTranscodeProfileAdjuster::FindMatchedSrcStream",
    877);
  v9 = 0;
  *a4 = 0;
  v10 = 0;
  *a5 = 0;
  while ( v10 < *(_DWORD *)(a3 + 200) )
  {
    v25 = 0;
    v24 = 0;
    v26 = GUID_00000000_0000_0000_0000_000000000000;
    v11 = CTPtrArray<IMFStreamDescriptor,20>::operator[](a3, v10);
    ComSmartPtr<IMFStreamDescriptor>::operator=(&v25, v11);
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 272LL))(v25, &v24);
    if ( v9 < 0 )
    {
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CTranscodeProfileAdjuster::FindMatchedSrcStream",
            891,
            v9);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_31;
      v18 = 137;
LABEL_30:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids, a1, v9);
      goto LABEL_31;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v24 + 64LL))(v24, &v26);
    if ( v9 < 0 )
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
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
        if ( *((_DWORD *)v17 + 499) != v9 )
          CallStackContext::TraceFailure(v17, "CTranscodeProfileAdjuster::FindMatchedSrcStream", 892, v9);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_31;
      v18 = 138;
      goto LABEL_30;
    }
    v14 = *(_QWORD *)&v26.Data1 - *a2;
    if ( *(_QWORD *)&v26.Data1 == *a2 )
      v14 = *(_QWORD *)v26.Data4 - a2[1];
    if ( !v14 )
    {
      *a4 = 1;
      *a5 = v10;
LABEL_31:
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v24);
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v25);
      break;
    }
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v24);
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v25);
    ++v10;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v23);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000a940  mov     [rsp-38h+arg_8], rbx
0x18000a945  push    rbp
0x18000a946  push    rsi
0x18000a947  push    rdi
0x18000a948  push    r12
0x18000a94a  push    r13
0x18000a94c  push    r14
0x18000a94e  push    r15
0x18000a950  mov     rbp, rsp
0x18000a953  sub     rsp, 60h
0x18000a957  mov     rax, cs:__security_cookie
0x18000a95e  xor     rax, rsp
0x18000a961  mov     [rbp+var_8], rax
0x18000a965  mov     r15, [rbp+arg_20]
0x18000a969  mov     r12, r8
0x18000a96c  mov     rsi, rdx
0x18000a96f  mov     r13, rcx
0x18000a972  mov     r8d, 36Dh; int
0x18000a978  lea     rdx, aCtranscodeprof_7; "CTranscodeProfileAdjuster::FindMatchedS"...
0x18000a97f  lea     rcx, [rbp+var_30]; this
0x18000a983  mov     r14, r9
0x18000a986  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000a98b  xor     ebx, ebx
0x18000a98d  mov     [r14], ebx
0x18000a990  xor     edi, edi
0x18000a992  mov     [r15], ebx
0x18000a995  cmp     edi, [r12+0C8h]
0x18000a99d  jnb     loc_18000AB93
0x18000a9a3  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000a9aa  mov     edx, edi
0x18000a9ac  mov     [rbp+var_20], 0
0x18000a9b4  mov     rcx, r12
0x18000a9b7  mov     [rbp+var_28], 0
0x18000a9bf  movdqu  [rbp+var_18], xmm0
0x18000a9c4  call    ??A?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@QEBAPEAUIMFStreamDescriptor@@K@Z; CTPtrArray<IMFStreamDescriptor,20>::operator[](ulong)
0x18000a9c9  mov     rdx, rax
0x18000a9cc  lea     rcx, [rbp+var_20]
0x18000a9d0  call    ??4?$ComSmartPtr@UIMFStreamDescriptor@@@@QEAAPEAUIMFStreamDescriptor@@PEAU1@@Z; ComSmartPtr<IMFStreamDescriptor>::operator=(IMFStreamDescriptor *)
0x18000a9d5  mov     rcx, [rbp+var_20]
0x18000a9d9  lea     rdx, [rbp+var_28]
0x18000a9dd  mov     rax, [rcx]
0x18000a9e0  mov     rax, [rax+110h]
0x18000a9e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9ec  mov     ebx, eax
0x18000a9ee  test    eax, eax
0x18000a9f0  js      loc_18000AADD
0x18000a9f6  mov     rcx, [rbp+var_28]
0x18000a9fa  lea     rdx, [rbp+var_18]
0x18000a9fe  mov     rax, [rcx]
0x18000aa01  mov     rax, [rax+40h]
0x18000aa05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa0a  mov     ebx, eax
0x18000aa0c  test    eax, eax
0x18000aa0e  js      short loc_18000AA4E
0x18000aa10  mov     rax, qword ptr [rbp+var_18]
0x18000aa14  sub     rax, [rsi]
0x18000aa17  jnz     short loc_18000AA21
0x18000aa19  mov     rax, qword ptr [rbp+var_18+8]
0x18000aa1d  sub     rax, [rsi+8]
0x18000aa21  lea     rcx, [rbp+var_28]
0x18000aa25  test    rax, rax
0x18000aa28  jz      short loc_18000AA3F
0x18000aa2a  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18000aa2f  lea     rcx, [rbp+var_20]
0x18000aa33  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18000aa38  inc     edi
0x18000aa3a  jmp     loc_18000A995
0x18000aa3f  mov     dword ptr [r14], 1
0x18000aa46  mov     [r15], edi
0x18000aa49  jmp     loc_18000AB85
0x18000aa4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000aa55  test    rcx, rcx
0x18000aa58  jnz     short loc_18000AA9B
0x18000aa5a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000aa60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000aa67  mov     rcx, rax
0x18000aa6a  test    rax, rax
0x18000aa6d  jz      short loc_18000AA8D
0x18000aa6f  mov     rax, [rax]
0x18000aa72  mov     edx, 7F0h
0x18000aa77  mov     rax, [rax+8]
0x18000aa7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa80  test    eax, eax
0x18000aa82  jz      short loc_18000AA8D
0x18000aa84  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000aa8b  jmp     short loc_18000AA9B
0x18000aa8d  lea     rcx, qword_180069A90; this
0x18000aa94  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000aa9b  cmp     byte ptr [rcx+8], 0
0x18000aa9f  jz      short loc_18000AAC6
0x18000aaa1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000aaa6  cmp     [rax+7CCh], ebx
0x18000aaac  jz      short loc_18000AAC6
0x18000aaae  mov     r9d, ebx; int
0x18000aab1  lea     rdx, aCtranscodeprof_7; "CTranscodeProfileAdjuster::FindMatchedS"...
0x18000aab8  mov     r8d, 37Ch; int
0x18000aabe  mov     rcx, rax; this
0x18000aac1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000aac6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000aacb  cmp     al, 1
0x18000aacd  jb      loc_18000AB81
0x18000aad3  mov     edx, 8Ah
0x18000aad8  jmp     loc_18000AB63
0x18000aadd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000aae4  test    rcx, rcx
0x18000aae7  jnz     short loc_18000AB2A
0x18000aae9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000aaef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000aaf6  mov     rcx, rax
0x18000aaf9  test    rax, rax
0x18000aafc  jz      short loc_18000AB1C
0x18000aafe  mov     rax, [rax]
0x18000ab01  mov     edx, 7F0h
0x18000ab06  mov     rax, [rax+8]
0x18000ab0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab0f  test    eax, eax
0x18000ab11  jz      short loc_18000AB1C
0x18000ab13  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ab1a  jmp     short loc_18000AB2A
0x18000ab1c  lea     rcx, qword_180069A90; this
0x18000ab23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ab2a  cmp     byte ptr [rcx+8], 0
0x18000ab2e  jz      short loc_18000AB55
0x18000ab30  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000ab35  cmp     [rax+7CCh], ebx
0x18000ab3b  jz      short loc_18000AB55
0x18000ab3d  mov     r9d, ebx; int
0x18000ab40  lea     rdx, aCtranscodeprof_7; "CTranscodeProfileAdjuster::FindMatchedS"...
0x18000ab47  mov     r8d, 37Bh; int
0x18000ab4d  mov     rcx, rax; this
0x18000ab50  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000ab55  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000ab5a  cmp     al, 1
0x18000ab5c  jb      short loc_18000AB81
0x18000ab5e  mov     edx, 89h
0x18000ab63  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab6a  lea     r8, WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids
0x18000ab71  mov     r9, r13
0x18000ab74  mov     [rsp+60h+var_40], ebx
0x18000ab78  mov     rcx, [rcx+10h]
0x18000ab7c  call    WPP_SF_qd
0x18000ab81  lea     rcx, [rbp+var_28]
0x18000ab85  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18000ab8a  lea     rcx, [rbp+var_20]
0x18000ab8e  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18000ab93  lea     rcx, [rbp+var_30]; this
0x18000ab97  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000ab9c  mov     eax, ebx
0x18000ab9e  mov     rcx, [rbp+var_8]
0x18000aba2  xor     rcx, rsp; StackCookie
0x18000aba5  call    __security_check_cookie
0x18000abaa  mov     rbx, [rsp+60h+arg_8]
0x18000abb2  add     rsp, 60h
0x18000abb6  pop     r15
0x18000abb8  pop     r14
0x18000abba  pop     r13
0x18000abbc  pop     r12
0x18000abbe  pop     rdi
0x18000abbf  pop     rsi
0x18000abc0  pop     rbp
0x18000abc1  retn
```
