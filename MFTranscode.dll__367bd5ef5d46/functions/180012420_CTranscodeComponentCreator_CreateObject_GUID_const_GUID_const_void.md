# CTranscodeComponentCreator::CreateObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180012420`
- end: `0x1800128ef`
- name: `?CreateObject@CTranscodeComponentCreator@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `1231`
- prototype: `int(CTranscodeComponentCreator *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x180012420`
- `0x180019ad4`
- `0x18001a330`
- `0x18001c280`
- `0x180031c98`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012774`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012774`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001246f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001254d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012613`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800126dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012790`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001283a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001246f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001254d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012613`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800126dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012790`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001283a`

## string_xrefs

- `0x180012433`: `CTranscodeComponentCreator::CreateObject`

## pseudocode

```c
__int64 __fastcall CTranscodeComponentCreator::CreateObject(
        CTranscodeComponentCreator *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v8; // rdx
  __int64 *v9; // rcx
  HRESULT Instance; // ebx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  struct IMFActivate *ppv; // [rsp+88h] [rbp+50h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&ppv, "CTranscodeComponentCreator::CreateObject", 219);
  if ( !a4 )
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    Instance = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CTranscodeComponentCreator::CreateObject",
          223,
          -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v13 = 22;
LABEL_12:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        WPP_60c454de96f7327ebad2115a8fee1984_Traceguids,
        this,
        Instance);
      goto LABEL_78;
    }
    goto LABEL_78;
  }
  v14 = *(_QWORD *)&CLSID_MFTranscodeProfile.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&CLSID_MFTranscodeProfile.Data1 == *(_QWORD *)&a2->Data1 )
    v14 = *(_QWORD *)CLSID_MFTranscodeProfile.Data4 - *(_QWORD *)a2->Data4;
  if ( v14 )
  {
    v19 = *(_QWORD *)&CLSID_TranscodeSinkActivate.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_TranscodeSinkActivate.Data1 == *(_QWORD *)&a2->Data1 )
      v19 = *(_QWORD *)CLSID_TranscodeSinkActivate.Data4 - *(_QWORD *)a2->Data4;
    ppv = 0;
    if ( v19 )
    {
      Instance = CoCreateInstance(a2, 0, 1u, &IID_IUnknown, (LPVOID *)&ppv);
      if ( Instance >= 0 )
      {
        Instance = ((__int64 (__fastcall *)(struct IMFActivate *, const struct _GUID *, void **))ppv->lpVtbl->QueryInterface)(
                     ppv,
                     a3,
                     a4);
        if ( Instance >= 0 )
          goto LABEL_77;
        v35 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
          CallStackTracing::s_wpInstance = v36;
          if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
          {
            v35 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v35 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v35 + 8) )
        {
          v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
          if ( *((_DWORD *)v37 + 499) != Instance )
            CallStackContext::TraceFailure(v37, "CTranscodeComponentCreator::CreateObject", 241, Instance);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_77;
        v33 = 27;
      }
      else
      {
        v30 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
          CallStackTracing::s_wpInstance = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)v32 + 499) != Instance )
            CallStackContext::TraceFailure(v32, "CTranscodeComponentCreator::CreateObject", 240, Instance);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_77;
        v33 = 26;
      }
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v33,
        WPP_60c454de96f7327ebad2115a8fee1984_Traceguids,
        this,
        Instance);
    }
    else
    {
      Instance = CTranscodeSinkActivate::CreateInstance(&ppv);
      if ( Instance >= 0 )
      {
        Instance = ((__int64 (__fastcall *)(struct IMFActivate *, const struct _GUID *, void **))ppv->lpVtbl->QueryInterface)(
                     ppv,
                     a3,
                     a4);
        if ( Instance >= 0 )
          goto LABEL_77;
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
          if ( *((_DWORD *)v28 + 499) != Instance )
            CallStackContext::TraceFailure(v28, "CTranscodeComponentCreator::CreateObject", 235, Instance);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_77;
        v24 = 25;
      }
      else
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != Instance )
            CallStackContext::TraceFailure(v23, "CTranscodeComponentCreator::CreateObject", 234, Instance);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_77;
        v24 = 24;
      }
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v24,
        WPP_60c454de96f7327ebad2115a8fee1984_Traceguids,
        this,
        Instance);
    }
LABEL_77:
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppv);
    goto LABEL_78;
  }
  Instance = CTranscodeProfile::CreateInstance(a3, a4);
  if ( Instance < 0 )
  {
    v16 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v18 + 499) != Instance )
        CallStackContext::TraceFailure(v18, "CTranscodeComponentCreator::CreateObject", 228, Instance);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v13 = 23;
      goto LABEL_12;
    }
  }
LABEL_78:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180012420  push    rbp
0x180012422  push    rbx
0x180012423  push    rsi
0x180012424  push    rdi
0x180012425  push    r12
0x180012427  push    r14
0x180012429  mov     rbp, rsp
0x18001242c  sub     rsp, 38h
0x180012430  mov     rsi, r8
0x180012433  lea     r12, aCtranscodecomp_1; "CTranscodeComponentCreator::CreateObjec"...
0x18001243a  mov     rbx, rdx
0x18001243d  mov     r14, rcx
0x180012440  mov     rdx, r12; char *
0x180012443  lea     rcx, [rbp+arg_18]; this
0x180012447  mov     r8d, 0DBh; int
0x18001244d  mov     rdi, r9
0x180012450  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180012455  test    rdi, rdi
0x180012458  jnz     loc_18001250C
0x18001245e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012465  mov     ebx, 80004003h
0x18001246a  test    rcx, rcx
0x18001246d  jnz     short loc_1800124B0
0x18001246f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012475  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001247c  mov     rcx, rax
0x18001247f  test    rax, rax
0x180012482  jz      short loc_1800124A2
0x180012484  mov     rax, [rax]
0x180012487  mov     edx, 7F0h
0x18001248c  mov     rax, [rax+8]
0x180012490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012495  test    eax, eax
0x180012497  jz      short loc_1800124A2
0x180012499  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800124a0  jmp     short loc_1800124B0
0x1800124a2  lea     rcx, qword_180069A90; this
0x1800124a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800124b0  cmp     byte ptr [rcx+8], 0
0x1800124b4  jz      short loc_1800124D7
0x1800124b6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800124bb  cmp     [rax+7CCh], ebx
0x1800124c1  jz      short loc_1800124D7
0x1800124c3  mov     r9d, ebx; int
0x1800124c6  mov     r8d, 0DFh; int
0x1800124cc  mov     rdx, r12; char *
0x1800124cf  mov     rcx, rax; this
0x1800124d2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800124d7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800124dc  cmp     al, 1
0x1800124de  jb      loc_1800128D7
0x1800124e4  mov     edx, 16h
0x1800124e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124f0  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x1800124f7  mov     r9, r14
0x1800124fa  mov     dword ptr [rsp+38h+ppv], ebx
0x1800124fe  mov     rcx, [rcx+10h]
0x180012502  call    WPP_SF_qd
0x180012507  jmp     loc_1800128D7
0x18001250c  mov     rax, qword ptr cs:CLSID_MFTranscodeProfile.Data1
0x180012513  sub     rax, [rbx]
0x180012516  jnz     short loc_180012523
0x180012518  mov     rax, qword ptr cs:CLSID_MFTranscodeProfile.Data4
0x18001251f  sub     rax, [rbx+8]
0x180012523  test    rax, rax
0x180012526  jnz     loc_1800125CC
0x18001252c  mov     rdx, rdi; void **
0x18001252f  mov     rcx, rsi; struct _GUID *
0x180012532  call    ?CreateInstance@CTranscodeProfile@@SAJAEBU_GUID@@PEAPEAX@Z; CTranscodeProfile::CreateInstance(_GUID const &,void * *)
0x180012537  mov     ebx, eax
0x180012539  test    eax, eax
0x18001253b  jns     loc_1800128D7
0x180012541  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012548  test    rcx, rcx
0x18001254b  jnz     short loc_18001258E
0x18001254d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012553  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001255a  mov     rcx, rax
0x18001255d  test    rax, rax
0x180012560  jz      short loc_180012580
0x180012562  mov     rax, [rax]
0x180012565  mov     edx, 7F0h
0x18001256a  mov     rax, [rax+8]
0x18001256e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012573  test    eax, eax
0x180012575  jz      short loc_180012580
0x180012577  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001257e  jmp     short loc_18001258E
0x180012580  lea     rcx, qword_180069A90; this
0x180012587  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001258e  cmp     byte ptr [rcx+8], 0
0x180012592  jz      short loc_1800125B5
0x180012594  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012599  cmp     [rax+7CCh], ebx
0x18001259f  jz      short loc_1800125B5
0x1800125a1  mov     r9d, ebx; int
0x1800125a4  mov     r8d, 0E4h; int
0x1800125aa  mov     rdx, r12; char *
0x1800125ad  mov     rcx, rax; this
0x1800125b0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800125b5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800125ba  cmp     al, 1
0x1800125bc  jb      loc_1800128D7
0x1800125c2  mov     edx, 17h
0x1800125c7  jmp     loc_1800124E9
0x1800125cc  mov     rax, qword ptr cs:CLSID_TranscodeSinkActivate.Data1
0x1800125d3  sub     rax, [rbx]
0x1800125d6  jnz     short loc_1800125E3
0x1800125d8  mov     rax, qword ptr cs:CLSID_TranscodeSinkActivate.Data4
0x1800125df  sub     rax, [rbx+8]
0x1800125e3  mov     [rbp+arg_18], 0
0x1800125eb  test    rax, rax
0x1800125ee  jnz     loc_18001275B
0x1800125f4  lea     rcx, [rbp+arg_18]; struct IMFActivate **
0x1800125f8  call    ?CreateInstance@CTranscodeSinkActivate@@SAJPEAPEAUIMFActivate@@@Z; CTranscodeSinkActivate::CreateInstance(IMFActivate * *)
0x1800125fd  mov     ebx, eax
0x1800125ff  test    eax, eax
0x180012601  jns     loc_1800126B5
0x180012607  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001260e  test    rcx, rcx
0x180012611  jnz     short loc_180012654
0x180012613  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012619  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012620  mov     rcx, rax
0x180012623  test    rax, rax
0x180012626  jz      short loc_180012646
0x180012628  mov     rax, [rax]
0x18001262b  mov     edx, 7F0h
0x180012630  mov     rax, [rax+8]
0x180012634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012639  test    eax, eax
0x18001263b  jz      short loc_180012646
0x18001263d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012644  jmp     short loc_180012654
0x180012646  lea     rcx, qword_180069A90; this
0x18001264d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012654  cmp     byte ptr [rcx+8], 0
0x180012658  jz      short loc_18001267B
0x18001265a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001265f  cmp     [rax+7CCh], ebx
0x180012665  jz      short loc_18001267B
0x180012667  mov     r9d, ebx; int
0x18001266a  mov     r8d, 0EAh; int
0x180012670  mov     rdx, r12; char *
0x180012673  mov     rcx, rax; this
0x180012676  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001267b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180012680  cmp     al, 1
0x180012682  jb      short loc_1800126A7
0x180012684  mov     edx, 18h
0x180012689  mov     rcx, cs:WPP_GLOBAL_Control
0x180012690  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x180012697  mov     r9, r14
0x18001269a  mov     dword ptr [rsp+38h+ppv], ebx
0x18001269e  mov     rcx, [rcx+10h]
0x1800126a2  call    WPP_SF_qd
0x1800126a7  lea     rcx, [rbp+arg_18]
0x1800126ab  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800126b0  jmp     loc_1800128D7
0x1800126b5  mov     rcx, [rbp+arg_18]
0x1800126b9  mov     r8, rdi
0x1800126bc  mov     rdx, rsi
0x1800126bf  mov     rax, [rcx]
0x1800126c2  mov     rax, [rax]
0x1800126c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126ca  mov     ebx, eax
0x1800126cc  test    eax, eax
0x1800126ce  jns     short loc_1800126A7
0x1800126d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800126d7  test    rcx, rcx
0x1800126da  jnz     short loc_18001271D
0x1800126dc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800126e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800126e9  mov     rcx, rax
0x1800126ec  test    rax, rax
0x1800126ef  jz      short loc_18001270F
0x1800126f1  mov     rax, [rax]
0x1800126f4  mov     edx, 7F0h
0x1800126f9  mov     rax, [rax+8]
0x1800126fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012702  test    eax, eax
0x180012704  jz      short loc_18001270F
0x180012706  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001270d  jmp     short loc_18001271D
0x18001270f  lea     rcx, qword_180069A90; this
0x180012716  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001271d  cmp     byte ptr [rcx+8], 0
0x180012721  jz      short loc_180012744
0x180012723  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012728  cmp     [rax+7CCh], ebx
0x18001272e  jz      short loc_180012744
0x180012730  mov     r9d, ebx; int
0x180012733  mov     r8d, 0EBh; int
0x180012739  mov     rdx, r12; char *
0x18001273c  mov     rcx, rax; this
0x18001273f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012744  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180012749  cmp     al, 1
0x18001274b  jb      loc_1800126A7
0x180012751  mov     edx, 19h
0x180012756  jmp     loc_180012689
0x18001275b  xor     edx, edx; pUnkOuter
0x18001275d  lea     rax, [rbp+arg_18]
0x180012761  lea     r9, IID_IUnknown; riid
0x180012768  mov     [rsp+38h+ppv], rax; ppv
0x18001276d  mov     rcx, rbx; rclsid
0x180012770  lea     r8d, [rdx+1]; dwClsContext
0x180012774  call    cs:__imp_CoCreateInstance
0x18001277a  mov     ebx, eax
0x18001277c  test    eax, eax
0x18001277e  jns     loc_18001280F
0x180012784  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001278b  test    rcx, rcx
0x18001278e  jnz     short loc_1800127D1
0x180012790  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012796  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001279d  mov     rcx, rax
0x1800127a0  test    rax, rax
0x1800127a3  jz      short loc_1800127C3
0x1800127a5  mov     rax, [rax]
0x1800127a8  mov     edx, 7F0h
0x1800127ad  mov     rax, [rax+8]
0x1800127b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127b6  test    eax, eax
0x1800127b8  jz      short loc_1800127C3
0x1800127ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800127c1  jmp     short loc_1800127D1
0x1800127c3  lea     rcx, qword_180069A90; this
0x1800127ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800127d1  cmp     byte ptr [rcx+8], 0
0x1800127d5  jz      short loc_1800127F8
0x1800127d7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800127dc  cmp     [rax+7CCh], ebx
0x1800127e2  jz      short loc_1800127F8
0x1800127e4  mov     r9d, ebx; int
0x1800127e7  mov     r8d, 0F0h; int
0x1800127ed  mov     rdx, r12; char *
0x1800127f0  mov     rcx, rax; this
0x1800127f3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800127f8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800127fd  cmp     al, 1
0x1800127ff  jb      loc_1800128CE
0x180012805  mov     edx, 1Ah
0x18001280a  jmp     loc_1800128B0
0x18001280f  mov     rcx, [rbp+arg_18]
0x180012813  mov     r8, rdi
0x180012816  mov     rdx, rsi
0x180012819  mov     rax, [rcx]
0x18001281c  mov     rax, [rax]
0x18001281f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012824  mov     ebx, eax
0x180012826  test    eax, eax
0x180012828  jns     loc_1800128CE
0x18001282e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012835  test    rcx, rcx
0x180012838  jnz     short loc_18001287B
0x18001283a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012840  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012847  mov     rcx, rax
0x18001284a  test    rax, rax
0x18001284d  jz      short loc_18001286D
0x18001284f  mov     rax, [rax]
0x180012852  mov     edx, 7F0h
0x180012857  mov     rax, [rax+8]
0x18001285b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012860  test    eax, eax
0x180012862  jz      short loc_18001286D
0x180012864  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001286b  jmp     short loc_18001287B
0x18001286d  lea     rcx, qword_180069A90; this
0x180012874  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001287b  cmp     byte ptr [rcx+8], 0
0x18001287f  jz      short loc_1800128A2
0x180012881  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012886  cmp     [rax+7CCh], ebx
0x18001288c  jz      short loc_1800128A2
0x18001288e  mov     r9d, ebx; int
0x180012891  mov     r8d, 0F1h; int
0x180012897  mov     rdx, r12; char *
0x18001289a  mov     rcx, rax; this
0x18001289d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800128a2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800128a7  cmp     al, 1
0x1800128a9  jb      short loc_1800128CE
0x1800128ab  mov     edx, 1Bh
0x1800128b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128b7  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x1800128be  mov     r9, r14
0x1800128c1  mov     dword ptr [rsp+38h+ppv], ebx
0x1800128c5  mov     rcx, [rcx+10h]
0x1800128c9  call    WPP_SF_qd
0x1800128ce  lea     rcx, [rbp+arg_18]
0x1800128d2  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800128d7  lea     rcx, [rbp+arg_18]; this
0x1800128db  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800128e0  mov     eax, ebx
0x1800128e2  add     rsp, 38h
0x1800128e6  pop     r14
0x1800128e8  pop     r12
0x1800128ea  pop     rdi
  ... truncated ...
```
