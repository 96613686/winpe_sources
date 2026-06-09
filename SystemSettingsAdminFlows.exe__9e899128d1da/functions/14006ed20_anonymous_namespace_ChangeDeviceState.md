# _anonymous_namespace_::ChangeDeviceState

- ea: `0x14006ed20`
- end: `0x14006ee45`
- name: `_anonymous_namespace_::ChangeDeviceState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14006f2f0`

## callees

- `0x140005f30`
- `0x14002a2c0`
- `0x14006ed20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14006ed8b`
- `KERNEL32!GetLastError` at `0x14006edea`
- `KERNEL32!GetLastError` at `0x14006ed8b`
- `KERNEL32!GetLastError` at `0x14006edea`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x14006ed81`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x14006ed81`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x14006ede0`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x14006ede0`

## string_xrefs

- `0x14006edc1`: `pcshell\shell\systemsettings\adminflows\accessibility\narratoradminflowhandler.cpp`
- `0x14006ee20`: `pcshell\shell\systemsettings\adminflows\accessibility\narratoradminflowhandler.cpp`

## pseudocode

```c
BOOL __fastcall anonymous_namespace_::ChangeDeviceState(HDEVINFO *a1, __int128 *a2, char a3)
{
  __int128 v3; // xmm0
  __int128 v5; // xmm1
  HDEVINFO v6; // rcx
  signed int LastError; // eax
  unsigned __int64 v8; // r9
  BOOL result; // eax
  signed int v10; // eax
  unsigned __int64 v11; // r9
  _SP_CLASSINSTALL_HEADER ClassInstallParams; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h]
  __int64 v14; // [rsp+2Ch] [rbp-3Ch]
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = *a2;
  v5 = a2[1];
  v6 = *a1;
  ClassInstallParams.cbSize = 8;
  ClassInstallParams.InstallFunction = 18;
  v13 = 2 - (a3 != 0);
  v14 = 2;
  *(_OWORD *)&DeviceInfoData.cbSize = v3;
  *(_OWORD *)&DeviceInfoData.ClassGuid.Data4[4] = v5;
  if ( !SetupDiSetClassInstallParamsW(v6, &DeviceInfoData, &ClassInstallParams, 0x14u) )
  {
    LastError = GetLastError();
    v8 = (unsigned int)LastError;
    if ( (LastError & 0xE0000000) == 0xE0000000 )
    {
      v8 = (unsigned __int16)LastError | 0x800F0000;
    }
    else if ( LastError > 0 )
    {
      v8 = (unsigned __int16)LastError | 0x80070000;
    }
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF1,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\narratoradminflowhandler.cpp",
      (const char *)v8,
      ClassInstallParams.cbSize);
  }
  result = SetupDiCallClassInstaller(0x12u, *a1, &DeviceInfoData);
  if ( !result )
  {
    v10 = GetLastError();
    v11 = (unsigned int)v10;
    if ( (v10 & 0xE0000000) == 0xE0000000 )
    {
      v11 = (unsigned __int16)v10 | 0x800F0000;
    }
    else if ( v10 > 0 )
    {
      v11 = (unsigned __int16)v10 | 0x80070000;
    }
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF6,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\narratoradminflowhandler.cpp",
      (const char *)v11,
      ClassInstallParams.cbSize);
  }
  return result;
}

```

## disassembly

```asm
0x14006ed20  push    rbx
0x14006ed22  sub     rsp, 60h
0x14006ed26  mov     rax, cs:__security_cookie
0x14006ed2d  xor     rax, rsp
0x14006ed30  mov     [rsp+68h+var_10], rax
0x14006ed35  movups  xmm0, xmmword ptr [rdx]
0x14006ed38  neg     r8b
0x14006ed3b  mov     rbx, rcx
0x14006ed3e  movups  xmm1, xmmword ptr [rdx+10h]
0x14006ed42  mov     rcx, [rcx]; DeviceInfoSet
0x14006ed45  lea     r8, [rsp+68h+ClassInstallParams]; ClassInstallParams
0x14006ed4a  sbb     eax, eax
0x14006ed4c  mov     [rsp+68h+ClassInstallParams.cbSize], 8; int
0x14006ed54  add     eax, 2
0x14006ed57  mov     [rsp+68h+ClassInstallParams.InstallFunction], 12h
0x14006ed5f  mov     r9d, 14h; ClassInstallParamsSize
0x14006ed65  mov     [rsp+68h+var_40], eax
0x14006ed69  lea     rdx, [rsp+68h+DeviceInfoData]; DeviceInfoData
0x14006ed6e  mov     [rsp+68h+var_3C], 2
0x14006ed77  movups  xmmword ptr [rsp+68h+DeviceInfoData.cbSize], xmm0
0x14006ed7c  movups  xmmword ptr [rsp+68h+DeviceInfoData.ClassGuid.Data4+4], xmm1
0x14006ed81  call    cs:__imp_SetupDiSetClassInstallParamsW
0x14006ed87  test    eax, eax
0x14006ed89  jnz     short loc_14006EDD3
0x14006ed8b  call    cs:__imp_GetLastError
0x14006ed91  mov     ecx, 0E0000000h
0x14006ed96  mov     r9d, eax
0x14006ed99  and     eax, ecx
0x14006ed9b  cmp     eax, ecx
0x14006ed9d  jnz     short loc_14006EDAC
0x14006ed9f  movzx   r9d, r9w
0x14006eda3  or      r9d, 800F0000h
0x14006edaa  jmp     short loc_14006EDBC
0x14006edac  test    r9d, r9d
0x14006edaf  jle     short loc_14006EDBC
0x14006edb1  movzx   r9d, r9w
0x14006edb5  or      r9d, 80070000h; char *
0x14006edbc  mov     rcx, [rsp+68h]; this
0x14006edc1  lea     r8, aPcshellShellSy_31; "pcshell\\shell\\systemsettings\\adminfl"...
0x14006edc8  mov     edx, 0F1h; void *
0x14006edcd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006edd3  mov     rdx, [rbx]; DeviceInfoSet
0x14006edd6  lea     r8, [rsp+68h+DeviceInfoData]; DeviceInfoData
0x14006eddb  mov     ecx, 12h; InstallFunction
0x14006ede0  call    cs:__imp_SetupDiCallClassInstaller
0x14006ede6  test    eax, eax
0x14006ede8  jnz     short loc_14006EE32
0x14006edea  call    cs:__imp_GetLastError
0x14006edf0  mov     ecx, 0E0000000h
0x14006edf5  mov     r9d, eax
0x14006edf8  and     eax, ecx
0x14006edfa  cmp     eax, ecx
0x14006edfc  jnz     short loc_14006EE0B
0x14006edfe  movzx   r9d, r9w
0x14006ee02  or      r9d, 800F0000h
0x14006ee09  jmp     short loc_14006EE1B
0x14006ee0b  test    r9d, r9d
0x14006ee0e  jle     short loc_14006EE1B
0x14006ee10  movzx   r9d, r9w
0x14006ee14  or      r9d, 80070000h; char *
0x14006ee1b  mov     rcx, [rsp+68h]; this
0x14006ee20  lea     r8, aPcshellShellSy_31; "pcshell\\shell\\systemsettings\\adminfl"...
0x14006ee27  mov     edx, 0F6h; void *
0x14006ee2c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006ee32  mov     rcx, [rsp+68h+var_10]
0x14006ee37  xor     rcx, rsp; StackCookie
0x14006ee3a  call    __security_check_cookie
0x14006ee3f  add     rsp, 60h
0x14006ee43  pop     rbx
0x14006ee44  retn
```
