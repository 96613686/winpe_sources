# PrepareAppXActivation

- ea: `0x180050450`
- end: `0x180050760`
- name: `PrepareAppXActivation`
- size: `784`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000cbe4`
- `0x1800263e4`
- `0x1800445ac`
- `0x1800463dc`
- `0x180046980`
- `0x180046cbc`
- `0x180050450`
- `0x180050768`
- `0x180050790`
- `0x180054ff0`
- `0x180056208`
- `0x18005b3c4`
- `0x18005b840`
- `0x18005e570`
- `0x18007638c`
- `0x1800763a8`
- `0x1800763ec`
- `0x18008d368`
- `0x18008d4a4`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005067b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005067b`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageIdFromFullName` at `0x1800504c4`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageIdFromFullName` at `0x180050517`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageIdFromFullName` at `0x1800504c4`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageIdFromFullName` at `0x180050517`
- `ext-ms-win-core-storelicensing-l1-1-0!EnsureStoreLicenseForPackageActivation` at `0x1800506b5`
- `ext-ms-win-core-storelicensing-l1-1-0!EnsureStoreLicenseForPackageActivation` at `0x1800506b5`

## string_xrefs

- `0x1800504de`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x18005052c`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x18005057c`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x18005068d`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x1800506d4`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x1800506f4`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall PrepareAppXActivation(__int64 a1, struct ExtendedLaunchContext **a2)
{
  __int64 v4; // rax
  unsigned int v5; // eax
  int *v6; // rbx
  unsigned int v7; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 result; // rax
  int v11; // r14d
  void *v12; // rbx
  __int64 v13; // rax
  struct ExtendedLaunchContext *v14; // rbx
  __int64 v15; // rsi
  __int64 v16; // r8
  const char *v17; // r9
  int v18; // eax
  void *v19; // rcx
  unsigned int ReturnLength; // [rsp+20h] [rbp-88h]
  int ReturnLengtha; // [rsp+20h] [rbp-88h]
  __int64 v22; // [rsp+30h] [rbp-78h] BYREF
  struct ExtendedLaunchContext *v23; // [rsp+38h] [rbp-70h] BYREF
  char v24[32]; // [rsp+40h] [rbp-68h] BYREF
  char v25[72]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  void *bufferLength; // [rsp+B0h] [rbp+8h] BYREF
  int *v28; // [rsp+C0h] [rbp+18h] BYREF
  void *Block; // [rsp+C8h] [rbp+20h] BYREF

  try
  {
    v4 = std::wstring::wstring(v24, *(_QWORD *)(a1 + 16));
    CreatePackageInformation(&v22, v4);
    if ( (*(_BYTE *)(a1 + 32) & 1) == 0
      && !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 8LL))(v22, *(_QWORD *)(a1 + 24)) )
    {
      LODWORD(bufferLength) = 0;
      v5 = PackageIdFromFullName(*(PCWSTR *)(a1 + 16), 0, (UINT32 *)&bufferLength, 0);
      if ( v5 != 122 && v5 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0xB8,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
          (const char *)v5,
          ReturnLength);
      v6 = (int *)operator new((unsigned int)bufferLength);
      v28 = v6;
      v7 = PackageIdFromFullName(*(PCWSTR *)(a1 + 16), 0, (UINT32 *)&bufferLength, (BYTE *)v6);
      if ( v7 )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xBC,
               (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
               (const char *)v7,
               ReturnLength);
        std::unique_ptr<PACKAGE_ID>::~unique_ptr<PACKAGE_ID>(&v28);
        std::unique_ptr<PackageInformation>::~unique_ptr<PackageInformation>(&v22);
        return v8;
      }
      if ( !VerifyFileIsInApprovedSystemList(*(LPCWCH *)(a1 + 24), v6[1]) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBE,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
          (const char *)0x80070057LL,
          ReturnLength);
      std::unique_ptr<PACKAGE_ID>::~unique_ptr<PACKAGE_ID>(&v28);
    }
    v11 = *(_DWORD *)(a1 + 32);
    v12 = operator new(0xB8u);
    bufferLength = v12;
    v13 = std::wstring::wstring(v25, *(_QWORD *)(a1 + 16));
    v14 = (struct ExtendedLaunchContext *)ExtendedLaunchContext::ExtendedLaunchContext(v12, v13);
    v23 = v14;
    v15 = *(_QWORD *)(a1 + 8);
    _lambda_d1bd32268257bad6c31a192902f222b7_::_lambda_d1bd32268257bad6c31a192902f222b7_(
      (_lambda_d1bd32268257bad6c31a192902f222b7_ *)&bufferLength,
      v14);
    if ( !(unsigned int)_lambda_d1bd32268257bad6c31a192902f222b7_::operator()(&bufferLength, v16) && v15 )
      _lambda_d1bd32268257bad6c31a192902f222b7_::operator()(&bufferLength, v15);
    *((_DWORD *)v14 + 9) = *(_DWORD *)(a1 + 36);
    if ( (v11 & 4) == 0 && (unsigned __int8)IsEnsureStoreLicenseForPackageActivationPresent() )
    {
      wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, *(_QWORD *)a1);
      LODWORD(bufferLength) = 0;
      LODWORD(v28) = 0;
      if ( !GetTokenInformation(*(HANDLE *)a1, TokenSessionId, &bufferLength, 4u, (PDWORD)&v28) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x41,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
          v17);
      v18 = EnsureStoreLicenseForPackageActivation(
              *(_QWORD *)(a1 + 16),
              (unsigned int)bufferLength,
              *(_QWORD *)Block,
              0);
      if ( v18 < 0 && (v18 & 0x20000000) != 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD4,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
          (const char *)(v18 & 0xDFFFFFFF),
          ReturnLengtha);
      if ( v18 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0xD8,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
          (const char *)(unsigned int)v18,
          ReturnLengtha);
      v19 = Block;
      Block = 0;
      if ( v19 )
        operator delete(v19);
    }
    v23 = 0;
    *a2 = v14;
    std::unique_ptr<ExtendedLaunchContext>::~unique_ptr<ExtendedLaunchContext>(&v23);
    std::unique_ptr<PackageInformation>::~unique_ptr<PackageInformation>(&v22);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(bufferLength) = wil::details::in1diag3::Return_CaughtException(
                              retaddr,
                              (void *)0xDD,
                              (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionl"
                                            "ib\\activationextensions.cpp",
                              v9);
    return (unsigned int)bufferLength;
  }
  return result;
}

```

