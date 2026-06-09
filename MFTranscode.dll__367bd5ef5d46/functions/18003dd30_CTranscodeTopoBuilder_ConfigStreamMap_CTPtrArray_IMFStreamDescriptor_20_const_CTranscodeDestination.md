# CTranscodeTopoBuilder::ConfigStreamMap(CTPtrArray<IMFStreamDescriptor,20> const &,CTranscodeDestination *)

- ea: `0x18003dd30`
- end: `0x18003e1b4`
- name: `?ConfigStreamMap@CTranscodeTopoBuilder@@IEAAJAEBV?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@PEAVCTranscodeDestination@@@Z`
- size: `1156`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003b8cc`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x18001ce18`
- `0x180038974`
- `0x18003dd30`
- `0x18003f60c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003dea5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003df34`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003dfc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e052`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e0e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003dea5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003df34`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003dfc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e052`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e0e1`

## string_xrefs

- `0x18003dd5e`: `CTranscodeTopoBuilder::ConfigStreamMap`
- `0x18003defc`: `CTranscodeTopoBuilder::ConfigStreamMap`
- `0x18003df8b`: `CTranscodeTopoBuilder::ConfigStreamMap`
- `0x18003e01a`: `CTranscodeTopoBuilder::ConfigStreamMap`
- `0x18003e0a9`: `CTranscodeTopoBuilder::ConfigStreamMap`
- `0x18003e138`: `CTranscodeTopoBuilder::ConfigStreamMap`

## pseudocode

