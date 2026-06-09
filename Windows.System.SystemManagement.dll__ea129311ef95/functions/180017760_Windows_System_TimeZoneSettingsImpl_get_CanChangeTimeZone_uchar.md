# Windows::System::TimeZoneSettingsImpl::get_CanChangeTimeZone(uchar *)

- ea: `0x180017760`
- end: `0x1800177eb`
- name: `?get_CanChangeTimeZone@TimeZoneSettingsImpl@System@Windows@@UEAAJPEAE@Z`
- size: `139`
- prototype: `__int64 __fastcall(Windows::System::TimeZoneSettingsImpl *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180017760`
- `0x18001c6a8`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x1800177b7`
- `ntdll!RtlAcquirePrivilege` at `0x1800177b7`
- `ntdll!RtlReleasePrivilege` at `0x1800177d8`
- `ntdll!RtlReleasePrivilege` at `0x1800177d8`

## pseudocode

```c
__int64 __fastcall Windows::System::TimeZoneSettingsImpl::get_CanChangeTimeZone(
        Windows::System::TimeZoneSettingsImpl *this,
        unsigned __int8 *a2)
{
  unsigned int v3; // ebx
  NTSTATUS v4; // eax
  unsigned __int8 v6; // [rsp+38h] [rbp+10h] BYREF
  ULONG Privilege; // [rsp+40h] [rbp+18h] BYREF
  PVOID ReturnedState; // [rsp+48h] [rbp+20h] BYREF

  ReturnedState = 0;
  Privilege = 34;
  v6 = 0;
  if ( a2 )
  {
    *a2 = 0;
    if ( (int)Windows::System::SystemManagementUtil::HasSystemManagementCapability(&v6) >= 0
      && v6
      && (v4 = RtlAcquirePrivilege(&Privilege, 1u, 0, &ReturnedState), v3 = v4 | 0x10000000, v4 >= 0) )
    {
      *a2 = 1;
    }
    else
    {
      v3 = 0;
    }
    if ( ReturnedState )
      RtlReleasePrivilege(ReturnedState);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v3;
}

```

## disassembly

```asm
0x180017760  mov     rax, rsp
0x180017763  mov     [rax+8], rbx
0x180017767  push    rdi
0x180017768  sub     rsp, 20h
0x18001776c  mov     qword ptr [rax+20h], 0
0x180017774  mov     rdi, rdx
0x180017777  mov     dword ptr [rax+18h], 22h ; '"'
0x18001777e  mov     byte ptr [rax+10h], 0
0x180017782  test    rdx, rdx
0x180017785  jnz     short loc_18001778E
0x180017787  mov     ebx, 80004003h
0x18001778c  jmp     short loc_1800177DE
0x18001778e  lea     rcx, [rsp+28h+arg_8]; unsigned __int8 *
0x180017793  mov     byte ptr [rdx], 0
0x180017796  call    ?HasSystemManagementCapability@SystemManagementUtil@System@Windows@@SAJPEAE@Z; Windows::System::SystemManagementUtil::HasSystemManagementCapability(uchar *)
0x18001779b  test    eax, eax
0x18001779d  js      short loc_1800177CC
0x18001779f  cmp     [rsp+28h+arg_8], 0
0x1800177a4  jz      short loc_1800177CC
0x1800177a6  xor     r8d, r8d; Flags
0x1800177a9  lea     r9, [rsp+28h+ReturnedState]; ReturnedState
0x1800177ae  lea     rcx, [rsp+28h+Privilege]; Privilege
0x1800177b3  lea     edx, [r8+1]; NumPriv
0x1800177b7  call    cs:__imp_RtlAcquirePrivilege
0x1800177bd  mov     ebx, eax
0x1800177bf  or      ebx, 10000000h
0x1800177c5  jl      short loc_1800177CC
0x1800177c7  mov     byte ptr [rdi], 1
0x1800177ca  jmp     short loc_1800177CE
0x1800177cc  xor     ebx, ebx
0x1800177ce  mov     rcx, [rsp+28h+ReturnedState]; ReturnedState
0x1800177d3  test    rcx, rcx
0x1800177d6  jz      short loc_1800177DE
0x1800177d8  call    cs:__imp_RtlReleasePrivilege
0x1800177de  mov     eax, ebx
0x1800177e0  mov     rbx, [rsp+28h+arg_0]
0x1800177e5  add     rsp, 20h
0x1800177e9  pop     rdi
0x1800177ea  retn
```
