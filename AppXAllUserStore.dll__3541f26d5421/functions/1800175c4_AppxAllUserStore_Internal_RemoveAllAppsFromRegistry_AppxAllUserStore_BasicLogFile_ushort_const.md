# AppxAllUserStore::Internal::RemoveAllAppsFromRegistry(AppxAllUserStore::BasicLogFile &,ushort const *)

- ea: `0x1800175c4`
- end: `0x1800178e0`
- name: `?RemoveAllAppsFromRegistry@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG@Z`
- size: `796`
- prototype: `__int64 __fastcall(AppxAllUserStore::Internal *__hidden this, struct AppxAllUserStore::BasicLogFile *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180016878`

## callees

- `0x180002b1c`
- `0x180004920`
- `0x180004968`
- `0x180006d40`
- `0x18000d6a0`
- `0x1800175c4`
- `0x180017cd0`
- `0x180017f18`
- `0x180017f50`
- `0x180018248`
- `0x1800334f4`

## string_xrefs

- `0x1800176b4`: `GetAllUserApplicationsPath failed, 0x%0x.`
- `0x18001784e`: `DeleteTree Staged key 0x%0x.`
- `0x18001786b`: `Open staged key at target failed, 0x%0x.`
- `0x180017747`: `DeleteTree Applications key 0x%0x.`
- `0x1800175dd`: `In RemoveAllAppsFromRegistry %ls.`
- `0x18001764e`: `LoadSoftwareHiveAndOpenKeyForSystemRoot dst failed, 0x%0x.`
- `0x1800177b2`: `GetStagedApplicationsPath failed, 0x%0x.`
- `0x180017764`: `Open applications key at target failed, 0x%0x.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::RemoveAllAppsFromRegistry(
        AppxAllUserStore::Internal *this,
        struct AppxAllUserStore::BasicLogFile *a2,
        const unsigned __int16 *a3)
{
  int v5; // eax
  int v6; // eax
  struct Common::StringBuffer *v7; // r9
  unsigned int v8; // ebx
  int v9; // eax
  int AllUserChildStorePath; // eax
  int v11; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  struct Common::StringBuffer *v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  int v19; // eax
  LSTATUS v20; // eax
  LSTATUS v21; // eax
  unsigned int v22; // ebx
  int v23; // eax
  __int64 v24; // rdx
  int v26; // [rsp+20h] [rbp-60h]
  HKEY v27; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v28[4]; // [rsp+38h] [rbp-48h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+48h] [rbp-38h] BYREF
  int v30; // [rsp+58h] [rbp-28h]
  LPCWSTR v31[2]; // [rsp+60h] [rbp-20h] BYREF
  int v32; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  HKEY phkResult; // [rsp+B0h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+38h] BYREF

  v5 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"In RemoveAllAppsFromRegistry %ls.", a2);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x975,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v5);
  hKey = 0;
  *(_OWORD *)v28 = 0;
  v6 = AppxAllUserStore::Internal::LoadSoftwareHiveAndOpenKeyForSystemRoot(
         this,
         a2,
         L"APPX_HIVE_RESTORE_DST_ALIAS_SOFTWARE",
         0xF003Fu,
         (unsigned int)v28,
         &hKey,
         (struct Common::RegistryKey *)v27);
  v8 = v6;
  if ( v6 >= 0 )
  {
    v30 = 0;
    *(_OWORD *)lpSubKey = 0;
    AllUserChildStorePath = AppxAllUserStore::GetAllUserChildStorePath(
                              (AppxAllUserStore *)L"Applications",
                              0,
                              (unsigned int *)lpSubKey,
                              v7);
    v8 = AllUserChildStorePath;
    if ( AllUserChildStorePath < 0 )
    {
      v11 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"GetAllUserApplicationsPath failed, 0x%0x.",
              (unsigned int)AllUserChildStorePath);
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x98A,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v11);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x98A,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)v8,
        v26);
LABEL_11:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
      goto LABEL_33;
    }
    phkResult = 0;
    v12 = Common::RegistryKey::Open(&phkResult, hKey, lpSubKey[1], 0xF003Fu);
    if ( v12 < 0 )
    {
      v15 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"Open applications key at target failed, 0x%0x.",
              (unsigned int)v12);
      if ( v15 >= 0 )
        goto LABEL_20;
      v17 = 2452;
    }
    else
    {
      v13 = Common::RegistryKey::DeleteSubKeyTree(&phkResult, 0);
      v14 = v13;
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x98F,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v13);
      v15 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"DeleteTree Applications key 0x%0x.", v14);
      if ( v15 >= 0 )
      {
LABEL_20:
        v32 = 0;
        *(_OWORD *)v31 = 0;
        v18 = AppxAllUserStore::GetAllUserChildStorePath((AppxAllUserStore *)L"Staged", 0, (unsigned int *)v31, v16);
        v8 = v18;
        if ( v18 < 0 )
        {
          v19 = AppxAllUserStore::BasicLogFile::WriteMsg(
                  this,
                  L"GetStagedApplicationsPath failed, 0x%0x.",
                  (unsigned int)v18);
          if ( v19 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x999,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
              (const char *)(unsigned int)v19);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x999,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)v8,
            v26);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v31);
          Common::RegistryKey::~RegistryKey(&phkResult);
          goto LABEL_11;
        }
        v27 = 0;
        v20 = Common::RegistryKey::Open(&v27, hKey, v31[1], 0xF003Fu);
        if ( v20 < 0 )
        {
          v23 = AppxAllUserStore::BasicLogFile::WriteMsg(
                  this,
                  L"Open staged key at target failed, 0x%0x.",
                  (unsigned int)v20);
          if ( v23 >= 0 )
          {
LABEL_32:
            Common::RegistryKey::~RegistryKey(&v27);
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v31);
            Common::RegistryKey::~RegistryKey(&phkResult);
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
            v8 = 0;
            goto LABEL_33;
          }
          v24 = 2468;
        }
        else
        {
          v21 = Common::RegistryKey::DeleteSubKeyTree(&v27, 0);
          v22 = v21;
          if ( v21 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x99F,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
              (const char *)(unsigned int)v21);
          v23 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"DeleteTree Staged key 0x%0x.", v22);
          if ( v23 >= 0 )
            goto LABEL_32;
          v24 = 2464;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v24,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v23);
        goto LABEL_32;
      }
      v17 = 2448;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v17,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v15);
    goto LABEL_20;
  }
  v9 = AppxAllUserStore::BasicLogFile::WriteMsg(
         this,
         L"LoadSoftwareHiveAndOpenKeyForSystemRoot dst failed, 0x%0x.",
         (unsigned int)v6);
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x986,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v9);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x986,
    (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
    (const char *)v8,
    v26);
LABEL_33:
  Common::RegistryKey::~RegistryKey(&hKey);
  AppxAllUserStore::AutoRegLoadHive::~AutoRegLoadHive((AppxAllUserStore::AutoRegLoadHive *)v28);
  return v8;
}

```

