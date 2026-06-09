# CASFTranscodeDestination::SetDeviceNeededMetadataOnStream(CTBucketHash<ulong,StreamSinkInfo> &,_GUID const &,IMFAttributes *,IMFMetadataProvider *)

- ea: `0x180045c38`
- end: `0x180045f44`
- name: `?SetDeviceNeededMetadataOnStream@CASFTranscodeDestination@@IEAAJAEAV?$CTBucketHash@KUStreamSinkInfo@@@@AEBU_GUID@@PEAUIMFAttributes@@PEAUIMFMetadataProvider@@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800458d0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000ee40`
- `0x18001a320`
- `0x18001a330`
- `0x18001c280`
- `0x180038114`
- `0x180045c38`
- `0x180045f4c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045f00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045f00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045d4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045e42`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045d4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045e42`
- `MFPlat!DestroyPropVariant` at `0x180045f12`
- `MFPlat!DestroyPropVariant` at `0x180045f1c`
- `MFPlat!DestroyPropVariant` at `0x180045f12`
- `MFPlat!DestroyPropVariant` at `0x180045f1c`

## string_xrefs

- `0x180045e05`: `DeviceConformanceTemplate`

## pseudocode

```c
__int64 __fastcall CASFTranscodeDestination::SetDeviceNeededMetadataOnStream(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5)
{
  int v9; // ebx
  __int64 v10; // rax
  int v11; // edx
  int v12; // r8d
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  LPVOID pv; // [rsp+30h] [rbp-41h] BYREF
  __int64 v24; // [rsp+38h] [rbp-39h] BYREF
  _BYTE v25[20]; // [rsp+40h] [rbp-31h] BYREF
  __int128 v26; // [rsp+58h] [rbp-19h] BYREF
  __int64 v27; // [rsp+68h] [rbp-9h]
  __int128 v28; // [rsp+70h] [rbp-1h] BYREF
  __int128 v29; // [rsp+80h] [rbp+Fh] BYREF
  __int64 v30; // [rsp+90h] [rbp+1Fh]
  int v31; // [rsp+D0h] [rbp+5Fh] BYREF
  int v32; // [rsp+E8h] [rbp+77h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v31,
    "CASFTranscodeDestination::SetDeviceNeededMetadataOnStream",
    301);
  v9 = 0;
  pv = 0;
  v32 = 0;
  v24 = 0;
  v27 = 0;
  v30 = 0;
  v28 = 0;
  v26 = 0;
  v29 = 0;
  if ( a4 && (unsigned int)CTBucketHash<unsigned long,StreamSinkInfo>::GetFirstPosition(a2, &v28) )
  {
    v31 = 0;
    memset(v25, 0, sizeof(v25));
    do
    {
      if ( !(unsigned int)CTBucketHash<unsigned long,StreamSinkInfo>::GetNext(a2, &v28, &v31, v25) )
        goto LABEL_38;
      v10 = *a3 - *(_QWORD *)&v25[4];
      if ( *a3 == *(_QWORD *)&v25[4] )
        v10 = a3[1] - *(_QWORD *)&v25[12];
    }
    while ( v10 );
    if ( _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel() >= 0x20u )
      WPP_SF_qS(*((_QWORD *)WPP_GLOBAL_Control + 7), v11, v12, a1, 0);
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)a5 + 24LL))(
           a5,
           0,
           *(unsigned int *)v25,
           0,
           &v24);
    if ( v9 >= 0 )
    {
      if ( (*(int (__fastcall **)(__int64, const IID *, LPVOID *, int *))(*(_QWORD *)a4 + 104LL))(
             a4,
             &MF_TRANSCODE_ENCODINGPROFILE,
             &pv,
             &v32) < 0 )
        goto LABEL_34;
      LOWORD(v26) = 31;
      *((_QWORD *)&v26 + 1) = pv;
      pv = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, __int128 *))(*(_QWORD *)v24 + 48LL))(
             v24,
             L"DeviceConformanceTemplate",
             &v26);
      if ( v9 >= 0 )
        goto LABEL_34;
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
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
            "CASFTranscodeDestination::SetDeviceNeededMetadataOnStream",
            345,
            v9);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_34;
      v17 = 35;
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
        if ( *((_DWORD *)v16 + 499) != v9 )
          CallStackContext::TraceFailure(v16, "CASFTranscodeDestination::SetDeviceNeededMetadataOnStream", 335, v9);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_34;
      v17 = 34;
    }
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_0a758c1def7e3974366218a1d0d46647_Traceguids, a1, v9);
LABEL_34:
    if ( v24 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      v24 = 0;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
  }
LABEL_38:
  DestroyPropVariant(&v26);
  DestroyPropVariant(&v29);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v31);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180045c38  mov     [rsp-8+arg_8], rbx
