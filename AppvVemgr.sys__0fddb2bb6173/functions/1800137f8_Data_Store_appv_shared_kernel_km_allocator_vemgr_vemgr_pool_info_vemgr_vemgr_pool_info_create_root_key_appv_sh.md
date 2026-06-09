# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_root_key(appv::shared::kernel::handle &,Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ConfigurationType)

- ea: `0x1800137f8`
- end: `0x180013a48`
- name: `?create_root_key@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEAVhandle@kernel@shared@appv@@W4ConfigurationType@1@@Z`
- size: `592`
- prototype: `__int64 __fastcall(HANDLE *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800147fc`
- `0x180014964`

## callees

- `0x18000b420`
- `0x18000e23c`
- `0x1800137f8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180013840`
- `ntoskrnl!ZwClose` at `0x180013881`
- `ntoskrnl!ZwClose` at `0x180013895`
- `ntoskrnl!ZwClose` at `0x1800138d6`
- `ntoskrnl!ZwClose` at `0x1800138ea`
- `ntoskrnl!ZwClose` at `0x1800138fe`
- `ntoskrnl!ZwClose` at `0x180013963`
- `ntoskrnl!ZwClose` at `0x180013977`
- `ntoskrnl!ZwClose` at `0x18001398b`
- `ntoskrnl!ZwClose` at `0x18001399f`
- `ntoskrnl!ZwClose` at `0x1800139e5`
- `ntoskrnl!ZwClose` at `0x1800139f9`
- `ntoskrnl!ZwClose` at `0x180013a0d`
- `ntoskrnl!ZwClose` at `0x180013a21`
- `ntoskrnl!ZwClose` at `0x180013840`
- `ntoskrnl!ZwClose` at `0x180013881`
- `ntoskrnl!ZwClose` at `0x180013895`
- `ntoskrnl!ZwClose` at `0x1800138d6`
- `ntoskrnl!ZwClose` at `0x1800138ea`
- `ntoskrnl!ZwClose` at `0x1800138fe`
- `ntoskrnl!ZwClose` at `0x180013963`
- `ntoskrnl!ZwClose` at `0x180013977`
- `ntoskrnl!ZwClose` at `0x18001398b`
- `ntoskrnl!ZwClose` at `0x18001399f`
- `ntoskrnl!ZwClose` at `0x1800139e5`
- `ntoskrnl!ZwClose` at `0x1800139f9`
- `ntoskrnl!ZwClose` at `0x180013a0d`
- `ntoskrnl!ZwClose` at `0x180013a21`

## string_xrefs

- `0x18001381f`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft`
- `0x180013924`: `Configuration`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_root_key(
        HANDLE *a1,
        int a2)
{
  int v4; // ebx
  HANDLE v6; // rbx
  NTSTATUS v7; // edi
  HANDLE v8; // rdi
  NTSTATUS v9; // esi
  HANDLE v10; // rsi
  NTSTATUS key; // r15d
  HANDLE v12; // rcx
  int v13; // r14d
  const WCHAR *v14; // rdx
  HANDLE v15; // r14
  HANDLE v16; // [rsp+20h] [rbp-10h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp+40h] BYREF
  HANDLE v18; // [rsp+78h] [rbp+48h] BYREF

  Handle = 0;
  v4 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
         0,
         L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft",
         &Handle);
  if ( v4 < 0 )
  {
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)v4;
  }
  v6 = Handle;
  v18 = 0;
  v7 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
         Handle,
         L"AppV",
         &v18);
  if ( v7 < 0 )
  {
    if ( v18 )
      ZwClose(v18);
    if ( v6 )
      ZwClose(v6);
    return (unsigned int)v7;
  }
  v8 = v18;
  v16 = 0;
  v9 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
         v18,
         L"MAV",
         &v16);
  if ( v9 < 0 )
  {
    if ( v16 )
      ZwClose(v16);
    if ( v8 )
      ZwClose(v8);
    if ( v6 )
      ZwClose(v6);
    return (unsigned int)v9;
  }
  v10 = v16;
  Handle = 0;
  key = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
          v16,
          L"Configuration",
          &Handle);
  if ( key < 0 )
  {
    v12 = Handle;
    if ( Handle )
      goto LABEL_39;
    goto LABEL_40;
  }
  if ( !a2 )
  {
    v14 = L"Packages";
LABEL_37:
    v15 = Handle;
    key = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
            Handle,
            v14,
            a1);
    if ( v15 )
    {
      v12 = v15;
LABEL_39:
      ZwClose(v12);
    }
LABEL_40:
    if ( v10 )
      ZwClose(v10);
    if ( v8 )
      ZwClose(v8);
    if ( v6 )
      ZwClose(v6);
    return (unsigned int)key;
  }
  v13 = a2 - 1;
  if ( !v13 )
  {
    v14 = L"Groups";
    goto LABEL_37;
  }
  if ( v13 == 1 )
  {
    v14 = L"Volumes";
    goto LABEL_37;
  }
  if ( Handle )
    ZwClose(Handle);
  if ( v10 )
    ZwClose(v10);
  if ( v8 )
    ZwClose(v8);
  if ( v6 )
    ZwClose(v6);
  return 3221225485LL;
}

```

