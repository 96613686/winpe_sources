# RunVirtualInfoStore<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::GetRegistryInfo(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,bool &)

- ea: `0x180017c7c`
- end: `0x180018269`
- name: `?GetRegistryInfo@?$RunVirtualInfoStore@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SA_NAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@0AEA_N@Z`
- size: `1517`
- prototype: `char __fastcall(__int64, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018b9c`

## callees

- `0x180003f50`
- `0x180005430`
- `0x18000a958`
- `0x18000a9e4`
- `0x18000acbc`
- `0x18000cf74`
- `0x18000e23c`
- `0x180017c7c`
- `0x180019014`
- `0x18001ad74`
- `0x18001b3cc`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180017ed5`
- `ntoskrnl!ExAllocatePool2` at `0x180017ed5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800180d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800180ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001817f`
- `ntoskrnl!ExFreePoolWithTag` at `0x180018196`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001822f`
- `ntoskrnl!ExFreePoolWithTag` at `0x180018246`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800180d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800180ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001817f`
- `ntoskrnl!ExFreePoolWithTag` at `0x180018196`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001822f`
- `ntoskrnl!ExFreePoolWithTag` at `0x180018246`
- `ntoskrnl!ZwClose` at `0x180017e4e`
- `ntoskrnl!ZwClose` at `0x1800180a8`
- `ntoskrnl!ZwClose` at `0x1800180bc`
- `ntoskrnl!ZwClose` at `0x180018154`
- `ntoskrnl!ZwClose` at `0x180018168`
- `ntoskrnl!ZwClose` at `0x180018204`
- `ntoskrnl!ZwClose` at `0x180018218`
- `ntoskrnl!ZwClose` at `0x180017e4e`
- `ntoskrnl!ZwClose` at `0x1800180a8`
- `ntoskrnl!ZwClose` at `0x1800180bc`
- `ntoskrnl!ZwClose` at `0x180018154`
- `ntoskrnl!ZwClose` at `0x180018168`
- `ntoskrnl!ZwClose` at `0x180018204`
- `ntoskrnl!ZwClose` at `0x180018218`
- `ntoskrnl!RtlInitUnicodeString` at `0x180017cbb`
- `ntoskrnl!RtlInitUnicodeString` at `0x180017d5a`
- `ntoskrnl!RtlInitUnicodeString` at `0x180017ef6`
- `ntoskrnl!RtlInitUnicodeString` at `0x180017cbb`
- `ntoskrnl!RtlInitUnicodeString` at `0x180017d5a`
- `ntoskrnl!RtlInitUnicodeString` at `0x180017ef6`

## string_xrefs

