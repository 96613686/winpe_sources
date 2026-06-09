# wil::details::static_lazy<MidiBS2UMPTransformTelemetryProvider>::Completer::~Completer(void)

- ea: `0x180008c4c`
- end: `0x180008d1f`
- name: `??1Completer@?$static_lazy@VMidiBS2UMPTransformTelemetryProvider@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009528`

## callees

- `0x180001e60`
- `0x180008c4c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008cc2`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008cc2`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180008cda`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180008cda`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008d02`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008d02`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<MidiBS2UMPTransformTelemetryProvider>::Completer::~Completer(_DWORD *a1)
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
0x180008c4c  push    rbx
0x180008c4e  push    rsi
0x180008c4f  push    rdi
0x180008c50  push    r14
0x180008c52  sub     rsp, 48h
0x180008c56  mov     rax, cs:__security_cookie
0x180008c5d  xor     rax, rsp
0x180008c60  mov     [rsp+68h+var_38], rax
0x180008c65  cmp     dword ptr [rcx+8], 0
0x180008c69  mov     rdi, rcx
0x180008c6c  jnz     loc_180008CF8
0x180008c72  mov     rbx, [rcx]
0x180008c75  mov     rsi, [rbx+20h]
0x180008c79  mov     [rbx+10h], rsi
0x180008c7d  mov     byte ptr [rbx+18h], 1
0x180008c81  mov     rax, [rsi+8]
0x180008c85  lea     r14, [rsi+20h]
0x180008c89  cmp     qword ptr [r14], 0
0x180008c8d  movups  xmm0, xmmword ptr [rax-10h]
0x180008c91  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180008c97  jz      short loc_180008CA0
0x180008c99  mov     ecx, 5
0x180008c9e  int     29h; Win8: RtlFailFast(ecx)
0x180008ca0  mov     r9, r14; RegHandle
0x180008ca3  mov     qword ptr [rsi+28h], 0
0x180008cab  mov     r8, rsi; CallbackContext
0x180008cae  mov     qword ptr [rsi+30h], 0
0x180008cb6  lea     rdx, _tlgEnableCallback; EnableCallback
0x180008cbd  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180008cc2  call    cs:__imp_EventRegister
0x180008cc8  test    eax, eax
0x180008cca  jnz     short loc_180008CE0
0x180008ccc  mov     r8, [rsi+8]
0x180008cd0  lea     edx, [rax+2]
0x180008cd3  mov     rcx, [r14]
0x180008cd6  movzx   r9d, word ptr [r8]
0x180008cda  call    cs:__imp_EventSetInformation
0x180008ce0  mov     rax, [rbx+8]
0x180008ce4  lea     rcx, [rbx+8]
0x180008ce8  mov     dword ptr [rbx+1Ch], 1
0x180008cef  mov     rax, [rax+8]
0x180008cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cf8  mov     rcx, [rdi]; lpInitOnce
0x180008cfb  mov     edx, [rdi+8]; dwFlags
0x180008cfe  lea     r8, [rcx+8]; lpContext
0x180008d02  call    cs:__imp_InitOnceComplete
0x180008d08  mov     rcx, [rsp+68h+var_38]
0x180008d0d  xor     rcx, rsp; StackCookie
0x180008d10  call    __security_check_cookie
0x180008d15  add     rsp, 48h
0x180008d19  pop     r14
0x180008d1b  pop     rdi
0x180008d1c  pop     rsi
0x180008d1d  pop     rbx
0x180008d1e  retn
```
