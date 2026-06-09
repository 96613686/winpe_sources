# SystemSettings::PenSettings::ActionTypeOptionManager::CheckIfPackageIsInstalled(ushort const *,bool *)

- ea: `0x180021a44`
- end: `0x180021b2c`
- name: `?CheckIfPackageIsInstalled@ActionTypeOptionManager@PenSettings@SystemSettings@@SAJPEBGPEA_N@Z`
- size: `232`
- prototype: `__int64 __fastcall(PCWSTR packageFamilyName, bool *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180028910`
- `0x18002a3d4`
- `0x18002bbb0`
- `0x18002c190`
- `0x18002ce20`

## callees

- `0x1800030e0`
- `0x180003c64`
- `0x18000a2bc`
- `0x180021a44`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x180021ac6`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x180021ac6`

## string_xrefs

- `0x180021ae7`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::PenSettings::ActionTypeOptionManager::CheckIfPackageIsInstalled(
        PCWSTR packageFamilyName,
        bool *a2)
{
  LONG PackagesByPackageFamily; // eax
  unsigned int v5; // ebx
  int bufferLength; // [rsp+20h] [rbp-148h]
  UINT32 count; // [rsp+40h] [rbp-128h] BYREF
  UINT32 v9; // [rsp+44h] [rbp-124h] BYREF
  PWSTR packageFullNames; // [rsp+48h] [rbp-120h] BYREF
  WCHAR buffer[128]; // [rsp+50h] [rbp-118h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  *a2 = 1;
  memset_0(buffer, 0, sizeof(buffer));
  v9 = 128;
  packageFullNames = 0;
  count = 1;
  PackagesByPackageFamily = FindPackagesByPackageFamily(
                              packageFamilyName,
                              0x20010u,
                              &count,
                              &packageFullNames,
                              &v9,
                              buffer,
                              0);
  v5 = PackagesByPackageFamily;
  if ( PackagesByPackageFamily > 0 )
    v5 = (unsigned __int16)PackagesByPackageFamily | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
  {
    *a2 = count != 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D3,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
      (const char *)v5,
      bufferLength);
    return v5;
  }
}

```

## disassembly

```asm
0x180021a44  mov     [rsp+arg_10], rbx
0x180021a49  push    rdi
0x180021a4a  sub     rsp, 160h
0x180021a51  mov     rax, cs:__security_cookie
0x180021a58  xor     rax, rsp
0x180021a5b  mov     [rsp+168h+var_18], rax
0x180021a63  mov     rdi, rdx
0x180021a66  mov     byte ptr [rdx], 1
0x180021a69  mov     rbx, rcx
0x180021a6c  xor     edx, edx; Val
0x180021a6e  lea     rcx, [rsp+168h+var_118]; void *
0x180021a73  mov     r8d, 100h; Size
0x180021a79  call    memset_0
0x180021a7e  lea     rax, [rsp+168h+var_118]
0x180021a83  mov     [rsp+168h+packageProperties], 0; packageProperties
0x180021a8c  mov     [rsp+168h+buffer], rax; buffer
0x180021a91  lea     r9, [rsp+168h+packageFullNames]; packageFullNames
0x180021a96  lea     rax, [rsp+168h+var_124]
0x180021a9b  mov     [rsp+168h+var_124], 80h
0x180021aa3  lea     r8, [rsp+168h+count]; count
0x180021aa8  mov     [rsp+168h+bufferLength], rax; int
0x180021aad  mov     edx, 20010h; packageFilters
0x180021ab2  mov     [rsp+168h+packageFullNames], 0
0x180021abb  mov     rcx, rbx; packageFamilyName
0x180021abe  mov     [rsp+168h+count], 1
0x180021ac6  call    cs:__imp_FindPackagesByPackageFamily
0x180021acc  mov     ebx, eax
0x180021ace  test    eax, eax
0x180021ad0  jle     short loc_180021ADB
0x180021ad2  movzx   ebx, ax
0x180021ad5  or      ebx, 80070000h
0x180021adb  test    ebx, ebx
0x180021add  jns     short loc_180021AFF
0x180021adf  mov     rcx, [rsp+168h]; this
0x180021ae7  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x180021aee  mov     r9d, ebx; char *
0x180021af1  mov     edx, 1D3h; void *
0x180021af6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021afb  mov     eax, ebx
0x180021afd  jmp     short loc_180021B0B
0x180021aff  cmp     [rsp+168h+count], 1
0x180021b04  setnb   al
0x180021b07  mov     [rdi], al
0x180021b09  xor     eax, eax
0x180021b0b  mov     rcx, [rsp+168h+var_18]
0x180021b13  xor     rcx, rsp; StackCookie
0x180021b16  call    __security_check_cookie
0x180021b1b  mov     rbx, [rsp+168h+arg_10]
0x180021b23  add     rsp, 160h
0x180021b2a  pop     rdi
0x180021b2b  retn
```
