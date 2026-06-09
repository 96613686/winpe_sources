# MFCreateTranscodeProfile

- ea: `0x18001c050`
- end: `0x18001c237`
- name: `MFCreateTranscodeProfile`
- size: `487`
- prototype: `HRESULT __stdcall(IMFTranscodeProfile **ppTranscodeProfile)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x18001d754`
- `0x18002c348`
- `0x180039a70`
- `0x18003acf0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180019ad4`
- `0x18001a330`
- `0x18001c050`
- `0x18001c280`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c097`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c166`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c097`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c166`

## string_xrefs

- `0x18001c05d`: `MFCreateTranscodeProfile`
- `0x18001c0ee`: `MFCreateTranscodeProfile`
- `0x18001c1bd`: `MFCreateTranscodeProfile`

## pseudocode

```c
HRESULT __stdcall MFCreateTranscodeProfile(IMFTranscodeProfile **ppTranscodeProfile)
{
  __int64 v2; // rdx
  __int64 *v3; // rcx
  int v4; // ebx
  CallStackTracing *v5; // rax
  struct CallStackContext *v6; // rax
  __int64 v7; // rdx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  void *v11; // rcx
  void *v13; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v13, "MFCreateTranscodeProfile", 107);
  v13 = 0;
  if ( ppTranscodeProfile )
  {
    *ppTranscodeProfile = 0;
    v4 = CTranscodeProfile::CreateInstance(&IID_IMFTranscodeProfile, &v13);
    if ( v4 >= 0 )
    {
      v11 = 0;
      *ppTranscodeProfile = (IMFTranscodeProfile *)v13;
    }
    else
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
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
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "MFCreateTranscodeProfile", 115, v4);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids, 0, v4);
      v11 = v13;
    }
    if ( v11 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  else
  {
    v3 = (__int64 *)CallStackTracing::s_wpInstance;
    v4 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v5 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
      CallStackTracing::s_wpInstance = v5;
      if ( v5 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2032) )
      {
        v3 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v3 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v3 + 8) )
    {
      v6 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v3);
      if ( *((_DWORD *)v6 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v6, "MFCreateTranscodeProfile", 112, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_60c454de96f7327ebad2115a8fee1984_Traceguids,
        0,
        -2147467261);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v13);
  return v4;
}

```

## disassembly

```asm
0x18001c050  mov     [rsp+arg_8], rbx
0x18001c055  push    rdi
0x18001c056  sub     rsp, 30h
0x18001c05a  mov     rdi, rcx
0x18001c05d  lea     rdx, aMfcreatetransc_4; "MFCreateTranscodeProfile"
0x18001c064  lea     rcx, [rsp+38h+arg_0]; this
0x18001c069  mov     r8d, 6Bh ; 'k'; int
0x18001c06f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001c074  mov     [rsp+38h+arg_0], 0
0x18001c07d  test    rdi, rdi
0x18001c080  jnz     loc_18001C138
0x18001c086  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c08d  mov     ebx, 80004003h
0x18001c092  test    rcx, rcx
0x18001c095  jnz     short loc_18001C0D8
0x18001c097  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001c09d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c0a4  mov     rcx, rax
0x18001c0a7  test    rax, rax
0x18001c0aa  jz      short loc_18001C0CA
0x18001c0ac  mov     rax, [rax]
0x18001c0af  mov     edx, 7F0h
0x18001c0b4  mov     rax, [rax+8]
0x18001c0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0bd  test    eax, eax
0x18001c0bf  jz      short loc_18001C0CA
0x18001c0c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c0c8  jmp     short loc_18001C0D8
0x18001c0ca  lea     rcx, qword_180069A90; this
0x18001c0d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c0d8  cmp     byte ptr [rcx+8], 0
0x18001c0dc  jz      short loc_18001C103
0x18001c0de  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001c0e3  cmp     [rax+7CCh], ebx
0x18001c0e9  jz      short loc_18001C103
0x18001c0eb  mov     r9d, ebx; int
0x18001c0ee  lea     rdx, aMfcreatetransc_4; "MFCreateTranscodeProfile"
0x18001c0f5  mov     r8d, 70h ; 'p'; int
0x18001c0fb  mov     rcx, rax; this
0x18001c0fe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001c103  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001c108  cmp     al, 1
0x18001c10a  jb      loc_18001C220
0x18001c110  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c117  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x18001c11e  mov     edx, 0Bh
0x18001c123  mov     [rsp+38h+var_18], ebx
0x18001c127  xor     r9d, r9d
0x18001c12a  mov     rcx, [rcx+10h]
0x18001c12e  call    WPP_SF_qd
0x18001c133  jmp     loc_18001C220
0x18001c138  lea     rdx, [rsp+38h+arg_0]; void **
0x18001c13d  mov     qword ptr [rdi], 0
0x18001c144  lea     rcx, IID_IMFTranscodeProfile; struct _GUID *
0x18001c14b  call    ?CreateInstance@CTranscodeProfile@@SAJAEBU_GUID@@PEAPEAX@Z; CTranscodeProfile::CreateInstance(_GUID const &,void * *)
0x18001c150  mov     ebx, eax
0x18001c152  test    eax, eax
0x18001c154  jns     loc_18001C205
0x18001c15a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c161  test    rcx, rcx
0x18001c164  jnz     short loc_18001C1A7
0x18001c166  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001c16c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c173  mov     rcx, rax
0x18001c176  test    rax, rax
0x18001c179  jz      short loc_18001C199
0x18001c17b  mov     rax, [rax]
0x18001c17e  mov     edx, 7F0h
0x18001c183  mov     rax, [rax+8]
0x18001c187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c18c  test    eax, eax
0x18001c18e  jz      short loc_18001C199
0x18001c190  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c197  jmp     short loc_18001C1A7
0x18001c199  lea     rcx, qword_180069A90; this
0x18001c1a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c1a7  cmp     byte ptr [rcx+8], 0
0x18001c1ab  jz      short loc_18001C1D2
0x18001c1ad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001c1b2  cmp     [rax+7CCh], ebx
0x18001c1b8  jz      short loc_18001C1D2
0x18001c1ba  mov     r9d, ebx; int
0x18001c1bd  lea     rdx, aMfcreatetransc_4; "MFCreateTranscodeProfile"
0x18001c1c4  mov     r8d, 73h ; 's'; int
0x18001c1ca  mov     rcx, rax; this
0x18001c1cd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001c1d2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001c1d7  cmp     al, 1
0x18001c1d9  jb      short loc_18001C1FE
0x18001c1db  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1e2  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x18001c1e9  mov     edx, 0Ch
0x18001c1ee  mov     [rsp+38h+var_18], ebx
0x18001c1f2  xor     r9d, r9d
0x18001c1f5  mov     rcx, [rcx+10h]
0x18001c1f9  call    WPP_SF_qd
0x18001c1fe  mov     rcx, [rsp+38h+arg_0]
0x18001c203  jmp     short loc_18001C20F
0x18001c205  mov     rax, [rsp+38h+arg_0]
0x18001c20a  xor     ecx, ecx
0x18001c20c  mov     [rdi], rax
0x18001c20f  test    rcx, rcx
0x18001c212  jz      short loc_18001C220
0x18001c214  mov     rax, [rcx]
0x18001c217  mov     rax, [rax+10h]
0x18001c21b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c220  lea     rcx, [rsp+38h+arg_0]; this
0x18001c225  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001c22a  mov     eax, ebx
0x18001c22c  mov     rbx, [rsp+38h+arg_8]
0x18001c231  add     rsp, 30h
0x18001c235  pop     rdi
0x18001c236  retn
```
