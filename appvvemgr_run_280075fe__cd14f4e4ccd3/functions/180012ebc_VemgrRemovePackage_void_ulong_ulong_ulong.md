# VemgrRemovePackage(void *,ulong,ulong,ulong *)

- ea: `0x180012ebc`
- end: `0x180012fce`
- name: `?VemgrRemovePackage@@YAJPEAXKKPEAK@Z`
- size: `274`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180012670`

## callees

- `0x18000a9e4`
- `0x1800101e4`
- `0x1800127c0`
- `0x180012ebc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180012fa7`
- `ntoskrnl!ExFreePoolWithTag` at `0x180012fa7`
- `ntoskrnl!RtlInitUnicodeString` at `0x180012f16`
- `ntoskrnl!RtlInitUnicodeString` at `0x180012f16`

## pseudocode

```c
__int64 __fastcall VemgrRemovePackage(unsigned __int16 *a1, unsigned int a2, unsigned int a3, unsigned int *a4)
{
  unsigned __int64 v8; // rdx
  __int64 v9; // rcx
  char *v10; // rax
  int v11; // eax
  UNICODE_STRING v12; // [rsp+20h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF

  if ( !a1 || a2 < 0xC || a3 < 4 )
  {
    if ( a4 )
      *a4 = 0;
    return 3221225485LL;
  }
  if ( !a4 )
    return 3221225485LL;
  if ( *(_DWORD *)a1 != a2 )
  {
    *a4 = 0;
    return 3221225990LL;
  }
  *(_QWORD *)&v12.Length = 0;
  v12.Buffer = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v8 = a1[3];
  v9 = a1[2];
  if ( __PAIR32__(v8, v9) )
  {
    if ( (unsigned int)v9 > a2 - 8 || (int)v9 + (int)v8 > a2 - 8 )
      goto LABEL_15;
    v10 = (char *)a1 + v9 + 8;
  }
  else
  {
    v10 = 0;
  }
  v11 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
          &v12,
          v10,
          v8 >> 1);
  if ( v11 >= 0 )
  {
    if ( *(_DWORD *)&v12.Length > 2u )
    {
      v11 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemovePackage<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
              *((_QWORD *)vemgr::g_pDeviceExtn + 2),
              &v12);
      goto LABEL_16;
    }
LABEL_15:
    v11 = -1073741811;
  }
LABEL_16:
  MarshalReturnCode(v11, a1, a2, a4);
  if ( v12.Buffer )
    ExFreePoolWithTag(v12.Buffer, 0);
  return 0;
}

```

## disassembly

```asm
0x180012ebc  push    rbx
0x180012ebe  push    rbp
0x180012ebf  push    rsi
0x180012ec0  push    rdi
0x180012ec1  sub     rsp, 48h
0x180012ec5  xor     ebp, ebp
0x180012ec7  mov     rbx, r9
0x180012eca  mov     esi, edx
0x180012ecc  mov     rdi, rcx
0x180012ecf  test    rcx, rcx
0x180012ed2  jz      loc_180012FB7
0x180012ed8  cmp     edx, 0Ch
0x180012edb  jb      loc_180012FB7
0x180012ee1  cmp     r8d, 4
0x180012ee5  jb      loc_180012FB7
0x180012eeb  test    rbx, rbx
0x180012eee  jz      loc_180012FBF
0x180012ef4  cmp     [rcx], edx
0x180012ef6  jz      short loc_180012F05
0x180012ef8  mov     [r9], ebp
0x180012efb  mov     eax, 0C0000206h
0x180012f00  jmp     loc_180012FC4
0x180012f05  xor     edx, edx; SourceString
0x180012f07  mov     [rsp+68h+var_48], rbp
0x180012f0c  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180012f11  mov     [rsp+68h+P], rbp
0x180012f16  call    cs:__imp_RtlInitUnicodeString
0x180012f1d  nop     dword ptr [rax+rax+00h]
0x180012f22  movzx   edx, word ptr [rdi+6]
0x180012f26  movzx   ecx, word ptr [rdi+4]
0x180012f2a  test    dx, dx
0x180012f2d  jnz     short loc_180012F39
0x180012f2f  test    cx, cx
0x180012f32  jnz     short loc_180012F39
0x180012f34  mov     rax, rbp
0x180012f37  jmp     short loc_180012F51
0x180012f39  lea     r8d, [rsi-8]
0x180012f3d  cmp     ecx, r8d
0x180012f40  ja      short loc_180012F86
0x180012f42  lea     eax, [rcx+rdx]
0x180012f45  cmp     eax, r8d
0x180012f48  ja      short loc_180012F86
0x180012f4a  lea     rax, [rdi+8]
0x180012f4e  add     rax, rcx
0x180012f51  mov     r8, rdx
0x180012f54  lea     rcx, [rsp+68h+var_48]
0x180012f59  shr     r8, 1
0x180012f5c  mov     rdx, rax
0x180012f5f  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x180012f64  test    eax, eax
0x180012f66  js      short loc_180012F8B
0x180012f68  cmp     dword ptr [rsp+68h+var_48], 2
0x180012f6d  jbe     short loc_180012F86
0x180012f6f  mov     rcx, cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x180012f76  lea     rdx, [rsp+68h+var_48]
0x180012f7b  mov     rcx, [rcx+10h]
0x180012f7f  call    ??$RemovePackage@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemovePackage<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x180012f84  jmp     short loc_180012F8B
0x180012f86  mov     eax, 0C000000Dh
0x180012f8b  mov     r9, rbx; unsigned int *
0x180012f8e  mov     r8d, esi; unsigned int
0x180012f91  mov     rdx, rdi; void *
0x180012f94  mov     ecx, eax; int
0x180012f96  call    ?MarshalReturnCode@@YAXJPEAXKPEAK@Z; MarshalReturnCode(long,void *,ulong,ulong *)
0x180012f9b  mov     rcx, [rsp+68h+P]; P
0x180012fa0  test    rcx, rcx
0x180012fa3  jz      short loc_180012FB3
0x180012fa5  xor     edx, edx; Tag
0x180012fa7  call    cs:__imp_ExFreePoolWithTag
0x180012fae  nop     dword ptr [rax+rax+00h]
0x180012fb3  xor     eax, eax
0x180012fb5  jmp     short loc_180012FC4
0x180012fb7  test    rbx, rbx
0x180012fba  jz      short loc_180012FBF
0x180012fbc  mov     [r9], ebp
0x180012fbf  mov     eax, 0C000000Dh
0x180012fc4  add     rsp, 48h
0x180012fc8  pop     rdi
0x180012fc9  pop     rsi
0x180012fca  pop     rbp
0x180012fcb  pop     rbx
0x180012fcc  retn
```
