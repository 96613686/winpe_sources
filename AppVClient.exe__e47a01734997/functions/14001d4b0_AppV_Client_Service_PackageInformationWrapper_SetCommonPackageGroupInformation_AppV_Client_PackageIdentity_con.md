# AppV::Client::Service::PackageInformationWrapper::SetCommonPackageGroupInformation(AppV::Client::PackageIdentity const &,PackageGroupProperties &)

- ea: `0x14001d4b0`
- end: `0x14001d5d9`
- name: `?SetCommonPackageGroupInformation@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEBUPackageIdentity@34@AEAUPackageGroupProperties@@@Z`
- size: `297`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Service::PackageInformationWrapper *__hidden this, const struct AppV::Client::PackageIdentity *, struct PackageGroupProperties *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001a1a0`
- `0x14001a610`

## callees

- `0x140004280`
- `0x140006304`
- `0x140018bec`
- `0x14001b390`
- `0x14001bff0`
- `0x14001d4b0`
- `0x14001dbe8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001d585`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001d585`
- `OLEAUT32!__imp_SysAllocString` at `0x14001d4eb`
- `OLEAUT32!__imp_SysAllocString` at `0x14001d519`
- `OLEAUT32!__imp_SysAllocString` at `0x14001d4eb`
- `OLEAUT32!__imp_SysAllocString` at `0x14001d519`

## string_xrefs

- `0x14001d57e`: `admin\appman\appv\client\host\service\packageinformationwrapper.cpp`
- `0x14001d595`: `admin\appman\appv\client\host\service\packageinformationwrapper.cpp`

## pseudocode

```c
unsigned __int64 __fastcall AppV::Client::Service::PackageInformationWrapper::SetCommonPackageGroupInformation(
        AppV::Client::Service::PackageInformationWrapper *this,
        const struct AppV::Client::PackageIdentity *a2,
        struct PackageGroupProperties *a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  unsigned __int64 result; // rax
  char *v9; // rax
  const char *v10; // rax
  char *v11[4]; // [rsp+20h] [rbp-48h] BYREF

  v6 = softricity::shared::tostring(v11, a2);
  if ( *(_QWORD *)(v6 + 24) > 7u )
    v6 = *(_QWORD *)v6;
  *(_QWORD *)a3 = SysAllocString((const OLECHAR *)v6);
  std::wstring::~wstring(v11);
  v7 = softricity::shared::tostring(v11, (char *)a2 + 16);
  if ( *(_QWORD *)(v7 + 24) > 7u )
    v7 = *(_QWORD *)v7;
  *((_QWORD *)a3 + 1) = SysAllocString((const OLECHAR *)v7);
  std::wstring::~wstring(v11);
  if ( *(_QWORD *)a3 && *((_QWORD *)a3 + 1) )
  {
    result = AppV::Client::Service::PackageInformationWrapper::GetPackageGroupDisplayName(this, a2, (wchar_t **)a3 + 2);
    if ( (result & 0x8000000000LL) != 0 )
    {
      if ( (AppV::Client::Service::PackageInformationWrapper::GetPackageGroupPriority(this, a2, (unsigned int *)a3 + 6)
          & 0x8000000000LL) == 0 )
        *((_DWORD *)a3 + 6) = -1;
      return 0x8000000000LL;
    }
  }
  else
  {
    v9 = strrchr("admin\\appman\\appv\\client\\host\\service\\packageinformationwrapper.cpp", 92);
    if ( v9 )
      v10 = v9 + 1;
    else
      v10 = "admin\\appman\\appv\\client\\host\\service\\packageinformationwrapper.cpp";
    return (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v10) << 52)
         | 0x40230000000ELL;
  }
  return result;
}

```

## disassembly

