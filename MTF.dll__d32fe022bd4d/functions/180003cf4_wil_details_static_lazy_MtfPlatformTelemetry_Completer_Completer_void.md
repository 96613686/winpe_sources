# wil::details::static_lazy<MtfPlatformTelemetry>::Completer::~Completer(void)

- ea: `0x180003cf4`
- end: `0x180003dc7`
- name: `??1Completer@?$static_lazy@VMtfPlatformTelemetry@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800053cc`

## callees

- `0x180003cf4`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180003daa`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180003daa`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180003d82`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180003d82`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003d6a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003d6a`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<MtfPlatformTelemetry>::Completer::~Completer(_DWORD *a1)
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
0x180003cf4  push    rbx
0x180003cf6  push    rsi
0x180003cf7  push    rdi
0x180003cf8  push    r14
0x180003cfa  sub     rsp, 48h
0x180003cfe  mov     rax, cs:__security_cookie
0x180003d05  xor     rax, rsp
0x180003d08  mov     [rsp+68h+var_38], rax
0x180003d0d  cmp     dword ptr [rcx+8], 0
0x180003d11  mov     rdi, rcx
0x180003d14  jnz     loc_180003DA0
0x180003d1a  mov     rbx, [rcx]
0x180003d1d  mov     rsi, [rbx+20h]
0x180003d21  mov     [rbx+10h], rsi
0x180003d25  mov     byte ptr [rbx+18h], 1
0x180003d29  mov     rax, [rsi+8]
0x180003d2d  lea     r14, [rsi+20h]
0x180003d31  cmp     qword ptr [r14], 0
0x180003d35  movups  xmm0, xmmword ptr [rax-10h]
0x180003d39  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180003d3f  jz      short loc_180003D48
0x180003d41  mov     ecx, 5
0x180003d46  int     29h; Win8: RtlFailFast(ecx)
0x180003d48  mov     r9, r14; RegHandle
0x180003d4b  mov     qword ptr [rsi+28h], 0
0x180003d53  mov     r8, rsi; CallbackContext
0x180003d56  mov     qword ptr [rsi+30h], 0
0x180003d5e  lea     rdx, _tlgEnableCallback; EnableCallback
0x180003d65  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180003d6a  call    cs:__imp_EventRegister
0x180003d70  test    eax, eax
0x180003d72  jnz     short loc_180003D88
0x180003d74  mov     r8, [rsi+8]
0x180003d78  lea     edx, [rax+2]
0x180003d7b  mov     rcx, [r14]
0x180003d7e  movzx   r9d, word ptr [r8]
0x180003d82  call    cs:__imp_EventSetInformation
0x180003d88  mov     rax, [rbx+8]
0x180003d8c  lea     rcx, [rbx+8]
0x180003d90  mov     dword ptr [rbx+1Ch], 1
0x180003d97  mov     rax, [rax+8]
0x180003d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da0  mov     rcx, [rdi]; lpInitOnce
0x180003da3  mov     edx, [rdi+8]; dwFlags
0x180003da6  lea     r8, [rcx+8]; lpContext
0x180003daa  call    cs:__imp_InitOnceComplete
0x180003db0  mov     rcx, [rsp+68h+var_38]
0x180003db5  xor     rcx, rsp; StackCookie
0x180003db8  call    __security_check_cookie
0x180003dbd  add     rsp, 48h
0x180003dc1  pop     r14
0x180003dc3  pop     rdi
0x180003dc4  pop     rsi
0x180003dc5  pop     rbx
0x180003dc6  retn
```
