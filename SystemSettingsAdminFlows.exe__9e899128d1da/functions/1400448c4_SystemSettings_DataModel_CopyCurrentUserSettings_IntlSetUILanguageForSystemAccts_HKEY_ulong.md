# SystemSettings::DataModel::CopyCurrentUserSettings::IntlSetUILanguageForSystemAccts(HKEY__ *,ulong *)

- ea: `0x1400448c4`
- end: `0x140044ac1`
- name: `?IntlSetUILanguageForSystemAccts@CopyCurrentUserSettings@DataModel@SystemSettings@@CAXPEAUHKEY__@@PEAK@Z`
- size: `509`
- prototype: `void __fastcall(HKEY hKey, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400437e4`

## callees

- `0x140004e68`
- `0x140005f30`
- `0x14000614e`
- `0x14002996c`
- `0x140043d64`
- `0x140043ea4`
- `0x1400448c4`
- `0x140044ac8`

## import_xrefs

- `KERNEL32!SetThreadPreferredUILanguages` at `0x140044a95`
- `KERNEL32!SetThreadPreferredUILanguages` at `0x140044a95`
- `KERNEL32!NotifyUILanguageChange` at `0x140044a54`
- `KERNEL32!NotifyUILanguageChange` at `0x140044a54`
- `KERNEL32!GetSystemPreferredUILanguages` at `0x140044932`
- `KERNEL32!GetSystemPreferredUILanguages` at `0x140044932`
- `KERNEL32!CompareStringOrdinal` at `0x140044a76`
- `KERNEL32!CompareStringOrdinal` at `0x140044a76`

## string_xrefs

- `0x140044976`: `pcshell\shell\systemsettings\adminflows\languagemanager\lib\copycurrentusersettings.cpp`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CopyCurrentUserSettings::IntlSetUILanguageForSystemAccts(
        HKEY hKey,
        unsigned int *a2)
{
  const WCHAR *v4; // rsi
  int v5; // r8d
  int v6; // r8d
  __int64 v7; // rdx
  int v8; // r9d
  __int64 v9; // rdx
  unsigned __int16 *v10; // rax
  __int64 v11; // rax
  int v12; // r8d
  int pdwStatusRtrn; // [rsp+20h] [rbp-E0h]
  DWORD v14; // [rsp+30h] [rbp-D0h] BYREF
  ULONG pcchLanguagesBuffer; // [rsp+34h] [rbp-CCh] BYREF
  ULONG pulNumLanguages; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pcwstrNewLanguage[352]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 Src[352]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR pwszLanguagesBuffer[352]; // [rsp+5C0h] [rbp+4C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8B8h] [rbp+7B8h]

  memset_0(pwszLanguagesBuffer, 0, 0x2BCu);
  pcchLanguagesBuffer = 350;
  pulNumLanguages = 1;
  v4 = (const WCHAR *)((unsigned __int64)pwszLanguagesBuffer
                     & -(__int64)GetSystemPreferredUILanguages(
                                   0x408u,
                                   &pulNumLanguages,
                                   pwszLanguagesBuffer,
                                   &pcchLanguagesBuffer));
  memset_0(pcwstrNewLanguage, 0, 0x2BCu);
  if ( !(unsigned int)SystemSettings::DataModel::CopyCurrentUserSettings::IntlGetUserUILanguage(
                        hKey,
                        pcwstrNewLanguage,
                        v5) )
  {
    v7 = 159;
LABEL_3:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\copycurrentusersettings.cpp",
      (const char *)0x80004005LL,
      pdwStatusRtrn);
    return;
  }
  if ( (int)SystemSettings::DataModel::CopyCurrentUserSettings::IntlSetUserPreferredMUILanguage(
              pcwstrNewLanguage,
              1,
              v6) < 0 )
  {
    v7 = 165;
    goto LABEL_3;
  }
  memset_0(Src, 0, 0x2BCu);
  v9 = 700;
  v10 = Src;
  do
  {
    *(_BYTE *)v10 = 0;
    v10 = (unsigned __int16 *)((char *)v10 + 1);
    --v9;
  }
  while ( v9 );
  if ( SystemSettings::DataModel::CopyCurrentUserSettings::IntlGetUserUILangConfig(hKey, pcwstrNewLanguage, Src, v8) )
  {
    v11 = -1;
    do
      ++v11;
    while ( pcwstrNewLanguage[v11] );
    memcpy_0(&pcwstrNewLanguage[(unsigned int)(v11 + 1)], Src, 700 - 2LL * (unsigned int)(v11 + 1));
    if ( (int)SystemSettings::DataModel::CopyCurrentUserSettings::IntlSetUserPreferredMUILanguage(
                pcwstrNewLanguage,
                0,
                v12) < 0 )
    {
      v7 = 183;
      goto LABEL_3;
    }
  }
  v14 = 0;
  if ( NotifyUILanguageChange(1u, pcwstrNewLanguage, v4, 0, &v14)
    && a2
    && CompareStringOrdinal(pcwstrNewLanguage, -1, v4, -1, 0) != 2 )
  {
    *a2 = v14;
  }
  SetThreadPreferredUILanguages(8u, &Data, 0);
}

