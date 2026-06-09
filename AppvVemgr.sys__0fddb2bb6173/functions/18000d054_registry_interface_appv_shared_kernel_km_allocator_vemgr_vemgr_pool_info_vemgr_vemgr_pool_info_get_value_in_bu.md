# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value_in_buffer(void *,wchar_t const *,appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)

- ea: `0x18000d054`
- end: `0x18000d17b`
- name: `?get_value_in_buffer@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJPEAXPEB_WAEAV?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `295`
- prototype: `unsigned int __fastcall(HANDLE KeyHandle, wchar_t *, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ce10`
- `0x18000ce9c`
- `0x18000cf74`

## callees

- `0x18000d054`
- `0x18000e8d4`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x18000d0fa`
- `ntoskrnl!ZwQueryValueKey` at `0x18000d157`
- `ntoskrnl!ZwQueryValueKey` at `0x18000d0fa`
- `ntoskrnl!ZwQueryValueKey` at `0x18000d157`

## pseudocode

```c
unsigned int __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value_in_buffer(
        HANDLE KeyHandle,
        wchar_t *a2,
        __int64 a3)
{
  __int64 v6; // rax
  unsigned int v7; // edx
  unsigned __int16 v8; // cx
  unsigned int result; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+50h] [rbp+8h] BYREF

  if ( !KeyHandle || !a2 )
    return -1073741811;
  v6 = -1;
  ValueName = 0;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  if ( (unsigned int)(2 * v6) > 0xFFFF )
    v8 = -1;
  else
    v8 = 2 * v6;
  if ( (v7 > 0xFFFF ? 0xC0000000 : 0) == 0xC0000000 )
  {
    if ( v7 > 0xFFFF )
      return v7 > 0xFFFF ? 0xC0000095 : 0;
  }
  else
  {
    ValueName.Buffer = a2;
    ValueName.MaximumLength = v8;
    ValueName.Length = v8;
  }
  ResultLength = 0;
  result = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, 0, 0, &ResultLength);
  if ( result == -1073741789 || result == -2147483643 )
  {
    if ( (int)appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(
                a3,
                ResultLength,
                v10,
                v11) >= 0 )
      return ZwQueryValueKey(
               KeyHandle,
               &ValueName,
               KeyValueFullInformation,
               *(PVOID *)(a3 + 8),
               *(_DWORD *)a3,
               &ResultLength);
    else
      return -1073741670;
  }
  return result;
}

```

## disassembly

```asm
0x18000d054  mov     [rsp+arg_8], rbx
0x18000d059  mov     [rsp+arg_10], rsi
0x18000d05e  push    rdi
0x18000d05f  sub     rsp, 40h
0x18000d063  xor     esi, esi
0x18000d065  mov     rdi, r8
0x18000d068  mov     r9, rdx
0x18000d06b  mov     rbx, rcx
0x18000d06e  test    rcx, rcx
0x18000d071  jz      loc_18000D165
0x18000d077  test    rdx, rdx
0x18000d07a  jz      loc_18000D165
0x18000d080  xorps   xmm0, xmm0
0x18000d083  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d087  movups  xmmword ptr [rsp+48h+ValueName.Length], xmm0
0x18000d08c  inc     rax
0x18000d08f  cmp     [rdx+rax*2], si
0x18000d093  jnz     short loc_18000D08C
0x18000d095  lea     rdx, [rax+rax]
0x18000d099  mov     r11d, 0FFFFh
0x18000d09f  cmp     edx, r11d
0x18000d0a2  ja      short loc_18000D0A9
0x18000d0a4  movzx   ecx, dx
0x18000d0a7  jmp     short loc_18000D0AC
0x18000d0a9  mov     ecx, r11d
0x18000d0ac  cmp     r11d, edx
0x18000d0af  mov     r10d, 0C0000000h
0x18000d0b5  sbb     r8d, r8d
0x18000d0b8  and     r8d, 0C0000095h
0x18000d0bf  mov     eax, r8d
0x18000d0c2  and     eax, r10d
0x18000d0c5  cmp     eax, r10d
0x18000d0c8  jz      short loc_18000D12B
0x18000d0ca  mov     [rsp+48h+ValueName.Buffer], r9
0x18000d0cf  mov     [rsp+48h+ValueName.MaximumLength], cx
0x18000d0d4  mov     [rsp+48h+ValueName.Length], cx
0x18000d0d9  xor     r9d, r9d; KeyValueInformation
0x18000d0dc  mov     [rsp+48h+arg_0], esi
0x18000d0e0  lea     rax, [rsp+48h+arg_0]
0x18000d0e5  mov     rcx, rbx; KeyHandle
0x18000d0e8  mov     [rsp+48h+ResultLength], rax; ResultLength
0x18000d0ed  lea     rdx, [rsp+48h+ValueName]; ValueName
0x18000d0f2  mov     [rsp+48h+Length], esi; Length
0x18000d0f6  lea     r8d, [r9+1]; KeyValueInformationClass
0x18000d0fa  call    cs:__imp_ZwQueryValueKey
0x18000d101  nop     dword ptr [rax+rax+00h]
0x18000d106  cmp     eax, 0C0000023h
0x18000d10b  jz      short loc_18000D114
0x18000d10d  cmp     eax, 80000005h
0x18000d112  jnz     short loc_18000D16A
0x18000d114  mov     edx, [rsp+48h+arg_0]
0x18000d118  mov     rcx, rdi
0x18000d11b  call    ?resize@?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(ulong)
0x18000d120  test    eax, eax
0x18000d122  jns     short loc_18000D135
0x18000d124  mov     eax, 0C000009Ah
0x18000d129  jmp     short loc_18000D16A
0x18000d12b  cmp     edx, r11d
0x18000d12e  jbe     short loc_18000D0D9
0x18000d130  mov     eax, r8d
0x18000d133  jmp     short loc_18000D16A
0x18000d135  mov     r9, [rdi+8]; KeyValueInformation
0x18000d139  lea     rax, [rsp+48h+arg_0]
0x18000d13e  mov     [rsp+48h+ResultLength], rax; ResultLength
0x18000d143  lea     rdx, [rsp+48h+ValueName]; ValueName
0x18000d148  mov     eax, [rdi]
0x18000d14a  mov     r8d, 1; KeyValueInformationClass
0x18000d150  mov     rcx, rbx; KeyHandle
0x18000d153  mov     [rsp+48h+Length], eax; Length
0x18000d157  call    cs:__imp_ZwQueryValueKey
0x18000d15e  nop     dword ptr [rax+rax+00h]
0x18000d163  jmp     short loc_18000D16A
0x18000d165  mov     eax, 0C000000Dh
0x18000d16a  mov     rbx, [rsp+48h+arg_8]
0x18000d16f  mov     rsi, [rsp+48h+arg_10]
0x18000d174  add     rsp, 40h
0x18000d178  pop     rdi
0x18000d179  retn
```
