# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x180009d7c`
- end: `0x180009e73`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c87c`

## callees

- `0x180002880`
- `0x180009d7c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009e43`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009e43`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180009df7`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180009df7`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180009e15`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180009e15`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  ULONGLONG *v3; // rsi
  bool v4; // zf
  __int64 v5; // rax
  GUID ProviderId; // [rsp+20h] [rbp-28h] BYREF

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
0x180009d7c  mov     [rsp+arg_8], rbx
0x180009d81  mov     [rsp+arg_10], rsi
0x180009d86  mov     [rsp+arg_18], rdi
0x180009d8b  push    r14
0x180009d8d  sub     rsp, 40h
0x180009d91  mov     rax, cs:__security_cookie
0x180009d98  xor     rax, rsp
0x180009d9b  mov     [rsp+48h+var_18], rax
0x180009da0  cmp     dword ptr [rcx+8], 0
0x180009da4  mov     rdi, rcx
0x180009da7  jnz     loc_180009E39
0x180009dad  mov     rbx, [rcx]
0x180009db0  mov     rsi, [rbx+20h]
0x180009db4  mov     [rbx+10h], rsi
0x180009db8  mov     byte ptr [rbx+18h], 1
0x180009dbc  mov     rax, [rsi+8]
0x180009dc0  lea     r14, [rsi+20h]
0x180009dc4  cmp     qword ptr [r14], 0
0x180009dc8  movups  xmm0, xmmword ptr [rax-10h]
0x180009dcc  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x180009dd2  jz      short loc_180009DDB
0x180009dd4  mov     ecx, 5
0x180009dd9  int     29h; Win8: RtlFailFast(ecx)
0x180009ddb  and     qword ptr [rsi+28h], 0
0x180009de0  lea     rdx, _tlgEnableCallback; EnableCallback
0x180009de7  and     qword ptr [rsi+30h], 0
0x180009dec  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x180009df1  mov     r9, r14; RegHandle
0x180009df4  mov     r8, rsi; CallbackContext
0x180009df7  call    cs:__imp_EventRegister
0x180009dfe  nop     dword ptr [rax+rax+00h]
0x180009e03  test    eax, eax
0x180009e05  jnz     short loc_180009E21
0x180009e07  mov     r8, [rsi+8]
0x180009e0b  lea     edx, [rax+2]
0x180009e0e  mov     rcx, [r14]
0x180009e11  movzx   r9d, word ptr [r8]
0x180009e15  call    cs:__imp_EventSetInformation
0x180009e1c  nop     dword ptr [rax+rax+00h]
0x180009e21  mov     rax, [rbx+8]
0x180009e25  lea     rcx, [rbx+8]
0x180009e29  mov     dword ptr [rbx+1Ch], 1
0x180009e30  mov     rax, [rax+8]
0x180009e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e39  mov     rcx, [rdi]; lpInitOnce
0x180009e3c  mov     edx, [rdi+8]; dwFlags
0x180009e3f  lea     r8, [rcx+8]; lpContext
0x180009e43  call    cs:__imp_InitOnceComplete
0x180009e4a  nop     dword ptr [rax+rax+00h]
0x180009e4f  mov     rcx, [rsp+48h+var_18]
0x180009e54  xor     rcx, rsp; StackCookie
0x180009e57  call    __security_check_cookie
0x180009e5c  mov     rbx, [rsp+48h+arg_8]
0x180009e61  mov     rsi, [rsp+48h+arg_10]
0x180009e66  mov     rdi, [rsp+48h+arg_18]
0x180009e6b  add     rsp, 40h
0x180009e6f  pop     r14
0x180009e71  retn
```
