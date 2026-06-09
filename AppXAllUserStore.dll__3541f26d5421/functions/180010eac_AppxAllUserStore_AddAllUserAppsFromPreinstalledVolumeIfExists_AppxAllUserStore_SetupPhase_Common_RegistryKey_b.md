# AppxAllUserStore::AddAllUserAppsFromPreinstalledVolumeIfExists(AppxAllUserStore::SetupPhase,Common::RegistryKey *,bool,bool,Common::COMMON_STRING const *,Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> *,Common::Array<AppxAllUserStore::_MainPackageInfo,Common::ContainerOperations<AppxAllUserStore::_MainPackageInfo,AppxAllUserStore::_MainPackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_MainPackageInfo>,Common::ArrayOperations<AppxAllUserStore::_MainPackageInfo,Common::NoKey>> *)

- ea: `0x180010eac`
- end: `0x1800110c5`
- name: `?AddAllUserAppsFromPreinstalledVolumeIfExists@AppxAllUserStore@@YAJW4SetupPhase@1@PEAVRegistryKey@Common@@_N2PEBUCOMMON_STRING@4@PEAV?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@4@PEAV?$Array@U_MainPackageInfo@AppxAllUserStore@@V?$ContainerOperations@U_MainPackageInfo@AppxAllUserStore@@U12@@Common@@VNoKey@4@V?$ContainerOperations@VNoKey@Common@@U_MainPackageInfo@AppxAllUserStore@@@4@V?$ArrayOperations@U_MainPackageInfo@AppxAllUserStore@@VNoKey@Common@@@4@@4@@Z`
- size: `537`
- prototype: `__int64 __fastcall(int, __int64, char, char, __int64, char, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180015070`

## callees

- `0x1800036d4`
- `0x180004968`
- `0x180007278`
- `0x180007860`
- `0x180010eac`
- `0x1800110cc`
- `0x180018248`
- `0x18003eb64`
- `0x180046a5c`
- `0x18004954c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010fb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010fb8`

## string_xrefs

- `0x180010f39`: `<PreinstalledAppsVolumeHive>\`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::AddAllUserAppsFromPreinstalledVolumeIfExists(
        int a1,
        __int64 a2,
        char a3,
        char a4,
        __int64 a5,
        char a6,
        __int64 a7)
{
  int IsStateSeparationEnabled; // eax
  struct Common::RegistryKey *v12; // r8
  unsigned int v13; // ebx
  unsigned int v15; // edi
  int AllUserStoreForPreinstalledAppsVolume; // eax
  __int64 v17; // rcx
  unsigned int v18; // r8d
  LSTATUS v19; // eax
  __int64 v20; // rcx
  unsigned int v21; // r8d
  wil::details::in1diag3 *v22; // rcx
  unsigned __int64 v23; // r9
  __int64 v24; // rdx
  int v25; // eax
  int phkResult; // [rsp+20h] [rbp-40h]
  int phkResulta; // [rsp+20h] [rbp-40h]
  bool v28; // [rsp+40h] [rbp-20h] BYREF
  HKEY v29; // [rsp+48h] [rbp-18h] BYREF
  HKEY hKey[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v28 = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled(&v28);
  v13 = IsStateSeparationEnabled;
  if ( IsStateSeparationEnabled < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x99E,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)(unsigned int)IsStateSeparationEnabled,
      phkResult);
    return v13;
  }
  if ( v28 )
  {
    hKey[0] = 0;
    v15 = a4 != 0 ? 0xFFFFFFFA : 0;
    AllUserStoreForPreinstalledAppsVolume = AppxAllUserStore::GetAllUserStoreForPreinstalledAppsVolume(
                                              v15 + 131103,
                                              hKey,
                                              v12);
    v13 = AllUserStoreForPreinstalledAppsVolume;
    if ( AllUserStoreForPreinstalledAppsVolume < 0 )
    {
      if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
        McTemplateU0zd_EventWriteTransfer(
          v17,
          AppxAllUserStoreOpenKeyError,
          L"<PreinstalledAppsVolumeHive>\\",
          (unsigned int)AllUserStoreForPreinstalledAppsVolume);
      if ( v13 + 2147024894 > 1 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9AF,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
          (const char *)v13,
          phkResult);
LABEL_27:
        Common::RegistryKey::~RegistryKey(hKey);
        return v13;
      }
      wil::details::in1diag3::Log_Hr(retaddr, (void *)0x9AC, v18, (const char *)v13, phkResult);
LABEL_19:
      v13 = 0;
      goto LABEL_27;
    }
    v29 = 0;
    Common::AutoHandleCloseHKEY<HKEY__ *>(0);
    v29 = 0;
    v19 = RegOpenKeyExW(hKey[0], L"Applications", 0, v15 + 131103, &v29);
    v13 = v19;
    if ( v19 > 0 )
      v13 = (unsigned __int16)v19 | 0x80070000;
    if ( (v13 & 0x80000000) != 0 )
    {
      if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
        McTemplateU0zd_EventWriteTransfer(v20, AppxAllUserStoreOpenKeyError, L"Applications", v13);
      v22 = retaddr;
      v23 = v13;
      if ( v13 + 2147024894 <= 1 )
      {
        wil::details::in1diag3::Log_Hr(retaddr, (void *)0x9BE, v21, (const char *)v13, phkResulta);
        Common::RegistryKey::~RegistryKey(&v29);
        goto LABEL_19;
      }
      v24 = 2497;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        v22,
        (void *)v24,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)v23,
        phkResulta);
      Common::RegistryKey::~RegistryKey(&v29);
      goto LABEL_27;
    }
    v25 = AppxAllUserStore::AddAllUserApplicationsToDynamicArrayForUser(
            a1,
            (Common::RegistryKey *)&v29,
            a2,
            a3,
            a4,
            a5,
            a6,
            a7);
    v13 = v25;
    if ( v25 < 0 )
    {
      v24 = 2508;
LABEL_25:
      v22 = retaddr;
      v23 = (unsigned int)v25;
      goto LABEL_26;
    }
    if ( !a4 )
    {
      v25 = Common::RegistryKey::FlushKey((Common::RegistryKey *)hKey);
      v13 = v25;
      if ( v25 < 0 )
      {
        v24 = 2512;
        goto LABEL_25;
      }
    }
    Common::AutoHandleCloseHKEY<HKEY__ *>(v29);
    Common::AutoHandleCloseHKEY<HKEY__ *>(hKey[0]);
  }
  return 0;
}

```

