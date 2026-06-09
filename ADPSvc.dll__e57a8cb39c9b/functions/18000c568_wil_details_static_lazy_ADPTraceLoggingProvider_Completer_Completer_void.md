# wil::details::static_lazy<ADPTraceLoggingProvider>::Completer::~Completer(void)

- ea: `0x18000c568`
- end: `0x18000c63b`
- name: `??1Completer@?$static_lazy@VADPTraceLoggingProvider@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e1d0`

## callees

- `0x180002250`
- `0x18000c568`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000c5de`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000c5de`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000c5f6`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000c5f6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c61e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c61e`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<ADPTraceLoggingProvider>::Completer::~Completer(_DWORD *a1)
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
0x18000c568  push    rbx
0x18000c56a  push    rsi
0x18000c56b  push    rdi
0x18000c56c  push    r14
0x18000c56e  sub     rsp, 48h
0x18000c572  mov     rax, cs:__security_cookie
0x18000c579  xor     rax, rsp
0x18000c57c  mov     [rsp+68h+var_38], rax
0x18000c581  cmp     dword ptr [rcx+8], 0
0x18000c585  mov     rdi, rcx
0x18000c588  jnz     loc_18000C614
0x18000c58e  mov     rbx, [rcx]
0x18000c591  mov     rsi, [rbx+20h]
0x18000c595  mov     [rbx+10h], rsi
0x18000c599  mov     byte ptr [rbx+18h], 1
0x18000c59d  mov     rax, [rsi+8]
0x18000c5a1  lea     r14, [rsi+20h]
0x18000c5a5  cmp     qword ptr [r14], 0
0x18000c5a9  movups  xmm0, xmmword ptr [rax-10h]
0x18000c5ad  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x18000c5b3  jz      short loc_18000C5BC
0x18000c5b5  mov     ecx, 5
0x18000c5ba  int     29h; Win8: RtlFailFast(ecx)
0x18000c5bc  mov     r9, r14; RegHandle
0x18000c5bf  mov     qword ptr [rsi+28h], 0
0x18000c5c7  mov     r8, rsi; CallbackContext
0x18000c5ca  mov     qword ptr [rsi+30h], 0
0x18000c5d2  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000c5d9  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x18000c5de  call    cs:__imp_EventRegister
0x18000c5e4  test    eax, eax
0x18000c5e6  jnz     short loc_18000C5FC
0x18000c5e8  mov     r8, [rsi+8]
0x18000c5ec  lea     edx, [rax+2]
0x18000c5ef  mov     rcx, [r14]
0x18000c5f2  movzx   r9d, word ptr [r8]
0x18000c5f6  call    cs:__imp_EventSetInformation
0x18000c5fc  mov     rax, [rbx+8]
0x18000c600  lea     rcx, [rbx+8]
0x18000c604  mov     dword ptr [rbx+1Ch], 1
0x18000c60b  mov     rax, [rax+8]
0x18000c60f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c614  mov     rcx, [rdi]; lpInitOnce
0x18000c617  mov     edx, [rdi+8]; dwFlags
0x18000c61a  lea     r8, [rcx+8]; lpContext
0x18000c61e  call    cs:__imp_InitOnceComplete
0x18000c624  mov     rcx, [rsp+68h+var_38]
0x18000c629  xor     rcx, rsp; StackCookie
0x18000c62c  call    __security_check_cookie
0x18000c631  add     rsp, 48h
0x18000c635  pop     r14
0x18000c637  pop     rdi
0x18000c638  pop     rsi
0x18000c639  pop     rbx
0x18000c63a  retn
```
