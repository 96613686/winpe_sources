# wil::details::static_lazy<DeviceCenterContextHandlersLogging>::Completer::~Completer(void)

- ea: `0x180005c40`
- end: `0x180005d13`
- name: `??1Completer@?$static_lazy@VDeviceCenterContextHandlersLogging@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009170`

## callees

- `0x180005c40`
- `0x18000c990`
- `0x18000e010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180005cce`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180005cce`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180005cb6`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180005cb6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180005cf6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180005cf6`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<DeviceCenterContextHandlersLogging>::Completer::~Completer(_DWORD *a1)
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
0x180005c40  push    rbx
0x180005c42  push    rsi
0x180005c43  push    rdi
0x180005c44  push    r14
0x180005c46  sub     rsp, 48h
0x180005c4a  mov     rax, cs:__security_cookie
0x180005c51  xor     rax, rsp
0x180005c54  mov     [rsp+68h+var_38], rax
0x180005c59  cmp     dword ptr [rcx+8], 0
0x180005c5d  mov     rdi, rcx
0x180005c60  jnz     loc_180005CEC
0x180005c66  mov     rbx, [rcx]
0x180005c69  mov     rsi, [rbx+20h]
0x180005c6d  mov     [rbx+10h], rsi
0x180005c71  mov     byte ptr [rbx+18h], 1
0x180005c75  mov     rax, [rsi+8]
0x180005c79  lea     r14, [rsi+20h]
0x180005c7d  cmp     qword ptr [r14], 0
0x180005c81  movups  xmm0, xmmword ptr [rax-10h]
0x180005c85  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180005c8b  jz      short loc_180005C94
0x180005c8d  mov     ecx, 5
0x180005c92  int     29h; Win8: RtlFailFast(ecx)
0x180005c94  mov     r9, r14; RegHandle
0x180005c97  mov     qword ptr [rsi+28h], 0
0x180005c9f  mov     r8, rsi; CallbackContext
0x180005ca2  mov     qword ptr [rsi+30h], 0
0x180005caa  lea     rdx, _tlgEnableCallback; EnableCallback
0x180005cb1  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180005cb6  call    cs:__imp_EventRegister
0x180005cbc  test    eax, eax
0x180005cbe  jnz     short loc_180005CD4
0x180005cc0  mov     r8, [rsi+8]
0x180005cc4  lea     edx, [rax+2]
0x180005cc7  mov     rcx, [r14]
0x180005cca  movzx   r9d, word ptr [r8]
0x180005cce  call    cs:__imp_EventSetInformation
0x180005cd4  mov     rax, [rbx+8]
0x180005cd8  lea     rcx, [rbx+8]
0x180005cdc  mov     dword ptr [rbx+1Ch], 1
0x180005ce3  mov     rax, [rax+8]
0x180005ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cec  mov     rcx, [rdi]; lpInitOnce
0x180005cef  mov     edx, [rdi+8]; dwFlags
0x180005cf2  lea     r8, [rcx+8]; lpContext
0x180005cf6  call    cs:__imp_InitOnceComplete
0x180005cfc  mov     rcx, [rsp+68h+var_38]
0x180005d01  xor     rcx, rsp; StackCookie
0x180005d04  call    __security_check_cookie
0x180005d09  add     rsp, 48h
0x180005d0d  pop     r14
0x180005d0f  pop     rdi
0x180005d10  pop     rsi
0x180005d11  pop     rbx
0x180005d12  retn
```
