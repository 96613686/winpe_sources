# CDShowTransEnumMediaTypes::Next(ulong,_AMMediaType * *,ulong *)

- ea: `0x18005c750`
- end: `0x18005c961`
- name: `?Next@CDShowTransEnumMediaTypes@@UEAAJKPEAPEAU_AMMediaType@@PEAK@Z`
- size: `529`
- prototype: `int(CDShowTransEnumMediaTypes *__hidden this, unsigned int, struct _AMMediaType **, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x180032a50`
- `0x180051ce4`
- `0x18005c750`
- `0x1800c9010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c7a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c892`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c7a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c892`
- `MFPlat!MFCreateAMMediaTypeFromMFMediaType` at `0x18005c870`
- `MFPlat!MFCreateAMMediaTypeFromMFMediaType` at `0x18005c870`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDShowTransEnumMediaTypes::Next(
        IMFMediaType **this,
        int a2,
        struct _AMMediaType **a3,
        unsigned int *a4)
{
  HRESULT v7; // ebx
  CallStackTracing *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  unsigned int v14; // esi
  GUID guidFormatBlockType; // [rsp+30h] [rbp-38h] BYREF
  char v17; // [rsp+70h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    v14 = 0;
    v7 = 1;
  }
  else
  {
    if ( !a2 )
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v17, "CDShowTransEnumMediaTypes::Next", 2024);
      v7 = -2147024809;
      v8 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        {
          v8 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v8);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CDShowTransEnumMediaTypes::Next", 2024, -2147024809);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          89,
          &WPP_e67ca36682193615575df34b6326caef_Traceguids,
          this,
          -2147024809);
LABEL_13:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v17);
      return (unsigned int)v7;
    }
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v17, "CDShowTransEnumMediaTypes::Next", 2026);
    guidFormatBlockType = GUID_00000000_0000_0000_0000_000000000000;
    v7 = MFCreateAMMediaTypeFromMFMediaType(this[4], &guidFormatBlockType, a3);
    if ( v7 < 0 )
    {
      v11 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext(v11);
        if ( *((_DWORD *)v13 + 499) != v7 )
          CallStackContext::TraceFailure(v13, "CDShowTransEnumMediaTypes::Next", 2026, v7);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_e67ca36682193615575df34b6326caef_Traceguids, this, v7);
      goto LABEL_13;
    }
    v14 = 1;
    ++*((_DWORD *)this + 6);
    v7 = 0;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v17);
  }
  if ( a4 )
    *a4 = v14;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005c750  push    rbx
0x18005c752  push    rsi
0x18005c753  push    rdi
0x18005c754  push    r14
0x18005c756  sub     rsp, 48h
0x18005c75a  mov     r14, r9
0x18005c75d  mov     rbx, r8
0x18005c760  mov     rdi, rcx
0x18005c763  cmp     dword ptr [rcx+18h], 0
0x18005c767  jnz     loc_18005C947
0x18005c76d  lea     rcx, [rsp+68h+arg_0]; this
0x18005c772  test    edx, edx
0x18005c774  lea     rdx, aCdshowtransenu; "CDShowTransEnumMediaTypes::Next"
0x18005c77b  jnz     loc_18005C849
0x18005c781  mov     esi, 7E8h
0x18005c786  mov     r8d, esi; int
0x18005c789  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005c78e  nop
0x18005c78f  mov     ebx, 80070057h
0x18005c794  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c79b  test    rcx, rcx
0x18005c79e  jnz     short loc_18005C7E5
0x18005c7a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005c7a7  nop     dword ptr [rax+rax+00h]
0x18005c7ac  mov     rcx, rax
0x18005c7af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c7b6  test    rax, rax
0x18005c7b9  jz      short loc_18005C7D7
0x18005c7bb  mov     rax, [rax]
0x18005c7be  lea     edx, [rsi+8]
0x18005c7c1  mov     rax, [rax+8]
0x18005c7c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c7ca  test    eax, eax
0x18005c7cc  jz      short loc_18005C7D7
0x18005c7ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c7d5  jmp     short loc_18005C7E5
0x18005c7d7  lea     rcx, qword_1800EB130; this
0x18005c7de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c7e5  cmp     byte ptr [rcx+8], 0
0x18005c7e9  jz      short loc_18005C80D
0x18005c7eb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005c7f0  cmp     [rax+7CCh], ebx
0x18005c7f6  jz      short loc_18005C80D
0x18005c7f8  mov     r9d, ebx; int
0x18005c7fb  mov     r8d, esi; int
0x18005c7fe  lea     rdx, aCdshowtransenu; "CDShowTransEnumMediaTypes::Next"
0x18005c805  mov     rcx, rax; this
0x18005c808  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005c80d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005c814  jb      short loc_18005C83A
0x18005c816  mov     edx, 59h ; 'Y'
0x18005c81b  mov     [rsp+68h+var_48], ebx
0x18005c81f  mov     r9, rdi
0x18005c822  lea     r8, WPP_e67ca36682193615575df34b6326caef_Traceguids
0x18005c829  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c830  mov     rcx, [rcx+10h]
0x18005c834  call    WPP_SF_qD
0x18005c839  nop
0x18005c83a  lea     rcx, [rsp+68h+arg_0]; this
0x18005c83f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18005c844  jmp     loc_18005C954
0x18005c849  mov     esi, 7EAh
0x18005c84e  mov     r8d, esi; int
0x18005c851  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005c856  nop
0x18005c857  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18005c85e  movdqu  xmmword ptr [rsp+68h+guidFormatBlockType.Data1], xmm0
0x18005c864  mov     r8, rbx; ppAMType
0x18005c867  lea     rdx, [rsp+68h+guidFormatBlockType]; guidFormatBlockType
0x18005c86c  mov     rcx, [rdi+20h]; pMFType
0x18005c870  call    cs:__imp_MFCreateAMMediaTypeFromMFMediaType
0x18005c877  nop     dword ptr [rax+rax+00h]
0x18005c87c  mov     ebx, eax
0x18005c87e  test    eax, eax
0x18005c880  jns     loc_18005C931
0x18005c886  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c88d  test    rcx, rcx
0x18005c890  jnz     short loc_18005C8D7
0x18005c892  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005c899  nop     dword ptr [rax+rax+00h]
0x18005c89e  mov     rcx, rax
0x18005c8a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c8a8  test    rax, rax
0x18005c8ab  jz      short loc_18005C8C9
0x18005c8ad  mov     rax, [rax]
0x18005c8b0  lea     edx, [rsi+6]
0x18005c8b3  mov     rax, [rax+8]
0x18005c8b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c8bc  test    eax, eax
0x18005c8be  jz      short loc_18005C8C9
0x18005c8c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c8c7  jmp     short loc_18005C8D7
0x18005c8c9  lea     rcx, qword_1800EB130; this
0x18005c8d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c8d7  cmp     byte ptr [rcx+8], 0
0x18005c8db  jz      short loc_18005C8FF
0x18005c8dd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005c8e2  cmp     [rax+7CCh], ebx
0x18005c8e8  jz      short loc_18005C8FF
0x18005c8ea  mov     r9d, ebx; int
0x18005c8ed  mov     r8d, esi; int
0x18005c8f0  lea     rdx, aCdshowtransenu; "CDShowTransEnumMediaTypes::Next"
0x18005c8f7  mov     rcx, rax; this
0x18005c8fa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005c8ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005c906  jb      short loc_18005C92C
0x18005c908  mov     edx, 5Ah ; 'Z'
0x18005c90d  mov     [rsp+68h+var_48], ebx
0x18005c911  mov     r9, rdi
0x18005c914  lea     r8, WPP_e67ca36682193615575df34b6326caef_Traceguids
0x18005c91b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c922  mov     rcx, [rcx+10h]
0x18005c926  call    WPP_SF_qD
0x18005c92b  nop
0x18005c92c  jmp     loc_18005C83A
0x18005c931  mov     esi, 1
0x18005c936  inc     dword ptr [rdi+18h]
0x18005c939  xor     ebx, ebx
0x18005c93b  lea     rcx, [rsp+68h+arg_0]; this
0x18005c940  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18005c945  jmp     short loc_18005C94C
0x18005c947  xor     esi, esi
0x18005c949  lea     ebx, [rsi+1]
0x18005c94c  test    r14, r14
0x18005c94f  jz      short loc_18005C954
0x18005c951  mov     [r14], esi
0x18005c954  mov     eax, ebx
0x18005c956  add     rsp, 48h
0x18005c95a  pop     r14
0x18005c95c  pop     rdi
0x18005c95d  pop     rsi
0x18005c95e  pop     rbx
0x18005c95f  retn
```