## disassembly

```asm
0x180010eac  push    rbp
0x180010eae  push    rbx
0x180010eaf  push    rsi
0x180010eb0  push    rdi
0x180010eb1  push    r12
0x180010eb3  push    r14
0x180010eb5  push    r15
0x180010eb7  mov     rbp, rsp
0x180010eba  sub     rsp, 60h
0x180010ebe  mov     r12d, ecx
0x180010ec1  mov     [rbp+var_20], 0
0x180010ec5  lea     rcx, [rbp+var_20]; bool *
0x180010ec9  mov     sil, r9b
0x180010ecc  mov     r14b, r8b
0x180010ecf  mov     r15, rdx
0x180010ed2  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x180010ed7  mov     ebx, eax
0x180010ed9  test    eax, eax
0x180010edb  jns     short loc_180010EFC
0x180010edd  mov     rcx, [rbp+38h]; this
0x180010ee1  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x180010ee8  mov     r9d, eax; char *
0x180010eeb  mov     edx, 99Eh; void *
0x180010ef0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010ef5  mov     eax, ebx
0x180010ef7  jmp     loc_1800110B6
0x180010efc  cmp     [rbp+var_20], 0
0x180010f00  jz      loc_1800110B4
0x180010f06  mov     al, sil
0x180010f09  mov     [rbp+hKey], 0
0x180010f11  neg     al
0x180010f13  lea     rdx, [rbp+hKey]; phkResult
0x180010f17  sbb     edi, edi
0x180010f19  and     edi, 0FFFFFFFAh
0x180010f1c  lea     ecx, [rdi+2001Fh]; samDesired
0x180010f22  call    ?GetAllUserStoreForPreinstalledAppsVolume@AppxAllUserStore@@YAJKAEAVRegistryKey@Common@@@Z; AppxAllUserStore::GetAllUserStoreForPreinstalledAppsVolume(ulong,Common::RegistryKey &)
0x180010f27  mov     ebx, eax
0x180010f29  test    eax, eax
0x180010f2b  jns     short loc_180010F83
0x180010f2d  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x180010f34  jge     short loc_180010F4C
0x180010f36  mov     r9d, eax
0x180010f39  lea     r8, aPreinstalledap_0; "<PreinstalledAppsVolumeHive>\\"
0x180010f40  lea     rdx, AppxAllUserStoreOpenKeyError
0x180010f47  call    McTemplateU0zd_EventWriteTransfer
0x180010f4c  lea     ecx, [rbx+7FF8FFFEh]
0x180010f52  mov     r9d, ebx; char *
0x180010f55  cmp     ecx, 1
0x180010f58  mov     rcx, [rbp+38h]; this
0x180010f5c  jbe     short loc_180010F74
0x180010f5e  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x180010f65  mov     edx, 9AFh; void *
0x180010f6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010f6f  jmp     loc_180011094
0x180010f74  mov     edx, 9ACh; void *
0x180010f79  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180010f7e  jmp     loc_18001101C
0x180010f83  xor     ecx, ecx
0x180010f85  mov     [rbp+var_18], 0
0x180010f8d  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180010f92  mov     rcx, [rbp+hKey]; hKey
0x180010f96  lea     rax, [rbp+var_18]
0x180010f9a  lea     r9d, [rdi+2001Fh]; samDesired
0x180010fa1  mov     [rsp+60h+phkResult], rax; int
0x180010fa6  xor     r8d, r8d; ulOptions
0x180010fa9  mov     [rbp+var_18], 0
0x180010fb1  lea     rdx, ?allUserApplicationsString@AppxAllUserStore@@3QBGB; "Applications"
0x180010fb8  call    cs:__imp_RegOpenKeyExW
0x180010fbe  mov     ebx, eax
0x180010fc0  test    eax, eax
0x180010fc2  jle     short loc_180010FCD
0x180010fc4  movzx   ebx, ax
0x180010fc7  or      ebx, 80070000h
0x180010fcd  test    ebx, ebx
0x180010fcf  jns     short loc_180011020
0x180010fd1  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x180010fd8  jge     short loc_180010FF0
0x180010fda  mov     r9d, ebx
0x180010fdd  lea     r8, ?allUserApplicationsString@AppxAllUserStore@@3QBGB; "Applications"
0x180010fe4  lea     rdx, AppxAllUserStoreOpenKeyError
0x180010feb  call    McTemplateU0zd_EventWriteTransfer
0x180010ff0  mov     rcx, [rbp+38h]; this
0x180010ff4  lea     eax, [rbx+7FF8FFFEh]
0x180010ffa  mov     r9d, ebx; char *
0x180010ffd  cmp     eax, 1
0x180011000  jbe     short loc_180011009
0x180011002  mov     edx, 9C1h
0x180011007  jmp     short loc_18001107F
0x180011009  mov     edx, 9BEh; void *
0x18001100e  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180011013  lea     rcx, [rbp+var_18]; this
0x180011017  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18001101c  xor     ebx, ebx
0x18001101e  jmp     short loc_180011094
0x180011020  mov     rax, [rbp+arg_30]
0x180011024  lea     rdx, [rbp+var_18]
0x180011028  mov     [rsp+60h+var_28], rax
0x18001102d  mov     r9b, r14b
0x180011030  mov     rax, [rbp+arg_28]
0x180011034  mov     r8, r15
0x180011037  mov     [rsp+60h+var_30], rax
0x18001103c  mov     ecx, r12d
0x18001103f  mov     rax, [rbp+arg_20]
0x180011043  mov     [rsp+60h+var_38], rax
0x180011048  mov     byte ptr [rsp+60h+phkResult], sil; int
0x18001104d  call    ?AddAllUserApplicationsToDynamicArrayForUser@AppxAllUserStore@@YAJW4SetupPhase@1@PEAVRegistryKey@Common@@1_N2PEBUCOMMON_STRING@4@PEAV?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@4@PEAV?$Array@U_MainPackageInfo@AppxAllUserStore@@V?$ContainerOperations@U_MainPackageInfo@AppxAllUserStore@@U12@@Common@@VNoKey@4@V?$ContainerOperations@VNoKey@Common@@U_MainPackageInfo@AppxAllUserStore@@@4@V?$ArrayOperations@U_MainPackageInfo@AppxAllUserStore@@VNoKey@Common@@@4@@4@@Z; AppxAllUserStore::AddAllUserApplicationsToDynamicArrayForUser(AppxAllUserStore::SetupPhase,Common::RegistryKey *,Common::RegistryKey *,bool,bool,Common::COMMON_STRING const *,Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> *,Common::Array<AppxAllUserStore::_MainPackageInfo,Common::ContainerOperations<AppxAllUserStore::_MainPackageInfo,AppxAllUserStore::_MainPackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_MainPackageInfo>,Common::ArrayOperations<AppxAllUserStore::_MainPackageInfo,Common::NoKey>> *)
0x180011052  mov     ebx, eax
0x180011054  test    eax, eax
0x180011056  jns     short loc_18001105F
0x180011058  mov     edx, 9CCh
0x18001105d  jmp     short loc_180011078
0x18001105f  test    sil, sil
0x180011062  jnz     short loc_1800110A2
0x180011064  lea     rcx, [rbp+hKey]; this
0x180011068  call    ?FlushKey@RegistryKey@Common@@QEAAJXZ; Common::RegistryKey::FlushKey(void)
0x18001106d  mov     ebx, eax
0x18001106f  test    eax, eax
0x180011071  jns     short loc_1800110A2
0x180011073  mov     edx, 9D0h; void *
0x180011078  mov     rcx, [rbp+38h]; this
0x18001107c  mov     r9d, eax; char *
0x18001107f  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x180011086  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001108b  lea     rcx, [rbp+var_18]; this
0x18001108f  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180011094  lea     rcx, [rbp+hKey]; this
0x180011098  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18001109d  jmp     loc_180010EF5
0x1800110a2  mov     rcx, [rbp+var_18]
0x1800110a6  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1800110ab  mov     rcx, [rbp+hKey]
0x1800110af  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1800110b4  xor     eax, eax
0x1800110b6  add     rsp, 60h
0x1800110ba  pop     r15
0x1800110bc  pop     r14
0x1800110be  pop     r12
0x1800110c0  pop     rdi
0x1800110c1  pop     rsi
0x1800110c2  pop     rbx
0x1800110c3  pop     rbp
0x1800110c4  retn
```
