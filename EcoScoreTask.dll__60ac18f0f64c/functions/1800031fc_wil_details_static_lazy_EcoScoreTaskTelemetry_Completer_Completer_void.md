# wil::details::static_lazy<EcoScoreTaskTelemetry>::Completer::~Completer(void)

- ea: `0x1800031fc`
- end: `0x1800032cf`
- name: `??1Completer@?$static_lazy@VEcoScoreTaskTelemetry@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005760`

## callees

- `0x1800031fc`
- `0x180007c90`
- `0x180009010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003272`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003272`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000328a`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000328a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800032b2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800032b2`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<EcoScoreTaskTelemetry>::Completer::~Completer(_DWORD *a1)
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
0x1800031fc  push    rbx
0x1800031fe  push    rsi
0x1800031ff  push    rdi
0x180003200  push    r14
0x180003202  sub     rsp, 48h
0x180003206  mov     rax, cs:__security_cookie
0x18000320d  xor     rax, rsp
0x180003210  mov     [rsp+68h+var_38], rax
0x180003215  cmp     dword ptr [rcx+8], 0
0x180003219  mov     rdi, rcx
0x18000321c  jnz     loc_1800032A8
0x180003222  mov     rbx, [rcx]
0x180003225  mov     rsi, [rbx+20h]
0x180003229  mov     [rbx+10h], rsi
0x18000322d  mov     byte ptr [rbx+18h], 1
0x180003231  mov     rax, [rsi+8]
0x180003235  lea     r14, [rsi+20h]
0x180003239  cmp     qword ptr [r14], 0
0x18000323d  movups  xmm0, xmmword ptr [rax-10h]
0x180003241  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180003247  jz      short loc_180003250
0x180003249  mov     ecx, 5
0x18000324e  int     29h; Win8: RtlFailFast(ecx)
0x180003250  mov     r9, r14; RegHandle
0x180003253  mov     qword ptr [rsi+28h], 0
0x18000325b  mov     r8, rsi; CallbackContext
0x18000325e  mov     qword ptr [rsi+30h], 0
0x180003266  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000326d  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180003272  call    cs:__imp_EventRegister
0x180003278  test    eax, eax
0x18000327a  jnz     short loc_180003290
0x18000327c  mov     r8, [rsi+8]
0x180003280  lea     edx, [rax+2]
0x180003283  mov     rcx, [r14]
0x180003286  movzx   r9d, word ptr [r8]
0x18000328a  call    cs:__imp_EventSetInformation
0x180003290  mov     rax, [rbx+8]
0x180003294  lea     rcx, [rbx+8]
0x180003298  mov     dword ptr [rbx+1Ch], 1
0x18000329f  mov     rax, [rax+8]
0x1800032a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032a8  mov     rcx, [rdi]; lpInitOnce
0x1800032ab  mov     edx, [rdi+8]; dwFlags
0x1800032ae  lea     r8, [rcx+8]; lpContext
0x1800032b2  call    cs:__imp_InitOnceComplete
0x1800032b8  mov     rcx, [rsp+68h+var_38]
0x1800032bd  xor     rcx, rsp; StackCookie
0x1800032c0  call    __security_check_cookie
0x1800032c5  add     rsp, 48h
0x1800032c9  pop     r14
0x1800032cb  pop     rdi
0x1800032cc  pop     rsi
0x1800032cd  pop     rbx
0x1800032ce  retn
```
