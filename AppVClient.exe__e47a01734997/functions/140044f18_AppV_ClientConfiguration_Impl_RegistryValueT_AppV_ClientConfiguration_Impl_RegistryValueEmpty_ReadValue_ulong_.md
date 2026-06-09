# AppV::ClientConfiguration::Impl::RegistryValueT<AppV::ClientConfiguration::Impl::RegistryValueEmpty>::ReadValue(ulong,uchar *,ulong)

- ea: `0x140044f18`
- end: `0x14004500b`
- name: `?ReadValue@?$RegistryValueT@URegistryValueEmpty@Impl@ClientConfiguration@AppV@@@Impl@ClientConfiguration@AppV@@AEAA_KKPEAEK@Z`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140042804`
- `0x140044e14`

## callees

- `0x140018bec`
- `0x140044f18`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140044f5a`
- `ADVAPI32!RegQueryValueExW` at `0x140044f5a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140044f72`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140044fc0`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140044f72`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140044fc0`

## string_xrefs

- `0x140044f6b`: `admin\appman\appv\shared\clientconfiguration\RegistryValue.h`
- `0x140044f82`: `admin\appman\appv\shared\clientconfiguration\RegistryValue.h`
- `0x140044fb9`: `admin\appman\appv\shared\clientconfiguration\RegistryValue.h`
- `0x140044fd0`: `admin\appman\appv\shared\clientconfiguration\RegistryValue.h`

## pseudocode

```c
__int64 __fastcall AppV::ClientConfiguration::Impl::RegistryValueT<AppV::ClientConfiguration::Impl::RegistryValueEmpty>::ReadValue(
        __int64 a1,
        int a2,
        BYTE *lpData,
        DWORD a4)
{
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  __int64 v7; // rdi
  char *v8; // rax
  const char *v9; // rax
  unsigned __int64 FileId; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rax
  char *v14; // rax
  const char *v15; // rax
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF

  cbData = a4;
  v5 = (const WCHAR *)(a1 + 64);
  Type = 0;
  if ( *(_QWORD *)(a1 + 88) > 7u )
    v5 = *(const WCHAR **)v5;
  v6 = RegQueryValueExW(*(HKEY *)(a1 + 96), v5, 0, &Type, lpData, &cbData);
  v7 = v6;
  if ( v6 )
  {
    v8 = strrchr("admin\\appman\\appv\\shared\\clientconfiguration\\RegistryValue.h", 92);
    if ( v8 )
      v9 = v8 + 1;
    else
      v9 = "admin\\appman\\appv\\shared\\clientconfiguration\\RegistryValue.h";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v9);
    v11 = 0x342500000000LL;
    v12 = v7 | (FileId << 52);
    return v11 | v12;
  }
  if ( a2 != Type )
  {
    v14 = strrchr("admin\\appman\\appv\\shared\\clientconfiguration\\RegistryValue.h", 92);
    if ( v14 )
      v15 = v14 + 1;
    else
      v15 = "admin\\appman\\appv\\shared\\clientconfiguration\\RegistryValue.h";
    v12 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v15) << 52;
    v11 = 0x350500040002LL;
    return v11 | v12;
  }
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x140044f18  mov     [rsp+arg_8], rbx
0x140044f1d  push    rdi
0x140044f1e  sub     rsp, 30h
0x140044f22  mov     ebx, edx
0x140044f24  mov     [rsp+38h+cbData], r9d
0x140044f29  lea     rdx, [rcx+40h]
0x140044f2d  mov     [rsp+38h+Type], 0
0x140044f35  cmp     qword ptr [rdx+18h], 7
0x140044f3a  jbe     short loc_140044F3F
0x140044f3c  mov     rdx, [rdx]; lpValueName
0x140044f3f  mov     rcx, [rcx+60h]; hKey
0x140044f43  lea     rax, [rsp+38h+cbData]
0x140044f48  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140044f4d  lea     r9, [rsp+38h+Type]; lpType
0x140044f52  mov     [rsp+38h+lpData], r8; lpData
0x140044f57  xor     r8d, r8d; lpReserved
0x140044f5a  call    cs:__imp_RegQueryValueExW
0x140044f60  mov     edi, eax
0x140044f62  test    eax, eax
0x140044f64  jz      short loc_140044FAE
0x140044f66  mov     edx, 5Ch ; '\'; Ch
0x140044f6b  lea     rcx, aAdminAppmanApp_0; "admin\\appman\\appv\\shared\\clientconf"...
0x140044f72  call    cs:__imp_strrchr
0x140044f78  test    rax, rax
0x140044f7b  jz      short loc_140044F82
0x140044f7d  inc     rax
0x140044f80  jmp     short loc_140044F89
0x140044f82  lea     rax, aAdminAppmanApp_0; "admin\\appman\\appv\\shared\\clientconf"...
0x140044f89  mov     rdx, rax; char *
0x140044f8c  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140044f93  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140044f98  shl     rax, 34h
0x140044f9c  mov     rcx, 342500000000h
0x140044fa6  or      rax, rdi
0x140044fa9  or      rax, rcx
0x140044fac  jmp     short loc_140045000
0x140044fae  cmp     ebx, [rsp+38h+Type]
0x140044fb2  jz      short loc_140044FF6
0x140044fb4  mov     edx, 5Ch ; '\'; Ch
0x140044fb9  lea     rcx, aAdminAppmanApp_0; "admin\\appman\\appv\\shared\\clientconf"...
0x140044fc0  call    cs:__imp_strrchr
0x140044fc6  test    rax, rax
0x140044fc9  jz      short loc_140044FD0
0x140044fcb  inc     rax
0x140044fce  jmp     short loc_140044FD7
0x140044fd0  lea     rax, aAdminAppmanApp_0; "admin\\appman\\appv\\shared\\clientconf"...
0x140044fd7  mov     rdx, rax; char *
0x140044fda  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140044fe1  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140044fe6  shl     rax, 34h
0x140044fea  mov     rcx, 350500040002h
0x140044ff4  jmp     short loc_140044FA9
0x140044ff6  mov     rax, 8000000000h
0x140045000  mov     rbx, [rsp+38h+arg_8]
0x140045005  add     rsp, 30h
0x140045009  pop     rdi
0x14004500a  retn
```
