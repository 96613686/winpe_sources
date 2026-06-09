# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_package(wchar_t const *)

- ea: `0x1800141d0`
- end: `0x180014330`
- name: `?remove_package@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W@Z`
- size: `352`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800101e4`
- `0x1800147fc`

## callees

- `0x18000b478`
- `0x18000e23c`
- `0x180013af0`
- `0x1800141d0`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18001420c`
- `ntoskrnl!ZwClose` at `0x180014254`
- `ntoskrnl!ZwClose` at `0x180014268`
- `ntoskrnl!ZwClose` at `0x1800142e7`
- `ntoskrnl!ZwClose` at `0x1800142fe`
- `ntoskrnl!ZwClose` at `0x180014312`
- `ntoskrnl!ZwClose` at `0x18001420c`
- `ntoskrnl!ZwClose` at `0x180014254`
- `ntoskrnl!ZwClose` at `0x180014268`
- `ntoskrnl!ZwClose` at `0x1800142e7`
- `ntoskrnl!ZwClose` at `0x1800142fe`
- `ntoskrnl!ZwClose` at `0x180014312`

## string_xrefs

- `0x1800141f1`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\MAV\Configuration\Packages`
- `0x180014287`: `UserConfigEx`
- `0x1800142ba`: `Data_Store::remove_package() - Removing package %s. Package has not been unpublished.`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_package(
        __int64 a1)
{
  NTSTATUS v2; // ebx
  HANDLE v4; // rbx
  NTSTATUS v5; // eax
  unsigned int v6; // edi
  NTSTATUS v7; // eax
  HANDLE v8; // rdi
  unsigned int v9; // r14d
  HANDLE Handle; // [rsp+48h] [rbp+28h] BYREF
  HANDLE v11; // [rsp+50h] [rbp+30h] BYREF

  Handle = 0;
  v2 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
         0,
         (__int64)L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\AppV\\MAV\\Configuration\\Packages",
         &Handle);
  if ( v2 >= 0 )
  {
    v4 = Handle;
    v11 = 0;
    v5 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
           Handle,
           a1,
           &v11);
    v6 = v5;
    if ( v5 >= 0 )
    {
      Handle = 0;
      v7 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
             v11,
             (__int64)L"UserConfigEx",
             &Handle);
      v8 = Handle;
      if ( v7 >= 0 )
      {
        LODWORD(Handle) = 0;
        if ( (int)registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_subkey_count(
                    v8,
                    &Handle) >= 0 )
        {
          if ( (_DWORD)Handle )
            LogWrite(3, 0, L"Data_Store::remove_package() - Removing package %s. Package has not been unpublished.", a1);
        }
      }
      v9 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(
             v11,
             &dword_18001E3EC);
      if ( v8 )
        ZwClose(v8);
      if ( v11 )
        ZwClose(v11);
      if ( v4 )
        ZwClose(v4);
      return v9;
    }
    else
    {
      if ( v5 == -1073741772 )
        v6 = 0;
      if ( v11 )
        ZwClose(v11);
      if ( v4 )
        ZwClose(v4);
      return v6;
    }
  }
  else
  {
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)v2;
  }
}

```

## disassembly