- `0x180017d6c`: `\REGISTRY\USER\`
- `0x180017e1a`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\`
- `0x180017e2a`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\`
- `0x180017cf5`: `unVirtualInfoStore::GetRegistryInfo() - Failed to build process path from %s. Error: %d`
- `0x180017d36`: `unVirtualInfoStore::GetRegistryInfo() - Failed to parse process path from %s`
- `0x180017e35`: `unVirtualInfoStore::GetRegistryInfo() - Failed to open registry key %s. Error: %d`
- `0x180017eb0`: `unVirtualInfoStore::GetRegistryInfo() - Succeeded in opening registry key %s.`
- `0x1800181ab`: `unVirtualInfoStore::GetRegistryInfo() - Failed to reset moniker`
- `0x180017f72`: `unVirtualInfoStore::ReadDefaultValue() - Failed to get registry value from registry key %s. Error: %d`

## pseudocode

```c
char __fastcall RunVirtualInfoStore<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::GetRegistryInfo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _BYTE *a4)
{
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // eax
  unsigned int v11; // ecx
  __int64 v12; // r9
  PVOID v13; // r9
  __int64 v14; // r9
  unsigned int v15; // eax
  __int64 v16; // rdx
  HANDLE v17; // rbx
  wchar_t *Buffer; // rdx
  PVOID v19; // rdx
  HANDLE v20; // rbx
  int v21; // eax
  HANDLE v22; // rcx
  PVOID v23; // rdx
  PVOID v24; // r9
  __int64 Pool2; // rax
  _QWORD *v26; // rdi
  _DWORD *v27; // r15
  volatile signed __int32 *v28; // rsi
  HANDLE v29; // rdi
  int value; // eax
  HANDLE v31; // rcx
  char v32; // r15
  HANDLE v34[2]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v35; // [rsp+40h] [rbp-29h] BYREF
  PVOID v36; // [rsp+48h] [rbp-21h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING v38; // [rsp+60h] [rbp-9h] BYREF
  struct _UNICODE_STRING v39; // [rsp+70h] [rbp+7h] BYREF
  HANDLE Handle; // [rsp+E8h] [rbp+7Fh] BYREF

  v35 = 0;
  *a4 = 1;
  v36 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v10 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::build_managed_unicode_string(
          (__int64)&v35,
          (unsigned int *)a1,
          v8,
          v9);
  if ( v10 < 0 )
  {
    v11 = *(_DWORD *)a1 >> 1;
    if ( v11 <= 0xFFFF && (_WORD)v11 )
      v12 = *(_QWORD *)(a1 + 8);
    else
      v12 = 0;
    LogWrite(1, 0, L"unVirtualInfoStore::GetRegistryInfo() - Failed to build process path from %s. Error: %d", v12, v10);
LABEL_96:
    if ( v36 )
      ExFreePoolWithTag(v36, 0);
    return 0;
  }
  if ( !(unsigned __int8)appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::trim_front(&v35) )
  {
    if ( (unsigned int)v35 >> 1 > 0xFFFF || (v13 = v36, !(unsigned __int16)((unsigned int)v35 >> 1)) )
      v13 = 0;
    LogWrite(1, 0, L"unVirtualInfoStore::GetRegistryInfo() - Failed to parse process path from %s", v13);
    goto LABEL_96;
  }
  *(_QWORD *)&v38.Length = 0;
  v38.Buffer = 0;
  RtlInitUnicodeString(&v39, 0);
  appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
    (__int64)&v38,
    L"\\REGISTRY\\USER\\",
    15,
    v14);
  v15 = *(_DWORD *)a3 >> 1;
  if ( v15 <= 0xFFFF && (_WORD)v15 )
    v16 = *(_QWORD *)(a3 + 8);
  else
    v16 = 0;
  appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
    &v38,
    v16);
  appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
    &v38,
    (__int64)L"\\SOFTWARE\\Microsoft\\AppV\\Client\\RunVirtual\\");
  v17 = 0;
  v34[0] = 0;
  Handle = 0;
  if ( *(_DWORD *)&v38.Length >> 1 > 0xFFFFu || (Buffer = v38.Buffer, !(unsigned __int16)(*(_DWORD *)&v38.Length >> 1)) )
    Buffer = 0;
  if ( (int)registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
              0,
              Buffer,
              v34) >= 0 )
  {
    if ( (unsigned int)v35 >> 1 > 0xFFFF || (v19 = v36, !(unsigned __int16)((unsigned int)v35 >> 1)) )
      v19 = 0;
    v20 = v34[0];
    if ( (int)registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
                v34[0],
                v19,
                &Handle) >= 0 )
    {
      *a4 = 0;
      goto LABEL_35;
    }
    v17 = Handle;
  }
  v21 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
          0,
          L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\AppV\\Client\\RunVirtual\\",
          v34);
  if ( v21 < 0 )
  {
    LogWrite(
      1,
      0,
      L"unVirtualInfoStore::GetRegistryInfo() - Failed to open registry key %s. Error: %d",
      L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\AppV\\Client\\RunVirtual\\",
      v21);
    if ( v17 )
      ZwClose(v17);
    v22 = v34[0];
    if ( !v34[0] )
      goto LABEL_94;
    goto LABEL_93;
  }
  if ( (unsigned int)v35 >> 1 > 0xFFFF || (v23 = v36, !(unsigned __int16)((unsigned int)v35 >> 1)) )
    v23 = 0;
  v20 = v34[0];
  if ( (int)registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
              v34[0],
              v23,
              &Handle) < 0 )
  {
LABEL_89:
    v31 = Handle;
    if ( !Handle )
    {
LABEL_91:
      if ( !v20 )
        goto LABEL_94;
      v22 = v20;
LABEL_93:
      ZwClose(v22);
LABEL_94:
      if ( v38.Buffer )
        ExFreePoolWithTag(v38.Buffer, 0);
      goto LABEL_96;
    }
LABEL_90:
    ZwClose(v31);
    goto LABEL_91;
  }
