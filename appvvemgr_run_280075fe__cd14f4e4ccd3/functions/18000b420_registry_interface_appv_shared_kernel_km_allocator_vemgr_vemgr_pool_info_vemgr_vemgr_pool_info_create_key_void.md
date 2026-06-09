# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,wchar_t const *,appv::shared::kernel::handle &)

- ea: `0x18000b420`
- end: `0x18000b471`
- name: `?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@@Z`
- size: `81`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e354`
- `0x18000fa58`
- `0x1800137f8`
- `0x180014acc`
- `0x180014d1c`
- `0x180015008`
- `0x180015154`
- `0x180015278`
- `0x1800153c8`

## callees

- `0x18000b350`
- `0x18000b420`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18000b449`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000b449`

## pseudocode

```c
NTSTATUS __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
        void *a1,
        const WCHAR *a2,
        HANDLE *a3)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  if ( !a2 )
    return -1073741811;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  return registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
           a1,
           &DestinationString,
           a3);
}

```

## disassembly

```asm
0x18000b420  mov     [rsp+arg_0], rbx
0x18000b425  push    rdi
0x18000b426  sub     rsp, 30h
0x18000b42a  mov     rbx, r8
0x18000b42d  mov     rdi, rcx
0x18000b430  test    rdx, rdx
0x18000b433  jnz     short loc_18000B43C
0x18000b435  mov     eax, 0C000000Dh
0x18000b43a  jmp     short loc_18000B465
0x18000b43c  xorps   xmm0, xmm0
0x18000b43f  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x18000b444  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x18000b449  call    cs:__imp_RtlInitUnicodeString
0x18000b450  nop     dword ptr [rax+rax+00h]
0x18000b455  mov     r8, rbx
0x18000b458  lea     rdx, [rsp+38h+DestinationString]
0x18000b45d  mov     rcx, rdi
0x18000b460  call    ?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEBU_UNICODE_STRING@@AEAVhandle@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,_UNICODE_STRING const &,appv::shared::kernel::handle &)
0x18000b465  mov     rbx, [rsp+38h+arg_0]
0x18000b46a  add     rsp, 30h
0x18000b46e  pop     rdi
0x18000b46f  retn
```
