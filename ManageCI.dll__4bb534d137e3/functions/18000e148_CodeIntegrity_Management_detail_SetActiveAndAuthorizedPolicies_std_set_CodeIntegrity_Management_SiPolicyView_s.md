# CodeIntegrity::Management::detail::SetActiveAndAuthorizedPolicies(std::set<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>> *)

- ea: `0x18000e148`
- end: `0x18000e3eb`
- name: `?SetActiveAndAuthorizedPolicies@detail@Management@CodeIntegrity@@YAXPEAV?$set@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@@std@@@Z`
- size: `675`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014ee0`

## callees

- `0x180009e50`
- `0x18000a308`
- `0x18000d470`
- `0x18000de20`
- `0x18000de54`
- `0x18000def4`
- `0x18000e148`
- `0x18000e464`
- `0x1800235a0`
- `0x180023780`
- `0x180023fa8`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e1ea`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e36e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e1ea`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e36e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e1cb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e34b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e1cb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e34b`
- `ntdll!NtQuerySystemInformation` at `0x18000e19e`
- `ntdll!NtQuerySystemInformation` at `0x18000e238`
- `ntdll!NtQuerySystemInformation` at `0x18000e19e`
- `ntdll!NtQuerySystemInformation` at `0x18000e238`

## string_xrefs

- `0x18000e39d`: `onecore\base\ci\management\dll\ntextensions.cpp`
- `0x18000e3b2`: `onecore\base\ci\management\dll\ntextensions.cpp`
- `0x18000e3c4`: `onecore\base\ci\management\dll\ntextensions.cpp`
- `0x18000e3d9`: `onecore\base\ci\management\dll\ntextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CodeIntegrity::Management::detail::SetActiveAndAuthorizedPolicies(void **a1)
{
  void *v2; // rbx
  int inited; // eax
  unsigned int v4; // eax
  const char *v5; // r9
  unsigned __int64 v6; // rdx
  void **v7; // rax
  unsigned __int64 v8; // rdx
  NTSTATUS v9; // eax
  int v10; // eax
  unsigned __int64 v11; // rbx
  __int64 v12; // rdx
  unsigned __int64 v13; // rsi
  _BYTE *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  void *v18; // [rsp+20h] [rbp-60h] BYREF
  _BYTE v19[8]; // [rsp+28h] [rbp-58h] BYREF
  _BYTE v20[8]; // [rsp+30h] [rbp-50h] BYREF
  __int128 v21; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v22[16]; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v23[16]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v24; // [rsp+68h] [rbp-18h]
  __int64 v25; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  __int64 v27; // [rsp+A8h] [rbp+28h] BYREF
  ULONG ReturnLength; // [rsp+B0h] [rbp+30h] BYREF
  void *v29; // [rsp+B8h] [rbp+38h] BYREF

  v2 = 0;
  v18 = 0;
  LODWORD(v27) = 0;
  ReturnLength = 0;
  v24 = 0;
  v25 = 0;
  inited = SIPolicyInitSystem(&v27);
  if ( inited < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x3D,
      (int)"onecore\\base\\ci\\management\\dll\\ntextensions.cpp",
      (const char *)(unsigned int)inited,
      (int)v18);
  BYTE1(v27) = 1;
  v4 = NtQuerySystemInformation(SystemVerifierFaultsInformation|SystemHandleInformation|0x80, 0, 0, &ReturnLength);
  v5 = 0;
  if ( v4 != -1073741820 )
    v5 = (const char *)v4;
  if ( (int)v5 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x4C,
      (int)"onecore\\base\\ci\\management\\dll\\ntextensions.cpp",
      v5,
      (int)v18);
  if ( ReturnLength )
  {
    v7 = (void **)std::make_unique<unsigned char [0],0>(&v29, ReturnLength);
    if ( &v18 != v7 )
    {
      v2 = *v7;
      *v7 = 0;
      v18 = v2;
    }
    std::unique_ptr<_SIPOLICY_FILE_ITEM [0]>::~unique_ptr<_SIPOLICY_FILE_ITEM [0]>(&v29, v8);
    v9 = NtQuerySystemInformation(
           SystemVerifierFaultsInformation|SystemHandleInformation|0x80,
           v2,
           ReturnLength,
           &ReturnLength);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x5B,
        (int)"onecore\\base\\ci\\management\\dll\\ntextensions.cpp",
        (const char *)(unsigned int)v9,
        (int)v18);
    v10 = SIPolicyInitializeFromSerializedPolicies(v2, ReturnLength);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x63,
        (int)"onecore\\base\\ci\\management\\dll\\ntextensions.cpp",
        (const char *)(unsigned int)v10,
        (int)v18);
    v11 = 0;
    if ( g_NumberOfSiPolicies )
    {
      v12 = g_SiPolicyHandles;
      do
      {
        v13 = v12 + 8 * v11;
        v21 = *(_OWORD *)((-(__int64)(*(_DWORD *)(*(_QWORD *)v13 + 40LL) < 6u) & 0xFFFFFFFFFFFFFD50uLL)
                        + *(_QWORD *)v13
                        + 704);
        std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>,0>>::find<_GUID,std::less<void>,0>(
          a1,
          &v29,
          &v21);
        if ( v29 == *a1 )
        {
          std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>,0>>::emplace<void * &>(
            a1,
            v22,
            v13);
          v14 = *(_BYTE **)std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>,0>>::find<_GUID,std::less<void>,0>(
                             a1,
                             v19,
                             &v21);
        }
        else
        {
          v15 = std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyView>>::_Extract(a1);
          std::_Tree_node<CodeIntegrity::Management::SiPolicyView,void *>::_Freenode<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyView,void *>>>(
            v16,
            v15);
          std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>,0>>::emplace<void * &>(
            a1,
            v23,
            g_SiPolicyHandles + 8 * v11);
          v17 = std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>,0>>::find<_GUID,std::less<void>,0>(
                  a1,
                  v20,
                  &v21);
          v14 = *(_BYTE **)v17;
          *(_BYTE *)(*(_QWORD *)v17 + 122LL) = 1;
        }
        v29 = v14;
        v14[120] = 1;
        v12 = g_SiPolicyHandles;
        if ( (*(_BYTE *)(*(_QWORD *)(g_SiPolicyHandles + 8 * v11) + 768LL) & 0x20) != 0 )
          v14[121] = 1;
        ++v11;
      }
      while ( v11 < (unsigned int)g_NumberOfSiPolicies );
    }
    RtlAcquireSRWLockExclusive(&qword_180039820);
    v27 = qword_1800395E0;
    qword_1800395E0 = 0;
    RtlReleaseSRWLockExclusive(&qword_180039820);
    SIPolicyReleaseState(&v27);
  }
  else
  {
    RtlAcquireSRWLockExclusive(&qword_180039820);
    v27 = qword_1800395E0;
    qword_1800395E0 = 0;
    RtlReleaseSRWLockExclusive(&qword_180039820);
    SIPolicyReleaseState(&v27);
  }
  std::unique_ptr<_SIPOLICY_FILE_ITEM [0]>::~unique_ptr<_SIPOLICY_FILE_ITEM [0]>(&v18, v6);
}

```

