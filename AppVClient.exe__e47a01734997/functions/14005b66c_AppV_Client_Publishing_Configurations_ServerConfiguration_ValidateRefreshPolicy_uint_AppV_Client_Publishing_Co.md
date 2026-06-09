# AppV::Client::Publishing::Configurations::ServerConfiguration::ValidateRefreshPolicy(uint,AppV::Client::Publishing::Configurations::ServerProperties::RefreshPolicy const &)

- ea: `0x14005b66c`
- end: `0x14005b89d`
- name: `?ValidateRefreshPolicy@ServerConfiguration@Configurations@Publishing@Client@AppV@@AEAA_KIAEBURefreshPolicy@ServerProperties@2345@@Z`
- size: `561`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Publishing::Configurations::ServerConfiguration *__hidden this, unsigned int, const struct AppV::Client::Publishing::Configurations::ServerProperties::RefreshPolicy *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005b8a4`

## callees

- `0x140004280`
- `0x1400147fc`
- `0x140018bec`
- `0x14005b66c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005b705`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005b7a6`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005b845`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005b705`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005b7a6`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005b845`

## string_xrefs

- `0x14005b6fe`: `admin\appman\appv\client\publishing\configurations\serverconfiguration.cpp`
- `0x14005b715`: `admin\appman\appv\client\publishing\configurations\serverconfiguration.cpp`
- `0x14005b79f`: `admin\appman\appv\client\publishing\configurations\serverconfiguration.cpp`
- `0x14005b7b6`: `admin\appman\appv\client\publishing\configurations\serverconfiguration.cpp`
- `0x14005b83e`: `admin\appman\appv\client\publishing\configurations\serverconfiguration.cpp`
- `0x14005b855`: `admin\appman\appv\client\publishing\configurations\serverconfiguration.cpp`

## pseudocode

