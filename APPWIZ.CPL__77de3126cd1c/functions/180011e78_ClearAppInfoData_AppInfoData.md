# ClearAppInfoData(_AppInfoData *)

- ea: `0x180011e78`
- end: `0x180012033`
- name: `?ClearAppInfoData@@YAXPEAU_AppInfoData@@@Z`
- size: `443`
- prototype: `void __fastcall(struct _AppInfoData *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180014600`
- `0x1800198bc`
- `0x18004430c`

## callees

- `0x180011e78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011e9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011eae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011ec2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011ed6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011eea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011efe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011fb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011fc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011fe1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011ffe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001201b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011e9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011eae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011ec2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011ed6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011eea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011efe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011fb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011fc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011fe1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011ffe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001201b`

## pseudocode

```c
void __fastcall ClearAppInfoData(struct _AppInfoData *a1)
{
  if ( a1 )
  {
    if ( (a1->dwMask & 1) != 0 )
    {
      CoTaskMemFree(a1->pszDisplayName);
      a1->pszDisplayName = 0;
    }
    if ( (a1->dwMask & 2) != 0 )
    {
      CoTaskMemFree(a1->pszVersion);
      a1->pszVersion = 0;
    }
    if ( (a1->dwMask & 4) != 0 )
    {
      CoTaskMemFree(a1->pszPublisher);
      a1->pszPublisher = 0;
    }
    if ( (a1->dwMask & 8) != 0 )
    {
      CoTaskMemFree(a1->pszProductID);
      a1->pszProductID = 0;
    }
    if ( (a1->dwMask & 0x10) != 0 )
    {
      CoTaskMemFree(a1->pszRegisteredOwner);
      a1->pszRegisteredOwner = 0;
    }
    if ( (a1->dwMask & 0x20) != 0 )
    {
      CoTaskMemFree(a1->pszRegisteredCompany);
      a1->pszRegisteredCompany = 0;
    }
    if ( (a1->dwMask & 0x40) != 0 )
    {
      CoTaskMemFree(a1->pszLanguage);
      a1->pszLanguage = 0;
    }
    if ( SLOBYTE(a1->dwMask) < 0 )
    {
      CoTaskMemFree(a1->pszSupportUrl);
      a1->pszSupportUrl = 0;
    }
    if ( (a1->dwMask & 0x100) != 0 )
    {
      CoTaskMemFree(a1->pszSupportTelephone);
      a1->pszSupportTelephone = 0;
    }
    if ( (a1->dwMask & 0x200) != 0 )
    {
      CoTaskMemFree(a1->pszHelpLink);
      a1->pszHelpLink = 0;
    }
    if ( (a1->dwMask & 0x400) != 0 )
    {
      CoTaskMemFree(a1->pszInstallLocation);
      a1->pszInstallLocation = 0;
    }
    if ( (a1->dwMask & 0x800) != 0 )
    {
      CoTaskMemFree(a1->pszInstallSource);
      a1->pszInstallSource = 0;
    }
    if ( (a1->dwMask & 0x1000) != 0 )
    {
      CoTaskMemFree(a1->pszInstallDate);
      a1->pszInstallDate = 0;
    }
    if ( (a1->dwMask & 0x4000) != 0 )
    {
      CoTaskMemFree(a1->pszContact);
      a1->pszContact = 0;
    }
    if ( (a1->dwMask & 0x8000) != 0 )
    {
      CoTaskMemFree(a1->pszComments);
      a1->pszComments = 0;
    }
    if ( (a1->dwMask & 0x20000) != 0 )
    {
      CoTaskMemFree(a1->pszImage);
      a1->pszImage = 0;
    }
    if ( (a1->dwMask & 0x40000) != 0 )
    {
      CoTaskMemFree(a1->pszReadmeUrl);
      a1->pszReadmeUrl = 0;
    }
    if ( (a1->dwMask & 0x80000) != 0 )
    {
      CoTaskMemFree(a1->pszUpdateInfoUrl);
      a1->pszUpdateInfoUrl = 0;
    }
  }
}

```

## disassembly

