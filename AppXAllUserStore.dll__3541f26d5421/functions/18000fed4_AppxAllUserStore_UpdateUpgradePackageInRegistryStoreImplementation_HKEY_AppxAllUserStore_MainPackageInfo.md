# AppxAllUserStore::UpdateUpgradePackageInRegistryStoreImplementation(HKEY__ *,AppxAllUserStore::_MainPackageInfo *)

- ea: `0x18000fed4`
- end: `0x180010133`
- name: `?UpdateUpgradePackageInRegistryStoreImplementation@AppxAllUserStore@@YAJPEAUHKEY__@@PEAU_MainPackageInfo@1@@Z`
- size: `607`
- prototype: `__int64 __fastcall(AppxAllUserStore *__hidden this, HKEY, struct AppxAllUserStore::_MainPackageInfo *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180030700`

## callees

- `0x180004920`
- `0x180004940`
- `0x180004968`
- `0x180006870`
- `0x180006d40`
- `0x180007860`
- `0x180007a10`
- `0x180007ebc`
- `0x18000a170`
- `0x18000fed4`
- `0x180018248`
- `0x1800269d8`
- `0x18002848c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010011`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010011`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::UpdateUpgradePackageInRegistryStoreImplementation(
        AppxAllUserStore *this,
        const unsigned __int16 *a2,
        struct AppxAllUserStore::_MainPackageInfo *a3,
        struct Common::Deployment::PackageID *a4)
{
  int PackageIDFromPackageMoniker; // eax
  unsigned __int16 **v5; // r9
  unsigned int v6; // ebx
  int PackageFamilyNameFromPackageFullName; // eax
  struct Common::StringBuffer *v8; // r9
  int AllUserChildStorePath; // eax
  const WCHAR *v10; // rbx
  HKEY v11; // rdi
  LSTATUS v12; // eax
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rax
  __int128 v16; // xmm1
  int v17; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  void *v21; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+48h] [rbp-B8h]
  unsigned __int16 v24[8]; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+60h] [rbp-A0h]
  __int64 v26; // [rsp+68h] [rbp-98h]
  __int128 v27; // [rsp+70h] [rbp-90h]
  int v28; // [rsp+80h] [rbp-80h]
  int v29; // [rsp+88h] [rbp-78h]
  __int128 v30; // [rsp+90h] [rbp-70h]
  int v31; // [rsp+A0h] [rbp-60h]
  __int128 v32; // [rsp+A8h] [rbp-58h]
  int v33; // [rsp+B8h] [rbp-48h]
  _OWORD v34[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v35; // [rsp+E0h] [rbp-20h]
  char v36; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]
  HKEY hKey; // [rsp+140h] [rbp+40h] BYREF
  LPCWCH *v39; // [rsp+148h] [rbp+48h] BYREF
  int v40; // [rsp+150h] [rbp+50h] BYREF
  HKEY v41; // [rsp+158h] [rbp+58h] BYREF

  v39 = (LPCWCH *)a2;
  hKey = (HKEY)this;
  v29 = 11;
  v25 = 0;
  *(_OWORD *)v24 = 0;
  v28 = 0;
  v27 = 0;
  v31 = 0;
  v30 = 0;
  v33 = 0;
  v32 = 0;
  v26 = 0;
  PackageIDFromPackageMoniker = Common::Deployment::GetPackageIDFromPackageMoniker(
                                  *(Common::Deployment **)a2,
                                  a2,
                                  v24,
                                  a4);
  v6 = PackageIDFromPackageMoniker;
  if ( PackageIDFromPackageMoniker < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64E,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
      (const char *)(unsigned int)PackageIDFromPackageMoniker,
      phkResult);
LABEL_17:
    Common::Deployment::PackageID::~PackageID((Common::Deployment::PackageID *)v24);
    return v6;
  }
  v21 = 0;
  v40 = 0;
  PackageFamilyNameFromPackageFullName = AppxAllUserStore::GetPackageFamilyNameFromPackageFullName(
                                           *v39,
                                           (unsigned __int16 *)&v40,
                                           (unsigned int *)&v21,
                                           v5);
  v6 = PackageFamilyNameFromPackageFullName;
  if ( PackageFamilyNameFromPackageFullName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x653,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
      (const char *)(unsigned int)PackageFamilyNameFromPackageFullName,
      phkResult);
LABEL_16:
    Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(&v21);
    goto LABEL_17;
  }
  v23 = 0;
  *(_OWORD *)lpSubKey = 0;
  AllUserChildStorePath = AppxAllUserStore::GetAllUserChildStorePath(
                            (AppxAllUserStore *)L"Upgrade",
                            0,
                            (unsigned int *)lpSubKey,
                            v8);
  v6 = AllUserChildStorePath;
  if ( AllUserChildStorePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x656,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
      (const char *)(unsigned int)AllUserChildStorePath,
      phkResult);
LABEL_15:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
    goto LABEL_16;
  }
  v10 = lpSubKey[1];
  v11 = hKey;
  v41 = 0;
  Common::AutoHandleCloseHKEY<HKEY__ *>(0);
  v41 = 0;
  v12 = RegOpenKeyExW(v11, v10, 0, 0x20019u, &v41);
  v6 = v12;
  if ( v12 > 0 )
    v6 = (unsigned __int16)v12 | 0x80070000;
  if ( v6 + 2147024894 <= 1 )
  {
    Common::RegistryKey::~RegistryKey(&v41);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
    Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(&v21);
  }
  else
  {
    if ( (v6 & 0x80000000) != 0 )
    {
      v13 = v6;
      v14 = 1630;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
        (const char *)v13,
        phkResulta);
      Common::RegistryKey::~RegistryKey(&v41);
      goto LABEL_15;
    }
    v15 = lambda_cc27486b722014f047fa87bd52250e61_::_lambda_cc27486b722014f047fa87bd52250e61_(
            (unsigned int)&v36,
            (unsigned int)&v21,
            (unsigned int)&v41,
            (unsigned int)v24,
            (__int64)&hKey,
            (__int64)&v39);
    v16 = *(_OWORD *)(v15 + 16);
    v34[0] = *(_OWORD *)v15;
    v35 = *(_QWORD *)(v15 + 32);
    v34[1] = v16;
    v17 = AppxAllUserStore::EnumKeyAndDoActionForAllSubkeys__lambda_473c16a5bb81ddf2b14a95560b74d61f___(&v41, v34);
    v6 = v17;
    if ( v17 < 0 )
    {
      v13 = (unsigned int)v17;
      v14 = 1677;
      goto LABEL_14;
    }
    Common::AutoHandleCloseHKEY<HKEY__ *>(v41);
    if ( lpSubKey[1] )
      Common::GlobalHeap::Free((void *)lpSubKey[1]);
    Common::GlobalHeap::Free(v21);
  }
  Common::Deployment::PackageID::~PackageID((Common::Deployment::PackageID *)v24);
  return 0;
}

```

