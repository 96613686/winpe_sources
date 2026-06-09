# appv::shared::kernel::ConvertSid<appv::shared::kernel::UnicodeString_allocator>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)

- ea: `0x14000d718`
- end: `0x14000d79a`
- name: `??$ConvertSid@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@012@@Z`
- size: `130`
- prototype: `NTSTATUS __fastcall(PSID Sid, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000db88`
- `0x140014560`
- `0x140014760`

## callees

- `0x1400034fc`
- `0x14000d718`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d780`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d780`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000d75c`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000d75c`
- `ntoskrnl!RtlValidSid` at `0x14000d728`
- `ntoskrnl!RtlValidSid` at `0x14000d728`

## pseudocode

```c
NTSTATUS __fastcall appv::shared::kernel::ConvertSid<appv::shared::kernel::UnicodeString_allocator>(
        PSID Sid,
        __int64 a2)
{
  NTSTATUS result; // eax
  int v5; // ebx
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-18h] BYREF

  if ( !RtlValidSid(Sid) )
    return -1073741811;
  *(_QWORD *)&UnicodeString.Length = 0;
  UnicodeString.Buffer = 0;
  result = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u);
  if ( result >= 0 )
  {
    v5 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(
           a2,
           &UnicodeString);
    RtlFreeUnicodeString(&UnicodeString);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x14000d718  mov     [rsp+arg_0], rbx
0x14000d71d  push    rdi
0x14000d71e  sub     rsp, 30h
0x14000d722  mov     rdi, rdx
0x14000d725  mov     rbx, rcx
0x14000d728  call    cs:__imp_RtlValidSid
0x14000d72f  nop     dword ptr [rax+rax+00h]
0x14000d734  test    al, al
0x14000d736  jnz     short loc_14000D73F
0x14000d738  mov     eax, 0C000000Dh
0x14000d73d  jmp     short loc_14000D78E
0x14000d73f  mov     r8b, 1; AllocateDestinationString
0x14000d742  mov     qword ptr [rsp+38h+UnicodeString.Length], 0
0x14000d74b  mov     rdx, rbx; Sid
0x14000d74e  mov     [rsp+38h+UnicodeString.Buffer], 0
0x14000d757  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x14000d75c  call    cs:__imp_RtlConvertSidToUnicodeString
0x14000d763  nop     dword ptr [rax+rax+00h]
0x14000d768  test    eax, eax
0x14000d76a  js      short loc_14000D78E
0x14000d76c  lea     rdx, [rsp+38h+UnicodeString]
0x14000d771  mov     rcx, rdi
0x14000d774  call    ?build_managed_unicode_string@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(_UNICODE_STRING const &)
0x14000d779  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x14000d77e  mov     ebx, eax
0x14000d780  call    cs:__imp_RtlFreeUnicodeString
0x14000d787  nop     dword ptr [rax+rax+00h]
0x14000d78c  mov     eax, ebx
0x14000d78e  mov     rbx, [rsp+38h+arg_0]
0x14000d793  add     rsp, 30h
0x14000d797  pop     rdi
0x14000d798  retn
```
