# AppxAllUserStore::EnlistPackageOnUserStore(AppxAllUserStore::SetupPhase,ushort const *,Common::RegistryKey *,Common::RegistryKey *,bool,bool,bool,ushort const *,ushort const *,Common::Array<AppxAllUserStore::_MainPackageInfo,Common::ContainerOperations<AppxAllUserStore::_MainPackageInfo,AppxAllUserStore::_MainPackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_MainPackageInfo>,Common::ArrayOperations<AppxAllUserStore::_MainPackageInfo,Common::NoKey>> *)

- ea: `0x18000bba0`
- end: `0x18000bf0a`
- name: `?EnlistPackageOnUserStore@AppxAllUserStore@@YAJW4SetupPhase@1@PEBGPEAVRegistryKey@Common@@2_N3311PEAV?$Array@U_MainPackageInfo@AppxAllUserStore@@V?$ContainerOperations@U_MainPackageInfo@AppxAllUserStore@@U12@@Common@@VNoKey@4@V?$ContainerOperations@VNoKey@Common@@U_MainPackageInfo@AppxAllUserStore@@@4@V?$ArrayOperations@U_MainPackageInfo@AppxAllUserStore@@VNoKey@Common@@@4@@4@@Z`
- size: `874`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800379c8`
- `0x1800399a0`

## callees

- `0x180004968`
- `0x18000bba0`
- `0x18000bf10`
- `0x18000c594`
- `0x180017f50`
- `0x180018248`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bdc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bdce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bde8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bdc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bdce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bde8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be65`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bd60`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000be97`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bd60`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000be97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bbf7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bc5f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bbf7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bc5f`

## string_xrefs

