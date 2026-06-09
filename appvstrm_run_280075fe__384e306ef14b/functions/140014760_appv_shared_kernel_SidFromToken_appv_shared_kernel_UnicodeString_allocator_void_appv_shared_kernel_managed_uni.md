# appv::shared::kernel::SidFromToken<appv::shared::kernel::UnicodeString_allocator>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,uchar *)

- ea: `0x140014760`
- end: `0x1400147f6`
- name: `??$SidFromToken@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@012@PEAE@Z`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140014640`
- `0x140014934`

## callees

- `0x14000d718`
- `0x140014760`
- `0x140014d38`
- `0x140015af0`

## import_xrefs

- `ntoskrnl!ZwQueryInformationToken` at `0x1400147a6`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400147a6`

## pseudocode

```c
int __fastcall appv::shared::kernel::SidFromToken<appv::shared::kernel::UnicodeString_allocator>(
        void *a1,
        __int64 a2,
        bool *a3)
{
  int result; // eax
  ULONG ReturnLength[4]; // [rsp+30h] [rbp-88h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  ReturnLength[0] = 0;
  result = ZwQueryInformationToken(a1, TokenUser, TokenInformation, 0x54u, ReturnLength);
  if ( result >= 0 )
  {
    if ( a3 )
      *a3 = appv::shared::kernel::sid_is_system(TokenInformation[0]);
    return appv::shared::kernel::ConvertSid<appv::shared::kernel::UnicodeString_allocator>(TokenInformation[0], a2);
  }
  return result;
}

```

## disassembly

```asm
0x140014760  mov     [rsp+arg_18], rbx
0x140014765  push    rdi
0x140014766  sub     rsp, 0B0h
0x14001476d  mov     rax, cs:__security_cookie
0x140014774  xor     rax, rsp
0x140014777  mov     [rsp+0B8h+var_18], rax
0x14001477f  mov     r9d, 54h ; 'T'; TokenInformationLength
0x140014785  mov     [rsp+0B8h+var_88], 0
0x14001478d  mov     rbx, r8
0x140014790  lea     rax, [rsp+0B8h+var_88]
0x140014795  mov     rdi, rdx
0x140014798  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x14001479d  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x1400147a2  lea     edx, [r9-53h]; TokenInformationClass
0x1400147a6  call    cs:__imp_ZwQueryInformationToken
0x1400147ad  nop     dword ptr [rax+rax+00h]
0x1400147b2  test    eax, eax
0x1400147b4  js      short loc_1400147D4
0x1400147b6  test    rbx, rbx
0x1400147b9  jz      short loc_1400147C7
0x1400147bb  mov     rcx, [rsp+0B8h+TokenInformation]; Sid2
0x1400147c0  call    appv__shared__kernel__sid_is_system
0x1400147c5  mov     [rbx], al
0x1400147c7  mov     rcx, [rsp+0B8h+TokenInformation]; Sid
0x1400147cc  mov     rdx, rdi
0x1400147cf  call    ??$ConvertSid@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@012@@Z; appv::shared::kernel::ConvertSid<appv::shared::kernel::UnicodeString_allocator>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)
0x1400147d4  mov     rcx, [rsp+0B8h+var_18]
0x1400147dc  xor     rcx, rsp; StackCookie
0x1400147df  call    __security_check_cookie
0x1400147e4  mov     rbx, [rsp+0B8h+arg_18]
0x1400147ec  add     rsp, 0B0h
0x1400147f3  pop     rdi
0x1400147f4  retn
```
