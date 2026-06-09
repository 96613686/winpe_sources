# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TraceLogger::Provider(void)

- ea: `0x1800121f0`
- end: `0x180012354`
- name: `?Provider@TraceLogger@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SAPEBU_tlgProvider_t@@XZ`
- size: `356`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012470`
- `0x1800677b0`

## callees

- `0x1800121f0`
- `0x1801f7110`
- `0x1801f7660`
- `0x180242120`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x18001221f`
- `KERNEL32!InitOnceBeginInitialize` at `0x18001221f`
- `KERNEL32!InitOnceComplete` at `0x180012323`
- `KERNEL32!InitOnceComplete` at `0x180012323`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800122f3`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800122f3`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800122d8`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800122d8`

## pseudocode

```c
const struct _tlgProvider_t *winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TraceLogger::Provider(
        void)
{
  _QWORD *v0; // rbx
  ULONGLONG *v1; // r9
  LPVOID Context; // [rsp+20h] [rbp-38h] BYREF
  BOOL fPending; // [rsp+28h] [rbp-30h] BYREF
  GUID ProviderId; // [rsp+30h] [rbp-28h] BYREF

  Context = 0;
  if ( InitOnceBeginInitialize(
         &`winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TraceLogger::Instance'::`2'::wrapper,
         0,
         &fPending,
         &Context)
    && fPending )
  {
    Context = &qword_1803E2AB0;
    qword_1803E2AB8 = 0;
    byte_1803E2AC0 = 0;
    dword_1803E2AC4 = 0;
    qword_1803E2AB0 = (__int64)&winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TraceLogger::`vftable';
    CallbackContext = &`winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TraceLogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TraceLogger::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    v0 = CallbackContext;
    qword_1803E2AB8 = (__int64)CallbackContext;
    byte_1803E2AC0 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    v1 = (ULONGLONG *)((char *)CallbackContext + 32);
    *((_QWORD *)CallbackContext + 5) = 0;
    v0[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v0, v1) )
      EventSetInformation(v0[4], 2, v0[1], *(unsigned __int16 *)v0[1]);
    dword_1803E2AC4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1803E2AB0 + 8))(&qword_1803E2AB0);
    InitOnceComplete(
      &`winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TraceLogger::Instance'::`2'::wrapper,
      0,
      &qword_1803E2AB0);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x1800121f0  push    rsi
0x1800121f2  sub     rsp, 50h
0x1800121f6  mov     rax, cs:__security_cookie
0x1800121fd  xor     rax, rsp
0x180012200  mov     [rsp+58h+var_18], rax
0x180012205  xor     esi, esi
0x180012207  lea     r9, [rsp+58h+Context]; lpContext
0x18001220c  lea     r8, [rsp+58h+fPending]; fPending
0x180012211  mov     [rsp+58h+Context], rsi
0x180012216  xor     edx, edx; dwFlags
0x180012218  lea     rcx, ?wrapper@?1??Instance@TraceLogger@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@KAPEAV23456789@XZ@4V?$static_lazy@VTraceLogger@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@details@wil@@A; lpInitOnce
0x18001221f  call    cs:__imp_InitOnceBeginInitialize
0x180012225  test    eax, eax
0x180012227  jz      loc_180012338
0x18001222d  cmp     [rsp+58h+fPending], esi
0x180012231  jz      loc_180012338
0x180012237  mov     [rsp+58h+arg_0], rbx
0x18001223c  lea     rax, ??_7TraceLogger@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@6B@; const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TraceLogger::`vftable'
0x180012243  mov     [rsp+58h+arg_8], rbp
0x180012248  lea     rbp, qword_1803E2AB0
0x18001224f  mov     [rsp+58h+Context], rbp
0x180012254  mov     [rsp+58h+arg_10], rdi
0x180012259  mov     cs:qword_1803E2AB8, rsi
0x180012260  mov     cs:byte_1803E2AC0, sil
0x180012267  mov     cs:dword_1803E2AC4, esi
0x18001226d  mov     cs:qword_1803E2AB0, rax
0x180012274  lea     rax, ?__hInner@?1???0StaticHandle@TraceLogger@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TraceLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001227b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@TraceLogger@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@KAPEAV3456789winrt@@XZ@SA@XZ; void (__cdecl *)()
0x180012282  mov     cs:CallbackContext, rax
0x180012289  call    atexit
0x18001228e  mov     rbx, cs:CallbackContext
0x180012295  mov     cs:qword_1803E2AB8, rbx
0x18001229c  mov     cs:byte_1803E2AC0, 1
0x1800122a3  mov     rax, [rbx+8]
0x1800122a7  movups  xmm0, xmmword ptr [rax-10h]
0x1800122ab  movups  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x1800122b0  cmp     [rbx+20h], rsi
0x1800122b4  jz      short loc_1800122BD
0x1800122b6  mov     ecx, 5
0x1800122bb  int     29h; Win8: RtlFailFast(ecx)
0x1800122bd  lea     r9, [rbx+20h]; RegHandle
0x1800122c1  mov     [rbx+28h], rsi
0x1800122c5  mov     r8, rbx; CallbackContext
0x1800122c8  mov     [rbx+30h], rsi
0x1800122cc  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800122d3  lea     rcx, [rsp+58h+ProviderId]; ProviderId
0x1800122d8  call    cs:__imp_EventRegister
0x1800122de  test    eax, eax
0x1800122e0  jnz     short loc_1800122F9
0x1800122e2  mov     r8, [rbx+8]
0x1800122e6  mov     edx, 2
0x1800122eb  mov     rcx, [rbx+20h]
0x1800122ef  movzx   r9d, word ptr [r8]
0x1800122f3  call    cs:__imp_EventSetInformation
0x1800122f9  mov     rax, cs:qword_1803E2AB0
0x180012300  mov     rcx, rbp
0x180012303  mov     cs:dword_1803E2AC4, 1
0x18001230d  mov     rax, [rax+8]
0x180012311  call    cs:__guard_dispatch_icall_fptr
0x180012317  mov     r8, rbp; lpContext
0x18001231a  lea     rcx, ?wrapper@?1??Instance@TraceLogger@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@KAPEAV23456789@XZ@4V?$static_lazy@VTraceLogger@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@details@wil@@A; lpInitOnce
0x180012321  xor     edx, edx; dwFlags
0x180012323  call    cs:__imp_InitOnceComplete
0x180012329  mov     rdi, [rsp+58h+arg_10]
0x18001232e  mov     rbp, [rsp+58h+arg_8]
0x180012333  mov     rbx, [rsp+58h+arg_0]
0x180012338  mov     rax, [rsp+58h+Context]
0x18001233d  mov     rax, [rax+8]
0x180012341  mov     rcx, [rsp+58h+var_18]
0x180012346  xor     rcx, rsp; StackCookie
0x180012349  call    __security_check_cookie
0x18001234e  add     rsp, 50h
0x180012352  pop     rsi
0x180012353  retn
```
