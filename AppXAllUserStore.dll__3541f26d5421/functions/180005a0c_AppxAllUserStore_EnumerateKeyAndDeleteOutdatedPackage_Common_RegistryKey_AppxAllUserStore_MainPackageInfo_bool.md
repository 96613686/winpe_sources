# AppxAllUserStore::EnumerateKeyAndDeleteOutdatedPackage(Common::RegistryKey *,AppxAllUserStore::_MainPackageInfo *,bool *,bool *)

- ea: `0x180005a0c`
- end: `0x180005ebf`
- name: `?EnumerateKeyAndDeleteOutdatedPackage@AppxAllUserStore@@YAJPEAVRegistryKey@Common@@PEAU_MainPackageInfo@1@PEA_N2@Z`
- size: `1203`
- prototype: `__int64 __fastcall(AppxAllUserStore *__hidden this, struct Common::RegistryKey *, struct AppxAllUserStore::_MainPackageInfo *, bool *, bool *)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004a28`
- `0x180012dcc`
- `0x18002bbf0`

## callees

- `0x180002748`
- `0x180004920`
- `0x180004968`
- `0x180005a0c`
- `0x180006870`
- `0x180007860`
- `0x180007a10`
- `0x180007ebc`
- `0x180008db0`
- `0x18000d7b0`
- `0x180018248`
- `0x18001ee7c`
- `0x18001f28c`
- `0x180026828`
- `0x18002848c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005ad9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005b8b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005ad9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005b8b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180005dfc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180005dfc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005a74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005a74`

## string_xrefs

