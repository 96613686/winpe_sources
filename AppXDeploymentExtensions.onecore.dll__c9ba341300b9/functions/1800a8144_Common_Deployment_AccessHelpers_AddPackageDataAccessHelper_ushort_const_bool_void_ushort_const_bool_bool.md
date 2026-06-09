# Common::Deployment::AccessHelpers::AddPackageDataAccessHelper(ushort const *,bool,void *,ushort const *,bool,bool)

- ea: `0x1800a8144`
- end: `0x1800a861c`
- name: `?AddPackageDataAccessHelper@AccessHelpers@Deployment@Common@@SAJPEBG_NPEAX011@Z`
- size: `1240`
- prototype: `static int(const unsigned __int16 *, bool, void *, const unsigned __int16 *, bool, bool)`
- caller_count: `5`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18012c290`
- `0x1801e848c`
- `0x1801f2598`
- `0x1801f2950`
- `0x1801f46ec`

## callees

- `0x18000e6e0`
- `0x180021224`
- `0x18005deb8`
- `0x18005e98c`
- `0x1800a8144`
- `0x1800a8f80`
- `0x1800a9010`
- `0x1800bbdd8`
- `0x1800bc4a0`
- `0x1800cf838`
- `0x1801d9fa0`
- `0x1801f0158`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a82e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a83c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8476`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a853d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8567`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a82e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a83c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8476`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a853d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8567`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a82d0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a83b4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a8461`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a84be`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a8528`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a82d0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a83b4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a8461`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a84be`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a8528`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a82fa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a83de`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a848b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a8552`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a8597`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a82fa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a83de`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a848b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a8552`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a8597`

## string_xrefs

- `0x1800a81a9`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x1800a8207`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x1800a82ad`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x1800a8387`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x1800a8434`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x1800a8505`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x1800a85ef`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x1800a8378`: `GetAccess %ls`
- `0x1800a829e`: `Impersonate %ls %ls`
- `0x1800a8425`: `Failed applying SACL from ApplyPackageDataAccessSACL taken ownership %ls %ls %ls %d %d`
- `0x1800a84f6`: `Failed applying SACL from ApplyPackageDataAccessSACL %ls %ls %ls %d %d`
- `0x1800a8265`: `Failed applying DACL from ApplyPackageDataAccessACLs %ls %ls %ls %d %d`
- `0x1800a81f8`: `ConvertSidToString %ls %ls %p`
- `0x1800a819a`: `PackageSidToPackageCapabilitySid %ls %ls %p`
- `0x1800a85d6`: `ApplyPackageDataAccessACLs %ls %ls %ls %d %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Common::Deployment::AccessHelpers::AddPackageDataAccessHelper(
        char *a1,
        char a2,
        void *a3,
        const unsigned __int16 *a4,
        bool a5,
        bool a6)
{
  int Access; // ebx
  void *v10; // rdx
  const unsigned __int16 *v11; // r9
  const unsigned __int16 *v12; // r8
  DirectoryACLs *v13; // rcx
  unsigned __int16 *v14; // r12
  const unsigned __int16 *v15; // rdx
  bool v16; // r8
  bool v17; // r8
  bool v18; // r9
  const unsigned __int16 *v19; // rdx
  bool v20; // r8
  void *v21; // rdx
  unsigned __int16 *v23; // r14
  bool v24; // [rsp+28h] [rbp-C1h]
  _BYTE v25[8]; // [rsp+50h] [rbp-99h] BYREF
  HANDLE hToken; // [rsp+58h] [rbp-91h]
  PSID Sid; // [rsp+60h] [rbp-89h] BYREF
  unsigned __int16 *v28[2]; // [rsp+68h] [rbp-81h] BYREF
  int v29; // [rsp+78h] [rbp-71h]
  _OWORD v30[2]; // [rsp+80h] [rbp-69h] BYREF
  char v31; // [rsp+A0h] [rbp-49h]
  __int64 v32; // [rsp+A8h] [rbp-41h]
  __int64 v33; // [rsp+B0h] [rbp-39h]
  char v34; // [rsp+B8h] [rbp-31h]
  char v35; // [rsp+C0h] [rbp-29h]
  __int64 v36; // [rsp+C8h] [rbp-21h]
  __int128 v37; // [rsp+D0h] [rbp-19h]
  char v38; // [rsp+E0h] [rbp-9h]
  char v39; // [rsp+E8h] [rbp-1h]
  __int64 v40; // [rsp+F0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+4Fh]

  if ( a2 )
    return 0;
  Sid = 0;
  Access = PackageSid::PackageSidToPackageCapabilitySid(a3, &Sid);
  if ( Access >= 0 )
  {
    *(_OWORD *)v28 = 0;
    v29 = 0;
    Access = Common::SidHelper::ConvertSidToString(Sid, (struct Common::StringBuffer *)v28);
    if ( Access < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x18E,
        (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
        (const char *)(unsigned int)Access,
        (int)"ConvertSidToString %ls %ls %p",
        a1,
        a4,
        Sid);
LABEL_62:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v28);
      goto LABEL_63;
    }
    LOBYTE(v11) = a5;
    v12 = a4;
    v13 = (DirectoryACLs *)a1;
    if ( a6 )
    {
      v14 = v28[1];
      Access = DirectoryACLs::ApplyPackageDataAccessACLs((DirectoryACLs *)a1, v28[1], a4, v11, a6, v24);
      if ( Access < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x19D,
          (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
          (const char *)(unsigned int)Access,
          (int)"Failed applying DACL from ApplyPackageDataAccessACLs %ls %ls %ls %d %d",
          a1,
          a4,
          v14,
          a5,
          a6);
        goto LABEL_62;
      }
      v25[0] = 0;
      hToken = 0;
      Access = Common::ImpersonateSelf::Impersonate((Common::ImpersonateSelf *)v25);
      if ( Access < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1A3,
          (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
          (const char *)(unsigned int)Access,
          (int)"Impersonate %ls %ls",
          a1);
        if ( !v25[0] )
          goto LABEL_62;
        if ( hToken )
        {
          if ( !ImpersonateLoggedOnUser(hToken) )
          {
            Common::HandleInternalFailure();
            __debugbreak();
          }
          CloseHandle(hToken);
          hToken = 0;
          goto LABEL_15;
        }
        if ( RevertToSelf() )
        {
LABEL_15:
          v25[0] = 0;
          goto LABEL_62;
        }
        Common::HandleInternalFailure();
      }
      LOBYTE(v15) = a5;
      Access = DirectoryACLs::ApplyPackageDataAccessSACL((DirectoryACLs *)a1, v15, v16);
      if ( Access != -2147024891 )
        goto LABEL_45;
      memset(v30, 0, sizeof(v30));
      v31 = 0;
      v32 = 0;
      v33 = 0;
      v34 = 0;
      v35 = 0;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      v39 = 0;
      v40 = 0;
      Access = Common::Deployment::TakeOwnership::GetAccess(
                 (Common::Deployment::TakeOwnership *)v30,
                 (const unsigned __int16 *)a1,
                 v17,
                 v18);
      if ( Access < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1AB,
          (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
          (const char *)(unsigned int)Access,
          (int)"GetAccess %ls",
          a1);
        Common::Deployment::TakeOwnership::~TakeOwnership((Common::Deployment::TakeOwnership *)v30);
        if ( !v25[0] )
          goto LABEL_62;
        if ( hToken )
        {
          if ( !ImpersonateLoggedOnUser(hToken) )
          {
            Common::HandleInternalFailure();
            __debugbreak();
          }
          CloseHandle(hToken);
          hToken = 0;
          goto LABEL_26;
        }
        if ( RevertToSelf() )
        {
LABEL_26:
          v25[0] = 0;
          goto LABEL_62;
        }
        Common::HandleInternalFailure();
      }
      LOBYTE(v19) = a5;
      Access = DirectoryACLs::ApplyPackageDataAccessSACL((DirectoryACLs *)a1, v19, v20);
      if ( Access < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1AF,
          (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
          (const char *)(unsigned int)Access,
          (int)"Failed applying SACL from ApplyPackageDataAccessSACL taken ownership %ls %ls %ls %d %d",
          a1);
        Common::Deployment::TakeOwnership::~TakeOwnership((Common::Deployment::TakeOwnership *)v30);
        if ( !v25[0] )
          goto LABEL_62;
        if ( hToken )
        {
          if ( !ImpersonateLoggedOnUser(hToken) )
          {
            Common::HandleInternalFailure();
            __debugbreak();
          }
          CloseHandle(hToken);
          hToken = 0;
          goto LABEL_36;
        }
        if ( RevertToSelf() )
        {
LABEL_36:
          v25[0] = 0;
          goto LABEL_62;
        }
        Common::HandleInternalFailure();
      }
      Common::Deployment::TakeOwnership::~TakeOwnership((Common::Deployment::TakeOwnership *)v30);
      while ( 1 )
      {
        if ( !v25[0] )
          goto LABEL_56;
        if ( !hToken )
          break;
        if ( ImpersonateLoggedOnUser(hToken) )
          goto LABEL_55;
        Common::HandleInternalFailure();
LABEL_45:
        if ( Access < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x1B5,
            (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
            (const char *)(unsigned int)Access,
            (int)"Failed applying SACL from ApplyPackageDataAccessSACL %ls %ls %ls %d %d",
            a1,
            a4,
            v14,
            a5,
            a6);
          if ( !v25[0] )
            goto LABEL_62;
          if ( hToken )
          {
            if ( !ImpersonateLoggedOnUser(hToken) )
            {
              Common::HandleInternalFailure();
              __debugbreak();
            }
            CloseHandle(hToken);
            hToken = 0;
            goto LABEL_51;
          }
          if ( RevertToSelf() )
          {
LABEL_51:
            v25[0] = 0;
            goto LABEL_62;
          }
          Common::HandleInternalFailure();
LABEL_55:
          CloseHandle(hToken);
          goto LABEL_56;
        }
      }
      if ( RevertToSelf() )
        goto LABEL_56;
      Common::HandleInternalFailure();
    }
    v23 = v28[1];
    Access = DirectoryACLs::ApplyPackageDataAccessACLs(v13, v28[1], v12, v11, 0, v24);
    if ( Access < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1C3,
        (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
        (const char *)(unsigned int)Access,
        (int)"ApplyPackageDataAccessACLs %ls %ls %ls %d %d",
        a1,
        v23,
        a4,
        a5,
        0);
      goto LABEL_62;
    }
LABEL_56:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v28);
    Common::AutoPtrSidRtlFreeSid((Common *)Sid, v21);
    return 0;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x189,
    (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
    (const char *)(unsigned int)Access,
    (int)"PackageSidToPackageCapabilitySid %ls %ls %p",
    a1,
    a4,
    a3);
LABEL_63:
  Common::AutoPtrSidRtlFreeSid((Common *)Sid, v10);
  return (unsigned int)Access;
}

```

