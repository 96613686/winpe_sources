# appv::shared::kernel::SidFromToken<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,uchar *)

- ea: `0x180002d7c`
- end: `0x180002e8c`
- name: `??$SidFromToken@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@012@PEAE@Z`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x180002cb4`

## callees

- `0x180001504`
- `0x180002d7c`
- `0x18001baf0`

## import_xrefs

- `ntoskrnl!ZwQueryInformationToken` at `0x180002dc6`
- `ntoskrnl!ZwQueryInformationToken` at `0x180002dc6`
- `ntoskrnl!RtlEqualSid` at `0x180002dfd`
- `ntoskrnl!RtlEqualSid` at `0x180002e21`
- `ntoskrnl!RtlEqualSid` at `0x180002e45`
- `ntoskrnl!RtlEqualSid` at `0x180002dfd`
- `ntoskrnl!RtlEqualSid` at `0x180002e21`
- `ntoskrnl!RtlEqualSid` at `0x180002e45`
- `ntoskrnl!SeExports` at `0x180002de9`
- `ntoskrnl!SeExports` at `0x180002e0d`
- `ntoskrnl!SeExports` at `0x180002e31`

## pseudocode

```c
NTSTATUS __fastcall appv::shared::kernel::SidFromToken<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        void *a1,
        __int64 a2,
        char *a3)
{
  char v4; // di
  NTSTATUS result; // eax
  PSID v6; // rbx
  ULONG ReturnLength[4]; // [rsp+30h] [rbp-98h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-88h] BYREF

  ReturnLength[0] = 0;
  v4 = 1;
  result = ZwQueryInformationToken(a1, TokenUser, TokenInformation, 0x54u, ReturnLength);
  if ( result >= 0 )
  {
    if ( a3 )
    {
      v6 = TokenInformation[0];
      if ( !TokenInformation[0]
        || !RtlEqualSid(SeExports->SeLocalSystemSid, TokenInformation[0])
        && !RtlEqualSid(SeExports->SeLocalServiceSid, v6)
        && !RtlEqualSid(SeExports->SeNetworkServiceSid, v6) )
      {
        v4 = 0;
      }
      *a3 = v4;
    }
    return appv::shared::kernel::ConvertSid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(TokenInformation[0]);
  }
  return result;
}

```

## disassembly

```asm
0x180002d7c  mov     [rsp+arg_18], rbx
0x180002d81  push    rbp
0x180002d82  push    rsi
0x180002d83  push    rdi
0x180002d84  sub     rsp, 0B0h
0x180002d8b  mov     rax, cs:__security_cookie
0x180002d92  xor     rax, rsp
0x180002d95  mov     [rsp+0C8h+var_28], rax
0x180002d9d  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180002da3  mov     [rsp+0C8h+var_98], 0
0x180002dab  mov     rsi, r8
0x180002dae  lea     rax, [rsp+0C8h+var_98]
0x180002db3  mov     rbp, rdx
0x180002db6  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x180002dbb  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x180002dc0  lea     edi, [r9-53h]
0x180002dc4  mov     edx, edi; TokenInformationClass
0x180002dc6  call    cs:__imp_ZwQueryInformationToken
0x180002dcd  nop     dword ptr [rax+rax+00h]
0x180002dd2  test    eax, eax
0x180002dd4  js      loc_180002E68
0x180002dda  test    rsi, rsi
0x180002ddd  jz      short loc_180002E5B
0x180002ddf  mov     rbx, [rsp+0C8h+TokenInformation]
0x180002de4  test    rbx, rbx
0x180002de7  jz      short loc_180002E55
0x180002de9  mov     rax, cs:__imp_SeExports
0x180002df0  mov     rdx, rbx; Sid2
0x180002df3  mov     rcx, [rax]
0x180002df6  mov     rcx, [rcx+108h]; Sid1
0x180002dfd  call    cs:__imp_RtlEqualSid
0x180002e04  nop     dword ptr [rax+rax+00h]
0x180002e09  test    al, al
0x180002e0b  jnz     short loc_180002E58
0x180002e0d  mov     rax, cs:__imp_SeExports
0x180002e14  mov     rdx, rbx; Sid2
0x180002e17  mov     rcx, [rax]
0x180002e1a  mov     rcx, [rcx+180h]; Sid1
0x180002e21  call    cs:__imp_RtlEqualSid
0x180002e28  nop     dword ptr [rax+rax+00h]
0x180002e2d  test    al, al
0x180002e2f  jnz     short loc_180002E58
0x180002e31  mov     rax, cs:__imp_SeExports
0x180002e38  mov     rdx, rbx; Sid2
0x180002e3b  mov     rcx, [rax]
0x180002e3e  mov     rcx, [rcx+188h]; Sid1
0x180002e45  call    cs:__imp_RtlEqualSid
0x180002e4c  nop     dword ptr [rax+rax+00h]
0x180002e51  test    al, al
0x180002e53  jnz     short loc_180002E58
0x180002e55  xor     dil, dil
0x180002e58  mov     [rsi], dil
0x180002e5b  mov     rcx, [rsp+0C8h+TokenInformation]; Sid
0x180002e60  mov     rdx, rbp
0x180002e63  call    ??$ConvertSid@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@012@@Z; appv::shared::kernel::ConvertSid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x180002e68  mov     rcx, [rsp+0C8h+var_28]
0x180002e70  xor     rcx, rsp; StackCookie
0x180002e73  call    __security_check_cookie
0x180002e78  mov     rbx, [rsp+0C8h+arg_18]
0x180002e80  add     rsp, 0B0h
0x180002e87  pop     rdi
0x180002e88  pop     rsi
0x180002e89  pop     rbp
0x180002e8a  retn
```
