# wil::details::static_lazy<MidiSchedulerTransformTelemetryProvider>::Completer::~Completer(void)

- ea: `0x180008dfc`
- end: `0x180008ecf`
- name: `??1Completer@?$static_lazy@VMidiSchedulerTransformTelemetryProvider@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800096d8`

## callees

- `0x180002000`
- `0x180008dfc`
- `0x18000e010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180008e8a`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180008e8a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008e72`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008e72`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008eb2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008eb2`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<MidiSchedulerTransformTelemetryProvider>::Completer::~Completer(_DWORD *a1)
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
0x180008dfc  push    rbx
0x180008dfe  push    rsi
0x180008dff  push    rdi
0x180008e00  push    r14
0x180008e02  sub     rsp, 48h
0x180008e06  mov     rax, cs:__security_cookie
0x180008e0d  xor     rax, rsp
0x180008e10  mov     [rsp+68h+var_38], rax
0x180008e15  cmp     dword ptr [rcx+8], 0
0x180008e19  mov     rdi, rcx
0x180008e1c  jnz     loc_180008EA8
0x180008e22  mov     rbx, [rcx]
0x180008e25  mov     rsi, [rbx+20h]
0x180008e29  mov     [rbx+10h], rsi
0x180008e2d  mov     byte ptr [rbx+18h], 1
0x180008e31  mov     rax, [rsi+8]
0x180008e35  lea     r14, [rsi+20h]
0x180008e39  cmp     qword ptr [r14], 0
0x180008e3d  movups  xmm0, xmmword ptr [rax-10h]
0x180008e41  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180008e47  jz      short loc_180008E50
0x180008e49  mov     ecx, 5
0x180008e4e  int     29h; Win8: RtlFailFast(ecx)
0x180008e50  mov     r9, r14; RegHandle
0x180008e53  mov     qword ptr [rsi+28h], 0
0x180008e5b  mov     r8, rsi; CallbackContext
0x180008e5e  mov     qword ptr [rsi+30h], 0
0x180008e66  lea     rdx, _tlgEnableCallback; EnableCallback
0x180008e6d  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180008e72  call    cs:__imp_EventRegister
0x180008e78  test    eax, eax
0x180008e7a  jnz     short loc_180008E90
0x180008e7c  mov     r8, [rsi+8]
0x180008e80  lea     edx, [rax+2]
0x180008e83  mov     rcx, [r14]
0x180008e86  movzx   r9d, word ptr [r8]
0x180008e8a  call    cs:__imp_EventSetInformation
0x180008e90  mov     rax, [rbx+8]
0x180008e94  lea     rcx, [rbx+8]
0x180008e98  mov     dword ptr [rbx+1Ch], 1
0x180008e9f  mov     rax, [rax+8]
0x180008ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ea8  mov     rcx, [rdi]; lpInitOnce
0x180008eab  mov     edx, [rdi+8]; dwFlags
0x180008eae  lea     r8, [rcx+8]; lpContext
0x180008eb2  call    cs:__imp_InitOnceComplete
0x180008eb8  mov     rcx, [rsp+68h+var_38]
0x180008ebd  xor     rcx, rsp; StackCookie
0x180008ec0  call    __security_check_cookie
0x180008ec5  add     rsp, 48h
0x180008ec9  pop     r14
0x180008ecb  pop     rdi
0x180008ecc  pop     rsi
0x180008ecd  pop     rbx
0x180008ece  retn
```
