# AppxAllUserStore::Internal::AddDeletedAllUserPackagesIfNeeded(AppxAllUserStore::BasicLogFile *,ushort const *,HKEY__ * const,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)

- ea: `0x180041198`
- end: `0x1800414bf`
- name: `?AddDeletedAllUserPackagesIfNeeded@Internal@AppxAllUserStore@@YAJPEAVBasicLogFile@2@PEBGQEAUHKEY__@@AEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@@Z`
- size: `807`
- prototype: `__int64 __fastcall(AppxAllUserStore::BasicLogFile *this, AppxAllUserStore::Internal *, HKEY, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004252c`

## callees

- `0x180002108`
- `0x180004920`
- `0x180004b4c`
- `0x180006d40`
- `0x18000ed34`
- `0x1800131f0`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x18001a6a0`
- `0x18001b3f0`
- `0x180021b64`
- `0x180041198`
- `0x180044624`
- `0x1800467fc`

## string_xrefs

- `0x1800411fe`: `Deleted`
- `0x1800411cc`: `In AddDeletedAllUserPackagesIfNeeded %ws.`
- `0x180041222`: `GetDeletedPath failed 0x%0x.`
- `0x1800412bf`: `Deleted key path %ws, root %ws.`
- `0x1800412f3`: `GetPackagesFromRegistryStoreInternal %ws got %u, 0x%0x.`
- `0x1800413e1`: `DeleteAllPackagesFromPackageArray %u: 0x%0x.`
- `0x18004143b`: `Apps key %ws deleted count %u array size %u.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::AddDeletedAllUserPackagesIfNeeded(
        AppxAllUserStore::BasicLogFile *this,
        AppxAllUserStore::Internal *a2,
        HKEY a3,
        unsigned int *a4)
{
  int v8; // eax
  int AllUserChildStorePath; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  int appended; // eax
  const char *v15; // rbx
  unsigned int PackagesFromRegistryStoreInternal; // eax
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // esi
  int v20; // eax
  unsigned int v21; // eax
  int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  int v25; // eax
  const struct _tlgProvider_t *v26; // rax
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned int *v30; // [rsp+20h] [rbp-50h]
  __int64 v31; // [rsp+20h] [rbp-50h]
  char *v32; // [rsp+28h] [rbp-48h]
  __int64 v33; // [rsp+30h] [rbp-40h]
  unsigned int v34; // [rsp+38h] [rbp-38h]
  __int64 v35; // [rsp+40h] [rbp-30h] BYREF
  AppxAllUserStore::Internal *v36; // [rsp+48h] [rbp-28h] BYREF
  struct HKEY__ v37[4]; // [rsp+50h] [rbp-20h] BYREF
  int v38; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  struct AppxAllUserStore::_PackageInfo *v40; // [rsp+A0h] [rbp+30h] BYREF

  if ( this )
  {
    v8 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"In AddDeletedAllUserPackagesIfNeeded %ws.", a2);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x42C,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)(unsigned int)v8);
  }
  v38 = 0;
  *(_OWORD *)&v37[0].unused = 0;
  AllUserChildStorePath = AppxAllUserStore::GetAllUserChildStorePath(
                            (AppxAllUserStore *)L"Deleted",
                            0,
                            (unsigned int *)v37,
                            (struct Common::StringBuffer *)a4);
  v10 = AllUserChildStorePath;
  if ( AllUserChildStorePath < 0 )
  {
    if ( this )
    {
      v11 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"GetDeletedPath failed 0x%0x.",
              (unsigned int)AllUserChildStorePath);
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x430,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)v11);
    }
    v12 = v10;
    v13 = 1072;
    goto LABEL_12;
  }
  appended = Common::PathHelpers::AppendPathSegment((struct Common::StringBuffer *)v37, L"Applications");
  v10 = appended;
  if ( appended < 0 )
  {
    v13 = 1073;
LABEL_11:
    v12 = (unsigned int)appended;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
      (const char *)v12,
      (int)v30);
    goto LABEL_33;
  }
  appended = Common::PathHelpers::AddTrailingSlashIfNecessary((struct Common::StringBuffer *)v37);
  v10 = appended;
  if ( appended < 0 )
  {
    v13 = 1077;
    goto LABEL_11;
  }
  v15 = *(const char **)&v37[2].unused;
  v35 = 0;
  LODWORD(v40) = 0;
  PackagesFromRegistryStoreInternal = AppxAllUserStore::GetPackagesFromRegistryStoreInternal(
                                        a3,
                                        v37,
                                        (struct Common::StringBuffer *)&v35,
                                        &v40,
                                        v30);
  v17 = wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x43B,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)PackagesFromRegistryStoreInternal,
          (__int64)"Deleted key path %ws, root %ws.",
          v15,
          a2);
  v18 = (unsigned int)v40;
  v19 = v17;
  if ( this )
  {
    LODWORD(v31) = v17;
    v20 = AppxAllUserStore::BasicLogFile::WriteMsg(
            this,
            L"GetPackagesFromRegistryStoreInternal %ws got %u, 0x%0x.",
            *(_QWORD *)&v37[2].unused,
            (unsigned int)v40,
            v31);
    if ( v20 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x43E,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)(unsigned int)v20);
  }
  if ( v19 >= 0 )
  {
    if ( v18 )
    {
      v21 = AppxAllUserStore::Internal::ProcessMainPackagesList(this, a2, v18, (__int64)&v35, (__int64)a4);
      v19 = v21;
      if ( this )
      {
        v22 = AppxAllUserStore::BasicLogFile::WriteMsg(
                this,
                L"ProcessMainPackagesList got %u folders, 0x%0x.",
                a4[4],
                v21);
        if ( v22 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x458,
            (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
            (const char *)(unsigned int)v22);
      }
      v23 = DeleteAllPackagesFromPackageArray(v18, &v35);
      LODWORD(v32) = v18;
      v24 = wil::details::in1diag3::Log_IfFailedMsg(
              retaddr,
              (void *)0x45C,
              (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)v23,
              (__int64)"Count %u.",
              v32);
      if ( this )
      {
        v25 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"DeleteAllPackagesFromPackageArray %u: 0x%0x.", v18, v24);
        if ( v25 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x45D,
            (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
            (const char *)(unsigned int)v25);
      }
      if ( v19 < 0 )
      {
        v34 = a4[4];
        LODWORD(v33) = v18;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x460,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)v19,
          (int)"Apps key %ws deleted count %u array size %u.",
          *(const char **)&v37[2].unused,
          v33,
          v34);
        goto LABEL_20;
      }
    }
  }
  else
  {
    v18 = 0;
    if ( (unsigned int)(v19 + 2147024894) > 1 )
    {
LABEL_20:
      v10 = v19;
      goto LABEL_33;
    }
  }
  v26 = AppxAllUserStoreTelemetry::Provider();
  if ( *(_DWORD *)v26 > 5u )
  {
    v40 = (struct AppxAllUserStore::_PackageInfo *)v18;
    v35 = *(_QWORD *)&v37[2].unused;
    v36 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      (__int64)v26,
      (__int64)&word_18005D42E,
      v27,
      v28,
      (const unsigned __int16 **)&v36,
      (const unsigned __int16 **)&v35,
      (__int64)&v40);
  }
  v10 = 0;
