# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,void *,ulong)

- ea: `0x1800146ac`
- end: `0x1800146f9`
- name: `?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W0K@Z`
- size: `77`
- prototype: `NTSTATUS __fastcall(void *, __int64, void *, ULONG)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180015008`
- `0x1800153c8`

## callees

- `0x1800146ac`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x1800146e0`
- `ntoskrnl!ZwSetValueKey` at `0x1800146e0`

## string_xrefs

- `0x1800146bc`: `UserSid`

## pseudocode

```c
NTSTATUS __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
        void *a1,
        __int64 a2,
        void *a3,
        ULONG a4)
{
  struct _UNICODE_STRING v5; // [rsp+30h] [rbp-18h] BYREF

  if ( !a1 )
    return -1073741811;
  *(_QWORD *)&v5.Length = 917518;
  v5.Buffer = L"UserSid";
  return ZwSetValueKey(a1, &v5, 0, 3u, a3, a4);
}

```

## disassembly

```asm
0x1800146ac  mov     r11, rsp
0x1800146af  sub     rsp, 48h
0x1800146b3  test    rcx, rcx
0x1800146b6  jz      short loc_1800146EE
0x1800146b8  mov     [r11-20h], r9d
0x1800146bc  lea     rax, aUsersid; "UserSid"
0x1800146c3  mov     [r11-28h], r8
0x1800146c7  lea     rdx, [r11-18h]; ValueName
0x1800146cb  xor     r8d, r8d; TitleIndex
0x1800146ce  mov     qword ptr [r11-18h], 0E000Eh
0x1800146d6  mov     r9d, 3; Type
0x1800146dc  mov     [r11-10h], rax
0x1800146e0  call    cs:__imp_ZwSetValueKey
0x1800146e7  nop     dword ptr [rax+rax+00h]
0x1800146ec  jmp     short loc_1800146F3
0x1800146ee  mov     eax, 0C000000Dh
0x1800146f3  add     rsp, 48h
0x1800146f7  retn
```