0x180045c3d  push    rbp
0x180045c3e  push    rsi
0x180045c3f  push    rdi
0x180045c40  push    r14
0x180045c42  push    r15
0x180045c44  lea     rbp, [rsp-2Fh]
0x180045c49  sub     rsp, 0A0h
0x180045c50  mov     rdi, r8
0x180045c53  mov     rsi, rdx
0x180045c56  mov     r14, rcx
0x180045c59  lea     rdx, aCasftranscoded_6; "CASFTranscodeDestination::SetDeviceNeed"...
0x180045c60  mov     r8d, 12Dh; int
0x180045c66  lea     rcx, [rbp+4Fh+arg_0]; this
0x180045c6a  mov     r15, r9
0x180045c6d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180045c72  xor     ebx, ebx
0x180045c74  xor     eax, eax
0x180045c76  mov     [rbp+4Fh+pv], rbx
0x180045c7a  xorps   xmm0, xmm0
0x180045c7d  mov     [rbp+4Fh+arg_18], ebx
0x180045c80  xorps   xmm1, xmm1
0x180045c83  mov     [rbp+4Fh+var_88], rbx
0x180045c87  mov     [rbp+4Fh+var_58], rax
0x180045c8b  mov     [rbp+4Fh+var_30], rax
0x180045c8f  movups  [rbp+4Fh+var_50], xmm0
0x180045c93  movups  [rbp+4Fh+var_68], xmm1
0x180045c97  movups  [rbp+4Fh+var_40], xmm0
0x180045c9b  test    r15, r15
0x180045c9e  jz      loc_180045F0E
0x180045ca4  lea     rdx, [rbp+4Fh+var_50]
0x180045ca8  mov     rcx, rsi
0x180045cab  call    ?GetFirstPosition@?$CTBucketHash@KUStreamSinkInfo@@@@QEAAHAEAU_POSITION@1@@Z; CTBucketHash<ulong,StreamSinkInfo>::GetFirstPosition(CTBucketHash<ulong,StreamSinkInfo>::_POSITION &)
0x180045cb0  test    eax, eax
0x180045cb2  jz      loc_180045F0E
0x180045cb8  xor     eax, eax
0x180045cba  mov     [rbp+4Fh+var_70], eax
0x180045cbd  mov     [rbp+4Fh+arg_0], eax
0x180045cc0  movups  [rbp+4Fh+var_80], xmm0
0x180045cc4  lea     r9, [rbp+4Fh+var_80]
0x180045cc8  mov     rcx, rsi
0x180045ccb  lea     r8, [rbp+4Fh+arg_0]
0x180045ccf  lea     rdx, [rbp+4Fh+var_50]
0x180045cd3  call    ?GetNext@?$CTBucketHash@KUStreamSinkInfo@@@@QEAAHAEAU_POSITION@1@AEAKAEAUStreamSinkInfo@@@Z; CTBucketHash<ulong,StreamSinkInfo>::GetNext(CTBucketHash<ulong,StreamSinkInfo>::_POSITION &,ulong &,StreamSinkInfo &)
0x180045cd8  test    eax, eax
0x180045cda  jz      loc_180045F0E
0x180045ce0  mov     rax, [rdi]
0x180045ce3  sub     rax, qword ptr [rbp+4Fh+var_80+4]
0x180045ce7  jnz     short loc_180045CF1
0x180045ce9  mov     rax, [rdi+8]
0x180045ced  sub     rax, qword ptr [rbp+4Fh+var_80+0Ch]
0x180045cf1  test    rax, rax
0x180045cf4  jnz     short loc_180045CC4
0x180045cf6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PIPELINE@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel(void)
0x180045cfb  cmp     al, 20h ; ' '
0x180045cfd  jb      short loc_180045D17
0x180045cff  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d06  mov     r9, r14
0x180045d09  mov     [rsp+0C0h+var_A0], rbx
0x180045d0e  mov     rcx, [rcx+38h]
0x180045d12  call    WPP_SF_qS
0x180045d17  mov     rcx, [rbp+4Fh+arg_20]
0x180045d1b  lea     rdx, [rbp+4Fh+var_88]
0x180045d1f  mov     r8d, dword ptr [rbp+4Fh+var_80]
0x180045d23  xor     r9d, r9d
0x180045d26  mov     [rsp+0C0h+var_A0], rdx
0x180045d2b  xor     edx, edx
0x180045d2d  mov     rax, [rcx]
0x180045d30  mov     rax, [rax+18h]
0x180045d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d39  mov     ebx, eax
0x180045d3b  test    eax, eax
0x180045d3d  jns     loc_180045DD2
0x180045d43  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045d4a  test    rcx, rcx
0x180045d4d  jnz     short loc_180045D90
0x180045d4f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045d55  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045d5c  mov     rcx, rax
0x180045d5f  test    rax, rax
0x180045d62  jz      short loc_180045D82
0x180045d64  mov     rax, [rax]
0x180045d67  mov     edx, 7F0h
0x180045d6c  mov     rax, [rax+8]
0x180045d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d75  test    eax, eax
0x180045d77  jz      short loc_180045D82
0x180045d79  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045d80  jmp     short loc_180045D90
0x180045d82  lea     rcx, qword_180069A90; this
0x180045d89  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045d90  cmp     byte ptr [rcx+8], 0
0x180045d94  jz      short loc_180045DBB
0x180045d96  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045d9b  cmp     [rax+7CCh], ebx
0x180045da1  jz      short loc_180045DBB
0x180045da3  mov     r9d, ebx; int
0x180045da6  lea     rdx, aCasftranscoded_6; "CASFTranscodeDestination::SetDeviceNeed"...
0x180045dad  mov     r8d, 14Fh; int
0x180045db3  mov     rcx, rax; this
0x180045db6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045dbb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045dc0  cmp     al, 1
0x180045dc2  jb      loc_180045EDA
0x180045dc8  mov     edx, 22h ; '"'
0x180045dcd  jmp     loc_180045EBC
0x180045dd2  mov     rax, [r15]
0x180045dd5  lea     r9, [rbp+4Fh+arg_18]
0x180045dd9  lea     r8, [rbp+4Fh+pv]
0x180045ddd  mov     rcx, r15
0x180045de0  lea     rdx, MF_TRANSCODE_ENCODINGPROFILE
0x180045de7  mov     rax, [rax+68h]
0x180045deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045df0  test    eax, eax
0x180045df2  js      loc_180045EDA
0x180045df8  mov     rcx, [rbp+4Fh+var_88]
0x180045dfc  lea     r8, [rbp+4Fh+var_68]
0x180045e00  mov     eax, 1Fh
0x180045e05  lea     rdx, g_wszDeviceConformanceTemplate; "DeviceConformanceTemplate"
0x180045e0c  mov     word ptr [rbp+4Fh+var_68], ax
0x180045e10  mov     rax, [rbp+4Fh+pv]
0x180045e14  mov     qword ptr [rbp+4Fh+var_68+8], rax
0x180045e18  mov     [rbp+4Fh+pv], 0
0x180045e20  mov     rax, [rcx]
0x180045e23  mov     rax, [rax+30h]
0x180045e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e2c  mov     ebx, eax
0x180045e2e  test    eax, eax
0x180045e30  jns     loc_180045EDA
0x180045e36  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045e3d  test    rcx, rcx
0x180045e40  jnz     short loc_180045E83
0x180045e42  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045e48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045e4f  mov     rcx, rax
0x180045e52  test    rax, rax
0x180045e55  jz      short loc_180045E75
0x180045e57  mov     rax, [rax]
0x180045e5a  mov     edx, 7F0h
0x180045e5f  mov     rax, [rax+8]
0x180045e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e68  test    eax, eax
0x180045e6a  jz      short loc_180045E75
0x180045e6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045e73  jmp     short loc_180045E83
0x180045e75  lea     rcx, qword_180069A90; this
0x180045e7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045e83  cmp     byte ptr [rcx+8], 0
0x180045e87  jz      short loc_180045EAE
0x180045e89  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045e8e  cmp     [rax+7CCh], ebx
0x180045e94  jz      short loc_180045EAE
0x180045e96  mov     r9d, ebx; int
0x180045e99  lea     rdx, aCasftranscoded_6; "CASFTranscodeDestination::SetDeviceNeed"...
0x180045ea0  mov     r8d, 159h; int
0x180045ea6  mov     rcx, rax; this
0x180045ea9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045eae  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045eb3  cmp     al, 1
0x180045eb5  jb      short loc_180045EDA
0x180045eb7  mov     edx, 23h ; '#'
0x180045ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ec3  lea     r8, WPP_0a758c1def7e3974366218a1d0d46647_Traceguids
0x180045eca  mov     r9, r14
0x180045ecd  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180045ed1  mov     rcx, [rcx+10h]
0x180045ed5  call    WPP_SF_qd
0x180045eda  mov     rcx, [rbp+4Fh+var_88]
0x180045ede  test    rcx, rcx
0x180045ee1  jz      short loc_180045EF7
0x180045ee3  mov     rax, [rcx]
0x180045ee6  mov     rax, [rax+10h]
0x180045eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045eef  mov     [rbp+4Fh+var_88], 0
0x180045ef7  mov     rcx, [rbp+4Fh+pv]; pv
0x180045efb  test    rcx, rcx
0x180045efe  jz      short loc_180045F0E
0x180045f00  call    cs:__imp_CoTaskMemFree
0x180045f06  mov     [rbp+4Fh+pv], 0
0x180045f0e  lea     rcx, [rbp+4Fh+var_68]
0x180045f12  call    cs:__imp_DestroyPropVariant
0x180045f18  lea     rcx, [rbp+4Fh+var_40]
0x180045f1c  call    cs:__imp_DestroyPropVariant
0x180045f22  lea     rcx, [rbp+4Fh+arg_0]; this
0x180045f26  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180045f2b  mov     eax, ebx
0x180045f2d  mov     rbx, [rsp+0C0h+arg_8]
0x180045f35  add     rsp, 0A0h
0x180045f3c  pop     r15
0x180045f3e  pop     r14
0x180045f40  pop     rdi
0x180045f41  pop     rsi
0x180045f42  pop     rbp
0x180045f43  retn
```
