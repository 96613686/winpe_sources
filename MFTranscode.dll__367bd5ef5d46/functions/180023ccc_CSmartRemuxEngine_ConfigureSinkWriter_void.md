# CSmartRemuxEngine::_ConfigureSinkWriter(void)

- ea: `0x180023ccc`
- end: `0x180023e98`
- name: `?_ConfigureSinkWriter@CSmartRemuxEngine@@IEAAJXZ`
- size: `460`
- prototype: `__int64 __fastcall(CSmartRemuxEngine *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001eed8`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x180023ccc`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180023d2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180023de4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180023d2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180023de4`

## string_xrefs

- `0x180023cde`: `CSmartRemuxEngine::_ConfigureSinkWriter`
- `0x180023d84`: `CSmartRemuxEngine::_ConfigureSinkWriter`
- `0x180023e3b`: `CSmartRemuxEngine::_ConfigureSinkWriter`

## pseudocode

```c
__int64 __fastcall CSmartRemuxEngine::_ConfigureSinkWriter(CSmartRemuxEngine *this)
{
  __int64 v2; // rdx
  int v3; // ebx
  __int64 *v4; // rcx
  CallStackTracing *v5; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  char v13; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v13, "CSmartRemuxEngine::_ConfigureSinkWriter", 875);
  if ( *((_BYTE *)this + 117)
    && (v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)this + 5) + 24LL))(
               *((_QWORD *)this + 5),
               *((_QWORD *)this + 15),
               (char *)this + 100),
        v3 < 0) )
  {
    v4 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v5 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
      CallStackTracing::s_wpInstance = v5;
      if ( v5 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2032) )
      {
        v4 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v3 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CSmartRemuxEngine::_ConfigureSinkWriter", 879, v3);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v7 = 80;
LABEL_24:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, this, v3);
    }
  }
  else
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)this + 5) + 24LL))(
           *((_QWORD *)this + 5),
           *((_QWORD *)this + 19),
           (char *)this + 132);
    if ( v3 < 0 )
    {
      v9 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
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
        v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)v11 + 499) != v3 )
          CallStackContext::TraceFailure(v11, "CSmartRemuxEngine::_ConfigureSinkWriter", 882, v3);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v7 = 81;
        goto LABEL_24;
      }
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v13);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180023ccc  mov     [rsp+arg_8], rbx
0x180023cd1  mov     [rsp+arg_10], rsi
0x180023cd6  push    rdi
0x180023cd7  sub     rsp, 30h
0x180023cdb  mov     rdi, rcx
0x180023cde  lea     rdx, aCsmartremuxeng_22; "CSmartRemuxEngine::_ConfigureSinkWriter"
0x180023ce5  lea     rcx, [rsp+38h+arg_0]; this
0x180023cea  mov     r8d, 36Bh; int
0x180023cf0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180023cf5  cmp     byte ptr [rdi+75h], 0
0x180023cf9  jz      loc_180023DB0
0x180023cff  mov     rcx, [rdi+28h]
0x180023d03  lea     r8, [rdi+64h]
0x180023d07  mov     rdx, [rdi+78h]
0x180023d0b  mov     rax, [rcx]
0x180023d0e  mov     rax, [rax+18h]
0x180023d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d17  mov     ebx, eax
0x180023d19  test    eax, eax
0x180023d1b  jns     loc_180023DB0
0x180023d21  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180023d28  test    rcx, rcx
0x180023d2b  jnz     short loc_180023D6E
0x180023d2d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180023d33  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180023d3a  mov     rcx, rax
0x180023d3d  test    rax, rax
0x180023d40  jz      short loc_180023D60
0x180023d42  mov     rax, [rax]
0x180023d45  mov     edx, 7F0h
0x180023d4a  mov     rax, [rax+8]
0x180023d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d53  test    eax, eax
0x180023d55  jz      short loc_180023D60
0x180023d57  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180023d5e  jmp     short loc_180023D6E
0x180023d60  lea     rcx, qword_180069A90; this
0x180023d67  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180023d6e  cmp     byte ptr [rcx+8], 0
0x180023d72  jz      short loc_180023D99
0x180023d74  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180023d79  cmp     [rax+7CCh], ebx
0x180023d7f  jz      short loc_180023D99
0x180023d81  mov     r9d, ebx; int
0x180023d84  lea     rdx, aCsmartremuxeng_22; "CSmartRemuxEngine::_ConfigureSinkWriter"
0x180023d8b  mov     r8d, 36Fh; int
0x180023d91  mov     rcx, rax; this
0x180023d94  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180023d99  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180023d9e  cmp     al, 1
0x180023da0  jb      loc_180023E7C
0x180023da6  mov     edx, 50h ; 'P'
0x180023dab  jmp     loc_180023E5E
0x180023db0  mov     rcx, [rdi+28h]
0x180023db4  lea     r8, [rdi+84h]
0x180023dbb  mov     rdx, [rdi+98h]
0x180023dc2  mov     rax, [rcx]
0x180023dc5  mov     rax, [rax+18h]
0x180023dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023dce  mov     ebx, eax
0x180023dd0  test    eax, eax
0x180023dd2  jns     loc_180023E7C
0x180023dd8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180023ddf  test    rcx, rcx
0x180023de2  jnz     short loc_180023E25
0x180023de4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180023dea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180023df1  mov     rcx, rax
0x180023df4  test    rax, rax
0x180023df7  jz      short loc_180023E17
0x180023df9  mov     rax, [rax]
0x180023dfc  mov     edx, 7F0h
0x180023e01  mov     rax, [rax+8]
0x180023e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e0a  test    eax, eax
0x180023e0c  jz      short loc_180023E17
0x180023e0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180023e15  jmp     short loc_180023E25
0x180023e17  lea     rcx, qword_180069A90; this
0x180023e1e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180023e25  cmp     byte ptr [rcx+8], 0
0x180023e29  jz      short loc_180023E50
0x180023e2b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180023e30  cmp     [rax+7CCh], ebx
0x180023e36  jz      short loc_180023E50
0x180023e38  mov     r9d, ebx; int
0x180023e3b  lea     rdx, aCsmartremuxeng_22; "CSmartRemuxEngine::_ConfigureSinkWriter"
0x180023e42  mov     r8d, 372h; int
0x180023e48  mov     rcx, rax; this
0x180023e4b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180023e50  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180023e55  cmp     al, 1
0x180023e57  jb      short loc_180023E7C
0x180023e59  mov     edx, 51h ; 'Q'
0x180023e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e65  lea     r8, WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids
0x180023e6c  mov     r9, rdi
0x180023e6f  mov     [rsp+38h+var_18], ebx
0x180023e73  mov     rcx, [rcx+10h]
0x180023e77  call    WPP_SF_qd
0x180023e7c  lea     rcx, [rsp+38h+arg_0]; this
0x180023e81  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180023e86  mov     rsi, [rsp+38h+arg_10]
0x180023e8b  mov     eax, ebx
0x180023e8d  mov     rbx, [rsp+38h+arg_8]
0x180023e92  add     rsp, 30h
0x180023e96  pop     rdi
0x180023e97  retn
```
