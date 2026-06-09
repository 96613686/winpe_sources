# CASFTranscodeProfileConverter::ConvertProfile(IMFTranscodeProfile *,_GUID const &,void * *)

- ea: `0x180010110`
- end: `0x18001062a`
- name: `?ConvertProfile@CASFTranscodeProfileConverter@@UEAAJPEAUIMFTranscodeProfile@@AEBU_GUID@@PEAPEAX@Z`
- size: `1306`
- prototype: `__int64 __fastcall(CASFTranscodeProfileConverter *__hidden this, struct IMFTranscodeProfile *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800446a8`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180010110`
- `0x180018f9c`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010189`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001024a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800102f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800103bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010471`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010537`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010189`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001024a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800102f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800103bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010471`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010537`
- `mfasfsrcsnk!MFCreateASFProfile` at `0x18001022e`
- `mfasfsrcsnk!MFCreateASFProfile` at `0x18001022e`

## pseudocode

```c
__int64 __fastcall CASFTranscodeProfileConverter::ConvertProfile(
        CASFTranscodeProfileConverter *this,
        struct IMFTranscodeProfile *a2,
        const struct _GUID *a3,
        IMFASFProfile **a4)
{
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 *v10; // rcx
  HRESULT v11; // ebx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  unsigned __int16 v23; // si
  __int64 v24; // rdx
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  IMFASFProfile *ppIProfile; // [rsp+30h] [rbp-28h] BYREF
  struct IMFAttributes *v38; // [rsp+38h] [rbp-20h] BYREF
  struct IMFAttributes *v39; // [rsp+40h] [rbp-18h] BYREF
  char v40; // [rsp+A0h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v40,
    "CASFTranscodeProfileConverter::ConvertProfile",
    740);
  ppIProfile = 0;
  v38 = 0;
  v39 = 0;
  v9 = *(_QWORD *)&IID_IMFASFProfile.Data1 - *(_QWORD *)&a3->Data1;
  if ( *(_QWORD *)&IID_IMFASFProfile.Data1 == *(_QWORD *)&a3->Data1 )
    v9 = *(_QWORD *)IID_IMFASFProfile.Data4 - *(_QWORD *)a3->Data4;
  if ( v9 )
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    v11 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CASFTranscodeProfileConverter::ConvertProfile",
          750,
          -2147024809);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v14 = 87;
LABEL_14:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids, this, v11);
    }
  }
  else
  {
    v11 = MFCreateASFProfile(&ppIProfile);
    if ( v11 >= 0 )
    {
      v11 = ((__int64 (__fastcall *)(struct IMFTranscodeProfile *, struct IMFAttributes **))a2->lpVtbl->GetAudioAttributes)(
              a2,
              &v38);
      if ( v11 >= 0 )
      {
        v23 = 1;
        if ( v38 )
        {
          v11 = CASFTranscodeProfileConverter::ConvertStream(this, v38, &MFMediaType_Audio, 1u, ppIProfile);
          if ( v11 < 0 )
          {
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
              CallStackTracing::s_wpInstance = v26;
              if ( v26
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
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
              if ( *((_DWORD *)v27 + 499) != v11 )
                CallStackContext::TraceFailure(v27, "CASFTranscodeProfileConverter::ConvertProfile", 758, v11);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v14 = 90;
              goto LABEL_14;
            }
            goto LABEL_74;
          }
          v23 = 2;
        }
        v11 = ((__int64 (__fastcall *)(struct IMFTranscodeProfile *, struct IMFAttributes **))a2->lpVtbl->GetVideoAttributes)(
                a2,
                &v39);
        if ( v11 >= 0 )
        {
          if ( v39
            && (v11 = CASFTranscodeProfileConverter::ConvertStream(this, v39, &MFMediaType_Video, v23, ppIProfile),
                v11 < 0) )
          {
            v33 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
              CallStackTracing::s_wpInstance = v34;
              if ( v34
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
              {
                v33 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v33 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v33 + 8) )
            {
              v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
              if ( *((_DWORD *)v35 + 499) != v11 )
                CallStackContext::TraceFailure(v35, "CASFTranscodeProfileConverter::ConvertProfile", 765, v11);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v14 = 92;
              goto LABEL_14;
            }
          }
          else
          {
            *a4 = ppIProfile;
            ppIProfile = 0;
          }
        }
        else
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
            CallStackTracing::s_wpInstance = v30;
            if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
            {
              v29 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v29 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v29 + 8) )
          {
            v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
            if ( *((_DWORD *)v31 + 499) != v11 )
              CallStackContext::TraceFailure(v31, "CASFTranscodeProfileConverter::ConvertProfile", 762, v11);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v14 = 91;
            goto LABEL_14;
          }
        }
        goto LABEL_74;
      }
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
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
        if ( *((_DWORD *)v22 + 499) != v11 )
          CallStackContext::TraceFailure(v22, "CASFTranscodeProfileConverter::ConvertProfile", 755, v11);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 89;
        goto LABEL_14;
      }
    }
    else
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
        if ( *((_DWORD *)v18 + 499) != v11 )
          CallStackContext::TraceFailure(v18, "CASFTranscodeProfileConverter::ConvertProfile", 753, v11);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 88;
        goto LABEL_14;
      }
    }
  }
