# wil::details::static_lazy<uus::UndockedStubTelemetry>::Completer::~Completer(void)

- ea: `0x1400088ac`
- end: `0x14000897f`
- name: `??1Completer@?$static_lazy@VUndockedStubTelemetry@uus@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400098bc`

## callees

- `0x140002120`
- `0x1400088ac`
- `0x14000c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x14000893a`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x14000893a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140008922`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140008922`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140008962`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140008962`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<uus::UndockedStubTelemetry>::Completer::~Completer(_DWORD *a1)
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
0x1400088ac  push    rbx
0x1400088ae  push    rsi
0x1400088af  push    rdi
0x1400088b0  push    r14
0x1400088b2  sub     rsp, 48h
0x1400088b6  mov     rax, cs:__security_cookie
0x1400088bd  xor     rax, rsp
0x1400088c0  mov     [rsp+68h+var_38], rax
0x1400088c5  cmp     dword ptr [rcx+8], 0
0x1400088c9  mov     rdi, rcx
0x1400088cc  jnz     loc_140008958
0x1400088d2  mov     rbx, [rcx]
0x1400088d5  mov     rsi, [rbx+20h]
0x1400088d9  mov     [rbx+10h], rsi
0x1400088dd  mov     byte ptr [rbx+18h], 1
0x1400088e1  mov     rax, [rsi+8]
0x1400088e5  lea     r14, [rsi+20h]
0x1400088e9  cmp     qword ptr [r14], 0
0x1400088ed  movups  xmm0, xmmword ptr [rax-10h]
0x1400088f1  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x1400088f7  jz      short loc_140008900
0x1400088f9  mov     ecx, 5
0x1400088fe  int     29h; Win8: RtlFailFast(ecx)
0x140008900  mov     r9, r14; RegHandle
0x140008903  mov     qword ptr [rsi+28h], 0
0x14000890b  mov     r8, rsi; CallbackContext
0x14000890e  mov     qword ptr [rsi+30h], 0
0x140008916  lea     rdx, _tlgEnableCallback; EnableCallback
0x14000891d  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x140008922  call    cs:__imp_EventRegister
0x140008928  test    eax, eax
0x14000892a  jnz     short loc_140008940
0x14000892c  mov     r8, [rsi+8]
0x140008930  lea     edx, [rax+2]
0x140008933  mov     rcx, [r14]
0x140008936  movzx   r9d, word ptr [r8]
0x14000893a  call    cs:__imp_EventSetInformation
0x140008940  mov     rax, [rbx+8]
0x140008944  lea     rcx, [rbx+8]
0x140008948  mov     dword ptr [rbx+1Ch], 1
0x14000894f  mov     rax, [rax+8]
0x140008953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008958  mov     rcx, [rdi]; lpInitOnce
0x14000895b  mov     edx, [rdi+8]; dwFlags
0x14000895e  lea     r8, [rcx+8]; lpContext
0x140008962  call    cs:__imp_InitOnceComplete
0x140008968  mov     rcx, [rsp+68h+var_38]
0x14000896d  xor     rcx, rsp; StackCookie
0x140008970  call    __security_check_cookie
0x140008975  add     rsp, 48h
0x140008979  pop     r14
0x14000897b  pop     rdi
0x14000897c  pop     rsi
0x14000897d  pop     rbx
0x14000897e  retn
```
