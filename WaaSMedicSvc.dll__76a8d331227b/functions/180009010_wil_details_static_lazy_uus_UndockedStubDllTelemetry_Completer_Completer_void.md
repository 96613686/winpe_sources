# wil::details::static_lazy<uus::UndockedStubDllTelemetry>::Completer::~Completer(void)

- ea: `0x180009010`
- end: `0x1800090e3`
- name: `??1Completer@?$static_lazy@VUndockedStubDllTelemetry@uus@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a570`

## callees

- `0x180002200`
- `0x180009010`
- `0x18000d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000909e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000909e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180009086`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180009086`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800090c6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800090c6`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<uus::UndockedStubDllTelemetry>::Completer::~Completer(_DWORD *a1)
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
0x180009010  push    rbx
0x180009012  push    rsi
0x180009013  push    rdi
0x180009014  push    r14
0x180009016  sub     rsp, 48h
0x18000901a  mov     rax, cs:__security_cookie
0x180009021  xor     rax, rsp
0x180009024  mov     [rsp+68h+var_38], rax
0x180009029  cmp     dword ptr [rcx+8], 0
0x18000902d  mov     rdi, rcx
0x180009030  jnz     loc_1800090BC
0x180009036  mov     rbx, [rcx]
0x180009039  mov     rsi, [rbx+20h]
0x18000903d  mov     [rbx+10h], rsi
0x180009041  mov     byte ptr [rbx+18h], 1
0x180009045  mov     rax, [rsi+8]
0x180009049  lea     r14, [rsi+20h]
0x18000904d  cmp     qword ptr [r14], 0
0x180009051  movups  xmm0, xmmword ptr [rax-10h]
0x180009055  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x18000905b  jz      short loc_180009064
0x18000905d  mov     ecx, 5
0x180009062  int     29h; Win8: RtlFailFast(ecx)
0x180009064  mov     r9, r14; RegHandle
0x180009067  mov     qword ptr [rsi+28h], 0
0x18000906f  mov     r8, rsi; CallbackContext
0x180009072  mov     qword ptr [rsi+30h], 0
0x18000907a  lea     rdx, _tlgEnableCallback; EnableCallback
0x180009081  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180009086  call    cs:__imp_EventRegister
0x18000908c  test    eax, eax
0x18000908e  jnz     short loc_1800090A4
0x180009090  mov     r8, [rsi+8]
0x180009094  lea     edx, [rax+2]
0x180009097  mov     rcx, [r14]
0x18000909a  movzx   r9d, word ptr [r8]
0x18000909e  call    cs:__imp_EventSetInformation
0x1800090a4  mov     rax, [rbx+8]
0x1800090a8  lea     rcx, [rbx+8]
0x1800090ac  mov     dword ptr [rbx+1Ch], 1
0x1800090b3  mov     rax, [rax+8]
0x1800090b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090bc  mov     rcx, [rdi]; lpInitOnce
0x1800090bf  mov     edx, [rdi+8]; dwFlags
0x1800090c2  lea     r8, [rcx+8]; lpContext
0x1800090c6  call    cs:__imp_InitOnceComplete
0x1800090cc  mov     rcx, [rsp+68h+var_38]
0x1800090d1  xor     rcx, rsp; StackCookie
0x1800090d4  call    __security_check_cookie
0x1800090d9  add     rsp, 48h
0x1800090dd  pop     r14
0x1800090df  pop     rdi
0x1800090e0  pop     rsi
0x1800090e1  pop     rbx
0x1800090e2  retn
```
