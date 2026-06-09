# wil::details::static_lazy<MidiDiagnosticsTransportTelemetryProvider>::Completer::~Completer(void)

- ea: `0x18000a4fc`
- end: `0x18000a5cf`
- name: `??1Completer@?$static_lazy@VMidiDiagnosticsTransportTelemetryProvider@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000add8`

## callees

- `0x1800033d0`
- `0x18000a4fc`
- `0x180013010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000a58a`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000a58a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a572`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a572`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a5b2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a5b2`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<MidiDiagnosticsTransportTelemetryProvider>::Completer::~Completer(_DWORD *a1)
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
0x18000a4fc  push    rbx
0x18000a4fe  push    rsi
0x18000a4ff  push    rdi
0x18000a500  push    r14
0x18000a502  sub     rsp, 48h
0x18000a506  mov     rax, cs:__security_cookie
0x18000a50d  xor     rax, rsp
0x18000a510  mov     [rsp+68h+var_38], rax
0x18000a515  cmp     dword ptr [rcx+8], 0
0x18000a519  mov     rdi, rcx
0x18000a51c  jnz     loc_18000A5A8
0x18000a522  mov     rbx, [rcx]
0x18000a525  mov     rsi, [rbx+20h]
0x18000a529  mov     [rbx+10h], rsi
0x18000a52d  mov     byte ptr [rbx+18h], 1
0x18000a531  mov     rax, [rsi+8]
0x18000a535  lea     r14, [rsi+20h]
0x18000a539  cmp     qword ptr [r14], 0
0x18000a53d  movups  xmm0, xmmword ptr [rax-10h]
0x18000a541  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x18000a547  jz      short loc_18000A550
0x18000a549  mov     ecx, 5
0x18000a54e  int     29h; Win8: RtlFailFast(ecx)
0x18000a550  mov     r9, r14; RegHandle
0x18000a553  mov     qword ptr [rsi+28h], 0
0x18000a55b  mov     r8, rsi; CallbackContext
0x18000a55e  mov     qword ptr [rsi+30h], 0
0x18000a566  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000a56d  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x18000a572  call    cs:__imp_EventRegister
0x18000a578  test    eax, eax
0x18000a57a  jnz     short loc_18000A590
0x18000a57c  mov     r8, [rsi+8]
0x18000a580  lea     edx, [rax+2]
0x18000a583  mov     rcx, [r14]
0x18000a586  movzx   r9d, word ptr [r8]
0x18000a58a  call    cs:__imp_EventSetInformation
0x18000a590  mov     rax, [rbx+8]
0x18000a594  lea     rcx, [rbx+8]
0x18000a598  mov     dword ptr [rbx+1Ch], 1
0x18000a59f  mov     rax, [rax+8]
0x18000a5a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5a8  mov     rcx, [rdi]; lpInitOnce
0x18000a5ab  mov     edx, [rdi+8]; dwFlags
0x18000a5ae  lea     r8, [rcx+8]; lpContext
0x18000a5b2  call    cs:__imp_InitOnceComplete
0x18000a5b8  mov     rcx, [rsp+68h+var_38]
0x18000a5bd  xor     rcx, rsp; StackCookie
0x18000a5c0  call    __security_check_cookie
0x18000a5c5  add     rsp, 48h
0x18000a5c9  pop     r14
0x18000a5cb  pop     rdi
0x18000a5cc  pop     rsi
0x18000a5cd  pop     rbx
0x18000a5ce  retn
```
