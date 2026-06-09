# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_subkey_internal(void *,wchar_t const *)

- ea: `0x18000ba58`
- end: `0x18000baea`
- name: `?delete_subkey_internal@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJPEAXPEB_W@Z`
- size: `146`
- prototype: `NTSTATUS __fastcall(void *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b478`

## callees

- `0x18000ba58`
- `0x18000e23c`

## import_xrefs

- `ntoskrnl!ZwDeleteKey` at `0x18000baac`
- `ntoskrnl!ZwDeleteKey` at `0x18000bad2`
- `ntoskrnl!ZwDeleteKey` at `0x18000baac`
- `ntoskrnl!ZwDeleteKey` at `0x18000bad2`
- `ntoskrnl!ZwClose` at `0x18000ba94`
- `ntoskrnl!ZwClose` at `0x18000bac2`
- `ntoskrnl!ZwClose` at `0x18000ba94`
- `ntoskrnl!ZwClose` at `0x18000bac2`

## pseudocode

```c
NTSTATUS __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_subkey_internal(
        void *a1,
        __int64 a2)
{
  int v2; // eax
  int v3; // ebx
  HANDLE v5; // rbx
  NTSTATUS v6; // edi
  HANDLE Handle; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return ZwDeleteKey(a1);
  Handle = 0;
  v2 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
         a1,
         a2,
         &Handle);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v5 = Handle;
    v6 = ZwDeleteKey(Handle);
    if ( v5 )
      ZwClose(v5);
    return v6;
  }
  else
  {
    if ( v2 == -1073741772 )
      v3 = 0;
    if ( Handle )
      ZwClose(Handle);
    return v3;
  }
}

```

## disassembly

```asm
0x18000ba58  mov     [rsp+arg_0], rbx
0x18000ba5d  push    rdi
0x18000ba5e  sub     rsp, 20h
0x18000ba62  test    rdx, rdx
0x18000ba65  jz      short loc_18000BAD2
0x18000ba67  lea     r8, [rsp+28h+Handle]
0x18000ba6c  mov     [rsp+28h+Handle], 0
0x18000ba75  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18000ba7a  mov     ebx, eax
0x18000ba7c  test    eax, eax
0x18000ba7e  jns     short loc_18000BAA4
0x18000ba80  xor     ecx, ecx
0x18000ba82  cmp     eax, 0C0000034h
0x18000ba87  cmovz   ebx, ecx
0x18000ba8a  mov     rcx, [rsp+28h+Handle]; Handle
0x18000ba8f  test    rcx, rcx
0x18000ba92  jz      short loc_18000BAA0
0x18000ba94  call    cs:__imp_ZwClose
0x18000ba9b  nop     dword ptr [rax+rax+00h]
0x18000baa0  mov     eax, ebx
0x18000baa2  jmp     short loc_18000BADE
0x18000baa4  mov     rbx, [rsp+28h+Handle]
0x18000baa9  mov     rcx, rbx; KeyHandle
0x18000baac  call    cs:__imp_ZwDeleteKey
0x18000bab3  nop     dword ptr [rax+rax+00h]
0x18000bab8  mov     edi, eax
0x18000baba  test    rbx, rbx
0x18000babd  jz      short loc_18000BACE
0x18000babf  mov     rcx, rbx; Handle
0x18000bac2  call    cs:__imp_ZwClose
0x18000bac9  nop     dword ptr [rax+rax+00h]
0x18000bace  mov     eax, edi
0x18000bad0  jmp     short loc_18000BADE
0x18000bad2  call    cs:__imp_ZwDeleteKey
0x18000bad9  nop     dword ptr [rax+rax+00h]
0x18000bade  mov     rbx, [rsp+28h+arg_0]
0x18000bae3  add     rsp, 20h
0x18000bae7  pop     rdi
0x18000bae8  retn
```
