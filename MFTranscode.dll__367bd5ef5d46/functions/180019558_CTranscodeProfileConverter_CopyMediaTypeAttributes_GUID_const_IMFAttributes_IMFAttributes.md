# CTranscodeProfileConverter::CopyMediaTypeAttributes(_GUID const &,IMFAttributes *,IMFAttributes *)

- ea: `0x180019558`
- end: `0x180019848`
- name: `?CopyMediaTypeAttributes@CTranscodeProfileConverter@@IEAAJAEBU_GUID@@PEAUIMFAttributes@@1@Z`
- size: `752`
- prototype: `__int64 __fastcall(CTranscodeProfileConverter *__hidden this, const struct _GUID *, struct IMFAttributes *, struct IMFAttributes *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180018bdc`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800174c0`
- `0x180019558`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800195da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800196f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019780`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800195da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800196f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019780`
- `MFPlat!DestroyPropVariant` at `0x1800196d8`
- `MFPlat!DestroyPropVariant` at `0x18001981c`
- `MFPlat!DestroyPropVariant` at `0x1800196d8`
- `MFPlat!DestroyPropVariant` at `0x18001981c`

## string_xrefs

- `0x180019581`: `CTranscodeProfileConverter::CopyMediaTypeAttributes`
- `0x180019631`: `CTranscodeProfileConverter::CopyMediaTypeAttributes`
- `0x180019748`: `CTranscodeProfileConverter::CopyMediaTypeAttributes`
- `0x1800197d7`: `CTranscodeProfileConverter::CopyMediaTypeAttributes`

## pseudocode

```c
__int64 __fastcall CTranscodeProfileConverter::CopyMediaTypeAttributes(
        CTranscodeProfileConverter *this,
        const struct _GUID *a2,
        struct IMFAttributes *a3,
        struct IMFAttributes *a4)
{
  struct IMFAttributesVtbl *lpVtbl; // rax
  __int64 v9; // rdx
  int v10; // ebx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  unsigned int i; // edi
  HRESULT (__stdcall *GetItemByIndex)(IMFAttributes *, UINT32, GUID *, PROPVARIANT *); // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v26[4]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v27; // [rsp+34h] [rbp-3Ch] BYREF
  __int128 v28; // [rsp+38h] [rbp-38h] BYREF
  __int64 v29; // [rsp+48h] [rbp-28h]
  GUID v30; // [rsp+50h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v26,
    "CTranscodeProfileConverter::CopyMediaTypeAttributes",
    664);
  v27 = 0;
  v29 = 0;
  lpVtbl = a3->lpVtbl;
  v28 = 0;
  v10 = ((__int64 (__fastcall *)(struct IMFAttributes *, unsigned int *))lpVtbl->GetCount)(a3, &v27);
  if ( v10 >= 0 )
  {
    for ( i = 0; i < v27; ++i )
    {
      GetItemByIndex = a3->lpVtbl->GetItemByIndex;
      v30 = GUID_00000000_0000_0000_0000_000000000000;
      v10 = ((__int64 (__fastcall *)(struct IMFAttributes *, _QWORD, GUID *, __int128 *))GetItemByIndex)(
              a3,
              i,
              &v30,
              &v28);
      if ( v10 < 0 )
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
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
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CTranscodeProfileConverter::CopyMediaTypeAttributes",
              677,
              v10);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v14 = 84;
          goto LABEL_38;
        }
        break;
      }
      if ( (*(unsigned int (__fastcall **)(CTranscodeProfileConverter *, const struct _GUID *, GUID *))(*(_QWORD *)this + 16LL))(
             this,
             a2,
             &v30) )
      {
        v10 = ((__int64 (__fastcall *)(struct IMFAttributes *, GUID *, __int128 *))a4->lpVtbl->SetItem)(a4, &v30, &v28);
        if ( v10 < 0 )
        {
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
            v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
            if ( *((_DWORD *)v21 + 499) != v10 )
              CallStackContext::TraceFailure(v21, "CTranscodeProfileConverter::CopyMediaTypeAttributes", 680, v10);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v14 = 85;
            goto LABEL_38;
          }
          break;
        }
      }
      DestroyPropVariant(&v28);
    }
  }
  else
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != v10 )
        CallStackContext::TraceFailure(v13, "CTranscodeProfileConverter::CopyMediaTypeAttributes", 671, v10);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v14 = 83;
