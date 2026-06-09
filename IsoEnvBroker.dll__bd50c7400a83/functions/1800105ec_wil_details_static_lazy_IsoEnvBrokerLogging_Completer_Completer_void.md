# wil::details::static_lazy<IsoEnvBrokerLogging>::Completer::~Completer(void)

- ea: `0x1800105ec`
- end: `0x1800106bf`
- name: `??1Completer@?$static_lazy@VIsoEnvBrokerLogging@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011d64`

## callees

- `0x180002520`
- `0x1800105ec`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800106a2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800106a2`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001067a`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001067a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180010662`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180010662`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<IsoEnvBrokerLogging>::Completer::~Completer(_DWORD *a1)
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
0x1800105ec  push    rbx
0x1800105ee  push    rsi
0x1800105ef  push    rdi
0x1800105f0  push    r14
0x1800105f2  sub     rsp, 48h
0x1800105f6  mov     rax, cs:__security_cookie
0x1800105fd  xor     rax, rsp
0x180010600  mov     [rsp+68h+var_38], rax
0x180010605  cmp     dword ptr [rcx+8], 0
0x180010609  mov     rdi, rcx
0x18001060c  jnz     loc_180010698
0x180010612  mov     rbx, [rcx]
0x180010615  mov     rsi, [rbx+20h]
0x180010619  mov     [rbx+10h], rsi
0x18001061d  mov     byte ptr [rbx+18h], 1
0x180010621  mov     rax, [rsi+8]
0x180010625  lea     r14, [rsi+20h]
0x180010629  cmp     qword ptr [r14], 0
0x18001062d  movups  xmm0, xmmword ptr [rax-10h]
0x180010631  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180010637  jz      short loc_180010640
0x180010639  mov     ecx, 5
0x18001063e  int     29h; Win8: RtlFailFast(ecx)
0x180010640  mov     r9, r14; RegHandle
0x180010643  mov     qword ptr [rsi+28h], 0
0x18001064b  mov     r8, rsi; CallbackContext
0x18001064e  mov     qword ptr [rsi+30h], 0
0x180010656  lea     rdx, _tlgEnableCallback; EnableCallback
0x18001065d  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180010662  call    cs:__imp_EventRegister
0x180010668  test    eax, eax
0x18001066a  jnz     short loc_180010680
0x18001066c  mov     r8, [rsi+8]
0x180010670  lea     edx, [rax+2]
0x180010673  mov     rcx, [r14]
0x180010676  movzx   r9d, word ptr [r8]
0x18001067a  call    cs:__imp_EventSetInformation
0x180010680  mov     rax, [rbx+8]
0x180010684  lea     rcx, [rbx+8]
0x180010688  mov     dword ptr [rbx+1Ch], 1
0x18001068f  mov     rax, [rax+8]
0x180010693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010698  mov     rcx, [rdi]; lpInitOnce
0x18001069b  mov     edx, [rdi+8]; dwFlags
0x18001069e  lea     r8, [rcx+8]; lpContext
0x1800106a2  call    cs:__imp_InitOnceComplete
0x1800106a8  mov     rcx, [rsp+68h+var_38]
0x1800106ad  xor     rcx, rsp; StackCookie
0x1800106b0  call    __security_check_cookie
0x1800106b5  add     rsp, 48h
0x1800106b9  pop     r14
0x1800106bb  pop     rdi
0x1800106bc  pop     rsi
0x1800106bd  pop     rbx
0x1800106be  retn
```
