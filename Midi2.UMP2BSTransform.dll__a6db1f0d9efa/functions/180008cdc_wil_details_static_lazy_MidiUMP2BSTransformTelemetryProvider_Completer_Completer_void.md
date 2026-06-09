# wil::details::static_lazy<MidiUMP2BSTransformTelemetryProvider>::Completer::~Completer(void)

- ea: `0x180008cdc`
- end: `0x180008daf`
- name: `??1Completer@?$static_lazy@VMidiUMP2BSTransformTelemetryProvider@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800095b8`

## callees

- `0x180001ef0`
- `0x180008cdc`
- `0x18000f010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008d52`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008d52`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180008d6a`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180008d6a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008d92`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008d92`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<MidiUMP2BSTransformTelemetryProvider>::Completer::~Completer(_DWORD *a1)
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
0x180008cdc  push    rbx
0x180008cde  push    rsi
0x180008cdf  push    rdi
0x180008ce0  push    r14
0x180008ce2  sub     rsp, 48h
0x180008ce6  mov     rax, cs:__security_cookie
0x180008ced  xor     rax, rsp
0x180008cf0  mov     [rsp+68h+var_38], rax
0x180008cf5  cmp     dword ptr [rcx+8], 0
0x180008cf9  mov     rdi, rcx
0x180008cfc  jnz     loc_180008D88
0x180008d02  mov     rbx, [rcx]
0x180008d05  mov     rsi, [rbx+20h]
0x180008d09  mov     [rbx+10h], rsi
0x180008d0d  mov     byte ptr [rbx+18h], 1
0x180008d11  mov     rax, [rsi+8]
0x180008d15  lea     r14, [rsi+20h]
0x180008d19  cmp     qword ptr [r14], 0
0x180008d1d  movups  xmm0, xmmword ptr [rax-10h]
0x180008d21  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180008d27  jz      short loc_180008D30
0x180008d29  mov     ecx, 5
0x180008d2e  int     29h; Win8: RtlFailFast(ecx)
0x180008d30  mov     r9, r14; RegHandle
0x180008d33  mov     qword ptr [rsi+28h], 0
0x180008d3b  mov     r8, rsi; CallbackContext
0x180008d3e  mov     qword ptr [rsi+30h], 0
0x180008d46  lea     rdx, _tlgEnableCallback; EnableCallback
0x180008d4d  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180008d52  call    cs:__imp_EventRegister
0x180008d58  test    eax, eax
0x180008d5a  jnz     short loc_180008D70
0x180008d5c  mov     r8, [rsi+8]
0x180008d60  lea     edx, [rax+2]
0x180008d63  mov     rcx, [r14]
0x180008d66  movzx   r9d, word ptr [r8]
0x180008d6a  call    cs:__imp_EventSetInformation
0x180008d70  mov     rax, [rbx+8]
0x180008d74  lea     rcx, [rbx+8]
0x180008d78  mov     dword ptr [rbx+1Ch], 1
0x180008d7f  mov     rax, [rax+8]
0x180008d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d88  mov     rcx, [rdi]; lpInitOnce
0x180008d8b  mov     edx, [rdi+8]; dwFlags
0x180008d8e  lea     r8, [rcx+8]; lpContext
0x180008d92  call    cs:__imp_InitOnceComplete
0x180008d98  mov     rcx, [rsp+68h+var_38]
0x180008d9d  xor     rcx, rsp; StackCookie
0x180008da0  call    __security_check_cookie
0x180008da5  add     rsp, 48h
0x180008da9  pop     r14
0x180008dab  pop     rdi
0x180008dac  pop     rsi
0x180008dad  pop     rbx
0x180008dae  retn
```
