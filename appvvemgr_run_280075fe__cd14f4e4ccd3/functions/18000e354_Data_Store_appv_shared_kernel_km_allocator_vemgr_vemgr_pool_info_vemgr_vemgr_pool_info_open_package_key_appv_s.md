# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(appv::shared::kernel::handle &,wchar_t const *,wchar_t const *,bool)

- ea: `0x18000e354`
- end: `0x18000e52c`
- name: `?open_package_key@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEAVhandle@kernel@shared@appv@@PEB_W1_N@Z`
- size: `472`
- prototype: ``
- caller_count: `10`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002b48`
- `0x18000d72c`
- `0x18000e960`
- `0x18000fe44`
- `0x180013718`
- `0x180013d4c`
- `0x180013f40`
- `0x180014470`
- `0x1800145a8`
- `0x180014acc`

## callees

- `0x18000a864`
- `0x18000a958`
- `0x18000b420`
- `0x18000e23c`
- `0x18000e354`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000e412`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000e4f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000e412`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000e4f0`
- `ntoskrnl!ZwClose` at `0x18000e3c3`
- `ntoskrnl!ZwClose` at `0x18000e427`
- `ntoskrnl!ZwClose` at `0x18000e504`
- `ntoskrnl!ZwClose` at `0x18000e3c3`
- `ntoskrnl!ZwClose` at `0x18000e427`
- `ntoskrnl!ZwClose` at `0x18000e504`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000e3e4`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000e457`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000e3e4`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000e457`

## string_xrefs