## disassembly

```asm
0x18000fed4  mov     [rsp-8+arg_8], rdx
0x18000fed9  mov     [rsp-8+hKey], rcx
0x18000fede  push    rbp
0x18000fedf  push    rbx
0x18000fee0  push    rdi
0x18000fee1  lea     rbp, [rsp-20h]
0x18000fee6  sub     rsp, 120h
0x18000feed  xor     eax, eax
0x18000feef  mov     [rbp+30h+var_A8], 0Bh
0x18000fef6  xorps   xmm0, xmm0
0x18000fef9  mov     [rsp+130h+var_D0], eax
0x18000fefd  movups  xmmword ptr [rsp+130h+var_E0], xmm0
0x18000ff02  mov     [rbp+30h+var_B0], eax
0x18000ff05  lea     r8, [rsp+130h+var_E0]; unsigned __int16 *
0x18000ff0a  movups  [rsp+130h+var_C0], xmm0
0x18000ff0f  mov     [rbp+30h+var_90], eax
0x18000ff12  movups  [rbp+30h+var_A0], xmm0
0x18000ff16  mov     [rbp+30h+var_78], eax
0x18000ff19  movups  [rbp+30h+var_88], xmm0
0x18000ff1d  mov     [rsp+130h+var_C8], rax
0x18000ff22  mov     rcx, [rdx]; this
0x18000ff25  call    ?GetPackageIDFromPackageMoniker@Deployment@Common@@YAJPEBG0PEAVPackageID@12@@Z; Common::Deployment::GetPackageIDFromPackageMoniker(ushort const *,ushort const *,Common::Deployment::PackageID *)
0x18000ff2a  mov     ebx, eax
0x18000ff2c  test    eax, eax
0x18000ff2e  jns     short loc_18000FF4D
0x18000ff30  mov     rcx, [rbp+38h]; this
0x18000ff34  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000ff3b  mov     r9d, eax; char *
0x18000ff3e  mov     edx, 64Eh; void *
0x18000ff43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ff48  jmp     loc_1800100CD
0x18000ff4d  mov     rcx, [rbp+30h+arg_8]
0x18000ff51  lea     r8, [rsp+130h+var_100]; unsigned int *
0x18000ff56  mov     [rsp+130h+var_100], 0
0x18000ff5f  lea     rdx, [rbp+30h+arg_10]; unsigned __int16 *
0x18000ff63  mov     [rbp+30h+arg_10], 0
0x18000ff6a  mov     rcx, [rcx]; lpString1
0x18000ff6d  call    ?GetPackageFamilyNameFromPackageFullName@AppxAllUserStore@@YAJPEBGPEAIPEAPEAG@Z; AppxAllUserStore::GetPackageFamilyNameFromPackageFullName(ushort const *,uint *,ushort * *)
0x18000ff72  mov     ebx, eax
0x18000ff74  test    eax, eax
0x18000ff76  jns     short loc_18000FF95
0x18000ff78  mov     rcx, [rbp+38h]; this
0x18000ff7c  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000ff83  mov     r9d, eax; char *
0x18000ff86  mov     edx, 653h; void *
0x18000ff8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ff90  jmp     loc_1800100C3
0x18000ff95  xor     eax, eax
0x18000ff97  lea     r8, [rsp+130h+lpSubKey]; bool
0x18000ff9c  xorps   xmm0, xmm0
0x18000ff9f  mov     [rsp+130h+var_E8], eax
0x18000ffa3  xor     edx, edx; unsigned __int16 *
0x18000ffa5  lea     rcx, ?upgradeApplicationsString@AppxAllUserStore@@3QBGB; "Upgrade"
0x18000ffac  movups  xmmword ptr [rsp+130h+lpSubKey], xmm0
0x18000ffb1  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x18000ffb6  mov     ebx, eax
0x18000ffb8  test    eax, eax
0x18000ffba  jns     short loc_18000FFD9
0x18000ffbc  mov     rcx, [rbp+38h]; this
0x18000ffc0  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000ffc7  mov     r9d, eax; char *
0x18000ffca  mov     edx, 656h; void *
0x18000ffcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ffd4  jmp     loc_1800100B9
0x18000ffd9  mov     rbx, [rsp+130h+lpSubKey+8]
0x18000ffde  xor     ecx, ecx
0x18000ffe0  mov     rdi, [rbp+30h+hKey]
0x18000ffe4  mov     [rbp+30h+arg_18], 0
0x18000ffec  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000fff1  lea     rax, [rbp+30h+arg_18]
0x18000fff5  mov     [rbp+30h+arg_18], 0
0x18000fffd  mov     r9d, 20019h; samDesired
0x180010003  mov     [rsp+130h+phkResult], rax; phkResult
0x180010008  xor     r8d, r8d; ulOptions
0x18001000b  mov     rdx, rbx; lpSubKey
0x18001000e  mov     rcx, rdi; hKey
0x180010011  call    cs:__imp_RegOpenKeyExW
0x180010017  mov     ebx, eax
0x180010019  test    eax, eax
0x18001001b  jle     short loc_180010026
0x18001001d  movzx   ebx, ax
0x180010020  or      ebx, 80070000h
0x180010026  lea     eax, [rbx+7FF8FFFEh]
0x18001002c  cmp     eax, 1
0x18001002f  jbe     loc_1800100FF
0x180010035  test    ebx, ebx
0x180010037  jns     short loc_180010043
0x180010039  mov     r9d, ebx
0x18001003c  mov     edx, 65Eh
0x180010041  jmp     short loc_1800100A0
0x180010043  lea     rax, [rbp+30h+arg_8]
0x180010047  mov     [rsp+130h+var_108], rax
0x18001004c  lea     r9, [rsp+130h+var_E0]
0x180010051  lea     rax, [rbp+30h+hKey]
0x180010055  lea     r8, [rbp+30h+arg_18]
0x180010059  mov     [rsp+130h+phkResult], rax; int
0x18001005e  lea     rdx, [rsp+130h+var_100]
0x180010063  lea     rcx, [rbp+30h+var_40]
0x180010067  call    _lambda_cc27486b722014f047fa87bd52250e61____lambda_cc27486b722014f047fa87bd52250e61_
0x18001006c  lea     rdx, [rbp+30h+var_70]
0x180010070  lea     rcx, [rbp+30h+arg_18]
0x180010074  movups  xmm0, xmmword ptr [rax]
0x180010077  movups  xmm1, xmmword ptr [rax+10h]
0x18001007b  movaps  [rbp+30h+var_70], xmm0
0x18001007f  movsd   xmm0, qword ptr [rax+20h]
0x180010084  movsd   [rbp+30h+var_50], xmm0
0x180010089  movaps  [rbp+30h+var_60], xmm1
0x18001008d  call    AppxAllUserStore__EnumKeyAndDoActionForAllSubkeys__lambda_473c16a5bb81ddf2b14a95560b74d61f___
0x180010092  mov     ebx, eax
0x180010094  test    eax, eax
0x180010096  jns     short loc_1800100DB
0x180010098  mov     r9d, eax; char *
0x18001009b  mov     edx, 68Dh; void *
0x1800100a0  mov     rcx, [rbp+38h]; this
0x1800100a4  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800100ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800100b0  lea     rcx, [rbp+30h+arg_18]; this
0x1800100b4  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800100b9  lea     rcx, [rsp+130h+lpSubKey]; this
0x1800100be  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800100c3  lea     rcx, [rsp+130h+var_100]
0x1800100c8  call    ??1?$AutoArray@U_MainPackageInfo@AppxAllUserStore@@$1??$AutoArrayDeallocate@U_MainPackageInfo@AppxAllUserStore@@@Common@@YAXPEAU12@@Z@Common@@QEAA@XZ; Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(void)
0x1800100cd  lea     rcx, [rsp+130h+var_E0]; this
0x1800100d2  call    ??1PackageID@Deployment@Common@@QEAA@XZ; Common::Deployment::PackageID::~PackageID(void)
0x1800100d7  mov     eax, ebx
0x1800100d9  jmp     short loc_180010128
0x1800100db  mov     rcx, [rbp+30h+arg_18]
0x1800100df  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1800100e4  mov     rcx, [rsp+130h+lpSubKey+8]; void *
0x1800100e9  test    rcx, rcx
0x1800100ec  jz      short loc_1800100F3
0x1800100ee  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800100f3  mov     rcx, [rsp+130h+var_100]; void *
0x1800100f8  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800100fd  jmp     short loc_18001011C
0x1800100ff  lea     rcx, [rbp+30h+arg_18]; this
0x180010103  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180010108  lea     rcx, [rsp+130h+lpSubKey]; this
0x18001010d  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180010112  lea     rcx, [rsp+130h+var_100]
0x180010117  call    ??1?$AutoArray@U_MainPackageInfo@AppxAllUserStore@@$1??$AutoArrayDeallocate@U_MainPackageInfo@AppxAllUserStore@@@Common@@YAXPEAU12@@Z@Common@@QEAA@XZ; Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(void)
0x18001011c  lea     rcx, [rsp+130h+var_E0]; this
0x180010121  call    ??1PackageID@Deployment@Common@@QEAA@XZ; Common::Deployment::PackageID::~PackageID(void)
0x180010126  xor     eax, eax
0x180010128  add     rsp, 120h
0x18001012f  pop     rdi
0x180010130  pop     rbx
0x180010131  pop     rbp
0x180010132  retn
```
