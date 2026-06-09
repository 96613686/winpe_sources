# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x180009858`
- end: `0x18000992b`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c2ec`

## callees

- `0x1800028f0`
- `0x180009858`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000990e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000990e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800098ce`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800098ce`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800098e6`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800098e6`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(_DWORD *a1)
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
0x180009858  push    rbx
0x18000985a  push    rsi
0x18000985b  push    rdi
0x18000985c  push    r14
0x18000985e  sub     rsp, 48h
0x180009862  mov     rax, cs:__security_cookie
0x180009869  xor     rax, rsp
0x18000986c  mov     [rsp+68h+var_38], rax
0x180009871  cmp     dword ptr [rcx+8], 0
0x180009875  mov     rdi, rcx
0x180009878  jnz     loc_180009904
0x18000987e  mov     rbx, [rcx]
0x180009881  mov     rsi, [rbx+20h]
0x180009885  mov     [rbx+10h], rsi
0x180009889  mov     byte ptr [rbx+18h], 1
0x18000988d  mov     rax, [rsi+8]
0x180009891  lea     r14, [rsi+20h]
0x180009895  cmp     qword ptr [r14], 0
0x180009899  movups  xmm0, xmmword ptr [rax-10h]
0x18000989d  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x1800098a3  jz      short loc_1800098AC
0x1800098a5  mov     ecx, 5
0x1800098aa  int     29h; Win8: RtlFailFast(ecx)
0x1800098ac  mov     r9, r14; RegHandle
0x1800098af  mov     qword ptr [rsi+28h], 0
0x1800098b7  mov     r8, rsi; CallbackContext
0x1800098ba  mov     qword ptr [rsi+30h], 0
0x1800098c2  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800098c9  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x1800098ce  call    cs:__imp_EventRegister
0x1800098d4  test    eax, eax
0x1800098d6  jnz     short loc_1800098EC
0x1800098d8  mov     r8, [rsi+8]
0x1800098dc  lea     edx, [rax+2]
0x1800098df  mov     rcx, [r14]
0x1800098e2  movzx   r9d, word ptr [r8]
0x1800098e6  call    cs:__imp_EventSetInformation
0x1800098ec  mov     rax, [rbx+8]
0x1800098f0  lea     rcx, [rbx+8]
0x1800098f4  mov     dword ptr [rbx+1Ch], 1
0x1800098fb  mov     rax, [rax+8]
0x1800098ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009904  mov     rcx, [rdi]; lpInitOnce
0x180009907  mov     edx, [rdi+8]; dwFlags
0x18000990a  lea     r8, [rcx+8]; lpContext
0x18000990e  call    cs:__imp_InitOnceComplete
0x180009914  mov     rcx, [rsp+68h+var_38]
0x180009919  xor     rcx, rsp; StackCookie
0x18000991c  call    __security_check_cookie
0x180009921  add     rsp, 48h
0x180009925  pop     r14
0x180009927  pop     rdi
0x180009928  pop     rsi
0x180009929  pop     rbx
0x18000992a  retn
```