- `0x180005e61`: `onecore\base\appmodel\common\registrykey.cpp`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::EnumerateKeyAndDeleteOutdatedPackage(
        HKEY *this,
        struct Common::RegistryKey *a2,
        struct AppxAllUserStore::_MainPackageInfo *a3,
        bool *a4)
{
  const WCHAR *v5; // rbx
  LSTATUS v7; // eax
  const unsigned __int16 *v8; // rdx
  struct Common::Deployment::PackageID *v9; // r9
  signed int PackageIDFromPackageMoniker; // ebx
  HKEY v11; // rcx
  char v12; // di
  LSTATUS Value; // eax
  bool *v14; // r9
  bool v15; // sf
  __int64 v16; // rdx
  int refreshed; // eax
  unsigned __int64 v18; // r9
  LSTATUS v19; // eax
  bool v20; // sf
  bool *v21; // rax
  int v22; // eax
  int UInt32ValueIf; // eax
  const unsigned __int16 *v24; // rdx
  int StringValueIfExists; // eax
  __int64 v26; // rdx
  __int64 v27; // rcx
  const unsigned __int16 **v28; // rdx
  unsigned __int16 *v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rax
  __int128 v32; // xmm1
  LSTATUS v33; // eax
  int phkResult; // [rsp+28h] [rbp-E0h]
  int phkResulta; // [rsp+28h] [rbp-E0h]
  bool v37[8]; // [rsp+38h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int Data; // [rsp+48h] [rbp-C0h] BYREF
  DWORD Data_4; // [rsp+4Ch] [rbp-BCh] BYREF
  BYTE Data_8[16]; // [rsp+50h] [rbp-B8h] BYREF
  int v42; // [rsp+60h] [rbp-A8h]
  __int128 v43; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v44; // [rsp+78h] [rbp-90h]
  __int64 v45; // [rsp+88h] [rbp-80h]
  unsigned __int16 v46[8]; // [rsp+98h] [rbp-70h] BYREF
  int v47; // [rsp+A8h] [rbp-60h]
  __int64 v48; // [rsp+B0h] [rbp-58h]
  __int128 v49; // [rsp+B8h] [rbp-50h]
  int v50; // [rsp+C8h] [rbp-40h]
  int v51; // [rsp+D0h] [rbp-38h]
  __int128 v52; // [rsp+D8h] [rbp-30h]
  int v53; // [rsp+E8h] [rbp-20h]
  __int128 v54; // [rsp+F0h] [rbp-18h]
  int v55; // [rsp+100h] [rbp-8h]
  char v56; // [rsp+108h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]
  HKEY *v58; // [rsp+168h] [rbp+60h] BYREF
  struct Common::RegistryKey *v59; // [rsp+170h] [rbp+68h] BYREF
  bool *v60; // [rsp+180h] [rbp+78h] BYREF

  v60 = a4;
  v59 = a2;
  v58 = this;
  v42 = 0;
  *(_OWORD *)Data_8 = 0;
  hKey = 0;
  v5 = *(const WCHAR **)a2;
  Common::AutoHandleCloseHKEY<HKEY__ *>(0);
  hKey = 0;
  v7 = RegOpenKeyExW(*this, v5, 0, 0x20019u, &hKey);
  PackageIDFromPackageMoniker = v7;
  if ( v7 > 0 )
    PackageIDFromPackageMoniker = (unsigned __int16)v7 | 0x80070000;
  if ( PackageIDFromPackageMoniker <= -2147024895
    || (unsigned int)(PackageIDFromPackageMoniker + 2147024892) <= 0x7FF8FFFB )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
      (const char *)(unsigned int)PackageIDFromPackageMoniker,
      phkResult);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x275,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
      (const char *)(unsigned int)PackageIDFromPackageMoniker,
      phkResulta);
    goto LABEL_61;
  }
  v11 = hKey;
  if ( !hKey )
  {
    v47 = 0;
    v50 = 0;
    *(_OWORD *)v46 = 0;
    v53 = 0;
    v49 = 0;
    v55 = 0;
    v52 = 0;
    v48 = 0;
    v54 = 0;
    v51 = 11;
    v29 = *(unsigned __int16 **)v59;
    *(_BYTE *)a3 = 0;
    PackageIDFromPackageMoniker = Common::Deployment::GetPackageIDFromPackageMoniker(
                                    (Common::Deployment *)v29,
                                    v8,
                                    v46,
                                    v9);
    if ( PackageIDFromPackageMoniker >= 0 )
    {
      v31 = lambda_cc27486b722014f047fa87bd52250e61_::_lambda_cc27486b722014f047fa87bd52250e61_(
              (unsigned int)&v56,
              (unsigned int)v46,
              (unsigned int)Data_8,
              (unsigned int)&v58,
              (__int64)&v59,
              (__int64)&v60);
      v32 = *(_OWORD *)(v31 + 16);
      v43 = *(_OWORD *)v31;
      v45 = *(_QWORD *)(v31 + 32);
      v44 = v32;
      PackageIDFromPackageMoniker = AppxAllUserStore::EnumKeyAndDoActionForAllSubkeys__lambda_194360a9069636156e46757edebd65ba___(
                                      v58,
                                      &v43);
      if ( PackageIDFromPackageMoniker >= 0 )
      {
        Common::Deployment::PackageID::~PackageID((Common::Deployment::PackageID *)v46);
        goto LABEL_47;
      }
      v30 = 753;
    }
    else
    {
      v30 = 704;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
      (const char *)(unsigned int)PackageIDFromPackageMoniker,
      phkResult);
    Common::Deployment::PackageID::~PackageID((Common::Deployment::PackageID *)v46);
LABEL_61:
    Common::AutoHandleCloseHKEY<HKEY__ *>(hKey);
    if ( *(_QWORD *)&Data_8[8] )
      Common::GlobalHeap::Free(*(void **)&Data_8[8]);
    return (unsigned int)PackageIDFromPackageMoniker;
  }
  *(_BYTE *)a3 = 1;
  v12 = 0;
  v37[0] = 0;
  Value = RegQueryValueExW(v11, L"RequiresAllUserStoreRefresh", 0, 0, 0, 0);
  PackageIDFromPackageMoniker = Value;
  if ( !Value || Value == 234 )
  {
    v12 = 1;
    v37[0] = 1;
  }
  else
  {
    if ( (unsigned int)(Value - 2) <= 1 )
      goto LABEL_15;
    v15 = Value < 0;
    if ( Value > 0 )
    {
      PackageIDFromPackageMoniker = (unsigned __int16)Value | 0x80070000;
      v15 = 1;
    }
    if ( v15 )
    {
      v16 = 637;
LABEL_54:
      v18 = (unsigned int)PackageIDFromPackageMoniker;
      goto LABEL_55;
    }
  }
  if ( v12 )
    goto LABEL_26;
