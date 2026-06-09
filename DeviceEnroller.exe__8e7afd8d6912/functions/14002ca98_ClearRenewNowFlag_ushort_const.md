# ClearRenewNowFlag(ushort const *)

- ea: `0x14002ca98`
- end: `0x14002cb52`
- name: `?ClearRenewNowFlag@@YAJPEBG@Z`
- size: `186`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140019a6c`

## callees

- `0x1400095b4`
- `0x14002ca98`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x14002cb24`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x14002cb24`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14002caae`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14002caae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002cae1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002cae1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002cb3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002cb3f`

## pseudocode

```c
__int64 __fastcall ClearRenewNowFlag(const unsigned __int16 *a1)
{
  char IsStateSeparationEnabled; // al
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  HKEY v5; // rcx
  int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)off_14005EF50 + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         0,
         0x20019u,
         &hKey);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( (v4 & 0x80000000) == 0 )
    v4 = OmaDmRegistryDeleteValue(hKey, a1, L"RenewNow");
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)v4,
      phkResult);
  v5 = hKey;
  hKey = 0;
  if ( v5 )
    RegCloseKey(v5);
  return v4;
}

```

## disassembly

```asm
0x14002ca98  mov     [rsp+arg_0], rbx
0x14002ca9d  push    rdi
0x14002ca9e  sub     rsp, 30h
0x14002caa2  mov     rdi, rcx
0x14002caa5  mov     [rsp+38h+hKey], 0
0x14002caae  call    cs:__imp_RtlIsStateSeparationEnabled
0x14002cab4  lea     rcx, off_14005EF50; "Software\\Microsoft\\Enrollments"
0x14002cabb  mov     r9d, 20019h; samDesired
0x14002cac1  neg     al
0x14002cac3  lea     rax, [rsp+38h+hKey]
0x14002cac8  sbb     rdx, rdx
0x14002cacb  mov     qword ptr [rsp+38h+phkResult], rax; int
0x14002cad0  and     edx, 8
0x14002cad3  xor     r8d, r8d; ulOptions
0x14002cad6  mov     rdx, [rdx+rcx]; lpSubKey
0x14002cada  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002cae1  call    cs:__imp_RegOpenKeyExW
0x14002cae7  mov     ebx, eax
0x14002cae9  test    eax, eax
0x14002caeb  jle     short loc_14002CAF6
0x14002caed  movzx   ebx, ax
0x14002caf0  or      ebx, 80070000h
0x14002caf6  test    ebx, ebx
0x14002caf8  jns     short loc_14002CB15
0x14002cafa  mov     rcx, [rsp+38h]; this
0x14002caff  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002cb06  mov     r9d, ebx; char *
0x14002cb09  mov     edx, 12E4h; void *
0x14002cb0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002cb13  jmp     short loc_14002CB2C
0x14002cb15  mov     rcx, [rsp+38h+hKey]
0x14002cb1a  lea     r8, aRenewnow; "RenewNow"
0x14002cb21  mov     rdx, rdi
0x14002cb24  call    cs:__imp_?OmaDmRegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; OmaDmRegistryDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x14002cb2a  mov     ebx, eax
0x14002cb2c  mov     rcx, [rsp+38h+hKey]; hKey
0x14002cb31  mov     [rsp+38h+hKey], 0
0x14002cb3a  test    rcx, rcx
0x14002cb3d  jz      short loc_14002CB45
0x14002cb3f  call    cs:__imp_RegCloseKey
0x14002cb45  mov     eax, ebx
0x14002cb47  mov     rbx, [rsp+38h+arg_0]
0x14002cb4c  add     rsp, 30h
0x14002cb50  pop     rdi
0x14002cb51  retn
```
