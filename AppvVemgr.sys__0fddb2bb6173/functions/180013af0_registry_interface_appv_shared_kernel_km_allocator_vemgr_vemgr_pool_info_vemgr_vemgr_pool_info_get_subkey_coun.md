# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_subkey_count(void *,ulong &)

- ea: `0x180013af0`
- end: `0x180013b71`
- name: `?get_subkey_count@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEAK@Z`
- size: `129`
- prototype: `__int64 __fastcall(void *, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800141d0`
- `0x180014338`

## callees

- `0x180013af0`
- `0x18001baf0`

## import_xrefs

- `ntoskrnl!ZwQueryKey` at `0x180013b3b`
- `ntoskrnl!ZwQueryKey` at `0x180013b3b`

## pseudocode

```c
__int64 __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_subkey_count(
        void *a1,
        _DWORD *a2)
{
  NTSTATUS v3; // eax
  int v4; // edx
  ULONG ResultLength; // [rsp+30h] [rbp-48h] BYREF
  __int128 KeyInformation; // [rsp+38h] [rbp-40h] BYREF
  __int128 v8; // [rsp+48h] [rbp-30h]
  __int128 v9; // [rsp+58h] [rbp-20h]

  ResultLength = 0;
  KeyInformation = 0;
  v8 = 0;
  v9 = 0;
  v3 = ZwQueryKey(a1, KeyFullInformation, &KeyInformation, 0x30u, &ResultLength);
  v4 = 0;
  if ( v3 != -2147483643 )
    v4 = v3;
  if ( v4 >= 0 )
    *a2 = DWORD1(v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013af0  push    rbx
0x180013af2  sub     rsp, 70h
0x180013af6  mov     rax, cs:__security_cookie
0x180013afd  xor     rax, rsp
0x180013b00  mov     [rsp+78h+var_10], rax
0x180013b05  xorps   xmm0, xmm0
0x180013b08  mov     [rsp+78h+var_48], 0
0x180013b10  mov     r9d, 30h ; '0'; Length
0x180013b16  lea     rax, [rsp+78h+var_48]
0x180013b1b  mov     rbx, rdx
0x180013b1e  mov     [rsp+78h+ResultLength], rax; ResultLength
0x180013b23  lea     r8, [rsp+78h+KeyInformation]; KeyInformation
0x180013b28  movups  [rsp+78h+KeyInformation], xmm0
0x180013b2d  lea     edx, [r9-2Eh]; KeyInformationClass
0x180013b31  movups  [rsp+78h+var_30], xmm0
0x180013b36  movups  [rsp+78h+var_20], xmm0
0x180013b3b  call    cs:__imp_ZwQueryKey
0x180013b42  nop     dword ptr [rax+rax+00h]
0x180013b47  xor     edx, edx
0x180013b49  cmp     eax, 80000005h
0x180013b4e  cmovnz  edx, eax
0x180013b51  test    edx, edx
0x180013b53  js      short loc_180013B5B
0x180013b55  mov     ecx, dword ptr [rsp+78h+var_30+4]
0x180013b59  mov     [rbx], ecx
0x180013b5b  mov     eax, edx
0x180013b5d  mov     rcx, [rsp+78h+var_10]
0x180013b62  xor     rcx, rsp; StackCookie
0x180013b65  call    __security_check_cookie
0x180013b6a  add     rsp, 70h
0x180013b6e  pop     rbx
0x180013b6f  retn
```