## disassembly

```asm
0x1800175c4  mov     [rsp-18h+arg_0], rbx
0x1800175c9  push    rbp
0x1800175ca  push    rdi
0x1800175cb  push    r14
0x1800175cd  mov     rbp, rsp
0x1800175d0  sub     rsp, 80h
0x1800175d7  mov     rbx, rdx
0x1800175da  mov     r8, rdx
0x1800175dd  lea     rdx, aInRemoveallapp; "In RemoveAllAppsFromRegistry %ls."
0x1800175e4  mov     rdi, rcx
0x1800175e7  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800175ec  lea     r14, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800175f3  test    eax, eax
0x1800175f5  jns     short loc_18001760B
0x1800175f7  mov     rcx, [rbp+18h]; this
0x1800175fb  mov     r9d, eax; char *
0x1800175fe  mov     r8, r14; unsigned int
0x180017601  mov     edx, 975h; void *
0x180017606  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001760b  lea     rax, [rbp+hKey]
0x18001760f  mov     [rbp+hKey], 0
0x180017617  mov     [rsp+80h+var_58], rax; phkResult
0x18001761c  lea     r8, aAppxHiveRestor_0; "APPX_HIVE_RESTORE_DST_ALIAS_SOFTWARE"
0x180017623  lea     rax, [rbp+var_48]
0x180017627  xorps   xmm0, xmm0
0x18001762a  mov     r9d, 0F003Fh; samDesired
0x180017630  mov     qword ptr [rsp+80h+var_60], rax; int
0x180017635  mov     rdx, rbx; struct AppxAllUserStore::BasicLogFile *
0x180017638  mov     rcx, rdi; this
0x18001763b  movdqu  xmmword ptr [rbp+var_48], xmm0
0x180017640  call    ?LoadSoftwareHiveAndOpenKeyForSystemRoot@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG1KAEAVAutoRegLoadHive@2@AEAVRegistryKey@Common@@@Z; AppxAllUserStore::Internal::LoadSoftwareHiveAndOpenKeyForSystemRoot(AppxAllUserStore::BasicLogFile &,ushort const *,ushort const *,ulong,AppxAllUserStore::AutoRegLoadHive &,Common::RegistryKey &)
0x180017645  mov     ebx, eax
0x180017647  test    eax, eax
0x180017649  jns     short loc_18001768D
0x18001764b  mov     r8d, eax
0x18001764e  lea     rdx, aLoadsoftwarehi_0; "LoadSoftwareHiveAndOpenKeyForSystemRoot"...
0x180017655  mov     rcx, rdi; this
0x180017658  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x18001765d  mov     edi, 986h
0x180017662  test    eax, eax
0x180017664  jns     short loc_180017677
0x180017666  mov     rcx, [rbp+18h]; this
0x18001766a  mov     r9d, eax; char *
0x18001766d  mov     r8, r14; unsigned int
0x180017670  mov     edx, edi; void *
0x180017672  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017677  mov     rcx, [rbp+18h]; this
0x18001767b  mov     r9d, ebx; char *
0x18001767e  mov     r8, r14; unsigned int
0x180017681  mov     edx, edi; void *
0x180017683  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017688  jmp     loc_1800178B8
0x18001768d  xor     eax, eax
0x18001768f  lea     r8, [rbp+lpSubKey]; bool
0x180017693  xorps   xmm0, xmm0
0x180017696  mov     [rbp+var_28], eax
0x180017699  xor     edx, edx; unsigned __int16 *
0x18001769b  lea     rcx, ?allUserApplicationsString@AppxAllUserStore@@3QBGB; "Applications"
0x1800176a2  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x1800176a6  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x1800176ab  mov     ebx, eax
0x1800176ad  test    eax, eax
0x1800176af  jns     short loc_1800176FC
0x1800176b1  mov     r8d, eax
0x1800176b4  lea     rdx, aGetalluserappl; "GetAllUserApplicationsPath failed, 0x%0"...
0x1800176bb  mov     rcx, rdi; this
0x1800176be  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800176c3  mov     edi, 98Ah
0x1800176c8  test    eax, eax
0x1800176ca  jns     short loc_1800176DD
0x1800176cc  mov     rcx, [rbp+18h]; this
0x1800176d0  mov     r9d, eax; char *
0x1800176d3  mov     r8, r14; unsigned int
0x1800176d6  mov     edx, edi; void *
0x1800176d8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800176dd  mov     rcx, [rbp+18h]; this
0x1800176e1  mov     r9d, ebx; char *
0x1800176e4  mov     r8, r14; unsigned int
0x1800176e7  mov     edx, edi; void *
0x1800176e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800176ee  lea     rcx, [rbp+lpSubKey]; this
0x1800176f2  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800176f7  jmp     loc_1800178B8
0x1800176fc  mov     r8, [rbp+lpSubKey+8]; lpSubKey
0x180017700  lea     rcx, [rbp+phkResult]; phkResult
0x180017704  mov     rdx, [rbp+hKey]; hKey
0x180017708  mov     r9d, 0F003Fh; samDesired
0x18001770e  mov     [rbp+phkResult], 0
0x180017716  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18001771b  test    eax, eax
0x18001771d  js      short loc_180017761
0x18001771f  xor     edx, edx; unsigned __int16 *
0x180017721  lea     rcx, [rbp+phkResult]; this
0x180017725  call    ?DeleteSubKeyTree@RegistryKey@Common@@QEAAJPEBG@Z; Common::RegistryKey::DeleteSubKeyTree(ushort const *)
0x18001772a  mov     ebx, eax
0x18001772c  test    eax, eax
0x18001772e  jns     short loc_180017744
0x180017730  mov     rcx, [rbp+18h]; this
0x180017734  mov     r9d, eax; char *
0x180017737  mov     r8, r14; unsigned int
0x18001773a  mov     edx, 98Fh; void *
0x18001773f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017744  mov     r8d, ebx
0x180017747  lea     rdx, aDeletetreeAppl; "DeleteTree Applications key 0x%0x."
0x18001774e  mov     rcx, rdi; this
0x180017751  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180017756  test    eax, eax
0x180017758  jns     short loc_18001778B
0x18001775a  mov     edx, 990h
0x18001775f  jmp     short loc_18001777C
0x180017761  mov     r8d, eax
0x180017764  lea     rdx, aOpenApplicatio; "Open applications key at target failed,"...
0x18001776b  mov     rcx, rdi; this
0x18001776e  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180017773  test    eax, eax
0x180017775  jns     short loc_18001778B
0x180017777  mov     edx, 994h; void *
0x18001777c  mov     rcx, [rbp+18h]; this
0x180017780  mov     r9d, eax; char *
0x180017783  mov     r8, r14; unsigned int
0x180017786  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001778b  xor     eax, eax
0x18001778d  lea     r8, [rbp+var_20]; bool
0x180017791  xorps   xmm0, xmm0
0x180017794  mov     [rbp+var_10], eax
0x180017797  xor     edx, edx; unsigned __int16 *
0x180017799  lea     rcx, ?stagedApplicationsString@AppxAllUserStore@@3QBGB; "Staged"
0x1800177a0  movups  xmmword ptr [rbp+var_20], xmm0
0x1800177a4  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x1800177a9  mov     ebx, eax
0x1800177ab  test    eax, eax
0x1800177ad  jns     short loc_180017803
0x1800177af  mov     r8d, eax
0x1800177b2  lea     rdx, aGetstagedappli; "GetStagedApplicationsPath failed, 0x%0x"...
0x1800177b9  mov     rcx, rdi; this
0x1800177bc  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800177c1  mov     edi, 999h
0x1800177c6  test    eax, eax
0x1800177c8  jns     short loc_1800177DB
0x1800177ca  mov     rcx, [rbp+18h]; this
0x1800177ce  mov     r9d, eax; char *
0x1800177d1  mov     r8, r14; unsigned int
0x1800177d4  mov     edx, edi; void *
0x1800177d6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800177db  mov     rcx, [rbp+18h]; this
0x1800177df  mov     r9d, ebx; char *
0x1800177e2  mov     r8, r14; unsigned int
0x1800177e5  mov     edx, edi; void *
0x1800177e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800177ec  lea     rcx, [rbp+var_20]; this
0x1800177f0  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800177f5  lea     rcx, [rbp+phkResult]; this
0x1800177f9  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800177fe  jmp     loc_1800176EE
0x180017803  mov     r8, [rbp+var_20+8]; lpSubKey
0x180017807  lea     rcx, [rbp+var_50]; phkResult
0x18001780b  mov     rdx, [rbp+hKey]; hKey
0x18001780f  mov     r9d, 0F003Fh; samDesired
0x180017815  mov     [rbp+var_50], 0
0x18001781d  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180017822  test    eax, eax
0x180017824  js      short loc_180017868
0x180017826  xor     edx, edx; unsigned __int16 *
0x180017828  lea     rcx, [rbp+var_50]; this
0x18001782c  call    ?DeleteSubKeyTree@RegistryKey@Common@@QEAAJPEBG@Z; Common::RegistryKey::DeleteSubKeyTree(ushort const *)
0x180017831  mov     ebx, eax
0x180017833  test    eax, eax
0x180017835  jns     short loc_18001784B
0x180017837  mov     rcx, [rbp+18h]; this
0x18001783b  mov     r9d, eax; char *
0x18001783e  mov     r8, r14; unsigned int
0x180017841  mov     edx, 99Fh; void *
0x180017846  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001784b  mov     r8d, ebx
0x18001784e  lea     rdx, aDeletetreeStag; "DeleteTree Staged key 0x%0x."
0x180017855  mov     rcx, rdi; this
0x180017858  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x18001785d  test    eax, eax
0x18001785f  jns     short loc_180017892
0x180017861  mov     edx, 9A0h
0x180017866  jmp     short loc_180017883
0x180017868  mov     r8d, eax
0x18001786b  lea     rdx, aOpenStagedKeyA; "Open staged key at target failed, 0x%0x"...
0x180017872  mov     rcx, rdi; this
0x180017875  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x18001787a  test    eax, eax
0x18001787c  jns     short loc_180017892
0x18001787e  mov     edx, 9A4h; void *
0x180017883  mov     rcx, [rbp+18h]; this
0x180017887  mov     r9d, eax; char *
0x18001788a  mov     r8, r14; unsigned int
0x18001788d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017892  lea     rcx, [rbp+var_50]; this
0x180017896  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18001789b  lea     rcx, [rbp+var_20]; this
0x18001789f  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800178a4  lea     rcx, [rbp+phkResult]; this
0x1800178a8  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800178ad  lea     rcx, [rbp+lpSubKey]; this
0x1800178b1  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800178b6  xor     ebx, ebx
0x1800178b8  lea     rcx, [rbp+hKey]; this
0x1800178bc  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800178c1  lea     rcx, [rbp+var_48]; this
0x1800178c5  call    ??1AutoRegLoadHive@AppxAllUserStore@@QEAA@XZ; AppxAllUserStore::AutoRegLoadHive::~AutoRegLoadHive(void)
0x1800178ca  mov     eax, ebx
0x1800178cc  mov     rbx, [rsp+80h+arg_0]
0x1800178d4  add     rsp, 80h
0x1800178db  pop     r14
0x1800178dd  pop     rdi
0x1800178de  pop     rbp
0x1800178df  retn
```
