# AppV::Client::Publishing::Configurations::ServerConfiguration::ValidateServerEntry(AppV::Client::Publishing::Configurations::ServerProperties const &,bool)

- ea: `0x14005b8a4`
- end: `0x14005ba34`
- name: `?ValidateServerEntry@ServerConfiguration@Configurations@Publishing@Client@AppV@@AEAA_KAEBUServerProperties@2345@_N@Z`
- size: `400`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Publishing::Configurations::ServerConfiguration *__hidden this, const struct AppV::Client::Publishing::Configurations::ServerProperties *, bool)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005ae3c`
- `0x14005b3d0`
- `0x14005b400`

## callees

- `0x140004280`
- `0x1400147fc`
- `0x140018bec`
- `0x14005b66c`
- `0x14005b8a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005b928`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005b9b2`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005b928`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005b9b2`

## string_xrefs

- `0x14005b921`: `admin\appman\appv\client\publishing\configurations\serverconfiguration.cpp`
- `0x14005b938`: `admin\appman\appv\client\publishing\configurations\serverconfiguration.cpp`
- `0x14005b9ab`: `admin\appman\appv\client\publishing\configurations\serverconfiguration.cpp`
- `0x14005b9c2`: `admin\appman\appv\client\publishing\configurations\serverconfiguration.cpp`

## pseudocode

