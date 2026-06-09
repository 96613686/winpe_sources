# CTranscodeTopoBuilder::GetSelectedSourceStreams(IMFPresentationDescriptor *,CTPtrArray<IMFStreamDescriptor,20> &)

- ea: `0x18003e5dc`
- end: `0x18003e946`
- name: `?GetSelectedSourceStreams@CTranscodeTopoBuilder@@IEAAJPEAUIMFPresentationDescriptor@@AEAV?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@@Z`
- size: `874`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003b8cc`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18001a330`
- `0x18001c280`
- `0x180038b18`
- `0x18003e5dc`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e640`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e746`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e7d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e894`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e640`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e746`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e7d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e894`

## pseudocode

```c
__int64 __fastcall CTranscodeTopoBuilder::GetSelectedSourceStreams(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 v6; // rax
  __int64 v7; // rdx
  int v8; // ebx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  int v13; // esi
  unsigned int i; // edi
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v29[2]; // [rsp+30h] [rbp-10h] BYREF
  int v30; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v31; // [rsp+88h] [rbp+48h] BYREF
  int v32; // [rsp+98h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v30,
    "CTranscodeTopoBuilder::GetSelectedSourceStreams",
    334);
  v6 = *a2;
  v31 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v6 + 264))(a2, &v31);
  if ( v8 >= 0 )
  {
    v13 = 0;
    for ( i = 0; i < v31; ++i )
    {
      v15 = *a2;
      v29[0] = 0;
      v30 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, int *, __int64 *))(v15 + 272))(a2, i, &v30, v29);
      if ( v8 < 0 )
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
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
              "CTranscodeTopoBuilder::GetSelectedSourceStreams",
              347,
              v8);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v21 = 48;
LABEL_39:
          WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids, a1, v8);
        }
LABEL_40:
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v29);
        goto LABEL_53;
      }
      if ( v30 )
      {
        v32 = 0;
        if ( !(unsigned int)CTPtrArray<IMFStreamDescriptor,20>::Add(a3, v29[0], &v32) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
          v8 = -2147024882;
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
            if ( *((_DWORD *)v20 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v20, "CTranscodeTopoBuilder::GetSelectedSourceStreams", 354, -2147024882);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v21 = 49;
            goto LABEL_39;
          }
          goto LABEL_40;
        }
        ++v13;
      }
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v29);
    }
    if ( !v13 )
    {
      v25 = (__int64 *)CallStackTracing::s_wpInstance;
      v8 = -1072873828;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
        CallStackTracing::s_wpInstance = v26;
        if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v25 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v25 + 8) )
      {
        v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
        if ( *((_DWORD *)v27 + 499) != -1072873828 )
          CallStackContext::TraceFailure(v27, "CTranscodeTopoBuilder::GetSelectedSourceStreams", 363, -1072873828);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 50;
        goto LABEL_52;
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
        CallStackContext::TraceFailure(v11, "CTranscodeTopoBuilder::GetSelectedSourceStreams", 340, v8);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 47;
LABEL_52:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids, a1, v8);
    }
  }
LABEL_53:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v30);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003e5dc  push    rbp
0x18003e5de  push    rbx
0x18003e5df  push    rsi
0x18003e5e0  push    rdi
0x18003e5e1  push    r12
0x18003e5e3  push    r14
0x18003e5e5  push    r15
0x18003e5e7  mov     rbp, rsp
0x18003e5ea  sub     rsp, 40h
0x18003e5ee  mov     r12, r8
0x18003e5f1  mov     r15, rdx
0x18003e5f4  mov     r14, rcx
0x18003e5f7  lea     rdx, aCtranscodetopo_8; "CTranscodeTopoBuilder::GetSelectedSourc"...
0x18003e5fe  mov     r8d, 14Eh; int
0x18003e604  lea     rcx, [rbp+arg_0]; this
0x18003e608  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003e60d  mov     rax, [r15]
0x18003e610  lea     rdx, [rbp+arg_8]
0x18003e614  mov     rcx, r15
0x18003e617  mov     [rbp+arg_8], 0
0x18003e61e  mov     rax, [rax+108h]
0x18003e625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e62a  mov     ebx, eax
0x18003e62c  test    eax, eax
0x18003e62e  jns     loc_18003E6C3
0x18003e634  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e63b  test    rcx, rcx
0x18003e63e  jnz     short loc_18003E681
0x18003e640  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003e646  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e64d  mov     rcx, rax
0x18003e650  test    rax, rax
0x18003e653  jz      short loc_18003E673
0x18003e655  mov     rax, [rax]
0x18003e658  mov     edx, 7F0h
0x18003e65d  mov     rax, [rax+8]
0x18003e661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e666  test    eax, eax
0x18003e668  jz      short loc_18003E673
0x18003e66a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e671  jmp     short loc_18003E681
0x18003e673  lea     rcx, qword_180069A90; this
0x18003e67a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e681  cmp     byte ptr [rcx+8], 0
0x18003e685  jz      short loc_18003E6AC
0x18003e687  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003e68c  cmp     [rax+7CCh], ebx
0x18003e692  jz      short loc_18003E6AC
0x18003e694  mov     r9d, ebx; int
0x18003e697  lea     rdx, aCtranscodetopo_8; "CTranscodeTopoBuilder::GetSelectedSourc"...
0x18003e69e  mov     r8d, 154h; int
0x18003e6a4  mov     rcx, rax; this
0x18003e6a7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003e6ac  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003e6b1  cmp     al, 1
0x18003e6b3  jb      loc_18003E92C
0x18003e6b9  mov     edx, 2Fh ; '/'
0x18003e6be  jmp     loc_18003E90E
0x18003e6c3  xor     esi, esi
0x18003e6c5  xor     edi, edi
0x18003e6c7  cmp     edi, [rbp+arg_8]
0x18003e6ca  jnb     loc_18003E87B
0x18003e6d0  mov     rax, [r15]
0x18003e6d3  lea     r9, [rbp+var_10]
0x18003e6d7  lea     r8, [rbp+arg_0]
0x18003e6db  mov     [rbp+var_10], 0
0x18003e6e3  mov     edx, edi
0x18003e6e5  mov     [rbp+arg_0], 0
0x18003e6ec  mov     rcx, r15
0x18003e6ef  mov     rax, [rax+110h]
0x18003e6f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6fb  mov     ebx, eax
0x18003e6fd  test    eax, eax
0x18003e6ff  js      loc_18003E7C9
0x18003e705  cmp     [rbp+arg_0], 0
0x18003e709  jz      short loc_18003E728
0x18003e70b  mov     rdx, [rbp+var_10]
0x18003e70f  lea     r8, [rbp+arg_18]
0x18003e713  mov     rcx, r12
0x18003e716  mov     [rbp+arg_18], 0
0x18003e71d  call    ?Add@?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@QEAAHPEAUIMFStreamDescriptor@@PEAK@Z; CTPtrArray<IMFStreamDescriptor,20>::Add(IMFStreamDescriptor *,ulong *)
0x18003e722  test    eax, eax
0x18003e724  jz      short loc_18003E735
0x18003e726  inc     esi
0x18003e728  lea     rcx, [rbp+var_10]
0x18003e72c  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18003e731  inc     edi
0x18003e733  jmp     short loc_18003E6C7
0x18003e735  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e73c  mov     ebx, 8007000Eh
0x18003e741  test    rcx, rcx
0x18003e744  jnz     short loc_18003E787
0x18003e746  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003e74c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e753  mov     rcx, rax
0x18003e756  test    rax, rax
0x18003e759  jz      short loc_18003E779
0x18003e75b  mov     rax, [rax]
0x18003e75e  mov     edx, 7F0h
0x18003e763  mov     rax, [rax+8]
0x18003e767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e76c  test    eax, eax
0x18003e76e  jz      short loc_18003E779
0x18003e770  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e777  jmp     short loc_18003E787
0x18003e779  lea     rcx, qword_180069A90; this
0x18003e780  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e787  cmp     byte ptr [rcx+8], 0
0x18003e78b  jz      short loc_18003E7B2
0x18003e78d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003e792  cmp     [rax+7CCh], ebx
0x18003e798  jz      short loc_18003E7B2
0x18003e79a  mov     r9d, ebx; int
0x18003e79d  lea     rdx, aCtranscodetopo_8; "CTranscodeTopoBuilder::GetSelectedSourc"...
0x18003e7a4  mov     r8d, 162h; int
0x18003e7aa  mov     rcx, rax; this
0x18003e7ad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003e7b2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003e7b7  cmp     al, 1
0x18003e7b9  jb      loc_18003E86D
0x18003e7bf  mov     edx, 31h ; '1'
0x18003e7c4  jmp     loc_18003E84F
0x18003e7c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e7d0  test    rcx, rcx
0x18003e7d3  jnz     short loc_18003E816
0x18003e7d5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003e7db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e7e2  mov     rcx, rax
0x18003e7e5  test    rax, rax
0x18003e7e8  jz      short loc_18003E808
0x18003e7ea  mov     rax, [rax]
0x18003e7ed  mov     edx, 7F0h
0x18003e7f2  mov     rax, [rax+8]
0x18003e7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7fb  test    eax, eax
0x18003e7fd  jz      short loc_18003E808
0x18003e7ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e806  jmp     short loc_18003E816
0x18003e808  lea     rcx, qword_180069A90; this
0x18003e80f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e816  cmp     byte ptr [rcx+8], 0
0x18003e81a  jz      short loc_18003E841
0x18003e81c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003e821  cmp     [rax+7CCh], ebx
0x18003e827  jz      short loc_18003E841
0x18003e829  mov     r9d, ebx; int
0x18003e82c  lea     rdx, aCtranscodetopo_8; "CTranscodeTopoBuilder::GetSelectedSourc"...
0x18003e833  mov     r8d, 15Bh; int
0x18003e839  mov     rcx, rax; this
0x18003e83c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003e841  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003e846  cmp     al, 1
0x18003e848  jb      short loc_18003E86D
0x18003e84a  mov     edx, 30h ; '0'
0x18003e84f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e856  lea     r8, WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids
0x18003e85d  mov     r9, r14
0x18003e860  mov     [rsp+40h+var_20], ebx
0x18003e864  mov     rcx, [rcx+10h]
0x18003e868  call    WPP_SF_qd
0x18003e86d  lea     rcx, [rbp+var_10]
0x18003e871  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18003e876  jmp     loc_18003E92C
0x18003e87b  test    esi, esi
0x18003e87d  jnz     loc_18003E92C
0x18003e883  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e88a  mov     ebx, 0C00D3E9Ch
0x18003e88f  test    rcx, rcx
0x18003e892  jnz     short loc_18003E8D5
0x18003e894  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003e89a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e8a1  mov     rcx, rax
0x18003e8a4  test    rax, rax
0x18003e8a7  jz      short loc_18003E8C7
0x18003e8a9  mov     rax, [rax]
0x18003e8ac  mov     edx, 7F0h
0x18003e8b1  mov     rax, [rax+8]
0x18003e8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e8ba  test    eax, eax
0x18003e8bc  jz      short loc_18003E8C7
0x18003e8be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e8c5  jmp     short loc_18003E8D5
0x18003e8c7  lea     rcx, qword_180069A90; this
0x18003e8ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e8d5  cmp     byte ptr [rcx+8], 0
0x18003e8d9  jz      short loc_18003E900
0x18003e8db  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003e8e0  cmp     [rax+7CCh], ebx
0x18003e8e6  jz      short loc_18003E900
0x18003e8e8  mov     r9d, ebx; int
0x18003e8eb  lea     rdx, aCtranscodetopo_8; "CTranscodeTopoBuilder::GetSelectedSourc"...
0x18003e8f2  mov     r8d, 16Bh; int
0x18003e8f8  mov     rcx, rax; this
0x18003e8fb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003e900  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003e905  cmp     al, 1
0x18003e907  jb      short loc_18003E92C
0x18003e909  mov     edx, 32h ; '2'
0x18003e90e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e915  lea     r8, WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids
0x18003e91c  mov     r9, r14
0x18003e91f  mov     [rsp+40h+var_20], ebx
0x18003e923  mov     rcx, [rcx+10h]
0x18003e927  call    WPP_SF_qd
0x18003e92c  lea     rcx, [rbp+arg_0]; this
0x18003e930  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003e935  mov     eax, ebx
0x18003e937  add     rsp, 40h
0x18003e93b  pop     r15
0x18003e93d  pop     r14
0x18003e93f  pop     r12
0x18003e941  pop     rdi
0x18003e942  pop     rsi
0x18003e943  pop     rbx
0x18003e944  pop     rbp
0x18003e945  retn
```
