# CDShowTransformTypeConverter::GetTypesFromEnum(IEnumMediaTypes *,ATL::CInterfaceArray<IMFMediaType,&__s_GUID const _GUID_44ae0fa8_ea31_4109_8d2e_4cae4997c555> &)

- ea: `0x180059d2c`
- end: `0x180059fba`
- name: `?GetTypesFromEnum@CDShowTransformTypeConverter@@SAJPEAUIEnumMediaTypes@@AEAV?$CInterfaceArray@UIMFMediaType@@$1?_GUID_44ae0fa8_ea31_4109_8d2e_4cae4997c555@@3U__s_GUID@@B@ATL@@@Z`
- size: `654`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18006d984`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180029244`
- `0x180032a50`
- `0x180051550`
- `0x180051ce4`
- `0x180059d2c`
- `0x1800bcb5c`
- `0x1800c9010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059e51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059f0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059e51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059f0a`
- `MFPlat!MFCreateMediaType` at `0x180059db1`
- `MFPlat!MFCreateMediaType` at `0x180059db1`
- `MFPlat!MFInitMediaTypeFromAMMediaType` at `0x180059dcf`
- `MFPlat!MFInitMediaTypeFromAMMediaType` at `0x180059dcf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDShowTransformTypeConverter::GetTypesFromEnum(__int64 a1, _QWORD *a2)
{
  struct _AMMediaType *v4; // rcx
  int v5; // eax
  HRESULT v6; // ebx
  IMFMediaType *v7; // rbx
  unsigned __int64 v8; // rsi
  CallStackTracing *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  CallStackTracing *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  AM_MEDIA_TYPE *pAMType; // [rsp+30h] [rbp-10h] BYREF
  char v18; // [rsp+70h] [rbp+30h] BYREF
  int v19; // [rsp+80h] [rbp+40h] BYREF
  IMFMediaType *ppMFType; // [rsp+88h] [rbp+48h] BYREF

  v19 = 0;
  v4 = 0;
  for ( pAMType = 0; ; v4 = pAMType )
  {
    ppMFType = 0;
    if ( v4 )
    {
      CDShowTransformTypeConverter::DeleteMediaType(v4);
      pAMType = 0;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, AM_MEDIA_TYPE **, int *))(*(_QWORD *)a1 + 24LL))(
           a1,
           1,
           &pAMType,
           &v19);
    v6 = v5;
    if ( v5 == 1 )
      break;
    if ( v5 < 0 )
      goto LABEL_37;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v18,
      "CDShowTransformTypeConverter::GetTypesFromEnum",
      151);
    v6 = MFCreateMediaType(&ppMFType);
    if ( v6 < 0 )
    {
      v13 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v13);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CDShowTransformTypeConverter::GetTypesFromEnum",
            151,
            v6);
      }
      if ( g_wppLevels )
      {
        v12 = 20;
LABEL_24:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_4424637dafd93ac8aa68a350a9714af2_Traceguids, 0, v6);
      }
LABEL_25:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v18);
      goto LABEL_37;
    }
    v6 = MFInitMediaTypeFromAMMediaType(ppMFType, pAMType);
    if ( v6 < 0 )
    {
      v9 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v9 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        v11 = CallStackTracing::GetThreadRelativeContext(v9);
        if ( *((_DWORD *)v11 + 499) != v6 )
          CallStackContext::TraceFailure(v11, "CDShowTransformTypeConverter::GetTypesFromEnum", 153, v6);
      }
      if ( g_wppLevels )
      {
        v12 = 21;
        goto LABEL_24;
      }
      goto LABEL_25;
    }
    v7 = ppMFType;
    v8 = a2[1];
    if ( v8 >= a2[2]
      && !(unsigned __int8)ATL::CAtlArray<CDShowTransformOutput *,ATL::CElementTraits<CDShowTransformOutput *>>::GrowBuffer(
                             a2,
                             v8 + 1) )
    {
      ATL::AtlThrowImpl(-2147024882);
    }
    *(_QWORD *)(*a2 + 8 * v8) = v7;
    if ( v7 )
      ((void (__fastcall *)(IMFMediaType *))v7->lpVtbl->AddRef)(v7);
    ++a2[1];
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v18);
    ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppMFType);
  }
  v6 = 0;
LABEL_37:
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppMFType);
  if ( pAMType )
    CDShowTransformTypeConverter::DeleteMediaType(pAMType);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180059d2c  push    rbp
0x180059d2e  push    rbx
0x180059d2f  push    rsi
0x180059d30  push    rdi
0x180059d31  push    r14
0x180059d33  mov     rbp, rsp
0x180059d36  sub     rsp, 40h
0x180059d3a  mov     rdi, rdx
0x180059d3d  mov     r14, rcx
0x180059d40  mov     [rbp+arg_10], 0
0x180059d47  xor     ecx, ecx; pv
0x180059d49  mov     [rbp+pAMType], rcx
0x180059d4d  mov     [rbp+ppMFType], 0
0x180059d55  test    rcx, rcx
0x180059d58  jz      short loc_180059D67
0x180059d5a  call    ?DeleteMediaType@CDShowTransformTypeConverter@@SAXPEAU_AMMediaType@@@Z; CDShowTransformTypeConverter::DeleteMediaType(_AMMediaType *)
0x180059d5f  mov     [rbp+pAMType], 0
0x180059d67  mov     rax, [r14]
0x180059d6a  lea     r9, [rbp+arg_10]
0x180059d6e  lea     r8, [rbp+pAMType]
0x180059d72  mov     edx, 1
0x180059d77  mov     rcx, r14
0x180059d7a  mov     rax, [rax+18h]
0x180059d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d83  mov     ebx, eax
0x180059d85  cmp     eax, 1
0x180059d88  jz      loc_180059F93
0x180059d8e  test    eax, eax
0x180059d90  js      loc_180059F95
0x180059d96  mov     r8d, 97h; int
0x180059d9c  lea     rdx, aCdshowtransfor_18; "CDShowTransformTypeConverter::GetTypesF"...
0x180059da3  lea     rcx, [rbp+arg_0]; this
0x180059da7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180059dac  nop
0x180059dad  lea     rcx, [rbp+ppMFType]; ppMFType
0x180059db1  call    cs:__imp_MFCreateMediaType
0x180059db8  nop     dword ptr [rax+rax+00h]
0x180059dbd  mov     ebx, eax
0x180059dbf  test    eax, eax
0x180059dc1  js      loc_180059EFE
0x180059dc7  mov     rdx, [rbp+pAMType]; pAMType
0x180059dcb  mov     rcx, [rbp+ppMFType]; pMFType
0x180059dcf  call    cs:__imp_MFInitMediaTypeFromAMMediaType
0x180059dd6  nop     dword ptr [rax+rax+00h]
0x180059ddb  mov     ebx, eax
0x180059ddd  test    eax, eax
0x180059ddf  js      short loc_180059E45
0x180059de1  mov     rbx, [rbp+ppMFType]
0x180059de5  mov     rsi, [rdi+8]
0x180059de9  cmp     rsi, [rdi+10h]
0x180059ded  jb      short loc_180059DFF
0x180059def  lea     rdx, [rsi+1]
0x180059df3  mov     rcx, rdi
0x180059df6  call    ?GrowBuffer@?$CAtlArray@PEAVCDShowTransformOutput@@V?$CElementTraits@PEAVCDShowTransformOutput@@@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<CDShowTransformOutput *,ATL::CElementTraits<CDShowTransformOutput *>>::GrowBuffer(unsigned __int64)
0x180059dfb  test    al, al
0x180059dfd  jz      short loc_180059E3A
0x180059dff  mov     rax, [rdi]
0x180059e02  mov     [rax+rsi*8], rbx
0x180059e06  test    rbx, rbx
0x180059e09  jz      short loc_180059E1A
0x180059e0b  mov     rax, [rbx]
0x180059e0e  mov     rcx, rbx
0x180059e11  mov     rax, [rax+8]
0x180059e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e1a  inc     qword ptr [rdi+8]
0x180059e1e  lea     rcx, [rbp+arg_0]; this
0x180059e22  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180059e27  nop
0x180059e28  lea     rcx, [rbp+ppMFType]; void *
0x180059e2c  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x180059e31  mov     rcx, [rbp+pAMType]
0x180059e35  jmp     loc_180059D4D
0x180059e3a  mov     ecx, 8007000Eh; int
0x180059e3f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180059e45  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059e4c  test    rcx, rcx
0x180059e4f  jnz     short loc_180059E98
0x180059e51  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180059e58  nop     dword ptr [rax+rax+00h]
0x180059e5d  mov     rcx, rax
0x180059e60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180059e67  test    rax, rax
0x180059e6a  jz      short loc_180059E8A
0x180059e6c  mov     rax, [rax]
0x180059e6f  mov     edx, 7F0h
0x180059e74  mov     rax, [rax+8]
0x180059e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e7d  test    eax, eax
0x180059e7f  jz      short loc_180059E8A
0x180059e81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059e88  jmp     short loc_180059E98
0x180059e8a  lea     rcx, qword_1800EB130; this
0x180059e91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180059e98  cmp     byte ptr [rcx+8], 0
0x180059e9c  jz      short loc_180059EC3
0x180059e9e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180059ea3  cmp     [rax+7CCh], ebx
0x180059ea9  jz      short loc_180059EC3
0x180059eab  mov     r9d, ebx; int
0x180059eae  mov     r8d, 99h; int
0x180059eb4  lea     rdx, aCdshowtransfor_18; "CDShowTransformTypeConverter::GetTypesF"...
0x180059ebb  mov     rcx, rax; this
0x180059ebe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180059ec3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180059eca  jb      short loc_180059EF0
0x180059ecc  mov     edx, 15h
0x180059ed1  mov     [rsp+40h+var_20], ebx
0x180059ed5  xor     r9d, r9d
0x180059ed8  lea     r8, WPP_4424637dafd93ac8aa68a350a9714af2_Traceguids
0x180059edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180059ee6  mov     rcx, [rcx+10h]
0x180059eea  call    WPP_SF_qD
0x180059eef  nop
0x180059ef0  lea     rcx, [rbp+arg_0]; this
0x180059ef4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180059ef9  jmp     loc_180059F95
0x180059efe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059f05  test    rcx, rcx
0x180059f08  jnz     short loc_180059F51
0x180059f0a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180059f11  nop     dword ptr [rax+rax+00h]
0x180059f16  mov     rcx, rax
0x180059f19  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180059f20  test    rax, rax
0x180059f23  jz      short loc_180059F43
0x180059f25  mov     rax, [rax]
0x180059f28  mov     edx, 7F0h
0x180059f2d  mov     rax, [rax+8]
0x180059f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f36  test    eax, eax
0x180059f38  jz      short loc_180059F43
0x180059f3a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059f41  jmp     short loc_180059F51
0x180059f43  lea     rcx, qword_1800EB130; this
0x180059f4a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180059f51  cmp     byte ptr [rcx+8], 0
0x180059f55  jz      short loc_180059F7C
0x180059f57  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180059f5c  cmp     [rax+7CCh], ebx
0x180059f62  jz      short loc_180059F7C
0x180059f64  mov     r9d, ebx; int
0x180059f67  mov     r8d, 97h; int
0x180059f6d  lea     rdx, aCdshowtransfor_18; "CDShowTransformTypeConverter::GetTypesF"...
0x180059f74  mov     rcx, rax; this
0x180059f77  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180059f7c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180059f83  jb      loc_180059EF0
0x180059f89  mov     edx, 14h
0x180059f8e  jmp     loc_180059ED1
0x180059f93  xor     ebx, ebx
0x180059f95  lea     rcx, [rbp+ppMFType]; void *
0x180059f99  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x180059f9e  mov     rcx, [rbp+pAMType]; pv
0x180059fa2  test    rcx, rcx
0x180059fa5  jz      short loc_180059FAC
0x180059fa7  call    ?DeleteMediaType@CDShowTransformTypeConverter@@SAXPEAU_AMMediaType@@@Z; CDShowTransformTypeConverter::DeleteMediaType(_AMMediaType *)
0x180059fac  mov     eax, ebx
0x180059fae  add     rsp, 40h
0x180059fb2  pop     r14
0x180059fb4  pop     rdi
0x180059fb5  pop     rsi
0x180059fb6  pop     rbx
0x180059fb7  pop     rbp
0x180059fb8  retn
```