LABEL_15:
  refreshed = AppxAllUserStore::NeedsRefreshBasedOnDependencies(
                (AppxAllUserStore *)&hKey,
                v59,
                (struct AppxAllUserStore::_MainPackageInfo *)v37,
                v14);
  PackageIDFromPackageMoniker = refreshed;
  if ( refreshed < 0 )
  {
    v18 = (unsigned int)refreshed;
    v16 = 645;
LABEL_55:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
      (const char *)v18,
      phkResult);
    goto LABEL_56;
  }
  if ( v37[0] )
  {
LABEL_26:
    Data_4 = 0;
    v37[0] = 0;
    UInt32ValueIf = Common::RegistryKey::GetUInt32ValueIfExists<unsigned long>(&hKey, L"IsLOBApp", (BYTE *)&Data_4, v37);
    PackageIDFromPackageMoniker = UInt32ValueIf;
    if ( UInt32ValueIf < 0 )
    {
      v18 = (unsigned int)UInt32ValueIf;
      v16 = 652;
      goto LABEL_55;
    }
    LODWORD(v44) = 0;
    v43 = 0;
    *((_DWORD *)v59 + 9) = Data_4;
    StringValueIfExists = Common::RegistryKey::GetStringValueIfExists(
                            (Common::RegistryKey *)&hKey,
                            v24,
                            (struct Common::StringBuffer *)&v43,
                            v37);
    PackageIDFromPackageMoniker = StringValueIfExists;
    if ( StringValueIfExists >= 0 )
    {
      if ( v37[0] )
      {
        v27 = *((_QWORD *)&v43 + 1);
        *((_QWORD *)&v43 + 1) = 0;
        LODWORD(v43) = 0;
        LODWORD(v44) = 0;
        *((_QWORD *)v59 + 2) = v27;
      }
      if ( v60 )
      {
        Data = 0;
        *v60 = Common::RegistryKey::GetUInt32Value((Common::RegistryKey *)&hKey, L"LastReturnValue", &Data) >= 0
            && !Data;
      }
      v28 = (const unsigned __int16 **)v59;
      *(_BYTE *)a3 = 0;
      StringValueIfExists = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)Data_8, *v28);
      PackageIDFromPackageMoniker = StringValueIfExists;
      if ( StringValueIfExists >= 0 )
      {
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v43);
        goto LABEL_47;
      }
      v26 = 679;
    }
    else
    {
      v26 = 657;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
      (const char *)(unsigned int)StringValueIfExists,
      phkResult);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v43);
LABEL_56:
    Common::RegistryKey::~RegistryKey(&hKey);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Data_8);
    return (unsigned int)PackageIDFromPackageMoniker;
  }
  if ( v60 )
  {
    Data = 0;
    Data_4 = 4;
    v19 = RegQueryValueExW(hKey, L"LastReturnValue", 0, 0, (LPBYTE)&Data, &Data_4);
    v20 = v19 < 0;
    if ( v19 > 0 )
      v20 = 1;
    if ( v20 || Data )
    {
      v21 = v60;
      *(_BYTE *)a3 = 0;
      *v21 = 0;
      v22 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)Data_8, *(const unsigned __int16 **)v59);
      PackageIDFromPackageMoniker = v22;
      if ( v22 < 0 )
      {
        v18 = (unsigned int)v22;
        v16 = 690;
        goto LABEL_55;
      }
    }
    else
    {
      *v60 = 1;
    }
  }