- `0x18000bece`: `onecore\base\appmodel\common\registrykey.cpp`
- `0x18000be7a`: `NumberOfAttempts`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::EnlistPackageOnUserStore(
        int a1,
        WCHAR *a2,
        HKEY *a3,
        HKEY *a4,
        char a5,
        char a6,
        char a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10)
{
  char v10; // r12
  REGSAM v15; // r15d
  REGSAM v16; // r9d
  LSTATUS v17; // eax
  unsigned int v18; // ebx
  HKEY v19; // rcx
  LSTATUS v20; // eax
  bool *v21; // r9
  unsigned int v22; // ebx
  int v23; // eax
  int v24; // eax
  LSTATUS Value; // eax
  bool v27; // sf
  char v28; // bl
  LSTATUS v29; // eax
  bool v30; // sf
  int phkResult; // [rsp+20h] [rbp-58h]
  int phkResulta; // [rsp+20h] [rbp-58h]
  int phkResultb; // [rsp+20h] [rbp-58h]
  int phkResultc; // [rsp+20h] [rbp-58h]
  BYTE v35[8]; // [rsp+50h] [rbp-28h] BYREF
  HKEY lpcbData; // [rsp+58h] [rbp-20h] BYREF
  HKEY hKey[3]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  int Data; // [rsp+D8h] [rbp+60h] BYREF

  v10 = a7;
  hKey[0] = 0;
  v15 = 131097;
  if ( !a4 )
    goto LABEL_9;
  v16 = 131097;
  if ( !a7 )
    v16 = 983071;
  v17 = RegOpenKeyExW(*a4, a2, 0, v16, hKey);
  v18 = v17;
  if ( v17 > 0 )
    v18 = (unsigned __int16)v17 | 0x80070000;
  if ( (int)v18 <= -2147024895 || v18 + 2147024892 <= 0x7FF8FFFB )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
      (const char *)v18,
      phkResult);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6EB,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)v18,
      phkResultc);
    Common::RegistryKey::~RegistryKey(hKey);
    return v18;
  }
  if ( (unsigned __int64)hKey[0] - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_9;
  LODWORD(lpcbData) = 4;
  Data = 0;
  *(_DWORD *)v35 = 0;
  Value = RegQueryValueExW(hKey[0], L"LastReturnValue", 0, 0, (LPBYTE)&Data, (LPDWORD)&lpcbData);
  v27 = Value < 0;
  if ( Value > 0 )
    v27 = 1;
  if ( v27 )
    goto LABEL_33;
  if ( Data )
  {
    LODWORD(lpcbData) = 4;
    v29 = RegQueryValueExW(hKey[0], L"NumberOfAttempts", 0, 0, v35, (LPDWORD)&lpcbData);
    v30 = v29 < 0;
    if ( v29 > 0 )
      v30 = 1;
    if ( v30 || Data && *(_DWORD *)v35 < 0xAu )
      goto LABEL_33;
  }
  v28 = 0;
  if ( a5 )
LABEL_33:
    v28 = 1;
  if ( (unsigned __int64)hKey[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey[0]);
  hKey[0] = 0;
  if ( v28 )
  {
LABEL_9:
    v19 = *a3;
    lpcbData = 0;
    if ( !v10 )
      v15 = 983071;
    v20 = RegOpenKeyExW(v19, a2, 0, v15, &lpcbData);
    v22 = v20;
    if ( v20 > 0 )
      v22 = (unsigned __int16)v20 | 0x80070000;
    if ( (v22 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71E,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)v22,
        phkResulta);
      if ( (unsigned __int64)lpcbData - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(lpcbData);
      if ( (unsigned __int64)hKey[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(hKey[0]);
    }
    else
    {
      LOBYTE(Data) = 1;
      v23 = AppxAllUserStore::CheckKeyForEnablement(
              &lpcbData,
              (struct Common::RegistryKey *)a2,
              (unsigned __int16 *)&Data,
              v21);
      if ( v23 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x721,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
          (const char *)(unsigned int)v23);
      if ( !(_BYTE)Data
        || (v24 = AppxAllUserStore::AddPackageToDynamicPackageArray(
                    a1,
                    (Common::Deployment *)a2,
                    (struct Common::StringBuffer *)&lpcbData,
                    0,
                    a6,
                    0,
                    a8,
                    a9,
                    a10),
            v22 = v24,
            v24 >= 0) )
      {
        if ( (unsigned __int64)lpcbData - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          RegCloseKey(lpcbData);
        goto LABEL_30;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x72E,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)(unsigned int)v24,
        phkResultb);
      if ( (unsigned __int64)lpcbData - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(lpcbData);
      if ( (unsigned __int64)hKey[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        RegCloseKey(hKey[0]);
        return v22;
      }
    }
    return v22;
  }
LABEL_30:
  if ( (unsigned __int64)hKey[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey[0]);
  return 0;
}

```

## disassembly

```asm
0x18000bba0  push    rbp
0x18000bba2  push    rbx
0x18000bba3  push    rsi
0x18000bba4  push    rdi
0x18000bba5  push    r12
0x18000bba7  push    r13
0x18000bba9  push    r14
0x18000bbab  push    r15
0x18000bbad  mov     rbp, rsp
0x18000bbb0  sub     rsp, 78h
0x18000bbb4  movzx   r12d, [rbp+arg_30]
0x18000bbb9  mov     rax, r9
0x18000bbbc  mov     [rbp+hKey], 0
0x18000bbc4  mov     rsi, r8
0x18000bbc7  mov     rdi, rdx
0x18000bbca  mov     r14d, ecx
0x18000bbcd  mov     r15d, 20019h
0x18000bbd3  mov     r13d, 0F001Fh
0x18000bbd9  test    r9, r9
0x18000bbdc  jz      short loc_18000BC3B
0x18000bbde  mov     r9d, r15d
0x18000bbe1  lea     rcx, [rbp+hKey]
0x18000bbe5  mov     [rsp+78h+phkResult], rcx; int
0x18000bbea  test    r12b, r12b
0x18000bbed  mov     rcx, [rax]; hKey
0x18000bbf0  cmovz   r9d, r13d; samDesired
0x18000bbf4  xor     r8d, r8d; ulOptions
0x18000bbf7  call    cs:__imp_RegOpenKeyExW
0x18000bbfd  mov     ebx, eax
0x18000bbff  test    eax, eax
0x18000bc01  jle     short loc_18000BC0C
0x18000bc03  movzx   ebx, ax
0x18000bc06  or      ebx, 80070000h
0x18000bc0c  cmp     ebx, 80070001h
0x18000bc12  jle     loc_18000BECA
0x18000bc18  lea     eax, [rbx+7FF8FFFCh]
0x18000bc1e  cmp     eax, 7FF8FFFBh
0x18000bc23  jbe     loc_18000BECA
0x18000bc29  mov     rcx, [rbp+hKey]; hKey
0x18000bc2d  lea     rax, [rcx-1]
0x18000bc31  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000bc35  jbe     loc_18000BD32
0x18000bc3b  mov     rcx, [rsi]; hKey
0x18000bc3e  lea     rax, [rbp+var_20]
0x18000bc42  test    r12b, r12b
0x18000bc45  mov     [rbp+var_20], 0
0x18000bc4d  mov     rdx, rdi; lpSubKey
0x18000bc50  mov     [rsp+78h+phkResult], rax; int
0x18000bc55  cmovz   r15d, r13d
0x18000bc59  xor     r8d, r8d; ulOptions
0x18000bc5c  mov     r9d, r15d; samDesired
0x18000bc5f  call    cs:__imp_RegOpenKeyExW
0x18000bc65  mov     ebx, eax
0x18000bc67  test    eax, eax
0x18000bc69  jle     short loc_18000BC74
0x18000bc6b  movzx   ebx, ax
0x18000bc6e  or      ebx, 80070000h
0x18000bc74  test    ebx, ebx
0x18000bc76  js      loc_18000BE22
0x18000bc7c  lea     r8, [rbp+Data]; unsigned __int16 *
0x18000bc80  mov     byte ptr [rbp+Data], 1
0x18000bc84  mov     rdx, rdi; struct Common::RegistryKey *
0x18000bc87  lea     rcx, [rbp+var_20]; this
0x18000bc8b  call    ?CheckKeyForEnablement@AppxAllUserStore@@YAJPEAVRegistryKey@Common@@PEBGAEA_N@Z; AppxAllUserStore::CheckKeyForEnablement(Common::RegistryKey *,ushort const *,bool &)
0x18000bc90  test    eax, eax
0x18000bc92  js      loc_18000BDF0
0x18000bc98  cmp     byte ptr [rbp+Data], 0
0x18000bc9c  jz      loc_18000BDDA
0x18000bca2  mov     rax, [rbp+arg_48]
0x18000bca9  lea     r8, [rbp+var_20]
0x18000bcad  mov     [rsp+78h+var_38], rax
0x18000bcb2  xor     r9d, r9d
0x18000bcb5  mov     rax, [rbp+arg_40]
0x18000bcbc  mov     rdx, rdi
0x18000bcbf  mov     [rsp+78h+var_40], rax
0x18000bcc4  mov     ecx, r14d
0x18000bcc7  mov     rax, [rbp+arg_38]
0x18000bcce  mov     [rsp+78h+var_48], rax
0x18000bcd3  movzx   eax, [rbp+arg_28]
0x18000bcd7  mov     byte ptr [rsp+78h+lpcbData], 0
0x18000bcdc  mov     byte ptr [rsp+78h+phkResult], al; int
0x18000bce0  call    ?AddPackageToDynamicPackageArray@AppxAllUserStore@@YAJW4SetupPhase@1@PEBGPEAVRegistryKey@Common@@_N3311PEAV?$Array@U_MainPackageInfo@AppxAllUserStore@@V?$ContainerOperations@U_MainPackageInfo@AppxAllUserStore@@U12@@Common@@VNoKey@4@V?$ContainerOperations@VNoKey@Common@@U_MainPackageInfo@AppxAllUserStore@@@4@V?$ArrayOperations@U_MainPackageInfo@AppxAllUserStore@@VNoKey@Common@@@4@@4@@Z; AppxAllUserStore::AddPackageToDynamicPackageArray(AppxAllUserStore::SetupPhase,ushort const *,Common::RegistryKey *,bool,bool,bool,ushort const *,ushort const *,Common::Array<AppxAllUserStore::_MainPackageInfo,Common::ContainerOperations<AppxAllUserStore::_MainPackageInfo,AppxAllUserStore::_MainPackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_MainPackageInfo>,Common::ArrayOperations<AppxAllUserStore::_MainPackageInfo,Common::NoKey>> *)
0x18000bce5  mov     ebx, eax
0x18000bce7  test    eax, eax
0x18000bce9  jns     loc_18000BDDA
0x18000bcef  mov     rcx, [rbp+40h]; this
0x18000bcf3  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000bcfa  mov     r9d, eax; char *
0x18000bcfd  mov     edx, 72Eh; void *
0x18000bd02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd07  mov     rcx, [rbp+var_20]; hKey
0x18000bd0b  lea     rdx, [rcx-1]
0x18000bd0f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000bd13  jbe     loc_18000BE0D
0x18000bd19  mov     rcx, [rbp+hKey]; hKey
0x18000bd1d  lea     rax, [rcx-1]
0x18000bd21  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000bd25  jbe     loc_18000BE18
0x18000bd2b  mov     eax, ebx
0x18000bd2d  jmp     loc_18000BDB5
0x18000bd32  xor     eax, eax
0x18000bd34  mov     dword ptr [rbp+var_20], 4
0x18000bd3b  mov     [rbp+Data], eax
0x18000bd3e  lea     rdx, ValueName; "LastReturnValue"
0x18000bd45  mov     dword ptr [rbp+var_28], eax
0x18000bd48  xor     r9d, r9d; lpType
0x18000bd4b  lea     rax, [rbp+var_20]
0x18000bd4f  xor     r8d, r8d; lpReserved
0x18000bd52  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18000bd57  lea     rax, [rbp+Data]
0x18000bd5b  mov     [rsp+78h+phkResult], rax; lpData
0x18000bd60  call    cs:__imp_RegQueryValueExW
0x18000bd66  test    eax, eax
0x18000bd68  jle     short loc_18000BD74
0x18000bd6a  movzx   eax, ax
0x18000bd6d  or      eax, 80070000h
0x18000bd72  test    eax, eax
0x18000bd74  js      short loc_18000BDD6
0x18000bd76  cmp     [rbp+Data], 0
0x18000bd7a  jnz     loc_18000BE6D
0x18000bd80  xor     bl, bl
0x18000bd82  cmp     [rbp+arg_20], bl
0x18000bd85  jnz     short loc_18000BDD6
0x18000bd87  mov     rcx, [rbp+hKey]; hKey
0x18000bd8b  lea     rax, [rcx-1]
0x18000bd8f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000bd93  jbe     short loc_18000BDC6
0x18000bd95  mov     [rbp+hKey], 0
0x18000bd9d  test    bl, bl
0x18000bd9f  jnz     loc_18000BC3B
0x18000bda5  mov     rcx, [rbp+hKey]; hKey
0x18000bda9  lea     rax, [rcx-1]
0x18000bdad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000bdb1  jbe     short loc_18000BDCE
0x18000bdb3  xor     eax, eax
0x18000bdb5  add     rsp, 78h
0x18000bdb9  pop     r15
0x18000bdbb  pop     r14
0x18000bdbd  pop     r13
0x18000bdbf  pop     r12
0x18000bdc1  pop     rdi
0x18000bdc2  pop     rsi
0x18000bdc3  pop     rbx
0x18000bdc4  pop     rbp
0x18000bdc5  retn
0x18000bdc6  call    cs:__imp_RegCloseKey
0x18000bdcc  jmp     short loc_18000BD95
0x18000bdce  call    cs:__imp_RegCloseKey
0x18000bdd4  jmp     short loc_18000BDB3
0x18000bdd6  mov     bl, 1
0x18000bdd8  jmp     short loc_18000BD87
0x18000bdda  mov     rcx, [rbp+var_20]; hKey
0x18000bdde  lea     rax, [rcx-1]
0x18000bde2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000bde6  ja      short loc_18000BDA5
0x18000bde8  call    cs:__imp_RegCloseKey
0x18000bdee  jmp     short loc_18000BDA5
0x18000bdf0  mov     rcx, [rbp+40h]; this
0x18000bdf4  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000bdfb  mov     r9d, eax; char *
0x18000bdfe  mov     edx, 721h; void *
0x18000be03  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000be08  jmp     loc_18000BC98
0x18000be0d  call    cs:__imp_RegCloseKey
0x18000be13  jmp     loc_18000BD19
0x18000be18  call    cs:__imp_RegCloseKey
0x18000be1e  mov     eax, ebx
0x18000be20  jmp     short loc_18000BDB5
0x18000be22  mov     rcx, [rbp+40h]; this
0x18000be26  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000be2d  mov     r9d, ebx; char *
0x18000be30  mov     edx, 71Eh; void *
0x18000be35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be3a  mov     rcx, [rbp+var_20]; hKey
0x18000be3e  lea     rax, [rcx-1]
0x18000be42  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000be46  jbe     short loc_18000BE65
0x18000be48  mov     rcx, [rbp+hKey]; hKey
0x18000be4c  lea     rdx, [rcx-1]
0x18000be50  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000be54  ja      loc_18000BD2B
0x18000be5a  call    cs:__imp_RegCloseKey
0x18000be60  jmp     loc_18000BD2B
0x18000be65  call    cs:__imp_RegCloseKey
0x18000be6b  jmp     short loc_18000BE48
0x18000be6d  mov     rcx, [rbp+hKey]; hKey
0x18000be71  lea     rax, [rbp+var_20]
0x18000be75  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18000be7a  lea     rdx, aNumberofattemp; "NumberOfAttempts"
0x18000be81  lea     rax, [rbp+var_28]
0x18000be85  mov     dword ptr [rbp+var_20], 4
0x18000be8c  xor     r9d, r9d; lpType
0x18000be8f  mov     [rsp+78h+phkResult], rax; lpData
0x18000be94  xor     r8d, r8d; lpReserved
0x18000be97  call    cs:__imp_RegQueryValueExW
0x18000be9d  test    eax, eax
0x18000be9f  jle     short loc_18000BEAB
0x18000bea1  movzx   eax, ax
0x18000bea4  or      eax, 80070000h
0x18000bea9  test    eax, eax
0x18000beab  js      loc_18000BDD6
0x18000beb1  cmp     [rbp+Data], 0
0x18000beb5  jz      loc_18000BD80
0x18000bebb  cmp     dword ptr [rbp+var_28], 0Ah
0x18000bebf  jb      loc_18000BDD6
0x18000bec5  jmp     loc_18000BD80
0x18000beca  mov     rcx, [rbp+40h]; this
0x18000bece  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\common\\regist"...
0x18000bed5  mov     r9d, ebx; char *
0x18000bed8  mov     edx, 0ADh; void *
0x18000bedd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bee2  mov     rcx, [rbp+40h]; this
0x18000bee6  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000beed  mov     r9d, ebx; char *
0x18000bef0  mov     edx, 6EBh; void *
0x18000bef5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000befa  lea     rcx, [rbp+hKey]; this
0x18000befe  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18000bf03  mov     eax, ebx
0x18000bf05  jmp     loc_18000BDB5
```
