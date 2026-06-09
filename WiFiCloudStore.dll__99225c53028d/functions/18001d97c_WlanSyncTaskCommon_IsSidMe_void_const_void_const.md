# WlanSyncTaskCommon::IsSidMe(void * const,void * const)

- ea: `0x18001d97c`
- end: `0x18001d9de`
- name: `?IsSidMe@WlanSyncTaskCommon@@CA_NQEAX0@Z`
- size: `98`
- prototype: `bool __fastcall(void *const, void *const)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d86c`

## callees

- `0x18001d97c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d985`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d985`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001d9c2`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001d9d2`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001d9c2`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001d9d2`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001d9a9`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001d9a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
bool __fastcall WlanSyncTaskCommon::IsSidMe(void *const a1, void *const a2)
{
  bool result; // al
  int v4; // [rsp+40h] [rbp+18h] BYREF

  result = 1;
  if ( !EqualSid(a1, a2) )
  {
    v4 = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v4, 0);
    if ( v4 != 14
      || !IsWellKnownSid(a2, WinWorldSid) && !IsWellKnownSid(a2, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid) )
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001d97c  push    rbx
0x18001d97e  sub     rsp, 20h
0x18001d982  mov     rbx, rdx
0x18001d985  call    cs:__imp_EqualSid
0x18001d98b  test    eax, eax
0x18001d98d  jz      short loc_18001D997
0x18001d98f  mov     al, 1
0x18001d991  add     rsp, 20h
0x18001d995  pop     rbx
0x18001d996  retn
0x18001d997  xor     r8d, r8d
0x18001d99a  mov     [rsp+28h+arg_10], 0
0x18001d9a2  lea     rdx, [rsp+28h+arg_10]
0x18001d9a7  xor     ecx, ecx
0x18001d9a9  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18001d9af  cmp     [rsp+28h+arg_10], 0Eh
0x18001d9b4  jz      short loc_18001D9BA
0x18001d9b6  xor     al, al
0x18001d9b8  jmp     short loc_18001D991
0x18001d9ba  mov     edx, 1; WellKnownSidType
0x18001d9bf  mov     rcx, rbx; pSid
0x18001d9c2  call    cs:__imp_IsWellKnownSid
0x18001d9c8  test    eax, eax
0x18001d9ca  jnz     short loc_18001D98F
0x18001d9cc  lea     edx, [rax+6Eh]; WellKnownSidType
0x18001d9cf  mov     rcx, rbx; pSid
0x18001d9d2  call    cs:__imp_IsWellKnownSid
0x18001d9d8  test    eax, eax
0x18001d9da  jnz     short loc_18001D98F
0x18001d9dc  jmp     short loc_18001D9B6
```