LABEL_35:
  if ( (unsigned int)v35 >> 1 > 0xFFFF || (v24 = v36, !(unsigned __int16)((unsigned int)v35 >> 1)) )
    v24 = 0;
  LogWrite(3, 0, L"unVirtualInfoStore::GetRegistryInfo() - Succeeded in opening registry key %s.", v24);
  *(_OWORD *)v34 = 0;
  Pool2 = ExAllocatePool2(64, 32, 1715758931);
  v26 = (_QWORD *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = 0;
    *(_QWORD *)(Pool2 + 8) = 0;
    RtlInitUnicodeString((PUNICODE_STRING)(Pool2 + 16), 0);
  }
  else
  {
    v26 = 0;
  }
  kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
    v34,
    v26);
  v27 = v34[0];
  v28 = (volatile signed __int32 *)v34[1];
  if ( !v34[0] || !v34[1] || !*((_DWORD *)v34[1] + 2) )
  {
    LogWrite(1, 0, L"unVirtualInfoStore::GetRegistryInfo() - Failed to reset moniker");
    if ( v28 )
    {
      if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
        if ( !_InterlockedDecrement(v28 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 16LL))(v28);
      }
    }
    goto LABEL_89;
  }
  _InterlockedIncrement((volatile signed __int32 *)v34[1] + 2);
  v29 = Handle;
  value = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
            Handle,
            (__int64)&dword_18001E3EC,
            (__int64)v27);
  if ( value < 0 && value != -1073741772 )
  {
    LogWrite(
      1,
      0,
      L"unVirtualInfoStore::ReadDefaultValue() - Failed to get registry value from registry key %s. Error: %d",
      &dword_18001E3EC,
      value);
    if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
      if ( !_InterlockedDecrement(v28 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 16LL))(v28);
    }
    if ( v28 )
    {
      if ( !_InterlockedDecrement(v28 + 2) )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
        if ( !_InterlockedDecrement(v28 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 16LL))(v28);
      }
    }
    if ( !v29 )
      goto LABEL_91;
    v31 = v29;
    goto LABEL_90;
  }
  if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
    if ( !_InterlockedDecrement(v28 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 16LL))(v28);
  }
  if ( *v27 > 2u )
  {
    *(_QWORD *)a2 = v27;
    kernel_std::detail::shared_count::operator=(
      (volatile signed __int32 **)(a2 + 8),
      (volatile signed __int32 **)&v34[1]);
    if ( v28 )
    {
      if ( !_InterlockedDecrement(v28 + 2) )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
        if ( !_InterlockedDecrement(v28 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 16LL))(v28);
      }
    }
    if ( v29 )
      ZwClose(v29);
    if ( v20 )
      ZwClose(v20);
    if ( v38.Buffer )
      ExFreePoolWithTag(v38.Buffer, 0);
    if ( v36 )
      ExFreePoolWithTag(v36, 0);
    return 1;
  }
  else
  {
    v32 = RunVirtualInfoStore<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ReadValues(
            &Handle,
            a1,
            a2);
    if ( v28 )
    {
      if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
        if ( !_InterlockedDecrement(v28 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 16LL))(v28);
      }
    }
    if ( v29 )
      ZwClose(v29);
    if ( v20 )
      ZwClose(v20);
    if ( v38.Buffer )
      ExFreePoolWithTag(v38.Buffer, 0);
    if ( v36 )
      ExFreePoolWithTag(v36, 0);
    return v32;
  }
}

