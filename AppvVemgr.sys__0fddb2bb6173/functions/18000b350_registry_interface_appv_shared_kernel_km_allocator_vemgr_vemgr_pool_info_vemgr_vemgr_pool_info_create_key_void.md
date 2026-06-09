# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,_UNICODE_STRING const &,appv::shared::kernel::handle &)

- ea: `0x18000b350`
- end: `0x18000b419`
- name: `?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEBU_UNICODE_STRING@@AEAVhandle@kernel@shared@appv@@@Z`
- size: `201`
- prototype: `NTSTATUS __fastcall(void *, struct _UNICODE_STRING *, HANDLE *)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b420`
- `0x180014d1c`

## callees

- `0x18000b350`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18000b3f5`
- `ntoskrnl!ZwClose` at `0x18000b3f5`
- `ntoskrnl!ZwCreateKey` at `0x18000b3d3`
- `ntoskrnl!ZwCreateKey` at `0x18000b3d3`

## pseudocode

```c
NTSTATUS __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
        void *a1,
        struct _UNICODE_STRING *a2,
        HANDLE *a3)
{
  NTSTATUS result; // eax
  NTSTATUS v5; // ebx
  void *v6; // rsi
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *KeyHandle; // [rsp+88h] [rbp+10h] BYREF

  if ( !a2->Buffer )
    return -1073741811;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.ObjectName = a2;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  KeyHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  result = ZwCreateKey(&KeyHandle, 0x10000000u, &ObjectAttributes, 0, 0, 0, 0);
  v5 = result;
  if ( result >= 0 )
  {
    v6 = KeyHandle;
    if ( *a3 )
      ZwClose(*a3);
    *a3 = v6;
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18000b350  mov     [rsp+arg_0], rbx
0x18000b355  mov     [rsp+arg_10], rsi
0x18000b35a  push    rdi
0x18000b35b  sub     rsp, 70h
0x18000b35f  cmp     qword ptr [rdx+8], 0
0x18000b364  mov     rdi, r8
0x18000b367  jnz     short loc_18000B373
0x18000b369  mov     eax, 0C000000Dh
0x18000b36e  jmp     loc_18000B406
0x18000b373  mov     [rsp+78h+ObjectAttributes.RootDirectory], rcx
0x18000b378  lea     r8, [rsp+78h+ObjectAttributes]; ObjectAttributes
0x18000b37d  mov     [rsp+78h+ObjectAttributes.ObjectName], rdx
0x18000b382  lea     rcx, [rsp+78h+KeyHandle]; KeyHandle
0x18000b38a  xorps   xmm0, xmm0
0x18000b38d  mov     [rsp+78h+Disposition], 0; Disposition
0x18000b396  mov     [rsp+78h+CreateOptions], 0; CreateOptions
0x18000b39e  mov     edx, 10000000h; DesiredAccess
0x18000b3a3  xor     r9d, r9d; TitleIndex
0x18000b3a6  mov     [rsp+78h+Class], 0; Class
0x18000b3af  movdqu  xmmword ptr [rsp+78h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b3b5  mov     [rsp+78h+KeyHandle], 0
0x18000b3c1  mov     qword ptr [rsp+78h+ObjectAttributes.Length], 30h ; '0'
0x18000b3ca  mov     qword ptr [rsp+78h+ObjectAttributes.Attributes], 240h
0x18000b3d3  call    cs:__imp_ZwCreateKey
0x18000b3da  nop     dword ptr [rax+rax+00h]
0x18000b3df  mov     ebx, eax
0x18000b3e1  test    eax, eax
0x18000b3e3  js      short loc_18000B406
0x18000b3e5  mov     rcx, [rdi]; Handle
0x18000b3e8  mov     rsi, [rsp+78h+KeyHandle]
0x18000b3f0  test    rcx, rcx
0x18000b3f3  jz      short loc_18000B401
0x18000b3f5  call    cs:__imp_ZwClose
0x18000b3fc  nop     dword ptr [rax+rax+00h]
0x18000b401  mov     [rdi], rsi
0x18000b404  mov     eax, ebx
0x18000b406  lea     r11, [rsp+78h+var_8]
0x18000b40b  mov     rbx, [r11+10h]
0x18000b40f  mov     rsi, [r11+20h]
0x18000b413  mov     rsp, r11
0x18000b416  pop     rdi
0x18000b417  retn
```
