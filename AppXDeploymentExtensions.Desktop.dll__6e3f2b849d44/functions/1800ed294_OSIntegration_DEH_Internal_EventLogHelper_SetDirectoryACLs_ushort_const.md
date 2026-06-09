# OSIntegration::DEH::Internal::EventLogHelper::SetDirectoryACLs(ushort const *)

- ea: `0x1800ed294`
- end: `0x1800ed629`
- name: `?SetDirectoryACLs@EventLogHelper@Internal@DEH@OSIntegration@@AEAAJPEBG@Z`
- size: `917`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::EventLogHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18008b854`

## callees

- `0x180005e08`
- `0x180009dc0`
- `0x180018f88`
- `0x18001adb4`
- `0x18008ab30`
- `0x180098514`
- `0x1800af1bc`
- `0x1800ed294`
- `0x180173890`
- `0x1801749bc`
- `0x18017e74c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ed457`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ed539`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ed5ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ed457`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ed539`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ed5ba`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800ed43d`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800ed51f`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800ed5a0`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800ed43d`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800ed51f`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800ed5a0`
- `ADVAPI32!RevertToSelf` at `0x1800ed46d`
- `ADVAPI32!RevertToSelf` at `0x1800ed57b`
- `ADVAPI32!RevertToSelf` at `0x1800ed612`
- `ADVAPI32!RevertToSelf` at `0x1800ed46d`
- `ADVAPI32!RevertToSelf` at `0x1800ed57b`
- `ADVAPI32!RevertToSelf` at `0x1800ed612`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OSIntegration::DEH::Internal::EventLogHelper::SetDirectoryACLs(
        OSIntegration::DEH::Internal::EventLogHelper *this,
        const unsigned __int16 *a2)
{
  int v2; // r14d
  __int64 v4; // rsi
  __int64 v5; // rdx
  int v6; // eax
  int PackageSid; // ebx
  __int64 v8; // rdx
  const struct std::nothrow_t *v9; // rdx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  void *v14; // rdi
  void *v15; // rbx
  int v16; // esi
  const struct std::nothrow_t *v17; // rdx
  const struct std::nothrow_t *v18; // rdx
  int v19; // [rsp+20h] [rbp-79h]
  int v20; // [rsp+20h] [rbp-79h]
  _BYTE v21[8]; // [rsp+40h] [rbp-59h] BYREF
  HANDLE hToken; // [rsp+48h] [rbp-51h]
  void *v23[2]; // [rsp+50h] [rbp-49h] BYREF
  int v24; // [rsp+60h] [rbp-39h]
  void *v25[2]; // [rsp+68h] [rbp-31h] BYREF
  int v26; // [rsp+78h] [rbp-21h]
  void *v27[2]; // [rsp+80h] [rbp-19h] BYREF
  int v28; // [rsp+90h] [rbp-9h]
  int v29[2]; // [rsp+98h] [rbp-1h] BYREF
  void *v30; // [rsp+A0h] [rbp+7h] BYREF
  _QWORD v31[3]; // [rsp+A8h] [rbp+Fh] BYREF
  char v32; // [rsp+C0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  PSID pSid; // [rsp+100h] [rbp+67h] BYREF
  PSID Sid; // [rsp+110h] [rbp+77h] BYREF
  __int64 v36; // [rsp+118h] [rbp+7Fh] BYREF

  v2 = (int)a2;
  v4 = 3;
  v5 = *((_QWORD *)this + 3);
  v6 = *(_DWORD *)(v5 + 384);
  if ( (v6 & 1) != 0 )
    v4 = 7;
  if ( (v6 & 0x100) == 0 )
    v4 |= 8uLL;
  pSid = 0;
  Sid = 0;
  *(_OWORD *)v23 = 0;
  v24 = 0;
  PackageSid = Common::StringBuffer::SetValueFromString(
                 (Common::StringBuffer *)v23,
                 *(const unsigned __int16 **)(v5 + 248));
  if ( PackageSid < 0 )
  {
    v8 = 186;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\eventlog\\eventloghelper.cpp",
      (const char *)(unsigned int)PackageSid,
      v19);
LABEL_8:
    if ( v23[1] )
      operator delete(v23[1], v9);
    return (unsigned int)PackageSid;
  }
  PackageSid = Common::Deployment::PackageInfo::GetPackageSid(
                 (const struct Common::COMMON_STRING *)v23,
                 *(struct PackageRepository::IRepositorySession **)(*((_QWORD *)this + 3) + 48LL),
                 &pSid);
  if ( PackageSid < 0 )
  {
    v8 = 192;
    goto LABEL_7;
  }
  PackageSid = PackageSid::PackageSidToPackageCapabilitySid(pSid, &Sid);
  if ( PackageSid < 0 )
  {
    v8 = 197;
    goto LABEL_7;
  }
  *(_OWORD *)v25 = 0;
  v26 = 0;
  v11 = Common::SidHelper::ConvertSidToString(pSid, (struct Common::StringBuffer *)v25);
  PackageSid = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\eventlog\\eventloghelper.cpp",
      (const char *)(unsigned int)v11,
      v19);
LABEL_17:
    if ( v25[1] )
      operator delete(v25[1], v9);
    goto LABEL_8;
  }
  *(_OWORD *)v27 = 0;
  v28 = 0;
  v12 = Common::SidHelper::ConvertSidToString(Sid, (struct Common::StringBuffer *)v27);
  PackageSid = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\eventlog\\eventloghelper.cpp",
      (const char *)(unsigned int)v12,
      v19);
    goto LABEL_21;
  }
  v21[0] = 0;
  hToken = 0;
  v13 = Common::ImpersonateSelf::Impersonate((Common::ImpersonateSelf *)v21);
  PackageSid = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\eventlog\\eventloghelper.cpp",
      (const char *)(unsigned int)v13,
      v19);
    if ( !v21[0] )
      goto LABEL_21;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
      hToken = 0;
      goto LABEL_29;
    }
    if ( RevertToSelf() )
    {
LABEL_29:
      v21[0] = 0;
LABEL_21:
      if ( v27[1] )
        operator delete(v27[1], v9);
      goto LABEL_17;
    }
    Common::HandleInternalFailure();
  }
  v36 = *(_QWORD *)(*((_QWORD *)this + 3) + 248LL);
  v14 = v27[1];
  *(void **)v29 = v27[1];
  v15 = v25[1];
  v30 = v25[1];
  memset(v31, 0, sizeof(v31));
  v32 = 1;
  v16 = DirectoryACLs::ApplyAppXPackageRootFolderACLs(
          v36,
          v2,
          1,
          (unsigned int)&v30,
          (__int64)v29,
          (unsigned int)&v36,
          (__int64)v31,
          v4);
  Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>::~Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>(v31);
  if ( v16 >= 0 )
  {
    if ( v21[0] )
    {
      if ( hToken )
      {
        if ( !ImpersonateLoggedOnUser(hToken) )
        {
          Common::HandleInternalFailure();
          __debugbreak();
        }
        CloseHandle(hToken);
        hToken = 0;
      }
      else if ( !RevertToSelf() )
      {
        Common::HandleInternalFailure();
        JUMPOUT(0x1800ED628LL);
      }
      v21[0] = 0;
    }
    if ( v14 )
      operator delete(v14, v17);
    if ( v15 )
      operator delete(v15, v17);
    if ( v23[1] )
      operator delete(v23[1], v17);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\eventlog\\eventloghelper.cpp",
      (const char *)(unsigned int)v16,
      v20);
    if ( v21[0] )
    {
      if ( hToken )
      {
        if ( !ImpersonateLoggedOnUser(hToken) )
        {
          Common::HandleInternalFailure();
          __debugbreak();
        }
        CloseHandle(hToken);
        hToken = 0;
      }
      else if ( !RevertToSelf() )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      v21[0] = 0;
    }
    if ( v14 )
      operator delete(v14, v18);
    if ( v15 )
      operator delete(v15, v18);
    if ( v23[1] )
      operator delete(v23[1], v18);
    return (unsigned int)v16;
  }
}

```

