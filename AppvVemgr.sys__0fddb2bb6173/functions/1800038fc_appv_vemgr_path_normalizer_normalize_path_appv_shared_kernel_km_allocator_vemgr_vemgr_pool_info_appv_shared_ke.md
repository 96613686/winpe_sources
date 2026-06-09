# appv::vemgr::path_normalizer::normalize_path<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,bool)

- ea: `0x1800038fc`
- end: `0x180003b05`
- name: `??$normalize_path@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@path_normalizer@vemgr@appv@@SAJAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@2@_N@Z`
- size: `521`
- prototype: `__int64 __fastcall(__int64, unsigned __int8)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x18000da60`
- `0x180012804`
- `0x180019014`

## callees

- `0x180003750`
- `0x1800038fc`
- `0x18000a864`
- `0x18000a9e4`
- `0x18000acbc`
- `0x18000fb58`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x180003983`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1800039bb`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x180003983`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1800039bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x180003a05`
- `ntoskrnl!ExFreePoolWithTag` at `0x180003a28`
- `ntoskrnl!ExFreePoolWithTag` at `0x180003ab6`
- `ntoskrnl!ExFreePoolWithTag` at `0x180003af4`
- `ntoskrnl!ExFreePoolWithTag` at `0x180003a05`
- `ntoskrnl!ExFreePoolWithTag` at `0x180003a28`
- `ntoskrnl!ExFreePoolWithTag` at `0x180003ab6`
- `ntoskrnl!ExFreePoolWithTag` at `0x180003af4`
- `ntoskrnl!RtlInitUnicodeString` at `0x180003926`
- `ntoskrnl!RtlInitUnicodeString` at `0x180003948`
- `ntoskrnl!RtlInitUnicodeString` at `0x180003969`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800039a5`
- `ntoskrnl!RtlInitUnicodeString` at `0x180003926`
- `ntoskrnl!RtlInitUnicodeString` at `0x180003948`
- `ntoskrnl!RtlInitUnicodeString` at `0x180003969`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800039a5`

## pseudocode

