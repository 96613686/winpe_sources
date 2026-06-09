# AppxAllUserStore::Internal::RestoreDeletedPackagesInAllUserStore(AppxAllUserStore::BasicLogFile &,ushort const *,ushort const *,Common::RegistryKey &,Common::RegistryKey &)

- ea: `0x1800178e8`
- end: `0x180017cc8`
- name: `?RestoreDeletedPackagesInAllUserStore@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG1AEAVRegistryKey@Common@@2@Z`
- size: `992`
- prototype: `int(AppxAllUserStore::Internal *__hidden this, struct AppxAllUserStore::BasicLogFile *, const unsigned __int16 *, const unsigned __int16 *, struct Common::RegistryKey *, struct Common::RegistryKey *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180016d5c`

## callees

- `0x1800036d4`
- `0x180004920`
- `0x180004968`
- `0x180006d40`
- `0x18000d6a0`
- `0x1800178e8`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x1800192a4`
- `0x1800192ec`
- `0x180019318`
- `0x1800262ec`
- `0x1800467fc`

## string_xrefs

- `0x180017adf`: `Open %ls failed, 0x%0x.`
- `0x180017a6e`: `GetAllUserApplicationsPath failed, 0x%0x.`
- `0x180017b67`: `GetSystemSisPath, 0x%0x.`
- `0x180017909`: `In RestoreDeletedPackagesInAllUserStore %ls %ls.`
- `0x180017c60`: `DeleteSubKeyTreeIfExists 0x%0x.`
- `0x18001795d`: `Open failed, 0x%0x.`
- `0x1800179e5`: `Open deleted\%ls failed, 0x%0x.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::RestoreDeletedPackagesInAllUserStore(
        AppxAllUserStore::Internal *this,
        const WCHAR *a2,
        AppxAllUserStore *a3,
        unsigned __int64 a4,
        HKEY *a5)
{
  int v9; // eax
  HKEY v10; // rdx
  LSTATUS v11; // eax
  int v12; // eax
  __int64 v13; // rcx
  LSTATUS v14; // eax
  struct Common::StringBuffer *v15; // r9
  int v16; // eax
  __int64 v17; // rcx
  int AllUserChildStorePath; // eax
  int v19; // eax
  LSTATUS v20; // eax
  struct Common::StringBuffer *v21; // r8
  int v22; // eax
  __int64 v23; // rcx
  int SystemSisPath; // eax
  int v25; // eax
  __int64 v26; // rdx
  unsigned __int64 v27; // r9
  int v28; // eax
  _OWORD *v29; // rax
  __int128 v30; // xmm1
  int v31; // eax
  int v32; // eax
  unsigned int v33; // ebx
  int v34; // eax
  int v36; // [rsp+20h] [rbp-71h]
  HKEY v37; // [rsp+30h] [rbp-61h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+38h] [rbp-59h] BYREF
  int v39; // [rsp+48h] [rbp-49h]
  HKEY phkResult; // [rsp+50h] [rbp-41h] BYREF
  int v41[4]; // [rsp+58h] [rbp-39h] BYREF
  int v42; // [rsp+68h] [rbp-29h]
  _OWORD v43[2]; // [rsp+70h] [rbp-21h] BYREF
  char v44; // [rsp+90h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]
  HKEY v46; // [rsp+108h] [rbp+77h] BYREF

  v9 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"In RestoreDeletedPackagesInAllUserStore %ls %ls.", a3, a2);
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6BB,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v9);
  v10 = *(HKEY *)a4;
  phkResult = 0;
  v11 = Common::RegistryKey::Open(&phkResult, v10, a2, 0x20019u);
  LODWORD(a4) = v11;
  if ( v11 < 0 )
  {
    v12 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Open failed, 0x%0x.", (unsigned int)v11);
    if ( v12 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6C0,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v12);
    if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
      McTemplateU0zd_EventWriteTransfer(v13, AppxAllUserStoreOpenKeyError, a2, (unsigned int)a4);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C0,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)a4,
      v36);
    goto LABEL_45;
  }
  v46 = 0;
  v14 = Common::RegistryKey::Open(&v46, phkResult, L"Applications", 0x20019u);
  LODWORD(a4) = v14;
  if ( v14 < 0 )
  {
    v16 = AppxAllUserStore::BasicLogFile::WriteMsg(
            this,
            L"Open deleted\\%ls failed, 0x%0x.",
            L"Applications",
            (unsigned int)v14);
    if ( v16 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6C8,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v16);
    if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
      McTemplateU0zd_EventWriteTransfer(v17, AppxAllUserStoreOpenKeyError, L"Applications", (unsigned int)a4);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C8,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)a4,
      v36);
    goto LABEL_15;
  }
  v39 = 0;
  *(_OWORD *)lpSubKey = 0;
  AllUserChildStorePath = AppxAllUserStore::GetAllUserChildStorePath(
                            (AppxAllUserStore *)L"Applications",
                            0,
                            (unsigned int *)lpSubKey,
                            v15);
  LODWORD(a4) = AllUserChildStorePath;
  if ( AllUserChildStorePath < 0 )
  {
    v19 = AppxAllUserStore::BasicLogFile::WriteMsg(
            this,
            L"GetAllUserApplicationsPath failed, 0x%0x.",
            (unsigned int)AllUserChildStorePath);
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6CD,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v19);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6CD,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)a4,
      v36);
    goto LABEL_20;
  }
  v37 = 0;
  v20 = Common::RegistryKey::Open(&v37, *a5, lpSubKey[1], 0xF003Fu);
  LODWORD(a4) = v20;
  if ( v20 < 0 )
  {
    v22 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Open %ls failed, 0x%0x.", lpSubKey[1], (unsigned int)v20);
    if ( v22 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6D3,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v22);
    if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
      McTemplateU0zd_EventWriteTransfer(v23, AppxAllUserStoreOpenKeyError, lpSubKey[1], (unsigned int)a4);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D3,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)a4,
      v36);
    goto LABEL_27;
  }
  v42 = 0;
  *(_OWORD *)v41 = 0;
  SystemSisPath = AppxAllUserStore::GetSystemSisPath(a3, (Common::Deployment::Configuration *)v41, v21);
  LODWORD(a4) = SystemSisPath;
  if ( SystemSisPath < 0 )
  {
    v25 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"GetSystemSisPath, 0x%0x.", (unsigned int)SystemSisPath);
    if ( v25 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6D7,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v25);
    v26 = 1751;
    goto LABEL_32;
  }
  v28 = Common::PathHelpers::AddTrailingSlashIfNecessary((struct Common::StringBuffer *)v41);
  LODWORD(a4) = v28;
  if ( v28 < 0 )
  {
    v27 = (unsigned int)v28;
    v26 = 1752;
    goto LABEL_33;
  }
  v29 = (_OWORD *)lambda_e8ac0e144359e5e5f4b03267d2f650ae_::_lambda_e8ac0e144359e5e5f4b03267d2f650ae_(
                    (unsigned int)&v44,
                    (_DWORD)this,
                    (unsigned int)&v46,
                    (unsigned int)&v37,
                    (__int64)v41);
  v30 = v29[1];
  v43[0] = *v29;
  v43[1] = v30;
  a4 = (unsigned int)AppxAllUserStore::EnumKeyAndDoActionForAllSubkeys__lambda_bf31dbdb74ab162ca3e696a95a30df9c___(
                       &v46,
                       v43);
  v31 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"EnumKeyAndDoActionForAllSubkeys, 0x%0x.", a4);
  if ( v31 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6E8,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v31);
  if ( (a4 & 0x80000000) != 0LL )
  {
    v26 = 1769;
LABEL_32:
    v27 = (unsigned int)a4;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)v27,
      v36);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v41);
