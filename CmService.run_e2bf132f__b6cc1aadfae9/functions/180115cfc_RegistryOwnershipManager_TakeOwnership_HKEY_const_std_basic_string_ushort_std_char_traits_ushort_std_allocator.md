# RegistryOwnershipManager::TakeOwnership(HKEY__ * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180115cfc`
- end: `0x180116100`
- name: `?TakeOwnership@RegistryOwnershipManager@@QEAAJQEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1028`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801158d0`

## callees

- `0x180004bd0`
- `0x1800051b0`
- `0x1800067f0`
- `0x18000da68`
- `0x18000da88`
- `0x18003a8d4`
- `0x18003d0b8`
- `0x18003de70`
- `0x18003e87c`
- `0x180114bd4`
- `0x180115cfc`
- `0x180116408`
- `0x180116b48`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180115ef6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180115fa4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180115ef6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180115fa4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180115f4d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180115ff6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180115f4d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180115ff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115ee5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115ee5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115f93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180115d52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180115f04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180115fb2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180115d52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180115f04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180115fb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180115d44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180115d44`

## string_xrefs

- `0x180115d92`: `SeTakeOwnershipPrivilege`
- `0x180115dc8`: `SeRestorePrivilege`
- `0x180115ea4`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`
- `0x180115f65`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`
- `0x18011600e`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`
- `0x1801160a2`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall RegistryOwnershipManager::TakeOwnership(__int64 a1, __int64 a2, _QWORD *a3)
{
  HKEY v5; // r14
  DWORD LastError; // ebx
  char *v7; // rbx
  __int64 *v8; // r14
  int v9; // eax
  unsigned int v10; // ebx
  void *v12; // r15
  DWORD v13; // ebx
  const char *v14; // r9
  unsigned int v15; // ebx
  void *v16; // r15
  DWORD v17; // ebx
  const char *v18; // r9
  unsigned int v19; // ebx
  __int64 v20; // r8
  int v21; // ebx
  DWORD nSubAuthority2; // [rsp+20h] [rbp-108h]
  DWORD nSubAuthority2a; // [rsp+20h] [rbp-108h]
  char *v24; // [rsp+60h] [rbp-C8h] BYREF
  char *v25; // [rsp+68h] [rbp-C0h]
  char *v26; // [rsp+70h] [rbp-B8h]
  char **v27; // [rsp+78h] [rbp-B0h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp-A8h] BYREF
  __int128 v29; // [rsp+88h] [rbp-A0h] BYREF
  char **v30; // [rsp+98h] [rbp-90h]
  __int64 v31; // [rsp+A0h] [rbp-88h]
  __int128 v32; // [rsp+B0h] [rbp-78h] BYREF
  __int64 v33; // [rsp+C0h] [rbp-68h]
  __int64 v34; // [rsp+C8h] [rbp-60h]
  __int128 v35; // [rsp+D0h] [rbp-58h] BYREF
  __int64 v36; // [rsp+E0h] [rbp-48h]
  __int64 v37; // [rsp+E8h] [rbp-40h]
  __int64 v38; // [rsp+F0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v5 = *(HKEY *)a1;
  if ( *(_QWORD *)a1 )
  {
    LastError = GetLastError();
    RegCloseKey(v5);
    SetLastError(LastError);
  }
  *(_QWORD *)a1 = -2147483646;
  std::wstring::operator=(a1 + 8, a3);
  v32 = 0;
  v33 = 0;
  v34 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v32, L"SeTakeOwnershipPrivilege", 24);
  v35 = 0;
  v36 = 0;
  v37 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v35, L"SeRestorePrivilege", 18);
  v7 = (char *)operator new(0x40u);
  v24 = v7;
  v25 = v7;
  v26 = v7 + 64;
  v27 = &v24;
  v8 = (__int64 *)&v32;
  *(_QWORD *)&v29 = v7;
  *((_QWORD *)&v29 + 1) = v7;
  v30 = &v24;
  while ( v8 != &v38 )
  {
    std::wstring::wstring(v7, v8);
    v7 += 32;
    *((_QWORD *)&v29 + 1) = v7;
    v8 += 4;
  }
  v25 = v7;
  `eh vector destructor iterator'(&v32, 0x20u, 2u, std::wstring::~wstring);
  v9 = RegistryOwnershipManager::EnablePrivileges(a1, &v24);
  v10 = v9;
  if ( v9 >= 0 )
  {
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    v12 = *(void **)(a1 + 40);
    if ( v12 )
    {
      v13 = GetLastError();
      FreeSid(v12);
      SetLastError(v13);
    }
    *(_QWORD *)(a1 + 40) = 0;
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, (PSID *)(a1 + 40)) )
    {
      v16 = *(void **)(a1 + 48);
      if ( v16 )
      {
        v17 = GetLastError();
        FreeSid(v16);
        SetLastError(v17);
      }
      *(_QWORD *)(a1 + 48) = 0;
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, (PSID *)(a1 + 48)) )
      {
        if ( a3[3] > 7u )
          a3 = (_QWORD *)*a3;
        v29 = 0;
        v30 = 0;
        v31 = 0;
        v20 = -1;
        do
          ++v20;
        while ( *((_WORD *)a3 + v20) );
        std::wstring::_Construct<1,unsigned short const *>(&v29, a3, v20);
        v21 = RegistryOwnershipManager::TakeOwnershipRecursive(a1, &v29);
        std::wstring::~wstring(&v29);
        if ( v21 >= 0 )
        {
          std::vector<std::wstring>::_Tidy(&v24);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
            (const char *)(unsigned int)v21,
            nSubAuthority2a);
          std::vector<std::wstring>::_Tidy(&v24);
          return (unsigned int)v21;
        }
      }
      else
      {
        v19 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x31,
                (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
                v18);
        std::vector<std::wstring>::_Tidy(&v24);
        return v19;
      }
    }
    else
    {
      v15 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x2E,
              (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
              v14);
      std::vector<std::wstring>::_Tidy(&v24);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
      (const char *)(unsigned int)v9,
      nSubAuthority2);
    std::vector<std::wstring>::_Tidy(&v24);
    return v10;
  }
}