- `0x18000e39e`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\MAV\Configuration\Packages`
- `0x18000e390`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\MAV\Configuration\Groups`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(
        HANDLE *a1,
        __int64 a2,
        __int64 a3,
        char a4)
{
  const wchar_t *v9; // rdx
  NTSTATUS v10; // esi
  int v11; // ebx
  PVOID v12; // rdx
  HANDLE v13; // rbx
  unsigned int key; // edi
  PVOID v15; // rdx
  struct _UNICODE_STRING v16; // [rsp+20h] [rbp-30h] BYREF
  __int64 v17; // [rsp+30h] [rbp-20h] BYREF
  PVOID P; // [rsp+38h] [rbp-18h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+38h] BYREF

  if ( !a2 && !a3 )
    return 3221225485LL;
  Handle = 0;
  v9 = L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\AppV\\MAV\\Configuration\\Packages";
  if ( a3 )
    v9 = L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\AppV\\MAV\\Configuration\\Groups";
  v10 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
          0,
          (__int64)v9,
          &Handle);
  if ( v10 >= 0 )
  {
    v17 = 0;
    P = 0;
    RtlInitUnicodeString(&DestinationString, 0);
    if ( a3
      && (v11 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
                  &v17,
                  a3),
          v11 < 0)
      || a2
      && ((unsigned int)v17 > 2
       && (v16 = 0,
           RtlInitUnicodeString(&v16, L"\\"),
           v11 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
                   &v17,
                   &v16),
           v11 < 0)
       || (v11 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
                   &v17,
                   a2),
           v11 < 0)) )
    {
      if ( P )
        ExFreePoolWithTag(P, 0);
      if ( Handle )
        ZwClose(Handle);
      return (unsigned int)v11;
    }
    else
    {
      if ( (unsigned int)v17 >> 1 > 0xFFFF || (v12 = P, !(unsigned __int16)((unsigned int)v17 >> 1)) )
        v12 = 0;
      v13 = Handle;
      key = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
              Handle,
              (__int64)v12,
              a1);
      if ( key == -1073741772 && a4 )
      {
        if ( (unsigned int)v17 >> 1 > 0xFFFF || (v15 = P, !(unsigned __int16)((unsigned int)v17 >> 1)) )
          v15 = 0;
        key = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
                v13,
                v15,
                a1);
      }
      if ( P )
        ExFreePoolWithTag(P, 0);
      if ( v13 )
        ZwClose(v13);
      return key;
    }
  }
  else
  {
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x18000e354  mov     [rsp-28h+arg_0], rbx
0x18000e359  mov     [rsp-28h+arg_10], rsi
0x18000e35e  push    rbp
0x18000e35f  push    rdi
0x18000e360  push    r12
0x18000e362  push    r14
0x18000e364  push    r15
0x18000e366  mov     rbp, rsp
0x18000e369  sub     rsp, 50h
0x18000e36d  xor     r12d, r12d
0x18000e370  mov     r15b, r9b
0x18000e373  mov     rbx, r8
0x18000e376  mov     rdi, rdx
0x18000e379  mov     r14, rcx
0x18000e37c  test    rdx, rdx
0x18000e37f  jnz     short loc_18000E390
0x18000e381  test    rbx, rbx
0x18000e384  jnz     short loc_18000E390
0x18000e386  mov     eax, 0C000000Dh
0x18000e38b  jmp     loc_18000E512
0x18000e390  lea     rax, aRegistryMachin; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x18000e397  mov     [rbp+Handle], r12
0x18000e39b  test    rbx, rbx
0x18000e39e  lea     rdx, aRegistryMachin_4; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x18000e3a5  lea     r8, [rbp+Handle]
0x18000e3a9  cmovnz  rdx, rax
0x18000e3ad  xor     ecx, ecx
0x18000e3af  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18000e3b4  mov     esi, eax
0x18000e3b6  test    eax, eax
0x18000e3b8  jns     short loc_18000E3D6
0x18000e3ba  mov     rcx, [rbp+Handle]; Handle
0x18000e3be  test    rcx, rcx
0x18000e3c1  jz      short loc_18000E3CF
0x18000e3c3  call    cs:__imp_ZwClose
0x18000e3ca  nop     dword ptr [rax+rax+00h]
0x18000e3cf  mov     eax, esi
0x18000e3d1  jmp     loc_18000E512
0x18000e3d6  xor     edx, edx; SourceString
0x18000e3d8  mov     [rbp+var_20], r12
0x18000e3dc  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000e3e0  mov     [rbp+P], r12
0x18000e3e4  call    cs:__imp_RtlInitUnicodeString
0x18000e3eb  nop     dword ptr [rax+rax+00h]
0x18000e3f0  test    rbx, rbx
0x18000e3f3  jz      short loc_18000E43A
0x18000e3f5  mov     rdx, rbx
0x18000e3f8  lea     rcx, [rbp+var_20]
0x18000e3fc  call    ?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJPEB_W@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(wchar_t const *)
0x18000e401  mov     ebx, eax
0x18000e403  test    eax, eax
0x18000e405  jns     short loc_18000E43A
0x18000e407  mov     rcx, [rbp+P]; P
0x18000e40b  test    rcx, rcx
0x18000e40e  jz      short loc_18000E41E
0x18000e410  xor     edx, edx; Tag
0x18000e412  call    cs:__imp_ExFreePoolWithTag
0x18000e419  nop     dword ptr [rax+rax+00h]
0x18000e41e  mov     rcx, [rbp+Handle]; Handle
0x18000e422  test    rcx, rcx
0x18000e425  jz      short loc_18000E433
0x18000e427  call    cs:__imp_ZwClose
0x18000e42e  nop     dword ptr [rax+rax+00h]
0x18000e433  mov     eax, ebx
0x18000e435  jmp     loc_18000E512
0x18000e43a  test    rdi, rdi
0x18000e43d  jz      short loc_18000E48C
0x18000e43f  cmp     dword ptr [rbp+var_20], 2
0x18000e443  jbe     short loc_18000E476
0x18000e445  xorps   xmm0, xmm0
0x18000e448  lea     rdx, asc_18002108C; "\\"
0x18000e44f  lea     rcx, [rbp+var_30]; DestinationString
0x18000e453  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x18000e457  call    cs:__imp_RtlInitUnicodeString
0x18000e45e  nop     dword ptr [rax+rax+00h]
0x18000e463  lea     rdx, [rbp+var_30]
0x18000e467  lea     rcx, [rbp+var_20]
0x18000e46b  call    ?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(_UNICODE_STRING const &)
0x18000e470  mov     ebx, eax
0x18000e472  test    eax, eax
0x18000e474  js      short loc_18000E407
0x18000e476  mov     rdx, rdi
0x18000e479  lea     rcx, [rbp+var_20]
0x18000e47d  call    ?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJPEB_W@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(wchar_t const *)
0x18000e482  mov     ebx, eax
0x18000e484  test    eax, eax
0x18000e486  js      loc_18000E407
0x18000e48c  mov     eax, dword ptr [rbp+var_20]
0x18000e48f  mov     esi, 0FFFFh
0x18000e494  shr     eax, 1
0x18000e496  cmp     eax, esi
0x18000e498  ja      short loc_18000E4A3
0x18000e49a  mov     rdx, [rbp+P]
0x18000e49e  test    ax, ax
0x18000e4a1  jnz     short loc_18000E4A6
0x18000e4a3  mov     rdx, r12
0x18000e4a6  mov     rbx, [rbp+Handle]
0x18000e4aa  mov     r8, r14
0x18000e4ad  mov     rcx, rbx
0x18000e4b0  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18000e4b5  mov     edi, eax
0x18000e4b7  cmp     eax, 0C0000034h
0x18000e4bc  jnz     short loc_18000E4E5
0x18000e4be  test    r15b, r15b
0x18000e4c1  jz      short loc_18000E4E5
0x18000e4c3  mov     eax, dword ptr [rbp+var_20]
0x18000e4c6  shr     eax, 1
0x18000e4c8  cmp     eax, esi
0x18000e4ca  ja      short loc_18000E4D5
0x18000e4cc  mov     rdx, [rbp+P]
0x18000e4d0  test    ax, ax
0x18000e4d3  jnz     short loc_18000E4D8
0x18000e4d5  mov     rdx, r12
0x18000e4d8  mov     r8, r14
0x18000e4db  mov     rcx, rbx
0x18000e4de  call    ?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,wchar_t const *,appv::shared::kernel::handle &)
0x18000e4e3  mov     edi, eax
0x18000e4e5  mov     rcx, [rbp+P]; P
0x18000e4e9  test    rcx, rcx
0x18000e4ec  jz      short loc_18000E4FC
0x18000e4ee  xor     edx, edx; Tag
0x18000e4f0  call    cs:__imp_ExFreePoolWithTag
0x18000e4f7  nop     dword ptr [rax+rax+00h]
0x18000e4fc  test    rbx, rbx
0x18000e4ff  jz      short loc_18000E510
0x18000e501  mov     rcx, rbx; Handle
0x18000e504  call    cs:__imp_ZwClose
0x18000e50b  nop     dword ptr [rax+rax+00h]
0x18000e510  mov     eax, edi
0x18000e512  lea     r11, [rsp+50h+var_s0]
0x18000e517  mov     rbx, [r11+30h]
0x18000e51b  mov     rsi, [r11+40h]
0x18000e51f  mov     rsp, r11
0x18000e522  pop     r15
0x18000e524  pop     r14
0x18000e526  pop     r12
0x18000e528  pop     rdi
0x18000e529  pop     rbp
0x18000e52a  retn
```
