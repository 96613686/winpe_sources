# CTranscodeConfig::SetOutputPath(ushort const *)

- ea: `0x1800169a0`
- end: `0x180016be9`
- name: `?SetOutputPath@CTranscodeConfig@@UEAAJPEBG@Z`
- size: `585`
- prototype: `__int64 __fastcall(CTranscodeConfig *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800169a0`
- `0x180017008`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800169e8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016a85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016b35`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800169e8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016a85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016b35`

## string_xrefs

- `0x1800169b5`: `CTranscodeConfig::SetOutputPath`
- `0x180016a3f`: `CTranscodeConfig::SetOutputPath`
- `0x180016adc`: `CTranscodeConfig::SetOutputPath`
- `0x180016b8c`: `CTranscodeConfig::SetOutputPath`

## pseudocode

```c
__int64 __fastcall CTranscodeConfig::SetOutputPath(CTranscodeConfig *this, const unsigned __int16 *a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  unsigned int v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v18; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v18, "CTranscodeConfig::SetOutputPath", 413);
  if ( a2 )
  {
    if ( *a2 )
    {
      CMFBaseStringT<unsigned short>::operator=((char *)this + 32, a2);
      if ( *((int *)this + 9) < 0 || (v6 = 0, !*((_DWORD *)this + 10)) )
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
        v6 = -2147024882;
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeConfig::SetOutputPath", 419, -2147024882);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 57;
          goto LABEL_35;
        }
      }
    }
    else
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      v6 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
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
        v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
        if ( *((_DWORD *)v12 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v12, "CTranscodeConfig::SetOutputPath", 414, -2147024809);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 56;
        goto LABEL_35;
      }
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    v6 = -2147467261;
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
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v8 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v8, "CTranscodeConfig::SetOutputPath", 413, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 55;
LABEL_35:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids, this, v6);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v18);
  return v6;
}

```

## disassembly