```

## disassembly

```asm
0x180115cfc  mov     [rsp+arg_8], rbx
0x180115d01  push    rsi
0x180115d02  push    rdi
0x180115d03  push    r12
0x180115d05  push    r14
0x180115d07  push    r15
0x180115d09  sub     rsp, 100h
0x180115d10  mov     rax, cs:__security_cookie
0x180115d17  xor     rax, rsp
0x180115d1a  mov     [rsp+128h+var_38], rax
0x180115d22  mov     rsi, r8
0x180115d25  mov     rdi, rcx
0x180115d28  mov     r14, [rcx]
0x180115d2b  xor     r12d, r12d
0x180115d2e  test    r14, r14
0x180115d31  jz      short loc_180115D5E
0x180115d33  call    cs:__imp_GetLastError
0x180115d3a  nop     dword ptr [rax+rax+00h]
0x180115d3f  mov     ebx, eax
0x180115d41  mov     rcx, r14; hKey
0x180115d44  call    cs:__imp_RegCloseKey
0x180115d4b  nop     dword ptr [rax+rax+00h]
0x180115d50  mov     ecx, ebx; dwErrCode
0x180115d52  call    cs:__imp_SetLastError
0x180115d59  nop     dword ptr [rax+rax+00h]
0x180115d5e  mov     qword ptr [rdi], 0FFFFFFFF80000002h
0x180115d65  lea     rcx, [rdi+8]
0x180115d69  mov     rdx, rsi
0x180115d6c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180115d71  xorps   xmm0, xmm0
0x180115d74  movups  [rsp+128h+var_78], xmm0
0x180115d7c  mov     [rsp+128h+var_68], r12
0x180115d84  mov     [rsp+128h+var_60], r12
0x180115d8c  mov     r8d, 18h
0x180115d92  lea     rdx, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x180115d99  lea     rcx, [rsp+128h+var_78]
0x180115da1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180115da6  nop
0x180115da7  xorps   xmm0, xmm0
0x180115daa  movups  [rsp+128h+var_58], xmm0
0x180115db2  mov     [rsp+128h+var_48], r12
0x180115dba  mov     [rsp+128h+var_40], r12
0x180115dc2  mov     r8d, 12h
0x180115dc8  lea     rdx, aSerestoreprivi; "SeRestorePrivilege"
0x180115dcf  lea     rcx, [rsp+128h+var_58]
0x180115dd7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180115ddc  nop
0x180115ddd  xorps   xmm0, xmm0
0x180115de0  movdqu  [rsp+128h+var_C8], xmm0
0x180115de6  mov     [rsp+128h+var_B8], r12
0x180115deb  mov     ecx, 40h ; '@'; Size
0x180115df0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180115df5  mov     rbx, rax
0x180115df8  mov     qword ptr [rsp+128h+var_C8], rax
0x180115dfd  mov     qword ptr [rsp+128h+var_C8+8], rax
0x180115e02  lea     rcx, [rax+40h]
0x180115e06  mov     [rsp+128h+var_B8], rcx
0x180115e0b  lea     rax, [rsp+128h+var_C8]
0x180115e10  mov     [rsp+128h+var_B0], rax
0x180115e15  lea     r14, [rsp+128h+var_78]
0x180115e1d  lea     r15, [rsp+128h+var_38]
0x180115e25  mov     qword ptr [rsp+128h+var_A0], rbx
0x180115e2d  mov     qword ptr [rsp+128h+var_A0+8], rbx
0x180115e35  lea     rax, [rsp+128h+var_C8]
0x180115e3a  mov     [rsp+128h+var_90], rax
0x180115e42  cmp     r14, r15
0x180115e45  jz      short loc_180115E64
0x180115e47  mov     rdx, r14
0x180115e4a  mov     rcx, rbx
0x180115e4d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180115e52  add     rbx, 20h ; ' '
0x180115e56  mov     qword ptr [rsp+128h+var_A0+8], rbx
0x180115e5e  add     r14, 20h ; ' '
0x180115e62  jmp     short loc_180115E42
0x180115e64  mov     qword ptr [rsp+128h+var_C8+8], rbx
0x180115e69  lea     r9, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x180115e70  mov     edx, 20h ; ' '; unsigned __int64
0x180115e75  lea     r8d, [rdx-1Eh]; unsigned __int64
0x180115e79  lea     rcx, [rsp+128h+var_78]; void *
0x180115e81  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180115e86  lea     rdx, [rsp+128h+var_C8]
0x180115e8b  mov     rcx, rdi
0x180115e8e  call    ?EnablePrivileges@RegistryOwnershipManager@@AEAAJAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; RegistryOwnershipManager::EnablePrivileges(std::vector<std::wstring> const &)
0x180115e93  mov     ebx, eax
0x180115e95  test    eax, eax
0x180115e97  jns     short loc_180115EC7
0x180115e99  mov     rcx, [rsp+128h]; this
0x180115ea1  mov     r9d, eax; char *
0x180115ea4  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x180115eab  mov     edx, 29h ; ')'; void *
0x180115eb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180115eb5  nop
0x180115eb6  lea     rcx, [rsp+128h+var_C8]
0x180115ebb  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180115ec0  mov     eax, ebx
0x180115ec2  jmp     loc_1801160D7
0x180115ec7  mov     dword ptr [rsp+128h+pIdentifierAuthority.Value], r12d
0x180115ecf  mov     word ptr [rsp+128h+pIdentifierAuthority.Value+4], 500h
0x180115ed9  lea     r14, [rdi+28h]
0x180115edd  mov     r15, [r14]
0x180115ee0  test    r15, r15
0x180115ee3  jz      short loc_180115F11
0x180115ee5  call    cs:__imp_GetLastError
0x180115eec  nop     dword ptr [rax+rax+00h]
0x180115ef1  mov     ebx, eax
0x180115ef3  mov     rcx, r15; pSid
0x180115ef6  call    cs:__imp_FreeSid
0x180115efd  nop     dword ptr [rax+rax+00h]
0x180115f02  mov     ecx, ebx; dwErrCode
0x180115f04  call    cs:__imp_SetLastError
0x180115f0b  nop     dword ptr [rax+rax+00h]
0x180115f10  nop
0x180115f11  mov     [r14], r12
0x180115f14  mov     [rsp+128h+pSid], r14; pSid
0x180115f19  mov     [rsp+128h+nSubAuthority7], r12d; nSubAuthority7
0x180115f1e  mov     [rsp+128h+nSubAuthority6], r12d; nSubAuthority6
0x180115f23  mov     [rsp+128h+nSubAuthority5], r12d; nSubAuthority5
0x180115f28  mov     [rsp+128h+nSubAuthority4], r12d; nSubAuthority4
0x180115f2d  mov     [rsp+128h+nSubAuthority3], r12d; nSubAuthority3
0x180115f32  mov     [rsp+128h+nSubAuthority2], r12d; nSubAuthority2
0x180115f37  mov     r9d, 220h; nSubAuthority1
0x180115f3d  mov     r8d, 20h ; ' '; nSubAuthority0
0x180115f43  mov     dl, 2; nSubAuthorityCount
0x180115f45  lea     rcx, [rsp+128h+pIdentifierAuthority]; pIdentifierAuthority
0x180115f4d  call    cs:__imp_AllocateAndInitializeSid
0x180115f54  nop     dword ptr [rax+rax+00h]
0x180115f59  test    eax, eax
0x180115f5b  jnz     short loc_180115F87
0x180115f5d  mov     rcx, [rsp+128h]; this
0x180115f65  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x180115f6c  lea     edx, [rax+2Eh]; void *
0x180115f6f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180115f74  mov     ebx, eax
0x180115f76  lea     rcx, [rsp+128h+var_C8]
0x180115f7b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180115f80  mov     eax, ebx
0x180115f82  jmp     loc_1801160D7
0x180115f87  lea     r14, [rdi+30h]
0x180115f8b  mov     r15, [r14]
0x180115f8e  test    r15, r15
0x180115f91  jz      short loc_180115FBF
0x180115f93  call    cs:__imp_GetLastError
0x180115f9a  nop     dword ptr [rax+rax+00h]
0x180115f9f  mov     ebx, eax
0x180115fa1  mov     rcx, r15; pSid
0x180115fa4  call    cs:__imp_FreeSid
0x180115fab  nop     dword ptr [rax+rax+00h]
0x180115fb0  mov     ecx, ebx; dwErrCode
0x180115fb2  call    cs:__imp_SetLastError
0x180115fb9  nop     dword ptr [rax+rax+00h]
0x180115fbe  nop
0x180115fbf  mov     [r14], r12
0x180115fc2  mov     [rsp+128h+pSid], r14; pSid
0x180115fc7  mov     [rsp+128h+nSubAuthority7], r12d; nSubAuthority7
0x180115fcc  mov     [rsp+128h+nSubAuthority6], r12d; nSubAuthority6
0x180115fd1  mov     [rsp+128h+nSubAuthority5], r12d; nSubAuthority5
0x180115fd6  mov     [rsp+128h+nSubAuthority4], r12d; nSubAuthority4
0x180115fdb  mov     [rsp+128h+nSubAuthority3], r12d; nSubAuthority3
0x180115fe0  mov     [rsp+128h+nSubAuthority2], r12d; int
0x180115fe5  xor     r9d, r9d; nSubAuthority1
0x180115fe8  lea     r8d, [r9+12h]; nSubAuthority0
0x180115fec  mov     dl, 1; nSubAuthorityCount
0x180115fee  lea     rcx, [rsp+128h+pIdentifierAuthority]; pIdentifierAuthority
0x180115ff6  call    cs:__imp_AllocateAndInitializeSid
0x180115ffd  nop     dword ptr [rax+rax+00h]
0x180116002  test    eax, eax
0x180116004  jnz     short loc_180116030
0x180116006  mov     rcx, [rsp+128h]; this
0x18011600e  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x180116015  lea     edx, [rax+31h]; void *
0x180116018  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18011601d  mov     ebx, eax
0x18011601f  lea     rcx, [rsp+128h+var_C8]
0x180116024  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180116029  mov     eax, ebx
0x18011602b  jmp     loc_1801160D7
0x180116030  cmp     qword ptr [rsi+18h], 7
0x180116035  jbe     short loc_18011603A
0x180116037  mov     rsi, [rsi]
0x18011603a  xorps   xmm0, xmm0
0x18011603d  movups  [rsp+128h+var_A0], xmm0
0x180116045  mov     [rsp+128h+var_90], r12
0x18011604d  mov     [rsp+128h+var_88], r12
0x180116055  or      r8, 0FFFFFFFFFFFFFFFFh
0x180116059  inc     r8
0x18011605c  cmp     [rsi+r8*2], r12w
0x180116061  jnz     short loc_180116059
0x180116063  mov     rdx, rsi
0x180116066  lea     rcx, [rsp+128h+var_A0]
0x18011606e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180116073  nop
0x180116074  lea     rdx, [rsp+128h+var_A0]
0x18011607c  mov     rcx, rdi
0x18011607f  call    ?TakeOwnershipRecursive@RegistryOwnershipManager@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegistryOwnershipManager::TakeOwnershipRecursive(std::wstring const &)
0x180116084  mov     ebx, eax
0x180116086  lea     rcx, [rsp+128h+var_A0]; void *
0x18011608e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180116093  test    ebx, ebx
0x180116095  jns     short loc_1801160C2
0x180116097  mov     rcx, [rsp+128h]; this
0x18011609f  mov     r9d, ebx; char *
0x1801160a2  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x1801160a9  mov     edx, 34h ; '4'; void *
0x1801160ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801160b3  nop
0x1801160b4  lea     rcx, [rsp+128h+var_C8]
0x1801160b9  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801160be  mov     eax, ebx
0x1801160c0  jmp     short loc_1801160D7
0x1801160c2  lea     rcx, [rsp+128h+var_C8]
0x1801160c7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801160cc  xor     eax, eax
0x1801160ce  jmp     short loc_1801160D7
0x1801160d0  mov     eax, dword ptr [rsp+128h+pIdentifierAuthority.Value]
0x1801160d7  mov     rcx, [rsp+128h+var_38]
0x1801160df  xor     rcx, rsp; StackCookie
0x1801160e2  call    __security_check_cookie
0x1801160e7  mov     rbx, [rsp+128h+arg_8]
0x1801160ef  add     rsp, 100h
0x1801160f6  pop     r15
0x1801160f8  pop     r14
0x1801160fa  pop     r12
0x1801160fc  pop     rdi
0x1801160fd  pop     rsi
0x1801160fe  retn
```
