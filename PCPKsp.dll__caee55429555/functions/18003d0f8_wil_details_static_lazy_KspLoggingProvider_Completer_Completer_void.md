# wil::details::static_lazy<KspLoggingProvider>::Completer::~Completer(void)

- ea: `0x18003d0f8`
- end: `0x18003d1e7`
- name: `??1Completer@?$static_lazy@VKspLoggingProvider@@@details@wil@@QEAA@XZ`
- size: `239`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800113f0`
- `0x18003cf80`
- `0x18003d040`
- `0x18005c6f0`

## callees

- `0x18003d0f8`
- `0x1800764d0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18003d189`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18003d189`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18003d16b`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18003d16b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003d1b7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003d1b7`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<KspLoggingProvider>::Completer::~Completer(_DWORD *a1)
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
0x18003d0f8  push    rbx
0x18003d0fa  push    rsi
0x18003d0fb  push    rdi
0x18003d0fc  push    r14
0x18003d0fe  sub     rsp, 48h
0x18003d102  mov     rax, cs:__security_cookie
0x18003d109  xor     rax, rsp
0x18003d10c  mov     [rsp+68h+var_38], rax
0x18003d111  cmp     dword ptr [rcx+8], 0
0x18003d115  mov     rdi, rcx
0x18003d118  jnz     loc_18003D1AD
0x18003d11e  mov     rbx, [rcx]
0x18003d121  mov     rsi, [rbx+20h]
0x18003d125  mov     [rbx+10h], rsi
0x18003d129  mov     byte ptr [rbx+18h], 1
0x18003d12d  mov     rax, [rsi+8]
0x18003d131  lea     r14, [rsi+20h]
0x18003d135  cmp     qword ptr [r14], 0
0x18003d139  movups  xmm0, xmmword ptr [rax-10h]
0x18003d13d  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x18003d143  jnz     loc_18003D1DB
0x18003d149  mov     r9, r14; RegHandle
0x18003d14c  mov     qword ptr [rsi+28h], 0
0x18003d154  mov     r8, rsi; CallbackContext
0x18003d157  mov     qword ptr [rsi+30h], 0
0x18003d15f  lea     rdx, _tlgEnableCallback; EnableCallback
0x18003d166  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x18003d16b  call    cs:__imp_EventRegister
0x18003d172  nop     dword ptr [rax+rax+00h]
0x18003d177  test    eax, eax
0x18003d179  jnz     short loc_18003D195
0x18003d17b  mov     r8, [rsi+8]
0x18003d17f  lea     edx, [rax+2]
0x18003d182  mov     rcx, [r14]
0x18003d185  movzx   r9d, word ptr [r8]
0x18003d189  call    cs:__imp_EventSetInformation
0x18003d190  nop     dword ptr [rax+rax+00h]
0x18003d195  mov     rax, [rbx+8]
0x18003d199  lea     rcx, [rbx+8]
0x18003d19d  mov     dword ptr [rbx+1Ch], 1
0x18003d1a4  mov     rax, [rax+8]
0x18003d1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1ad  mov     rcx, [rdi]; lpInitOnce
0x18003d1b0  mov     edx, [rdi+8]; dwFlags
0x18003d1b3  lea     r8, [rcx+8]; lpContext
0x18003d1b7  call    cs:__imp_InitOnceComplete
0x18003d1be  nop     dword ptr [rax+rax+00h]
0x18003d1c3  mov     rcx, [rsp+68h+var_38]
0x18003d1c8  xor     rcx, rsp; StackCookie
0x18003d1cb  call    __security_check_cookie
0x18003d1d0  add     rsp, 48h
0x18003d1d4  pop     r14
0x18003d1d6  pop     rdi
0x18003d1d7  pop     rsi
0x18003d1d8  pop     rbx
0x18003d1d9  retn
0x18003d1db  mov     ecx, 5
0x18003d1e0  int     29h; Win8: RtlFailFast(ecx)
0x18003d1e2  jmp     loc_18003D149
```
