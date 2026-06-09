# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)

- ea: `0x1800147fc`
- end: `0x18001495b`
- name: `?store@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180012004`

## callees

- `0x18000e23c`
- `0x1800137f8`
- `0x1800141d0`
- `0x1800147fc`
- `0x180015154`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180014891`
- `ntoskrnl!ZwClose` at `0x1800148ea`
- `ntoskrnl!ZwClose` at `0x1800148fe`
- `ntoskrnl!ZwClose` at `0x180014891`
- `ntoskrnl!ZwClose` at `0x1800148ea`
- `ntoskrnl!ZwClose` at `0x1800148fe`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store(
        __int64 **a1)
{
  __int64 *v2; // rax
  __int64 v3; // rax
  unsigned int v4; // eax
  int root_key; // ebx
  __int64 *v7; // rax
  _DWORD *v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rdx
  HANDLE v11; // rbx
  NTSTATUS v12; // esi
  __int64 v13; // rax
  unsigned int v14; // ecx
  __int64 v15; // rcx
  HANDLE Handle; // [rsp+40h] [rbp+8h] BYREF
  HANDLE v17; // [rsp+48h] [rbp+10h] BYREF

  if ( !*a1 )
    return 3221225485LL;
  v2 = a1[1];
  if ( !v2 )
    return 3221225485LL;
  if ( !*((_DWORD *)v2 + 2) )
    return 3221225485LL;
  if ( !**a1 )
    return 3221225485LL;
  v3 = (*a1)[1];
  if ( !v3 )
    return 3221225485LL;
  if ( !*(_DWORD *)(v3 + 8) )
    return 3221225485LL;
  v4 = *(_DWORD *)**a1 >> 1;
  if ( v4 > 0xFFFF || !(_WORD)v4 )
    return 3221225485LL;
  Handle = 0;
  root_key = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_root_key(
               (__int64)&Handle,
               0);
  if ( root_key >= 0 )
  {
    v7 = *a1;
    v17 = 0;
    v8 = (_DWORD *)*v7;
    v9 = *(_DWORD *)*v7 >> 1;
    if ( v9 <= 0xFFFF && (_WORD)v9 )
      v10 = *((_QWORD *)v8 + 1);
    else
      v10 = 0;
    v11 = Handle;
    v12 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
            Handle,
            v10,
            &v17);
    if ( v12 < 0 )
    {
      v12 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_package_data(
              &Handle,
              a1);
      if ( v12 < 0 )
      {
        v13 = **a1;
        v14 = *(_DWORD *)v13 >> 1;
        if ( v14 <= 0xFFFF && (_WORD)v14 )
          v15 = *(_QWORD *)(v13 + 8);
        else
          v15 = 0;
        Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_package(v15);
      }
    }
    if ( v17 )
      ZwClose(v17);
    if ( v11 )
      ZwClose(v11);
    return (unsigned int)v12;
  }
  else
  {
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)root_key;
  }
}

```

## disassembly