```c
__int64 __fastcall CTranscodeTopoBuilder::ConfigStreamMap(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // ebx
  unsigned int i; // esi
  __int64 v8; // rax
  __int64 v9; // r14
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v32[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v33; // [rsp+38h] [rbp-31h] BYREF
  __int64 v34; // [rsp+40h] [rbp-29h] BYREF
  int v35; // [rsp+48h] [rbp-21h] BYREF
  int v36; // [rsp+4Ch] [rbp-1Dh] BYREF
  int v37; // [rsp+50h] [rbp-19h] BYREF
  int v38; // [rsp+58h] [rbp-11h] BYREF
  GUID v39; // [rsp+5Ch] [rbp-Dh]
  GUID v40; // [rsp+70h] [rbp+7h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v32, "CTranscodeTopoBuilder::ConfigStreamMap", 373);
  v6 = 0;
  for ( i = 0; i < *(_DWORD *)(a2 + 200); ++i )
  {
    v34 = 0;
    v33 = 0;
    v40 = GUID_00000000_0000_0000_0000_000000000000;
    v37 = 0;
    v36 = 0;
    v35 = 0;
    v8 = CTPtrArray<IMFStreamDescriptor,20>::operator[](a2, i);
    ComSmartPtr<IMFStreamDescriptor>::operator=(&v34, v8);
    v9 = v34;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 272LL))(v34, &v33);
    if ( v6 < 0 )
    {
      v28 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v29;
        if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
        {
          v28 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v28 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v28 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeTopoBuilder::ConfigStreamMap", 388, v6);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_61;
      v18 = 52;
LABEL_60:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids, a1, v6);
      goto LABEL_61;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v33 + 64LL))(v33, &v40);
    if ( v6 < 0 )
    {
      v25 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
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
        if ( *((_DWORD *)v27 + 499) != v6 )
          CallStackContext::TraceFailure(v27, "CTranscodeTopoBuilder::ConfigStreamMap", 389, v6);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_61;
      v18 = 53;
      goto LABEL_60;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 264LL))(v9, &v37);
    if ( v6 < 0 )
    {
      v22 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
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
        if ( *((_DWORD *)v24 + 499) != v6 )
          CallStackContext::TraceFailure(v24, "CTranscodeTopoBuilder::ConfigStreamMap", 390, v6);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_61;
      v18 = 54;
      goto LABEL_60;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, GUID *, int *, int *))(*(_QWORD *)a3 + 32LL))(a3, &v40, &v35, &v36);
    if ( v6 < 0 )
    {
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
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
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != v6 )
          CallStackContext::TraceFailure(v21, "CTranscodeTopoBuilder::ConfigStreamMap", 391, v6);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_61;
      v18 = 55;
      goto LABEL_60;
    }
    if ( v35 )
    {
      v38 = v36;
      v39 = v40;
      v6 = CTBucketHash<unsigned long,StreamSinkInfo>::Insert(a1 + 8, &v37, &v38);
      if ( v6 < 0 )
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
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
          if ( *((_DWORD *)v17 + 499) != v6 )
            CallStackContext::TraceFailure(v17, "CTranscodeTopoBuilder::ConfigStreamMap", 397, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v18 = 56;
          goto LABEL_60;
        }
LABEL_61:
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v33);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v34);
        break;
      }
    }
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v33);
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v34);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v32);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003dd30  push    rbp
0x18003dd32  push    rbx
0x18003dd33  push    rsi
0x18003dd34  push    rdi
0x18003dd35  push    r12
0x18003dd37  push    r14
0x18003dd39  push    r15
0x18003dd3b  lea     rbp, [rsp-27h]
0x18003dd40  sub     rsp, 90h
0x18003dd47  mov     rax, cs:__security_cookie
0x18003dd4e  xor     rax, rsp
0x18003dd51  mov     [rbp+57h+var_40], rax
0x18003dd55  mov     r12, r8
0x18003dd58  mov     r15, rdx
0x18003dd5b  mov     rdi, rcx
0x18003dd5e  lea     rdx, aCtranscodetopo_9; "CTranscodeTopoBuilder::ConfigStreamMap"
0x18003dd65  mov     r8d, 175h; int
0x18003dd6b  lea     rcx, [rbp+57h+var_90]; this
0x18003dd6f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003dd74  xor     ebx, ebx
0x18003dd76  xor     esi, esi
0x18003dd78  cmp     esi, [r15+0C8h]
0x18003dd7f  jnb     loc_18003E18B
0x18003dd85  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003dd8c  mov     edx, esi
0x18003dd8e  mov     [rbp+57h+var_80], 0
0x18003dd96  mov     rcx, r15
0x18003dd99  mov     [rbp+57h+var_88], 0
0x18003dda1  movdqu  [rbp+57h+var_50], xmm0
0x18003dda6  mov     [rbp+57h+var_70], 0
0x18003ddad  mov     [rbp+57h+var_74], 0
0x18003ddb4  mov     [rbp+57h+var_78], 0
0x18003ddbb  call    ??A?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@QEBAPEAUIMFStreamDescriptor@@K@Z; CTPtrArray<IMFStreamDescriptor,20>::operator[](ulong)
0x18003ddc0  mov     rdx, rax
0x18003ddc3  lea     rcx, [rbp+57h+var_80]
0x18003ddc7  call    ??4?$ComSmartPtr@UIMFStreamDescriptor@@@@QEAAPEAUIMFStreamDescriptor@@PEAU1@@Z; ComSmartPtr<IMFStreamDescriptor>::operator=(IMFStreamDescriptor *)
0x18003ddcc  mov     r14, [rbp+57h+var_80]
0x18003ddd0  lea     rdx, [rbp+57h+var_88]
0x18003ddd4  mov     rcx, r14
0x18003ddd7  mov     rax, [r14]
0x18003ddda  mov     rax, [rax+110h]
0x18003dde1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dde6  mov     ebx, eax
0x18003dde8  test    eax, eax
0x18003ddea  js      loc_18003E0D5
0x18003ddf0  mov     rcx, [rbp+57h+var_88]
0x18003ddf4  lea     rdx, [rbp+57h+var_50]
0x18003ddf8  mov     rax, [rcx]
0x18003ddfb  mov     rax, [rax+40h]
0x18003ddff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de04  mov     ebx, eax
0x18003de06  test    eax, eax
0x18003de08  js      loc_18003E046
0x18003de0e  mov     rax, [r14]
0x18003de11  lea     rdx, [rbp+57h+var_70]
0x18003de15  mov     rcx, r14
0x18003de18  mov     rax, [rax+108h]
0x18003de1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de24  mov     ebx, eax
0x18003de26  test    eax, eax
0x18003de28  js      loc_18003DFB7
0x18003de2e  mov     rax, [r12]
0x18003de32  lea     r9, [rbp+57h+var_74]
0x18003de36  lea     r8, [rbp+57h+var_78]
0x18003de3a  mov     rcx, r12
0x18003de3d  lea     rdx, [rbp+57h+var_50]
0x18003de41  mov     rax, [rax+20h]
0x18003de45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de4a  mov     ebx, eax
0x18003de4c  test    eax, eax
0x18003de4e  js      loc_18003DF28
0x18003de54  cmp     [rbp+57h+var_78], 0
0x18003de58  jz      short loc_18003DE80
0x18003de5a  movups  xmm0, [rbp+57h+var_50]
0x18003de5e  mov     eax, [rbp+57h+var_74]
0x18003de61  lea     rcx, [rdi+8]
0x18003de65  lea     r8, [rbp+57h+var_68]
0x18003de69  mov     [rbp+57h+var_68], eax
0x18003de6c  lea     rdx, [rbp+57h+var_70]
0x18003de70  movdqu  [rbp+57h+var_64], xmm0
0x18003de75  call    ?Insert@?$CTBucketHash@KUStreamSinkInfo@@@@QEAAJAEBKAEBUStreamSinkInfo@@@Z; CTBucketHash<ulong,StreamSinkInfo>::Insert(ulong const &,StreamSinkInfo const &)
0x18003de7a  mov     ebx, eax
0x18003de7c  test    eax, eax
0x18003de7e  js      short loc_18003DE99
0x18003de80  lea     rcx, [rbp+57h+var_88]
0x18003de84  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18003de89  lea     rcx, [rbp+57h+var_80]
0x18003de8d  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18003de92  inc     esi
0x18003de94  jmp     loc_18003DD78
0x18003de99  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dea0  test    rcx, rcx
0x18003dea3  jnz     short loc_18003DEE6
0x18003dea5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003deab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003deb2  mov     rcx, rax
0x18003deb5  test    rax, rax
0x18003deb8  jz      short loc_18003DED8
0x18003deba  mov     rax, [rax]
0x18003debd  mov     edx, 7F0h
0x18003dec2  mov     rax, [rax+8]
0x18003dec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003decb  test    eax, eax
0x18003decd  jz      short loc_18003DED8
0x18003decf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ded6  jmp     short loc_18003DEE6
0x18003ded8  lea     rcx, qword_180069A90; this
0x18003dedf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dee6  cmp     byte ptr [rcx+8], 0
0x18003deea  jz      short loc_18003DF11
0x18003deec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003def1  cmp     [rax+7CCh], ebx
0x18003def7  jz      short loc_18003DF11
0x18003def9  mov     r9d, ebx; int
0x18003defc  lea     rdx, aCtranscodetopo_9; "CTranscodeTopoBuilder::ConfigStreamMap"
0x18003df03  mov     r8d, 18Dh; int
0x18003df09  mov     rcx, rax; this
0x18003df0c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003df11  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003df16  cmp     al, 1
0x18003df18  jb      loc_18003E179
0x18003df1e  mov     edx, 38h ; '8'
0x18003df23  jmp     loc_18003E15B
0x18003df28  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003df2f  test    rcx, rcx
0x18003df32  jnz     short loc_18003DF75
0x18003df34  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003df3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003df41  mov     rcx, rax
0x18003df44  test    rax, rax
0x18003df47  jz      short loc_18003DF67
0x18003df49  mov     rax, [rax]
0x18003df4c  mov     edx, 7F0h
0x18003df51  mov     rax, [rax+8]
0x18003df55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df5a  test    eax, eax
0x18003df5c  jz      short loc_18003DF67
0x18003df5e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003df65  jmp     short loc_18003DF75
0x18003df67  lea     rcx, qword_180069A90; this
0x18003df6e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003df75  cmp     byte ptr [rcx+8], 0
0x18003df79  jz      short loc_18003DFA0
0x18003df7b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003df80  cmp     [rax+7CCh], ebx
0x18003df86  jz      short loc_18003DFA0
0x18003df88  mov     r9d, ebx; int
0x18003df8b  lea     rdx, aCtranscodetopo_9; "CTranscodeTopoBuilder::ConfigStreamMap"
0x18003df92  mov     r8d, 187h; int
0x18003df98  mov     rcx, rax; this
0x18003df9b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003dfa0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003dfa5  cmp     al, 1
0x18003dfa7  jb      loc_18003E179
0x18003dfad  mov     edx, 37h ; '7'
0x18003dfb2  jmp     loc_18003E15B
0x18003dfb7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dfbe  test    rcx, rcx
0x18003dfc1  jnz     short loc_18003E004
0x18003dfc3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003dfc9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dfd0  mov     rcx, rax
0x18003dfd3  test    rax, rax
0x18003dfd6  jz      short loc_18003DFF6
0x18003dfd8  mov     rax, [rax]
0x18003dfdb  mov     edx, 7F0h
0x18003dfe0  mov     rax, [rax+8]
0x18003dfe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dfe9  test    eax, eax
0x18003dfeb  jz      short loc_18003DFF6
0x18003dfed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dff4  jmp     short loc_18003E004
0x18003dff6  lea     rcx, qword_180069A90; this
0x18003dffd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e004  cmp     byte ptr [rcx+8], 0
0x18003e008  jz      short loc_18003E02F
0x18003e00a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003e00f  cmp     [rax+7CCh], ebx
0x18003e015  jz      short loc_18003E02F
0x18003e017  mov     r9d, ebx; int
0x18003e01a  lea     rdx, aCtranscodetopo_9; "CTranscodeTopoBuilder::ConfigStreamMap"
0x18003e021  mov     r8d, 186h; int
0x18003e027  mov     rcx, rax; this
0x18003e02a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003e02f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003e034  cmp     al, 1
0x18003e036  jb      loc_18003E179
0x18003e03c  mov     edx, 36h ; '6'
0x18003e041  jmp     loc_18003E15B
0x18003e046  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e04d  test    rcx, rcx
0x18003e050  jnz     short loc_18003E093
0x18003e052  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003e058  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e05f  mov     rcx, rax
0x18003e062  test    rax, rax
0x18003e065  jz      short loc_18003E085
0x18003e067  mov     rax, [rax]
0x18003e06a  mov     edx, 7F0h
0x18003e06f  mov     rax, [rax+8]
0x18003e073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e078  test    eax, eax
0x18003e07a  jz      short loc_18003E085
0x18003e07c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e083  jmp     short loc_18003E093
0x18003e085  lea     rcx, qword_180069A90; this
0x18003e08c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e093  cmp     byte ptr [rcx+8], 0
0x18003e097  jz      short loc_18003E0BE
0x18003e099  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003e09e  cmp     [rax+7CCh], ebx
0x18003e0a4  jz      short loc_18003E0BE
0x18003e0a6  mov     r9d, ebx; int
0x18003e0a9  lea     rdx, aCtranscodetopo_9; "CTranscodeTopoBuilder::ConfigStreamMap"
0x18003e0b0  mov     r8d, 185h; int
0x18003e0b6  mov     rcx, rax; this
0x18003e0b9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003e0be  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003e0c3  cmp     al, 1
0x18003e0c5  jb      loc_18003E179
0x18003e0cb  mov     edx, 35h ; '5'
0x18003e0d0  jmp     loc_18003E15B
0x18003e0d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e0dc  test    rcx, rcx
0x18003e0df  jnz     short loc_18003E122
0x18003e0e1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003e0e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e0ee  mov     rcx, rax
0x18003e0f1  test    rax, rax
0x18003e0f4  jz      short loc_18003E114
0x18003e0f6  mov     rax, [rax]
0x18003e0f9  mov     edx, 7F0h
0x18003e0fe  mov     rax, [rax+8]
0x18003e102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e107  test    eax, eax
0x18003e109  jz      short loc_18003E114
0x18003e10b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e112  jmp     short loc_18003E122
0x18003e114  lea     rcx, qword_180069A90; this
0x18003e11b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e122  cmp     byte ptr [rcx+8], 0
0x18003e126  jz      short loc_18003E14D
0x18003e128  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003e12d  cmp     [rax+7CCh], ebx
0x18003e133  jz      short loc_18003E14D
0x18003e135  mov     r9d, ebx; int
0x18003e138  lea     rdx, aCtranscodetopo_9; "CTranscodeTopoBuilder::ConfigStreamMap"
0x18003e13f  mov     r8d, 184h; int
0x18003e145  mov     rcx, rax; this
0x18003e148  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003e14d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003e152  cmp     al, 1
0x18003e154  jb      short loc_18003E179
0x18003e156  mov     edx, 34h ; '4'
0x18003e15b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e162  lea     r8, WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids
0x18003e169  mov     r9, rdi
0x18003e16c  mov     [rsp+0C0h+var_A0], ebx
0x18003e170  mov     rcx, [rcx+10h]
0x18003e174  call    WPP_SF_qd
0x18003e179  lea     rcx, [rbp+57h+var_88]
0x18003e17d  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18003e182  lea     rcx, [rbp+57h+var_80]
0x18003e186  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18003e18b  lea     rcx, [rbp+57h+var_90]; this
0x18003e18f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003e194  mov     eax, ebx
0x18003e196  mov     rcx, [rbp+57h+var_40]
0x18003e19a  xor     rcx, rsp; StackCookie
0x18003e19d  call    __security_check_cookie
0x18003e1a2  add     rsp, 90h
0x18003e1a9  pop     r15
0x18003e1ab  pop     r14
0x18003e1ad  pop     r12
0x18003e1af  pop     rdi
0x18003e1b0  pop     rsi
0x18003e1b1  pop     rbx
0x18003e1b2  pop     rbp
0x18003e1b3  retn
```