LABEL_33:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v37);
  return v10;
}

```

## disassembly

```asm
0x180041198  mov     [rsp-28h+arg_8], rbx
0x18004119d  mov     [rsp-28h+arg_10], rsi
0x1800411a2  push    rbp
0x1800411a3  push    rdi
0x1800411a4  push    r12
0x1800411a6  push    r14
0x1800411a8  push    r15
0x1800411aa  mov     rbp, rsp
0x1800411ad  sub     rsp, 70h
0x1800411b1  lea     rsi, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800411b8  mov     r15, r9
0x1800411bb  mov     r12, r8
0x1800411be  mov     r14, rdx
0x1800411c1  mov     rdi, rcx
0x1800411c4  test    rcx, rcx
0x1800411c7  jz      short loc_1800411F0
0x1800411c9  mov     r8, rdx
0x1800411cc  lea     rdx, aInAdddeletedal; "In AddDeletedAllUserPackagesIfNeeded %w"...
0x1800411d3  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800411d8  test    eax, eax
0x1800411da  jns     short loc_1800411F0
0x1800411dc  mov     rcx, [rbp+28h]; this
0x1800411e0  mov     r9d, eax; char *
0x1800411e3  mov     r8, rsi; unsigned int
0x1800411e6  mov     edx, 42Ch; void *
0x1800411eb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800411f0  xor     eax, eax
0x1800411f2  lea     r8, [rbp+var_20]; bool
0x1800411f6  xorps   xmm0, xmm0
0x1800411f9  mov     [rbp+var_10], eax
0x1800411fc  xor     edx, edx; unsigned __int16 *
0x1800411fe  lea     rcx, ?deletedApplicationsString@AppxAllUserStore@@3QBGB; "Deleted"
0x180041205  movups  xmmword ptr [rbp+var_20.unused], xmm0
0x180041209  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x18004120e  mov     ebx, eax
0x180041210  test    eax, eax
0x180041212  jns     short loc_18004124F
0x180041214  mov     r14d, 430h
0x18004121a  test    rdi, rdi
0x18004121d  jz      short loc_180041247
0x18004121f  mov     r8d, eax
0x180041222  lea     rdx, aGetdeletedpath_0; "GetDeletedPath failed 0x%0x."
0x180041229  mov     rcx, rdi; this
0x18004122c  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180041231  test    eax, eax
0x180041233  jns     short loc_180041247
0x180041235  mov     rcx, [rbp+28h]; this
0x180041239  mov     r9d, eax; char *
0x18004123c  mov     r8, rsi; unsigned int
0x18004123f  mov     edx, r14d; void *
0x180041242  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041247  mov     r9d, ebx
0x18004124a  mov     edx, r14d
0x18004124d  jmp     short loc_18004126D
0x18004124f  lea     rdx, ?allUserApplicationsString@AppxAllUserStore@@3QBGB; "Applications"
0x180041256  lea     rcx, [rbp+var_20]; struct Common::StringBuffer *
0x18004125a  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBuffer@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBuffer *,ushort const *)
0x18004125f  mov     ebx, eax
0x180041261  test    eax, eax
0x180041263  jns     short loc_18004127E
0x180041265  mov     edx, 431h; void *
0x18004126a  mov     r9d, eax; char *
0x18004126d  mov     rcx, [rbp+28h]; this
0x180041271  mov     r8, rsi; unsigned int
0x180041274  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041279  jmp     loc_18004149B
0x18004127e  lea     rcx, [rbp+var_20]; struct Common::StringBuffer *
0x180041282  call    ?AddTrailingSlashIfNecessary@PathHelpers@Common@@SAJPEAVStringBuffer@2@@Z; Common::PathHelpers::AddTrailingSlashIfNecessary(Common::StringBuffer *)
0x180041287  mov     ebx, eax
0x180041289  test    eax, eax
0x18004128b  jns     short loc_180041294
0x18004128d  mov     edx, 435h
0x180041292  jmp     short loc_18004126A
0x180041294  mov     rbx, qword ptr [rbp+var_20.unused+8]
0x180041298  lea     r9, [rbp+arg_0]; struct AppxAllUserStore::_PackageInfo **
0x18004129c  lea     r8, [rbp+var_30]; struct Common::StringBuffer *
0x1800412a0  mov     [rbp+var_30], 0
0x1800412a8  lea     rdx, [rbp+var_20]; HKEY
0x1800412ac  mov     dword ptr [rbp+arg_0], 0
0x1800412b3  mov     rcx, r12; hKey
0x1800412b6  call    ?GetPackagesFromRegistryStoreInternal@AppxAllUserStore@@YAJQEAUHKEY__@@PEAVStringBuffer@Common@@PEAPEAU_PackageInfo@1@PEAI@Z; AppxAllUserStore::GetPackagesFromRegistryStoreInternal(HKEY__ * const,Common::StringBuffer *,AppxAllUserStore::_PackageInfo * *,uint *)
0x1800412bb  mov     rcx, [rbp+28h]; this
0x1800412bf  lea     rdx, aDeletedKeyPath; "Deleted key path %ws, root %ws."
0x1800412c6  mov     [rsp+70h+var_40], r14
0x1800412cb  mov     r9d, eax; char *
0x1800412ce  mov     [rsp+70h+var_48], rbx; char *
0x1800412d3  mov     r8, rsi; unsigned int
0x1800412d6  mov     [rsp+70h+var_50], rdx; __int64
0x1800412db  mov     edx, 43Bh; void *
0x1800412e0  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800412e5  mov     ebx, dword ptr [rbp+arg_0]
0x1800412e8  mov     esi, eax
0x1800412ea  test    rdi, rdi
0x1800412ed  jz      short loc_180041325
0x1800412ef  mov     r8, qword ptr [rbp+var_20.unused+8]
0x1800412f3  lea     rdx, aGetpackagesfro; "GetPackagesFromRegistryStoreInternal %w"...
0x1800412fa  mov     r9d, ebx
0x1800412fd  mov     dword ptr [rsp+70h+var_50], eax; int
0x180041301  mov     rcx, rdi; this
0x180041304  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180041309  test    eax, eax
0x18004130b  jns     short loc_180041325
0x18004130d  mov     rcx, [rbp+28h]; this
0x180041311  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180041318  mov     r9d, eax; char *
0x18004131b  mov     edx, 43Eh; void *
0x180041320  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041325  test    esi, esi
0x180041327  jns     short loc_180041341
0x180041329  xor     ebx, ebx
0x18004132b  lea     eax, [rsi+7FF8FFFEh]
0x180041331  cmp     eax, 1
0x180041334  jbe     loc_180041451
0x18004133a  mov     ebx, esi
0x18004133c  jmp     loc_18004149B
0x180041341  test    ebx, ebx
0x180041343  jz      loc_180041451
0x180041349  lea     rax, [rbp+var_30]
0x18004134d  mov     [rsp+70h+var_40], r15; __int64
0x180041352  mov     [rsp+70h+var_48], rax; __int64
0x180041357  lea     r9, [rbp+var_20]
0x18004135b  mov     r8, r12
0x18004135e  mov     dword ptr [rsp+70h+var_50], ebx; int
0x180041362  mov     rdx, r14; AppxAllUserStore::Internal *
0x180041365  mov     rcx, rdi; this
0x180041368  call    ?ProcessMainPackagesList@Internal@AppxAllUserStore@@YAJPEAVBasicLogFile@2@PEBGQEAUHKEY__@@PEBVStringBuffer@Common@@IPEAPEAU_PackageInfo@2@AEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@6@@Z; AppxAllUserStore::Internal::ProcessMainPackagesList(AppxAllUserStore::BasicLogFile *,ushort const *,HKEY__ * const,Common::StringBuffer const *,uint,AppxAllUserStore::_PackageInfo * *,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)
0x18004136d  mov     esi, eax
0x18004136f  test    rdi, rdi
0x180041372  jz      short loc_1800413A6
0x180041374  mov     r8d, [r15+10h]
0x180041378  lea     rdx, aProcessmainpac; "ProcessMainPackagesList got %u folders,"...
0x18004137f  mov     r9d, eax
0x180041382  mov     rcx, rdi; this
0x180041385  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x18004138a  test    eax, eax
0x18004138c  jns     short loc_1800413A6
0x18004138e  mov     rcx, [rbp+28h]; this
0x180041392  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180041399  mov     r9d, eax; char *
0x18004139c  mov     edx, 458h; void *
0x1800413a1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800413a6  lea     rdx, [rbp+var_30]
0x1800413aa  mov     ecx, ebx
0x1800413ac  call    DeleteAllPackagesFromPackageArray
0x1800413b1  mov     rcx, [rbp+28h]; this
0x1800413b5  lea     rdx, aCountU; "Count %u."
0x1800413bc  mov     dword ptr [rsp+70h+var_48], ebx; char *
0x1800413c0  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800413c7  mov     [rsp+70h+var_50], rdx; int
0x1800413cc  mov     r9d, eax; char *
0x1800413cf  mov     edx, 45Ch; void *
0x1800413d4  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800413d9  test    rdi, rdi
0x1800413dc  jz      short loc_18004140F
0x1800413de  mov     r9d, eax
0x1800413e1  lea     rdx, aDeleteallpacka_1; "DeleteAllPackagesFromPackageArray %u: 0"...
0x1800413e8  mov     r8d, ebx
0x1800413eb  mov     rcx, rdi; this
0x1800413ee  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800413f3  test    eax, eax
0x1800413f5  jns     short loc_18004140F
0x1800413f7  mov     rcx, [rbp+28h]; this
0x1800413fb  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180041402  mov     r9d, eax; char *
0x180041405  mov     edx, 45Dh; void *
0x18004140a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004140f  test    esi, esi
0x180041411  jns     short loc_180041451
0x180041413  mov     eax, [r15+10h]
0x180041417  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x18004141e  mov     rcx, [rbp+28h]; this
0x180041422  mov     r9d, esi; char *
0x180041425  mov     [rsp+70h+var_38], eax
0x180041429  mov     edx, 460h; void *
0x18004142e  mov     rax, qword ptr [rbp+var_20.unused+8]
0x180041432  mov     dword ptr [rsp+70h+var_40], ebx
0x180041436  mov     [rsp+70h+var_48], rax; char *
0x18004143b  lea     rax, aAppsKeyWsDelet; "Apps key %ws deleted count %u array siz"...
0x180041442  mov     [rsp+70h+var_50], rax; int
0x180041447  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004144c  jmp     loc_18004133A
0x180041451  call    ?Provider@AppxAllUserStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppxAllUserStoreTelemetry::Provider(void)
0x180041456  mov     ecx, [rax]
0x180041458  cmp     ecx, 5
0x18004145b  jbe     short loc_180041499
0x18004145d  mov     ecx, ebx
0x18004145f  lea     rdx, word_18005D42E
0x180041466  mov     [rbp+arg_0], rcx
0x18004146a  mov     rcx, qword ptr [rbp+var_20.unused+8]
0x18004146e  mov     [rbp+var_30], rcx
0x180041472  lea     rcx, [rbp+arg_0]
0x180041476  mov     [rsp+70h+var_40], rcx
0x18004147b  lea     rcx, [rbp+var_30]
0x18004147f  mov     [rsp+70h+var_48], rcx
0x180041484  lea     rcx, [rbp+var_28]
0x180041488  mov     [rsp+70h+var_50], rcx
0x18004148d  mov     rcx, rax
0x180041490  mov     [rbp+var_28], r14
0x180041494  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180041499  xor     ebx, ebx
0x18004149b  lea     rcx, [rbp+var_20]; this
0x18004149f  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800414a4  lea     r11, [rsp+70h+var_s0]
0x1800414a9  mov     eax, ebx
0x1800414ab  mov     rbx, [r11+38h]
0x1800414af  mov     rsi, [r11+40h]
0x1800414b3  mov     rsp, r11
0x1800414b6  pop     r15
0x1800414b8  pop     r14
0x1800414ba  pop     r12
0x1800414bc  pop     rdi
0x1800414bd  pop     rbp
0x1800414be  retn
```
