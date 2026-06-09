# VemgrRemoveUser(void *,ulong,ulong,ulong *)

- ea: `0x1800130ec`
- end: `0x180013257`
- name: `?VemgrRemoveUser@@YAJPEAXKKPEAK@Z`
- size: `363`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180012670`

## callees

- `0x1800105f4`
- `0x180011ca8`
- `0x1800127c0`
- `0x1800130ec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800131fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x180013212`
- `ntoskrnl!ExFreePoolWithTag` at `0x180013229`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800131fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x180013212`
- `ntoskrnl!ExFreePoolWithTag` at `0x180013229`
- `ntoskrnl!RtlInitUnicodeString` at `0x180013155`
- `ntoskrnl!RtlInitUnicodeString` at `0x180013177`
- `ntoskrnl!RtlInitUnicodeString` at `0x180013199`
- `ntoskrnl!RtlInitUnicodeString` at `0x180013155`
- `ntoskrnl!RtlInitUnicodeString` at `0x180013177`
- `ntoskrnl!RtlInitUnicodeString` at `0x180013199`

## pseudocode

```c
__int64 __fastcall VemgrRemoveUser(_DWORD *a1, unsigned int a2, unsigned int a3, unsigned int *a4)
{
  int v8; // eax
  __int64 v9; // [rsp+30h] [rbp-29h] BYREF
  PVOID P; // [rsp+38h] [rbp-21h]
  struct _UNICODE_STRING v11; // [rsp+40h] [rbp-19h] BYREF
  __int64 v12; // [rsp+50h] [rbp-9h] BYREF
  PVOID v13; // [rsp+58h] [rbp-1h]
  struct _UNICODE_STRING v14; // [rsp+60h] [rbp+7h] BYREF
  __int64 v15; // [rsp+70h] [rbp+17h] BYREF
  PVOID v16; // [rsp+78h] [rbp+1Fh]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp+27h] BYREF

  if ( !a1 || a2 < 0x14 || a3 < 4 )
  {
    if ( a4 )
      *a4 = 0;
    return 3221225485LL;
  }
  if ( !a4 )
    return 3221225485LL;
  if ( *a1 == a2 )
  {
    v15 = 0;
    v16 = 0;
    RtlInitUnicodeString(&DestinationString, 0);
    v12 = 0;
    v13 = 0;
    RtlInitUnicodeString(&v14, 0);
    v9 = 0;
    P = 0;
    RtlInitUnicodeString(&v11, 0);
    v8 = unpack_remove_user_params<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::unpack<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
           (_DWORD)a1,
           a2,
           (unsigned int)&v15,
           (unsigned int)&v12,
           (__int64)&v9);
    if ( v8 >= 0 )
      v8 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveUser<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
             *((_QWORD *)vemgr::g_pDeviceExtn + 2),
             (__int64)&v15,
             (__int64)&v12,
             (__int64)&v9);
    MarshalReturnCode(v8, a1, a2, a4);
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v13 )
      ExFreePoolWithTag(v13, 0);
    if ( v16 )
      ExFreePoolWithTag(v16, 0);
    return 0;
  }
  else
  {
    *a4 = 0;
    return 3221225990LL;
  }
}

```

## disassembly

