# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_mappings(appv::shared::kernel::handle const &,wchar_t const *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &)

- ea: `0x180014d1c`
- end: `0x180015002`
- name: `?store_mappings@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@PEB_WAEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@345@@Z`
- size: `742`
- prototype: `__int64 __fastcall(__int64 *, void *, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180015154`
- `0x1800153c8`

## callees

- `0x18000b350`
- `0x18000b420`
- `0x18000b478`
- `0x18000e23c`
- `0x18000e8d4`
- `0x18000f994`
- `0x180014700`
- `0x180014d1c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180014d77`
- `ntoskrnl!ExFreePoolWithTag` at `0x180014fe1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180014d77`
- `ntoskrnl!ExFreePoolWithTag` at `0x180014fe1`
- `ntoskrnl!ZwClose` at `0x180014dd1`
- `ntoskrnl!ZwClose` at `0x180014e0a`
- `ntoskrnl!ZwClose` at `0x180014f5f`
- `ntoskrnl!ZwClose` at `0x180014f7f`
- `ntoskrnl!ZwClose` at `0x180014fa1`
- `ntoskrnl!ZwClose` at `0x180014fc6`
- `ntoskrnl!ZwClose` at `0x180014dd1`
- `ntoskrnl!ZwClose` at `0x180014e0a`
- `ntoskrnl!ZwClose` at `0x180014f5f`
- `ntoskrnl!ZwClose` at `0x180014f7f`
- `ntoskrnl!ZwClose` at `0x180014fa1`
- `ntoskrnl!ZwClose` at `0x180014fc6`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x180014e42`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x180014e42`

## string_xrefs

- `0x180014d8e`: `CopyOnWriteMappings`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_mappings(
        __int64 *a1,
        void *a2,
        __int64 a3)
{
  int v6; // edi
  PVOID v7; // rcx
  PVOID v8; // r14
  void *v9; // rcx
  HANDLE v10; // rcx
  int v11; // r15d
  HANDLE v12; // rcx
  __int64 *v13; // rsi
  __int64 *v14; // r13
  HANDLE v15; // rbx
  ULONG v16; // r12d
  HANDLE v17; // rdi
  __int64 v18; // [rsp+20h] [rbp-28h] BYREF
  PVOID P; // [rsp+28h] [rbp-20h]
  struct _UNICODE_STRING String; // [rsp+30h] [rbp-18h] BYREF
  HANDLE Handle; // [rsp+98h] [rbp+50h] BYREF

  Handle = a2;
  if ( !*(_DWORD *)a3 )
    return 0;
  v18 = 0;
  P = 0;
  String = 0;
  v6 = appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(
         (unsigned int *)&v18,
         0x14u);
  if ( v6 < 0 )
  {
    v7 = P;
    if ( !P )
      return (unsigned int)v6;
LABEL_5:
    ExFreePoolWithTag(v7, 0);
    return (unsigned int)v6;
  }
  v8 = P;
  v9 = (void *)*a1;
  String.Buffer = (wchar_t *)P;
  *(_DWORD *)&String.Length = 1310740;
  Handle = 0;
  if ( registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
         v9,
         (__int64)L"CopyOnWriteMappings",
         &Handle) >= 0 )
  {
    v6 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(
           *a1,
           L"CopyOnWriteMappings");
    if ( v6 < 0 )
    {
      v10 = Handle;
      if ( Handle )
LABEL_10:
        ZwClose(v10);
LABEL_11:
      if ( !v8 )
        return (unsigned int)v6;
      v7 = v8;
      goto LABEL_5;
    }
  }
  v11 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
          (void *)*a1,
          L"CopyOnWriteMappings",
          &Handle);
  if ( v11 >= 0 )
  {
    v13 = *(__int64 **)(a3 + 32);
    v14 = (__int64 *)(a3 + 8);
    v15 = Handle;
    v16 = 1;
    while ( v13 != v14 )
    {
      v6 = RtlIntegerToUnicodeString(v16, 0xAu, &String);
      if ( v6 < 0 )
        goto LABEL_36;
      Handle = 0;
      v6 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
             v15,
             &String,
             &Handle);
      if ( v6 < 0 )
      {
        if ( Handle )
          ZwClose(Handle);
LABEL_36:
        if ( !v15 )
          goto LABEL_11;
        v10 = v15;
        goto LABEL_10;
      }
      v17 = Handle;
      v11 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
              Handle,
              L"Flags",
              *(_DWORD *)(*v13 + 192));
      if ( v11 < 0
        || (v11 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
                    v17,
                    L"SourceVolumeName",
                    *v13),
            v11 < 0)
        || (v11 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
                    v17,
                    L"SourceLongName",
                    *v13 + 32),
            v11 < 0)
        || (v11 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
                    v17,
                    L"SourceShortName",
                    *v13 + 64),
            v11 < 0)
        || (v11 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
                    v17,
                    L"TargetVolumeName",
                    *v13 + 96),
            v11 < 0)
        || (v11 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
                    v17,
                    L"TargetLongName",
                    *v13 + 128),
            v11 < 0)
        || (v11 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
                    v17,
                    L"TargetShortName",
                    *v13 + 160),
            v11 < 0) )
      {
        if ( v17 )
          ZwClose(v17);
        if ( v15 )
        {
          v12 = v15;
          goto LABEL_15;
        }
        goto LABEL_41;
      }
      if ( v17 )
        ZwClose(v17);
      v13 = (__int64 *)v13[3];
      ++v16;
    }
    if ( v15 )
      ZwClose(v15);
    if ( !v8 )
      return (unsigned int)v11;
  }
  else
  {
    v12 = Handle;
    if ( Handle )
LABEL_15:
      ZwClose(v12);
  }
