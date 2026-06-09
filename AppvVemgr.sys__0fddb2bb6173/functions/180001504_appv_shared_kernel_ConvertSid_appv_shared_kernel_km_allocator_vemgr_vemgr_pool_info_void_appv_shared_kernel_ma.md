# appv::shared::kernel::ConvertSid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)

- ea: `0x180001504`
- end: `0x18000158f`
- name: `??$ConvertSid@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@012@@Z`
- size: `139`
- prototype: `NTSTATUS __fastcall(PSID Sid, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180002d7c`
- `0x180011538`
- `0x180011ca8`

## callees

- `0x180001504`
- `0x18000a9e4`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180001575`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180001575`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x180001548`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x180001548`
- `ntoskrnl!RtlValidSid` at `0x180001514`
- `ntoskrnl!RtlValidSid` at `0x180001514`

## pseudocode

```c
NTSTATUS __fastcall appv::shared::kernel::ConvertSid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
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
    v5 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
           a2,
           UnicodeString.Buffer,
           (unsigned __int64)UnicodeString.Length >> 1);
    RtlFreeUnicodeString(&UnicodeString);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180001504  mov     [rsp+arg_0], rbx
0x180001509  push    rdi
0x18000150a  sub     rsp, 30h
0x18000150e  mov     rdi, rdx
0x180001511  mov     rbx, rcx
0x180001514  call    cs:__imp_RtlValidSid
0x18000151b  nop     dword ptr [rax+rax+00h]
0x180001520  test    al, al
0x180001522  jnz     short loc_18000152B
0x180001524  mov     eax, 0C000000Dh
0x180001529  jmp     short loc_180001583
0x18000152b  mov     r8b, 1; AllocateDestinationString
0x18000152e  mov     qword ptr [rsp+38h+UnicodeString.Length], 0
0x180001537  mov     rdx, rbx; Sid
0x18000153a  mov     [rsp+38h+UnicodeString.Buffer], 0
0x180001543  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x180001548  call    cs:__imp_RtlConvertSidToUnicodeString
0x18000154f  nop     dword ptr [rax+rax+00h]
0x180001554  test    eax, eax
0x180001556  js      short loc_180001583
0x180001558  movzx   r8d, [rsp+38h+UnicodeString.Length]
0x18000155e  mov     rcx, rdi
0x180001561  mov     rdx, [rsp+38h+UnicodeString.Buffer]
0x180001566  shr     r8, 1
0x180001569  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18000156e  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x180001573  mov     ebx, eax
0x180001575  call    cs:__imp_RtlFreeUnicodeString
0x18000157c  nop     dword ptr [rax+rax+00h]
0x180001581  mov     eax, ebx
0x180001583  mov     rbx, [rsp+38h+arg_0]
0x180001588  add     rsp, 30h
0x18000158c  pop     rdi
0x18000158d  retn
```
