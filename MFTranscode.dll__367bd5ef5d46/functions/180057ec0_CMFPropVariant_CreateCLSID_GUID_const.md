# CMFPropVariant::CreateCLSID(_GUID const *)

- ea: `0x180057ec0`
- end: `0x180057fdd`
- name: `?CreateCLSID@CMFPropVariant@@QEAAJPEBU_GUID@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(CMFPropVariant *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180055d04`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x180057ec0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057edf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057edf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057f1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057f1e`

## string_xrefs

- `0x180057eeb`: `CMFPropVariant::CreateCLSID`
- `0x180057f75`: `CMFPropVariant::CreateCLSID`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::CreateCLSID(CMFPropVariant *this, const struct _GUID *a2)
{
  __int64 v4; // rdx
  struct _GUID *v5; // rax
  __int64 *v6; // rcx
  unsigned int v7; // ebx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v11; // [rsp+40h] [rbp+8h] BYREF

  *(_WORD *)this = 72;
  *((_QWORD *)this + 1) = CoTaskMemAlloc(0x10u);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v11, "CMFPropVariant::CreateCLSID", 1823);
  v5 = (struct _GUID *)*((_QWORD *)this + 1);
  if ( v5 )
  {
    v7 = 0;
    *v5 = *a2;
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::CreateCLSID", 1823, -2147024882);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        122,
        WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        this,
        -2147024882);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v11);
  return v7;
}

```

## disassembly

```asm
0x180057ec0  mov     [rsp+arg_8], rbx
0x180057ec5  mov     [rsp+arg_10], rsi
0x180057eca  push    rdi
0x180057ecb  sub     rsp, 30h
0x180057ecf  mov     rdi, rcx
0x180057ed2  mov     word ptr [rcx], 48h ; 'H'
0x180057ed7  mov     ecx, 10h; cb
0x180057edc  mov     rsi, rdx
0x180057edf  call    cs:__imp_CoTaskMemAlloc
0x180057ee5  mov     r8d, 71Fh; int
0x180057eeb  lea     rdx, aCmfpropvariant_3; "CMFPropVariant::CreateCLSID"
0x180057ef2  lea     rcx, [rsp+38h+arg_0]; this
0x180057ef7  mov     [rdi+8], rax
0x180057efb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180057f00  mov     rax, [rdi+8]
0x180057f04  test    rax, rax
0x180057f07  jnz     loc_180057FB8
0x180057f0d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057f14  mov     ebx, 8007000Eh
0x180057f19  test    rcx, rcx
0x180057f1c  jnz     short loc_180057F5F
0x180057f1e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180057f24  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057f2b  mov     rcx, rax
0x180057f2e  test    rax, rax
0x180057f31  jz      short loc_180057F51
0x180057f33  mov     rax, [rax]
0x180057f36  mov     edx, 7F0h
0x180057f3b  mov     rax, [rax+8]
0x180057f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f44  test    eax, eax
0x180057f46  jz      short loc_180057F51
0x180057f48  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057f4f  jmp     short loc_180057F5F
0x180057f51  lea     rcx, qword_180069A90; this
0x180057f58  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180057f5f  cmp     byte ptr [rcx+8], 0
0x180057f63  jz      short loc_180057F8A
0x180057f65  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057f6a  cmp     [rax+7CCh], ebx
0x180057f70  jz      short loc_180057F8A
0x180057f72  mov     r9d, ebx; int
0x180057f75  lea     rdx, aCmfpropvariant_3; "CMFPropVariant::CreateCLSID"
0x180057f7c  mov     r8d, 71Fh; int
0x180057f82  mov     rcx, rax; this
0x180057f85  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180057f8a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180057f8f  cmp     al, 1
0x180057f91  jb      short loc_180057FC1
0x180057f93  mov     rcx, cs:WPP_GLOBAL_Control
0x180057f9a  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180057fa1  mov     edx, 7Ah ; 'z'
0x180057fa6  mov     [rsp+38h+var_18], ebx
0x180057faa  mov     r9, rdi
0x180057fad  mov     rcx, [rcx+10h]
0x180057fb1  call    WPP_SF_qd
0x180057fb6  jmp     short loc_180057FC1
0x180057fb8  movups  xmm0, xmmword ptr [rsi]
0x180057fbb  xor     ebx, ebx
0x180057fbd  movdqu  xmmword ptr [rax], xmm0
0x180057fc1  lea     rcx, [rsp+38h+arg_0]; this
0x180057fc6  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180057fcb  mov     rsi, [rsp+38h+arg_10]
0x180057fd0  mov     eax, ebx
0x180057fd2  mov     rbx, [rsp+38h+arg_8]
0x180057fd7  add     rsp, 30h
0x180057fdb  pop     rdi
0x180057fdc  retn
```
