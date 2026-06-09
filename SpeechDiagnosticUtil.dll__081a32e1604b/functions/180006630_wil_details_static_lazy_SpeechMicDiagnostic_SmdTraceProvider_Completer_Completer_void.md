# wil::details::static_lazy<SpeechMicDiagnostic::SmdTraceProvider>::Completer::~Completer(void)

- ea: `0x180006630`
- end: `0x180006716`
- name: `??1Completer@?$static_lazy@VSmdTraceProvider@SpeechMicDiagnostic@@@details@wil@@QEAA@XZ`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800068cc`

## callees

- `0x180002910`
- `0x180006630`
- `0x180011010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x1800066f2`
- `KERNEL32!InitOnceComplete` at `0x1800066f2`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800066a6`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800066a6`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800066c4`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800066c4`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<SpeechMicDiagnostic::SmdTraceProvider>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  ULONGLONG *v3; // rsi
  bool v4; // zf
  __int64 v5; // rax
  GUID ProviderId; // [rsp+20h] [rbp-48h] BYREF

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    v3 = *(ULONGLONG **)(*(_QWORD *)a1 + 32LL);
    *(_QWORD *)(v2 + 16) = v3;
    *(_BYTE *)(v2 + 24) = 1;
    v4 = v3[4] == 0;
    ProviderId = *(GUID *)(v3[1] - 16);
    if ( !v4 )
      __fastfail(5u);
    v3[5] = 0;
    v3[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v3, v3 + 4) )
      EventSetInformation(
        v3[4],
        2,
        v3[1],
        *(unsigned __int16 *)v3[1],
        *(_QWORD *)&ProviderId.Data1,
        *(_QWORD *)ProviderId.Data4);
    v5 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v5 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x180006630  push    rbx
0x180006632  push    rsi
0x180006633  push    rdi
0x180006634  push    r14
0x180006636  sub     rsp, 48h
0x18000663a  mov     rax, cs:__security_cookie
0x180006641  xor     rax, rsp
0x180006644  mov     [rsp+68h+var_38], rax
0x180006649  cmp     dword ptr [rcx+8], 0
0x18000664d  mov     rdi, rcx
0x180006650  jnz     loc_1800066E8
0x180006656  mov     rbx, [rcx]
0x180006659  mov     rsi, [rbx+20h]
0x18000665d  mov     [rbx+10h], rsi
0x180006661  mov     byte ptr [rbx+18h], 1
0x180006665  mov     rax, [rsi+8]
0x180006669  lea     r14, [rsi+20h]
0x18000666d  cmp     qword ptr [r14], 0
0x180006671  movups  xmm0, xmmword ptr [rax-10h]
0x180006675  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x18000667b  jz      short loc_180006684
0x18000667d  mov     ecx, 5
0x180006682  int     29h; Win8: RtlFailFast(ecx)
0x180006684  mov     r9, r14; RegHandle
0x180006687  mov     qword ptr [rsi+28h], 0
0x18000668f  mov     r8, rsi; CallbackContext
0x180006692  mov     qword ptr [rsi+30h], 0
0x18000669a  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800066a1  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x1800066a6  call    cs:__imp_EventRegister
0x1800066ad  nop     dword ptr [rax+rax+00h]
0x1800066b2  test    eax, eax
0x1800066b4  jnz     short loc_1800066D0
0x1800066b6  mov     r8, [rsi+8]
0x1800066ba  lea     edx, [rax+2]
0x1800066bd  mov     rcx, [r14]
0x1800066c0  movzx   r9d, word ptr [r8]
0x1800066c4  call    cs:__imp_EventSetInformation
0x1800066cb  nop     dword ptr [rax+rax+00h]
0x1800066d0  mov     rax, [rbx+8]
0x1800066d4  lea     rcx, [rbx+8]
0x1800066d8  mov     dword ptr [rbx+1Ch], 1
0x1800066df  mov     rax, [rax+8]
0x1800066e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066e8  mov     rcx, [rdi]; lpInitOnce
0x1800066eb  mov     edx, [rdi+8]; dwFlags
0x1800066ee  lea     r8, [rcx+8]; lpContext
0x1800066f2  call    cs:__imp_InitOnceComplete
0x1800066f9  nop     dword ptr [rax+rax+00h]
0x1800066fe  mov     rcx, [rsp+68h+var_38]
0x180006703  xor     rcx, rsp; StackCookie
0x180006706  call    __security_check_cookie
0x18000670b  add     rsp, 48h
0x18000670f  pop     r14
0x180006711  pop     rdi
0x180006712  pop     rsi
0x180006713  pop     rbx
0x180006714  retn
```
