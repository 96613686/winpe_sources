# AppV::ClientConfiguration::Impl::RegistryValueT<AppV::ClientConfiguration::Impl::RegistryValueEmpty>::ReadValueSize(ulong,ulong &)

- ea: `0x140045014`
- end: `0x140045176`
- name: `?ReadValueSize@?$RegistryValueT@URegistryValueEmpty@Impl@ClientConfiguration@AppV@@@Impl@ClientConfiguration@AppV@@AEAA_KKAEAK@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140044e14`

## callees

- `0x140018bec`
- `0x140045014`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140045064`
- `ADVAPI32!RegQueryValueExW` at `0x140045064`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140045083`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400450d4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140045121`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140045083`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400450d4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140045121`

## string_xrefs

- `0x14004507c`: `admin\appman\appv\shared\clientconfiguration\RegistryValue.h`
- `0x140045093`: `admin\appman\appv\shared\clientconfiguration\RegistryValue.h`
- `0x1400450cd`: `admin\appman\appv\shared\clientconfiguration\RegistryValue.h`
- `0x1400450e4`: `admin\appman\appv\shared\clientconfiguration\RegistryValue.h`
- `0x14004511a`: `admin\appman\appv\shared\clientconfiguration\RegistryValue.h`
- `0x140045131`: `admin\appman\appv\shared\clientconfiguration\RegistryValue.h`

## pseudocode

```c
__int64 __fastcall AppV::ClientConfiguration::Impl::RegistryValueT<AppV::ClientConfiguration::Impl::RegistryValueEmpty>::ReadValueSize(
        __int64 a1,
        int a2,
        DWORD *a3)
{
  const WCHAR *v4; // rdx
  unsigned int v6; // eax
  __int64 v7; // rbx
  char *v8; // rax
  const char *v9; // rax
  unsigned __int64 FileId; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rax
  char *v14; // rax
  const char *v15; // rax
  char *v16; // rax
  const char *v17; // rax
  DWORD Type; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF

  cbData = 0;
  v4 = (const WCHAR *)(a1 + 64);
  Type = 0;
  if ( *(_QWORD *)(a1 + 88) > 7u )
    v4 = *(const WCHAR **)v4;
  v6 = RegQueryValueExW(*(HKEY *)(a1 + 96), v4, 0, &Type, 0, &cbData);
  v7 = v6;
  if ( v6 != 234 && v6 )
  {
    v8 = strrchr("admin\\appman\\appv\\shared\\clientconfiguration\\RegistryValue.h", 92);
    if ( v8 )
      v9 = v8 + 1;
    else
      v9 = "admin\\appman\\appv\\shared\\clientconfiguration\\RegistryValue.h";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v9);
    v11 = 0x312500000000LL;
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
    v11 = 0x320500040002LL;
    return v11 | v12;
  }
  if ( cbData >= 0x4000 )
  {
    v16 = strrchr("admin\\appman\\appv\\shared\\clientconfiguration\\RegistryValue.h", 92);
    if ( v16 )
      v17 = v16 + 1;
    else
      v17 = "admin\\appman\\appv\\shared\\clientconfiguration\\RegistryValue.h";
    v12 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v17) << 52;
    v11 = 0x330500040003LL;
    return v11 | v12;
  }
  *a3 = cbData;
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x140045014  mov     rax, rsp
0x140045017  mov     [rax+10h], rbx
0x14004501b  mov     [rax+18h], rsi
0x14004501f  push    rdi
0x140045020  sub     rsp, 30h
0x140045024  mov     esi, edx
0x140045026  mov     dword ptr [rax+20h], 0
0x14004502d  lea     rdx, [rcx+40h]
0x140045031  mov     dword ptr [rax+8], 0
0x140045038  cmp     qword ptr [rdx+18h], 7
0x14004503d  mov     rdi, r8
0x140045040  jbe     short loc_140045045
0x140045042  mov     rdx, [rdx]; lpValueName
0x140045045  mov     rcx, [rcx+60h]; hKey
0x140045049  lea     rax, [rsp+38h+cbData]
0x14004504e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140045053  lea     r9, [rsp+38h+Type]; lpType
0x140045058  xor     r8d, r8d; lpReserved
0x14004505b  mov     [rsp+38h+lpData], 0; lpData
0x140045064  call    cs:__imp_RegQueryValueExW
0x14004506a  mov     ebx, eax
0x14004506c  cmp     eax, 0EAh
0x140045071  jz      short loc_1400450C2
0x140045073  test    eax, eax
0x140045075  jz      short loc_1400450C2
0x140045077  mov     edx, 5Ch ; '\'; Ch
0x14004507c  lea     rcx, aAdminAppmanApp_0; "admin\\appman\\appv\\shared\\clientconf"...
0x140045083  call    cs:__imp_strrchr
0x140045089  test    rax, rax
0x14004508c  jz      short loc_140045093
0x14004508e  inc     rax
0x140045091  jmp     short loc_14004509A
0x140045093  lea     rax, aAdminAppmanApp_0; "admin\\appman\\appv\\shared\\clientconf"...
0x14004509a  mov     rdx, rax; char *
0x14004509d  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400450a4  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400450a9  shl     rax, 34h
0x1400450ad  mov     rcx, 312500000000h
0x1400450b7  or      rax, rbx
0x1400450ba  or      rax, rcx
0x1400450bd  jmp     loc_140045166
0x1400450c2  cmp     esi, [rsp+38h+Type]
0x1400450c6  jz      short loc_14004510A
0x1400450c8  mov     edx, 5Ch ; '\'; Ch
0x1400450cd  lea     rcx, aAdminAppmanApp_0; "admin\\appman\\appv\\shared\\clientconf"...
0x1400450d4  call    cs:__imp_strrchr
0x1400450da  test    rax, rax
0x1400450dd  jz      short loc_1400450E4
0x1400450df  inc     rax
0x1400450e2  jmp     short loc_1400450EB
0x1400450e4  lea     rax, aAdminAppmanApp_0; "admin\\appman\\appv\\shared\\clientconf"...
0x1400450eb  mov     rdx, rax; char *
0x1400450ee  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400450f5  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400450fa  shl     rax, 34h
0x1400450fe  mov     rcx, 320500040002h
0x140045108  jmp     short loc_1400450BA
0x14004510a  mov     eax, [rsp+38h+cbData]
0x14004510e  cmp     eax, 4000h
0x140045113  jb      short loc_14004515A
0x140045115  mov     edx, 5Ch ; '\'; Ch
0x14004511a  lea     rcx, aAdminAppmanApp_0; "admin\\appman\\appv\\shared\\clientconf"...
0x140045121  call    cs:__imp_strrchr
0x140045127  test    rax, rax
0x14004512a  jz      short loc_140045131
0x14004512c  inc     rax
0x14004512f  jmp     short loc_140045138
0x140045131  lea     rax, aAdminAppmanApp_0; "admin\\appman\\appv\\shared\\clientconf"...
0x140045138  mov     rdx, rax; char *
0x14004513b  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140045142  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140045147  shl     rax, 34h
0x14004514b  mov     rcx, 330500040003h
0x140045155  jmp     loc_1400450BA
0x14004515a  mov     [rdi], eax
0x14004515c  mov     rax, 8000000000h
0x140045166  mov     rbx, [rsp+38h+arg_8]
0x14004516b  mov     rsi, [rsp+38h+arg_10]
0x140045170  add     rsp, 30h
0x140045174  pop     rdi
0x140045175  retn
```
