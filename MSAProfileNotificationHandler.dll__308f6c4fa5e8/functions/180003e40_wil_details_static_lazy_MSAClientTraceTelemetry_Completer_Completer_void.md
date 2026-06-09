# wil::details::static_lazy<MSAClientTraceTelemetry>::Completer::~Completer(void)

- ea: `0x180003e40`
- end: `0x180003f13`
- name: `??1Completer@?$static_lazy@VMSAClientTraceTelemetry@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005820`

## callees

- `0x180001cb0`
- `0x180003e40`
- `0x180009010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003eb6`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003eb6`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180003ece`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180003ece`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180003ef6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180003ef6`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<MSAClientTraceTelemetry>::Completer::~Completer(_DWORD *a1)
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
0x180003e40  push    rbx
0x180003e42  push    rsi
0x180003e43  push    rdi
0x180003e44  push    r14
0x180003e46  sub     rsp, 48h
0x180003e4a  mov     rax, cs:__security_cookie
0x180003e51  xor     rax, rsp
0x180003e54  mov     [rsp+68h+var_38], rax
0x180003e59  cmp     dword ptr [rcx+8], 0
0x180003e5d  mov     rdi, rcx
0x180003e60  jnz     loc_180003EEC
0x180003e66  mov     rbx, [rcx]
0x180003e69  mov     rsi, [rbx+20h]
0x180003e6d  mov     [rbx+10h], rsi
0x180003e71  mov     byte ptr [rbx+18h], 1
0x180003e75  mov     rax, [rsi+8]
0x180003e79  lea     r14, [rsi+20h]
0x180003e7d  cmp     qword ptr [r14], 0
0x180003e81  movups  xmm0, xmmword ptr [rax-10h]
0x180003e85  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180003e8b  jz      short loc_180003E94
0x180003e8d  mov     ecx, 5
0x180003e92  int     29h; Win8: RtlFailFast(ecx)
0x180003e94  mov     r9, r14; RegHandle
0x180003e97  mov     qword ptr [rsi+28h], 0
0x180003e9f  mov     r8, rsi; CallbackContext
0x180003ea2  mov     qword ptr [rsi+30h], 0
0x180003eaa  lea     rdx, _tlgEnableCallback; EnableCallback
0x180003eb1  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180003eb6  call    cs:__imp_EventRegister
0x180003ebc  test    eax, eax
0x180003ebe  jnz     short loc_180003ED4
0x180003ec0  mov     r8, [rsi+8]
0x180003ec4  lea     edx, [rax+2]
0x180003ec7  mov     rcx, [r14]
0x180003eca  movzx   r9d, word ptr [r8]
0x180003ece  call    cs:__imp_EventSetInformation
0x180003ed4  mov     rax, [rbx+8]
0x180003ed8  lea     rcx, [rbx+8]
0x180003edc  mov     dword ptr [rbx+1Ch], 1
0x180003ee3  mov     rax, [rax+8]
0x180003ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eec  mov     rcx, [rdi]; lpInitOnce
0x180003eef  mov     edx, [rdi+8]; dwFlags
0x180003ef2  lea     r8, [rcx+8]; lpContext
0x180003ef6  call    cs:__imp_InitOnceComplete
0x180003efc  mov     rcx, [rsp+68h+var_38]
0x180003f01  xor     rcx, rsp; StackCookie
0x180003f04  call    __security_check_cookie
0x180003f09  add     rsp, 48h
0x180003f0d  pop     r14
0x180003f0f  pop     rdi
0x180003f10  pop     rsi
0x180003f11  pop     rbx
0x180003f12  retn
```
