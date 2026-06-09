# wil::details::static_lazy<IPxlatTelemetry>::Completer::~Completer(void)

- ea: `0x1800131d0`
- end: `0x1800132a3`
- name: `??1Completer@?$static_lazy@VIPxlatTelemetry@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015d0c`

## callees

- `0x180001d40`
- `0x1800131d0`
- `0x180019010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180013246`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180013246`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001325e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001325e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180013286`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180013286`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<IPxlatTelemetry>::Completer::~Completer(_DWORD *a1)
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
0x1800131d0  push    rbx
0x1800131d2  push    rsi
0x1800131d3  push    rdi
0x1800131d4  push    r14
0x1800131d6  sub     rsp, 48h
0x1800131da  mov     rax, cs:__security_cookie
0x1800131e1  xor     rax, rsp
0x1800131e4  mov     [rsp+68h+var_38], rax
0x1800131e9  cmp     dword ptr [rcx+8], 0
0x1800131ed  mov     rdi, rcx
0x1800131f0  jnz     loc_18001327C
0x1800131f6  mov     rbx, [rcx]
0x1800131f9  mov     rsi, [rbx+20h]
0x1800131fd  mov     [rbx+10h], rsi
0x180013201  mov     byte ptr [rbx+18h], 1
0x180013205  mov     rax, [rsi+8]
0x180013209  lea     r14, [rsi+20h]
0x18001320d  cmp     qword ptr [r14], 0
0x180013211  movups  xmm0, xmmword ptr [rax-10h]
0x180013215  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x18001321b  jz      short loc_180013224
0x18001321d  mov     ecx, 5
0x180013222  int     29h; Win8: RtlFailFast(ecx)
0x180013224  mov     r9, r14; RegHandle
0x180013227  mov     qword ptr [rsi+28h], 0
0x18001322f  mov     r8, rsi; CallbackContext
0x180013232  mov     qword ptr [rsi+30h], 0
0x18001323a  lea     rdx, _tlgEnableCallback; EnableCallback
0x180013241  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180013246  call    cs:__imp_EventRegister
0x18001324c  test    eax, eax
0x18001324e  jnz     short loc_180013264
0x180013250  mov     r8, [rsi+8]
0x180013254  lea     edx, [rax+2]
0x180013257  mov     rcx, [r14]
0x18001325a  movzx   r9d, word ptr [r8]
0x18001325e  call    cs:__imp_EventSetInformation
0x180013264  mov     rax, [rbx+8]
0x180013268  lea     rcx, [rbx+8]
0x18001326c  mov     dword ptr [rbx+1Ch], 1
0x180013273  mov     rax, [rax+8]
0x180013277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001327c  mov     rcx, [rdi]; lpInitOnce
0x18001327f  mov     edx, [rdi+8]; dwFlags
0x180013282  lea     r8, [rcx+8]; lpContext
0x180013286  call    cs:__imp_InitOnceComplete
0x18001328c  mov     rcx, [rsp+68h+var_38]
0x180013291  xor     rcx, rsp; StackCookie
0x180013294  call    __security_check_cookie
0x180013299  add     rsp, 48h
0x18001329d  pop     r14
0x18001329f  pop     rdi
0x1800132a0  pop     rsi
0x1800132a1  pop     rbx
0x1800132a2  retn
```
