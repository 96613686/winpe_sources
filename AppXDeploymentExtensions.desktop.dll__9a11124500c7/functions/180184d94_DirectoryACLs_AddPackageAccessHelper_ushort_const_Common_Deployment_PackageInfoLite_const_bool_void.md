# DirectoryACLs::AddPackageAccessHelper(ushort const *,Common::Deployment::PackageInfoLite const *,bool,void *)

- ea: `0x180184d94`
- end: `0x1801851db`
- name: `?AddPackageAccessHelper@DirectoryACLs@@YAJPEBGPEBVPackageInfoLite@Deployment@Common@@_NPEAX@Z`
- size: `1095`
- prototype: `__int64 __fastcall(DirectoryACLs *__hidden this, const unsigned __int16 *, const struct Common::Deployment::PackageInfoLite *, bool, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18017fbf0`

## callees

- `0x18000669c`
- `0x18001adb4`
- `0x18008ab30`
- `0x1800a0c14`
- `0x180173890`
- `0x180184d94`
- `0x1801851e4`
- `0x180185958`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180184e10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180185179`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801851a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180184e10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180185179`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801851a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180184f10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180184f96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18018501b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180185073`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180184f10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180184f96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18018501b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180185073`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180184ee1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180184f6b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180184ee1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180184f6b`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180184df6`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180184f30`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180184fb6`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18018503b`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180185097`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1801850f9`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18018515f`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180184df6`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180184f30`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180184fb6`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18018503b`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180185097`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1801850f9`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18018515f`
- `ADVAPI32!RevertToSelf` at `0x180184e23`
- `ADVAPI32!RevertToSelf` at `0x180184f4a`
- `ADVAPI32!RevertToSelf` at `0x180184fd0`
- `ADVAPI32!RevertToSelf` at `0x180185055`
- `ADVAPI32!RevertToSelf` at `0x18018510f`
- `ADVAPI32!RevertToSelf` at `0x180185189`
- `ADVAPI32!RevertToSelf` at `0x1801851c5`
- `ADVAPI32!RevertToSelf` at `0x180184e23`
- `ADVAPI32!RevertToSelf` at `0x180184f4a`
- `ADVAPI32!RevertToSelf` at `0x180184fd0`
- `ADVAPI32!RevertToSelf` at `0x180185055`
- `ADVAPI32!RevertToSelf` at `0x18018510f`
- `ADVAPI32!RevertToSelf` at `0x180185189`
- `ADVAPI32!RevertToSelf` at `0x1801851c5`

## string_xrefs

- `0x180184dd5`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x180184ef9`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x180184f7f`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x180185005`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x1801850d4`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x18018513e`: `onecore\admin\appmodel\common\directoryacls.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DirectoryACLs::AddPackageAccessHelper(
        WCHAR *this,
        unsigned __int64 a2,
        const struct Common::Deployment::PackageInfoLite *a3,
        void *a4)
{
  int v6; // eax
  unsigned int v7; // edi
  __int64 v9; // rax
  char v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdx
  ULONG *v15; // r9
  DWORD v16; // edx
  bool v17; // zf
  PSECURITY_DESCRIPTOR *p_SecurityDescriptor; // r8
  const char *v19; // r9
  const char *v20; // r9
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // [rsp+20h] [rbp-20h]
  _BYTE v25[8]; // [rsp+30h] [rbp-10h] BYREF
  HANDLE hToken; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp+38h] BYREF

  SecurityDescriptor = a4;
  v25[0] = 0;
  hToken = 0;
  v6 = Common::ImpersonateSelf::Impersonate((Common::ImpersonateSelf *)v25);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x673,
      (unsigned int)"onecore\\admin\\appmodel\\common\\directoryacls.cpp",
      (const char *)(unsigned int)v6,
      v24);
    if ( !v25[0] )
      return v7;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
      return v7;
    }
    if ( RevertToSelf() )
      return v7;
    Common::HandleInternalFailure();
  }
  v9 = (*(_BYTE *)a2 != 0 ? 6LL : 2LL) | 0x40;
  if ( !*(_BYTE *)(a2 + 9) )
    v9 = *(_BYTE *)a2 != 0 ? 6LL : 2LL;
  v10 = *(_BYTE *)(a2 + 1);
  v11 = v9 | 8;
  if ( !v10 )
    v11 = v9;
  v12 = v11 | 0x80;
  if ( !*(_BYTE *)(a2 + 40) )
    v12 = v11;
  v13 = v12 | 0x80;
  if ( !*(_BYTE *)(a2 + 5) )
    v13 = v12;
  v14 = v13 | 0x2000;
  if ( !*(_BYTE *)(a2 + 42) )
    v14 = v13;
  if ( *(_BYTE *)(a2 + 2) || *(_BYTE *)(a2 + 3) || *(_BYTE *)(a2 + 4) )
    goto LABEL_58;
  if ( !*(_BYTE *)(a2 + 6) )
    goto LABEL_51;
  SecurityDescriptor = 0;
  v15 = 0;
  v16 = 1;
  v17 = v10 == 0;
  p_SecurityDescriptor = &SecurityDescriptor;
  if ( v17 )
    goto LABEL_32;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:PAI(A;OICI;FA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;OI;0x1200a9;;;BA)(A;CI;0x1"
           "200a9;;;BA)(A;OICI;0x1200a9;;;BA)(A;OICI;0x1200a9;;;LS)(A;OICI;0x1200a9;;;NS)(A;OICI;FA;;;SY)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LODWORD(a2) = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x6A9,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\directoryacls.cpp",
                    v19);
    LocalFree(SecurityDescriptor);
    if ( !v25[0] )
      return (unsigned int)a2;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      goto LABEL_63;
    }
    if ( RevertToSelf() )
      return (unsigned int)a2;
    Common::HandleInternalFailure();
LABEL_32:
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:PAI(A;OICI;FA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;OI;0x120089;;;BA)(A;CI;0"
             "x120089;;;BA)(A;OICI;0x120089;;;BA)(A;OICI;0x120089;;;LS)(A;OICI;0x120089;;;NS)(A;OICI;FA;;;SY)",
            v16,
            p_SecurityDescriptor,
            v15) )
    {
      LODWORD(a2) = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x6B1,
                      (unsigned int)"onecore\\admin\\appmodel\\common\\directoryacls.cpp",
                      v20);
      LocalFree(SecurityDescriptor);
      if ( !v25[0] )
        return (unsigned int)a2;
      if ( hToken )
      {
        if ( !ImpersonateLoggedOnUser(hToken) )
        {
          Common::HandleInternalFailure();
          __debugbreak();
        }
        goto LABEL_63;
      }
      if ( RevertToSelf() )
        return (unsigned int)a2;
      Common::HandleInternalFailure();
    }
  }
  v21 = DirectoryACLs::ApplySecurityDescriptor(this, 0, (__int64)SecurityDescriptor);
  a2 = (unsigned int)v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6B4,
      (unsigned int)"onecore\\admin\\appmodel\\common\\directoryacls.cpp",
      (const char *)(unsigned int)v21,
      v24);
    LocalFree(SecurityDescriptor);
    if ( !v25[0] )
      return (unsigned int)a2;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      goto LABEL_63;
    }
    if ( RevertToSelf() )
      return (unsigned int)a2;
    Common::HandleInternalFailure();
  }
  LocalFree(SecurityDescriptor);
  while ( 1 )
  {
    if ( !v25[0] )
      return 0;
    if ( !hToken )
    {
      if ( !RevertToSelf() )
      {
        Common::HandleInternalFailure();
        JUMPOUT(0x1801851DALL);
      }
      return 0;
    }
    if ( ImpersonateLoggedOnUser(hToken) )
    {
      CloseHandle(hToken);
      return 0;
    }
    Common::HandleInternalFailure();
LABEL_51:
    v22 = DirectoryACLs::ApplyPackageACLsHelper(this, a2, v14, 0);
    a2 = (unsigned int)v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B8,
        (unsigned int)"onecore\\admin\\appmodel\\common\\directoryacls.cpp",
        (const char *)(unsigned int)v22,
        0);
      if ( !v25[0] )
        return (unsigned int)a2;
      if ( hToken )
      {
        if ( !ImpersonateLoggedOnUser(hToken) )
        {
          Common::HandleInternalFailure();
          __debugbreak();
        }
        goto LABEL_63;
      }
      if ( RevertToSelf() )
        return (unsigned int)a2;
      Common::HandleInternalFailure();
LABEL_58:
      v23 = DirectoryACLs::ApplyAppXFrameworkPackageRootFolderACLs(this, v14);
      a2 = (unsigned int)v23;
      if ( v23 < 0 )
        break;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x684,
    (unsigned int)"onecore\\admin\\appmodel\\common\\directoryacls.cpp",
    (const char *)(unsigned int)v23,
    v24);
  if ( !v25[0] )
    return (unsigned int)a2;
  if ( hToken )
  {
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      Common::HandleInternalFailure();
      __debugbreak();
    }
LABEL_63:
    CloseHandle(hToken);
  }
  else if ( !RevertToSelf() )
  {
    Common::HandleInternalFailure();
    __debugbreak();
  }
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x180184d94  mov     [rsp-18h+arg_0], rbx
0x180184d99  mov     [rsp-18h+arg_8], rsi
0x180184d9e  mov     [rsp-18h+SecurityDescriptor], r9
0x180184da3  push    rbp
0x180184da4  push    rdi
0x180184da5  push    r14
0x180184da7  mov     rbp, rsp
0x180184daa  sub     rsp, 40h
0x180184dae  mov     rbx, rdx
0x180184db1  mov     rsi, rcx
0x180184db4  xor     r14d, r14d
0x180184db7  mov     [rbp+var_10], r14b
0x180184dbb  mov     [rbp+hToken], r14
0x180184dbf  lea     rcx, [rbp+var_10]; this
0x180184dc3  call    ?Impersonate@ImpersonateSelf@Common@@QEAAJXZ; Common::ImpersonateSelf::Impersonate(void)
0x180184dc8  mov     edi, eax
0x180184dca  test    eax, eax
0x180184dcc  jns     short loc_180184E39
0x180184dce  mov     rcx, [rbp+18h]; this
0x180184dd2  mov     r9d, eax; char *
0x180184dd5  lea     r8, aOnecoreAdminAp_77; "onecore\\admin\\appmodel\\common\\direc"...
0x180184ddc  mov     edx, 673h; void *
0x180184de1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180184de6  nop
0x180184de7  cmp     [rbp+var_10], r14b
0x180184deb  jz      short loc_180184E1C
0x180184ded  mov     rcx, [rbp+hToken]; hToken
0x180184df1  test    rcx, rcx
0x180184df4  jz      short loc_180184E23
0x180184df6  call    cs:__imp_ImpersonateLoggedOnUser
0x180184dfd  nop     dword ptr [rax+rax+00h]
0x180184e02  test    eax, eax
0x180184e04  jnz     short loc_180184E0C
0x180184e06  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x180184e0b  int     3; Trap to Debugger
0x180184e0c  mov     rcx, [rbp+hToken]; hObject
0x180184e10  call    cs:__imp_CloseHandle
0x180184e17  nop     dword ptr [rax+rax+00h]
0x180184e1c  mov     eax, edi
0x180184e1e  jmp     loc_1801851B1
0x180184e23  call    cs:__imp_RevertToSelf
0x180184e2a  nop     dword ptr [rax+rax+00h]
0x180184e2f  test    eax, eax
0x180184e31  jnz     short loc_180184E1C
0x180184e33  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x180184e38  nop
0x180184e39  mov     al, [rbx]
0x180184e3b  neg     al
0x180184e3d  sbb     rcx, rcx
0x180184e40  and     ecx, 4
0x180184e43  add     rcx, 2
0x180184e47  mov     rax, rcx
0x180184e4a  or      rax, 40h
0x180184e4e  cmp     [rbx+9], r14b
0x180184e52  cmovz   rax, rcx
0x180184e56  mov     r8b, [rbx+1]
0x180184e5a  mov     rcx, rax
0x180184e5d  or      rcx, 8
0x180184e61  test    r8b, r8b
0x180184e64  cmovz   rcx, rax
0x180184e68  mov     rdx, rcx
0x180184e6b  mov     r9d, 80h
0x180184e71  or      rdx, r9
0x180184e74  cmp     [rbx+28h], r14b
0x180184e78  cmovz   rdx, rcx
0x180184e7c  mov     rax, rdx
0x180184e7f  or      rax, r9
0x180184e82  cmp     [rbx+5], r14b
0x180184e86  cmovz   rax, rdx
0x180184e8a  mov     rdx, rax
0x180184e8d  bts     rdx, 0Dh
0x180184e92  cmp     [rbx+2Ah], r14b
0x180184e96  cmovz   rdx, rax
0x180184e9a  cmp     [rbx+2], r14b
0x180184e9e  jnz     loc_180185125
0x180184ea4  cmp     [rbx+3], r14b
0x180184ea8  jnz     loc_180185125
0x180184eae  cmp     [rbx+4], r14b
0x180184eb2  jnz     loc_180185125
0x180184eb8  cmp     [rbx+6], r14b
0x180184ebc  jz      loc_1801850B1
0x180184ec2  mov     [rbp+SecurityDescriptor], r14
0x180184ec6  xor     r9d, r9d; SecurityDescriptorSize
0x180184ec9  lea     edx, [r9+1]; StringSDRevision
0x180184ecd  test    r8b, r8b
0x180184ed0  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180184ed4  jz      loc_180184F64
0x180184eda  lea     rcx, aDPaiAOiciFaS15; "D:PAI(A;OICI;FA;;;S-1-5-80-956008885-34"...
0x180184ee1  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180184ee8  nop     dword ptr [rax+rax+00h]
0x180184eed  test    eax, eax
0x180184eef  jnz     loc_180184FEA
0x180184ef5  mov     rcx, [rbp+18h]; this
0x180184ef9  lea     r8, aOnecoreAdminAp_77; "onecore\\admin\\appmodel\\common\\direc"...
0x180184f00  mov     edx, 6A9h; void *
0x180184f05  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180184f0a  mov     ebx, eax
0x180184f0c  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180184f10  call    cs:__imp_LocalFree
0x180184f17  nop     dword ptr [rax+rax+00h]
0x180184f1c  nop
0x180184f1d  cmp     [rbp+var_10], r14b
0x180184f21  jz      loc_180185185
0x180184f27  mov     rcx, [rbp+hToken]; hToken
0x180184f2b  test    rcx, rcx
0x180184f2e  jz      short loc_180184F4A
0x180184f30  call    cs:__imp_ImpersonateLoggedOnUser
0x180184f37  nop     dword ptr [rax+rax+00h]
0x180184f3c  test    eax, eax
0x180184f3e  jnz     loc_180185175
0x180184f44  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x180184f49  int     3; Trap to Debugger
0x180184f4a  call    cs:__imp_RevertToSelf
0x180184f51  nop     dword ptr [rax+rax+00h]
0x180184f56  test    eax, eax
0x180184f58  jnz     loc_180185185
0x180184f5e  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x180184f63  nop
0x180184f64  lea     rcx, aDPaiAOiciFaS15_0; "D:PAI(A;OICI;FA;;;S-1-5-80-956008885-34"...
0x180184f6b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180184f72  nop     dword ptr [rax+rax+00h]
0x180184f77  test    eax, eax
0x180184f79  jnz     short loc_180184FEA
0x180184f7b  mov     rcx, [rbp+18h]; this
0x180184f7f  lea     r8, aOnecoreAdminAp_77; "onecore\\admin\\appmodel\\common\\direc"...
0x180184f86  mov     edx, 6B1h; void *
0x180184f8b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180184f90  mov     ebx, eax
0x180184f92  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180184f96  call    cs:__imp_LocalFree
0x180184f9d  nop     dword ptr [rax+rax+00h]
0x180184fa2  nop
0x180184fa3  cmp     [rbp+var_10], r14b
0x180184fa7  jz      loc_180185185
0x180184fad  mov     rcx, [rbp+hToken]; hToken
0x180184fb1  test    rcx, rcx
0x180184fb4  jz      short loc_180184FD0
0x180184fb6  call    cs:__imp_ImpersonateLoggedOnUser
0x180184fbd  nop     dword ptr [rax+rax+00h]
0x180184fc2  test    eax, eax
0x180184fc4  jnz     loc_180185175
0x180184fca  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x180184fcf  int     3; Trap to Debugger
0x180184fd0  call    cs:__imp_RevertToSelf
0x180184fd7  nop     dword ptr [rax+rax+00h]
0x180184fdc  test    eax, eax
0x180184fde  jnz     loc_180185185
0x180184fe4  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x180184fe9  nop
0x180184fea  mov     r8, [rbp+SecurityDescriptor]
0x180184fee  xor     edx, edx
0x180184ff0  mov     rcx, rsi
0x180184ff3  call    ?ApplySecurityDescriptor@DirectoryACLs@@YAJPEBGW4Flags@1@PEAU_SECURITY_DESCRIPTOR@@@Z; DirectoryACLs::ApplySecurityDescriptor(ushort const *,DirectoryACLs::Flags,_SECURITY_DESCRIPTOR *)
0x180184ff8  mov     ebx, eax
0x180184ffa  test    eax, eax
0x180184ffc  jns     short loc_18018506F
0x180184ffe  mov     rcx, [rbp+18h]; this
0x180185002  mov     r9d, eax; char *
0x180185005  lea     r8, aOnecoreAdminAp_77; "onecore\\admin\\appmodel\\common\\direc"...
0x18018500c  mov     edx, 6B4h; void *
0x180185011  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180185016  nop
0x180185017  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18018501b  call    cs:__imp_LocalFree
0x180185022  nop     dword ptr [rax+rax+00h]
0x180185027  nop
0x180185028  cmp     [rbp+var_10], r14b
0x18018502c  jz      loc_180185185
0x180185032  mov     rcx, [rbp+hToken]; hToken
0x180185036  test    rcx, rcx
0x180185039  jz      short loc_180185055
0x18018503b  call    cs:__imp_ImpersonateLoggedOnUser
0x180185042  nop     dword ptr [rax+rax+00h]
0x180185047  test    eax, eax
0x180185049  jnz     loc_180185175
0x18018504f  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x180185054  int     3; Trap to Debugger
0x180185055  call    cs:__imp_RevertToSelf
0x18018505c  nop     dword ptr [rax+rax+00h]
0x180185061  test    eax, eax
0x180185063  jnz     loc_180185185
0x180185069  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x18018506e  nop
0x18018506f  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180185073  call    cs:__imp_LocalFree
0x18018507a  nop     dword ptr [rax+rax+00h]
0x18018507f  nop
0x180185080  cmp     [rbp+var_10], r14b
0x180185084  jz      loc_1801851AF
0x18018508a  mov     rcx, [rbp+hToken]; hToken
0x18018508e  test    rcx, rcx
0x180185091  jz      loc_1801851C5
0x180185097  call    cs:__imp_ImpersonateLoggedOnUser
0x18018509e  nop     dword ptr [rax+rax+00h]
0x1801850a3  test    eax, eax
0x1801850a5  jnz     loc_18018519F
0x1801850ab  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1801850b0  nop
0x1801850b1  mov     qword ptr [rsp+40h+var_20], r14; int
0x1801850b6  xor     r9d, r9d
0x1801850b9  mov     r8, rdx
0x1801850bc  mov     rdx, rbx
0x1801850bf  mov     rcx, rsi
0x1801850c2  call    ?ApplyPackageACLsHelper@DirectoryACLs@@YAJPEBGPEBVPackageInfoLite@Deployment@Common@@W4Flags@1@_NPEAX@Z; DirectoryACLs::ApplyPackageACLsHelper(ushort const *,Common::Deployment::PackageInfoLite const *,DirectoryACLs::Flags,bool,void *)
0x1801850c7  mov     ebx, eax
0x1801850c9  test    eax, eax
0x1801850cb  jns     short loc_180185080
0x1801850cd  mov     rcx, [rbp+18h]; this
0x1801850d1  mov     r9d, eax; char *
0x1801850d4  lea     r8, aOnecoreAdminAp_77; "onecore\\admin\\appmodel\\common\\direc"...
0x1801850db  mov     edx, 6B8h; void *
0x1801850e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801850e5  nop
0x1801850e6  cmp     [rbp+var_10], r14b
0x1801850ea  jz      loc_180185185
0x1801850f0  mov     rcx, [rbp+hToken]; hToken
0x1801850f4  test    rcx, rcx
0x1801850f7  jz      short loc_18018510F
0x1801850f9  call    cs:__imp_ImpersonateLoggedOnUser
0x180185100  nop     dword ptr [rax+rax+00h]
0x180185105  test    eax, eax
0x180185107  jnz     short loc_180185175
0x180185109  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x18018510e  int     3; Trap to Debugger
0x18018510f  call    cs:__imp_RevertToSelf
0x180185116  nop     dword ptr [rax+rax+00h]
0x18018511b  test    eax, eax
0x18018511d  jnz     short loc_180185185
0x18018511f  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x180185124  nop
0x180185125  mov     rcx, rsi
0x180185128  call    ?ApplyAppXFrameworkPackageRootFolderACLs@DirectoryACLs@@YAJPEBGW4Flags@1@@Z; DirectoryACLs::ApplyAppXFrameworkPackageRootFolderACLs(ushort const *,DirectoryACLs::Flags)
0x18018512d  mov     ebx, eax
0x18018512f  test    eax, eax
0x180185131  jns     loc_180185080
0x180185137  mov     rcx, [rbp+18h]; this
0x18018513b  mov     r9d, eax; char *
0x18018513e  lea     r8, aOnecoreAdminAp_77; "onecore\\admin\\appmodel\\common\\direc"...
0x180185145  mov     edx, 684h; void *
0x18018514a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018514f  nop
0x180185150  cmp     [rbp+var_10], r14b
0x180185154  jz      short loc_180185185
0x180185156  mov     rcx, [rbp+hToken]; hToken
0x18018515a  test    rcx, rcx
0x18018515d  jz      short loc_180185189
0x18018515f  call    cs:__imp_ImpersonateLoggedOnUser
0x180185166  nop     dword ptr [rax+rax+00h]
0x18018516b  test    eax, eax
0x18018516d  jnz     short loc_180185175
0x18018516f  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x180185174  int     3; Trap to Debugger
0x180185175  mov     rcx, [rbp+hToken]; hObject
0x180185179  call    cs:__imp_CloseHandle
0x180185180  nop     dword ptr [rax+rax+00h]
0x180185185  mov     eax, ebx
0x180185187  jmp     short loc_1801851B1
0x180185189  call    cs:__imp_RevertToSelf
0x180185190  nop     dword ptr [rax+rax+00h]
0x180185195  test    eax, eax
0x180185197  jnz     short loc_180185185
0x180185199  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x18018519e  int     3; Trap to Debugger
0x18018519f  mov     rcx, [rbp+hToken]; hObject
0x1801851a3  call    cs:__imp_CloseHandle
0x1801851aa  nop     dword ptr [rax+rax+00h]
0x1801851af  xor     eax, eax
0x1801851b1  mov     rbx, [rsp+40h+arg_0]
0x1801851b6  mov     rsi, [rsp+40h+arg_8]
0x1801851bb  add     rsp, 40h
0x1801851bf  pop     r14
0x1801851c1  pop     rdi
0x1801851c2  pop     rbp
0x1801851c3  retn
0x1801851c5  call    cs:__imp_RevertToSelf
0x1801851cc  nop     dword ptr [rax+rax+00h]
0x1801851d1  test    eax, eax
0x1801851d3  jnz     short loc_1801851AF
0x1801851d5  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
```
