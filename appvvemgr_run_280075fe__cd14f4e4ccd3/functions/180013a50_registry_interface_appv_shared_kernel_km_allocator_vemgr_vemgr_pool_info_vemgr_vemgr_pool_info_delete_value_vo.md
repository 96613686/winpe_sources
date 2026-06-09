# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_value(void *,wchar_t const *)

- ea: `0x180013a50`
- end: `0x180013ae8`
- name: `?delete_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W@Z`
- size: `152`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180013d4c`
- `0x1800145a8`

## callees

- `0x180013a50`

## import_xrefs

- `ntoskrnl!ZwDeleteValueKey` at `0x180013ac5`
- `ntoskrnl!ZwDeleteValueKey` at `0x180013ac5`

## pseudocode

```c
unsigned int __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_value(
        HANDLE KeyHandle,
        wchar_t *a2)
{
  __int64 v4; // rdx
  unsigned int v5; // edx
  unsigned __int16 v6; // cx
  struct _UNICODE_STRING ValueName; // [rsp+20h] [rbp-18h] BYREF

  if ( !KeyHandle || !a2 )
    return -1073741811;
  v4 = -1;
  ValueName = 0;
  do
    ++v4;
  while ( a2[v4] );
  v5 = 2 * v4;
  if ( v5 > 0xFFFF )
    v6 = -1;
  else
    v6 = v5;
  if ( (v5 > 0xFFFF ? 0xC0000000 : 0) != 0xC0000000 )
  {
    ValueName.Buffer = a2;
    ValueName.MaximumLength = v6;
    ValueName.Length = v6;
    return ZwDeleteValueKey(KeyHandle, &ValueName);
  }
  if ( v5 <= 0xFFFF )
    return ZwDeleteValueKey(KeyHandle, &ValueName);
  return v5 > 0xFFFF ? 0xC0000095 : 0;
}

```

## disassembly

```asm
0x180013a50  push    rbx
0x180013a52  sub     rsp, 30h
0x180013a56  xor     eax, eax
0x180013a58  mov     r8, rdx
0x180013a5b  mov     r10, rcx
0x180013a5e  test    rcx, rcx
0x180013a61  jz      short loc_180013ADC
0x180013a63  test    rdx, rdx
0x180013a66  jz      short loc_180013ADC
0x180013a68  xorps   xmm0, xmm0
0x180013a6b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180013a6f  movups  xmmword ptr [rsp+38h+ValueName.Length], xmm0
0x180013a74  inc     rdx
0x180013a77  cmp     [r8+rdx*2], ax
0x180013a7c  jnz     short loc_180013A74
0x180013a7e  add     rdx, rdx
0x180013a81  mov     ebx, 0FFFFh
0x180013a86  cmp     edx, ebx
0x180013a88  ja      short loc_180013A8F
0x180013a8a  movzx   ecx, dx
0x180013a8d  jmp     short loc_180013A91
0x180013a8f  mov     ecx, ebx
0x180013a91  cmp     ebx, edx
0x180013a93  mov     r11d, 0C0000000h
0x180013a99  sbb     r9d, r9d
0x180013a9c  and     r9d, 0C0000095h
0x180013aa3  mov     eax, r9d
0x180013aa6  and     eax, r11d
0x180013aa9  cmp     eax, r11d
0x180013aac  jz      short loc_180013AD3
0x180013aae  mov     [rsp+38h+ValueName.Buffer], r8
0x180013ab3  mov     [rsp+38h+ValueName.MaximumLength], cx
0x180013ab8  mov     [rsp+38h+ValueName.Length], cx
0x180013abd  lea     rdx, [rsp+38h+ValueName]; ValueName
0x180013ac2  mov     rcx, r10; KeyHandle
0x180013ac5  call    cs:__imp_ZwDeleteValueKey
0x180013acc  nop     dword ptr [rax+rax+00h]
0x180013ad1  jmp     short loc_180013AE1
0x180013ad3  cmp     edx, ebx
0x180013ad5  jbe     short loc_180013ABD
0x180013ad7  mov     eax, r9d
0x180013ada  jmp     short loc_180013AE1
0x180013adc  mov     eax, 0C000000Dh
0x180013ae1  add     rsp, 30h
0x180013ae5  pop     rbx
0x180013ae6  retn
```