```

## disassembly

```asm
0x180017c7c  push    rbp
0x180017c7e  push    rbx
0x180017c7f  push    rsi
0x180017c80  push    rdi
0x180017c81  push    r12
0x180017c83  push    r13
0x180017c85  push    r14
0x180017c87  push    r15
0x180017c89  lea     rbp, [rsp-1Fh]
0x180017c8e  sub     rsp, 88h
0x180017c95  mov     r13, rdx
0x180017c98  mov     r12, rcx
0x180017c9b  xor     r14d, r14d
0x180017c9e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180017ca2  mov     r15d, 1
0x180017ca8  mov     [rbp+57h+var_80], r14
0x180017cac  xor     edx, edx; SourceString
0x180017cae  mov     [r9], r15b
0x180017cb1  mov     [rbp+57h+var_78], r14
0x180017cb5  mov     rsi, r9
0x180017cb8  mov     rbx, r8
0x180017cbb  call    cs:__imp_RtlInitUnicodeString
0x180017cc2  nop     dword ptr [rax+rax+00h]
0x180017cc7  mov     rdx, r12
0x180017cca  lea     rcx, [rbp+57h+var_80]
0x180017cce  call    ?build_managed_unicode_string@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBV1234@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::build_managed_unicode_string(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x180017cd3  test    eax, eax
0x180017cd5  jns     short loc_180017D0F
0x180017cd7  mov     ecx, [r12]
0x180017cdb  mov     edi, 0FFFFh
0x180017ce0  shr     ecx, 1
0x180017ce2  cmp     ecx, edi
0x180017ce4  ja      short loc_180017CF2
0x180017ce6  test    cx, cx
0x180017ce9  jz      short loc_180017CF2
0x180017ceb  mov     r9, [r12+8]
0x180017cf0  jmp     short loc_180017CF5
0x180017cf2  mov     r9, r14
0x180017cf5  lea     r8, aUnvirtualinfos_6; "unVirtualInfoStore::GetRegistryInfo() -"...
0x180017cfc  mov     [rsp+0C0h+var_A0], eax
0x180017d00  xor     edx, edx
0x180017d02  mov     ecx, r15d
0x180017d05  call    LogWrite
0x180017d0a  jmp     loc_18001823B
0x180017d0f  lea     rcx, [rbp+57h+var_80]
0x180017d13  call    ?trim_front@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAA_N_W@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::trim_front(wchar_t)
0x180017d18  test    al, al
0x180017d1a  jnz     short loc_180017D4C
0x180017d1c  mov     eax, dword ptr [rbp+57h+var_80]
0x180017d1f  mov     edi, 0FFFFh
0x180017d24  shr     eax, 1
0x180017d26  cmp     eax, edi
0x180017d28  ja      short loc_180017D33
0x180017d2a  mov     r9, [rbp+57h+var_78]
0x180017d2e  test    ax, ax
0x180017d31  jnz     short loc_180017D36
0x180017d33  mov     r9, r14
0x180017d36  lea     r8, aUnvirtualinfos_2; "unVirtualInfoStore::GetRegistryInfo() -"...
0x180017d3d  xor     edx, edx
0x180017d3f  mov     ecx, r15d
0x180017d42  call    LogWrite
0x180017d47  jmp     loc_18001823B
0x180017d4c  xor     edx, edx; SourceString
0x180017d4e  mov     [rbp+57h+var_60], r14
0x180017d52  lea     rcx, [rbp+57h+var_50]; DestinationString
0x180017d56  mov     [rbp+57h+P], r14
0x180017d5a  call    cs:__imp_RtlInitUnicodeString
0x180017d61  nop     dword ptr [rax+rax+00h]
0x180017d66  mov     r8d, 0Fh
0x180017d6c  lea     rdx, aRegistryUser; "\\REGISTRY\\USER\\"
0x180017d73  lea     rcx, [rbp+57h+var_60]
0x180017d77  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x180017d7c  mov     eax, [rbx]
0x180017d7e  mov     edi, 0FFFFh
0x180017d83  shr     eax, 1
0x180017d85  cmp     eax, edi
0x180017d87  ja      short loc_180017D94
0x180017d89  test    ax, ax
0x180017d8c  jz      short loc_180017D94
0x180017d8e  mov     rdx, [rbx+8]
0x180017d92  jmp     short loc_180017D97
0x180017d94  mov     rdx, r14
0x180017d97  lea     rcx, [rbp+57h+var_60]
0x180017d9b  call    ?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJPEB_W@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(wchar_t const *)
0x180017da0  lea     rdx, aSoftwareMicros; "\\SOFTWARE\\Microsoft\\AppV\\Client\\Ru"...
0x180017da7  lea     rcx, [rbp+57h+var_60]
0x180017dab  call    ?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJPEB_W@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(wchar_t const *)
0x180017db0  mov     eax, dword ptr [rbp+57h+var_60]
0x180017db3  mov     rbx, r14
0x180017db6  shr     eax, 1
0x180017db8  mov     [rbp+57h+var_90], r14
0x180017dbc  mov     [rbp+57h+Handle], rbx
0x180017dc0  cmp     eax, edi
0x180017dc2  ja      short loc_180017DCD
0x180017dc4  mov     rdx, [rbp+57h+P]
0x180017dc8  test    ax, ax
0x180017dcb  jnz     short loc_180017DD0
0x180017dcd  mov     rdx, r14
0x180017dd0  lea     r8, [rbp+57h+var_90]
0x180017dd4  xor     ecx, ecx
0x180017dd6  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180017ddb  test    eax, eax
0x180017ddd  js      short loc_180017E14
0x180017ddf  mov     eax, dword ptr [rbp+57h+var_80]
0x180017de2  shr     eax, 1
0x180017de4  cmp     eax, edi
0x180017de6  ja      short loc_180017DF1
0x180017de8  mov     rdx, [rbp+57h+var_78]
0x180017dec  test    ax, ax
0x180017def  jnz     short loc_180017DF4
0x180017df1  mov     rdx, r14
0x180017df4  mov     rbx, [rbp+57h+var_90]
0x180017df8  lea     r8, [rbp+57h+Handle]
0x180017dfc  mov     rcx, rbx
0x180017dff  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180017e04  test    eax, eax
0x180017e06  js      short loc_180017E10
0x180017e08  mov     [rsi], r14b
0x180017e0b  jmp     loc_180017E99
0x180017e10  mov     rbx, [rbp+57h+Handle]
0x180017e14  lea     r8, [rbp+57h+var_90]
0x180017e18  xor     ecx, ecx
0x180017e1a  lea     rdx, aRegistryMachin_7; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x180017e21  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180017e26  test    eax, eax
0x180017e28  jns     short loc_180017E6C
0x180017e2a  lea     r9, aRegistryMachin_7; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x180017e31  mov     [rsp+0C0h+var_A0], eax
0x180017e35  lea     r8, aUnvirtualinfos_4; "unVirtualInfoStore::GetRegistryInfo() -"...
0x180017e3c  xor     edx, edx
0x180017e3e  mov     ecx, r15d
0x180017e41  call    LogWrite
0x180017e46  test    rbx, rbx
0x180017e49  jz      short loc_180017E5A
0x180017e4b  mov     rcx, rbx; Handle
0x180017e4e  call    cs:__imp_ZwClose
0x180017e55  nop     dword ptr [rax+rax+00h]
0x180017e5a  mov     rcx, [rbp+57h+var_90]
0x180017e5e  test    rcx, rcx
0x180017e61  jz      loc_180018224
0x180017e67  jmp     loc_180018218
0x180017e6c  mov     eax, dword ptr [rbp+57h+var_80]
0x180017e6f  shr     eax, 1
0x180017e71  cmp     eax, edi
0x180017e73  ja      short loc_180017E7E
0x180017e75  mov     rdx, [rbp+57h+var_78]
0x180017e79  test    ax, ax
0x180017e7c  jnz     short loc_180017E81
0x180017e7e  mov     rdx, r14
0x180017e81  mov     rbx, [rbp+57h+var_90]
0x180017e85  lea     r8, [rbp+57h+Handle]
0x180017e89  mov     rcx, rbx
0x180017e8c  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180017e91  test    eax, eax
0x180017e93  js      loc_1800181FB
0x180017e99  mov     eax, dword ptr [rbp+57h+var_80]
0x180017e9c  shr     eax, 1
0x180017e9e  cmp     eax, edi
0x180017ea0  ja      short loc_180017EAB
0x180017ea2  mov     r9, [rbp+57h+var_78]
0x180017ea6  test    ax, ax
0x180017ea9  jnz     short loc_180017EAE
0x180017eab  mov     r9, r14
0x180017eae  xor     edx, edx
0x180017eb0  lea     r8, aUnvirtualinfos; "unVirtualInfoStore::GetRegistryInfo() -"...
0x180017eb7  lea     ecx, [rdx+3]
0x180017eba  call    LogWrite
0x180017ebf  mov     edx, 20h ; ' '
0x180017ec4  xorps   xmm0, xmm0
0x180017ec7  mov     r8d, 66446753h
0x180017ecd  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180017ed2  lea     ecx, [rdx+20h]
0x180017ed5  call    cs:__imp_ExAllocatePool2
0x180017edc  nop     dword ptr [rax+rax+00h]
0x180017ee1  mov     rdi, rax
0x180017ee4  test    rax, rax
0x180017ee7  jz      short loc_180017F04
0x180017ee9  lea     rcx, [rax+10h]; DestinationString
0x180017eed  mov     [rax], r14
0x180017ef0  xor     edx, edx; SourceString
0x180017ef2  mov     [rax+8], r14
0x180017ef6  call    cs:__imp_RtlInitUnicodeString
0x180017efd  nop     dword ptr [rax+rax+00h]
0x180017f02  jmp     short loc_180017F07
0x180017f04  mov     rdi, r14
0x180017f07  mov     rdx, rdi
0x180017f0a  lea     rcx, [rbp+57h+var_90]
0x180017f0e  call    ??$reset@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAAXPEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x180017f13  mov     r15, [rbp+57h+var_90]
0x180017f17  mov     rsi, [rbp+57h+var_90+8]
0x180017f1b  test    r15, r15
0x180017f1e  jz      loc_1800181A9
0x180017f24  test    rsi, rsi
0x180017f27  jz      loc_1800181A9
0x180017f2d  mov     eax, [rsi+8]
0x180017f30  test    eax, eax
0x180017f32  jz      loc_1800181A9
0x180017f38  lock inc dword ptr [rsi+8]
0x180017f3c  mov     rdi, [rbp+57h+Handle]
0x180017f40  lea     rdx, dword_18001E3EC
0x180017f47  mov     rcx, rdi
0x180017f4a  mov     r8, r15
0x180017f4d  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x180017f52  test    eax, eax
0x180017f54  jns     loc_18001800B
0x180017f5a  cmp     eax, 0C0000034h
0x180017f5f  jz      loc_18001800B
0x180017f65  xor     edx, edx
0x180017f67  mov     [rsp+0C0h+var_A0], eax
0x180017f6b  lea     r9, dword_18001E3EC
0x180017f72  lea     r8, aUnvirtualinfos_0; "unVirtualInfoStore::ReadDefaultValue() "...
0x180017f79  lea     ecx, [rdx+1]
0x180017f7c  call    LogWrite
0x180017f81  or      r14d, 0FFFFFFFFh
0x180017f85  mov     eax, r14d
0x180017f88  lock xadd [rsi+8], eax
0x180017f8d  add     eax, r14d
0x180017f90  jnz     short loc_180017FBD
0x180017f92  mov     rax, [rsi]
0x180017f95  mov     rcx, rsi
0x180017f98  mov     rax, [rax+8]
0x180017f9c  call    _guard_dispatch_icall
0x180017fa1  mov     eax, r14d
0x180017fa4  lock xadd [rsi+0Ch], eax
0x180017fa9  add     eax, r14d
0x180017fac  jnz     short loc_180017FBD
0x180017fae  mov     rax, [rsi]
0x180017fb1  mov     rcx, rsi
0x180017fb4  mov     rax, [rax+10h]
0x180017fb8  call    _guard_dispatch_icall
0x180017fbd  test    rsi, rsi
0x180017fc0  jz      short loc_180017FFA
0x180017fc2  mov     eax, r14d
0x180017fc5  lock xadd [rsi+8], eax
0x180017fca  add     eax, r14d
0x180017fcd  jnz     short loc_180017FFA
0x180017fcf  mov     rax, [rsi]
0x180017fd2  mov     rcx, rsi
0x180017fd5  mov     rax, [rax+8]
0x180017fd9  call    _guard_dispatch_icall
0x180017fde  mov     eax, r14d
0x180017fe1  lock xadd [rsi+0Ch], eax
0x180017fe6  add     eax, r14d
0x180017fe9  jnz     short loc_180017FFA
0x180017feb  mov     rax, [rsi]
0x180017fee  mov     rcx, rsi
0x180017ff1  mov     rax, [rax+10h]
0x180017ff5  call    _guard_dispatch_icall
0x180017ffa  test    rdi, rdi
0x180017ffd  jz      loc_180018210
0x180018003  mov     rcx, rdi
0x180018006  jmp     loc_180018204
0x18001800b  or      r14d, 0FFFFFFFFh
0x18001800f  mov     eax, r14d
0x180018012  lock xadd [rsi+8], eax
0x180018017  add     eax, r14d
0x18001801a  jnz     short loc_180018047
0x18001801c  mov     rax, [rsi]
0x18001801f  mov     rcx, rsi
0x180018022  mov     rax, [rax+8]
0x180018026  call    _guard_dispatch_icall
0x18001802b  mov     eax, r14d
0x18001802e  lock xadd [rsi+0Ch], eax
0x180018033  add     eax, r14d
0x180018036  jnz     short loc_180018047
0x180018038  mov     rax, [rsi]
0x18001803b  mov     rcx, rsi
0x18001803e  mov     rax, [rax+10h]
0x180018042  call    _guard_dispatch_icall
0x180018047  cmp     dword ptr [r15], 2
0x18001804b  ja      loc_1800180FE
0x180018051  mov     r8, r13
0x180018054  lea     rcx, [rbp+57h+Handle]
0x180018058  mov     rdx, r12
0x18001805b  call    ?ReadValues@?$RunVirtualInfoStore@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CA_NAEAVhandle@kernel@shared@appv@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@345@AEAV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@@Z; RunVirtualInfoStore<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ReadValues(appv::shared::kernel::handle &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &)
0x180018060  mov     r15b, al
0x180018063  test    rsi, rsi
0x180018066  jz      short loc_1800180A0
0x180018068  mov     ecx, r14d
0x18001806b  lock xadd [rsi+8], ecx
0x180018070  add     ecx, r14d
0x180018073  jnz     short loc_1800180A0
0x180018075  mov     rcx, [rsi]
0x180018078  mov     rax, [rcx+8]
0x18001807c  mov     rcx, rsi
0x18001807f  call    _guard_dispatch_icall
0x180018084  mov     eax, r14d
0x180018087  lock xadd [rsi+0Ch], eax
0x18001808c  add     eax, r14d
0x18001808f  jnz     short loc_1800180A0
0x180018091  mov     rax, [rsi]
0x180018094  mov     rcx, rsi
0x180018097  mov     rax, [rax+10h]
0x18001809b  call    _guard_dispatch_icall
0x1800180a0  test    rdi, rdi
0x1800180a3  jz      short loc_1800180B4
0x1800180a5  mov     rcx, rdi; Handle
0x1800180a8  call    cs:__imp_ZwClose
0x1800180af  nop     dword ptr [rax+rax+00h]
0x1800180b4  test    rbx, rbx
  ... truncated ...
```