```c
__int64 __fastcall AppV::Client::Publishing::Configurations::ServerConfiguration::ValidateServerEntry(
        AppV::Client::Publishing::Configurations::ServerConfiguration *this,
        const struct AppV::Client::Publishing::Configurations::ServerProperties *a2,
        __int64 a3)
{
  char *v4; // rax
  const char *v5; // rax
  unsigned __int64 FileId; // rax
  __int64 v7; // rcx
  __int64 result; // rax
  char *v9; // rax
  const char *v10; // rax
  AppV::Client::Publishing::Configurations::ServerConfiguration *v11; // rcx
  __int64 v12; // rdi
  unsigned __int64 refreshed; // rax
  int v14; // [rsp+30h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+38h] [rbp-28h] BYREF
  int *v16; // [rsp+48h] [rbp-18h]
  __int64 v17; // [rsp+50h] [rbp-10h]

  if ( (_BYTE)a3 )
  {
    this = (AppV::Client::Publishing::Configurations::ServerConfiguration *)*(unsigned int *)a2;
    if ( (unsigned int)((_DWORD)this - 1) > 4 )
    {
      if ( (byte_1400B0B86 & 0x40) != 0 )
      {
        v14 = *(_DWORD *)a2;
        v16 = &v14;
        v17 = 4;
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)PROVIDER_MICROSOFT_APPV_CLIENT_Context,
          (const EVENT_DESCRIPTOR *)APPV_CLIENT_Evt_refreshConfigServerIdOutOfRange,
          a3,
          2u,
          &v15);
      }
      v4 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverconfiguration.cpp", 92);
      if ( v4 )
        v5 = v4 + 1;
      else
        v5 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverconfiguration.cpp";
      FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v5);
      v7 = 0x180700000706LL;
      return v7 | (FileId << 52);
    }
  }
  if ( !*((_QWORD *)a2 + 7) )
  {
    if ( (byte_1400B0B86 & 0x40) != 0 )
    {
      v14 = *(_DWORD *)a2;
      v17 = 4;
      v16 = &v14;
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)PROVIDER_MICROSOFT_APPV_CLIENT_Context,
        (const EVENT_DESCRIPTOR *)APPV_CLIENT_Evt_refreshConfigServerNoUrl,
        a3,
        2u,
        &v15);
    }
    v9 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverconfiguration.cpp", 92);
    if ( v9 )
      v10 = v9 + 1;
    else
      v10 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverconfiguration.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v10);
    v7 = 0x180700000703LL;
    return v7 | (FileId << 52);
  }
  result = AppV::Client::Publishing::Configurations::ServerConfiguration::ValidateRefreshPolicy(
             this,
             *(_DWORD *)a2,
             (const struct AppV::Client::Publishing::Configurations::ServerProperties *)((char *)a2 + 72));
  v12 = 0x8000000000LL;
  if ( (result & 0x8000000000LL) != 0 )
  {
    refreshed = AppV::Client::Publishing::Configurations::ServerConfiguration::ValidateRefreshPolicy(
                  v11,
                  *(_DWORD *)a2,
                  (const struct AppV::Client::Publishing::Configurations::ServerProperties *)((char *)a2 + 84));
    if ( (refreshed & 0x8000000000LL) == 0 )
      return refreshed;
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x14005b8a4  mov     [rsp-8+arg_0], rbx
0x14005b8a9  mov     [rsp-8+arg_10], rdi
0x14005b8ae  push    rbp
0x14005b8af  mov     rbp, rsp
0x14005b8b2  sub     rsp, 60h
0x14005b8b6  mov     rax, cs:__security_cookie
0x14005b8bd  xor     rax, rsp
0x14005b8c0  mov     [rbp+var_8], rax
0x14005b8c4  xor     edi, edi
0x14005b8c6  mov     rbx, rdx
0x14005b8c9  mov     edx, 4
0x14005b8ce  test    r8b, r8b
0x14005b8d1  jz      loc_14005B964
0x14005b8d7  mov     ecx, [rbx]
0x14005b8d9  lea     eax, [rcx-1]
0x14005b8dc  cmp     eax, edx
0x14005b8de  jbe     loc_14005B964
0x14005b8e4  test    cs:byte_1400B0B86, 40h
0x14005b8eb  jz      short loc_14005B91C
0x14005b8ed  lea     rax, [rbp+var_30]
0x14005b8f1  mov     [rbp+var_30], ecx
0x14005b8f4  mov     [rbp+var_18], rax
0x14005b8f8  lea     r9d, [rdx-2]
0x14005b8fc  lea     rax, [rbp+var_28]
0x14005b900  mov     [rbp+var_10], rdx
0x14005b904  lea     rdx, APPV_CLIENT_Evt_refreshConfigServerIdOutOfRange
0x14005b90b  mov     [rsp+60h+var_40], rax
0x14005b910  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x14005b917  call    McGenEventWrite_EventWriteTransfer
0x14005b91c  mov     edx, 5Ch ; '\'; Ch
0x14005b921  lea     rcx, aAdminAppmanApp_8; "admin\\appman\\appv\\client\\publishing"...
0x14005b928  call    cs:__imp_strrchr
0x14005b92e  test    rax, rax
0x14005b931  jz      short loc_14005B938
0x14005b933  inc     rax
0x14005b936  jmp     short loc_14005B93F
0x14005b938  lea     rax, aAdminAppmanApp_8; "admin\\appman\\appv\\client\\publishing"...
0x14005b93f  mov     rdx, rax; char *
0x14005b942  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005b949  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005b94e  mov     rcx, 180700000706h
0x14005b958  shl     rax, 34h
0x14005b95c  or      rax, rcx
0x14005b95f  jmp     loc_14005BA16
0x14005b964  cmp     [rbx+38h], rdi
0x14005b968  jnz     short loc_14005B9E7
0x14005b96a  test    cs:byte_1400B0B86, 40h
0x14005b971  jz      short loc_14005B9A6
0x14005b973  mov     eax, [rbx]
0x14005b975  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x14005b97c  mov     [rbp+var_30], eax
0x14005b97f  mov     r9d, 2
0x14005b985  lea     rax, [rbp+var_30]
0x14005b989  mov     [rbp+var_10], rdx
0x14005b98d  mov     [rbp+var_18], rax
0x14005b991  lea     rdx, APPV_CLIENT_Evt_refreshConfigServerNoUrl
0x14005b998  lea     rax, [rbp+var_28]
0x14005b99c  mov     [rsp+60h+var_40], rax
0x14005b9a1  call    McGenEventWrite_EventWriteTransfer
0x14005b9a6  mov     edx, 5Ch ; '\'; Ch
0x14005b9ab  lea     rcx, aAdminAppmanApp_8; "admin\\appman\\appv\\client\\publishing"...
0x14005b9b2  call    cs:__imp_strrchr
0x14005b9b8  test    rax, rax
0x14005b9bb  jz      short loc_14005B9C2
0x14005b9bd  inc     rax
0x14005b9c0  jmp     short loc_14005B9C9
0x14005b9c2  lea     rax, aAdminAppmanApp_8; "admin\\appman\\appv\\client\\publishing"...
0x14005b9c9  mov     rdx, rax; char *
0x14005b9cc  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005b9d3  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005b9d8  mov     rcx, 180700000703h; this
0x14005b9e2  jmp     loc_14005B958
0x14005b9e7  mov     edx, [rbx]; unsigned int
0x14005b9e9  lea     r8, [rbx+48h]; struct AppV::Client::Publishing::Configurations::ServerProperties::RefreshPolicy *
0x14005b9ed  call    ?ValidateRefreshPolicy@ServerConfiguration@Configurations@Publishing@Client@AppV@@AEAA_KIAEBURefreshPolicy@ServerProperties@2345@@Z; AppV::Client::Publishing::Configurations::ServerConfiguration::ValidateRefreshPolicy(uint,AppV::Client::Publishing::Configurations::ServerProperties::RefreshPolicy const &)
0x14005b9f2  mov     rdi, 8000000000h
0x14005b9fc  test    rdi, rax
0x14005b9ff  jz      short loc_14005BA16
0x14005ba01  mov     edx, [rbx]; unsigned int
0x14005ba03  lea     r8, [rbx+54h]; struct AppV::Client::Publishing::Configurations::ServerProperties::RefreshPolicy *
0x14005ba07  call    ?ValidateRefreshPolicy@ServerConfiguration@Configurations@Publishing@Client@AppV@@AEAA_KIAEBURefreshPolicy@ServerProperties@2345@@Z; AppV::Client::Publishing::Configurations::ServerConfiguration::ValidateRefreshPolicy(uint,AppV::Client::Publishing::Configurations::ServerProperties::RefreshPolicy const &)
0x14005ba0c  test    rdi, rax
0x14005ba0f  cmovz   rdi, rax
0x14005ba13  mov     rax, rdi
0x14005ba16  mov     rcx, [rbp+var_8]
0x14005ba1a  xor     rcx, rsp; StackCookie
0x14005ba1d  call    __security_check_cookie
0x14005ba22  lea     r11, [rsp+60h+var_s0]
0x14005ba27  mov     rbx, [r11+10h]
0x14005ba2b  mov     rdi, [r11+20h]
0x14005ba2f  mov     rsp, r11
0x14005ba32  pop     rbp
0x14005ba33  retn
```
