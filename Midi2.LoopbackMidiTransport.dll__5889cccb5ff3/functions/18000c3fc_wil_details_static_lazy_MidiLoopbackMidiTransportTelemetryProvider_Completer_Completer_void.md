# wil::details::static_lazy<MidiLoopbackMidiTransportTelemetryProvider>::Completer::~Completer(void)

- ea: `0x18000c3fc`
- end: `0x18000c4cf`
- name: `??1Completer@?$static_lazy@VMidiLoopbackMidiTransportTelemetryProvider@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ccd8`

## callees

- `0x180004180`
- `0x18000c3fc`
- `0x180032010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000c48a`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000c48a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000c472`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000c472`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c4b2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c4b2`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<MidiLoopbackMidiTransportTelemetryProvider>::Completer::~Completer(
        _DWORD *a1)
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
0x18000c3fc  push    rbx
0x18000c3fe  push    rsi
0x18000c3ff  push    rdi
0x18000c400  push    r14
0x18000c402  sub     rsp, 48h
0x18000c406  mov     rax, cs:__security_cookie
0x18000c40d  xor     rax, rsp
0x18000c410  mov     [rsp+68h+var_38], rax
0x18000c415  cmp     dword ptr [rcx+8], 0
0x18000c419  mov     rdi, rcx
0x18000c41c  jnz     loc_18000C4A8
0x18000c422  mov     rbx, [rcx]
0x18000c425  mov     rsi, [rbx+20h]
0x18000c429  mov     [rbx+10h], rsi
0x18000c42d  mov     byte ptr [rbx+18h], 1
0x18000c431  mov     rax, [rsi+8]
0x18000c435  lea     r14, [rsi+20h]
0x18000c439  cmp     qword ptr [r14], 0
0x18000c43d  movups  xmm0, xmmword ptr [rax-10h]
0x18000c441  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x18000c447  jz      short loc_18000C450
0x18000c449  mov     ecx, 5
0x18000c44e  int     29h; Win8: RtlFailFast(ecx)
0x18000c450  mov     r9, r14; RegHandle
0x18000c453  mov     qword ptr [rsi+28h], 0
0x18000c45b  mov     r8, rsi; CallbackContext
0x18000c45e  mov     qword ptr [rsi+30h], 0
0x18000c466  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000c46d  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x18000c472  call    cs:__imp_EventRegister
0x18000c478  test    eax, eax
0x18000c47a  jnz     short loc_18000C490
0x18000c47c  mov     r8, [rsi+8]
0x18000c480  lea     edx, [rax+2]
0x18000c483  mov     rcx, [r14]
0x18000c486  movzx   r9d, word ptr [r8]
0x18000c48a  call    cs:__imp_EventSetInformation
0x18000c490  mov     rax, [rbx+8]
0x18000c494  lea     rcx, [rbx+8]
0x18000c498  mov     dword ptr [rbx+1Ch], 1
0x18000c49f  mov     rax, [rax+8]
0x18000c4a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4a8  mov     rcx, [rdi]; lpInitOnce
0x18000c4ab  mov     edx, [rdi+8]; dwFlags
0x18000c4ae  lea     r8, [rcx+8]; lpContext
0x18000c4b2  call    cs:__imp_InitOnceComplete
0x18000c4b8  mov     rcx, [rsp+68h+var_38]
0x18000c4bd  xor     rcx, rsp; StackCookie
0x18000c4c0  call    __security_check_cookie
0x18000c4c5  add     rsp, 48h
0x18000c4c9  pop     r14
0x18000c4cb  pop     rdi
0x18000c4cc  pop     rsi
0x18000c4cd  pop     rbx
0x18000c4ce  retn
```