## disassembly

```asm
0x1800a8144  push    rbp
0x1800a8146  push    rbx
0x1800a8147  push    rsi
0x1800a8148  push    rdi
0x1800a8149  push    r12
0x1800a814b  push    r13
0x1800a814d  push    r14
0x1800a814f  lea     rbp, [rsp-17h]
0x1800a8154  sub     rsp, 100h
0x1800a815b  mov     rsi, r9
0x1800a815e  mov     r14, r8
0x1800a8161  mov     rdi, rcx
0x1800a8164  xor     r13d, r13d
0x1800a8167  test    dl, dl
0x1800a8169  jnz     loc_1800A8583
0x1800a816f  mov     [rsp+130h+Sid], r13
0x1800a8174  lea     rdx, [rsp+130h+Sid]; Sid
0x1800a8179  mov     rcx, r8; pSid
0x1800a817c  call    ?PackageSidToPackageCapabilitySid@PackageSid@@SAJQEAXPEAPEAX@Z; PackageSid::PackageSidToPackageCapabilitySid(void * const,void * *)
0x1800a8181  mov     ebx, eax
0x1800a8183  test    eax, eax
0x1800a8185  jns     short loc_1800A81BF
0x1800a8187  mov     rcx, [rbp+4Fh]; this
0x1800a818b  mov     [rsp+130h+var_F8], r14
0x1800a8190  mov     [rsp+130h+var_100], rsi
0x1800a8195  mov     [rsp+130h+var_108], rdi; char *
0x1800a819a  lea     rax, aPackagesidtopa_0; "PackageSidToPackageCapabilitySid %ls %l"...
0x1800a81a1  mov     qword ptr [rsp+130h+var_110], rax; int
0x1800a81a6  mov     r9d, ebx; char *
0x1800a81a9  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\common\\acces"...
0x1800a81b0  mov     edx, 189h; void *
0x1800a81b5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a81ba  jmp     loc_1800A860B
0x1800a81bf  xorps   xmm0, xmm0
0x1800a81c2  movups  xmmword ptr [rsp+130h+var_C8], xmm0
0x1800a81c7  mov     [rbp+47h+var_B8], r13d
0x1800a81cb  lea     rdx, [rsp+130h+var_C8]; this
0x1800a81d0  mov     rcx, [rsp+130h+Sid]; Sid
0x1800a81d5  call    ?ConvertSidToString@SidHelper@Common@@SAJQEAXPEAVStringBuffer@2@@Z; Common::SidHelper::ConvertSidToString(void * const,Common::StringBuffer *)
0x1800a81da  mov     ebx, eax
0x1800a81dc  test    eax, eax
0x1800a81de  jns     short loc_1800A821D
0x1800a81e0  mov     rcx, [rbp+4Fh]; this
0x1800a81e4  mov     rdx, [rsp+130h+Sid]
0x1800a81e9  mov     [rsp+130h+var_F8], rdx
0x1800a81ee  mov     [rsp+130h+var_100], rsi
0x1800a81f3  mov     [rsp+130h+var_108], rdi; char *
0x1800a81f8  lea     rax, aConvertsidtost_1; "ConvertSidToString %ls %ls %p"
0x1800a81ff  mov     qword ptr [rsp+130h+var_110], rax; int
0x1800a8204  mov     r9d, ebx; char *
0x1800a8207  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\common\\acces"...
0x1800a820e  mov     edx, 18Eh; void *
0x1800a8213  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a8218  jmp     loc_1800A8600
0x1800a821d  movzx   r14d, [rbp+47h+arg_28]
0x1800a8222  mov     r9b, byte ptr [rbp+47h+arg_20]; unsigned __int16 *
0x1800a8226  mov     r8, rsi; unsigned __int16 *
0x1800a8229  mov     rcx, rdi; this
0x1800a822c  test    r14b, r14b
0x1800a822f  jz      loc_1800A85A8
0x1800a8235  mov     [rsp+130h+var_110], r14b; bool
0x1800a823a  mov     r12, [rbp+47h+var_C8+8]
0x1800a823e  mov     rdx, r12; unsigned __int16 *
0x1800a8241  call    ?ApplyPackageDataAccessACLs@DirectoryACLs@@YAJPEBG00_N1@Z; DirectoryACLs::ApplyPackageDataAccessACLs(ushort const *,ushort const *,ushort const *,bool,bool)
0x1800a8246  mov     ebx, eax
0x1800a8248  test    eax, eax
0x1800a824a  jns     short loc_1800A8276
0x1800a824c  movzx   r8d, byte ptr [rbp+47h+arg_20]
0x1800a8251  mov     [rsp+130h+var_E8], r14d
0x1800a8256  mov     [rsp+130h+var_F0], r8d
0x1800a825b  mov     [rsp+130h+var_F8], r12
0x1800a8260  mov     [rsp+130h+var_100], rsi
0x1800a8265  lea     rax, aFailedApplying_0; "Failed applying DACL from ApplyPackageD"...
0x1800a826c  mov     edx, 19Dh
0x1800a8271  jmp     loc_1800A85E2
0x1800a8276  mov     [rsp+130h+var_E0], r13b
0x1800a827b  mov     [rsp+130h+hToken], r13
0x1800a8280  lea     rcx, [rsp+130h+var_E0]; this
0x1800a8285  call    ?Impersonate@ImpersonateSelf@Common@@QEAAJXZ; Common::ImpersonateSelf::Impersonate(void)
0x1800a828a  mov     ebx, eax
0x1800a828c  test    eax, eax
0x1800a828e  jns     short loc_1800A830A
0x1800a8290  mov     rcx, [rbp+4Fh]; this
0x1800a8294  mov     [rsp+130h+var_100], rsi
0x1800a8299  mov     [rsp+130h+var_108], rdi; char *
0x1800a829e  lea     rax, aImpersonateLsL; "Impersonate %ls %ls"
0x1800a82a5  mov     qword ptr [rsp+130h+var_110], rax; int
0x1800a82aa  mov     r9d, ebx; char *
0x1800a82ad  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\common\\acces"...
0x1800a82b4  mov     edx, 1A3h; void *
0x1800a82b9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a82be  nop
0x1800a82bf  cmp     [rsp+130h+var_E0], r13b
0x1800a82c4  jz      short loc_1800A82F5
0x1800a82c6  mov     rcx, [rsp+130h+hToken]; hToken
0x1800a82cb  test    rcx, rcx
0x1800a82ce  jz      short loc_1800A82FA
0x1800a82d0  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a82d6  test    eax, eax
0x1800a82d8  jnz     short loc_1800A82E0
0x1800a82da  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a82df  int     3; Trap to Debugger
0x1800a82e0  mov     rcx, [rsp+130h+hToken]; hObject
0x1800a82e5  call    cs:__imp_CloseHandle
0x1800a82eb  mov     [rsp+130h+hToken], r13
0x1800a82f0  mov     [rsp+130h+var_E0], r13b
0x1800a82f5  jmp     loc_1800A8600
0x1800a82fa  call    cs:__imp_RevertToSelf
0x1800a8300  test    eax, eax
0x1800a8302  jnz     short loc_1800A82F0
0x1800a8304  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a8309  nop
0x1800a830a  mov     dl, byte ptr [rbp+47h+arg_20]; unsigned __int16 *
0x1800a830d  mov     rcx, rdi; this
0x1800a8310  call    ?ApplyPackageDataAccessSACL@DirectoryACLs@@YAJPEBG_N@Z; DirectoryACLs::ApplyPackageDataAccessSACL(ushort const *,bool)
0x1800a8315  mov     ebx, eax
0x1800a8317  cmp     eax, 80070005h
0x1800a831c  jnz     loc_1800A84D2
0x1800a8322  xorps   xmm0, xmm0
0x1800a8325  movdqa  [rbp+47h+var_B0], xmm0
0x1800a832a  xorps   xmm1, xmm1
0x1800a832d  movdqa  [rbp+47h+var_A0], xmm1
0x1800a8332  mov     [rbp+47h+var_90], r13b
0x1800a8336  mov     [rbp+47h+var_88], r13
0x1800a833a  xor     eax, eax
0x1800a833c  mov     [rbp+47h+var_80], rax
0x1800a8340  mov     [rbp+47h+var_78], r13b
0x1800a8344  mov     [rbp+47h+var_70], r13b
0x1800a8348  mov     [rbp+47h+var_68], r13
0x1800a834c  movdqa  [rbp+47h+var_60], xmm0
0x1800a8351  mov     [rbp+47h+var_50], r13b
0x1800a8355  mov     [rbp+47h+var_48], r13b
0x1800a8359  mov     [rbp+47h+var_40], r13
0x1800a835d  mov     rdx, rdi; unsigned __int16 *
0x1800a8360  lea     rcx, [rbp+47h+var_B0]; this
0x1800a8364  call    ?GetAccess@TakeOwnership@Deployment@Common@@AEAAJPEBG_N1@Z; Common::Deployment::TakeOwnership::GetAccess(ushort const *,bool,bool)
0x1800a8369  mov     ebx, eax
0x1800a836b  test    eax, eax
0x1800a836d  jns     short loc_1800A83EE
0x1800a836f  mov     rcx, [rbp+4Fh]; this
0x1800a8373  mov     [rsp+130h+var_108], rdi; char *
0x1800a8378  lea     rax, aGetaccessLs; "GetAccess %ls"
0x1800a837f  mov     qword ptr [rsp+130h+var_110], rax; int
0x1800a8384  mov     r9d, ebx; char *
0x1800a8387  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\common\\acces"...
0x1800a838e  mov     edx, 1ABh; void *
0x1800a8393  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a8398  nop
0x1800a8399  lea     rcx, [rbp+47h+var_B0]; this
0x1800a839d  call    ??1TakeOwnership@Deployment@Common@@QEAA@XZ; Common::Deployment::TakeOwnership::~TakeOwnership(void)
0x1800a83a2  nop
0x1800a83a3  cmp     [rsp+130h+var_E0], r13b
0x1800a83a8  jz      short loc_1800A83D9
0x1800a83aa  mov     rcx, [rsp+130h+hToken]; hToken
0x1800a83af  test    rcx, rcx
0x1800a83b2  jz      short loc_1800A83DE
0x1800a83b4  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a83ba  test    eax, eax
0x1800a83bc  jnz     short loc_1800A83C4
0x1800a83be  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a83c3  int     3; Trap to Debugger
0x1800a83c4  mov     rcx, [rsp+130h+hToken]; hObject
0x1800a83c9  call    cs:__imp_CloseHandle
0x1800a83cf  mov     [rsp+130h+hToken], r13
0x1800a83d4  mov     [rsp+130h+var_E0], r13b
0x1800a83d9  jmp     loc_1800A8600
0x1800a83de  call    cs:__imp_RevertToSelf
0x1800a83e4  test    eax, eax
0x1800a83e6  jnz     short loc_1800A83D4
0x1800a83e8  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a83ed  nop
0x1800a83ee  mov     dl, byte ptr [rbp+47h+arg_20]; unsigned __int16 *
0x1800a83f1  mov     rcx, rdi; this
0x1800a83f4  call    ?ApplyPackageDataAccessSACL@DirectoryACLs@@YAJPEBG_N@Z; DirectoryACLs::ApplyPackageDataAccessSACL(ushort const *,bool)
0x1800a83f9  mov     ebx, eax
0x1800a83fb  test    eax, eax
0x1800a83fd  jns     loc_1800A849B
0x1800a8403  movzx   r8d, byte ptr [rbp+47h+arg_20]
0x1800a8408  mov     rcx, [rbp+4Fh]; this
0x1800a840c  mov     [rsp+130h+var_E8], r14d
0x1800a8411  mov     [rsp+130h+var_F0], r8d
0x1800a8416  mov     [rsp+130h+var_F8], r12
0x1800a841b  mov     [rsp+130h+var_100], rsi
0x1800a8420  mov     [rsp+130h+var_108], rdi; bool
0x1800a8425  lea     rax, aFailedApplying; "Failed applying SACL from ApplyPackageD"...
0x1800a842c  mov     qword ptr [rsp+130h+var_110], rax; int
0x1800a8431  mov     r9d, ebx; char *
0x1800a8434  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\common\\acces"...
0x1800a843b  mov     edx, 1AFh; void *
0x1800a8440  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a8445  nop
0x1800a8446  lea     rcx, [rbp+47h+var_B0]; this
0x1800a844a  call    ??1TakeOwnership@Deployment@Common@@QEAA@XZ; Common::Deployment::TakeOwnership::~TakeOwnership(void)
0x1800a844f  nop
0x1800a8450  cmp     [rsp+130h+var_E0], r13b
0x1800a8455  jz      short loc_1800A8486
0x1800a8457  mov     rcx, [rsp+130h+hToken]; hToken
0x1800a845c  test    rcx, rcx
0x1800a845f  jz      short loc_1800A848B
0x1800a8461  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a8467  test    eax, eax
0x1800a8469  jnz     short loc_1800A8471
0x1800a846b  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a8470  int     3; Trap to Debugger
0x1800a8471  mov     rcx, [rsp+130h+hToken]; hObject
0x1800a8476  call    cs:__imp_CloseHandle
0x1800a847c  mov     [rsp+130h+hToken], r13
0x1800a8481  mov     [rsp+130h+var_E0], r13b
0x1800a8486  jmp     loc_1800A8600
0x1800a848b  call    cs:__imp_RevertToSelf
0x1800a8491  test    eax, eax
0x1800a8493  jnz     short loc_1800A8481
0x1800a8495  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a849a  nop
0x1800a849b  lea     rcx, [rbp+47h+var_B0]; this
0x1800a849f  call    ??1TakeOwnership@Deployment@Common@@QEAA@XZ; Common::Deployment::TakeOwnership::~TakeOwnership(void)
0x1800a84a4  nop
0x1800a84a5  cmp     [rsp+130h+var_E0], r13b
0x1800a84aa  jz      loc_1800A856E
0x1800a84b0  mov     rcx, [rsp+130h+hToken]; hToken
0x1800a84b5  test    rcx, rcx
0x1800a84b8  jz      loc_1800A8597
0x1800a84be  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a84c4  test    eax, eax
0x1800a84c6  jnz     loc_1800A8562
0x1800a84cc  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a84d1  nop
0x1800a84d2  test    ebx, ebx
0x1800a84d4  jns     short loc_1800A84A5
0x1800a84d6  movzx   edx, byte ptr [rbp+47h+arg_20]
0x1800a84da  mov     rcx, [rbp+4Fh]; this
0x1800a84de  mov     [rsp+130h+var_E8], r14d
0x1800a84e3  mov     [rsp+130h+var_F0], edx
0x1800a84e7  mov     [rsp+130h+var_F8], r12
0x1800a84ec  mov     [rsp+130h+var_100], rsi
0x1800a84f1  mov     [rsp+130h+var_108], rdi; char *
0x1800a84f6  lea     rax, aFailedApplying_1; "Failed applying SACL from ApplyPackageD"...
0x1800a84fd  mov     qword ptr [rsp+130h+var_110], rax; int
0x1800a8502  mov     r9d, ebx; char *
0x1800a8505  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\common\\acces"...
0x1800a850c  mov     edx, 1B5h; void *
0x1800a8511  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a8516  nop
0x1800a8517  cmp     [rsp+130h+var_E0], r13b
0x1800a851c  jz      short loc_1800A854D
0x1800a851e  mov     rcx, [rsp+130h+hToken]; hToken
0x1800a8523  test    rcx, rcx
0x1800a8526  jz      short loc_1800A8552
0x1800a8528  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a852e  test    eax, eax
0x1800a8530  jnz     short loc_1800A8538
0x1800a8532  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a8537  int     3; Trap to Debugger
0x1800a8538  mov     rcx, [rsp+130h+hToken]; hObject
0x1800a853d  call    cs:__imp_CloseHandle
0x1800a8543  mov     [rsp+130h+hToken], r13
0x1800a8548  mov     [rsp+130h+var_E0], r13b
0x1800a854d  jmp     loc_1800A8600
0x1800a8552  call    cs:__imp_RevertToSelf
0x1800a8558  test    eax, eax
0x1800a855a  jnz     short loc_1800A8548
0x1800a855c  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a8561  nop
0x1800a8562  mov     rcx, [rsp+130h+hToken]; hObject
0x1800a8567  call    cs:__imp_CloseHandle
0x1800a856d  nop
0x1800a856e  lea     rcx, [rsp+130h+var_C8]; this
0x1800a8573  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800a8578  nop
0x1800a8579  mov     rcx, [rsp+130h+Sid]; this
0x1800a857e  call    ?AutoPtrSidRtlFreeSid@Common@@YAXPEAX@Z; Common::AutoPtrSidRtlFreeSid(void *)
0x1800a8583  xor     eax, eax
0x1800a8585  add     rsp, 100h
0x1800a858c  pop     r14
0x1800a858e  pop     r13
0x1800a8590  pop     r12
0x1800a8592  pop     rdi
0x1800a8593  pop     rsi
0x1800a8594  pop     rbx
0x1800a8595  pop     rbp
0x1800a8596  retn
0x1800a8597  call    cs:__imp_RevertToSelf
0x1800a859d  nop
0x1800a859e  test    eax, eax
0x1800a85a0  jnz     short loc_1800A856E
0x1800a85a2  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a85a7  nop
0x1800a85a8  mov     [rsp+130h+var_110], r13b; bool
0x1800a85ad  mov     r14, [rbp+47h+var_C8+8]
0x1800a85b1  mov     rdx, r14; unsigned __int16 *
0x1800a85b4  call    ?ApplyPackageDataAccessACLs@DirectoryACLs@@YAJPEBG00_N1@Z; DirectoryACLs::ApplyPackageDataAccessACLs(ushort const *,ushort const *,ushort const *,bool,bool)
0x1800a85b9  mov     ebx, eax
0x1800a85bb  test    eax, eax
0x1800a85bd  jns     short loc_1800A856E
0x1800a85bf  movzx   edx, byte ptr [rbp+47h+arg_20]
0x1800a85c3  mov     [rsp+130h+var_E8], r13d
0x1800a85c8  mov     [rsp+130h+var_F0], edx
0x1800a85cc  mov     [rsp+130h+var_F8], rsi
0x1800a85d1  mov     [rsp+130h+var_100], r14
0x1800a85d6  lea     rax, aApplypackageda; "ApplyPackageDataAccessACLs %ls %ls %ls "...
  ... truncated ...
```