LABEL_27:
    Common::RegistryKey::~RegistryKey(&v37);
LABEL_20:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
LABEL_15:
    Common::RegistryKey::~RegistryKey(&v46);
    goto LABEL_45;
  }
  v32 = Common::RegistryKey::DeleteSubKeyTreeIfExists((Common::RegistryKey *)&v46, 0);
  v33 = v32;
  if ( v32 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6EC,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v32);
  v34 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"DeleteSubKeyTreeIfExists 0x%0x.", v33);
  if ( v34 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6ED,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v34);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v41);
  Common::RegistryKey::~RegistryKey(&v37);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
  Common::RegistryKey::~RegistryKey(&v46);
  LODWORD(a4) = 0;
LABEL_45:
  Common::RegistryKey::~RegistryKey(&phkResult);
  return (unsigned int)a4;
}

```

## disassembly

```asm
0x1800178e8  push    rbp
0x1800178ea  push    rbx
0x1800178eb  push    rsi
0x1800178ec  push    rdi
0x1800178ed  push    r12
0x1800178ef  push    r14
0x1800178f1  lea     rbp, [rsp-27h]
0x1800178f6  sub     rsp, 0B8h
0x1800178fd  mov     rbx, r9
0x180017900  mov     rsi, rdx
0x180017903  mov     r9, rdx
0x180017906  mov     r14, r8
0x180017909  lea     rdx, aInRestoredelet; "In RestoreDeletedPackagesInAllUserStore"...
0x180017910  mov     rdi, rcx
0x180017913  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180017918  lea     r12, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x18001791f  test    eax, eax
0x180017921  jns     short loc_180017937
0x180017923  mov     rcx, [rbp+57h]; this
0x180017927  mov     r9d, eax; char *
0x18001792a  mov     r8, r12; unsigned int
0x18001792d  mov     edx, 6BBh; void *
0x180017932  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017937  mov     rdx, [rbx]; hKey
0x18001793a  lea     rcx, [rbp+4Fh+phkResult]; phkResult
0x18001793e  mov     r9d, 20019h; samDesired
0x180017944  mov     [rbp+4Fh+phkResult], 0
0x18001794c  mov     r8, rsi; lpSubKey
0x18001794f  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180017954  mov     ebx, eax
0x180017956  test    eax, eax
0x180017958  jns     short loc_1800179B7
0x18001795a  mov     r8d, eax
0x18001795d  lea     rdx, aOpenFailed0x0x; "Open failed, 0x%0x."
0x180017964  mov     rcx, rdi; this
0x180017967  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x18001796c  mov     edi, 6C0h
0x180017971  test    eax, eax
0x180017973  jns     short loc_180017986
0x180017975  mov     rcx, [rbp+57h]; this
0x180017979  mov     r9d, eax; char *
0x18001797c  mov     r8, r12; unsigned int
0x18001797f  mov     edx, edi; void *
0x180017981  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017986  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x18001798d  jge     short loc_1800179A1
0x18001798f  mov     r9d, ebx
0x180017992  lea     rdx, AppxAllUserStoreOpenKeyError
0x180017999  mov     r8, rsi
0x18001799c  call    McTemplateU0zd_EventWriteTransfer
0x1800179a1  mov     rcx, [rbp+57h]; this
0x1800179a5  mov     r9d, ebx; char *
0x1800179a8  mov     r8, r12; unsigned int
0x1800179ab  mov     edx, edi; void *
0x1800179ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800179b2  jmp     loc_180017CAD
0x1800179b7  mov     rdx, [rbp+4Fh+phkResult]; hKey
0x1800179bb  lea     rsi, ?allUserApplicationsString@AppxAllUserStore@@3QBGB; "Applications"
0x1800179c2  mov     r8, rsi; lpSubKey
0x1800179c5  mov     [rbp+4Fh+arg_18], 0
0x1800179cd  mov     r9d, 20019h; samDesired
0x1800179d3  lea     rcx, [rbp+4Fh+arg_18]; phkResult
0x1800179d7  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x1800179dc  mov     ebx, eax
0x1800179de  test    eax, eax
0x1800179e0  jns     short loc_180017A4B
0x1800179e2  mov     r9d, eax
0x1800179e5  lea     rdx, aOpenDeletedLsF; "Open deleted\\%ls failed, 0x%0x."
0x1800179ec  mov     r8, rsi
0x1800179ef  mov     rcx, rdi; this
0x1800179f2  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800179f7  mov     edi, 6C8h
0x1800179fc  test    eax, eax
0x1800179fe  jns     short loc_180017A11
0x180017a00  mov     rcx, [rbp+57h]; this
0x180017a04  mov     r9d, eax; char *
0x180017a07  mov     r8, r12; unsigned int
0x180017a0a  mov     edx, edi; void *
0x180017a0c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017a11  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x180017a18  jge     short loc_180017A2C
0x180017a1a  mov     r9d, ebx
0x180017a1d  lea     rdx, AppxAllUserStoreOpenKeyError
0x180017a24  mov     r8, rsi
0x180017a27  call    McTemplateU0zd_EventWriteTransfer
0x180017a2c  mov     rcx, [rbp+57h]; this
0x180017a30  mov     r9d, ebx; char *
0x180017a33  mov     r8, r12; unsigned int
0x180017a36  mov     edx, edi; void *
0x180017a38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017a3d  lea     rcx, [rbp+4Fh+arg_18]; this
0x180017a41  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180017a46  jmp     loc_180017CAD
0x180017a4b  xor     eax, eax
0x180017a4d  lea     r8, [rbp+4Fh+lpSubKey]; bool
0x180017a51  xorps   xmm0, xmm0
0x180017a54  mov     [rbp+4Fh+var_98], eax
0x180017a57  xor     edx, edx; unsigned __int16 *
0x180017a59  mov     rcx, rsi; this
0x180017a5c  movups  xmmword ptr [rbp+4Fh+lpSubKey], xmm0
0x180017a60  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x180017a65  mov     ebx, eax
0x180017a67  test    eax, eax
0x180017a69  jns     short loc_180017AB3
0x180017a6b  mov     r8d, eax
0x180017a6e  lea     rdx, aGetalluserappl; "GetAllUserApplicationsPath failed, 0x%0"...
0x180017a75  mov     rcx, rdi; this
0x180017a78  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180017a7d  mov     edi, 6CDh
0x180017a82  test    eax, eax
0x180017a84  jns     short loc_180017A97
0x180017a86  mov     rcx, [rbp+57h]; this
0x180017a8a  mov     r9d, eax; char *
0x180017a8d  mov     r8, r12; unsigned int
0x180017a90  mov     edx, edi; void *
0x180017a92  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017a97  mov     rcx, [rbp+57h]; this
0x180017a9b  mov     r9d, ebx; char *
0x180017a9e  mov     r8, r12; unsigned int
0x180017aa1  mov     edx, edi; void *
0x180017aa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017aa8  lea     rcx, [rbp+4Fh+lpSubKey]; this
0x180017aac  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180017ab1  jmp     short loc_180017A3D
0x180017ab3  mov     rdx, [rbp+4Fh+arg_20]
0x180017ab7  lea     rcx, [rbp+4Fh+var_B0]; phkResult
0x180017abb  mov     r8, [rbp+4Fh+lpSubKey+8]; lpSubKey
0x180017abf  mov     r9d, 0F003Fh; samDesired
0x180017ac5  mov     [rbp+4Fh+var_B0], 0
0x180017acd  mov     rdx, [rdx]; hKey
0x180017ad0  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180017ad5  mov     ebx, eax
0x180017ad7  test    eax, eax
0x180017ad9  jns     short loc_180017B46
0x180017adb  mov     r8, [rbp+4Fh+lpSubKey+8]
0x180017adf  lea     rdx, aOpenLsFailed0x; "Open %ls failed, 0x%0x."
0x180017ae6  mov     r9d, eax
0x180017ae9  mov     rcx, rdi; this
0x180017aec  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180017af1  mov     edi, 6D3h
0x180017af6  test    eax, eax
0x180017af8  jns     short loc_180017B0B
0x180017afa  mov     rcx, [rbp+57h]; this
0x180017afe  mov     r9d, eax; char *
0x180017b01  mov     r8, r12; unsigned int
0x180017b04  mov     edx, edi; void *
0x180017b06  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017b0b  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x180017b12  jge     short loc_180017B27
0x180017b14  mov     r8, [rbp+4Fh+lpSubKey+8]
0x180017b18  lea     rdx, AppxAllUserStoreOpenKeyError
0x180017b1f  mov     r9d, ebx
0x180017b22  call    McTemplateU0zd_EventWriteTransfer
0x180017b27  mov     rcx, [rbp+57h]; this
0x180017b2b  mov     r9d, ebx; char *
0x180017b2e  mov     r8, r12; unsigned int
0x180017b31  mov     edx, edi; void *
0x180017b33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b38  lea     rcx, [rbp+4Fh+var_B0]; this
0x180017b3c  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180017b41  jmp     loc_180017AA8
0x180017b46  xor     eax, eax
0x180017b48  lea     rdx, [rbp+4Fh+var_88]; Common::Deployment::Configuration *
0x180017b4c  xorps   xmm0, xmm0
0x180017b4f  mov     [rbp+4Fh+var_78], eax
0x180017b52  mov     rcx, r14; this
0x180017b55  movups  xmmword ptr [rbp+4Fh+var_88], xmm0
0x180017b59  call    ?GetSystemSisPath@AppxAllUserStore@@YAJPEBGAEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetSystemSisPath(ushort const *,Common::StringBuffer &)
0x180017b5e  mov     ebx, eax
0x180017b60  test    eax, eax
0x180017b62  jns     short loc_180017BAC
0x180017b64  mov     r8d, eax
0x180017b67  lea     rdx, aGetsystemsispa_1; "GetSystemSisPath, 0x%0x."
0x180017b6e  mov     rcx, rdi; this
0x180017b71  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180017b76  mov     edi, 6D7h
0x180017b7b  test    eax, eax
0x180017b7d  jns     short loc_180017B90
0x180017b7f  mov     rcx, [rbp+57h]; this
0x180017b83  mov     r9d, eax; char *
0x180017b86  mov     r8, r12; unsigned int
0x180017b89  mov     edx, edi; void *
0x180017b8b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017b90  mov     edx, edi; void *
0x180017b92  mov     r9d, ebx; char *
0x180017b95  mov     rcx, [rbp+57h]; this
0x180017b99  mov     r8, r12; unsigned int
0x180017b9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ba1  lea     rcx, [rbp+4Fh+var_88]; this
0x180017ba5  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180017baa  jmp     short loc_180017B38
0x180017bac  lea     rcx, [rbp+4Fh+var_88]; struct Common::StringBuffer *
0x180017bb0  call    ?AddTrailingSlashIfNecessary@PathHelpers@Common@@SAJPEAVStringBuffer@2@@Z; Common::PathHelpers::AddTrailingSlashIfNecessary(Common::StringBuffer *)
0x180017bb5  mov     ebx, eax
0x180017bb7  test    eax, eax
0x180017bb9  jns     short loc_180017BC5
0x180017bbb  mov     r9d, eax
0x180017bbe  mov     edx, 6D8h
0x180017bc3  jmp     short loc_180017B95
0x180017bc5  lea     rax, [rbp+4Fh+var_88]
0x180017bc9  mov     rdx, rdi
0x180017bcc  lea     r9, [rbp+4Fh+var_B0]
0x180017bd0  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180017bd5  lea     r8, [rbp+4Fh+arg_18]
0x180017bd9  lea     rcx, [rbp+4Fh+var_50]
0x180017bdd  call    _lambda_e8ac0e144359e5e5f4b03267d2f650ae____lambda_e8ac0e144359e5e5f4b03267d2f650ae_
0x180017be2  lea     rdx, [rbp+4Fh+var_70]
0x180017be6  lea     rcx, [rbp+4Fh+arg_18]
0x180017bea  movups  xmm0, xmmword ptr [rax]
0x180017bed  movups  xmm1, xmmword ptr [rax+10h]
0x180017bf1  movaps  [rbp+4Fh+var_70], xmm0
0x180017bf5  movaps  [rbp+4Fh+var_60], xmm1
0x180017bf9  call    AppxAllUserStore__EnumKeyAndDoActionForAllSubkeys__lambda_bf31dbdb74ab162ca3e696a95a30df9c___
0x180017bfe  mov     r8d, eax
0x180017c01  lea     rdx, aEnumkeyanddoac_0; "EnumKeyAndDoActionForAllSubkeys, 0x%0x."
0x180017c08  mov     rcx, rdi; this
0x180017c0b  mov     ebx, eax
0x180017c0d  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180017c12  test    eax, eax
0x180017c14  jns     short loc_180017C2A
0x180017c16  mov     rcx, [rbp+57h]; this
0x180017c1a  mov     r9d, eax; char *
0x180017c1d  mov     r8, r12; unsigned int
0x180017c20  mov     edx, 6E8h; void *
0x180017c25  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017c2a  test    ebx, ebx
0x180017c2c  jns     short loc_180017C38
0x180017c2e  mov     edx, 6E9h
0x180017c33  jmp     loc_180017B92
0x180017c38  xor     edx, edx; unsigned __int16 *
0x180017c3a  lea     rcx, [rbp+4Fh+arg_18]; this
0x180017c3e  call    ?DeleteSubKeyTreeIfExists@RegistryKey@Common@@QEAAJPEBG@Z; Common::RegistryKey::DeleteSubKeyTreeIfExists(ushort const *)
0x180017c43  mov     ebx, eax
0x180017c45  test    eax, eax
0x180017c47  jns     short loc_180017C5D
0x180017c49  mov     rcx, [rbp+57h]; this
0x180017c4d  mov     r9d, eax; char *
0x180017c50  mov     r8, r12; unsigned int
0x180017c53  mov     edx, 6ECh; void *
0x180017c58  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017c5d  mov     r8d, ebx
0x180017c60  lea     rdx, aDeletesubkeytr; "DeleteSubKeyTreeIfExists 0x%0x."
0x180017c67  mov     rcx, rdi; this
0x180017c6a  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180017c6f  test    eax, eax
0x180017c71  jns     short loc_180017C87
0x180017c73  mov     rcx, [rbp+57h]; this
0x180017c77  mov     r9d, eax; char *
0x180017c7a  mov     r8, r12; unsigned int
0x180017c7d  mov     edx, 6EDh; void *
0x180017c82  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017c87  lea     rcx, [rbp+4Fh+var_88]; this
0x180017c8b  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180017c90  lea     rcx, [rbp+4Fh+var_B0]; this
0x180017c94  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180017c99  lea     rcx, [rbp+4Fh+lpSubKey]; this
0x180017c9d  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180017ca2  lea     rcx, [rbp+4Fh+arg_18]; this
0x180017ca6  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180017cab  xor     ebx, ebx
0x180017cad  lea     rcx, [rbp+4Fh+phkResult]; this
0x180017cb1  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180017cb6  mov     eax, ebx
0x180017cb8  add     rsp, 0B8h
0x180017cbf  pop     r14
0x180017cc1  pop     r12
0x180017cc3  pop     rdi
0x180017cc4  pop     rsi
0x180017cc5  pop     rbx
0x180017cc6  pop     rbp
0x180017cc7  retn
```