## disassembly

```asm
0x180050450  push    rbx
0x180050452  push    rsi
0x180050453  push    rdi
0x180050454  push    r14
0x180050456  push    r15
0x180050458  sub     rsp, 80h
0x18005045f  mov     r15, rdx
0x180050462  mov     rdi, rcx
0x180050465  mov     rdx, [rcx+10h]
0x180050469  lea     rcx, [rsp+0A8h+var_68]
0x18005046e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180050473  mov     rdx, rax
0x180050476  lea     rcx, [rsp+0A8h+var_78]
0x18005047b  call    ?CreatePackageInformation@@YA?AV?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; CreatePackageInformation(std::wstring)
0x180050480  nop
0x180050481  test    byte ptr [rdi+20h], 1
0x180050485  jnz     loc_18005059B
0x18005048b  mov     rcx, [rsp+0A8h+var_78]
0x180050490  mov     rax, [rcx]
0x180050493  mov     rdx, [rdi+18h]
0x180050497  mov     rax, [rax+8]
0x18005049b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504a0  test    al, al
0x1800504a2  jnz     loc_18005059B
0x1800504a8  mov     dword ptr [rsp+0A8h+bufferLength], 0
0x1800504b3  xor     r9d, r9d; buffer
0x1800504b6  lea     r8, [rsp+0A8h+bufferLength]; bufferLength
0x1800504be  xor     edx, edx; flags
0x1800504c0  mov     rcx, [rdi+10h]; packageFullName
0x1800504c4  call    cs:__imp_PackageIdFromFullName
0x1800504ca  cmp     eax, 7Ah ; 'z'
0x1800504cd  jz      short loc_1800504EF
0x1800504cf  mov     rcx, [rsp+0A8h]; this
0x1800504d7  test    eax, eax
0x1800504d9  jz      short loc_1800504EF
0x1800504db  mov     r9d, eax; char *
0x1800504de  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800504e5  mov     edx, 0B8h; void *
0x1800504ea  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800504ef  mov     ecx, dword ptr [rsp+0A8h+bufferLength]; Size
0x1800504f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800504fb  mov     rbx, rax
0x1800504fe  mov     [rsp+0A8h+arg_10], rax
0x180050506  mov     r9, rax; buffer
0x180050509  lea     r8, [rsp+0A8h+bufferLength]; bufferLength
0x180050511  xor     edx, edx; flags
0x180050513  mov     rcx, [rdi+10h]; packageFullName
0x180050517  call    cs:__imp_PackageIdFromFullName
0x18005051d  test    eax, eax
0x18005051f  jz      short loc_18005055E
0x180050521  mov     rcx, [rsp+0A8h]; this
0x180050529  mov     r9d, eax; char *
0x18005052c  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180050533  mov     edx, 0BCh; void *
0x180050538  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005053d  mov     ebx, eax
0x18005053f  lea     rcx, [rsp+0A8h+arg_10]
0x180050547  call    ??1?$unique_ptr@UPACKAGE_ID@@U?$default_delete@UPACKAGE_ID@@@std@@@std@@QEAA@XZ; std::unique_ptr<PACKAGE_ID>::~unique_ptr<PACKAGE_ID>(void)
0x18005054c  nop
0x18005054d  lea     rcx, [rsp+0A8h+var_78]
0x180050552  call    ??1?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@QEAA@XZ; std::unique_ptr<PackageInformation>::~unique_ptr<PackageInformation>(void)
0x180050557  mov     eax, ebx
0x180050559  jmp     loc_180050750
0x18005055e  mov     edx, [rbx+4]
0x180050561  mov     rcx, [rdi+18h]; lpString1
0x180050565  call    VerifyFileIsInApprovedSystemList
0x18005056a  mov     rcx, [rsp+0A8h]; this
0x180050572  test    al, al
0x180050574  jnz     short loc_18005058E
0x180050576  mov     r9d, 80070057h; char *
0x18005057c  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180050583  mov     edx, 0BEh; void *
0x180050588  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005058e  lea     rcx, [rsp+0A8h+arg_10]
0x180050596  call    ??1?$unique_ptr@UPACKAGE_ID@@U?$default_delete@UPACKAGE_ID@@@std@@@std@@QEAA@XZ; std::unique_ptr<PACKAGE_ID>::~unique_ptr<PACKAGE_ID>(void)
0x18005059b  mov     r14d, [rdi+20h]
0x18005059f  mov     ecx, 0B8h; Size
0x1800505a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800505a9  mov     rbx, rax
0x1800505ac  mov     [rsp+0A8h+bufferLength], rax
0x1800505b4  mov     rdx, [rdi+10h]
0x1800505b8  lea     rcx, [rsp+0A8h+var_48]
0x1800505bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800505c2  mov     rdx, rax
0x1800505c5  mov     rcx, rbx
0x1800505c8  call    ??0ExtendedLaunchContext@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ExtendedLaunchContext::ExtendedLaunchContext(std::wstring)
0x1800505cd  mov     rbx, rax
0x1800505d0  mov     [rsp+0A8h+var_70], rax
0x1800505d5  mov     rsi, [rdi+8]
0x1800505d9  mov     r8, [rdi]
0x1800505dc  mov     rdx, rax; struct ExtendedLaunchContext *
0x1800505df  lea     rcx, [rsp+0A8h+bufferLength]; this
0x1800505e7  call    ??0_lambda_d1bd32268257bad6c31a192902f222b7_@@QEAA@PEAVExtendedLaunchContext@@@Z; _lambda_d1bd32268257bad6c31a192902f222b7_::_lambda_d1bd32268257bad6c31a192902f222b7_(ExtendedLaunchContext *)
0x1800505ec  mov     rdx, r8
0x1800505ef  lea     rcx, [rsp+0A8h+bufferLength]
0x1800505f7  call    ??R_lambda_d1bd32268257bad6c31a192902f222b7_@@QEBA@PEAX@Z; _lambda_d1bd32268257bad6c31a192902f222b7_::operator()(void *)
0x1800505fc  test    eax, eax
0x1800505fe  jnz     short loc_180050615
0x180050600  test    rsi, rsi
0x180050603  jz      short loc_180050615
0x180050605  mov     rdx, rsi
0x180050608  lea     rcx, [rsp+0A8h+bufferLength]
0x180050610  call    ??R_lambda_d1bd32268257bad6c31a192902f222b7_@@QEBA@PEAX@Z; _lambda_d1bd32268257bad6c31a192902f222b7_::operator()(void *)
0x180050615  mov     eax, [rdi+24h]
0x180050618  mov     [rbx+24h], eax
0x18005061b  test    r14b, 4
0x18005061f  jnz     loc_180050724
0x180050625  call    IsEnsureStoreLicenseForPackageActivationPresent
0x18005062a  test    al, al
0x18005062c  jz      loc_180050724
0x180050632  mov     rdx, [rdi]
0x180050635  lea     rcx, [rsp+0A8h+Block]
0x18005063d  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x180050642  nop
0x180050643  mov     dword ptr [rsp+0A8h+bufferLength], 0
0x18005064e  mov     dword ptr [rsp+0A8h+arg_10], 0
0x180050659  lea     rax, [rsp+0A8h+arg_10]
0x180050661  mov     qword ptr [rsp+0A8h+ReturnLength], rax; int
0x180050666  mov     r9d, 4; TokenInformationLength
0x18005066c  lea     r8, [rsp+0A8h+bufferLength]; TokenInformation
0x180050674  lea     edx, [r9+8]; TokenInformationClass
0x180050678  mov     rcx, [rdi]; TokenHandle
0x18005067b  call    cs:__imp_GetTokenInformation
0x180050681  mov     rcx, [rsp+0A8h]; this
0x180050689  test    eax, eax
0x18005068b  jnz     short loc_18005069C
0x18005068d  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180050694  lea     edx, [rax+41h]; void *
0x180050697  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005069c  xor     r9d, r9d
0x18005069f  mov     r8, [rsp+0A8h+Block]
0x1800506a7  mov     r8, [r8]
0x1800506aa  mov     edx, dword ptr [rsp+0A8h+bufferLength]
0x1800506b1  mov     rcx, [rdi+10h]
0x1800506b5  call    cs:__imp_EnsureStoreLicenseForPackageActivation
0x1800506bb  test    eax, eax
0x1800506bd  jns     short loc_1800506E5
0x1800506bf  bt      eax, 1Dh
0x1800506c3  jnb     short loc_1800506E5
0x1800506c5  btr     eax, 1Dh
0x1800506c9  mov     rcx, [rsp+0A8h]; this
0x1800506d1  mov     r9d, eax; char *
0x1800506d4  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800506db  mov     edx, 0D4h; void *
0x1800506e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800506e5  mov     rcx, [rsp+0A8h]; this
0x1800506ed  test    eax, eax
0x1800506ef  jns     short loc_180050706
0x1800506f1  mov     r9d, eax; char *
0x1800506f4  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800506fb  mov     edx, 0D8h; void *
0x180050700  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180050706  mov     rcx, [rsp+0A8h+Block]; Block
0x18005070e  mov     [rsp+0A8h+Block], 0
0x18005071a  test    rcx, rcx
0x18005071d  jz      short loc_180050724
0x18005071f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180050724  mov     [rsp+0A8h+var_70], 0
0x18005072d  mov     [r15], rbx
0x180050730  lea     rcx, [rsp+0A8h+var_70]
0x180050735  call    ??1?$unique_ptr@VExtendedLaunchContext@@U?$default_delete@VExtendedLaunchContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<ExtendedLaunchContext>::~unique_ptr<ExtendedLaunchContext>(void)
0x18005073a  nop
0x18005073b  lea     rcx, [rsp+0A8h+var_78]
0x180050740  call    ??1?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@QEAA@XZ; std::unique_ptr<PackageInformation>::~unique_ptr<PackageInformation>(void)
0x180050745  xor     eax, eax
0x180050747  jmp     short loc_180050750
0x180050749  mov     eax, dword ptr [rsp+0A8h+bufferLength]
0x180050750  add     rsp, 80h
0x180050757  pop     r15
0x180050759  pop     r14
0x18005075b  pop     rdi
0x18005075c  pop     rsi
0x18005075d  pop     rbx
0x18005075e  retn
```