```asm
0x14001d4b0  mov     [rsp+arg_18], rbx
0x14001d4b5  push    rbp
0x14001d4b6  push    rsi
0x14001d4b7  push    rdi
0x14001d4b8  sub     rsp, 50h
0x14001d4bc  mov     rax, cs:__security_cookie
0x14001d4c3  xor     rax, rsp
0x14001d4c6  mov     [rsp+68h+var_28], rax
0x14001d4cb  mov     rsi, rcx
0x14001d4ce  mov     rbx, r8
0x14001d4d1  lea     rcx, [rsp+68h+var_48]
0x14001d4d6  mov     rdi, rdx
0x14001d4d9  call    ?tostring@shared@softricity@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; softricity::shared::tostring(_GUID const &,bool)
0x14001d4de  cmp     qword ptr [rax+18h], 7
0x14001d4e3  jbe     short loc_14001D4E8
0x14001d4e5  mov     rax, [rax]
0x14001d4e8  mov     rcx, rax; psz
0x14001d4eb  call    cs:__imp_SysAllocString
0x14001d4f1  lea     rcx, [rsp+68h+var_48]
0x14001d4f6  mov     [rbx], rax
0x14001d4f9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001d4fe  lea     rdx, [rdi+10h]
0x14001d502  lea     rcx, [rsp+68h+var_48]
0x14001d507  call    ?tostring@shared@softricity@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; softricity::shared::tostring(_GUID const &,bool)
0x14001d50c  cmp     qword ptr [rax+18h], 7
0x14001d511  jbe     short loc_14001D516
0x14001d513  mov     rax, [rax]
0x14001d516  mov     rcx, rax; psz
0x14001d519  call    cs:__imp_SysAllocString
0x14001d51f  lea     rcx, [rsp+68h+var_48]
0x14001d524  mov     [rbx+8], rax
0x14001d528  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001d52d  cmp     qword ptr [rbx], 0
0x14001d531  jz      short loc_14001D579
0x14001d533  cmp     qword ptr [rbx+8], 0
0x14001d538  jz      short loc_14001D579
0x14001d53a  lea     r8, [rbx+10h]; wchar_t **
0x14001d53e  mov     rdx, rdi; struct AppV::Client::PackageIdentity *
0x14001d541  mov     rcx, rsi; this
0x14001d544  call    ?GetPackageGroupDisplayName@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEBUPackageIdentity@34@AEAPEA_W@Z; AppV::Client::Service::PackageInformationWrapper::GetPackageGroupDisplayName(AppV::Client::PackageIdentity const &,wchar_t * &)
0x14001d549  bt      rax, 27h ; '''
0x14001d54e  jnb     short loc_14001D5BC
0x14001d550  lea     r8, [rbx+18h]; unsigned int *
0x14001d554  mov     rdx, rdi; struct AppV::Client::PackageIdentity *
0x14001d557  mov     rcx, rsi; this
0x14001d55a  call    ?GetPackageGroupPriority@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEBUPackageIdentity@34@AEAI@Z; AppV::Client::Service::PackageInformationWrapper::GetPackageGroupPriority(AppV::Client::PackageIdentity const &,uint &)
0x14001d55f  bt      rax, 27h ; '''
0x14001d564  jb      short loc_14001D56D
0x14001d566  mov     dword ptr [rbx+18h], 0FFFFFFFFh
0x14001d56d  mov     rax, 8000000000h
0x14001d577  jmp     short loc_14001D5BC
0x14001d579  mov     edx, 5Ch ; '\'; Ch
0x14001d57e  lea     rcx, aAdminAppmanApp_11; "admin\\appman\\appv\\client\\host\\serv"...
0x14001d585  call    cs:__imp_strrchr
0x14001d58b  test    rax, rax
0x14001d58e  jz      short loc_14001D595
0x14001d590  inc     rax
0x14001d593  jmp     short loc_14001D59C
0x14001d595  lea     rax, aAdminAppmanApp_11; "admin\\appman\\appv\\client\\host\\serv"...
0x14001d59c  mov     rdx, rax; char *
0x14001d59f  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14001d5a6  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14001d5ab  shl     rax, 34h
0x14001d5af  mov     rcx, 40230000000Eh
0x14001d5b9  or      rax, rcx
0x14001d5bc  mov     rcx, [rsp+68h+var_28]
0x14001d5c1  xor     rcx, rsp; StackCookie
0x14001d5c4  call    __security_check_cookie
0x14001d5c9  mov     rbx, [rsp+68h+arg_18]
0x14001d5d1  add     rsp, 50h
0x14001d5d5  pop     rdi
0x14001d5d6  pop     rsi
0x14001d5d7  pop     rbp
0x14001d5d8  retn
```