LABEL_38:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids, this, v10);
    }
  }
  DestroyPropVariant(&v28);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v26);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180019558  push    rbp
0x18001955a  push    rbx
0x18001955b  push    rsi
0x18001955c  push    rdi
0x18001955d  push    r12
0x18001955f  push    r14
0x180019561  push    r15
0x180019563  mov     rbp, rsp
0x180019566  sub     rsp, 70h
0x18001956a  mov     rax, cs:__security_cookie
0x180019571  xor     rax, rsp
0x180019574  mov     [rbp+var_10], rax
0x180019578  mov     r14, r8
0x18001957b  mov     r12, rdx
0x18001957e  mov     rsi, rcx
0x180019581  lea     rdx, aCtranscodeprof_12; "CTranscodeProfileConverter::CopyMediaTy"...
0x180019588  mov     r8d, 298h; int
0x18001958e  lea     rcx, [rbp+var_40]; this
0x180019592  mov     r15, r9
0x180019595  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001959a  xor     eax, eax
0x18001959c  mov     [rbp+var_3C], 0
0x1800195a3  mov     [rbp+var_28], rax
0x1800195a7  lea     rdx, [rbp+var_3C]
0x1800195ab  mov     rax, [r14]
0x1800195ae  xorps   xmm0, xmm0
0x1800195b1  mov     rcx, r14
0x1800195b4  movups  [rbp+var_38], xmm0
0x1800195b8  mov     rax, [rax+0F0h]
0x1800195bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195c4  mov     ebx, eax
0x1800195c6  test    eax, eax
0x1800195c8  jns     loc_18001965D
0x1800195ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800195d5  test    rcx, rcx
0x1800195d8  jnz     short loc_18001961B
0x1800195da  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800195e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800195e7  mov     rcx, rax
0x1800195ea  test    rax, rax
0x1800195ed  jz      short loc_18001960D
0x1800195ef  mov     rax, [rax]
0x1800195f2  mov     edx, 7F0h
0x1800195f7  mov     rax, [rax+8]
0x1800195fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019600  test    eax, eax
0x180019602  jz      short loc_18001960D
0x180019604  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001960b  jmp     short loc_18001961B
0x18001960d  lea     rcx, qword_180069A90; this
0x180019614  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001961b  cmp     byte ptr [rcx+8], 0
0x18001961f  jz      short loc_180019646
0x180019621  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019626  cmp     [rax+7CCh], ebx
0x18001962c  jz      short loc_180019646
0x18001962e  mov     r9d, ebx; int
0x180019631  lea     rdx, aCtranscodeprof_12; "CTranscodeProfileConverter::CopyMediaTy"...
0x180019638  mov     r8d, 29Fh; int
0x18001963e  mov     rcx, rax; this
0x180019641  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019646  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001964b  cmp     al, 1
0x18001964d  jb      loc_180019818
0x180019653  mov     edx, 53h ; 'S'
0x180019658  jmp     loc_1800197FA
0x18001965d  xor     edi, edi
0x18001965f  cmp     edi, [rbp+var_3C]
0x180019662  jnb     loc_180019818
0x180019668  mov     rax, [r14]
0x18001966b  lea     r9, [rbp+var_38]
0x18001966f  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180019676  lea     r8, [rbp+var_20]
0x18001967a  mov     edx, edi
0x18001967c  mov     rcx, r14
0x18001967f  mov     rax, [rax+0F8h]
0x180019686  movdqu  [rbp+var_20], xmm0
0x18001968b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019690  mov     ebx, eax
0x180019692  test    eax, eax
0x180019694  js      loc_180019774
0x18001969a  mov     rax, [rsi]
0x18001969d  lea     r8, [rbp+var_20]
0x1800196a1  mov     rdx, r12
0x1800196a4  mov     rcx, rsi
0x1800196a7  mov     rax, [rax+10h]
0x1800196ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196b0  test    eax, eax
0x1800196b2  jz      short loc_1800196D4
0x1800196b4  mov     rax, [r15]
0x1800196b7  lea     r8, [rbp+var_38]
0x1800196bb  lea     rdx, [rbp+var_20]
0x1800196bf  mov     rcx, r15
0x1800196c2  mov     rax, [rax+90h]
0x1800196c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196ce  mov     ebx, eax
0x1800196d0  test    eax, eax
0x1800196d2  js      short loc_1800196E5
0x1800196d4  lea     rcx, [rbp+var_38]
0x1800196d8  call    cs:__imp_DestroyPropVariant
0x1800196de  inc     edi
0x1800196e0  jmp     loc_18001965F
0x1800196e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800196ec  test    rcx, rcx
0x1800196ef  jnz     short loc_180019732
0x1800196f1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800196f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800196fe  mov     rcx, rax
0x180019701  test    rax, rax
0x180019704  jz      short loc_180019724
0x180019706  mov     rax, [rax]
0x180019709  mov     edx, 7F0h
0x18001970e  mov     rax, [rax+8]
0x180019712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019717  test    eax, eax
0x180019719  jz      short loc_180019724
0x18001971b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019722  jmp     short loc_180019732
0x180019724  lea     rcx, qword_180069A90; this
0x18001972b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019732  cmp     byte ptr [rcx+8], 0
0x180019736  jz      short loc_18001975D
0x180019738  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001973d  cmp     [rax+7CCh], ebx
0x180019743  jz      short loc_18001975D
0x180019745  mov     r9d, ebx; int
0x180019748  lea     rdx, aCtranscodeprof_12; "CTranscodeProfileConverter::CopyMediaTy"...
0x18001974f  mov     r8d, 2A8h; int
0x180019755  mov     rcx, rax; this
0x180019758  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001975d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019762  cmp     al, 1
0x180019764  jb      loc_180019818
0x18001976a  mov     edx, 55h ; 'U'
0x18001976f  jmp     loc_1800197FA
0x180019774  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001977b  test    rcx, rcx
0x18001977e  jnz     short loc_1800197C1
0x180019780  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019786  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001978d  mov     rcx, rax
0x180019790  test    rax, rax
0x180019793  jz      short loc_1800197B3
0x180019795  mov     rax, [rax]
0x180019798  mov     edx, 7F0h
0x18001979d  mov     rax, [rax+8]
0x1800197a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197a6  test    eax, eax
0x1800197a8  jz      short loc_1800197B3
0x1800197aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800197b1  jmp     short loc_1800197C1
0x1800197b3  lea     rcx, qword_180069A90; this
0x1800197ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800197c1  cmp     byte ptr [rcx+8], 0
0x1800197c5  jz      short loc_1800197EC
0x1800197c7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800197cc  cmp     [rax+7CCh], ebx
0x1800197d2  jz      short loc_1800197EC
0x1800197d4  mov     r9d, ebx; int
0x1800197d7  lea     rdx, aCtranscodeprof_12; "CTranscodeProfileConverter::CopyMediaTy"...
0x1800197de  mov     r8d, 2A5h; int
0x1800197e4  mov     rcx, rax; this
0x1800197e7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800197ec  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800197f1  cmp     al, 1
0x1800197f3  jb      short loc_180019818
0x1800197f5  mov     edx, 54h ; 'T'
0x1800197fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180019801  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x180019808  mov     r9, rsi
0x18001980b  mov     [rsp+70h+var_50], ebx
0x18001980f  mov     rcx, [rcx+10h]
0x180019813  call    WPP_SF_qd
0x180019818  lea     rcx, [rbp+var_38]
0x18001981c  call    cs:__imp_DestroyPropVariant
0x180019822  lea     rcx, [rbp+var_40]; this
0x180019826  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001982b  mov     eax, ebx
0x18001982d  mov     rcx, [rbp+var_10]
0x180019831  xor     rcx, rsp; StackCookie
0x180019834  call    __security_check_cookie
0x180019839  add     rsp, 70h
0x18001983d  pop     r15
0x18001983f  pop     r14
0x180019841  pop     r12
0x180019843  pop     rdi
0x180019844  pop     rsi
0x180019845  pop     rbx
0x180019846  pop     rbp
0x180019847  retn
```