## disassembly

```asm
0x1800ed294  mov     [rsp-8+arg_8], rbx
0x1800ed299  push    rbp
0x1800ed29a  push    rsi
0x1800ed29b  push    rdi
0x1800ed29c  push    r14
0x1800ed29e  push    r15
0x1800ed2a0  lea     rbp, [rsp-37h]
0x1800ed2a5  sub     rsp, 0D0h
0x1800ed2ac  mov     r14, rdx
0x1800ed2af  mov     rdi, rcx
0x1800ed2b2  mov     esi, 3
0x1800ed2b7  mov     rdx, [rcx+18h]
0x1800ed2bb  mov     eax, [rdx+180h]
0x1800ed2c1  test    al, 1
0x1800ed2c3  lea     ecx, [rsi+4]
0x1800ed2c6  cmovnz  esi, ecx
0x1800ed2c9  bt      eax, 8
0x1800ed2cd  jb      short loc_1800ED2D3
0x1800ed2cf  or      rsi, 8
0x1800ed2d3  xor     r15d, r15d
0x1800ed2d6  mov     [rbp+57h+pSid], r15
0x1800ed2da  mov     [rbp+57h+Sid], r15
0x1800ed2de  xorps   xmm0, xmm0
0x1800ed2e1  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x1800ed2e5  mov     [rbp+57h+var_90], r15d
0x1800ed2e9  mov     rdx, [rdx+0F8h]; unsigned __int16 *
0x1800ed2f0  lea     rcx, [rbp+57h+var_A0]; this
0x1800ed2f4  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800ed2f9  mov     ebx, eax
0x1800ed2fb  test    eax, eax
0x1800ed2fd  jns     short loc_1800ED32D
0x1800ed2ff  mov     edx, 0BAh; void *
0x1800ed304  mov     rcx, [rbp+5Fh]; this
0x1800ed308  mov     r9d, ebx; char *
0x1800ed30b  lea     r8, aOnecoreAdminAp_74; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ed312  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ed317  nop
0x1800ed318  mov     rcx, [rbp+57h+var_A0+8]; void *
0x1800ed31c  test    rcx, rcx
0x1800ed31f  jz      short loc_1800ED326
0x1800ed321  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed326  mov     eax, ebx
0x1800ed328  jmp     loc_1800ED5FA
0x1800ed32d  mov     rdx, [rdi+18h]
0x1800ed331  lea     r8, [rbp+57h+pSid]; void **
0x1800ed335  mov     rdx, [rdx+30h]; struct PackageRepository::IRepositorySession *
0x1800ed339  lea     rcx, [rbp+57h+var_A0]; struct Common::COMMON_STRING *
0x1800ed33d  call    ?GetPackageSid@PackageInfo@Deployment@Common@@SAJAEBUCOMMON_STRING@3@PEAVIRepositorySession@PackageRepository@@PEAPEAX@Z; Common::Deployment::PackageInfo::GetPackageSid(Common::COMMON_STRING const &,PackageRepository::IRepositorySession *,void * *)
0x1800ed342  mov     ebx, eax
0x1800ed344  test    eax, eax
0x1800ed346  jns     short loc_1800ED34F
0x1800ed348  mov     edx, 0C0h
0x1800ed34d  jmp     short loc_1800ED304
0x1800ed34f  lea     rdx, [rbp+57h+Sid]; Sid
0x1800ed353  mov     rcx, [rbp+57h+pSid]; pSid
0x1800ed357  call    ?PackageSidToPackageCapabilitySid@PackageSid@@SAJQEAXPEAPEAX@Z; PackageSid::PackageSidToPackageCapabilitySid(void * const,void * *)
0x1800ed35c  mov     ebx, eax
0x1800ed35e  test    eax, eax
0x1800ed360  jns     short loc_1800ED369
0x1800ed362  mov     edx, 0C5h
0x1800ed367  jmp     short loc_1800ED304
0x1800ed369  xorps   xmm0, xmm0
0x1800ed36c  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x1800ed370  mov     [rbp+57h+var_78], r15d
0x1800ed374  lea     rdx, [rbp+57h+var_88]; struct Common::StringBuffer *
0x1800ed378  mov     rcx, [rbp+57h+pSid]; Sid
0x1800ed37c  call    ?ConvertSidToString@SidHelper@Common@@SAJQEAXPEAVStringBuffer@2@@Z; Common::SidHelper::ConvertSidToString(void * const,Common::StringBuffer *)
0x1800ed381  mov     ebx, eax
0x1800ed383  test    eax, eax
0x1800ed385  jns     short loc_1800ED3B7
0x1800ed387  mov     rcx, [rbp+5Fh]; this
0x1800ed38b  mov     r9d, eax; char *
0x1800ed38e  lea     r8, aOnecoreAdminAp_74; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ed395  mov     edx, 0C8h; void *
0x1800ed39a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ed39f  nop
0x1800ed3a0  mov     rcx, [rbp+57h+var_88+8]; void *
0x1800ed3a4  test    rcx, rcx
0x1800ed3a7  jz      loc_1800ED318
0x1800ed3ad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed3b2  jmp     loc_1800ED318
0x1800ed3b7  xorps   xmm0, xmm0
0x1800ed3ba  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x1800ed3be  mov     [rbp+57h+var_60], r15d
0x1800ed3c2  lea     rdx, [rbp+57h+var_70]; struct Common::StringBuffer *
0x1800ed3c6  mov     rcx, [rbp+57h+Sid]; Sid
0x1800ed3ca  call    ?ConvertSidToString@SidHelper@Common@@SAJQEAXPEAVStringBuffer@2@@Z; Common::SidHelper::ConvertSidToString(void * const,Common::StringBuffer *)
0x1800ed3cf  mov     ebx, eax
0x1800ed3d1  test    eax, eax
0x1800ed3d3  jns     short loc_1800ED3FE
0x1800ed3d5  mov     rcx, [rbp+5Fh]; this
0x1800ed3d9  mov     r9d, eax; char *
0x1800ed3dc  lea     r8, aOnecoreAdminAp_74; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ed3e3  mov     edx, 0CBh; void *
0x1800ed3e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ed3ed  nop
0x1800ed3ee  mov     rcx, [rbp+57h+var_70+8]; void *
0x1800ed3f2  test    rcx, rcx
0x1800ed3f5  jz      short loc_1800ED3A0
0x1800ed3f7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed3fc  jmp     short loc_1800ED3A0
0x1800ed3fe  mov     [rbp+57h+var_B0], r15b
0x1800ed402  mov     [rbp+57h+hToken], r15
0x1800ed406  lea     rcx, [rbp+57h+var_B0]; this
0x1800ed40a  call    ?Impersonate@ImpersonateSelf@Common@@QEAAJXZ; Common::ImpersonateSelf::Impersonate(void)
0x1800ed40f  mov     ebx, eax
0x1800ed411  test    eax, eax
0x1800ed413  jns     short loc_1800ED483
0x1800ed415  mov     rcx, [rbp+5Fh]; this
0x1800ed419  mov     r9d, eax; char *
0x1800ed41c  lea     r8, aOnecoreAdminAp_74; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ed423  mov     edx, 0CFh; void *
0x1800ed428  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ed42d  nop
0x1800ed42e  cmp     [rbp+57h+var_B0], r15b
0x1800ed432  jz      short loc_1800ED3EE
0x1800ed434  mov     rcx, [rbp+57h+hToken]; hToken
0x1800ed438  test    rcx, rcx
0x1800ed43b  jz      short loc_1800ED46D
0x1800ed43d  call    cs:__imp_ImpersonateLoggedOnUser
0x1800ed444  nop     dword ptr [rax+rax+00h]
0x1800ed449  test    eax, eax
0x1800ed44b  jnz     short loc_1800ED453
0x1800ed44d  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800ed452  int     3; Trap to Debugger
0x1800ed453  mov     rcx, [rbp+57h+hToken]; hObject
0x1800ed457  call    cs:__imp_CloseHandle
0x1800ed45e  nop     dword ptr [rax+rax+00h]
0x1800ed463  mov     [rbp+57h+hToken], r15
0x1800ed467  mov     [rbp+57h+var_B0], r15b
0x1800ed46b  jmp     short loc_1800ED3EE
0x1800ed46d  call    cs:__imp_RevertToSelf
0x1800ed474  nop     dword ptr [rax+rax+00h]
0x1800ed479  test    eax, eax
0x1800ed47b  jnz     short loc_1800ED467
0x1800ed47d  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800ed482  nop
0x1800ed483  mov     rax, [rdi+18h]
0x1800ed487  mov     rcx, [rax+0F8h]
0x1800ed48e  mov     [rbp+57h+arg_18], rcx
0x1800ed492  mov     rdi, [rbp+57h+var_70+8]
0x1800ed496  mov     qword ptr [rbp+57h+var_58], rdi
0x1800ed49a  mov     rbx, [rbp+57h+var_88+8]
0x1800ed49e  mov     [rbp+57h+var_50], rbx
0x1800ed4a2  mov     [rbp+57h+var_48], r15
0x1800ed4a6  mov     [rbp+57h+var_40], r15
0x1800ed4aa  mov     [rbp+57h+var_38], r15
0x1800ed4ae  mov     [rbp+57h+var_30], 1
0x1800ed4b2  mov     [rsp+0F0h+var_B8], rsi
0x1800ed4b7  lea     rax, [rbp+57h+var_48]
0x1800ed4bb  mov     [rsp+0F0h+var_C0], rax
0x1800ed4c0  lea     rax, [rbp+57h+arg_18]
0x1800ed4c4  mov     [rsp+0F0h+var_C8], rax
0x1800ed4c9  lea     rax, [rbp+57h+var_58]
0x1800ed4cd  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x1800ed4d2  lea     r9, [rbp+57h+var_50]
0x1800ed4d6  mov     r8d, 1
0x1800ed4dc  mov     rdx, r14
0x1800ed4df  call    ?ApplyAppXPackageRootFolderACLs@DirectoryACLs@@YAJPEAUHKEY__@@PEBG_KPEAPEBG33PEBV?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@Common@@W4Flags@1@@Z; DirectoryACLs::ApplyAppXPackageRootFolderACLs(HKEY__ *,ushort const *,unsigned __int64,ushort const * *,ushort const * *,ushort const * *,Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> const *,DirectoryACLs::Flags)
0x1800ed4e4  mov     esi, eax
0x1800ed4e6  lea     rcx, [rbp+57h+var_48]
0x1800ed4ea  call    ??1?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@Common@@QEAA@XZ; Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>::~Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>(void)
0x1800ed4ef  test    esi, esi
0x1800ed4f1  jns     loc_1800ED591
0x1800ed4f7  mov     rcx, [rbp+5Fh]; this
0x1800ed4fb  mov     r9d, esi; char *
0x1800ed4fe  lea     r8, aOnecoreAdminAp_74; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ed505  mov     edx, 0D8h; void *
0x1800ed50a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ed50f  nop
0x1800ed510  cmp     [rbp+57h+var_B0], r15b
0x1800ed514  jz      short loc_1800ED54D
0x1800ed516  mov     rcx, [rbp+57h+hToken]; hToken
0x1800ed51a  test    rcx, rcx
0x1800ed51d  jz      short loc_1800ED57B
0x1800ed51f  call    cs:__imp_ImpersonateLoggedOnUser
0x1800ed526  nop     dword ptr [rax+rax+00h]
0x1800ed52b  test    eax, eax
0x1800ed52d  jnz     short loc_1800ED535
0x1800ed52f  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800ed534  int     3; Trap to Debugger
0x1800ed535  mov     rcx, [rbp+57h+hToken]; hObject
0x1800ed539  call    cs:__imp_CloseHandle
0x1800ed540  nop     dword ptr [rax+rax+00h]
0x1800ed545  mov     [rbp+57h+hToken], r15
0x1800ed549  mov     [rbp+57h+var_B0], r15b
0x1800ed54d  test    rdi, rdi
0x1800ed550  jz      short loc_1800ED55B
0x1800ed552  mov     rcx, rdi; void *
0x1800ed555  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed55a  nop
0x1800ed55b  test    rbx, rbx
0x1800ed55e  jz      short loc_1800ED569
0x1800ed560  mov     rcx, rbx; void *
0x1800ed563  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed568  nop
0x1800ed569  mov     rcx, [rbp+57h+var_A0+8]; void *
0x1800ed56d  test    rcx, rcx
0x1800ed570  jz      short loc_1800ED577
0x1800ed572  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed577  mov     eax, esi
0x1800ed579  jmp     short loc_1800ED5FA
0x1800ed57b  call    cs:__imp_RevertToSelf
0x1800ed582  nop     dword ptr [rax+rax+00h]
0x1800ed587  test    eax, eax
0x1800ed589  jnz     short loc_1800ED549
0x1800ed58b  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800ed590  int     3; Trap to Debugger
0x1800ed591  cmp     [rbp+57h+var_B0], r15b
0x1800ed595  jz      short loc_1800ED5CE
0x1800ed597  mov     rcx, [rbp+57h+hToken]; hToken
0x1800ed59b  test    rcx, rcx
0x1800ed59e  jz      short loc_1800ED612
0x1800ed5a0  call    cs:__imp_ImpersonateLoggedOnUser
0x1800ed5a7  nop     dword ptr [rax+rax+00h]
0x1800ed5ac  test    eax, eax
0x1800ed5ae  jnz     short loc_1800ED5B6
0x1800ed5b0  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800ed5b5  int     3; Trap to Debugger
0x1800ed5b6  mov     rcx, [rbp+57h+hToken]; hObject
0x1800ed5ba  call    cs:__imp_CloseHandle
0x1800ed5c1  nop     dword ptr [rax+rax+00h]
0x1800ed5c6  mov     [rbp+57h+hToken], r15
0x1800ed5ca  mov     [rbp+57h+var_B0], r15b
0x1800ed5ce  test    rdi, rdi
0x1800ed5d1  jz      short loc_1800ED5DC
0x1800ed5d3  mov     rcx, rdi; void *
0x1800ed5d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed5db  nop
0x1800ed5dc  test    rbx, rbx
0x1800ed5df  jz      short loc_1800ED5EA
0x1800ed5e1  mov     rcx, rbx; void *
0x1800ed5e4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed5e9  nop
0x1800ed5ea  mov     rcx, [rbp+57h+var_A0+8]; void *
0x1800ed5ee  test    rcx, rcx
0x1800ed5f1  jz      short loc_1800ED5F8
0x1800ed5f3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed5f8  xor     eax, eax
0x1800ed5fa  mov     rbx, [rsp+0F0h+arg_8]
0x1800ed602  add     rsp, 0D0h
0x1800ed609  pop     r15
0x1800ed60b  pop     r14
0x1800ed60d  pop     rdi
0x1800ed60e  pop     rsi
0x1800ed60f  pop     rbp
0x1800ed610  retn
0x1800ed612  call    cs:__imp_RevertToSelf
0x1800ed619  nop     dword ptr [rax+rax+00h]
0x1800ed61e  nop
0x1800ed61f  test    eax, eax
0x1800ed621  jnz     short loc_1800ED5CA
0x1800ed623  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
```