```c
unsigned __int64 __fastcall AppV::Client::Publishing::Configurations::ServerConfiguration::ValidateRefreshPolicy(
        AppV::Client::Publishing::Configurations::ServerConfiguration *this,
        int a2,
        const struct AppV::Client::Publishing::Configurations::ServerProperties::RefreshPolicy *a3)
{
  int v3; // r9d
  char *v4; // rax
  const char *v5; // rax
  unsigned __int64 FileId; // rax
  __int64 v7; // rcx
  char *v8; // rax
  const char *v9; // rax
  char *v10; // rax
  const char *v11; // rax
  int v13; // [rsp+30h] [rbp-50h] BYREF
  int v14; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v15[16]; // [rsp+40h] [rbp-40h] BYREF
  int *v16; // [rsp+50h] [rbp-30h]
  __int64 v17; // [rsp+58h] [rbp-28h]
  int *v18; // [rsp+60h] [rbp-20h]
  __int64 v19; // [rsp+68h] [rbp-18h]

  if ( *(_BYTE *)a3 )
  {
    v3 = *((_DWORD *)a3 + 2);
    if ( v3 )
    {
      if ( v3 != 1 )
      {
        if ( (byte_1400B0B86 & 0x40) != 0 )
        {
          v14 = *((_DWORD *)a3 + 2);
          v16 = &v13;
          v13 = a2;
          v18 = &v14;
          v17 = 4;
          v19 = 4;
          McGenEventWrite_EventWriteTransfer(
            PROVIDER_MICROSOFT_APPV_CLIENT_Context,
            APPV_CLIENT_Evt_refreshConfigServerInvalidIntervalUnit,
            a3,
            3,
            v15);
        }
        v4 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverconfiguration.cpp", 92);
        if ( v4 )
          v5 = v4 + 1;
        else
          v5 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverconfiguration.cpp";
        FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v5);
        v7 = 0x1D0700000709LL;
        return v7 | (FileId << 52);
      }
      if ( *((_DWORD *)a3 + 1) > 0x16Du )
      {
        if ( (byte_1400B0B86 & 0x40) != 0 )
        {
          v13 = *((_DWORD *)a3 + 1);
          v14 = a2;
          v16 = &v14;
          v18 = &v13;
          v17 = 4;
          v19 = 4;
          McGenEventWrite_EventWriteTransfer(
            PROVIDER_MICROSOFT_APPV_CLIENT_Context,
            APPV_CLIENT_Evt_refreshConfigServerDayOutOfRange,
            a3,
            3,
            v15);
        }
        v8 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverconfiguration.cpp", 92);
        if ( v8 )
          v9 = v8 + 1;
        else
          v9 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverconfiguration.cpp";
        FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v9);
        v7 = 0x1C0700000707LL;
        return v7 | (FileId << 52);
      }
    }
    else if ( *((_DWORD *)a3 + 1) > 0x17u )
    {
      if ( (byte_1400B0B86 & 0x40) != 0 )
      {
        v13 = *((_DWORD *)a3 + 1);
        v14 = a2;
        v16 = &v14;
        v18 = &v13;
        v17 = 4;
        v19 = 4;
        McGenEventWrite_EventWriteTransfer(
          PROVIDER_MICROSOFT_APPV_CLIENT_Context,
          APPV_CLIENT_Evt_refreshConfigServerHourOutOfRange,
          a3,
          3,
          v15);
      }
      v10 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverconfiguration.cpp", 92);
      if ( v10 )
        v11 = v10 + 1;
      else
        v11 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverconfiguration.cpp";
      FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v11);
      v7 = 0x1C0700000708LL;
      return v7 | (FileId << 52);
    }
  }
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x14005b66c  push    rbp
0x14005b66e  mov     rbp, rsp
0x14005b671  sub     rsp, 80h
0x14005b678  mov     rax, cs:__security_cookie
0x14005b67f  xor     rax, rsp
0x14005b682  mov     [rbp+var_10], rax
0x14005b686  cmp     byte ptr [r8], 0
0x14005b68a  jz      loc_14005B87E
0x14005b690  mov     r9d, [r8+8]
0x14005b694  test    r9d, r9d
0x14005b697  jz      loc_14005B7DB
0x14005b69d  cmp     r9d, 1
0x14005b6a1  jz      loc_14005B73A
0x14005b6a7  test    cs:byte_1400B0B86, 40h
0x14005b6ae  jz      short loc_14005B6F9
0x14005b6b0  lea     rax, [rbp+var_50]
0x14005b6b4  mov     [rbp+var_48], r9d
0x14005b6b8  lea     rcx, [rbp+var_48]
0x14005b6bc  mov     [rbp+var_30], rax
0x14005b6c0  lea     rax, [rbp+var_40]
0x14005b6c4  mov     [rbp+var_50], edx
0x14005b6c7  mov     [rbp+var_20], rcx
0x14005b6cb  lea     rdx, APPV_CLIENT_Evt_refreshConfigServerInvalidIntervalUnit
0x14005b6d2  mov     r9d, 3
0x14005b6d8  mov     [rsp+80h+var_60], rax
0x14005b6dd  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x14005b6e4  mov     [rbp+var_28], 4
0x14005b6ec  mov     [rbp+var_18], 4
0x14005b6f4  call    McGenEventWrite_EventWriteTransfer
0x14005b6f9  mov     edx, 5Ch ; '\'; Ch
0x14005b6fe  lea     rcx, aAdminAppmanApp_8; "admin\\appman\\appv\\client\\publishing"...
0x14005b705  call    cs:__imp_strrchr
0x14005b70b  test    rax, rax
0x14005b70e  jz      short loc_14005B715
0x14005b710  inc     rax
0x14005b713  jmp     short loc_14005B71C
0x14005b715  lea     rax, aAdminAppmanApp_8; "admin\\appman\\appv\\client\\publishing"...
0x14005b71c  mov     rdx, rax; char *
0x14005b71f  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005b726  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005b72b  mov     rcx, 1D0700000709h
0x14005b735  jmp     loc_14005B875
0x14005b73a  mov     eax, [r8+4]
0x14005b73e  cmp     eax, 16Dh
0x14005b743  jbe     loc_14005B87E
0x14005b749  test    cs:byte_1400B0B86, 40h
0x14005b750  jz      short loc_14005B79A
0x14005b752  mov     [rbp+var_50], eax
0x14005b755  lea     rcx, [rbp+var_50]
0x14005b759  lea     rax, [rbp+var_48]
0x14005b75d  mov     [rbp+var_48], edx
0x14005b760  mov     [rbp+var_30], rax
0x14005b764  lea     rdx, APPV_CLIENT_Evt_refreshConfigServerDayOutOfRange
0x14005b76b  lea     rax, [rbp+var_40]
0x14005b76f  mov     [rbp+var_20], rcx
0x14005b773  mov     r9d, 3
0x14005b779  mov     [rsp+80h+var_60], rax
0x14005b77e  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x14005b785  mov     [rbp+var_28], 4
0x14005b78d  mov     [rbp+var_18], 4
0x14005b795  call    McGenEventWrite_EventWriteTransfer
0x14005b79a  mov     edx, 5Ch ; '\'; Ch
0x14005b79f  lea     rcx, aAdminAppmanApp_8; "admin\\appman\\appv\\client\\publishing"...
0x14005b7a6  call    cs:__imp_strrchr
0x14005b7ac  test    rax, rax
0x14005b7af  jz      short loc_14005B7B6
0x14005b7b1  inc     rax
0x14005b7b4  jmp     short loc_14005B7BD
0x14005b7b6  lea     rax, aAdminAppmanApp_8; "admin\\appman\\appv\\client\\publishing"...
0x14005b7bd  mov     rdx, rax; char *
0x14005b7c0  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005b7c7  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005b7cc  mov     rcx, 1C0700000707h
0x14005b7d6  jmp     loc_14005B875
0x14005b7db  mov     eax, [r8+4]
0x14005b7df  cmp     eax, 17h
0x14005b7e2  jbe     loc_14005B87E
0x14005b7e8  test    cs:byte_1400B0B86, 40h
0x14005b7ef  jz      short loc_14005B839
0x14005b7f1  mov     [rbp+var_50], eax
0x14005b7f4  lea     rcx, [rbp+var_50]
0x14005b7f8  lea     rax, [rbp+var_48]
0x14005b7fc  mov     [rbp+var_48], edx
0x14005b7ff  mov     [rbp+var_30], rax
0x14005b803  lea     rdx, APPV_CLIENT_Evt_refreshConfigServerHourOutOfRange
0x14005b80a  lea     rax, [rbp+var_40]
0x14005b80e  mov     [rbp+var_20], rcx
0x14005b812  mov     r9d, 3
0x14005b818  mov     [rsp+80h+var_60], rax
0x14005b81d  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x14005b824  mov     [rbp+var_28], 4
0x14005b82c  mov     [rbp+var_18], 4
0x14005b834  call    McGenEventWrite_EventWriteTransfer
0x14005b839  mov     edx, 5Ch ; '\'; Ch
0x14005b83e  lea     rcx, aAdminAppmanApp_8; "admin\\appman\\appv\\client\\publishing"...
0x14005b845  call    cs:__imp_strrchr
0x14005b84b  test    rax, rax
0x14005b84e  jz      short loc_14005B855
0x14005b850  inc     rax
0x14005b853  jmp     short loc_14005B85C
0x14005b855  lea     rax, aAdminAppmanApp_8; "admin\\appman\\appv\\client\\publishing"...
0x14005b85c  mov     rdx, rax; char *
0x14005b85f  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005b866  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005b86b  mov     rcx, 1C0700000708h
0x14005b875  shl     rax, 34h
0x14005b879  or      rax, rcx
0x14005b87c  jmp     short loc_14005B888
0x14005b87e  mov     rax, 8000000000h
0x14005b888  mov     rcx, [rbp+var_10]
0x14005b88c  xor     rcx, rsp; StackCookie
0x14005b88f  call    __security_check_cookie
0x14005b894  add     rsp, 80h
0x14005b89b  pop     rbp
0x14005b89c  retn
```