```asm
0x1800147fc  mov     [rsp+arg_10], rbx
0x180014801  push    rbp
0x180014802  push    rsi
0x180014803  push    rdi
0x180014804  sub     rsp, 20h
0x180014808  xor     ebp, ebp
0x18001480a  mov     rdi, rcx
0x18001480d  cmp     [rcx], rbp
0x180014810  jz      loc_180014948
0x180014816  mov     rax, [rcx+8]
0x18001481a  test    rax, rax
0x18001481d  jz      loc_180014948
0x180014823  mov     eax, [rax+8]
0x180014826  test    eax, eax
0x180014828  jz      loc_180014948
0x18001482e  mov     rax, [rcx]
0x180014831  cmp     [rax], rbp
0x180014834  jz      loc_180014948
0x18001483a  mov     rax, [rax+8]
0x18001483e  test    rax, rax
0x180014841  jz      loc_180014948
0x180014847  mov     eax, [rax+8]
0x18001484a  test    eax, eax
0x18001484c  jz      loc_180014948
0x180014852  mov     rax, [rcx]
0x180014855  mov     rcx, [rax]
0x180014858  mov     eax, [rcx]
0x18001485a  shr     eax, 1
0x18001485c  cmp     eax, 0FFFFh
0x180014861  ja      loc_180014948
0x180014867  test    ax, ax
0x18001486a  jz      loc_180014948
0x180014870  xor     edx, edx
0x180014872  mov     [rsp+38h+Handle], rbp
0x180014877  lea     rcx, [rsp+38h+Handle]
0x18001487c  call    ?create_root_key@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEAVhandle@kernel@shared@appv@@W4ConfigurationType@1@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_root_key(appv::shared::kernel::handle &,Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ConfigurationType)
0x180014881  mov     ebx, eax
0x180014883  test    eax, eax
0x180014885  jns     short loc_1800148A4
0x180014887  mov     rcx, [rsp+38h+Handle]; Handle
0x18001488c  test    rcx, rcx
0x18001488f  jz      short loc_18001489D
0x180014891  call    cs:__imp_ZwClose
0x180014898  nop     dword ptr [rax+rax+00h]
0x18001489d  mov     eax, ebx
0x18001489f  jmp     loc_18001494D
0x1800148a4  mov     rax, [rdi]
0x1800148a7  mov     [rsp+38h+arg_8], rbp
0x1800148ac  mov     rdx, [rax]
0x1800148af  mov     eax, [rdx]
0x1800148b1  shr     eax, 1
0x1800148b3  cmp     eax, 0FFFFh
0x1800148b8  ja      short loc_1800148C5
0x1800148ba  test    ax, ax
0x1800148bd  jz      short loc_1800148C5
0x1800148bf  mov     rdx, [rdx+8]
0x1800148c3  jmp     short loc_1800148C8
0x1800148c5  mov     rdx, rbp
0x1800148c8  mov     rbx, [rsp+38h+Handle]
0x1800148cd  lea     r8, [rsp+38h+arg_8]
0x1800148d2  mov     rcx, rbx
0x1800148d5  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x1800148da  mov     esi, eax
0x1800148dc  test    eax, eax
0x1800148de  js      short loc_18001490E
0x1800148e0  mov     rcx, [rsp+38h+arg_8]; Handle
0x1800148e5  test    rcx, rcx
0x1800148e8  jz      short loc_1800148F6
0x1800148ea  call    cs:__imp_ZwClose
0x1800148f1  nop     dword ptr [rax+rax+00h]
0x1800148f6  test    rbx, rbx
0x1800148f9  jz      short loc_18001490A
0x1800148fb  mov     rcx, rbx; Handle
0x1800148fe  call    cs:__imp_ZwClose
0x180014905  nop     dword ptr [rax+rax+00h]
0x18001490a  mov     eax, esi
0x18001490c  jmp     short loc_18001494D
0x18001490e  mov     rdx, rdi
0x180014911  lea     rcx, [rsp+38h+Handle]
0x180014916  call    ?store_package_data@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@AEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_package_data(appv::shared::kernel::handle const &,kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x18001491b  mov     esi, eax
0x18001491d  test    eax, eax
0x18001491f  jns     short loc_1800148E0
0x180014921  mov     rcx, [rdi]
0x180014924  mov     rax, [rcx]
0x180014927  mov     ecx, [rax]
0x180014929  shr     ecx, 1
0x18001492b  cmp     ecx, 0FFFFh
0x180014931  ja      short loc_18001493E
0x180014933  test    cx, cx
0x180014936  jz      short loc_18001493E
0x180014938  mov     rcx, [rax+8]
0x18001493c  jmp     short loc_180014941
0x18001493e  mov     rcx, rbp
0x180014941  call    ?remove_package@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_package(wchar_t const *)
0x180014946  jmp     short loc_1800148E0
0x180014948  mov     eax, 0C000000Dh
0x18001494d  mov     rbx, [rsp+38h+arg_10]
0x180014952  add     rsp, 20h
0x180014956  pop     rdi
0x180014957  pop     rsi
0x180014958  pop     rbp
0x180014959  retn
```
