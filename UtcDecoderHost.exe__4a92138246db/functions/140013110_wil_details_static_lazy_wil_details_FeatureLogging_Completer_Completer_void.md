# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x140013110`
- end: `0x1400131e3`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001449c`

## callees

- `0x140008660`
- `0x140013110`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400131c6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400131c6`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140013186`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140013186`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x14001319e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x14001319e`

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
0x140013110  push    rbx
0x140013112  push    rsi
0x140013113  push    rdi
0x140013114  push    r14
0x140013116  sub     rsp, 48h
0x14001311a  mov     rax, cs:__security_cookie
0x140013121  xor     rax, rsp
0x140013124  mov     [rsp+68h+var_38], rax
0x140013129  cmp     dword ptr [rcx+8], 0
0x14001312d  mov     rdi, rcx
0x140013130  jnz     loc_1400131BC
0x140013136  mov     rbx, [rcx]
0x140013139  mov     rsi, [rbx+20h]
0x14001313d  mov     [rbx+10h], rsi
0x140013141  mov     byte ptr [rbx+18h], 1
0x140013145  mov     rax, [rsi+8]
0x140013149  lea     r14, [rsi+20h]
0x14001314d  cmp     qword ptr [r14], 0
0x140013151  movups  xmm0, xmmword ptr [rax-10h]
0x140013155  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x14001315b  jz      short loc_140013164
0x14001315d  mov     ecx, 5
0x140013162  int     29h; Win8: RtlFailFast(ecx)
0x140013164  mov     r9, r14; RegHandle
0x140013167  mov     qword ptr [rsi+28h], 0
0x14001316f  mov     r8, rsi; CallbackContext
0x140013172  mov     qword ptr [rsi+30h], 0
0x14001317a  lea     rdx, _tlgEnableCallback; EnableCallback
0x140013181  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x140013186  call    cs:__imp_EventRegister
0x14001318c  test    eax, eax
0x14001318e  jnz     short loc_1400131A4
0x140013190  mov     r8, [rsi+8]
0x140013194  lea     edx, [rax+2]
0x140013197  mov     rcx, [r14]
0x14001319a  movzx   r9d, word ptr [r8]
0x14001319e  call    cs:__imp_EventSetInformation
0x1400131a4  mov     rax, [rbx+8]
0x1400131a8  lea     rcx, [rbx+8]
0x1400131ac  mov     dword ptr [rbx+1Ch], 1
0x1400131b3  mov     rax, [rax+8]
0x1400131b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400131bc  mov     rcx, [rdi]; lpInitOnce
0x1400131bf  mov     edx, [rdi+8]; dwFlags
0x1400131c2  lea     r8, [rcx+8]; lpContext
0x1400131c6  call    cs:__imp_InitOnceComplete
0x1400131cc  mov     rcx, [rsp+68h+var_38]
0x1400131d1  xor     rcx, rsp; StackCookie
0x1400131d4  call    __security_check_cookie
0x1400131d9  add     rsp, 48h
0x1400131dd  pop     r14
0x1400131df  pop     rdi
0x1400131e0  pop     rsi
0x1400131e1  pop     rbx
0x1400131e2  retn
```
