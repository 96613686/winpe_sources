# GetAutoUpdateState(WindowsUpdate::Internal::AutoUpdateState *)

- ea: `0x1800211d8`
- end: `0x18002131a`
- name: `?GetAutoUpdateState@@YAJPEAW4AutoUpdateState@Internal@WindowsUpdate@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(enum WindowsUpdate::Internal::AutoUpdateState *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180016044`
- `0x180020a1c`
- `0x180028b44`

## callees

- `0x1800211d8`
- `0x180026bb8`
- `0x180026c4c`
- `0x180029190`
- `0x180034cec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021274`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800212fe`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021274`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800212fe`

## string_xrefs

- `0x1800211f8`: `UpdatePolicy-UpdateManagementGroup`
- `0x180021291`: `AllowAppStoreAutoUpdate`
- `0x1800212b6`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsStore\WindowsUpdate`

## pseudocode

```c
__int64 __fastcall GetAutoUpdateState(enum WindowsUpdate::Internal::AutoUpdateState *a1)
{
  bool v2; // cf
  int v3; // eax
  const WCHAR *RegistryLocation; // rax
  DWORD pcbData; // [rsp+60h] [rbp+20h] BYREF
  int pvData; // [rsp+68h] [rbp+28h] BYREF
  DWORD pdwValue; // [rsp+70h] [rbp+30h] BYREF
  int v9; // [rsp+78h] [rbp+38h] BYREF

  *(_DWORD *)a1 = 1;
  pvData = 0;
  pcbData = 4;
  v9 = 0;
  pdwValue = 0;
  if ( SLGetWindowsInformationDWORD(L"UpdatePolicy-UpdateManagementGroup", &pdwValue) >= 0 && !pdwValue )
    goto LABEL_11;
  if ( !(unsigned int)GetStoreAppsAreDisabled() )
  {
    pcbData = 4;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Policies\\Microsoft\\WindowsStore",
            L"AutoDownload",
            0x10u,
            0,
            &pvData,
            &pcbData) )
    {
      v2 = pvData != 4;
LABEL_7:
      v3 = 3 - v2;
      goto LABEL_13;
    }
    if ( GetPolicyInt(L"ApplicationManagement", L"AllowAppStoreAutoUpdate", &v9) && (unsigned int)v9 <= 1 )
    {
      v2 = v9 != 1;
      goto LABEL_7;
    }
LABEL_11:
    pcbData = 4;
    RegistryLocation = (const WCHAR *)_InitOnceAndGetRegistryLocation(
                                        &qword_18006A468,
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsStore\\WindowsUpdate");
    if ( RegGetValueW(HKEY_LOCAL_MACHINE, RegistryLocation, L"AutoDownload", 0x10u, 0, &pvData, &pcbData) )
      return 0;
    v3 = pvData == 4;
LABEL_13:
    *(_DWORD *)a1 = v3;
    return 0;
  }
  *(_DWORD *)a1 = 2;
  return 0;
}

```

## disassembly

```asm
0x1800211d8  push    rbp
0x1800211da  push    rbx
0x1800211db  push    rdi
0x1800211dc  mov     rbp, rsp
0x1800211df  sub     rsp, 40h
0x1800211e3  mov     rdi, rcx
0x1800211e6  mov     dword ptr [rcx], 1
0x1800211ec  mov     ebx, 4
0x1800211f1  mov     [rbp+arg_8], 0
0x1800211f8  lea     rcx, pwszValueName; "UpdatePolicy-UpdateManagementGroup"
0x1800211ff  mov     [rbp+arg_0], ebx
0x180021202  lea     rdx, [rbp+pdwValue]; pdwValue
0x180021206  mov     [rbp+arg_18], 0
0x18002120d  mov     [rbp+pdwValue], 0
0x180021214  call    SLGetWindowsInformationDWORD
0x180021219  test    eax, eax
0x18002121b  js      short loc_180021227
0x18002121d  cmp     [rbp+pdwValue], 0
0x180021221  jz      loc_1800212B6
0x180021227  call    ?GetStoreAppsAreDisabled@@YAHXZ; GetStoreAppsAreDisabled(void)
0x18002122c  test    eax, eax
0x18002122e  jz      short loc_18002123B
0x180021230  mov     dword ptr [rdi], 2
0x180021236  jmp     loc_180021310
0x18002123b  lea     rax, [rbp+arg_0]
0x18002123f  mov     [rbp+arg_0], ebx
0x180021242  mov     [rsp+40h+pcbData], rax; pcbData
0x180021247  lea     r8, aAutodownload; "AutoDownload"
0x18002124e  lea     rax, [rbp+arg_8]
0x180021252  mov     r9d, 10h; dwFlags
0x180021258  mov     [rsp+40h+pvData], rax; pvData
0x18002125d  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\WindowsS"...
0x180021264  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002126b  mov     [rsp+40h+pdwType], 0; pdwType
0x180021274  call    cs:__imp_RegGetValueW
0x18002127a  test    eax, eax
0x18002127c  jnz     short loc_18002128D
0x18002127e  sub     ebx, [rbp+arg_8]
0x180021281  neg     ebx
0x180021283  sbb     eax, eax
0x180021285  add     eax, 3
0x180021288  jmp     loc_18002130E
0x18002128d  lea     r8, [rbp+arg_18]; int *
0x180021291  lea     rdx, aAllowappstorea; "AllowAppStoreAutoUpdate"
0x180021298  lea     rcx, aApplicationman; "ApplicationManagement"
0x18002129f  call    ?GetPolicyInt@@YA_NPEBG0PEAH@Z; GetPolicyInt(ushort const *,ushort const *,int *)
0x1800212a4  test    al, al
0x1800212a6  jz      short loc_1800212B6
0x1800212a8  mov     eax, [rbp+arg_18]
0x1800212ab  cmp     eax, 1
0x1800212ae  ja      short loc_1800212B6
0x1800212b0  dec     eax
0x1800212b2  neg     eax
0x1800212b4  jmp     short loc_180021283
0x1800212b6  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800212bd  mov     [rbp+arg_0], ebx
0x1800212c0  lea     rcx, qword_18006A468
0x1800212c7  call    ?_InitOnceAndGetRegistryLocation@@YAPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; _InitOnceAndGetRegistryLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x1800212cc  lea     rdx, [rbp+arg_0]
0x1800212d0  mov     r9d, 10h; dwFlags
0x1800212d6  mov     [rsp+40h+pcbData], rdx; pcbData
0x1800212db  lea     r8, aAutodownload; "AutoDownload"
0x1800212e2  lea     rdx, [rbp+arg_8]
0x1800212e6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800212ed  mov     [rsp+40h+pvData], rdx; pvData
0x1800212f2  mov     rdx, rax; lpSubKey
0x1800212f5  mov     [rsp+40h+pdwType], 0; pdwType
0x1800212fe  call    cs:__imp_RegGetValueW
0x180021304  test    eax, eax
0x180021306  jnz     short loc_180021310
0x180021308  cmp     [rbp+arg_8], ebx
0x18002130b  setz    al
0x18002130e  mov     [rdi], eax
0x180021310  xor     eax, eax
0x180021312  add     rsp, 40h
0x180021316  pop     rdi
0x180021317  pop     rbx
0x180021318  pop     rbp
0x180021319  retn
```
