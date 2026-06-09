# OSIntegration::Tools::WaitForPackageServicingToFinish(ushort const *)

- ea: `0x18006bda0`
- end: `0x18006c141`
- name: `?WaitForPackageServicingToFinish@Tools@OSIntegration@@YAJPEBG@Z`
- size: `929`
- prototype: `__int64 __fastcall(PCWSTR packageFullName, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b6ac0`
- `0x1800bd8b0`

## callees

- `0x18000e6e0`
- `0x180021224`
- `0x1800507a0`
- `0x18005ded4`
- `0x18006bda0`
- `0x18006cb78`
- `0x180081254`
- `0x1800937d4`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800a2854`
- `0x1800f0260`
- `0x1800f0700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006c04b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006c04b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006c008`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006c008`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18006c039`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18006c039`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006be18`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006be18`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18006bddc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18006bddc`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatusForUser` at `0x18006bfc8`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatusForUser` at `0x18006c060`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatusForUser` at `0x18006bfc8`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatusForUser` at `0x18006c060`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18006be32`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18006be32`
- `AppXDeploymentClient!__imp_RegisterNotification` at `0x18006be6e`
- `AppXDeploymentClient!__imp_RegisterNotification` at `0x18006be6e`
- `AppXDeploymentClient!__imp_UnregisterNotification` at `0x18006c0d8`
- `AppXDeploymentClient!__imp_UnregisterNotification` at `0x18006c0d8`

## string_xrefs

- `0x18006bded`: `onecore\admin\appmodel\osim\src\deh\appx\common\tools.cpp`
- `0x18006be46`: `onecore\admin\appmodel\osim\src\deh\appx\common\tools.cpp`
- `0x18006becc`: `onecore\admin\appmodel\osim\src\deh\appx\common\tools.cpp`
- `0x18006bf3c`: `onecore\admin\appmodel\osim\src\deh\appx\common\tools.cpp`
- `0x18006bf90`: `onecore\admin\appmodel\osim\src\deh\appx\common\tools.cpp`
- `0x18006bfdc`: `onecore\admin\appmodel\osim\src\deh\appx\common\tools.cpp`
- `0x18006c08c`: `onecore\admin\appmodel\osim\src\deh\appx\common\tools.cpp`
- `0x18006c0a9`: `onecore\admin\appmodel\osim\src\deh\appx\common\tools.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OSIntegration::Tools::WaitForPackageServicingToFinish(
        PCWSTR packageFullName,
        const unsigned __int16 *a2)
{
  HRESULT v3; // ebx
  __int64 v4; // rdx
  unsigned int v6; // eax
  int CurrentUserSid; // eax
  unsigned int v8; // edi
  __int64 v9; // rdx
  int PersistedRegKeyPath; // eax
  unsigned __int64 v11; // rdx
  WCHAR *v12; // rcx
  WCHAR *v13; // rbx
  int v14; // eax
  __int64 v15; // rdx
  unsigned int PackageStatusForUser; // eax
  WCHAR *EventW; // rdi
  const char *v18; // r9
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  unsigned int LastError; // eax
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  BOOL fAsynchronous; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-C8h] BYREF
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+44h] [rbp-BCh] BYREF
  PSID Sid; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v33[4]; // [rsp+68h] [rbp-98h] BYREF
  GUID pguid; // [rsp+88h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  pguid = 0;
  v3 = CoCreateGuid(&pguid);
  if ( v3 < 0 )
  {
    v4 = 1244;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\tools.cpp",
      (const char *)(unsigned int)v3,
      fAsynchronous);
    return (unsigned int)v3;
  }
  StringFromGUID2(&pguid, sz, 39);
  packageFamilyNameLength = 65;
  v6 = PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName);
  if ( v6 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x4E3,
             (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\tools.cpp",
             (const char *)v6,
             fAsynchronous);
  v3 = RegisterNotification(L"Package", sz, packageFamilyName);
  if ( v3 < 0 )
  {
    v4 = 1253;
    goto LABEL_3;
  }
  Sid = 0;
  v31 = 0;
  v32 = 0;
  CurrentUserSid = Common::SidHelper::GetCurrentUserSid(&Sid);
  v8 = CurrentUserSid;
  if ( CurrentUserSid >= 0 )
  {
    CurrentUserSid = Common::SidHelper::ConvertSidToString(Sid, (struct Common::StringBuffer *)&v31);
    v8 = CurrentUserSid;
    if ( CurrentUserSid < 0 )
    {
      v9 = 1258;
      goto LABEL_12;
    }
    lpSubKey = 0;
    v33[0] = L"Package";
    v33[1] = packageFamilyName;
    v33[2] = *((unsigned __int16 **)&v31 + 1);
    v33[3] = sz;
    PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(
                            (const struct Common::StateSeparationRedirectionMapping *)&Common::StateSeparation::AppModelDeploymentNotifications,
                            (const unsigned __int16 **)v33,
                            4u,
                            (unsigned __int16 **)&lpSubKey);
    v8 = PersistedRegKeyPath;
    if ( PersistedRegKeyPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4EE,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\tools.cpp",
        (const char *)(unsigned int)PersistedRegKeyPath,
        fAsynchronous);
      v12 = (WCHAR *)lpSubKey;
LABEL_15:
      operator delete(v12, v11);
      goto LABEL_38;
    }
    hKey = 0;
    v13 = (WCHAR *)lpSubKey;
    v14 = Common::RegistryKey::Open(&hKey, HKEY_LOCAL_MACHINE, lpSubKey, 0x20019u);
    v8 = v14;
    if ( v14 >= 0 )
    {
      v28 = 32;
      PackageStatusForUser = GetPackageStatusForUser(0, packageFullName, &v28);
      if ( PackageStatusForUser )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x4F4,
               (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\tools.cpp",
               (const char *)PackageStatusForUser,
               fAsynchronous);
        goto LABEL_19;
      }
      while ( (v28 & 0x20) != 0 )
      {
        EventW = (WCHAR *)CreateEventW(0, 1, 0, 0);
        lpSubKey = EventW;
        if ( (unsigned __int64)EventW - 1 > 0xFFFFFFFFFFFFFFFDuLL )
        {
          v21 = 1275;
LABEL_33:
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)v21,
                        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\tools.cpp",
                        v18);
LABEL_34:
          v8 = LastError;
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&lpSubKey);
          goto LABEL_19;
        }
        v19 = RegNotifyChangeKeyValue(hKey, 0, 4u, EventW, 1);
        if ( v19 )
        {
          v20 = 1277;
LABEL_31:
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)v20,
                        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\tools.cpp",
                        (const char *)v19,
                        fAsynchronous);
          goto LABEL_34;
        }
        if ( WaitForSingleObject(EventW, 0x7D0u) == -1 )
        {
          v21 = 1281;
          goto LABEL_33;
        }
        v19 = GetPackageStatusForUser(0, packageFullName, &v28);
        if ( v19 )
        {
          v20 = 1283;
          goto LABEL_31;
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&lpSubKey);
      }
      v14 = UnregisterNotification(L"Package", sz, packageFamilyName);
      v8 = v14;
      if ( v14 >= 0 )
      {
        Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
        operator delete(v13, v23);
        v8 = 0;
        goto LABEL_38;
      }
      v15 = 1286;
    }
    else
    {
      v15 = 1265;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\tools.cpp",
      (const char *)(unsigned int)v14,
      fAsynchronous);