```asm
0x1800141d0  mov     [rsp-18h+arg_0], rbx
0x1800141d5  push    rbp
0x1800141d6  push    rdi
0x1800141d7  push    r14
0x1800141d9  mov     rbp, rsp
0x1800141dc  sub     rsp, 20h
0x1800141e0  mov     r14, rcx
0x1800141e3  mov     [rbp+Handle], 0
0x1800141eb  xor     ecx, ecx
0x1800141ed  lea     r8, [rbp+Handle]
0x1800141f1  lea     rdx, aRegistryMachin_4; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x1800141f8  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x1800141fd  mov     ebx, eax
0x1800141ff  test    eax, eax
0x180014201  jns     short loc_18001421F
0x180014203  mov     rcx, [rbp+Handle]; Handle
0x180014207  test    rcx, rcx
0x18001420a  jz      short loc_180014218
0x18001420c  call    cs:__imp_ZwClose
0x180014213  nop     dword ptr [rax+rax+00h]
0x180014218  mov     eax, ebx
0x18001421a  jmp     loc_180014321
0x18001421f  mov     rbx, [rbp+Handle]
0x180014223  lea     r8, [rbp+arg_10]
0x180014227  mov     rcx, rbx
0x18001422a  mov     [rbp+arg_10], 0
0x180014232  mov     rdx, r14
0x180014235  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18001423a  mov     rcx, [rbp+arg_10]; Handle
0x18001423e  mov     edi, eax
0x180014240  test    eax, eax
0x180014242  jns     short loc_18001427B
0x180014244  xor     eax, eax
0x180014246  cmp     edi, 0C0000034h
0x18001424c  cmovz   edi, eax
0x18001424f  test    rcx, rcx
0x180014252  jz      short loc_180014260
0x180014254  call    cs:__imp_ZwClose
0x18001425b  nop     dword ptr [rax+rax+00h]
0x180014260  test    rbx, rbx
0x180014263  jz      short loc_180014274
0x180014265  mov     rcx, rbx; Handle
0x180014268  call    cs:__imp_ZwClose
0x18001426f  nop     dword ptr [rax+rax+00h]
0x180014274  mov     eax, edi
0x180014276  jmp     loc_180014321
0x18001427b  lea     r8, [rbp+Handle]
0x18001427f  mov     [rbp+Handle], 0
0x180014287  lea     rdx, aUserconfigex; "UserConfigEx"
0x18001428e  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180014293  mov     rdi, [rbp+Handle]
0x180014297  test    eax, eax
0x180014299  js      short loc_1800142CC
0x18001429b  lea     rdx, [rbp+Handle]
0x18001429f  mov     dword ptr [rbp+Handle], 0
0x1800142a6  mov     rcx, rdi
0x1800142a9  call    ?get_subkey_count@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEAK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_subkey_count(void *,ulong &)
0x1800142ae  test    eax, eax
0x1800142b0  js      short loc_1800142CC
0x1800142b2  cmp     dword ptr [rbp+Handle], 0
0x1800142b6  jbe     short loc_1800142CC
0x1800142b8  xor     edx, edx
0x1800142ba  lea     r8, aDataStoreRemov_1; "Data_Store::remove_package() - Removing"...
0x1800142c1  mov     r9, r14
0x1800142c4  lea     ecx, [rdx+3]
0x1800142c7  call    LogWrite
0x1800142cc  mov     rcx, [rbp+arg_10]
0x1800142d0  lea     rdx, dword_18001E3EC
0x1800142d7  call    ?delete_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W_N@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(void *,wchar_t const *,bool)
0x1800142dc  mov     r14d, eax
0x1800142df  test    rdi, rdi
0x1800142e2  jz      short loc_1800142F3
0x1800142e4  mov     rcx, rdi; Handle
0x1800142e7  call    cs:__imp_ZwClose
0x1800142ee  nop     dword ptr [rax+rax+00h]
0x1800142f3  cmp     [rbp+arg_10], 0
0x1800142f8  jz      short loc_18001430A
0x1800142fa  mov     rcx, [rbp+arg_10]; Handle
0x1800142fe  call    cs:__imp_ZwClose
0x180014305  nop     dword ptr [rax+rax+00h]
0x18001430a  test    rbx, rbx
0x18001430d  jz      short loc_18001431E
0x18001430f  mov     rcx, rbx; Handle
0x180014312  call    cs:__imp_ZwClose
0x180014319  nop     dword ptr [rax+rax+00h]
0x18001431e  mov     eax, r14d
0x180014321  mov     rbx, [rsp+20h+arg_0]
0x180014326  add     rsp, 20h
0x18001432a  pop     r14
0x18001432c  pop     rdi
0x18001432d  pop     rbp
0x18001432e  retn
```