```c
__int64 __fastcall appv::vemgr::path_normalizer::normalize_path<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        unsigned __int8 a2)
{
  NTSTATUS v4; // ebx
  unsigned int v6; // eax
  _WORD *v7; // r8
  UNICODE_STRING String1; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING v9; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING v10; // [rsp+40h] [rbp-30h] BYREF
  __int64 v11; // [rsp+50h] [rbp-20h] BYREF
  PVOID v12; // [rsp+58h] [rbp-18h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF

  v11 = 0;
  v12 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  *(_QWORD *)&v9.Length = 0;
  v9.Buffer = 0;
  RtlInitUnicodeString(&v10, 0);
  String1 = 0;
  RtlInitUnicodeString(&String1, L"\\??\\");
  if ( RtlPrefixUnicodeString(&String1, (PCUNICODE_STRING)(a1 + 16), 1u) == 1 )
  {
    v4 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::build_managed_unicode_string(
           &v9,
           a1);
    if ( v4 < 0 )
    {
LABEL_25:
      if ( v9.Buffer )
        ExFreePoolWithTag(v9.Buffer, 0);
      goto LABEL_8;
    }
    goto LABEL_4;
  }
  String1 = 0;
  RtlInitUnicodeString(&String1, L"\\??\\");
  if ( RtlPrefixUnicodeString(&String1, (PCUNICODE_STRING)(a1 + 16), 1u) == 1 )
  {
    appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::build_managed_unicode_string(
      &v9,
      a1);
    goto LABEL_4;
  }
  v6 = *(_DWORD *)a1 >> 1;
  if ( v6 > 0xFFFF
    || (unsigned __int16)v6 < 2u
    || (v7 = *(_WORD **)(a1 + 8), (unsigned __int16)(*v7 - 97) > 0x19u) && (unsigned __int16)(*v7 - 65) > 0x19u
    || v7[1] != 58 )
  {
    v4 = -1073741767;
    goto LABEL_20;
  }
  v4 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
         &v9,
         L"\\??\\",
         4);
  if ( v4 >= 0 )
  {
    v4 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
           &v9,
           a1 + 16);
    if ( v4 >= 0 )
    {
LABEL_4:
      v4 = appv::vemgr::path_normalizer::normalize<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(&v9, a2);
      if ( v4 >= 0 )
      {
        appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::swap(
          &v9,
          &v11);
        if ( v9.Buffer )
          ExFreePoolWithTag(v9.Buffer, 0);
        appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::swap(
          a1,
          &v11);
        goto LABEL_8;
      }
      goto LABEL_25;
    }
  }
LABEL_20:
  if ( v9.Buffer )
    ExFreePoolWithTag(v9.Buffer, 0);
LABEL_8:
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800038fc  push    rbp
0x1800038fe  push    rbx
0x1800038ff  push    rsi
0x180003900  push    rdi
0x180003901  push    r14
0x180003903  mov     rbp, rsp
0x180003906  sub     rsp, 70h
0x18000390a  mov     r14b, dl
0x18000390d  mov     [rbp+var_20], 0
0x180003915  mov     rdi, rcx
0x180003918  mov     [rbp+var_18], 0
0x180003920  xor     edx, edx; SourceString
0x180003922  lea     rcx, [rbp+DestinationString]; DestinationString
0x180003926  call    cs:__imp_RtlInitUnicodeString
0x18000392d  nop     dword ptr [rax+rax+00h]
0x180003932  xor     edx, edx; SourceString
0x180003934  mov     [rbp+var_40], 0
0x18000393c  lea     rcx, [rbp+var_30]; DestinationString
0x180003940  mov     [rbp+P], 0
0x180003948  call    cs:__imp_RtlInitUnicodeString
0x18000394f  nop     dword ptr [rax+rax+00h]
0x180003954  xorps   xmm0, xmm0
0x180003957  lea     rbx, SourceString; "\\??\\"
0x18000395e  mov     rdx, rbx; SourceString
0x180003961  lea     rcx, [rbp+String1]; DestinationString
0x180003965  movups  xmmword ptr [rbp+String1.Length], xmm0
0x180003969  call    cs:__imp_RtlInitUnicodeString
0x180003970  nop     dword ptr [rax+rax+00h]
0x180003975  lea     rsi, [rdi+10h]
0x180003979  mov     r8b, 1; CaseInSensitive
0x18000397c  mov     rdx, rsi; String2
0x18000397f  lea     rcx, [rbp+String1]; String1
0x180003983  call    cs:__imp_RtlPrefixUnicodeString
0x18000398a  nop     dword ptr [rax+rax+00h]
0x18000398f  cmp     al, 1
0x180003991  jz      loc_180003ACF
0x180003997  xorps   xmm0, xmm0
0x18000399a  lea     rcx, [rbp+String1]; DestinationString
0x18000399e  mov     rdx, rbx; SourceString
0x1800039a1  movups  xmmword ptr [rbp+String1.Length], xmm0
0x1800039a5  call    cs:__imp_RtlInitUnicodeString
0x1800039ac  nop     dword ptr [rax+rax+00h]
0x1800039b1  mov     r8b, 1; CaseInSensitive
0x1800039b4  lea     rcx, [rbp+String1]; String1
0x1800039b8  mov     rdx, rsi; String2
0x1800039bb  call    cs:__imp_RtlPrefixUnicodeString
0x1800039c2  nop     dword ptr [rax+rax+00h]
0x1800039c7  cmp     al, 1
0x1800039c9  jnz     short loc_180003A42
0x1800039cb  mov     rdx, rdi
0x1800039ce  lea     rcx, [rbp+var_40]
0x1800039d2  call    ?build_managed_unicode_string@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBV1234@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::build_managed_unicode_string(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x1800039d7  mov     dl, r14b
0x1800039da  lea     rcx, [rbp+var_40]
0x1800039de  call    ??$normalize@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@path_normalizer@vemgr@appv@@CAJAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@2@_N@Z; appv::vemgr::path_normalizer::normalize<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,bool)
0x1800039e3  mov     ebx, eax
0x1800039e5  test    eax, eax
0x1800039e7  js      loc_180003AE5
0x1800039ed  lea     rdx, [rbp+var_20]
0x1800039f1  lea     rcx, [rbp+var_40]
0x1800039f5  call    ?swap@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEAV1234@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::swap(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x1800039fa  mov     rcx, [rbp+P]; P
0x1800039fe  test    rcx, rcx
0x180003a01  jz      short loc_180003A11
0x180003a03  xor     edx, edx; Tag
0x180003a05  call    cs:__imp_ExFreePoolWithTag
0x180003a0c  nop     dword ptr [rax+rax+00h]
0x180003a11  lea     rdx, [rbp+var_20]
0x180003a15  mov     rcx, rdi
0x180003a18  call    ?swap@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEAV1234@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::swap(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x180003a1d  mov     rcx, [rbp+var_18]; P
0x180003a21  test    rcx, rcx
0x180003a24  jz      short loc_180003A34
0x180003a26  xor     edx, edx; Tag
0x180003a28  call    cs:__imp_ExFreePoolWithTag
0x180003a2f  nop     dword ptr [rax+rax+00h]
0x180003a34  mov     eax, ebx
0x180003a36  add     rsp, 70h
0x180003a3a  pop     r14
0x180003a3c  pop     rdi
0x180003a3d  pop     rsi
0x180003a3e  pop     rbx
0x180003a3f  pop     rbp
0x180003a40  retn
0x180003a42  mov     eax, [rdi]
0x180003a44  shr     eax, 1
0x180003a46  cmp     eax, 0FFFFh
0x180003a4b  ja      short loc_180003AA6
0x180003a4d  cmp     ax, 2
0x180003a51  jb      short loc_180003AA6
0x180003a53  mov     r8, [rdi+8]
0x180003a57  movzx   ecx, word ptr [r8]
0x180003a5b  lea     eax, [rcx-61h]
0x180003a5e  cmp     ax, 19h
0x180003a62  jbe     short loc_180003A6E
0x180003a64  sub     cx, 41h ; 'A'
0x180003a68  cmp     cx, 19h
0x180003a6c  ja      short loc_180003AA6
0x180003a6e  cmp     word ptr [r8+2], 3Ah ; ':'
0x180003a74  jnz     short loc_180003AA6
0x180003a76  mov     r8d, 4
0x180003a7c  lea     rcx, [rbp+var_40]
0x180003a80  mov     rdx, rbx
0x180003a83  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x180003a88  mov     ebx, eax
0x180003a8a  test    eax, eax
0x180003a8c  js      short loc_180003AAB
0x180003a8e  mov     rdx, rsi
0x180003a91  lea     rcx, [rbp+var_40]
0x180003a95  call    ?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(_UNICODE_STRING const &)
0x180003a9a  mov     ebx, eax
0x180003a9c  test    eax, eax
0x180003a9e  jns     loc_1800039D7
0x180003aa4  jmp     short loc_180003AAB
0x180003aa6  mov     ebx, 0C0000039h
0x180003aab  mov     rcx, [rbp+P]; P
0x180003aaf  test    rcx, rcx
0x180003ab2  jz      short loc_180003AC2
0x180003ab4  xor     edx, edx; Tag
0x180003ab6  call    cs:__imp_ExFreePoolWithTag
0x180003abd  nop     dword ptr [rax+rax+00h]
0x180003ac2  test    ebx, ebx
0x180003ac4  js      loc_180003A1D
0x180003aca  jmp     loc_180003A11
0x180003acf  mov     rdx, rdi
0x180003ad2  lea     rcx, [rbp+var_40]
0x180003ad6  call    ?build_managed_unicode_string@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBV1234@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::build_managed_unicode_string(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x180003adb  mov     ebx, eax
0x180003add  test    eax, eax
0x180003adf  jns     loc_1800039D7
0x180003ae5  mov     rcx, [rbp+P]; P
0x180003ae9  test    rcx, rcx
0x180003aec  jz      loc_180003A1D
0x180003af2  xor     edx, edx; Tag
0x180003af4  call    cs:__imp_ExFreePoolWithTag
0x180003afb  nop     dword ptr [rax+rax+00h]
0x180003b00  jmp     loc_180003A1D
```
