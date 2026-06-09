# CTranscodeManager::CreateInstance(IMFTranscodeManagerPriv * *)

- ea: `0x180035498`
- end: `0x1800355cc`
- name: `?CreateInstance@CTranscodeManager@@SAJPEAPEAUIMFTranscodeManagerPriv@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(struct IMFTranscodeManagerPriv **)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x1800019a0`
- `0x180036820`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180012230`
- `0x180017074`
- `0x18001a330`
- `0x18001c280`
- `0x18003535c`
- `0x180035428`
- `0x180035498`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800354fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800354fb`

## string_xrefs

- `0x1800354d0`: `CTranscodeManager::CreateInstance`
- `0x180035552`: `CTranscodeManager::CreateInstance`

## pseudocode

```c
__int64 __fastcall CTranscodeManager::CreateInstance(struct IMFTranscodeManagerPriv **a1)
{
  CTranscodeManager *v2; // rax
  CTranscodeManager *v3; // rdi
  __int64 v4; // rdx
  __int64 *v5; // rcx
  int Interface; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v9; // edx
  char v11; // [rsp+40h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = (CTranscodeManager *)operator new(0x20u);
  if ( v2 )
    v3 = CTranscodeManager::CTranscodeManager(v2);
  else
    v3 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v11, "CTranscodeManager::CreateInstance", 532);
  if ( v3 )
  {
    Interface = CTranscodeManager::QueryInterface(v3, &IID_IMFTranscodeManagerPriv, (void **)a1);
    if ( Interface < 0 )
      CTranscodeManager::`scalar deleting destructor'(v3, v9);
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    Interface = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeManager::CreateInstance", 532, -2147024882);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids,
        0,
        -2147024882);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v11);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x180035498  mov     [rsp+arg_8], rbx
0x18003549d  push    rdi
0x18003549e  sub     rsp, 30h
0x1800354a2  mov     rbx, rcx
0x1800354a5  mov     qword ptr [rcx], 0
0x1800354ac  mov     ecx, 20h ; ' '; Size
0x1800354b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800354b6  test    rax, rax
0x1800354b9  jz      short loc_1800354C8
0x1800354bb  mov     rcx, rax; this
0x1800354be  call    ??0CTranscodeManager@@IEAA@XZ; CTranscodeManager::CTranscodeManager(void)
0x1800354c3  mov     rdi, rax
0x1800354c6  jmp     short loc_1800354CA
0x1800354c8  xor     edi, edi
0x1800354ca  mov     r8d, 214h; int
0x1800354d0  lea     rdx, aCtranscodemana_2; "CTranscodeManager::CreateInstance"
0x1800354d7  lea     rcx, [rsp+38h+arg_0]; this
0x1800354dc  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800354e1  test    rdi, rdi
0x1800354e4  jnz     loc_180035595
0x1800354ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800354f1  mov     ebx, 8007000Eh
0x1800354f6  test    rcx, rcx
0x1800354f9  jnz     short loc_18003553C
0x1800354fb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035501  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035508  mov     rcx, rax
0x18003550b  test    rax, rax
0x18003550e  jz      short loc_18003552E
0x180035510  mov     rax, [rax]
0x180035513  mov     edx, 7F0h
0x180035518  mov     rax, [rax+8]
0x18003551c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035521  test    eax, eax
0x180035523  jz      short loc_18003552E
0x180035525  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003552c  jmp     short loc_18003553C
0x18003552e  lea     rcx, qword_180069A90; this
0x180035535  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003553c  cmp     byte ptr [rcx+8], 0
0x180035540  jz      short loc_180035567
0x180035542  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035547  cmp     [rax+7CCh], ebx
0x18003554d  jz      short loc_180035567
0x18003554f  mov     r9d, ebx; int
0x180035552  lea     rdx, aCtranscodemana_2; "CTranscodeManager::CreateInstance"
0x180035559  mov     r8d, 214h; int
0x18003555f  mov     rcx, rax; this
0x180035562  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035567  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003556c  cmp     al, 1
0x18003556e  jb      short loc_1800355B5
0x180035570  mov     rcx, cs:WPP_GLOBAL_Control
0x180035577  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x18003557e  mov     edx, 42h ; 'B'
0x180035583  mov     [rsp+38h+var_18], ebx
0x180035587  xor     r9d, r9d
0x18003558a  mov     rcx, [rcx+10h]
0x18003558e  call    WPP_SF_qd
0x180035593  jmp     short loc_1800355B5
0x180035595  mov     r8, rbx; void **
0x180035598  lea     rdx, IID_IMFTranscodeManagerPriv; struct _GUID *
0x18003559f  mov     rcx, rdi; this
0x1800355a2  call    ?QueryInterface@CTranscodeManager@@UEAAJAEBU_GUID@@PEAPEAX@Z; CTranscodeManager::QueryInterface(_GUID const &,void * *)
0x1800355a7  mov     ebx, eax
0x1800355a9  test    eax, eax
0x1800355ab  jns     short loc_1800355B5
0x1800355ad  mov     rcx, rdi; this
0x1800355b0  call    ??_GCTranscodeManager@@QEAAPEAXI@Z; CTranscodeManager::`scalar deleting destructor'(uint)
0x1800355b5  lea     rcx, [rsp+38h+arg_0]; this
0x1800355ba  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800355bf  mov     eax, ebx
0x1800355c1  mov     rbx, [rsp+38h+arg_8]
0x1800355c6  add     rsp, 30h
0x1800355ca  pop     rdi
0x1800355cb  retn
```
