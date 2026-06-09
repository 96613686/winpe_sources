# SceneAnalysisEffectDefnImpl::RuntimeClassInitialize(void)

- ea: `0x1800ac880`
- end: `0x1800ac992`
- name: `?RuntimeClassInitialize@SceneAnalysisEffectDefnImpl@@QEAAJXZ`
- size: `274`
- prototype: `__int64 __fastcall(SceneAnalysisEffectDefnImpl *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180008140`

## callees

- `0x18000b490`
- `0x18000c0f8`
- `0x18002a9bc`
- `0x18002ae0c`
- `0x18002afd0`
- `0x1800ac880`
- `0x18012f850`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac8ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac8ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800ac8c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800ac8c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ac8e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ac8e3`

## pseudocode

```c
__int64 __fastcall SceneAnalysisEffectDefnImpl::RuntimeClassInitialize(HSTRING *this)
{
  HRESULT String; // ebx
  __int64 *v3; // rcx
  CallStackTracing *v4; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v7; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v7,
    "SceneAnalysisEffectDefnImpl::RuntimeClassInitialize",
    38);
  WindowsDeleteString(this[8]);
  this[8] = 0;
  String = WindowsCreateString(L"Windows.Media.Core.SceneAnalysisEffect", 0x26u, this + 8);
  if ( String < 0 )
  {
    v3 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v4 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v4;
      if ( v4 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v4 + 8LL))(v4, 2032) )
      {
        v3 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v3 = &qword_18015FF10;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
      }
    }
    if ( *((_BYTE *)v3 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v3);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != String )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "SceneAnalysisEffectDefnImpl::RuntimeClassInitialize",
          39,
          String);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_45341311ee633afec8922ce86d82bcb5_Traceguids, this, String);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v7);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800ac880  mov     [rsp+arg_8], rbx
0x1800ac885  push    rdi
0x1800ac886  sub     rsp, 30h
0x1800ac88a  mov     rdi, rcx
0x1800ac88d  lea     rdx, aSceneanalysise_0; "SceneAnalysisEffectDefnImpl::RuntimeCla"...
0x1800ac894  lea     rcx, [rsp+38h+arg_0]; this
0x1800ac899  mov     r8d, 26h ; '&'; int
0x1800ac89f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ac8a4  lea     rbx, [rdi+40h]
0x1800ac8a8  mov     rcx, [rbx]; string
0x1800ac8ab  call    cs:__imp_WindowsDeleteString
0x1800ac8b1  mov     r8, rbx; string
0x1800ac8b4  mov     qword ptr [rbx], 0
0x1800ac8bb  mov     edx, 26h ; '&'; length
0x1800ac8c0  lea     rcx, ?RuntimeClass_Windows_Media_Core_SceneAnalysisEffect@@3QBGB; "Windows.Media.Core.SceneAnalysisEffect"
0x1800ac8c7  call    cs:__imp_WindowsCreateString
0x1800ac8cd  mov     ebx, eax
0x1800ac8cf  test    eax, eax
0x1800ac8d1  jns     loc_1800AC97B
0x1800ac8d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac8de  test    rcx, rcx
0x1800ac8e1  jnz     short loc_1800AC924
0x1800ac8e3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ac8e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac8f0  mov     rcx, rax
0x1800ac8f3  test    rax, rax
0x1800ac8f6  jz      short loc_1800AC916
0x1800ac8f8  mov     rax, [rax]
0x1800ac8fb  mov     edx, 7F0h
0x1800ac900  mov     rax, [rax+8]
0x1800ac904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac909  test    eax, eax
0x1800ac90b  jz      short loc_1800AC916
0x1800ac90d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac914  jmp     short loc_1800AC924
0x1800ac916  lea     rcx, qword_18015FF10; this
0x1800ac91d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac924  cmp     byte ptr [rcx+8], 0
0x1800ac928  jz      short loc_1800AC94F
0x1800ac92a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ac92f  cmp     [rax+7CCh], ebx
0x1800ac935  jz      short loc_1800AC94F
0x1800ac937  mov     r9d, ebx; int
0x1800ac93a  lea     rdx, aSceneanalysise_0; "SceneAnalysisEffectDefnImpl::RuntimeCla"...
0x1800ac941  mov     r8d, 27h ; '''; int
0x1800ac947  mov     rcx, rax; this
0x1800ac94a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ac94f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800ac954  cmp     al, 1
0x1800ac956  jb      short loc_1800AC97B
0x1800ac958  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac95f  lea     r8, WPP_45341311ee633afec8922ce86d82bcb5_Traceguids
0x1800ac966  mov     edx, 0Dh
0x1800ac96b  mov     [rsp+38h+var_18], ebx
0x1800ac96f  mov     r9, rdi
0x1800ac972  mov     rcx, [rcx+10h]
0x1800ac976  call    WPP_SF_qD
0x1800ac97b  lea     rcx, [rsp+38h+arg_0]; this
0x1800ac980  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ac985  mov     eax, ebx
0x1800ac987  mov     rbx, [rsp+38h+arg_8]
0x1800ac98c  add     rsp, 30h
0x1800ac990  pop     rdi
0x1800ac991  retn
```