```asm
0x1800169a0  mov     [rsp+arg_0], rbx
0x1800169a5  mov     [rsp+arg_10], rsi
0x1800169aa  push    rdi
0x1800169ab  sub     rsp, 30h
0x1800169af  mov     rbx, rdx
0x1800169b2  mov     rdi, rcx
0x1800169b5  lea     rdx, aCtranscodeconf_4; "CTranscodeConfig::SetOutputPath"
0x1800169bc  mov     r8d, 19Dh; int
0x1800169c2  lea     rcx, [rsp+38h+arg_8]; this
0x1800169c7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800169cc  xor     esi, esi
0x1800169ce  test    rbx, rbx
0x1800169d1  jnz     loc_180016A6B
0x1800169d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800169de  mov     ebx, 80004003h
0x1800169e3  test    rcx, rcx
0x1800169e6  jnz     short loc_180016A29
0x1800169e8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800169ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800169f5  mov     rcx, rax
0x1800169f8  test    rax, rax
0x1800169fb  jz      short loc_180016A1B
0x1800169fd  mov     rax, [rax]
0x180016a00  mov     edx, 7F0h
0x180016a05  mov     rax, [rax+8]
0x180016a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a0e  test    eax, eax
0x180016a10  jz      short loc_180016A1B
0x180016a12  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016a19  jmp     short loc_180016A29
0x180016a1b  lea     rcx, qword_180069A90; this
0x180016a22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180016a29  cmp     [rcx+8], sil
0x180016a2d  jz      short loc_180016A54
0x180016a2f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016a34  cmp     [rax+7CCh], ebx
0x180016a3a  jz      short loc_180016A54
0x180016a3c  mov     r9d, ebx; int
0x180016a3f  lea     rdx, aCtranscodeconf_4; "CTranscodeConfig::SetOutputPath"
0x180016a46  mov     r8d, 19Dh; int
0x180016a4c  mov     rcx, rax; this
0x180016a4f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180016a54  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180016a59  cmp     al, 1
0x180016a5b  jb      loc_180016BCD
0x180016a61  mov     edx, 37h ; '7'
0x180016a66  jmp     loc_180016BAF
0x180016a6b  cmp     [rbx], si
0x180016a6e  jnz     loc_180016B08
0x180016a74  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016a7b  mov     ebx, 80070057h
0x180016a80  test    rcx, rcx
0x180016a83  jnz     short loc_180016AC6
0x180016a85  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180016a8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016a92  mov     rcx, rax
0x180016a95  test    rax, rax
0x180016a98  jz      short loc_180016AB8
0x180016a9a  mov     rax, [rax]
0x180016a9d  mov     edx, 7F0h
0x180016aa2  mov     rax, [rax+8]
0x180016aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aab  test    eax, eax
0x180016aad  jz      short loc_180016AB8
0x180016aaf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016ab6  jmp     short loc_180016AC6
0x180016ab8  lea     rcx, qword_180069A90; this
0x180016abf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180016ac6  cmp     [rcx+8], sil
0x180016aca  jz      short loc_180016AF1
0x180016acc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016ad1  cmp     [rax+7CCh], ebx
0x180016ad7  jz      short loc_180016AF1
0x180016ad9  mov     r9d, ebx; int
0x180016adc  lea     rdx, aCtranscodeconf_4; "CTranscodeConfig::SetOutputPath"
0x180016ae3  mov     r8d, 19Eh; int
0x180016ae9  mov     rcx, rax; this
0x180016aec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180016af1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180016af6  cmp     al, 1
0x180016af8  jb      loc_180016BCD
0x180016afe  mov     edx, 38h ; '8'
0x180016b03  jmp     loc_180016BAF
0x180016b08  lea     rcx, [rdi+20h]
0x180016b0c  mov     rdx, rbx
0x180016b0f  call    ??4?$CMFBaseStringT@G@@QEAAAEBV0@PEBG@Z; CMFBaseStringT<ushort>::operator=(ushort const *)
0x180016b14  cmp     [rdi+24h], esi
0x180016b17  jl      short loc_180016B24
0x180016b19  mov     ebx, esi
0x180016b1b  cmp     [rdi+28h], esi
0x180016b1e  jnz     loc_180016BCD
0x180016b24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016b2b  mov     ebx, 8007000Eh
0x180016b30  test    rcx, rcx
0x180016b33  jnz     short loc_180016B76
0x180016b35  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180016b3b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016b42  mov     rcx, rax
0x180016b45  test    rax, rax
0x180016b48  jz      short loc_180016B68
0x180016b4a  mov     rax, [rax]
0x180016b4d  mov     edx, 7F0h
0x180016b52  mov     rax, [rax+8]
0x180016b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b5b  test    eax, eax
0x180016b5d  jz      short loc_180016B68
0x180016b5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016b66  jmp     short loc_180016B76
0x180016b68  lea     rcx, qword_180069A90; this
0x180016b6f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180016b76  cmp     [rcx+8], sil
0x180016b7a  jz      short loc_180016BA1
0x180016b7c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016b81  cmp     [rax+7CCh], ebx
0x180016b87  jz      short loc_180016BA1
0x180016b89  mov     r9d, ebx; int
0x180016b8c  lea     rdx, aCtranscodeconf_4; "CTranscodeConfig::SetOutputPath"
0x180016b93  mov     r8d, 1A3h; int
0x180016b99  mov     rcx, rax; this
0x180016b9c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180016ba1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180016ba6  cmp     al, 1
0x180016ba8  jb      short loc_180016BCD
0x180016baa  mov     edx, 39h ; '9'
0x180016baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180016bb6  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x180016bbd  mov     r9, rdi
0x180016bc0  mov     [rsp+38h+var_18], ebx
0x180016bc4  mov     rcx, [rcx+10h]
0x180016bc8  call    WPP_SF_qd
0x180016bcd  lea     rcx, [rsp+38h+arg_8]; this
0x180016bd2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180016bd7  mov     rsi, [rsp+38h+arg_10]
0x180016bdc  mov     eax, ebx
0x180016bde  mov     rbx, [rsp+38h+arg_0]
0x180016be3  add     rsp, 30h
0x180016be7  pop     rdi
0x180016be8  retn
```
