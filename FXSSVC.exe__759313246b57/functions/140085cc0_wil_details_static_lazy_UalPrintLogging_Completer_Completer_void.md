# wil::details::static_lazy<UalPrintLogging>::Completer::~Completer(void)

- ea: `0x140085cc0`
- end: `0x140085da6`
- name: `??1Completer@?$static_lazy@VUalPrintLogging@@@details@wil@@QEAA@XZ`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140085f74`

## callees

- `0x140085cc0`
- `0x140086ec0`
- `0x14008b010`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x140085d36`
- `ADVAPI32!EventRegister` at `0x140085d36`
- `ADVAPI32!EventSetInformation` at `0x140085d54`
- `ADVAPI32!EventSetInformation` at `0x140085d54`
- `KERNEL32!InitOnceComplete` at `0x140085d82`
- `KERNEL32!InitOnceComplete` at `0x140085d82`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<UalPrintLogging>::Completer::~Completer(_DWORD *a1)
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
0x140085cc0  push    rbx
0x140085cc2  push    rsi
0x140085cc3  push    rdi
0x140085cc4  push    r14
0x140085cc6  sub     rsp, 48h
0x140085cca  mov     rax, cs:__security_cookie
0x140085cd1  xor     rax, rsp
0x140085cd4  mov     [rsp+68h+var_38], rax
0x140085cd9  cmp     dword ptr [rcx+8], 0
0x140085cdd  mov     rdi, rcx
0x140085ce0  jnz     loc_140085D78
0x140085ce6  mov     rbx, [rcx]
0x140085ce9  mov     rsi, [rbx+20h]
0x140085ced  mov     [rbx+10h], rsi
0x140085cf1  mov     byte ptr [rbx+18h], 1
0x140085cf5  mov     rax, [rsi+8]
0x140085cf9  lea     r14, [rsi+20h]
0x140085cfd  cmp     qword ptr [r14], 0
0x140085d01  movups  xmm0, xmmword ptr [rax-10h]
0x140085d05  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x140085d0b  jz      short loc_140085D14
0x140085d0d  mov     ecx, 5
0x140085d12  int     29h; Win8: RtlFailFast(ecx)
0x140085d14  mov     r9, r14; RegHandle
0x140085d17  mov     qword ptr [rsi+28h], 0
0x140085d1f  mov     r8, rsi; CallbackContext
0x140085d22  mov     qword ptr [rsi+30h], 0
0x140085d2a  lea     rdx, _tlgEnableCallback; EnableCallback
0x140085d31  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x140085d36  call    cs:__imp_EventRegister
0x140085d3d  nop     dword ptr [rax+rax+00h]
0x140085d42  test    eax, eax
0x140085d44  jnz     short loc_140085D60
0x140085d46  mov     r8, [rsi+8]
0x140085d4a  lea     edx, [rax+2]
0x140085d4d  mov     rcx, [r14]
0x140085d50  movzx   r9d, word ptr [r8]
0x140085d54  call    cs:__imp_EventSetInformation
0x140085d5b  nop     dword ptr [rax+rax+00h]
0x140085d60  mov     rax, [rbx+8]
0x140085d64  lea     rcx, [rbx+8]
0x140085d68  mov     dword ptr [rbx+1Ch], 1
0x140085d6f  mov     rax, [rax+8]
0x140085d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140085d78  mov     rcx, [rdi]; lpInitOnce
0x140085d7b  mov     edx, [rdi+8]; dwFlags
0x140085d7e  lea     r8, [rcx+8]; lpContext
0x140085d82  call    cs:__imp_InitOnceComplete
0x140085d89  nop     dword ptr [rax+rax+00h]
0x140085d8e  mov     rcx, [rsp+68h+var_38]
0x140085d93  xor     rcx, rsp; StackCookie
0x140085d96  call    __security_check_cookie
0x140085d9b  add     rsp, 48h
0x140085d9f  pop     r14
0x140085da1  pop     rdi
0x140085da2  pop     rsi
0x140085da3  pop     rbx
0x140085da4  retn
```