```

## disassembly

```asm
0x1400448c4  mov     [rsp-8+arg_10], rbx
0x1400448c9  push    rbp
0x1400448ca  push    rsi
0x1400448cb  push    rdi
0x1400448cc  push    r14
0x1400448ce  push    r15
0x1400448d0  lea     rbp, [rsp-790h]
0x1400448d8  sub     rsp, 890h
0x1400448df  mov     rax, cs:__security_cookie
0x1400448e6  xor     rax, rsp
0x1400448e9  mov     [rbp+7B0h+var_30], rax
0x1400448f0  mov     rdi, rdx
0x1400448f3  mov     r14, rcx
0x1400448f6  mov     ebx, 2BCh
0x1400448fb  lea     rcx, [rbp+7B0h+pwszLanguagesBuffer]; void *
0x140044902  mov     r8d, ebx; Size
0x140044905  xor     edx, edx; Val
0x140044907  call    memset_0
0x14004490c  lea     r9, [rsp+8B0h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x140044911  mov     [rsp+8B0h+pcchLanguagesBuffer], 15Eh
0x140044919  lea     r8, [rbp+7B0h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x140044920  mov     [rsp+8B0h+pulNumLanguages], 1
0x140044928  lea     rdx, [rsp+8B0h+pulNumLanguages]; pulNumLanguages
0x14004492d  mov     ecx, 408h; dwFlags
0x140044932  call    cs:__imp_GetSystemPreferredUILanguages
0x140044938  mov     r8d, ebx; Size
0x14004493b  lea     rcx, [rsp+8B0h+pcwstrNewLanguage]; void *
0x140044940  neg     eax
0x140044942  lea     rax, [rbp+7B0h+pwszLanguagesBuffer]
0x140044949  sbb     rsi, rsi
0x14004494c  xor     edx, edx; Val
0x14004494e  and     rsi, rax
0x140044951  call    memset_0
0x140044956  lea     rdx, [rsp+8B0h+pcwstrNewLanguage]; unsigned __int16 *
0x14004495b  mov     rcx, r14; hKey
0x14004495e  call    ?IntlGetUserUILanguage@CopyCurrentUserSettings@DataModel@SystemSettings@@CAHPEAUHKEY__@@PEAGH@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlGetUserUILanguage(HKEY__ *,ushort *,int)
0x140044963  xor     r15d, r15d
0x140044966  test    eax, eax
0x140044968  jnz     short loc_14004498D
0x14004496a  mov     edx, 9Fh; void *
0x14004496f  mov     rcx, [rbp+7B8h]; this
0x140044976  lea     r8, aPcshellShellSy_33; "pcshell\\shell\\systemsettings\\adminfl"...
0x14004497d  mov     r9d, 80004005h; char *
0x140044983  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140044988  jmp     loc_140044A9B
0x14004498d  mov     edx, 1; int
0x140044992  lea     rcx, [rsp+8B0h+pcwstrNewLanguage]; unsigned __int16 *
0x140044997  call    ?IntlSetUserPreferredMUILanguage@CopyCurrentUserSettings@DataModel@SystemSettings@@CAJPEAGHH@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlSetUserPreferredMUILanguage(ushort *,int,int)
0x14004499c  test    eax, eax
0x14004499e  jns     short loc_1400449A7
0x1400449a0  mov     edx, 0A5h
0x1400449a5  jmp     short loc_14004496F
0x1400449a7  mov     r8, rbx; Size
0x1400449aa  lea     rcx, [rbp+7B0h+Src]; void *
0x1400449b1  xor     edx, edx; Val
0x1400449b3  call    memset_0
0x1400449b8  mov     rdx, rbx
0x1400449bb  lea     rax, [rbp+7B0h+Src]
0x1400449c2  mov     [rax], r15b
0x1400449c5  inc     rax
0x1400449c8  sub     rdx, 1
0x1400449cc  jnz     short loc_1400449C2
0x1400449ce  lea     r8, [rbp+7B0h+Src]; Destination
0x1400449d5  mov     rcx, r14; hKey
0x1400449d8  lea     rdx, [rsp+8B0h+pcwstrNewLanguage]; lpValueName
0x1400449dd  call    ?IntlGetUserUILangConfig@CopyCurrentUserSettings@DataModel@SystemSettings@@CAKPEAUHKEY__@@PEAG1H@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlGetUserUILangConfig(HKEY__ *,ushort *,ushort *,int)
0x1400449e2  or      r14, 0FFFFFFFFFFFFFFFFh
0x1400449e6  test    eax, eax
0x1400449e8  jz      short loc_140044A36
0x1400449ea  lea     rcx, [rsp+8B0h+pcwstrNewLanguage]
0x1400449ef  mov     rax, r14
0x1400449f2  inc     rax
0x1400449f5  cmp     [rcx+rax*2], r15w
0x1400449fa  jnz     short loc_1400449F2
0x1400449fc  lea     ecx, [rax+1]
0x1400449ff  add     rcx, rcx
0x140044a02  lea     rax, [rsp+8B0h+pcwstrNewLanguage]
0x140044a07  sub     rbx, rcx
0x140044a0a  lea     rdx, [rbp+7B0h+Src]; Src
0x140044a11  mov     r8, rbx; Size
0x140044a14  add     rcx, rax; void *
0x140044a17  call    memcpy_0
0x140044a1c  xor     edx, edx; int
0x140044a1e  lea     rcx, [rsp+8B0h+pcwstrNewLanguage]; unsigned __int16 *
0x140044a23  call    ?IntlSetUserPreferredMUILanguage@CopyCurrentUserSettings@DataModel@SystemSettings@@CAJPEAGHH@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlSetUserPreferredMUILanguage(ushort *,int,int)
0x140044a28  test    eax, eax
0x140044a2a  jns     short loc_140044A36
0x140044a2c  mov     edx, 0B7h
0x140044a31  jmp     loc_14004496F
0x140044a36  xor     r9d, r9d; dwReserved
0x140044a39  mov     [rsp+8B0h+var_880], r15d
0x140044a3e  lea     rax, [rsp+8B0h+var_880]
0x140044a43  mov     r8, rsi; pcwstrPreviousLanguage
0x140044a46  lea     rdx, [rsp+8B0h+pcwstrNewLanguage]; pcwstrNewLanguage
0x140044a4b  mov     qword ptr [rsp+8B0h+pdwStatusRtrn], rax; pdwStatusRtrn
0x140044a50  lea     ecx, [r9+1]; dwFlags
0x140044a54  call    cs:__imp_NotifyUILanguageChange
0x140044a5a  test    eax, eax
0x140044a5c  jz      short loc_140044A87
0x140044a5e  test    rdi, rdi
0x140044a61  jz      short loc_140044A87
0x140044a63  mov     r9d, r14d; cchCount2
0x140044a66  mov     [rsp+8B0h+pdwStatusRtrn], r15d; bIgnoreCase
0x140044a6b  mov     r8, rsi; lpString2
0x140044a6e  lea     rcx, [rsp+8B0h+pcwstrNewLanguage]; lpString1
0x140044a73  mov     edx, r14d; cchCount1
0x140044a76  call    cs:__imp_CompareStringOrdinal
0x140044a7c  cmp     eax, 2
0x140044a7f  jz      short loc_140044A87
0x140044a81  mov     eax, [rsp+8B0h+var_880]
0x140044a85  mov     [rdi], eax
0x140044a87  xor     r8d, r8d; pulNumLanguages
0x140044a8a  lea     rdx, Data; pwszLanguagesBuffer
0x140044a91  lea     ecx, [r8+8]; dwFlags
0x140044a95  call    cs:__imp_SetThreadPreferredUILanguages
0x140044a9b  mov     rcx, [rbp+7B0h+var_30]
0x140044aa2  xor     rcx, rsp; StackCookie
0x140044aa5  call    __security_check_cookie
0x140044aaa  mov     rbx, [rsp+8B0h+arg_10]
0x140044ab2  add     rsp, 890h
0x140044ab9  pop     r15
0x140044abb  pop     r14
0x140044abd  pop     rdi
0x140044abe  pop     rsi
0x140044abf  pop     rbp
0x140044ac0  retn
```