LABEL_41:
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180014d1c  mov     [rsp-40h+Handle], rdx
0x180014d21  push    rbp
0x180014d22  push    rbx
0x180014d23  push    rsi
0x180014d24  push    rdi
0x180014d25  push    r12
0x180014d27  push    r13
0x180014d29  push    r14
0x180014d2b  push    r15
0x180014d2d  mov     rbp, rsp
0x180014d30  sub     rsp, 48h
0x180014d34  xor     r12d, r12d
0x180014d37  mov     rbx, r8
0x180014d3a  mov     rsi, rcx
0x180014d3d  cmp     [r8], r12d
0x180014d40  jnz     short loc_180014D49
0x180014d42  xor     eax, eax
0x180014d44  jmp     loc_180014FF0
0x180014d49  xorps   xmm0, xmm0
0x180014d4c  mov     [rbp+var_28], r12
0x180014d50  mov     edx, 14h
0x180014d55  mov     [rbp+P], r12
0x180014d59  lea     rcx, [rbp+var_28]
0x180014d5d  movups  xmmword ptr [rbp+String.Length], xmm0
0x180014d61  call    ?resize@?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(ulong)
0x180014d66  mov     edi, eax
0x180014d68  test    eax, eax
0x180014d6a  jns     short loc_180014D8A
0x180014d6c  mov     rcx, [rbp+P]; P
0x180014d70  test    rcx, rcx
0x180014d73  jz      short loc_180014D83
0x180014d75  xor     edx, edx; Tag
0x180014d77  call    cs:__imp_ExFreePoolWithTag
0x180014d7e  nop     dword ptr [rax+rax+00h]
0x180014d83  mov     eax, edi
0x180014d85  jmp     loc_180014FF0
0x180014d8a  mov     r14, [rbp+P]
0x180014d8e  lea     r15, aCopyonwritemap; "CopyOnWriteMappings"
0x180014d95  mov     rcx, [rsi]
0x180014d98  lea     r8, [rbp+Handle]
0x180014d9c  mov     rdx, r15
0x180014d9f  mov     [rbp+String.Buffer], r14
0x180014da3  mov     dword ptr [rbp+String.Length], 140014h
0x180014daa  mov     [rbp+Handle], r12
0x180014dae  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180014db3  test    eax, eax
0x180014db5  js      short loc_180014DE7
0x180014db7  mov     rcx, [rsi]
0x180014dba  mov     rdx, r15
0x180014dbd  call    ?delete_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W_N@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(void *,wchar_t const *,bool)
0x180014dc2  mov     edi, eax
0x180014dc4  test    eax, eax
0x180014dc6  jns     short loc_180014DE7
0x180014dc8  mov     rcx, [rbp+Handle]; Handle
0x180014dcc  test    rcx, rcx
0x180014dcf  jz      short loc_180014DDD
0x180014dd1  call    cs:__imp_ZwClose
0x180014dd8  nop     dword ptr [rax+rax+00h]
0x180014ddd  test    r14, r14
0x180014de0  jz      short loc_180014D83
0x180014de2  mov     rcx, r14
0x180014de5  jmp     short loc_180014D75
0x180014de7  mov     rcx, [rsi]
0x180014dea  lea     r8, [rbp+Handle]
0x180014dee  mov     rdx, r15
0x180014df1  call    ?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,wchar_t const *,appv::shared::kernel::handle &)
0x180014df6  mov     r15d, eax
0x180014df9  test    eax, eax
0x180014dfb  jns     short loc_180014E1B
0x180014dfd  mov     rcx, [rbp+Handle]; Handle
0x180014e01  test    rcx, rcx
0x180014e04  jz      loc_180014FD7
0x180014e0a  call    cs:__imp_ZwClose
0x180014e11  nop     dword ptr [rax+rax+00h]
0x180014e16  jmp     loc_180014FD7
0x180014e1b  mov     rsi, [rbx+20h]
0x180014e1f  lea     r13, [rbx+8]
0x180014e23  mov     rbx, [rbp+Handle]
0x180014e27  mov     r12d, 1
0x180014e2d  cmp     rsi, r13
0x180014e30  jz      loc_180014FBE
0x180014e36  lea     r8, [rbp+String]; String
0x180014e3a  mov     edx, 0Ah; Base
0x180014e3f  mov     ecx, r12d; Value
0x180014e42  call    cs:__imp_RtlIntegerToUnicodeString
0x180014e49  nop     dword ptr [rax+rax+00h]
0x180014e4e  mov     edi, eax
0x180014e50  test    eax, eax
0x180014e52  js      loc_180014FAD
0x180014e58  lea     r8, [rbp+Handle]
0x180014e5c  mov     [rbp+Handle], 0
0x180014e64  lea     rdx, [rbp+String]
0x180014e68  mov     rcx, rbx
0x180014e6b  call    ?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEBU_UNICODE_STRING@@AEAVhandle@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,_UNICODE_STRING const &,appv::shared::kernel::handle &)
0x180014e70  mov     edi, eax
0x180014e72  test    eax, eax
0x180014e74  js      loc_180014F98
0x180014e7a  mov     r8, [rsi]
0x180014e7d  lea     rdx, aFlags; "Flags"
0x180014e84  mov     rdi, [rbp+Handle]
0x180014e88  mov     rcx, rdi; KeyHandle
0x180014e8b  mov     r8d, [r8+0C0h]
0x180014e92  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,ulong)
0x180014e97  mov     r15d, eax
0x180014e9a  test    eax, eax
0x180014e9c  js      loc_180014F77
0x180014ea2  mov     r8, [rsi]
0x180014ea5  lea     rdx, aSourcevolumena; "SourceVolumeName"
0x180014eac  mov     rcx, rdi; KeyHandle
0x180014eaf  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x180014eb4  mov     r15d, eax
0x180014eb7  test    eax, eax
0x180014eb9  js      loc_180014F77
0x180014ebf  mov     r8, [rsi]
0x180014ec2  lea     rdx, aSourcelongname; "SourceLongName"
0x180014ec9  add     r8, 20h ; ' '
0x180014ecd  mov     rcx, rdi; KeyHandle
0x180014ed0  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x180014ed5  mov     r15d, eax
0x180014ed8  test    eax, eax
0x180014eda  js      loc_180014F77
0x180014ee0  mov     r8, [rsi]
0x180014ee3  lea     rdx, aSourceshortnam; "SourceShortName"
0x180014eea  add     r8, 40h ; '@'
0x180014eee  mov     rcx, rdi; KeyHandle
0x180014ef1  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x180014ef6  mov     r15d, eax
0x180014ef9  test    eax, eax
0x180014efb  js      short loc_180014F77
0x180014efd  mov     r8, [rsi]
0x180014f00  lea     rdx, aTargetvolumena; "TargetVolumeName"
0x180014f07  add     r8, 60h ; '`'
0x180014f0b  mov     rcx, rdi; KeyHandle
0x180014f0e  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x180014f13  mov     r15d, eax
0x180014f16  test    eax, eax
0x180014f18  js      short loc_180014F77
0x180014f1a  mov     r8, [rsi]
0x180014f1d  lea     rdx, aTargetlongname; "TargetLongName"
0x180014f24  sub     r8, 0FFFFFFFFFFFFFF80h
0x180014f28  mov     rcx, rdi; KeyHandle
0x180014f2b  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x180014f30  mov     r15d, eax
0x180014f33  test    eax, eax
0x180014f35  js      short loc_180014F77
0x180014f37  mov     r8, [rsi]
0x180014f3a  lea     rdx, aTargetshortnam; "TargetShortName"
0x180014f41  add     r8, 0A0h
0x180014f48  mov     rcx, rdi; KeyHandle
0x180014f4b  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x180014f50  mov     r15d, eax
0x180014f53  test    eax, eax
0x180014f55  js      short loc_180014F77
0x180014f57  test    rdi, rdi
0x180014f5a  jz      short loc_180014F6B
0x180014f5c  mov     rcx, rdi; Handle
0x180014f5f  call    cs:__imp_ZwClose
0x180014f66  nop     dword ptr [rax+rax+00h]
0x180014f6b  mov     rsi, [rsi+18h]
0x180014f6f  inc     r12d
0x180014f72  jmp     loc_180014E2D
0x180014f77  test    rdi, rdi
0x180014f7a  jz      short loc_180014F8B
0x180014f7c  mov     rcx, rdi; Handle
0x180014f7f  call    cs:__imp_ZwClose
0x180014f86  nop     dword ptr [rax+rax+00h]
0x180014f8b  test    rbx, rbx
0x180014f8e  jz      short loc_180014FD7
0x180014f90  mov     rcx, rbx
0x180014f93  jmp     loc_180014E0A
0x180014f98  mov     rcx, [rbp+Handle]; Handle
0x180014f9c  test    rcx, rcx
0x180014f9f  jz      short loc_180014FAD
0x180014fa1  call    cs:__imp_ZwClose
0x180014fa8  nop     dword ptr [rax+rax+00h]
0x180014fad  test    rbx, rbx
0x180014fb0  jz      loc_180014DDD
0x180014fb6  mov     rcx, rbx
0x180014fb9  jmp     loc_180014DD1
0x180014fbe  test    rbx, rbx
0x180014fc1  jz      short loc_180014FD2
0x180014fc3  mov     rcx, rbx; Handle
0x180014fc6  call    cs:__imp_ZwClose
0x180014fcd  nop     dword ptr [rax+rax+00h]
0x180014fd2  test    r14, r14
0x180014fd5  jz      short loc_180014FED
0x180014fd7  test    r14, r14
0x180014fda  jz      short loc_180014FED
0x180014fdc  xor     edx, edx; Tag
0x180014fde  mov     rcx, r14; P
0x180014fe1  call    cs:__imp_ExFreePoolWithTag
0x180014fe8  nop     dword ptr [rax+rax+00h]
0x180014fed  mov     eax, r15d
0x180014ff0  add     rsp, 48h
0x180014ff4  pop     r15
0x180014ff6  pop     r14
0x180014ff8  pop     r13
0x180014ffa  pop     r12
0x180014ffc  pop     rdi
0x180014ffd  pop     rsi
0x180014ffe  pop     rbx
0x180014fff  pop     rbp
0x180015000  retn
```