LABEL_19:
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
    v12 = v13;
    goto LABEL_15;
  }
  v9 = 1257;
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\tools.cpp",
    (const char *)(unsigned int)CurrentUserSid,
    fAsynchronous);
LABEL_38:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v31);
  operator delete(Sid, v24);
  return v8;
}

```

## disassembly

```asm
0x18006bda0  mov     [rsp-8+arg_8], rbx
0x18006bda5  mov     [rsp-8+arg_10], rsi
0x18006bdaa  push    rbp
0x18006bdab  push    rdi
0x18006bdac  push    r15
0x18006bdae  lea     rbp, [rsp-90h]
0x18006bdb6  sub     rsp, 190h
0x18006bdbd  mov     rax, cs:__security_cookie
0x18006bdc4  xor     rax, rsp
0x18006bdc7  mov     [rbp+0A0h+var_20], rax
0x18006bdce  mov     rsi, rcx
0x18006bdd1  xorps   xmm0, xmm0
0x18006bdd4  movups  xmmword ptr [rbp+0A0h+pguid.Data1], xmm0
0x18006bdd8  lea     rcx, [rbp+0A0h+pguid]; pguid
0x18006bddc  call    cs:__imp_CoCreateGuid
0x18006bde2  mov     ebx, eax
0x18006bde4  test    eax, eax
0x18006bde6  jns     short loc_18006BE0A
0x18006bde8  mov     edx, 4DCh; void *
0x18006bded  lea     r8, aOnecoreAdminAp_38; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006bdf4  mov     r9d, ebx; char *
0x18006bdf7  mov     rcx, [rbp+0A8h]; this
0x18006bdfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006be03  mov     eax, ebx
0x18006be05  jmp     loc_18006C11A
0x18006be0a  mov     r8d, 27h ; '''; cchMax
0x18006be10  lea     rdx, [rbp+0A0h+sz]; lpsz
0x18006be14  lea     rcx, [rbp+0A0h+pguid]; rguid
0x18006be18  call    cs:__imp_StringFromGUID2
0x18006be1e  mov     [rsp+1A0h+packageFamilyNameLength], 41h ; 'A'
0x18006be26  lea     r8, [rbp+0A0h+packageFamilyName]; packageFamilyName
0x18006be2a  lea     rdx, [rsp+1A0h+packageFamilyNameLength]; packageFamilyNameLength
0x18006be2f  mov     rcx, rsi; packageFullName
0x18006be32  call    cs:__imp_PackageFamilyNameFromFullName
0x18006be38  test    eax, eax
0x18006be3a  jz      short loc_18006BE5C
0x18006be3c  mov     rcx, [rbp+0A8h]; this
0x18006be43  mov     r9d, eax; char *
0x18006be46  lea     r8, aOnecoreAdminAp_38; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006be4d  mov     edx, 4E3h; void *
0x18006be52  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006be57  jmp     loc_18006C11A
0x18006be5c  lea     r8, [rbp+0A0h+packageFamilyName]
0x18006be60  lea     rdx, [rbp+0A0h+sz]
0x18006be64  lea     r15, aPackage_2; "Package"
0x18006be6b  mov     rcx, r15
0x18006be6e  call    cs:__imp_RegisterNotification
0x18006be74  mov     ebx, eax
0x18006be76  test    eax, eax
0x18006be78  jns     short loc_18006BE84
0x18006be7a  mov     edx, 4E5h
0x18006be7f  jmp     loc_18006BDED
0x18006be84  mov     [rsp+1A0h+Sid], 0
0x18006be8d  xor     eax, eax
0x18006be8f  xorps   xmm0, xmm0
0x18006be92  movups  [rsp+1A0h+var_150], xmm0
0x18006be97  mov     [rsp+1A0h+var_140], eax
0x18006be9b  lea     rcx, [rsp+1A0h+Sid]; void **
0x18006bea0  call    ?GetCurrentUserSid@SidHelper@Common@@SAJPEAPEAX@Z; Common::SidHelper::GetCurrentUserSid(void * *)
0x18006bea5  mov     edi, eax
0x18006bea7  test    eax, eax
0x18006bea9  jns     short loc_18006BEB2
0x18006beab  mov     edx, 4E9h
0x18006beb0  jmp     short loc_18006BECC
0x18006beb2  lea     rdx, [rsp+1A0h+var_150]; this
0x18006beb7  mov     rcx, [rsp+1A0h+Sid]; Sid
0x18006bebc  call    ?ConvertSidToString@SidHelper@Common@@SAJQEAXPEAVStringBuffer@2@@Z; Common::SidHelper::ConvertSidToString(void * const,Common::StringBuffer *)
0x18006bec1  mov     edi, eax
0x18006bec3  test    eax, eax
0x18006bec5  jns     short loc_18006BEE7
0x18006bec7  mov     edx, 4EAh; void *
0x18006becc  lea     r8, aOnecoreAdminAp_38; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006bed3  mov     r9d, eax; char *
0x18006bed6  mov     rcx, [rbp+0A8h]; this
0x18006bedd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bee2  jmp     loc_18006C103
0x18006bee7  mov     [rsp+1A0h+lpSubKey], 0
0x18006bef0  mov     [rsp+1A0h+var_138], r15
0x18006bef5  lea     rax, [rbp+0A0h+packageFamilyName]
0x18006bef9  mov     [rsp+1A0h+var_130], rax
0x18006befe  mov     rax, qword ptr [rsp+1A0h+var_150+8]
0x18006bf03  mov     [rsp+1A0h+var_128], rax
0x18006bf08  lea     rax, [rbp+0A0h+sz]
0x18006bf0c  mov     [rbp+0A0h+var_120], rax
0x18006bf10  lea     r9, [rsp+1A0h+lpSubKey]; unsigned __int16 **
0x18006bf15  mov     r8d, 4; unsigned __int64
0x18006bf1b  lea     rdx, [rsp+1A0h+var_138]; unsigned __int16 **
0x18006bf20  lea     rcx, ?AppModelDeploymentNotifications@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; struct Common::StateSeparationRedirectionMapping *
0x18006bf27  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort * *)
0x18006bf2c  mov     edi, eax
0x18006bf2e  test    eax, eax
0x18006bf30  jns     short loc_18006BF5D
0x18006bf32  mov     rcx, [rbp+0A8h]; this
0x18006bf39  mov     r9d, eax; char *
0x18006bf3c  lea     r8, aOnecoreAdminAp_38; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006bf43  mov     edx, 4EEh; void *
0x18006bf48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bf4d  nop
0x18006bf4e  mov     rcx, [rsp+1A0h+lpSubKey]; void *
0x18006bf53  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006bf58  jmp     loc_18006C103
0x18006bf5d  mov     [rsp+1A0h+hKey], 0
0x18006bf66  mov     r9d, 20019h; samDesired
0x18006bf6c  mov     rbx, [rsp+1A0h+lpSubKey]
0x18006bf71  mov     r8, rbx; lpSubKey
0x18006bf74  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18006bf7b  lea     rcx, [rsp+1A0h+hKey]; phkResult
0x18006bf80  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18006bf85  mov     edi, eax
0x18006bf87  test    eax, eax
0x18006bf89  jns     short loc_18006BFB6
0x18006bf8b  mov     edx, 4F1h; void *
0x18006bf90  lea     r8, aOnecoreAdminAp_38; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006bf97  mov     r9d, eax; char *
0x18006bf9a  mov     rcx, [rbp+0A8h]; this
0x18006bfa1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bfa6  lea     rcx, [rsp+1A0h+hKey]; this
0x18006bfab  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18006bfb0  nop
0x18006bfb1  mov     rcx, rbx
0x18006bfb4  jmp     short loc_18006BF53
0x18006bfb6  mov     [rsp+1A0h+var_160], 20h ; ' '
0x18006bfbe  lea     r8, [rsp+1A0h+var_160]
0x18006bfc3  mov     rdx, rsi
0x18006bfc6  xor     ecx, ecx
0x18006bfc8  call    cs:__imp_GetPackageStatusForUser
0x18006bfce  test    eax, eax
0x18006bfd0  jz      short loc_18006BFF1
0x18006bfd2  mov     rcx, [rbp+0A8h]; this
0x18006bfd9  mov     r9d, eax; char *
0x18006bfdc  lea     r8, aOnecoreAdminAp_38; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006bfe3  mov     edx, 4F4h; void *
0x18006bfe8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006bfed  mov     edi, eax
0x18006bfef  jmp     short loc_18006BFA6
0x18006bff1  test    byte ptr [rsp+1A0h+var_160], 20h
0x18006bff6  jz      loc_18006C0CD
0x18006bffc  xor     r9d, r9d; lpName
0x18006bfff  xor     r8d, r8d; bInitialState
0x18006c002  lea     edx, [r9+1]; bManualReset
0x18006c006  xor     ecx, ecx; lpEventAttributes
0x18006c008  call    cs:__imp_CreateEventW
0x18006c00e  mov     rdi, rax
0x18006c011  mov     [rsp+1A0h+lpSubKey], rax
0x18006c016  dec     rax
0x18006c019  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006c01d  ja      loc_18006C0A4
0x18006c023  mov     [rsp+1A0h+fAsynchronous], 1; unsigned int
0x18006c02b  mov     r9, rdi; hEvent
0x18006c02e  xor     edx, edx; bWatchSubtree
0x18006c030  lea     r8d, [rdx+4]; dwNotifyFilter
0x18006c034  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18006c039  call    cs:__imp_RegNotifyChangeKeyValue
0x18006c03f  test    eax, eax
0x18006c041  jnz     short loc_18006C087
0x18006c043  mov     edx, 7D0h; dwMilliseconds
0x18006c048  mov     rcx, rdi; hHandle
0x18006c04b  call    cs:__imp_WaitForSingleObject
0x18006c051  cmp     eax, 0FFFFFFFFh
0x18006c054  jz      short loc_18006C080
0x18006c056  lea     r8, [rsp+1A0h+var_160]
0x18006c05b  mov     rdx, rsi
0x18006c05e  xor     ecx, ecx
0x18006c060  call    cs:__imp_GetPackageStatusForUser
0x18006c066  test    eax, eax
0x18006c068  jnz     short loc_18006C079
0x18006c06a  lea     rcx, [rsp+1A0h+lpSubKey]
0x18006c06f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006c074  jmp     loc_18006BFF1
0x18006c079  mov     edx, 503h
0x18006c07e  jmp     short loc_18006C08C
0x18006c080  mov     edx, 501h
0x18006c085  jmp     short loc_18006C0A9
0x18006c087  mov     edx, 4FDh; void *
0x18006c08c  lea     r8, aOnecoreAdminAp_38; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006c093  mov     r9d, eax; char *
0x18006c096  mov     rcx, [rbp+0A8h]; this
0x18006c09d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006c0a2  jmp     short loc_18006C0BC
0x18006c0a4  mov     edx, 4FBh; void *
0x18006c0a9  lea     r8, aOnecoreAdminAp_38; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006c0b0  mov     rcx, [rbp+0A8h]; this
0x18006c0b7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006c0bc  mov     edi, eax
0x18006c0be  lea     rcx, [rsp+1A0h+lpSubKey]
0x18006c0c3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006c0c8  jmp     loc_18006BFA6
0x18006c0cd  lea     r8, [rbp+0A0h+packageFamilyName]
0x18006c0d1  lea     rdx, [rbp+0A0h+sz]
0x18006c0d5  mov     rcx, r15
0x18006c0d8  call    cs:__imp_UnregisterNotification
0x18006c0de  mov     edi, eax
0x18006c0e0  test    eax, eax
0x18006c0e2  jns     short loc_18006C0EE
0x18006c0e4  mov     edx, 506h
0x18006c0e9  jmp     loc_18006BF90
0x18006c0ee  lea     rcx, [rsp+1A0h+hKey]; this
0x18006c0f3  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18006c0f8  nop
0x18006c0f9  mov     rcx, rbx; void *
0x18006c0fc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006c101  xor     edi, edi
0x18006c103  lea     rcx, [rsp+1A0h+var_150]; this
0x18006c108  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18006c10d  nop
0x18006c10e  mov     rcx, [rsp+1A0h+Sid]; void *
0x18006c113  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006c118  mov     eax, edi
0x18006c11a  mov     rcx, [rbp+0A0h+var_20]
0x18006c121  xor     rcx, rsp; StackCookie
0x18006c124  call    __security_check_cookie
0x18006c129  lea     r11, [rsp+1A0h+var_10]
0x18006c131  mov     rbx, [r11+28h]
0x18006c135  mov     rsi, [r11+30h]
0x18006c139  mov     rsp, r11
0x18006c13c  pop     r15
0x18006c13e  pop     rdi
0x18006c13f  pop     rbp
0x18006c140  retn
```
