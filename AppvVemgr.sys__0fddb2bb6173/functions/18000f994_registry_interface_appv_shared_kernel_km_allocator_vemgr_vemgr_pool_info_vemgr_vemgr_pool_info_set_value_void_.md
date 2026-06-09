# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,ulong)

- ea: `0x18000f994`
- end: `0x18000fa50`
- name: `?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WK@Z`
- size: `188`
- prototype: `unsigned int __fastcall(HANDLE KeyHandle, wchar_t *, int)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000fa58`
- `0x18000fe44`
- `0x180013718`
- `0x180014d1c`
- `0x180015008`
- `0x180015154`
- `0x180015278`
- `0x1800153c8`

## callees

- `0x18000f994`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x18000fa2d`
- `ntoskrnl!ZwSetValueKey` at `0x18000fa2d`

## pseudocode

```c
unsigned int __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
        HANDLE KeyHandle,
        wchar_t *a2,
        int a3)
{
  __int64 v5; // rdx
  unsigned int v6; // edx
  unsigned __int16 v7; // cx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF
  int Data; // [rsp+60h] [rbp+18h] BYREF

  Data = a3;
  if ( !KeyHandle || !a2 )
    return -1073741811;
  v5 = -1;
  ValueName = 0;
  do
    ++v5;
  while ( a2[v5] );
  v6 = 2 * v5;
  if ( v6 > 0xFFFF )
    v7 = -1;
  else
    v7 = v6;
  if ( (v6 > 0xFFFF ? 0xC0000000 : 0) != 0xC0000000 )
  {
    ValueName.Buffer = a2;
    ValueName.MaximumLength = v7;
    ValueName.Length = v7;
    return ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
  }
  if ( v6 <= 0xFFFF )
    return ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
  return v6 > 0xFFFF ? 0xC0000095 : 0;
}

```

## disassembly

```asm
0x18000f994  mov     [rsp+arg_10], r8d
0x18000f999  push    rbx
0x18000f99a  sub     rsp, 40h
0x18000f99e  xor     eax, eax
0x18000f9a0  mov     r8, rdx
0x18000f9a3  mov     r10, rcx
0x18000f9a6  test    rcx, rcx
0x18000f9a9  jz      loc_18000FA44
0x18000f9af  test    rdx, rdx
0x18000f9b2  jz      loc_18000FA44
0x18000f9b8  xorps   xmm0, xmm0
0x18000f9bb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000f9bf  movups  xmmword ptr [rsp+48h+ValueName.Length], xmm0
0x18000f9c4  inc     rdx
0x18000f9c7  cmp     [r8+rdx*2], ax
0x18000f9cc  jnz     short loc_18000F9C4
0x18000f9ce  add     rdx, rdx
0x18000f9d1  mov     ebx, 0FFFFh
0x18000f9d6  cmp     edx, ebx
0x18000f9d8  ja      short loc_18000F9DF
0x18000f9da  movzx   ecx, dx
0x18000f9dd  jmp     short loc_18000F9E1
0x18000f9df  mov     ecx, ebx
0x18000f9e1  cmp     ebx, edx
0x18000f9e3  mov     r11d, 0C0000000h
0x18000f9e9  sbb     r9d, r9d
0x18000f9ec  and     r9d, 0C0000095h
0x18000f9f3  mov     eax, r9d
0x18000f9f6  and     eax, r11d
0x18000f9f9  cmp     eax, r11d
0x18000f9fc  jz      short loc_18000FA3B
0x18000f9fe  mov     [rsp+48h+ValueName.Buffer], r8
0x18000fa03  mov     [rsp+48h+ValueName.MaximumLength], cx
0x18000fa08  mov     [rsp+48h+ValueName.Length], cx
0x18000fa0d  mov     r9d, 4; Type
0x18000fa13  lea     rax, [rsp+48h+arg_10]
0x18000fa18  mov     [rsp+48h+DataSize], r9d; DataSize
0x18000fa1d  lea     rdx, [rsp+48h+ValueName]; ValueName
0x18000fa22  xor     r8d, r8d; TitleIndex
0x18000fa25  mov     [rsp+48h+Data], rax; Data
0x18000fa2a  mov     rcx, r10; KeyHandle
0x18000fa2d  call    cs:__imp_ZwSetValueKey
0x18000fa34  nop     dword ptr [rax+rax+00h]
0x18000fa39  jmp     short loc_18000FA49
0x18000fa3b  cmp     edx, ebx
0x18000fa3d  jbe     short loc_18000FA0D
0x18000fa3f  mov     eax, r9d
0x18000fa42  jmp     short loc_18000FA49
0x18000fa44  mov     eax, 0C000000Dh
0x18000fa49  add     rsp, 40h
0x18000fa4d  pop     rbx
0x18000fa4e  retn
```
