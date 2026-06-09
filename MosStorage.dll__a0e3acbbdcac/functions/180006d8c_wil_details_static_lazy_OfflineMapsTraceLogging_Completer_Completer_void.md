# wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(void)

- ea: `0x180006d8c`
- end: `0x180006e5f`
- name: `??1Completer@?$static_lazy@VOfflineMapsTraceLogging@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a2fc`

## callees

- `0x180001c80`
- `0x180006d8c`
- `0x180010010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180006e1a`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180006e1a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180006e02`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180006e02`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006e42`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006e42`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(_DWORD *a1)
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
0x180006d8c  push    rbx
0x180006d8e  push    rsi
0x180006d8f  push    rdi
0x180006d90  push    r14
0x180006d92  sub     rsp, 48h
0x180006d96  mov     rax, cs:__security_cookie
0x180006d9d  xor     rax, rsp
0x180006da0  mov     [rsp+68h+var_38], rax
0x180006da5  cmp     dword ptr [rcx+8], 0
0x180006da9  mov     rdi, rcx
0x180006dac  jnz     loc_180006E38
0x180006db2  mov     rbx, [rcx]
0x180006db5  mov     rsi, [rbx+20h]
0x180006db9  mov     [rbx+10h], rsi
0x180006dbd  mov     byte ptr [rbx+18h], 1
0x180006dc1  mov     rax, [rsi+8]
0x180006dc5  lea     r14, [rsi+20h]
0x180006dc9  cmp     qword ptr [r14], 0
0x180006dcd  movups  xmm0, xmmword ptr [rax-10h]
0x180006dd1  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180006dd7  jz      short loc_180006DE0
0x180006dd9  mov     ecx, 5
0x180006dde  int     29h; Win8: RtlFailFast(ecx)
0x180006de0  mov     r9, r14; RegHandle
0x180006de3  mov     qword ptr [rsi+28h], 0
0x180006deb  mov     r8, rsi; CallbackContext
0x180006dee  mov     qword ptr [rsi+30h], 0
0x180006df6  lea     rdx, _tlgEnableCallback; EnableCallback
0x180006dfd  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180006e02  call    cs:__imp_EventRegister
0x180006e08  test    eax, eax
0x180006e0a  jnz     short loc_180006E20
0x180006e0c  mov     r8, [rsi+8]
0x180006e10  lea     edx, [rax+2]
0x180006e13  mov     rcx, [r14]
0x180006e16  movzx   r9d, word ptr [r8]
0x180006e1a  call    cs:__imp_EventSetInformation
0x180006e20  mov     rax, [rbx+8]
0x180006e24  lea     rcx, [rbx+8]
0x180006e28  mov     dword ptr [rbx+1Ch], 1
0x180006e2f  mov     rax, [rax+8]
0x180006e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e38  mov     rcx, [rdi]; lpInitOnce
0x180006e3b  mov     edx, [rdi+8]; dwFlags
0x180006e3e  lea     r8, [rcx+8]; lpContext
0x180006e42  call    cs:__imp_InitOnceComplete
0x180006e48  mov     rcx, [rsp+68h+var_38]
0x180006e4d  xor     rcx, rsp; StackCookie
0x180006e50  call    __security_check_cookie
0x180006e55  add     rsp, 48h
0x180006e59  pop     r14
0x180006e5b  pop     rdi
0x180006e5c  pop     rsi
0x180006e5d  pop     rbx
0x180006e5e  retn
```