```asm
0x180011e78  test    rcx, rcx
0x180011e7b  jz      locret_180012032
0x180011e81  mov     [rsp+arg_0], rbx
0x180011e86  push    rdi
0x180011e87  sub     rsp, 20h
0x180011e8b  xor     edi, edi
0x180011e8d  mov     rbx, rcx
0x180011e90  test    byte ptr [rcx+4], 1
0x180011e94  jz      short loc_180011EA4
0x180011e96  mov     rcx, [rcx+8]; pv
0x180011e9a  call    cs:__imp_CoTaskMemFree
0x180011ea0  mov     [rbx+8], rdi
0x180011ea4  test    byte ptr [rbx+4], 2
0x180011ea8  jz      short loc_180011EB8
0x180011eaa  mov     rcx, [rbx+10h]; pv
0x180011eae  call    cs:__imp_CoTaskMemFree
0x180011eb4  mov     [rbx+10h], rdi
0x180011eb8  test    byte ptr [rbx+4], 4
0x180011ebc  jz      short loc_180011ECC
0x180011ebe  mov     rcx, [rbx+18h]; pv
0x180011ec2  call    cs:__imp_CoTaskMemFree
0x180011ec8  mov     [rbx+18h], rdi
0x180011ecc  test    byte ptr [rbx+4], 8
0x180011ed0  jz      short loc_180011EE0
0x180011ed2  mov     rcx, [rbx+20h]; pv
0x180011ed6  call    cs:__imp_CoTaskMemFree
0x180011edc  mov     [rbx+20h], rdi
0x180011ee0  test    byte ptr [rbx+4], 10h
0x180011ee4  jz      short loc_180011EF4
0x180011ee6  mov     rcx, [rbx+28h]; pv
0x180011eea  call    cs:__imp_CoTaskMemFree
0x180011ef0  mov     [rbx+28h], rdi
0x180011ef4  test    byte ptr [rbx+4], 20h
0x180011ef8  jz      short loc_180011F08
0x180011efa  mov     rcx, [rbx+30h]; pv
0x180011efe  call    cs:__imp_CoTaskMemFree
0x180011f04  mov     [rbx+30h], rdi
0x180011f08  test    byte ptr [rbx+4], 40h
0x180011f0c  jz      short loc_180011F1C
0x180011f0e  mov     rcx, [rbx+38h]; pv
0x180011f12  call    cs:__imp_CoTaskMemFree
0x180011f18  mov     [rbx+38h], rdi
0x180011f1c  test    byte ptr [rbx+4], 80h
0x180011f20  jz      short loc_180011F30
0x180011f22  mov     rcx, [rbx+40h]; pv
0x180011f26  call    cs:__imp_CoTaskMemFree
0x180011f2c  mov     [rbx+40h], rdi
0x180011f30  test    dword ptr [rbx+4], 100h
0x180011f37  jz      short loc_180011F47
0x180011f39  mov     rcx, [rbx+48h]; pv
0x180011f3d  call    cs:__imp_CoTaskMemFree
0x180011f43  mov     [rbx+48h], rdi
0x180011f47  test    dword ptr [rbx+4], 200h
0x180011f4e  jz      short loc_180011F5E
0x180011f50  mov     rcx, [rbx+50h]; pv
0x180011f54  call    cs:__imp_CoTaskMemFree
0x180011f5a  mov     [rbx+50h], rdi
0x180011f5e  test    dword ptr [rbx+4], 400h
0x180011f65  jz      short loc_180011F75
0x180011f67  mov     rcx, [rbx+58h]; pv
0x180011f6b  call    cs:__imp_CoTaskMemFree
0x180011f71  mov     [rbx+58h], rdi
0x180011f75  test    dword ptr [rbx+4], 800h
0x180011f7c  jz      short loc_180011F8C
0x180011f7e  mov     rcx, [rbx+60h]; pv
0x180011f82  call    cs:__imp_CoTaskMemFree
0x180011f88  mov     [rbx+60h], rdi
0x180011f8c  test    dword ptr [rbx+4], 1000h
0x180011f93  jz      short loc_180011FA3
0x180011f95  mov     rcx, [rbx+68h]; pv
0x180011f99  call    cs:__imp_CoTaskMemFree
0x180011f9f  mov     [rbx+68h], rdi
0x180011fa3  test    dword ptr [rbx+4], 4000h
0x180011faa  jz      short loc_180011FBA
0x180011fac  mov     rcx, [rbx+70h]; pv
0x180011fb0  call    cs:__imp_CoTaskMemFree
0x180011fb6  mov     [rbx+70h], rdi
0x180011fba  test    dword ptr [rbx+4], 8000h
0x180011fc1  jz      short loc_180011FD1
0x180011fc3  mov     rcx, [rbx+78h]; pv
0x180011fc7  call    cs:__imp_CoTaskMemFree
0x180011fcd  mov     [rbx+78h], rdi
0x180011fd1  test    dword ptr [rbx+4], 20000h
0x180011fd8  jz      short loc_180011FEE
0x180011fda  mov     rcx, [rbx+80h]; pv
0x180011fe1  call    cs:__imp_CoTaskMemFree
0x180011fe7  mov     [rbx+80h], rdi
0x180011fee  test    dword ptr [rbx+4], 40000h
0x180011ff5  jz      short loc_18001200B
0x180011ff7  mov     rcx, [rbx+88h]; pv
0x180011ffe  call    cs:__imp_CoTaskMemFree
0x180012004  mov     [rbx+88h], rdi
0x18001200b  test    dword ptr [rbx+4], 80000h
0x180012012  jz      short loc_180012028
0x180012014  mov     rcx, [rbx+90h]; pv
0x18001201b  call    cs:__imp_CoTaskMemFree
0x180012021  mov     [rbx+90h], rdi
0x180012028  mov     rbx, [rsp+28h+arg_0]
0x18001202d  add     rsp, 20h
0x180012031  pop     rdi
0x180012032  retn
```