LABEL_47:
  if ( !*(_BYTE *)a3 )
  {
    if ( !*(_DWORD *)Data_8 )
    {
      PackageIDFromPackageMoniker = -2147009295;
      goto LABEL_56;
    }
    v33 = RegDeleteTreeW(*v58, *(LPCWSTR *)&Data_8[8]);
    PackageIDFromPackageMoniker = v33;
    if ( v33 > 0 )
      PackageIDFromPackageMoniker = (unsigned __int16)v33 | 0x80070000;
    if ( PackageIDFromPackageMoniker < 0 )
    {
      v16 = 763;
      goto LABEL_54;
    }
  }
  Common::AutoHandleCloseHKEY<HKEY__ *>(hKey);
  if ( *(_QWORD *)&Data_8[8] )
    Common::GlobalHeap::Free(*(void **)&Data_8[8]);
  return 0;
}

```

## disassembly

```asm
0x180005a0c  mov     rax, rsp
0x180005a0f  mov     [rax+18h], rbx
0x180005a13  mov     [rax+20h], r9
0x180005a17  mov     [rax+10h], rdx
0x180005a1b  mov     [rax+8], rcx
0x180005a1f  push    rbp
0x180005a20  push    rsi
0x180005a21  push    rdi
0x180005a22  push    r14
0x180005a24  push    r15
0x180005a26  lea     rbp, [rax-58h]
0x180005a2a  sub     rsp, 130h
0x180005a31  xorps   xmm0, xmm0
0x180005a34  xor     r14d, r14d
0x180005a37  mov     rdi, rcx
0x180005a3a  mov     dword ptr [rsp+150h+var_F8], r14d
0x180005a3f  movups  xmmword ptr [rsp+150h+Data+8], xmm0
0x180005a44  mov     [rsp+150h+hKey], r14
0x180005a49  xor     ecx, ecx
0x180005a4b  mov     rbx, [rdx]
0x180005a4e  mov     rsi, r8
0x180005a51  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180005a56  lea     rax, [rsp+150h+hKey]
0x180005a5b  mov     [rsp+150h+hKey], r14
0x180005a60  mov     rcx, [rdi]; hKey
0x180005a63  mov     r9d, 20019h; samDesired
0x180005a69  xor     r8d, r8d; ulOptions
0x180005a6c  mov     [rsp+150h+phkResult], rax; int
0x180005a71  mov     rdx, rbx; lpSubKey
0x180005a74  call    cs:__imp_RegOpenKeyExW
0x180005a7a  mov     ebx, eax
0x180005a7c  mov     r15d, 80070000h
0x180005a82  test    eax, eax
0x180005a84  jle     short loc_180005A8C
0x180005a86  movzx   ebx, ax
0x180005a89  or      ebx, r15d
0x180005a8c  cmp     ebx, 80070001h
0x180005a92  jle     loc_180005E5D
0x180005a98  lea     eax, [rbx+7FF8FFFCh]
0x180005a9e  cmp     eax, 7FF8FFFBh
0x180005aa3  jbe     loc_180005E5D
0x180005aa9  mov     rcx, [rsp+150h+hKey]; hKey
0x180005aae  test    rcx, rcx
0x180005ab1  jz      loc_180005D07
0x180005ab7  mov     [rsp+150h+lpcbData], r14; lpcbData
0x180005abc  lea     rdx, aRequiresalluse; "RequiresAllUserStoreRefresh"
0x180005ac3  xor     r9d, r9d; lpType
0x180005ac6  mov     [rsp+150h+phkResult], r14; int
0x180005acb  xor     r8d, r8d; lpReserved
0x180005ace  mov     byte ptr [rsi], 1
0x180005ad1  mov     dil, r14b
0x180005ad4  mov     [rsp+150h+var_120], r14b
0x180005ad9  call    cs:__imp_RegQueryValueExW
0x180005adf  mov     ebx, eax
0x180005ae1  test    eax, eax
0x180005ae3  jz      short loc_180005B0C
0x180005ae5  cmp     eax, 0EAh
0x180005aea  jz      short loc_180005B0C
0x180005aec  add     eax, 0FFFFFFFEh
0x180005aef  cmp     eax, 1
0x180005af2  jbe     short loc_180005B1D
0x180005af4  test    ebx, ebx
0x180005af6  jle     short loc_180005B00
0x180005af8  movzx   ebx, bx
0x180005afb  or      ebx, r15d
0x180005afe  test    ebx, ebx
0x180005b00  jns     short loc_180005B14
0x180005b02  mov     edx, 27Dh
0x180005b07  jmp     loc_180005E17
0x180005b0c  mov     dil, 1
0x180005b0f  mov     [rsp+150h+var_120], dil
0x180005b14  test    dil, dil
0x180005b17  jnz     loc_180005BE4
0x180005b1d  mov     rdx, [rbp+50h+arg_8]; struct Common::RegistryKey *
0x180005b21  lea     r8, [rsp+150h+var_120]; struct AppxAllUserStore::_MainPackageInfo *
0x180005b26  lea     rcx, [rsp+150h+hKey]; this
0x180005b2b  call    ?NeedsRefreshBasedOnDependencies@AppxAllUserStore@@YAJAEAVRegistryKey@Common@@PEAU_MainPackageInfo@1@AEA_N@Z; AppxAllUserStore::NeedsRefreshBasedOnDependencies(Common::RegistryKey &,AppxAllUserStore::_MainPackageInfo *,bool &)
0x180005b30  mov     ebx, eax
0x180005b32  test    eax, eax
0x180005b34  jns     short loc_180005B43
0x180005b36  mov     r9d, eax
0x180005b39  mov     edx, 285h
0x180005b3e  jmp     loc_180005E1A
0x180005b43  cmp     [rsp+150h+var_120], r14b
0x180005b48  jnz     loc_180005BE4
0x180005b4e  cmp     [rbp+50h+arg_18], r14
0x180005b52  jz      loc_180005DDD
0x180005b58  mov     rcx, [rsp+150h+hKey]; hKey
0x180005b5d  lea     rax, [rsp+150h+Data+4]
0x180005b62  mov     [rsp+150h+lpcbData], rax; lpcbData
0x180005b67  lea     rdx, ValueName; "LastReturnValue"
0x180005b6e  lea     rax, [rsp+150h+Data]
0x180005b73  mov     dword ptr [rsp+150h+Data], r14d
0x180005b78  xor     r9d, r9d; lpType
0x180005b7b  mov     [rsp+150h+phkResult], rax; lpData
0x180005b80  xor     r8d, r8d; lpReserved
0x180005b83  mov     dword ptr [rsp+150h+Data+4], 4
0x180005b8b  call    cs:__imp_RegQueryValueExW
0x180005b91  test    eax, eax
0x180005b93  jle     short loc_180005B9D
0x180005b95  movzx   eax, ax
0x180005b98  or      eax, r15d
0x180005b9b  test    eax, eax
0x180005b9d  js      short loc_180005BB2
0x180005b9f  cmp     dword ptr [rsp+150h+Data], r14d
0x180005ba4  jnz     short loc_180005BB2
0x180005ba6  mov     rax, [rbp+50h+arg_18]
0x180005baa  mov     byte ptr [rax], 1
0x180005bad  jmp     loc_180005DDD
0x180005bb2  mov     rax, [rbp+50h+arg_18]
0x180005bb6  lea     rcx, [rsp+150h+Data+8]; this
0x180005bbb  mov     [rsi], r14b
0x180005bbe  mov     [rax], r14b
0x180005bc1  mov     rdx, [rbp+50h+arg_8]
0x180005bc5  mov     rdx, [rdx]; Src
0x180005bc8  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180005bcd  mov     ebx, eax
0x180005bcf  test    eax, eax
0x180005bd1  jns     loc_180005DDD
0x180005bd7  mov     r9d, eax
0x180005bda  mov     edx, 2B2h
0x180005bdf  jmp     loc_180005E1A
0x180005be4  lea     r9, [rsp+150h+var_120]
0x180005be9  mov     dword ptr [rsp+150h+Data+4], r14d
0x180005bee  lea     r8, [rsp+150h+Data+4]
0x180005bf3  mov     [rsp+150h+var_120], r14b
0x180005bf8  lea     rdx, aIslobapp; "IsLOBApp"
0x180005bff  lea     rcx, [rsp+150h+hKey]
0x180005c04  call    ??$GetUInt32ValueIfExists@K@RegistryKey@Common@@QEAAJPEBGPEAKPEA_N@Z; Common::RegistryKey::GetUInt32ValueIfExists<ulong>(ushort const *,ulong *,bool *)
0x180005c09  mov     ebx, eax
0x180005c0b  test    eax, eax
0x180005c0d  jns     short loc_180005C1C
0x180005c0f  mov     r9d, eax
0x180005c12  mov     edx, 28Ch
0x180005c17  jmp     loc_180005E1A
0x180005c1c  mov     rcx, [rbp+50h+arg_8]
0x180005c20  lea     r9, [rsp+150h+var_120]; bool *
0x180005c25  mov     eax, dword ptr [rsp+150h+Data+4]
0x180005c29  lea     r8, [rsp+150h+var_F8+8]; struct Common::StringBuffer *
0x180005c2e  xorps   xmm0, xmm0
0x180005c31  mov     dword ptr [rsp+150h+var_E8+8], r14d
0x180005c36  movups  [rsp+150h+var_F8+8], xmm0
0x180005c3b  mov     [rcx+24h], eax
0x180005c3e  lea     rcx, [rsp+150h+hKey]; this
0x180005c43  call    ?GetStringValueIfExists@RegistryKey@Common@@QEAAJPEBGPEAVStringBuffer@2@PEA_N@Z; Common::RegistryKey::GetStringValueIfExists(ushort const *,Common::StringBuffer *,bool *)
0x180005c48  mov     ebx, eax
0x180005c4a  test    eax, eax
0x180005c4c  jns     short loc_180005C75
0x180005c4e  mov     edx, 291h; void *
0x180005c53  mov     rcx, [rbp+58h]; this
0x180005c57  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x180005c5e  mov     r9d, eax; char *
0x180005c61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c66  lea     rcx, [rsp+150h+var_F8+8]; this
0x180005c6b  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180005c70  jmp     loc_180005E2A
0x180005c75  cmp     [rsp+150h+var_120], r14b
0x180005c7a  jz      short loc_180005C98
0x180005c7c  mov     rcx, qword ptr [rsp+150h+var_E8]
0x180005c81  mov     rax, [rbp+50h+arg_8]
0x180005c85  mov     qword ptr [rsp+150h+var_E8], r14
0x180005c8a  mov     dword ptr [rsp+150h+var_F8+8], r14d
0x180005c8f  mov     dword ptr [rsp+150h+var_E8+8], r14d
0x180005c94  mov     [rax+10h], rcx
0x180005c98  cmp     [rbp+50h+arg_18], r14
0x180005c9c  jz      short loc_180005CD4
0x180005c9e  lea     r8, [rsp+150h+Data]; unsigned int *
0x180005ca3  mov     dword ptr [rsp+150h+Data], r14d
0x180005ca8  lea     rdx, ValueName; "LastReturnValue"
0x180005caf  lea     rcx, [rsp+150h+hKey]; this
0x180005cb4  call    ?GetUInt32Value@RegistryKey@Common@@QEAAJPEBGPEAI@Z; Common::RegistryKey::GetUInt32Value(ushort const *,uint *)
0x180005cb9  test    eax, eax
0x180005cbb  js      short loc_180005CCD
0x180005cbd  cmp     dword ptr [rsp+150h+Data], r14d
0x180005cc2  jnz     short loc_180005CCD
0x180005cc4  mov     rax, [rbp+50h+arg_18]
0x180005cc8  mov     byte ptr [rax], 1
0x180005ccb  jmp     short loc_180005CD4
0x180005ccd  mov     rax, [rbp+50h+arg_18]
0x180005cd1  mov     [rax], r14b
0x180005cd4  mov     rdx, [rbp+50h+arg_8]
0x180005cd8  lea     rcx, [rsp+150h+Data+8]; this
0x180005cdd  mov     [rsi], r14b
0x180005ce0  mov     rdx, [rdx]; Src
0x180005ce3  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180005ce8  mov     ebx, eax
0x180005cea  test    eax, eax
0x180005cec  jns     short loc_180005CF8
0x180005cee  mov     edx, 2A7h
0x180005cf3  jmp     loc_180005C53
0x180005cf8  lea     rcx, [rsp+150h+var_F8+8]; this
0x180005cfd  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180005d02  jmp     loc_180005DDD
0x180005d07  mov     rcx, [rbp+50h+arg_8]
0x180005d0b  lea     r8, [rbp+50h+var_C0]; unsigned __int16 *
0x180005d0f  xorps   xmm0, xmm0
0x180005d12  mov     [rbp+50h+var_B0], r14d
0x180005d16  xor     eax, eax
0x180005d18  mov     [rbp+50h+var_90], r14d
0x180005d1c  movups  xmmword ptr [rbp+50h+var_C0], xmm0
0x180005d20  mov     [rbp+50h+var_70], r14d
0x180005d24  movups  [rbp+50h+var_A0], xmm0
0x180005d28  mov     [rbp+50h+var_58], r14d
0x180005d2c  movups  [rbp+50h+var_80], xmm0
0x180005d30  mov     [rbp+50h+var_A8], rax
0x180005d34  movups  [rbp+50h+var_68], xmm0
0x180005d38  mov     [rbp+50h+var_88], 0Bh
0x180005d3f  mov     rcx, [rcx]; this
0x180005d42  mov     [rsi], r14b
0x180005d45  call    ?GetPackageIDFromPackageMoniker@Deployment@Common@@YAJPEBG0PEAVPackageID@12@@Z; Common::Deployment::GetPackageIDFromPackageMoniker(ushort const *,ushort const *,Common::Deployment::PackageID *)
0x180005d4a  mov     ebx, eax
0x180005d4c  test    eax, eax
0x180005d4e  jns     short loc_180005D76
0x180005d50  mov     edx, 2C0h; void *
0x180005d55  mov     rcx, [rbp+58h]; this
0x180005d59  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x180005d60  mov     r9d, ebx; char *
0x180005d63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005d68  lea     rcx, [rbp+50h+var_C0]; this
0x180005d6c  call    ??1PackageID@Deployment@Common@@QEAA@XZ; Common::Deployment::PackageID::~PackageID(void)
0x180005d71  jmp     loc_180005E8D
0x180005d76  lea     rax, [rbp+50h+arg_18]
0x180005d7a  mov     [rsp+150h+lpcbData], rax
0x180005d7f  lea     r9, [rbp+50h+arg_0]
0x180005d83  lea     rax, [rbp+50h+arg_8]
0x180005d87  lea     r8, [rsp+150h+Data+8]
0x180005d8c  mov     [rsp+150h+phkResult], rax; int
0x180005d91  lea     rdx, [rbp+50h+var_C0]
0x180005d95  lea     rcx, [rbp+50h+var_50]
0x180005d99  call    _lambda_cc27486b722014f047fa87bd52250e61____lambda_cc27486b722014f047fa87bd52250e61_
0x180005d9e  mov     rcx, [rbp+50h+arg_0]
0x180005da2  lea     rdx, [rsp+150h+var_F8+8]
0x180005da7  movups  xmm0, xmmword ptr [rax]
0x180005daa  movups  xmm1, xmmword ptr [rax+10h]
0x180005dae  movaps  [rsp+150h+var_F8+8], xmm0
0x180005db3  movsd   xmm0, qword ptr [rax+20h]
0x180005db8  movsd   [rbp+50h+var_D0], xmm0
0x180005dbd  movaps  xmmword ptr [rsp+150h+var_E8+8], xmm1
0x180005dc2  call    AppxAllUserStore__EnumKeyAndDoActionForAllSubkeys__lambda_194360a9069636156e46757edebd65ba___
0x180005dc7  mov     ebx, eax
0x180005dc9  test    eax, eax
0x180005dcb  jns     short loc_180005DD4
0x180005dcd  mov     edx, 2F1h
0x180005dd2  jmp     short loc_180005D55
0x180005dd4  lea     rcx, [rbp+50h+var_C0]; this
0x180005dd8  call    ??1PackageID@Deployment@Common@@QEAA@XZ; Common::Deployment::PackageID::~PackageID(void)
0x180005ddd  cmp     [rsi], r14b
0x180005de0  jnz     short loc_180005E40
0x180005de2  cmp     dword ptr [rsp+150h+Data+8], r14d
0x180005de7  jnz     short loc_180005DF0
0x180005de9  mov     ebx, 80073CF1h
0x180005dee  jmp     short loc_180005E2A
0x180005df0  mov     rcx, [rbp+50h+arg_0]
0x180005df4  mov     rdx, [rsp+150h+lpSubKey]; lpSubKey
0x180005df9  mov     rcx, [rcx]; hKey
0x180005dfc  call    cs:__imp_RegDeleteTreeW
0x180005e02  mov     ebx, eax
0x180005e04  test    eax, eax
0x180005e06  jle     short loc_180005E0E
0x180005e08  movzx   ebx, ax
0x180005e0b  or      ebx, r15d
0x180005e0e  test    ebx, ebx
0x180005e10  jns     short loc_180005E40
0x180005e12  mov     edx, 2FBh; void *
0x180005e17  mov     r9d, ebx; char *
0x180005e1a  mov     rcx, [rbp+58h]; this
0x180005e1e  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x180005e25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005e2a  lea     rcx, [rsp+150h+hKey]; this
0x180005e2f  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180005e34  lea     rcx, [rsp+150h+Data+8]; this
0x180005e39  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180005e3e  jmp     short loc_180005EA6
0x180005e40  mov     rcx, [rsp+150h+hKey]
0x180005e45  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180005e4a  mov     rcx, [rsp+150h+lpSubKey]; void *
0x180005e4f  test    rcx, rcx
0x180005e52  jz      short loc_180005E59
0x180005e54  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180005e59  xor     eax, eax
0x180005e5b  jmp     short loc_180005EA8
0x180005e5d  mov     rcx, [rbp+58h]; this
0x180005e61  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\common\\regist"...
0x180005e68  mov     r9d, ebx; char *
0x180005e6b  mov     edx, 0ADh; void *
0x180005e70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005e75  mov     rcx, [rbp+58h]; this
0x180005e79  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x180005e80  mov     r9d, ebx; char *
0x180005e83  mov     edx, 275h; void *
0x180005e88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005e8d  mov     rcx, [rsp+150h+hKey]
0x180005e92  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180005e97  mov     rcx, [rsp+150h+lpSubKey]; void *
0x180005e9c  test    rcx, rcx
0x180005e9f  jz      short loc_180005EA6
0x180005ea1  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180005ea6  mov     eax, ebx
0x180005ea8  mov     rbx, [rsp+150h+arg_10]
0x180005eb0  add     rsp, 130h
  ... truncated ...
```
