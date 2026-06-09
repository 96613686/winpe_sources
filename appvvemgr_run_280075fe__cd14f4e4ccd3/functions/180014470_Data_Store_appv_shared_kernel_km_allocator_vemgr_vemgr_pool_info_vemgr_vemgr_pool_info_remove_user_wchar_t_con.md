# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_user(wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x180014470`
- end: `0x1800145a2`
- name: `?remove_user@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W00@Z`
- size: `306`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800105f4`
- `0x180014acc`

## callees

- `0x18000a864`
- `0x18000a958`
- `0x18000b478`
- `0x18000e354`
- `0x180014470`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800144f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x180014576`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800144f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x180014576`
- `ntoskrnl!ZwClose` at `0x1800144a6`
- `ntoskrnl!ZwClose` at `0x18001458a`
- `ntoskrnl!ZwClose` at `0x1800144a6`
- `ntoskrnl!ZwClose` at `0x18001458a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800144c7`
- `ntoskrnl!RtlInitUnicodeString` at `0x180014514`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800144c7`
- `ntoskrnl!RtlInitUnicodeString` at `0x180014514`

## string_xrefs

- `0x1800144d3`: `UserConfigEx`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_user(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  int v4; // ebx
  PVOID v6; // rdx
  HANDLE v7; // rbx
  unsigned int v8; // edi
  struct _UNICODE_STRING v9; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+30h] [rbp-28h] BYREF
  PVOID P; // [rsp+38h] [rbp-20h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF
  HANDLE Handle; // [rsp+98h] [rbp+40h] BYREF

  Handle = 0;
  v4 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(
         &Handle,
         a1,
         a2,
         0);
  if ( v4 < 0 )
  {
LABEL_2:
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)v4;
  }
  v10 = 0;
  P = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v4 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
         &v10,
         L"UserConfigEx");
  if ( v4 < 0
    || (v9 = 0,
        RtlInitUnicodeString(&v9, L"\\"),
        v4 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
               &v10,
               &v9),
        v4 < 0)
    || (v4 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
               &v10,
               a3),
        v4 < 0) )
  {
    if ( P )
      ExFreePoolWithTag(P, 0);
    goto LABEL_2;
  }
  if ( (unsigned int)v10 >> 1 > 0xFFFF || (v6 = P, !(unsigned __int16)((unsigned int)v10 >> 1)) )
    v6 = 0;
  v7 = Handle;
  v8 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(
         Handle,
         v6);
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v7 )
    ZwClose(v7);
  return v8;
}

```

## disassembly

```asm
0x180014470  push    rbp
0x180014472  push    rbx
0x180014473  push    rsi
0x180014474  push    rdi
0x180014475  mov     rbp, rsp
0x180014478  sub     rsp, 58h
0x18001447c  mov     rdi, r8
0x18001447f  xor     esi, esi
0x180014481  mov     r8, rdx
0x180014484  mov     [rbp+Handle], rsi
0x180014488  mov     rdx, rcx
0x18001448b  xor     r9d, r9d
0x18001448e  lea     rcx, [rbp+Handle]
0x180014492  call    ?open_package_key@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEAVhandle@kernel@shared@appv@@PEB_W1_N@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(appv::shared::kernel::handle &,wchar_t const *,wchar_t const *,bool)
0x180014497  mov     ebx, eax
0x180014499  test    eax, eax
0x18001449b  jns     short loc_1800144B9
0x18001449d  mov     rcx, [rbp+Handle]; Handle
0x1800144a1  test    rcx, rcx
0x1800144a4  jz      short loc_1800144B2
0x1800144a6  call    cs:__imp_ZwClose
0x1800144ad  nop     dword ptr [rax+rax+00h]
0x1800144b2  mov     eax, ebx
0x1800144b4  jmp     loc_180014598
0x1800144b9  xor     edx, edx; SourceString
0x1800144bb  mov     [rbp+var_28], rsi
0x1800144bf  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800144c3  mov     [rbp+P], rsi
0x1800144c7  call    cs:__imp_RtlInitUnicodeString
0x1800144ce  nop     dword ptr [rax+rax+00h]
0x1800144d3  lea     rdx, aUserconfigex; "UserConfigEx"
0x1800144da  lea     rcx, [rbp+var_28]
0x1800144de  call    ?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJPEB_W@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(wchar_t const *)
0x1800144e3  mov     ebx, eax
0x1800144e5  test    eax, eax
0x1800144e7  jns     short loc_180014502
0x1800144e9  mov     rcx, [rbp+P]; P
0x1800144ed  test    rcx, rcx
0x1800144f0  jz      short loc_18001449D
0x1800144f2  xor     edx, edx; Tag
0x1800144f4  call    cs:__imp_ExFreePoolWithTag
0x1800144fb  nop     dword ptr [rax+rax+00h]
0x180014500  jmp     short loc_18001449D
0x180014502  xorps   xmm0, xmm0
0x180014505  lea     rdx, asc_18002108C; "\\"
0x18001450c  lea     rcx, [rbp+var_38]; DestinationString
0x180014510  movups  xmmword ptr [rbp+var_38.Length], xmm0
0x180014514  call    cs:__imp_RtlInitUnicodeString
0x18001451b  nop     dword ptr [rax+rax+00h]
0x180014520  lea     rdx, [rbp+var_38]
0x180014524  lea     rcx, [rbp+var_28]
0x180014528  call    ?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(_UNICODE_STRING const &)
0x18001452d  mov     ebx, eax
0x18001452f  test    eax, eax
0x180014531  js      short loc_1800144E9
0x180014533  mov     rdx, rdi
0x180014536  lea     rcx, [rbp+var_28]
0x18001453a  call    ?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJPEB_W@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(wchar_t const *)
0x18001453f  mov     ebx, eax
0x180014541  test    eax, eax
0x180014543  js      short loc_1800144E9
0x180014545  mov     eax, dword ptr [rbp+var_28]
0x180014548  shr     eax, 1
0x18001454a  cmp     eax, 0FFFFh
0x18001454f  ja      short loc_18001455A
0x180014551  mov     rdx, [rbp+P]
0x180014555  test    ax, ax
0x180014558  jnz     short loc_18001455D
0x18001455a  mov     rdx, rsi
0x18001455d  mov     rbx, [rbp+Handle]
0x180014561  mov     rcx, rbx
0x180014564  call    ?delete_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W_N@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(void *,wchar_t const *,bool)
0x180014569  mov     rcx, [rbp+P]; P
0x18001456d  mov     edi, eax
0x18001456f  test    rcx, rcx
0x180014572  jz      short loc_180014582
0x180014574  xor     edx, edx; Tag
0x180014576  call    cs:__imp_ExFreePoolWithTag
0x18001457d  nop     dword ptr [rax+rax+00h]
0x180014582  test    rbx, rbx
0x180014585  jz      short loc_180014596
0x180014587  mov     rcx, rbx; Handle
0x18001458a  call    cs:__imp_ZwClose
0x180014591  nop     dword ptr [rax+rax+00h]
0x180014596  mov     eax, edi
0x180014598  add     rsp, 58h
0x18001459c  pop     rdi
0x18001459d  pop     rsi
0x18001459e  pop     rbx
0x18001459f  pop     rbp
0x1800145a0  retn
```
