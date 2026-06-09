# wil::details::static_lazy<CmAgentTraceProvider>::Completer::~Completer(void)

- ea: `0x180005b70`
- end: `0x180005c56`
- name: `??1Completer@?$static_lazy@VCmAgentTraceProvider@@@details@wil@@QEAA@XZ`
- size: `230`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006fcc`

## callees

- `0x180002140`
- `0x180005b70`
- `0x18003c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180005be6`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180005be6`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180005c04`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180005c04`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180005c32`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180005c32`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<CmAgentTraceProvider>::Completer::~Completer(_DWORD *a1)
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
0x180005b70  push    rbx
0x180005b72  push    rsi
0x180005b73  push    rdi
0x180005b74  push    r14
0x180005b76  sub     rsp, 48h
0x180005b7a  mov     rax, cs:__security_cookie
0x180005b81  xor     rax, rsp
0x180005b84  mov     [rsp+68h+var_38], rax
0x180005b89  cmp     dword ptr [rcx+8], 0
0x180005b8d  mov     rdi, rcx
0x180005b90  jnz     loc_180005C28
0x180005b96  mov     rbx, [rcx]
0x180005b99  mov     rsi, [rbx+20h]
0x180005b9d  mov     [rbx+10h], rsi
0x180005ba1  mov     byte ptr [rbx+18h], 1
0x180005ba5  mov     rax, [rsi+8]
0x180005ba9  lea     r14, [rsi+20h]
0x180005bad  cmp     qword ptr [r14], 0
0x180005bb1  movups  xmm0, xmmword ptr [rax-10h]
0x180005bb5  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180005bbb  jz      short loc_180005BC4
0x180005bbd  mov     ecx, 5
0x180005bc2  int     29h; Win8: RtlFailFast(ecx)
0x180005bc4  mov     r9, r14; RegHandle
0x180005bc7  mov     qword ptr [rsi+28h], 0
0x180005bcf  mov     r8, rsi; CallbackContext
0x180005bd2  mov     qword ptr [rsi+30h], 0
0x180005bda  lea     rdx, _tlgEnableCallback; EnableCallback
0x180005be1  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180005be6  call    cs:__imp_EventRegister
0x180005bed  nop     dword ptr [rax+rax+00h]
0x180005bf2  test    eax, eax
0x180005bf4  jnz     short loc_180005C10
0x180005bf6  mov     r8, [rsi+8]
0x180005bfa  lea     edx, [rax+2]
0x180005bfd  mov     rcx, [r14]
0x180005c00  movzx   r9d, word ptr [r8]
0x180005c04  call    cs:__imp_EventSetInformation
0x180005c0b  nop     dword ptr [rax+rax+00h]
0x180005c10  mov     rax, [rbx+8]
0x180005c14  lea     rcx, [rbx+8]
0x180005c18  mov     dword ptr [rbx+1Ch], 1
0x180005c1f  mov     rax, [rax+8]
0x180005c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c28  mov     rcx, [rdi]; lpInitOnce
0x180005c2b  mov     edx, [rdi+8]; dwFlags
0x180005c2e  lea     r8, [rcx+8]; lpContext
0x180005c32  call    cs:__imp_InitOnceComplete
0x180005c39  nop     dword ptr [rax+rax+00h]
0x180005c3e  mov     rcx, [rsp+68h+var_38]
0x180005c43  xor     rcx, rsp; StackCookie
0x180005c46  call    __security_check_cookie
0x180005c4b  add     rsp, 48h
0x180005c4f  pop     r14
0x180005c51  pop     rdi
0x180005c52  pop     rsi
0x180005c53  pop     rbx
0x180005c54  retn
```