## disassembly

```asm
0x1800137f8  mov     [rsp-28h+arg_0], rbx
0x1800137fd  mov     [rsp-28h+arg_8], rsi
0x180013802  push    rbp
0x180013803  push    rdi
0x180013804  push    r12
0x180013806  push    r14
0x180013808  push    r15
0x18001380a  mov     rbp, rsp
0x18001380d  sub     rsp, 30h
0x180013811  mov     r14d, edx
0x180013814  mov     [rbp+Handle], 0
0x18001381c  mov     r12, rcx
0x18001381f  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x180013826  xor     ecx, ecx
0x180013828  lea     r8, [rbp+Handle]
0x18001382c  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180013831  mov     ebx, eax
0x180013833  test    eax, eax
0x180013835  jns     short loc_180013853
0x180013837  mov     rcx, [rbp+Handle]; Handle
0x18001383b  test    rcx, rcx
0x18001383e  jz      short loc_18001384C
0x180013840  call    cs:__imp_ZwClose
0x180013847  nop     dword ptr [rax+rax+00h]
0x18001384c  mov     eax, ebx
0x18001384e  jmp     loc_180013A30
0x180013853  mov     rbx, [rbp+Handle]
0x180013857  lea     r8, [rbp+arg_18]
0x18001385b  mov     rcx, rbx
0x18001385e  mov     [rbp+arg_18], 0
0x180013866  lea     rdx, aAppv; "AppV"
0x18001386d  call    ?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,wchar_t const *,appv::shared::kernel::handle &)
0x180013872  mov     edi, eax
0x180013874  test    eax, eax
0x180013876  jns     short loc_1800138A8
0x180013878  mov     rcx, [rbp+arg_18]; Handle
0x18001387c  test    rcx, rcx
0x18001387f  jz      short loc_18001388D
0x180013881  call    cs:__imp_ZwClose
0x180013888  nop     dword ptr [rax+rax+00h]
0x18001388d  test    rbx, rbx
0x180013890  jz      short loc_1800138A1
0x180013892  mov     rcx, rbx; Handle
0x180013895  call    cs:__imp_ZwClose
0x18001389c  nop     dword ptr [rax+rax+00h]
0x1800138a1  mov     eax, edi
0x1800138a3  jmp     loc_180013A30
0x1800138a8  mov     rdi, [rbp+arg_18]
0x1800138ac  lea     r8, [rbp+var_10]
0x1800138b0  mov     rcx, rdi
0x1800138b3  mov     [rbp+var_10], 0
0x1800138bb  lea     rdx, aMav; "MAV"
0x1800138c2  call    ?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,wchar_t const *,appv::shared::kernel::handle &)
0x1800138c7  mov     esi, eax
0x1800138c9  test    eax, eax
0x1800138cb  jns     short loc_180013911
0x1800138cd  mov     rcx, [rbp+var_10]; Handle
0x1800138d1  test    rcx, rcx
0x1800138d4  jz      short loc_1800138E2
0x1800138d6  call    cs:__imp_ZwClose
0x1800138dd  nop     dword ptr [rax+rax+00h]
0x1800138e2  test    rdi, rdi
0x1800138e5  jz      short loc_1800138F6
0x1800138e7  mov     rcx, rdi; Handle
0x1800138ea  call    cs:__imp_ZwClose
0x1800138f1  nop     dword ptr [rax+rax+00h]
0x1800138f6  test    rbx, rbx
0x1800138f9  jz      short loc_18001390A
0x1800138fb  mov     rcx, rbx; Handle
0x1800138fe  call    cs:__imp_ZwClose
0x180013905  nop     dword ptr [rax+rax+00h]
0x18001390a  mov     eax, esi
0x18001390c  jmp     loc_180013A30
0x180013911  mov     rsi, [rbp+var_10]
0x180013915  lea     r8, [rbp+Handle]
0x180013919  mov     rcx, rsi
0x18001391c  mov     [rbp+Handle], 0
0x180013924  lea     rdx, aConfiguration; "Configuration"
0x18001392b  call    ?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,wchar_t const *,appv::shared::kernel::handle &)
0x180013930  mov     r15d, eax
0x180013933  test    eax, eax
0x180013935  jns     short loc_180013949
0x180013937  mov     rcx, [rbp+Handle]
0x18001393b  test    rcx, rcx
0x18001393e  jz      loc_1800139F1
0x180013944  jmp     loc_1800139E5
0x180013949  test    r14d, r14d
0x18001394c  jz      short loc_1800139C4
0x18001394e  sub     r14d, 1
0x180013952  jz      short loc_1800139BB
0x180013954  cmp     r14d, 1
0x180013958  jz      short loc_1800139B2
0x18001395a  mov     rcx, [rbp+Handle]; Handle
0x18001395e  test    rcx, rcx
0x180013961  jz      short loc_18001396F
0x180013963  call    cs:__imp_ZwClose
0x18001396a  nop     dword ptr [rax+rax+00h]
0x18001396f  test    rsi, rsi
0x180013972  jz      short loc_180013983
0x180013974  mov     rcx, rsi; Handle
0x180013977  call    cs:__imp_ZwClose
0x18001397e  nop     dword ptr [rax+rax+00h]
0x180013983  test    rdi, rdi
0x180013986  jz      short loc_180013997
0x180013988  mov     rcx, rdi; Handle
0x18001398b  call    cs:__imp_ZwClose
0x180013992  nop     dword ptr [rax+rax+00h]
0x180013997  test    rbx, rbx
0x18001399a  jz      short loc_1800139AB
0x18001399c  mov     rcx, rbx; Handle
0x18001399f  call    cs:__imp_ZwClose
0x1800139a6  nop     dword ptr [rax+rax+00h]
0x1800139ab  mov     eax, 0C000000Dh
0x1800139b0  jmp     short loc_180013A30
0x1800139b2  lea     rdx, aVolumes; "Volumes"
0x1800139b9  jmp     short loc_1800139CB
0x1800139bb  lea     rdx, aGroups; "Groups"
0x1800139c2  jmp     short loc_1800139CB
0x1800139c4  lea     rdx, aPackages; "Packages"
0x1800139cb  mov     r14, [rbp+Handle]
0x1800139cf  mov     r8, r12
0x1800139d2  mov     rcx, r14
0x1800139d5  call    ?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,wchar_t const *,appv::shared::kernel::handle &)
0x1800139da  mov     r15d, eax
0x1800139dd  test    r14, r14
0x1800139e0  jz      short loc_1800139F1
0x1800139e2  mov     rcx, r14; Handle
0x1800139e5  call    cs:__imp_ZwClose
0x1800139ec  nop     dword ptr [rax+rax+00h]
0x1800139f1  test    rsi, rsi
0x1800139f4  jz      short loc_180013A05
0x1800139f6  mov     rcx, rsi; Handle
0x1800139f9  call    cs:__imp_ZwClose
0x180013a00  nop     dword ptr [rax+rax+00h]
0x180013a05  test    rdi, rdi
0x180013a08  jz      short loc_180013A19
0x180013a0a  mov     rcx, rdi; Handle
0x180013a0d  call    cs:__imp_ZwClose
0x180013a14  nop     dword ptr [rax+rax+00h]
0x180013a19  test    rbx, rbx
0x180013a1c  jz      short loc_180013A2D
0x180013a1e  mov     rcx, rbx; Handle
0x180013a21  call    cs:__imp_ZwClose
0x180013a28  nop     dword ptr [rax+rax+00h]
0x180013a2d  mov     eax, r15d
0x180013a30  mov     rbx, [rsp+30h+arg_0]
0x180013a35  mov     rsi, [rsp+30h+arg_8]
0x180013a3a  add     rsp, 30h
0x180013a3e  pop     r15
0x180013a40  pop     r14
0x180013a42  pop     r12
0x180013a44  pop     rdi
0x180013a45  pop     rbp
0x180013a46  retn
```