LABEL_74:
  if ( v38 )
  {
    ((void (__fastcall *)(struct IMFAttributes *))v38->lpVtbl->Release)(v38);
    v38 = 0;
  }
  if ( v39 )
  {
    ((void (__fastcall *)(struct IMFAttributes *))v39->lpVtbl->Release)(v39);
    v39 = 0;
  }
  if ( ppIProfile )
  {
    ((void (__fastcall *)(IMFASFProfile *))ppIProfile->lpVtbl->Release)(ppIProfile);
    ppIProfile = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v40);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180010110  push    rbp
0x180010112  push    rbx
0x180010113  push    rsi
0x180010114  push    rdi
0x180010115  push    r12
0x180010117  push    r13
0x180010119  push    r14
0x18001011b  push    r15
0x18001011d  mov     rbp, rsp
0x180010120  sub     rsp, 58h
0x180010124  mov     rbx, r8
0x180010127  lea     rdi, aCasftranscodep_1; "CASFTranscodeProfileConverter::ConvertP"...
0x18001012e  mov     r15, rdx
0x180010131  mov     r14, rcx
0x180010134  mov     rdx, rdi; char *
0x180010137  lea     rcx, [rbp+arg_0]; this
0x18001013b  mov     r8d, 2E4h; int
0x180010141  mov     r12, r9
0x180010144  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180010149  mov     rax, qword ptr cs:IID_IMFASFProfile.Data1
0x180010150  xor     r13d, r13d
0x180010153  mov     [rbp+ppIProfile], r13
0x180010157  mov     [rbp+var_20], r13
0x18001015b  mov     [rbp+var_18], r13
0x18001015f  sub     rax, [rbx]
0x180010162  jnz     short loc_18001016F
0x180010164  mov     rax, qword ptr cs:IID_IMFASFProfile.Data4
0x18001016b  sub     rax, [rbx+8]
0x18001016f  test    rax, rax
0x180010172  jz      loc_18001022A
0x180010178  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001017f  mov     ebx, 80070057h
0x180010184  test    rcx, rcx
0x180010187  jnz     short loc_1800101CA
0x180010189  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001018f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010196  mov     rcx, rax
0x180010199  test    rax, rax
0x18001019c  jz      short loc_1800101BC
0x18001019e  mov     rax, [rax]
0x1800101a1  mov     edx, 7F0h
0x1800101a6  mov     rax, [rax+8]
0x1800101aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101af  test    eax, eax
0x1800101b1  jz      short loc_1800101BC
0x1800101b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800101ba  jmp     short loc_1800101CA
0x1800101bc  lea     rcx, qword_180069A90; this
0x1800101c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800101ca  cmp     [rcx+8], r13b
0x1800101ce  jz      short loc_1800101F1
0x1800101d0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800101d5  cmp     [rax+7CCh], ebx
0x1800101db  jz      short loc_1800101F1
0x1800101dd  mov     r9d, ebx; int
0x1800101e0  mov     r8d, 2EEh; int
0x1800101e6  mov     rdx, rdi; char *
0x1800101e9  mov     rcx, rax; this
0x1800101ec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800101f1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800101f6  mov     edi, 1
0x1800101fb  cmp     al, dil
0x1800101fe  jb      loc_1800105C3
0x180010204  lea     edx, [rdi+56h]
0x180010207  mov     rcx, cs:WPP_GLOBAL_Control
0x18001020e  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x180010215  mov     r9, r14
0x180010218  mov     dword ptr [rsp+58h+var_38], ebx
0x18001021c  mov     rcx, [rcx+10h]
0x180010220  call    WPP_SF_qd
0x180010225  jmp     loc_1800105C3
0x18001022a  lea     rcx, [rbp+ppIProfile]; ppIProfile
0x18001022e  call    cs:__imp_MFCreateASFProfile
0x180010234  mov     ebx, eax
0x180010236  test    eax, eax
0x180010238  jns     loc_1800102CD
0x18001023e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010245  test    rcx, rcx
0x180010248  jnz     short loc_18001028B
0x18001024a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010250  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010257  mov     rcx, rax
0x18001025a  test    rax, rax
0x18001025d  jz      short loc_18001027D
0x18001025f  mov     rax, [rax]
0x180010262  mov     edx, 7F0h
0x180010267  mov     rax, [rax+8]
0x18001026b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010270  test    eax, eax
0x180010272  jz      short loc_18001027D
0x180010274  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001027b  jmp     short loc_18001028B
0x18001027d  lea     rcx, qword_180069A90; this
0x180010284  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001028b  cmp     [rcx+8], r13b
0x18001028f  jz      short loc_1800102B2
0x180010291  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010296  cmp     [rax+7CCh], ebx
0x18001029c  jz      short loc_1800102B2
0x18001029e  mov     r9d, ebx; int
0x1800102a1  mov     r8d, 2F1h; int
0x1800102a7  mov     rdx, rdi; char *
0x1800102aa  mov     rcx, rax; this
0x1800102ad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800102b2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800102b7  mov     edi, 1
0x1800102bc  cmp     al, dil
0x1800102bf  jb      loc_1800105C3
0x1800102c5  lea     edx, [rdi+57h]
0x1800102c8  jmp     loc_180010207
0x1800102cd  mov     rax, [r15]
0x1800102d0  lea     rdx, [rbp+var_20]
0x1800102d4  mov     rcx, r15
0x1800102d7  mov     rax, [rax+20h]
0x1800102db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102e0  mov     ebx, eax
0x1800102e2  test    eax, eax
0x1800102e4  jns     loc_180010379
0x1800102ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800102f1  test    rcx, rcx
0x1800102f4  jnz     short loc_180010337
0x1800102f6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800102fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010303  mov     rcx, rax
0x180010306  test    rax, rax
0x180010309  jz      short loc_180010329
0x18001030b  mov     rax, [rax]
0x18001030e  mov     edx, 7F0h
0x180010313  mov     rax, [rax+8]
0x180010317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001031c  test    eax, eax
0x18001031e  jz      short loc_180010329
0x180010320  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010327  jmp     short loc_180010337
0x180010329  lea     rcx, qword_180069A90; this
0x180010330  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010337  cmp     [rcx+8], r13b
0x18001033b  jz      short loc_18001035E
0x18001033d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010342  cmp     [rax+7CCh], ebx
0x180010348  jz      short loc_18001035E
0x18001034a  mov     r9d, ebx; int
0x18001034d  mov     r8d, 2F3h; int
0x180010353  mov     rdx, rdi; char *
0x180010356  mov     rcx, rax; this
0x180010359  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001035e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180010363  mov     edi, 1
0x180010368  cmp     al, dil
0x18001036b  jb      loc_1800105C3
0x180010371  lea     edx, [rdi+58h]
0x180010374  jmp     loc_180010207
0x180010379  mov     rdx, [rbp+var_20]; struct IMFAttributes *
0x18001037d  mov     edi, 1
0x180010382  movzx   esi, di
0x180010385  test    rdx, rdx
0x180010388  jz      loc_180010448
0x18001038e  mov     rax, [rbp+ppIProfile]
0x180010392  lea     r8, MFMediaType_Audio; struct _GUID *
0x180010399  mov     r9d, edi; unsigned __int16
0x18001039c  mov     [rsp+58h+var_38], rax; struct IMFASFProfile *
0x1800103a1  mov     rcx, r14; this
0x1800103a4  call    ?ConvertStream@CASFTranscodeProfileConverter@@AEAAJPEAUIMFAttributes@@AEBU_GUID@@GPEAUIMFASFProfile@@@Z; CASFTranscodeProfileConverter::ConvertStream(IMFAttributes *,_GUID const &,ushort,IMFASFProfile *)
0x1800103a9  mov     ebx, eax
0x1800103ab  test    eax, eax
0x1800103ad  jns     loc_180010443
0x1800103b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800103ba  test    rcx, rcx
0x1800103bd  jnz     short loc_180010400
0x1800103bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800103c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800103cc  mov     rcx, rax
0x1800103cf  test    rax, rax
0x1800103d2  jz      short loc_1800103F2
0x1800103d4  mov     rax, [rax]
0x1800103d7  mov     edx, 7F0h
0x1800103dc  mov     rax, [rax+8]
0x1800103e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103e5  test    eax, eax
0x1800103e7  jz      short loc_1800103F2
0x1800103e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800103f0  jmp     short loc_180010400
0x1800103f2  lea     rcx, qword_180069A90; this
0x1800103f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010400  cmp     [rcx+8], r13b
0x180010404  jz      short loc_18001042B
0x180010406  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001040b  cmp     [rax+7CCh], ebx
0x180010411  jz      short loc_18001042B
0x180010413  mov     r9d, ebx; int
0x180010416  lea     rdx, aCasftranscodep_1; "CASFTranscodeProfileConverter::ConvertP"...
0x18001041d  mov     r8d, 2F6h; int
0x180010423  mov     rcx, rax; this
0x180010426  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001042b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180010430  cmp     al, dil
0x180010433  jb      loc_1800105C3
0x180010439  mov     edx, 5Ah ; 'Z'
0x18001043e  jmp     loc_180010207
0x180010443  mov     esi, 2
0x180010448  mov     rax, [r15]
0x18001044b  lea     rdx, [rbp+var_18]
0x18001044f  mov     rcx, r15
0x180010452  mov     rax, [rax+30h]
0x180010456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001045b  mov     ebx, eax
0x18001045d  test    eax, eax
0x18001045f  jns     loc_1800104F5
0x180010465  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001046c  test    rcx, rcx
0x18001046f  jnz     short loc_1800104B2
0x180010471  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010477  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001047e  mov     rcx, rax
0x180010481  test    rax, rax
0x180010484  jz      short loc_1800104A4
0x180010486  mov     rax, [rax]
0x180010489  mov     edx, 7F0h
0x18001048e  mov     rax, [rax+8]
0x180010492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010497  test    eax, eax
0x180010499  jz      short loc_1800104A4
0x18001049b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800104a2  jmp     short loc_1800104B2
0x1800104a4  lea     rcx, qword_180069A90; this
0x1800104ab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800104b2  cmp     [rcx+8], r13b
0x1800104b6  jz      short loc_1800104DD
0x1800104b8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800104bd  cmp     [rax+7CCh], ebx
0x1800104c3  jz      short loc_1800104DD
0x1800104c5  mov     r9d, ebx; int
0x1800104c8  lea     rdx, aCasftranscodep_1; "CASFTranscodeProfileConverter::ConvertP"...
0x1800104cf  mov     r8d, 2FAh; int
0x1800104d5  mov     rcx, rax; this
0x1800104d8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800104dd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800104e2  cmp     al, dil
0x1800104e5  jb      loc_1800105C3
0x1800104eb  mov     edx, 5Bh ; '['
0x1800104f0  jmp     loc_180010207
0x1800104f5  mov     rcx, [rbp+var_18]
0x1800104f9  test    rcx, rcx
0x1800104fc  jz      loc_1800105B7
0x180010502  mov     rax, [rbp+ppIProfile]
0x180010506  lea     r8, MFMediaType_Video; struct _GUID *
0x18001050d  mov     rdx, rcx; struct IMFAttributes *
0x180010510  mov     [rsp+58h+var_38], rax; struct IMFASFProfile *
0x180010515  mov     rcx, r14; this
0x180010518  movzx   r9d, si; unsigned __int16
0x18001051c  call    ?ConvertStream@CASFTranscodeProfileConverter@@AEAAJPEAUIMFAttributes@@AEBU_GUID@@GPEAUIMFASFProfile@@@Z; CASFTranscodeProfileConverter::ConvertStream(IMFAttributes *,_GUID const &,ushort,IMFASFProfile *)
0x180010521  mov     ebx, eax
0x180010523  test    eax, eax
0x180010525  jns     loc_1800105B7
0x18001052b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010532  test    rcx, rcx
0x180010535  jnz     short loc_180010578
0x180010537  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001053d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010544  mov     rcx, rax
0x180010547  test    rax, rax
0x18001054a  jz      short loc_18001056A
0x18001054c  mov     rax, [rax]
0x18001054f  mov     edx, 7F0h
0x180010554  mov     rax, [rax+8]
0x180010558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001055d  test    eax, eax
0x18001055f  jz      short loc_18001056A
0x180010561  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010568  jmp     short loc_180010578
0x18001056a  lea     rcx, qword_180069A90; this
0x180010571  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010578  cmp     [rcx+8], r13b
0x18001057c  jz      short loc_1800105A3
0x18001057e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010583  cmp     [rax+7CCh], ebx
0x180010589  jz      short loc_1800105A3
0x18001058b  mov     r9d, ebx; int
0x18001058e  lea     rdx, aCasftranscodep_1; "CASFTranscodeProfileConverter::ConvertP"...
0x180010595  mov     r8d, 2FDh; int
0x18001059b  mov     rcx, rax; this
0x18001059e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800105a3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800105a8  cmp     al, dil
0x1800105ab  jb      short loc_1800105C3
0x1800105ad  mov     edx, 5Ch ; '\'
0x1800105b2  jmp     loc_180010207
0x1800105b7  mov     rax, [rbp+ppIProfile]
0x1800105bb  mov     [r12], rax
0x1800105bf  mov     [rbp+ppIProfile], r13
0x1800105c3  mov     rcx, [rbp+var_20]
0x1800105c7  test    rcx, rcx
0x1800105ca  jz      short loc_1800105DC
0x1800105cc  mov     rax, [rcx]
0x1800105cf  mov     rax, [rax+10h]
0x1800105d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105d8  mov     [rbp+var_20], r13
0x1800105dc  mov     rcx, [rbp+var_18]
0x1800105e0  test    rcx, rcx
0x1800105e3  jz      short loc_1800105F5
  ... truncated ...
```
