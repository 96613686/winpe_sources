# wil::details::static_lazy<NcdAutoSetupLogging>::Completer::~Completer(void)

- ea: `0x1800034b8`
- end: `0x18000358b`
- name: `??1Completer@?$static_lazy@VNcdAutoSetupLogging@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005f94`

## callees

- `0x1800034b8`
- `0x180013840`
- `0x180014010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000352e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000352e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180003546`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180003546`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000356e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000356e`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<NcdAutoSetupLogging>::Completer::~Completer(_DWORD *a1)
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
0x1800034b8  push    rbx
0x1800034ba  push    rsi
0x1800034bb  push    rdi
0x1800034bc  push    r14
0x1800034be  sub     rsp, 48h
0x1800034c2  mov     rax, cs:__security_cookie
0x1800034c9  xor     rax, rsp
0x1800034cc  mov     [rsp+68h+var_38], rax
0x1800034d1  cmp     dword ptr [rcx+8], 0
0x1800034d5  mov     rdi, rcx
0x1800034d8  jnz     loc_180003564
0x1800034de  mov     rbx, [rcx]
0x1800034e1  mov     rsi, [rbx+20h]
0x1800034e5  mov     [rbx+10h], rsi
0x1800034e9  mov     byte ptr [rbx+18h], 1
0x1800034ed  mov     rax, [rsi+8]
0x1800034f1  lea     r14, [rsi+20h]
0x1800034f5  cmp     qword ptr [r14], 0
0x1800034f9  movups  xmm0, xmmword ptr [rax-10h]
0x1800034fd  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180003503  jz      short loc_18000350C
0x180003505  mov     ecx, 5
0x18000350a  int     29h; Win8: RtlFailFast(ecx)
0x18000350c  mov     r9, r14; RegHandle
0x18000350f  mov     qword ptr [rsi+28h], 0
0x180003517  mov     r8, rsi; CallbackContext
0x18000351a  mov     qword ptr [rsi+30h], 0
0x180003522  lea     rdx, _tlgEnableCallback; EnableCallback
0x180003529  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x18000352e  call    cs:__imp_EventRegister
0x180003534  test    eax, eax
0x180003536  jnz     short loc_18000354C
0x180003538  mov     r8, [rsi+8]
0x18000353c  lea     edx, [rax+2]
0x18000353f  mov     rcx, [r14]
0x180003542  movzx   r9d, word ptr [r8]
0x180003546  call    cs:__imp_EventSetInformation
0x18000354c  mov     rax, [rbx+8]
0x180003550  lea     rcx, [rbx+8]
0x180003554  mov     dword ptr [rbx+1Ch], 1
0x18000355b  mov     rax, [rax+8]
0x18000355f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003564  mov     rcx, [rdi]; lpInitOnce
0x180003567  mov     edx, [rdi+8]; dwFlags
0x18000356a  lea     r8, [rcx+8]; lpContext
0x18000356e  call    cs:__imp_InitOnceComplete
0x180003574  mov     rcx, [rsp+68h+var_38]
0x180003579  xor     rcx, rsp; StackCookie
0x18000357c  call    __security_check_cookie
0x180003581  add     rsp, 48h
0x180003585  pop     r14
0x180003587  pop     rdi
0x180003588  pop     rsi
0x180003589  pop     rbx
0x18000358a  retn
```
