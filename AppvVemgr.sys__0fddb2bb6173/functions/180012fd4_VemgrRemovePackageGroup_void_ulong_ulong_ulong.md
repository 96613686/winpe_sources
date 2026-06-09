# VemgrRemovePackageGroup(void *,ulong,ulong,ulong *)

- ea: `0x180012fd4`
- end: `0x1800130e6`
- name: `?VemgrRemovePackageGroup@@YAJPEAXKKPEAK@Z`
- size: `274`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180012670`

## callees

- `0x18000a9e4`
- `0x180010374`
- `0x1800127c0`
- `0x180012fd4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800130bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800130bf`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001302e`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001302e`

## pseudocode

```c
__int64 __fastcall VemgrRemovePackageGroup(_DWORD *a1, unsigned int a2, unsigned int a3, unsigned int *a4)
{
  __int64 v8; // r9
  unsigned __int64 v9; // rdx
  __int64 v10; // rcx
  char *v11; // rax
  int v12; // eax
  UNICODE_STRING v13; // [rsp+20h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF

  if ( !a1 || a2 < 0xC || a3 < 4 )
  {
    if ( a4 )
      *a4 = 0;
    return 3221225485LL;
  }
  if ( !a4 )
    return 3221225485LL;
  if ( *a1 != a2 )
  {
    *a4 = 0;
    return 3221225990LL;
  }
  *(_QWORD *)&v13.Length = 0;
  v13.Buffer = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v9 = *((unsigned __int16 *)a1 + 3);
  v10 = *((unsigned __int16 *)a1 + 2);
  if ( __PAIR32__(v9, v10) )
  {
    if ( (unsigned int)v10 > a2 - 8 || (int)v10 + (int)v9 > a2 - 8 )
      goto LABEL_15;
    v11 = (char *)a1 + v10 + 8;
  }
  else
  {
    v11 = 0;
  }
  v12 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
          (__int64)&v13,
          v11,
          v9 >> 1,
          v8);
  if ( v12 >= 0 )
  {
    if ( *(_DWORD *)&v13.Length > 2u )
    {
      v12 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemovePackageGroup<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
              *((_QWORD *)vemgr::g_pDeviceExtn + 2),
              &v13);
      goto LABEL_16;
    }
LABEL_15:
    v12 = -1073741811;
  }
LABEL_16:
  MarshalReturnCode(v12, a1, a2, a4);
  if ( v13.Buffer )
    ExFreePoolWithTag(v13.Buffer, 0);
  return 0;
}

```

## disassembly

```asm
0x180012fd4  push    rbx
0x180012fd6  push    rbp
0x180012fd7  push    rsi
0x180012fd8  push    rdi
0x180012fd9  sub     rsp, 48h
0x180012fdd  xor     ebp, ebp
0x180012fdf  mov     rbx, r9
0x180012fe2  mov     esi, edx
0x180012fe4  mov     rdi, rcx
0x180012fe7  test    rcx, rcx
0x180012fea  jz      loc_1800130CF
0x180012ff0  cmp     edx, 0Ch
0x180012ff3  jb      loc_1800130CF
0x180012ff9  cmp     r8d, 4
0x180012ffd  jb      loc_1800130CF
0x180013003  test    rbx, rbx
0x180013006  jz      loc_1800130D7
0x18001300c  cmp     [rcx], edx
0x18001300e  jz      short loc_18001301D
0x180013010  mov     [r9], ebp
0x180013013  mov     eax, 0C0000206h
0x180013018  jmp     loc_1800130DC
0x18001301d  xor     edx, edx; SourceString
0x18001301f  mov     [rsp+68h+var_48], rbp
0x180013024  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180013029  mov     [rsp+68h+P], rbp
0x18001302e  call    cs:__imp_RtlInitUnicodeString
0x180013035  nop     dword ptr [rax+rax+00h]
0x18001303a  movzx   edx, word ptr [rdi+6]
0x18001303e  movzx   ecx, word ptr [rdi+4]
0x180013042  test    dx, dx
0x180013045  jnz     short loc_180013051
0x180013047  test    cx, cx
0x18001304a  jnz     short loc_180013051
0x18001304c  mov     rax, rbp
0x18001304f  jmp     short loc_180013069
0x180013051  lea     r8d, [rsi-8]
0x180013055  cmp     ecx, r8d
0x180013058  ja      short loc_18001309E
0x18001305a  lea     eax, [rcx+rdx]
0x18001305d  cmp     eax, r8d
0x180013060  ja      short loc_18001309E
0x180013062  lea     rax, [rdi+8]
0x180013066  add     rax, rcx
0x180013069  mov     r8, rdx
0x18001306c  lea     rcx, [rsp+68h+var_48]
0x180013071  shr     r8, 1
0x180013074  mov     rdx, rax
0x180013077  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18001307c  test    eax, eax
0x18001307e  js      short loc_1800130A3
0x180013080  cmp     dword ptr [rsp+68h+var_48], 2
0x180013085  jbe     short loc_18001309E
0x180013087  mov     rcx, cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x18001308e  lea     rdx, [rsp+68h+var_48]
0x180013093  mov     rcx, [rcx+10h]
0x180013097  call    ??$RemovePackageGroup@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemovePackageGroup<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x18001309c  jmp     short loc_1800130A3
0x18001309e  mov     eax, 0C000000Dh
0x1800130a3  mov     r9, rbx; unsigned int *
0x1800130a6  mov     r8d, esi; unsigned int
0x1800130a9  mov     rdx, rdi; void *
0x1800130ac  mov     ecx, eax; int
0x1800130ae  call    ?MarshalReturnCode@@YAXJPEAXKPEAK@Z; MarshalReturnCode(long,void *,ulong,ulong *)
0x1800130b3  mov     rcx, [rsp+68h+P]; P
0x1800130b8  test    rcx, rcx
0x1800130bb  jz      short loc_1800130CB
0x1800130bd  xor     edx, edx; Tag
0x1800130bf  call    cs:__imp_ExFreePoolWithTag
0x1800130c6  nop     dword ptr [rax+rax+00h]
0x1800130cb  xor     eax, eax
0x1800130cd  jmp     short loc_1800130DC
0x1800130cf  test    rbx, rbx
0x1800130d2  jz      short loc_1800130D7
0x1800130d4  mov     [r9], ebp
0x1800130d7  mov     eax, 0C000000Dh
0x1800130dc  add     rsp, 48h
0x1800130e0  pop     rdi
0x1800130e1  pop     rsi
0x1800130e2  pop     rbp
0x1800130e3  pop     rbx
0x1800130e4  retn
```
