# GetTranscodeComponentCreator

- ea: `0x18001bec0`
- end: `0x18001c045`
- name: `GetTranscodeComponentCreator`
- size: `389`
- prototype: `__int64 __fastcall(struct IMFComponentCreator **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180019850`
- `0x18001a330`
- `0x18001bec0`
- `0x18001c280`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001befa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001bf9b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001befa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001bf9b`

## string_xrefs

- `0x18001bec9`: `GetTranscodeComponentCreator`
- `0x18001bf51`: `GetTranscodeComponentCreator`
- `0x18001bff2`: `GetTranscodeComponentCreator`

## pseudocode

```c
__int64 __fastcall GetTranscodeComponentCreator(struct IMFComponentCreator **a1)
{
  __int64 v2; // rdx
  __int64 *v3; // rcx
  int Instance; // ebx
  CallStackTracing *v5; // rax
  struct CallStackContext *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v13; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v13, "GetTranscodeComponentCreator", 127);
  if ( a1 )
  {
    Instance = CTranscodeComponentCreator::CreateInstance(a1);
    if ( Instance < 0 )
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != Instance )
          CallStackContext::TraceFailure(ThreadRelativeContext, "GetTranscodeComponentCreator", 133, Instance);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v7 = 15;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v3 = (__int64 *)CallStackTracing::s_wpInstance;
    Instance = -2147467261;
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
        CallStackContext::TraceFailure(v6, "GetTranscodeComponentCreator", 131, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v7 = 14;
LABEL_23:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids, 0, Instance);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v13);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001bec0  push    rbx
0x18001bec2  sub     rsp, 30h
0x18001bec6  mov     rbx, rcx
0x18001bec9  lea     rdx, aGettranscodeco_0; "GetTranscodeComponentCreator"
0x18001bed0  lea     rcx, [rsp+38h+arg_0]; this
0x18001bed5  mov     r8d, 7Fh; int
0x18001bedb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001bee0  test    rbx, rbx
0x18001bee3  jnz     loc_18001BF7D
0x18001bee9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bef0  mov     ebx, 80004003h
0x18001bef5  test    rcx, rcx
0x18001bef8  jnz     short loc_18001BF3B
0x18001befa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001bf00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bf07  mov     rcx, rax
0x18001bf0a  test    rax, rax
0x18001bf0d  jz      short loc_18001BF2D
0x18001bf0f  mov     rax, [rax]
0x18001bf12  mov     edx, 7F0h
0x18001bf17  mov     rax, [rax+8]
0x18001bf1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf20  test    eax, eax
0x18001bf22  jz      short loc_18001BF2D
0x18001bf24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bf2b  jmp     short loc_18001BF3B
0x18001bf2d  lea     rcx, qword_180069A90; this
0x18001bf34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bf3b  cmp     byte ptr [rcx+8], 0
0x18001bf3f  jz      short loc_18001BF66
0x18001bf41  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001bf46  cmp     [rax+7CCh], ebx
0x18001bf4c  jz      short loc_18001BF66
0x18001bf4e  mov     r9d, ebx; int
0x18001bf51  lea     rdx, aGettranscodeco_0; "GetTranscodeComponentCreator"
0x18001bf58  mov     r8d, 83h; int
0x18001bf5e  mov     rcx, rax; this
0x18001bf61  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001bf66  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001bf6b  cmp     al, 1
0x18001bf6d  jb      loc_18001C033
0x18001bf73  mov     edx, 0Eh
0x18001bf78  jmp     loc_18001C015
0x18001bf7d  mov     rcx, rbx; struct IMFComponentCreator **
0x18001bf80  call    ?CreateInstance@CTranscodeComponentCreator@@SAJPEAPEAUIMFComponentCreator@@@Z; CTranscodeComponentCreator::CreateInstance(IMFComponentCreator * *)
0x18001bf85  mov     ebx, eax
0x18001bf87  test    eax, eax
0x18001bf89  jns     loc_18001C033
0x18001bf8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bf96  test    rcx, rcx
0x18001bf99  jnz     short loc_18001BFDC
0x18001bf9b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001bfa1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bfa8  mov     rcx, rax
0x18001bfab  test    rax, rax
0x18001bfae  jz      short loc_18001BFCE
0x18001bfb0  mov     rax, [rax]
0x18001bfb3  mov     edx, 7F0h
0x18001bfb8  mov     rax, [rax+8]
0x18001bfbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfc1  test    eax, eax
0x18001bfc3  jz      short loc_18001BFCE
0x18001bfc5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bfcc  jmp     short loc_18001BFDC
0x18001bfce  lea     rcx, qword_180069A90; this
0x18001bfd5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bfdc  cmp     byte ptr [rcx+8], 0
0x18001bfe0  jz      short loc_18001C007
0x18001bfe2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001bfe7  cmp     [rax+7CCh], ebx
0x18001bfed  jz      short loc_18001C007
0x18001bfef  mov     r9d, ebx; int
0x18001bff2  lea     rdx, aGettranscodeco_0; "GetTranscodeComponentCreator"
0x18001bff9  mov     r8d, 85h; int
0x18001bfff  mov     rcx, rax; this
0x18001c002  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001c007  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001c00c  cmp     al, 1
0x18001c00e  jb      short loc_18001C033
0x18001c010  mov     edx, 0Fh
0x18001c015  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c01c  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x18001c023  xor     r9d, r9d
0x18001c026  mov     [rsp+38h+var_18], ebx
0x18001c02a  mov     rcx, [rcx+10h]
0x18001c02e  call    WPP_SF_qd
0x18001c033  lea     rcx, [rsp+38h+arg_0]; this
0x18001c038  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001c03d  mov     eax, ebx
0x18001c03f  add     rsp, 30h
0x18001c043  pop     rbx
0x18001c044  retn
```
