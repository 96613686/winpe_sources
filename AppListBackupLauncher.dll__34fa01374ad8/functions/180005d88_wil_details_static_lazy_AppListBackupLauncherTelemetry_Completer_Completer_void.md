# wil::details::static_lazy<AppListBackupLauncherTelemetry>::Completer::~Completer(void)

- ea: `0x180005d88`
- end: `0x180005e5b`
- name: `??1Completer@?$static_lazy@VAppListBackupLauncherTelemetry@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009e0c`

## callees

- `0x180002300`
- `0x180005d88`
- `0x180012010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180005e16`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180005e16`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180005dfe`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180005dfe`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180005e3e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180005e3e`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<AppListBackupLauncherTelemetry>::Completer::~Completer(_DWORD *a1)
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
0x180005d88  push    rbx
0x180005d8a  push    rsi
0x180005d8b  push    rdi
0x180005d8c  push    r14
0x180005d8e  sub     rsp, 48h
0x180005d92  mov     rax, cs:__security_cookie
0x180005d99  xor     rax, rsp
0x180005d9c  mov     [rsp+68h+var_38], rax
0x180005da1  cmp     dword ptr [rcx+8], 0
0x180005da5  mov     rdi, rcx
0x180005da8  jnz     loc_180005E34
0x180005dae  mov     rbx, [rcx]
0x180005db1  mov     rsi, [rbx+20h]
0x180005db5  mov     [rbx+10h], rsi
0x180005db9  mov     byte ptr [rbx+18h], 1
0x180005dbd  mov     rax, [rsi+8]
0x180005dc1  lea     r14, [rsi+20h]
0x180005dc5  cmp     qword ptr [r14], 0
0x180005dc9  movups  xmm0, xmmword ptr [rax-10h]
0x180005dcd  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180005dd3  jz      short loc_180005DDC
0x180005dd5  mov     ecx, 5
0x180005dda  int     29h; Win8: RtlFailFast(ecx)
0x180005ddc  mov     r9, r14; RegHandle
0x180005ddf  mov     qword ptr [rsi+28h], 0
0x180005de7  mov     r8, rsi; CallbackContext
0x180005dea  mov     qword ptr [rsi+30h], 0
0x180005df2  lea     rdx, _tlgEnableCallback; EnableCallback
0x180005df9  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180005dfe  call    cs:__imp_EventRegister
0x180005e04  test    eax, eax
0x180005e06  jnz     short loc_180005E1C
0x180005e08  mov     r8, [rsi+8]
0x180005e0c  lea     edx, [rax+2]
0x180005e0f  mov     rcx, [r14]
0x180005e12  movzx   r9d, word ptr [r8]
0x180005e16  call    cs:__imp_EventSetInformation
0x180005e1c  mov     rax, [rbx+8]
0x180005e20  lea     rcx, [rbx+8]
0x180005e24  mov     dword ptr [rbx+1Ch], 1
0x180005e2b  mov     rax, [rax+8]
0x180005e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e34  mov     rcx, [rdi]; lpInitOnce
0x180005e37  mov     edx, [rdi+8]; dwFlags
0x180005e3a  lea     r8, [rcx+8]; lpContext
0x180005e3e  call    cs:__imp_InitOnceComplete
0x180005e44  mov     rcx, [rsp+68h+var_38]
0x180005e49  xor     rcx, rsp; StackCookie
0x180005e4c  call    __security_check_cookie
0x180005e51  add     rsp, 48h
0x180005e55  pop     r14
0x180005e57  pop     rdi
0x180005e58  pop     rsi
0x180005e59  pop     rbx
0x180005e5a  retn
```
