# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x18000916c`
- end: `0x18000923f`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000db3c`

## callees

- `0x180002240`
- `0x18000916c`
- `0x180058010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800091fa`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800091fa`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800091e2`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800091e2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009222`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009222`

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
0x18000916c  push    rbx
0x18000916e  push    rsi
0x18000916f  push    rdi
0x180009170  push    r14
0x180009172  sub     rsp, 48h
0x180009176  mov     rax, cs:__security_cookie
0x18000917d  xor     rax, rsp
0x180009180  mov     [rsp+68h+var_38], rax
0x180009185  cmp     dword ptr [rcx+8], 0
0x180009189  mov     rdi, rcx
0x18000918c  jnz     loc_180009218
0x180009192  mov     rbx, [rcx]
0x180009195  mov     rsi, [rbx+20h]
0x180009199  mov     [rbx+10h], rsi
0x18000919d  mov     byte ptr [rbx+18h], 1
0x1800091a1  mov     rax, [rsi+8]
0x1800091a5  lea     r14, [rsi+20h]
0x1800091a9  cmp     qword ptr [r14], 0
0x1800091ad  movups  xmm0, xmmword ptr [rax-10h]
0x1800091b1  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x1800091b7  jz      short loc_1800091C0
0x1800091b9  mov     ecx, 5
0x1800091be  int     29h; Win8: RtlFailFast(ecx)
0x1800091c0  mov     r9, r14; RegHandle
0x1800091c3  mov     qword ptr [rsi+28h], 0
0x1800091cb  mov     r8, rsi; CallbackContext
0x1800091ce  mov     qword ptr [rsi+30h], 0
0x1800091d6  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800091dd  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x1800091e2  call    cs:__imp_EventRegister
0x1800091e8  test    eax, eax
0x1800091ea  jnz     short loc_180009200
0x1800091ec  mov     r8, [rsi+8]
0x1800091f0  lea     edx, [rax+2]
0x1800091f3  mov     rcx, [r14]
0x1800091f6  movzx   r9d, word ptr [r8]
0x1800091fa  call    cs:__imp_EventSetInformation
0x180009200  mov     rax, [rbx+8]
0x180009204  lea     rcx, [rbx+8]
0x180009208  mov     dword ptr [rbx+1Ch], 1
0x18000920f  mov     rax, [rax+8]
0x180009213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009218  mov     rcx, [rdi]; lpInitOnce
0x18000921b  mov     edx, [rdi+8]; dwFlags
0x18000921e  lea     r8, [rcx+8]; lpContext
0x180009222  call    cs:__imp_InitOnceComplete
0x180009228  mov     rcx, [rsp+68h+var_38]
0x18000922d  xor     rcx, rsp; StackCookie
0x180009230  call    __security_check_cookie
0x180009235  add     rsp, 48h
0x180009239  pop     r14
0x18000923b  pop     rdi
0x18000923c  pop     rsi
0x18000923d  pop     rbx
0x18000923e  retn
```
