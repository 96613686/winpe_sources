# AppV::ClientConfiguration::Impl::RegistryValueT<AppV::ClientConfiguration::Impl::RegistryValueEmpty>::OpenSubKey(HKEY__ *,ulong)

- ea: `0x140044d7c`
- end: `0x140044e0d`
- name: `?OpenSubKey@?$RegistryValueT@URegistryValueEmpty@Impl@ClientConfiguration@AppV@@@Impl@ClientConfiguration@AppV@@AEAA_KPEAUHKEY__@@K@Z`
- size: `145`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140042804`
- `0x1400428d0`
- `0x140042a88`

## callees

- `0x140018bec`
- `0x140044d7c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140044da9`
- `ADVAPI32!RegOpenKeyExW` at `0x140044da9`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140044dcd`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140044dcd`

## string_xrefs

- `0x140044dc6`: `admin\appman\appv\shared\clientconfiguration\RegistryValue.h`
- `0x140044ddd`: `admin\appman\appv\shared\clientconfiguration\RegistryValue.h`

## pseudocode

```c
unsigned __int64 __fastcall AppV::ClientConfiguration::Impl::RegistryValueT<AppV::ClientConfiguration::Impl::RegistryValueEmpty>::OpenSubKey(
        __int64 a1)
{
  const WCHAR *v1; // rdx
  unsigned int v2; // eax
  __int64 v3; // rbx
  char *v5; // rax
  const char *v6; // rax

  v1 = (const WCHAR *)(a1 + 32);
  if ( *(_QWORD *)(a1 + 56) > 7u )
    v1 = *(const WCHAR **)v1;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0x20119u, (PHKEY)(a1 + 96));
  v3 = v2;
  if ( !v2 )
    return 0x8000000000LL;
  v5 = strrchr("admin\\appman\\appv\\shared\\clientconfiguration\\RegistryValue.h", 92);
  if ( v5 )
    v6 = v5 + 1;
  else
    v6 = "admin\\appman\\appv\\shared\\clientconfiguration\\RegistryValue.h";
  return v3
       | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v6) << 52)
       | 0x292500000000LL;
}

```

## disassembly

```asm
0x140044d7c  push    rbx
0x140044d7e  sub     rsp, 30h
0x140044d82  lea     rdx, [rcx+20h]
0x140044d86  cmp     qword ptr [rdx+18h], 7
0x140044d8b  jbe     short loc_140044D90
0x140044d8d  mov     rdx, [rdx]; lpSubKey
0x140044d90  lea     rax, [rcx+60h]
0x140044d94  mov     r9d, 20119h; samDesired
0x140044d9a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140044da1  mov     [rsp+38h+phkResult], rax; phkResult
0x140044da6  xor     r8d, r8d; ulOptions
0x140044da9  call    cs:__imp_RegOpenKeyExW
0x140044daf  mov     ebx, eax
0x140044db1  test    eax, eax
0x140044db3  jnz     short loc_140044DC1
0x140044db5  mov     rax, 8000000000h
0x140044dbf  jmp     short loc_140044E07
0x140044dc1  mov     edx, 5Ch ; '\'; Ch
0x140044dc6  lea     rcx, aAdminAppmanApp_0; "admin\\appman\\appv\\shared\\clientconf"...
0x140044dcd  call    cs:__imp_strrchr
0x140044dd3  test    rax, rax
0x140044dd6  jz      short loc_140044DDD
0x140044dd8  inc     rax
0x140044ddb  jmp     short loc_140044DE4
0x140044ddd  lea     rax, aAdminAppmanApp_0; "admin\\appman\\appv\\shared\\clientconf"...
0x140044de4  mov     rdx, rax; char *
0x140044de7  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140044dee  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140044df3  shl     rax, 34h
0x140044df7  mov     rcx, 292500000000h
0x140044e01  or      rax, rbx
0x140044e04  or      rax, rcx
0x140044e07  add     rsp, 30h
0x140044e0b  pop     rbx
0x140044e0c  retn
```
