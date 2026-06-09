# wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(void)

- ea: `0x180003ea4`
- end: `0x180003f77`
- name: `??1Completer@?$static_lazy@VOfflineMapsTraceLogging@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005c50`

## callees

- `0x180002550`
- `0x180003ea4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180003f5a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180003f5a`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180003f32`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180003f32`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003f1a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003f1a`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(_DWORD *a1)
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
0x180003ea4  push    rbx
0x180003ea6  push    rsi
0x180003ea7  push    rdi
0x180003ea8  push    r14
0x180003eaa  sub     rsp, 48h
0x180003eae  mov     rax, cs:__security_cookie
0x180003eb5  xor     rax, rsp
0x180003eb8  mov     [rsp+68h+var_38], rax
0x180003ebd  cmp     dword ptr [rcx+8], 0
0x180003ec1  mov     rdi, rcx
0x180003ec4  jnz     loc_180003F50
0x180003eca  mov     rbx, [rcx]
0x180003ecd  mov     rsi, [rbx+20h]
0x180003ed1  mov     [rbx+10h], rsi
0x180003ed5  mov     byte ptr [rbx+18h], 1
0x180003ed9  mov     rax, [rsi+8]
0x180003edd  lea     r14, [rsi+20h]
0x180003ee1  cmp     qword ptr [r14], 0
0x180003ee5  movups  xmm0, xmmword ptr [rax-10h]
0x180003ee9  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180003eef  jz      short loc_180003EF8
0x180003ef1  mov     ecx, 5
0x180003ef6  int     29h; Win8: RtlFailFast(ecx)
0x180003ef8  mov     r9, r14; RegHandle
0x180003efb  mov     qword ptr [rsi+28h], 0
0x180003f03  mov     r8, rsi; CallbackContext
0x180003f06  mov     qword ptr [rsi+30h], 0
0x180003f0e  lea     rdx, _tlgEnableCallback; EnableCallback
0x180003f15  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180003f1a  call    cs:__imp_EventRegister
0x180003f20  test    eax, eax
0x180003f22  jnz     short loc_180003F38
0x180003f24  mov     r8, [rsi+8]
0x180003f28  lea     edx, [rax+2]
0x180003f2b  mov     rcx, [r14]
0x180003f2e  movzx   r9d, word ptr [r8]
0x180003f32  call    cs:__imp_EventSetInformation
0x180003f38  mov     rax, [rbx+8]
0x180003f3c  lea     rcx, [rbx+8]
0x180003f40  mov     dword ptr [rbx+1Ch], 1
0x180003f47  mov     rax, [rax+8]
0x180003f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f50  mov     rcx, [rdi]; lpInitOnce
0x180003f53  mov     edx, [rdi+8]; dwFlags
0x180003f56  lea     r8, [rcx+8]; lpContext
0x180003f5a  call    cs:__imp_InitOnceComplete
0x180003f60  mov     rcx, [rsp+68h+var_38]
0x180003f65  xor     rcx, rsp; StackCookie
0x180003f68  call    __security_check_cookie
0x180003f6d  add     rsp, 48h
0x180003f71  pop     r14
0x180003f73  pop     rdi
0x180003f74  pop     rsi
0x180003f75  pop     rbx
0x180003f76  retn
```