## disassembly

```asm
0x18000e148  mov     [rsp-18h+arg_0], rbx
0x18000e14d  push    rbp
0x18000e14e  push    rsi
0x18000e14f  push    rdi
0x18000e150  mov     rbp, rsp
0x18000e153  sub     rsp, 80h
0x18000e15a  mov     rdi, rcx
0x18000e15d  xor     ebx, ebx
0x18000e15f  mov     [rbp+var_60], rbx
0x18000e163  mov     dword ptr [rbp+arg_8], ebx
0x18000e166  mov     [rbp+ReturnLength], ebx
0x18000e169  xorps   xmm0, xmm0
0x18000e16c  movdqu  [rbp+var_18], xmm0
0x18000e171  mov     [rbp+var_8], rbx
0x18000e175  lea     rcx, [rbp+arg_8]
0x18000e179  call    SIPolicyInitSystem
0x18000e17e  mov     rcx, [rbp+18h]; this
0x18000e182  test    eax, eax
0x18000e184  js      loc_18000E3AF
0x18000e18a  mov     byte ptr [rbp+arg_8+1], 1
0x18000e18e  lea     r9, [rbp+ReturnLength]; ReturnLength
0x18000e192  xor     r8d, r8d; SystemInformationLength
0x18000e195  xor     edx, edx; SystemInformation
0x18000e197  mov     esi, 0F1h
0x18000e19c  mov     ecx, esi; SystemInformationClass
0x18000e19e  call    cs:__imp_NtQuerySystemInformation
0x18000e1a4  xor     r9d, r9d
0x18000e1a7  cmp     eax, 0C0000004h
0x18000e1ac  cmovnz  r9d, eax; char *
0x18000e1b0  mov     rcx, [rbp+18h]; this
0x18000e1b4  test    r9d, r9d
0x18000e1b7  js      loc_18000E3C4
0x18000e1bd  mov     eax, [rbp+ReturnLength]
0x18000e1c0  test    eax, eax
0x18000e1c2  jnz     short loc_18000E1FF
0x18000e1c4  lea     rcx, qword_180039820
0x18000e1cb  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000e1d1  mov     rax, cs:qword_1800395E0
0x18000e1d8  mov     [rbp+arg_8], rax
0x18000e1dc  mov     cs:qword_1800395E0, rbx
0x18000e1e3  lea     rcx, qword_180039820
0x18000e1ea  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e1f0  lea     rcx, [rbp+arg_8]
0x18000e1f4  call    SIPolicyReleaseState
0x18000e1f9  nop
0x18000e1fa  jmp     loc_18000E37E
0x18000e1ff  mov     rdx, rax
0x18000e202  lea     rcx, [rbp+arg_18]
0x18000e206  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x18000e20b  lea     rcx, [rbp+var_60]
0x18000e20f  cmp     rcx, rax
0x18000e212  jz      short loc_18000E222
0x18000e214  mov     rbx, [rax]
0x18000e217  mov     qword ptr [rax], 0
0x18000e21e  mov     [rbp+var_60], rbx
0x18000e222  lea     rcx, [rbp+arg_18]
0x18000e226  call    ??1?$unique_ptr@$$BY0A@U_SIPOLICY_FILE_ITEM@@U?$default_delete@$$BY0A@U_SIPOLICY_FILE_ITEM@@@std@@@std@@QEAA@XZ; std::unique_ptr<_SIPOLICY_FILE_ITEM [0]>::~unique_ptr<_SIPOLICY_FILE_ITEM [0]>(void)
0x18000e22b  lea     r9, [rbp+ReturnLength]; ReturnLength
0x18000e22f  mov     r8d, [rbp+ReturnLength]; SystemInformationLength
0x18000e233  mov     rdx, rbx; SystemInformation
0x18000e236  mov     ecx, esi; SystemInformationClass
0x18000e238  call    cs:__imp_NtQuerySystemInformation
0x18000e23e  mov     rcx, [rbp+18h]; this
0x18000e242  test    eax, eax
0x18000e244  js      loc_18000E3D6
0x18000e24a  mov     edx, [rbp+ReturnLength]
0x18000e24d  mov     rcx, rbx
0x18000e250  call    SIPolicyInitializeFromSerializedPolicies
0x18000e255  mov     rcx, [rbp+18h]; this
0x18000e259  test    eax, eax
0x18000e25b  js      loc_18000E39A
0x18000e261  xor     ebx, ebx
0x18000e263  cmp     cs:g_NumberOfSiPolicies, ebx
0x18000e269  jbe     loc_18000E344
0x18000e26f  mov     rdx, cs:g_SiPolicyHandles
0x18000e276  lea     rsi, [rdx+rbx*8]
0x18000e27a  mov     rcx, [rsi]
0x18000e27d  cmp     dword ptr [rcx+28h], 6
0x18000e281  sbb     rax, rax
0x18000e284  and     rax, 0FFFFFFFFFFFFFD50h
0x18000e28a  movups  xmm0, xmmword ptr [rax+rcx+2C0h]
0x18000e292  movdqu  [rbp+var_48], xmm0
0x18000e297  lea     r8, [rbp+var_48]
0x18000e29b  lea     rdx, [rbp+arg_18]
0x18000e29f  mov     rcx, rdi
0x18000e2a2  call    ??$find@U_GUID@@U?$less@X@std@@$0A@@?$_Tree@V?$_Tset_traits@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VSiPolicyView@Management@CodeIntegrity@@@std@@@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>,0>>::find<_GUID,std::less<void>,0>(_GUID const &)
0x18000e2a7  mov     rdx, [rbp+arg_18]
0x18000e2ab  mov     rcx, rdi
0x18000e2ae  cmp     rdx, [rdi]
0x18000e2b1  jnz     short loc_18000E2D4
0x18000e2b3  mov     r8, rsi
0x18000e2b6  lea     rdx, [rbp+var_38]
0x18000e2ba  call    ??$emplace@AEAPEAX@?$_Tree@V?$_Tset_traits@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VSiPolicyView@Management@CodeIntegrity@@@std@@@std@@@std@@_N@1@AEAPEAX@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>,0>>::emplace<void * &>(void * &)
0x18000e2bf  lea     r8, [rbp+var_48]
0x18000e2c3  lea     rdx, [rbp+var_58]
0x18000e2c7  mov     rcx, rdi
0x18000e2ca  call    ??$find@U_GUID@@U?$less@X@std@@$0A@@?$_Tree@V?$_Tset_traits@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VSiPolicyView@Management@CodeIntegrity@@@std@@@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>,0>>::find<_GUID,std::less<void>,0>(_GUID const &)
0x18000e2cf  mov     rcx, [rax]
0x18000e2d2  jmp     short loc_18000E30F
0x18000e2d4  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@VSiPolicyView@Management@CodeIntegrity@@@std@@@std@@QEAAPEAU?$_Tree_node@VSiPolicyView@Management@CodeIntegrity@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VSiPolicyView@Management@CodeIntegrity@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyView>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyView>>,std::_Iterator_base0>)
0x18000e2d9  mov     rdx, rax
0x18000e2dc  call    ??$_Freenode@V?$allocator@U?$_Tree_node@VSiPolicyView@Management@CodeIntegrity@@PEAX@std@@@std@@@?$_Tree_node@VSiPolicyView@Management@CodeIntegrity@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@VSiPolicyView@Management@CodeIntegrity@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<CodeIntegrity::Management::SiPolicyView,void *>::_Freenode<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyView,void *>>>(std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyView,void *>> &,std::_Tree_node<CodeIntegrity::Management::SiPolicyView,void *> *)
0x18000e2e1  mov     rax, cs:g_SiPolicyHandles
0x18000e2e8  lea     r8, [rax+rbx*8]
0x18000e2ec  lea     rdx, [rbp+var_28]
0x18000e2f0  mov     rcx, rdi
0x18000e2f3  call    ??$emplace@AEAPEAX@?$_Tree@V?$_Tset_traits@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VSiPolicyView@Management@CodeIntegrity@@@std@@@std@@@std@@_N@1@AEAPEAX@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>,0>>::emplace<void * &>(void * &)
0x18000e2f8  lea     r8, [rbp+var_48]
0x18000e2fc  lea     rdx, [rbp+var_50]
0x18000e300  mov     rcx, rdi
0x18000e303  call    ??$find@U_GUID@@U?$less@X@std@@$0A@@?$_Tree@V?$_Tset_traits@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VSiPolicyView@Management@CodeIntegrity@@@std@@@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>,0>>::find<_GUID,std::less<void>,0>(_GUID const &)
0x18000e308  mov     rcx, [rax]
0x18000e30b  mov     byte ptr [rcx+7Ah], 1
0x18000e30f  mov     rax, rcx
0x18000e312  mov     [rbp+arg_18], rcx
0x18000e316  mov     byte ptr [rcx+78h], 1
0x18000e31a  mov     rdx, cs:g_SiPolicyHandles
0x18000e321  mov     rax, [rdx+rbx*8]
0x18000e325  test    byte ptr [rax+300h], 20h
0x18000e32c  jz      short loc_18000E332
0x18000e32e  mov     byte ptr [rcx+79h], 1
0x18000e332  inc     rbx
0x18000e335  mov     eax, cs:g_NumberOfSiPolicies
0x18000e33b  cmp     rbx, rax
0x18000e33e  jb      loc_18000E276
0x18000e344  lea     rcx, qword_180039820
0x18000e34b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000e351  mov     rax, cs:qword_1800395E0
0x18000e358  mov     [rbp+arg_8], rax
0x18000e35c  mov     cs:qword_1800395E0, 0
0x18000e367  lea     rcx, qword_180039820
0x18000e36e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e374  lea     rcx, [rbp+arg_8]
0x18000e378  call    SIPolicyReleaseState
0x18000e37d  nop
0x18000e37e  lea     rcx, [rbp+var_60]
0x18000e382  call    ??1?$unique_ptr@$$BY0A@U_SIPOLICY_FILE_ITEM@@U?$default_delete@$$BY0A@U_SIPOLICY_FILE_ITEM@@@std@@@std@@QEAA@XZ; std::unique_ptr<_SIPOLICY_FILE_ITEM [0]>::~unique_ptr<_SIPOLICY_FILE_ITEM [0]>(void)
0x18000e387  mov     rbx, [rsp+80h+arg_0]
0x18000e38f  add     rsp, 80h
0x18000e396  pop     rdi
0x18000e397  pop     rsi
0x18000e398  pop     rbp
0x18000e399  retn
0x18000e39a  mov     r9d, eax; char *
0x18000e39d  lea     r8, aOnecoreBaseCiM_0; "onecore\\base\\ci\\management\\dll\\nte"...
0x18000e3a4  mov     edx, 63h ; 'c'; void *
0x18000e3a9  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18000e3af  mov     r9d, eax; char *
0x18000e3b2  lea     r8, aOnecoreBaseCiM_0; "onecore\\base\\ci\\management\\dll\\nte"...
0x18000e3b9  mov     edx, 3Dh ; '='; void *
0x18000e3be  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18000e3c4  lea     r8, aOnecoreBaseCiM_0; "onecore\\base\\ci\\management\\dll\\nte"...
0x18000e3cb  mov     edx, 4Ch ; 'L'; void *
0x18000e3d0  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18000e3d6  mov     r9d, eax; char *
0x18000e3d9  lea     r8, aOnecoreBaseCiM_0; "onecore\\base\\ci\\management\\dll\\nte"...
0x18000e3e0  mov     edx, 5Bh ; '['; void *
0x18000e3e5  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
