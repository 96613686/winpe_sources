# appv::shared::kernel::SidFromEThread<appv::shared::kernel::UnicodeString_allocator>(_KTHREAD *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,uchar *)

- ea: `0x140014560`
- end: `0x140014637`
- name: `??$SidFromEThread@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAU_KTHREAD@@AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@012@PEAE@Z`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140014c40`

## callees

- `0x14000d718`
- `0x140014560`
- `0x140014d38`

## import_xrefs

- `ntoskrnl!PsReferenceImpersonationToken` at `0x14001458c`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14001458c`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400145d5`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14001460c`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400145d5`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14001460c`
- `ntoskrnl!SeQueryInformationToken` at `0x1400145c0`
- `ntoskrnl!SeQueryInformationToken` at `0x1400145c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001461f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001461f`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::SidFromEThread<appv::shared::kernel::UnicodeString_allocator>(
        struct _KTHREAD *a1,
        __int64 a2,
        _BYTE *a3)
{
  PACCESS_TOKEN v4; // rax
  void *v5; // rdi
  NTSTATUS v7; // ebx
  unsigned __int8 v8[4]; // [rsp+20h] [rbp-38h] BYREF
  int v9; // [rsp+24h] [rbp-34h] BYREF
  PVOID TokenInformation; // [rsp+28h] [rbp-30h] BYREF
  unsigned __int8 v11; // [rsp+78h] [rbp+20h] BYREF

  v11 = 0;
  v8[0] = 0;
  v9 = 0;
  v4 = PsReferenceImpersonationToken(a1, v8, &v11, (PSECURITY_IMPERSONATION_LEVEL)&v9);
  v5 = v4;
  if ( !v4 )
    return 3221225596LL;
  TokenInformation = 0;
  v7 = SeQueryInformationToken(v4, TokenOwner, &TokenInformation);
  if ( v7 >= 0 )
  {
    if ( a3 )
      *a3 = appv::shared::kernel::sid_is_system(*(PSID *)TokenInformation);
    v7 = appv::shared::kernel::ConvertSid<appv::shared::kernel::UnicodeString_allocator>(*(PSID *)TokenInformation);
    PsDereferenceImpersonationToken(v5);
    ExFreePoolWithTag(TokenInformation, 0);
  }
  else
  {
    PsDereferenceImpersonationToken(v5);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140014560  mov     rax, rsp
0x140014563  push    rbx
0x140014564  push    rbp
0x140014565  push    rsi
0x140014566  push    rdi
0x140014567  sub     rsp, 38h
0x14001456b  mov     rsi, r8
0x14001456e  mov     byte ptr [rax+20h], 0
0x140014572  mov     rbp, rdx
0x140014575  mov     byte ptr [rax-38h], 0
0x140014579  lea     r8, [rax+20h]; EffectiveOnly
0x14001457d  mov     dword ptr [rax-34h], 0
0x140014584  lea     rdx, [rax-38h]; CopyOnOpen
0x140014588  lea     r9, [rax-34h]; ImpersonationLevel
0x14001458c  call    cs:__imp_PsReferenceImpersonationToken
0x140014593  nop     dword ptr [rax+rax+00h]
0x140014598  mov     rdi, rax
0x14001459b  test    rax, rax
0x14001459e  jnz     short loc_1400145AA
0x1400145a0  mov     eax, 0C000007Ch
0x1400145a5  jmp     loc_14001462D
0x1400145aa  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x1400145af  mov     [rsp+58h+TokenInformation], 0
0x1400145b8  mov     edx, 4; TokenInformationClass
0x1400145bd  mov     rcx, rdi; Token
0x1400145c0  call    cs:__imp_SeQueryInformationToken
0x1400145c7  nop     dword ptr [rax+rax+00h]
0x1400145cc  mov     ebx, eax
0x1400145ce  test    eax, eax
0x1400145d0  jns     short loc_1400145E3
0x1400145d2  mov     rcx, rdi; ImpersonationToken
0x1400145d5  call    cs:__imp_PsDereferenceImpersonationToken
0x1400145dc  nop     dword ptr [rax+rax+00h]
0x1400145e1  jmp     short loc_14001462B
0x1400145e3  test    rsi, rsi
0x1400145e6  jz      short loc_1400145F7
0x1400145e8  mov     rcx, [rsp+58h+TokenInformation]
0x1400145ed  mov     rcx, [rcx]; Sid2
0x1400145f0  call    appv__shared__kernel__sid_is_system
0x1400145f5  mov     [rsi], al
0x1400145f7  mov     rcx, [rsp+58h+TokenInformation]
0x1400145fc  mov     rdx, rbp
0x1400145ff  mov     rcx, [rcx]; Sid
0x140014602  call    ??$ConvertSid@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@012@@Z; appv::shared::kernel::ConvertSid<appv::shared::kernel::UnicodeString_allocator>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)
0x140014607  mov     rcx, rdi; ImpersonationToken
0x14001460a  mov     ebx, eax
0x14001460c  call    cs:__imp_PsDereferenceImpersonationToken
0x140014613  nop     dword ptr [rax+rax+00h]
0x140014618  mov     rcx, [rsp+58h+TokenInformation]; P
0x14001461d  xor     edx, edx; Tag
0x14001461f  call    cs:__imp_ExFreePoolWithTag
0x140014626  nop     dword ptr [rax+rax+00h]
0x14001462b  mov     eax, ebx
0x14001462d  add     rsp, 38h
0x140014631  pop     rdi
0x140014632  pop     rsi
0x140014633  pop     rbp
0x140014634  pop     rbx
0x140014635  retn
```
