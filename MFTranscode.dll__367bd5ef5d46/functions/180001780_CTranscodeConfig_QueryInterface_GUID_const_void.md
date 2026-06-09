# CTranscodeConfig::QueryInterface(_GUID const &,void * *)

- ea: `0x180001780`
- end: `0x180001998`
- name: `?QueryInterface@CTranscodeConfig@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `536`
- prototype: `int(CTranscodeConfig *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180001780`
- `0x1800035c0`
- `0x180004a40`
- `0x18001a330`
- `0x18001c280`
- `0x18004f3c8`
- `0x18004f410`
- `0x1800594b0`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001806`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800018f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001806`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800018f1`

## string_xrefs

- `0x1800017b8`: `CTranscodeConfig::QueryInterface`

## pseudocode

```c
__int64 __fastcall CTranscodeConfig::QueryInterface(__int64 this, const struct _GUID *a2, void **a3)
{
  __int64 *v3; // rbx
  volatile signed __int32 *v6; // rsi
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v8; // edi
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  char v17; // [rsp+60h] [rbp+18h] BYREF

  v3 = (__int64 *)CallStackTracing::s_wpInstance;
  v6 = (volatile signed __int32 *)this;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v3 = (__int64 *)CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v3 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v3);
    this = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)this < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      this *= 2;
      *((_QWORD *)ThreadRelativeContext + this) = "CTranscodeConfig::QueryInterface";
      *((_DWORD *)ThreadRelativeContext + 2 * this + 2) = 330;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
    v3 = (__int64 *)CallStackTracing::s_wpInstance;
  }
  if ( a3 )
  {
    *a3 = 0;
    if ( !memcmp_0(a2, &IID_IMFTranscodeConfigPriv, 0x10u) || !memcmp_0(a2, &IID_IUnknown, 0x10u) )
    {
      v8 = 0;
      *a3 = (void *)v6;
      _InterlockedIncrement(v6 + 2);
      goto LABEL_32;
    }
    v8 = -2147467262;
    if ( !v3 )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v13, v12);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
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
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v3);
      if ( *((_DWORD *)v15 + 499) != -2147467262 )
        CallStackContext::TraceFailure(v15, "CTranscodeConfig::QueryInterface", 343, -2147467262);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 52;
      goto LABEL_18;
    }
  }
  else
  {
    v8 = -2147467261;
    if ( !v3 )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
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
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v3);
      if ( *((_DWORD *)v10 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v10, "CTranscodeConfig::QueryInterface", 330, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 51;
LABEL_18:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids, v6, v8);
    }
  }
LABEL_32:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v17);
  return v8;
}

```

## disassembly

```asm
0x180001780  mov     [rsp+arg_0], rbx
0x180001785  mov     [rsp+arg_8], rsi
0x18000178a  push    rdi
0x18000178b  push    r12
0x18000178d  push    r14
0x18000178f  sub     rsp, 30h
0x180001793  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000179a  mov     r14, r8
0x18000179d  mov     rdi, rdx
0x1800017a0  mov     rsi, rcx
0x1800017a3  test    rbx, rbx
0x1800017a6  jnz     short loc_1800017B4
0x1800017a8  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800017ad  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800017b4  cmp     byte ptr [rbx+8], 0
0x1800017b8  lea     r12, aCtranscodeconf_5; "CTranscodeConfig::QueryInterface"
0x1800017bf  jz      short loc_1800017F3
0x1800017c1  mov     rcx, rbx; this
0x1800017c4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800017c9  mov     ecx, [rax+7C4h]
0x1800017cf  cmp     ecx, [rax+7C8h]
0x1800017d5  jnb     short loc_1800017E6
0x1800017d7  add     rcx, rcx
0x1800017da  mov     [rax+rcx*8], r12
0x1800017de  mov     dword ptr [rax+rcx*8+8], 14Ah
0x1800017e6  inc     dword ptr [rax+7C4h]
0x1800017ec  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800017f3  test    r14, r14
0x1800017f6  jnz     loc_1800018A6
0x1800017fc  mov     edi, 80004003h
0x180001801  test    rbx, rbx
0x180001804  jnz     short loc_180001847
0x180001806  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000180c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180001813  mov     rcx, rax
0x180001816  test    rax, rax
0x180001819  jz      short loc_180001839
0x18000181b  mov     rax, [rax]
0x18000181e  mov     edx, 7F0h
0x180001823  mov     rax, [rax+8]
0x180001827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000182c  test    eax, eax
0x18000182e  jz      short loc_180001839
0x180001830  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001837  jmp     short loc_180001847
0x180001839  lea     rbx, qword_180069A90
0x180001840  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180001847  cmp     byte ptr [rbx+8], 0
0x18000184b  jz      short loc_180001871
0x18000184d  mov     rcx, rbx; this
0x180001850  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180001855  cmp     [rax+7CCh], edi
0x18000185b  jz      short loc_180001871
0x18000185d  mov     r9d, edi; int
0x180001860  mov     r8d, 14Ah; int
0x180001866  mov     rdx, r12; char *
0x180001869  mov     rcx, rax; this
0x18000186c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180001871  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180001876  cmp     al, 1
0x180001878  jb      loc_180001978
0x18000187e  mov     edx, 33h ; '3'
0x180001883  mov     rcx, cs:WPP_GLOBAL_Control
0x18000188a  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x180001891  mov     r9, rsi
0x180001894  mov     [rsp+48h+var_28], edi
0x180001898  mov     rcx, [rcx+10h]
0x18000189c  call    WPP_SF_qd
0x1800018a1  jmp     loc_180001978
0x1800018a6  mov     r8d, 10h; Size
0x1800018ac  mov     qword ptr [r14], 0
0x1800018b3  lea     rdx, IID_IMFTranscodeConfigPriv; Buf2
0x1800018ba  mov     rcx, rdi; Buf1
0x1800018bd  call    memcmp_0
0x1800018c2  test    eax, eax
0x1800018c4  jz      loc_18000196F
0x1800018ca  mov     r8d, 10h; Size
0x1800018d0  lea     rdx, IID_IUnknown; Buf2
0x1800018d7  mov     rcx, rdi; Buf1
0x1800018da  call    memcmp_0
0x1800018df  test    eax, eax
0x1800018e1  jz      loc_18000196F
0x1800018e7  mov     edi, 80004002h
0x1800018ec  test    rbx, rbx
0x1800018ef  jnz     short loc_180001932
0x1800018f1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800018f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800018fe  mov     rcx, rax
0x180001901  test    rax, rax
0x180001904  jz      short loc_180001924
0x180001906  mov     rax, [rax]
0x180001909  mov     edx, 7F0h
0x18000190e  mov     rax, [rax+8]
0x180001912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001917  test    eax, eax
0x180001919  jz      short loc_180001924
0x18000191b  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001922  jmp     short loc_180001932
0x180001924  lea     rbx, qword_180069A90
0x18000192b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180001932  cmp     byte ptr [rbx+8], 0
0x180001936  jz      short loc_18000195C
0x180001938  mov     rcx, rbx; this
0x18000193b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180001940  cmp     [rax+7CCh], edi
0x180001946  jz      short loc_18000195C
0x180001948  mov     r9d, edi; int
0x18000194b  mov     r8d, 157h; int
0x180001951  mov     rdx, r12; char *
0x180001954  mov     rcx, rax; this
0x180001957  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000195c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180001961  cmp     al, 1
0x180001963  jb      short loc_180001978
0x180001965  mov     edx, 34h ; '4'
0x18000196a  jmp     loc_180001883
0x18000196f  xor     edi, edi
0x180001971  mov     [r14], rsi
0x180001974  lock inc dword ptr [rsi+8]
0x180001978  lea     rcx, [rsp+48h+arg_10]; this
0x18000197d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180001982  mov     rbx, [rsp+48h+arg_0]
0x180001987  mov     eax, edi
0x180001989  mov     rsi, [rsp+48h+arg_8]
0x18000198e  add     rsp, 30h
0x180001992  pop     r14
0x180001994  pop     r12
0x180001996  pop     rdi
0x180001997  retn
```