```asm
0x1800130ec  push    rbp
0x1800130ee  push    rbx
0x1800130ef  push    rsi
0x1800130f0  push    rdi
0x1800130f1  lea     rbp, [rsp-3Fh]
0x1800130f6  sub     rsp, 98h
0x1800130fd  mov     rbx, r9
0x180013100  mov     edi, edx
0x180013102  mov     rsi, rcx
0x180013105  test    rcx, rcx
0x180013108  jz      loc_180013239
0x18001310e  cmp     edx, 14h
0x180013111  jb      loc_180013239
0x180013117  cmp     r8d, 4
0x18001311b  jb      loc_180013239
0x180013121  test    rbx, rbx
0x180013124  jz      loc_180013245
0x18001312a  cmp     [rcx], edx
0x18001312c  jz      short loc_18001313F
0x18001312e  mov     dword ptr [r9], 0
0x180013135  mov     eax, 0C0000206h
0x18001313a  jmp     loc_18001324A
0x18001313f  xor     edx, edx; SourceString
0x180013141  mov     [rbp+57h+var_40], 0
0x180013149  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001314d  mov     [rbp+57h+var_38], 0
0x180013155  call    cs:__imp_RtlInitUnicodeString
0x18001315c  nop     dword ptr [rax+rax+00h]
0x180013161  xor     edx, edx; SourceString
0x180013163  mov     [rbp+57h+var_60], 0
0x18001316b  lea     rcx, [rbp+57h+var_50]; DestinationString
0x18001316f  mov     [rbp+57h+var_58], 0
0x180013177  call    cs:__imp_RtlInitUnicodeString
0x18001317e  nop     dword ptr [rax+rax+00h]
0x180013183  xor     edx, edx; SourceString
0x180013185  mov     [rbp+57h+var_80], 0
0x18001318d  lea     rcx, [rbp+57h+var_70]; DestinationString
0x180013191  mov     [rbp+57h+P], 0
0x180013199  call    cs:__imp_RtlInitUnicodeString
0x1800131a0  nop     dword ptr [rax+rax+00h]
0x1800131a5  lea     rax, [rbp+57h+var_80]
0x1800131a9  mov     edx, edi
0x1800131ab  lea     r9, [rbp+57h+var_60]
0x1800131af  mov     [rsp+0B0h+var_90], rax
0x1800131b4  lea     r8, [rbp+57h+var_40]
0x1800131b8  mov     rcx, rsi
0x1800131bb  call    ??$unpack@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$unpack_remove_user_params@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@SAJPEBEKAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@11@Z; unpack_remove_user_params<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::unpack<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(uchar const *,ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x1800131c0  test    eax, eax
0x1800131c2  js      short loc_1800131E0
0x1800131c4  mov     rcx, cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x1800131cb  lea     r9, [rbp+57h+var_80]
0x1800131cf  lea     r8, [rbp+57h+var_60]
0x1800131d3  lea     rdx, [rbp+57h+var_40]
0x1800131d7  mov     rcx, [rcx+10h]
0x1800131db  call    ??$RemoveUser@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@00@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveUser<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x1800131e0  mov     r9, rbx; unsigned int *
0x1800131e3  mov     r8d, edi; unsigned int
0x1800131e6  mov     rdx, rsi; void *
0x1800131e9  mov     ecx, eax; int
0x1800131eb  call    ?MarshalReturnCode@@YAXJPEAXKPEAK@Z; MarshalReturnCode(long,void *,ulong,ulong *)
0x1800131f0  mov     rcx, [rbp+57h+P]; P
0x1800131f4  test    rcx, rcx
0x1800131f7  jz      short loc_180013207
0x1800131f9  xor     edx, edx; Tag
0x1800131fb  call    cs:__imp_ExFreePoolWithTag
0x180013202  nop     dword ptr [rax+rax+00h]
0x180013207  mov     rcx, [rbp+57h+var_58]; P
0x18001320b  test    rcx, rcx
0x18001320e  jz      short loc_18001321E
0x180013210  xor     edx, edx; Tag
0x180013212  call    cs:__imp_ExFreePoolWithTag
0x180013219  nop     dword ptr [rax+rax+00h]
0x18001321e  mov     rcx, [rbp+57h+var_38]; P
0x180013222  test    rcx, rcx
0x180013225  jz      short loc_180013235
0x180013227  xor     edx, edx; Tag
0x180013229  call    cs:__imp_ExFreePoolWithTag
0x180013230  nop     dword ptr [rax+rax+00h]
0x180013235  xor     eax, eax
0x180013237  jmp     short loc_18001324A
0x180013239  test    rbx, rbx
0x18001323c  jz      short loc_180013245
0x18001323e  mov     dword ptr [r9], 0
0x180013245  mov     eax, 0C000000Dh
0x18001324a  add     rsp, 98h
0x180013251  pop     rdi
0x180013252  pop     rsi
0x180013253  pop     rbx
0x180013254  pop     rbp
0x180013255  retn
```
