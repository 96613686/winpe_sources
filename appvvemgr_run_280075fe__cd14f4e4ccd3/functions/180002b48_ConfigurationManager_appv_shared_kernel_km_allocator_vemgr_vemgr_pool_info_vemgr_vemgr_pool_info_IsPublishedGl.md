# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedGlobally<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,bool &)

- ea: `0x180002b48`
- end: `0x180002cab`
- name: `??$IsPublishedGlobally@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0AEA_N@Z`
- size: `355`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180001d4c`
- `0x1800021d0`
- `0x180018b9c`

## callees

- `0x180002b48`
- `0x18000ce10`
- `0x18000e354`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x180002c79`
- `ntoskrnl!ExReleaseResourceLite` at `0x180002c79`
- `ntoskrnl!ZwClose` at `0x180002c14`
- `ntoskrnl!ZwClose` at `0x180002c5c`
- `ntoskrnl!ZwClose` at `0x180002c14`
- `ntoskrnl!ZwClose` at `0x180002c5c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180002c85`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180002c85`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180002ba4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180002ba4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180002b8c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180002b8c`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedGlobally<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        bool *a4)
{
  bool v9; // si
  unsigned int v10; // eax
  __int64 v11; // r8
  unsigned int v12; // eax
  __int64 v13; // rdx
  int v14; // ebx
  HANDLE v15; // rbx
  bool v16; // al
  struct _ERESOURCE *v17; // rcx
  HANDLE Handle; // [rsp+20h] [rbp-38h] BYREF
  int v19; // [rsp+68h] [rbp+10h] BYREF

  if ( *(_DWORD *)a2 <= 2u && *(_DWORD *)a3 <= 2u )
    return 3221225485LL;
  v9 = 0;
  if ( *(_QWORD *)(a1 + 88) )
  {
    KeEnterCriticalRegion();
    v9 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 88), 1u) == 1;
  }
  if ( *(_DWORD *)a3 > 2u && (v10 = *(_DWORD *)a3 >> 1, v10 <= 0xFFFF) && (_WORD)v10 )
    v11 = *(_QWORD *)(a3 + 8);
  else
    v11 = 0;
  if ( *(_DWORD *)a2 > 2u && (v12 = *(_DWORD *)a2 >> 1, v12 <= 0xFFFF) && (_WORD)v12 )
    v13 = *(_QWORD *)(a2 + 8);
  else
    v13 = 0;
  Handle = 0;
  v14 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(
          &Handle,
          v13,
          v11,
          0);
  if ( v14 >= 0 )
  {
    v15 = Handle;
    v19 = 0;
    v16 = (int)registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
                 Handle,
                 (__int64)L"Global",
                 &v19) >= 0
       && v19 != 0;
    *a4 = v16;
    if ( v15 )
      ZwClose(v15);
    v14 = 0;
  }
  else if ( Handle )
  {
    ZwClose(Handle);
  }
  if ( v9 )
  {
    v17 = *(struct _ERESOURCE **)(a1 + 88);
    if ( v17 )
    {
      ExReleaseResourceLite(v17);
      KeLeaveCriticalRegion();
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180002b48  mov     [rsp+arg_0], rbx
0x180002b4d  mov     [rsp+arg_10], rbp
0x180002b52  push    rsi
0x180002b53  push    rdi
0x180002b54  push    r12
0x180002b56  push    r14
0x180002b58  push    r15
0x180002b5a  sub     rsp, 30h
0x180002b5e  cmp     dword ptr [rdx], 2
0x180002b61  mov     r14, r9
0x180002b64  mov     rbx, r8
0x180002b67  mov     rdi, rdx
0x180002b6a  mov     rbp, rcx
0x180002b6d  ja      short loc_180002B7F
0x180002b6f  cmp     dword ptr [r8], 2
0x180002b73  ja      short loc_180002B7F
0x180002b75  mov     eax, 0C000000Dh
0x180002b7a  jmp     loc_180002C93
0x180002b7f  xor     r12d, r12d
0x180002b82  movzx   esi, r12b
0x180002b86  cmp     [rcx+58h], r12
0x180002b8a  jz      short loc_180002BB7
0x180002b8c  call    cs:__imp_KeEnterCriticalRegion
0x180002b93  nop     dword ptr [rax+rax+00h]
0x180002b98  mov     rcx, [rbp+58h]; Resource
0x180002b9c  lea     r15d, [r12+1]
0x180002ba1  mov     dl, r15b; Wait
0x180002ba4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180002bab  nop     dword ptr [rax+rax+00h]
0x180002bb0  cmp     al, r15b
0x180002bb3  cmovz   esi, r15d
0x180002bb7  mov     eax, [rbx]
0x180002bb9  mov     ecx, 0FFFFh
0x180002bbe  cmp     eax, 2
0x180002bc1  jbe     short loc_180002BD4
0x180002bc3  shr     eax, 1
0x180002bc5  cmp     eax, ecx
0x180002bc7  ja      short loc_180002BD4
0x180002bc9  test    ax, ax
0x180002bcc  jz      short loc_180002BD4
0x180002bce  mov     r8, [rbx+8]
0x180002bd2  jmp     short loc_180002BD7
0x180002bd4  mov     r8, r12
0x180002bd7  mov     eax, [rdi]
0x180002bd9  cmp     eax, 2
0x180002bdc  jbe     short loc_180002BEF
0x180002bde  shr     eax, 1
0x180002be0  cmp     eax, ecx
0x180002be2  ja      short loc_180002BEF
0x180002be4  test    ax, ax
0x180002be7  jz      short loc_180002BEF
0x180002be9  mov     rdx, [rdi+8]
0x180002bed  jmp     short loc_180002BF2
0x180002bef  mov     rdx, r12
0x180002bf2  xor     r9d, r9d
0x180002bf5  mov     [rsp+58h+Handle], r12
0x180002bfa  lea     rcx, [rsp+58h+Handle]
0x180002bff  call    ?open_package_key@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEAVhandle@kernel@shared@appv@@PEB_W1_N@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(appv::shared::kernel::handle &,wchar_t const *,wchar_t const *,bool)
0x180002c04  mov     ebx, eax
0x180002c06  test    eax, eax
0x180002c08  jns     short loc_180002C22
0x180002c0a  mov     rcx, [rsp+58h+Handle]; Handle
0x180002c0f  test    rcx, rcx
0x180002c12  jz      short loc_180002C6B
0x180002c14  call    cs:__imp_ZwClose
0x180002c1b  nop     dword ptr [rax+rax+00h]
0x180002c20  jmp     short loc_180002C6B
0x180002c22  mov     rbx, [rsp+58h+Handle]
0x180002c27  lea     r8, [rsp+58h+arg_8]
0x180002c2c  mov     rcx, rbx
0x180002c2f  mov     [rsp+58h+arg_8], r12d
0x180002c34  lea     rdx, aGlobal; "Global"
0x180002c3b  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,ulong &)
0x180002c40  test    eax, eax
0x180002c42  js      short loc_180002C4E
0x180002c44  cmp     [rsp+58h+arg_8], r12d
0x180002c49  setnz   al
0x180002c4c  jmp     short loc_180002C51
0x180002c4e  mov     al, r12b
0x180002c51  mov     [r14], al
0x180002c54  test    rbx, rbx
0x180002c57  jz      short loc_180002C68
0x180002c59  mov     rcx, rbx; Handle
0x180002c5c  call    cs:__imp_ZwClose
0x180002c63  nop     dword ptr [rax+rax+00h]
0x180002c68  mov     ebx, r12d
0x180002c6b  test    sil, sil
0x180002c6e  jz      short loc_180002C91
0x180002c70  mov     rcx, [rbp+58h]; Resource
0x180002c74  test    rcx, rcx
0x180002c77  jz      short loc_180002C91
0x180002c79  call    cs:__imp_ExReleaseResourceLite
0x180002c80  nop     dword ptr [rax+rax+00h]
0x180002c85  call    cs:__imp_KeLeaveCriticalRegion
0x180002c8c  nop     dword ptr [rax+rax+00h]
0x180002c91  mov     eax, ebx
0x180002c93  mov     rbx, [rsp+58h+arg_0]
0x180002c98  mov     rbp, [rsp+58h+arg_10]
0x180002c9d  add     rsp, 30h
0x180002ca1  pop     r15
0x180002ca3  pop     r14
0x180002ca5  pop     r12
0x180002ca7  pop     rdi
0x180002ca8  pop     rsi
0x180002ca9  retn
```
