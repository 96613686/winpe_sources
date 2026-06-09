# softgrid::shared::get_effective_impersonation_token(ATL::CAccessToken &,ulong)

- ea: `0x1400393c4`
- end: `0x140039495`
- name: `?get_effective_impersonation_token@shared@softgrid@@YA_NAEAVCAccessToken@ATL@@K@Z`
- size: `209`
- prototype: `bool __fastcall(softgrid::shared *__hidden this, struct ATL::CAccessToken *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140028e00`

## callees

- `0x1400393c4`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x1400393ed`
- `ADVAPI32!OpenThreadToken` at `0x1400393ed`
- `ADVAPI32!OpenProcessToken` at `0x14003942f`
- `ADVAPI32!OpenProcessToken` at `0x14003942f`
- `ADVAPI32!DuplicateToken` at `0x140039464`
- `ADVAPI32!DuplicateToken` at `0x140039464`
- `KERNEL32!GetCurrentThread` at `0x1400393cd`
- `KERNEL32!GetCurrentThread` at `0x1400393cd`
- `KERNEL32!GetCurrentProcess` at `0x140039413`
- `KERNEL32!GetCurrentProcess` at `0x140039413`

## pseudocode

```c
char __fastcall softgrid::shared::get_effective_impersonation_token(
        softgrid::shared *this,
        struct ATL::CAccessToken *a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  HANDLE v6; // rcx
  HANDLE TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  CurrentThread = GetCurrentThread();
  TokenHandle = 0;
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_2;
  CurrentProcess = GetCurrentProcess();
  TokenHandle = 0;
  if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
    return 0;
  (*(void (__fastcall **)(softgrid::shared *))(*(_QWORD *)this + 8LL))(this);
  v6 = TokenHandle;
  *((_QWORD *)this + 1) = TokenHandle;
  TokenHandle = 0;
  if ( DuplicateToken(v6, SecurityImpersonation, &TokenHandle) )
  {
LABEL_2:
    (*(void (__fastcall **)(softgrid::shared *))(*(_QWORD *)this + 8LL))(this);
    *((_QWORD *)this + 1) = TokenHandle;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1400393c4  push    rbx
0x1400393c6  sub     rsp, 20h
0x1400393ca  mov     rbx, rcx
0x1400393cd  call    cs:__imp_GetCurrentThread
0x1400393d3  mov     [rsp+28h+TokenHandle], 0
0x1400393dc  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1400393e1  mov     edx, 8; DesiredAccess
0x1400393e6  lea     r8d, [rdx-7]; OpenAsSelf
0x1400393ea  mov     rcx, rax; ThreadHandle
0x1400393ed  call    cs:__imp_OpenThreadToken
0x1400393f3  test    eax, eax
0x1400393f5  jz      short loc_140039413
0x1400393f7  mov     rcx, [rbx]
0x1400393fa  mov     rax, [rcx+8]
0x1400393fe  mov     rcx, rbx
0x140039401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039406  mov     rcx, [rsp+28h+TokenHandle]
0x14003940b  mov     [rbx+8], rcx
0x14003940f  mov     al, 1
0x140039411  jmp     short loc_14003948E
0x140039413  call    cs:__imp_GetCurrentProcess
0x140039419  mov     [rsp+28h+TokenHandle], 0
0x140039422  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x140039427  mov     edx, 0Ah; DesiredAccess
0x14003942c  mov     rcx, rax; ProcessHandle
0x14003942f  call    cs:__imp_OpenProcessToken
0x140039435  test    eax, eax
0x140039437  jz      short loc_14003948C
0x140039439  mov     rax, [rbx]
0x14003943c  mov     rcx, rbx
0x14003943f  mov     rax, [rax+8]
0x140039443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039448  mov     rcx, [rsp+28h+TokenHandle]; ExistingTokenHandle
0x14003944d  mov     [rbx+8], rcx
0x140039451  mov     [rsp+28h+TokenHandle], 0
0x14003945a  lea     r8, [rsp+28h+TokenHandle]; DuplicateTokenHandle
0x14003945f  mov     edx, 2; ImpersonationLevel
0x140039464  call    cs:__imp_DuplicateToken
0x14003946a  test    eax, eax
0x14003946c  jz      short loc_140039488
0x14003946e  mov     rax, [rbx]
0x140039471  mov     rcx, rbx
0x140039474  mov     rax, [rax+8]
0x140039478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003947d  mov     rax, [rsp+28h+TokenHandle]
0x140039482  mov     [rbx+8], rax
0x140039486  jmp     short loc_14003940F
0x140039488  xor     al, al
0x14003948a  jmp     short loc_14003948E
0x14003948c  xor     al, al
0x14003948e  add     rsp, 20h
0x140039492  pop     rbx
0x140039493  retn
```
