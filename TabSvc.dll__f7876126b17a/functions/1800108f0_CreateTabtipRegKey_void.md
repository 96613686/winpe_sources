# CreateTabtipRegKey(void *)

- ea: `0x1800108f0`
- end: `0x180010c1d`
- name: `?CreateTabtipRegKey@@YAXPEAX@Z`
- size: `813`
- prototype: `void __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002c3c4`

## callees

- `0x1800108f0`
- `0x180012df0`
- `0x180013cbc`
- `0x180018e9c`
- `0x1800199fc`
- `0x18001a724`
- `0x18001bbe0`
- `0x18001c684`
- `0x18002cc8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a8c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010a71`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010a71`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001094e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010b39`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001094e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010b39`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180010b6f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180010b6f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180010ac8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180010ac8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010954`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010954`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010b00`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010b00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010981`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010ae4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010bbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010981`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010ae4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010bbf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180010b81`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180010b81`

## pseudocode

```c
void __fastcall CreateTabtipRegKey(HANDLE TokenHandle)
{
  __int64 v2; // rax
  const wchar_t *v3; // rdx
  WCHAR *v4; // r8
  __int64 v5; // rbx
  WCHAR *v6; // rcx
  unsigned __int64 v7; // rdx
  LSTATUS v8; // eax
  bool v9; // sf
  PACL v10; // rcx
  PSID *v11; // rdi
  int v12; // esi
  BOOL TokenInformation; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  WINBOOL bDaclPresent[2]; // [rsp+58h] [rbp-A8h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  PACL pDacl; // [rsp+70h] [rbp-90h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+78h] [rbp-88h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v21; // [rsp+B0h] [rbp-50h]
  _BYTE v22[8]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE pSid2[120]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 v24[264]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR SubKey[264]; // [rsp+350h] [rbp+250h] BYREF

  memset_0(v24, 0, 0x208u);
  dwDisposition = 0;
  *(_QWORD *)bDaclPresent = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &dwDisposition);
  if ( GetLastError() == 122 )
  {
    v11 = (PSID *)LocalAlloc(0x40u, dwDisposition);
    if ( v11 )
    {
      v12 = -2147467259;
      TokenInformation = GetTokenInformation(TokenHandle, TokenUser, v11, dwDisposition, &dwDisposition);
      v5 = 260;
      if ( TokenInformation )
      {
        ATL::CSid::CSid(
          (ATL::CSid *)v22,
          (const struct _SID_IDENTIFIER_AUTHORITY *)&ATL::Sids::SecurityNTAuthority,
          1u,
          18);
        if ( EqualSid(*v11, pSid2) || !ConvertSidToStringSidW(*v11, (LPWSTR *)bDaclPresent) )
        {
          ATL::CSid::~CSid((ATL::CSid *)v22);
          v10 = (PACL)v11;
LABEL_21:
          LocalFree(v10);
          return;
        }
        ATL::CSid::~CSid((ATL::CSid *)v22);
        v12 = StringCchCopyW(v24, 0x104u, *(const unsigned __int16 **)bDaclPresent);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::GetImpl'::`2'::impl) )
          LocalFree(*(HLOCAL *)bDaclPresent);
      }
      LocalFree(v11);
      if ( v12 >= 0 )
      {
        memset_0(SubKey, 0, 0x208u);
        v2 = 2147483646;
        v3 = L"Software\\Microsoft\\Windows\\CurrentVersion\\TouchKeyboard\\Users\\";
        v4 = SubKey;
        do
        {
          if ( !v2 )
            break;
          if ( !*v3 )
            break;
          *v4++ = *v3++;
          --v2;
          --v5;
        }
        while ( v5 );
        v6 = v4 - 1;
        v7 = 2147942522LL;
        if ( v5 )
        {
          v6 = v4;
          v7 = 0;
        }
        *v6 = 0;
        if ( v5 )
          v7 = (unsigned int)StringCchCatW(SubKey, v7, v24);
        if ( (v7 & 0x80000000) == 0LL )
        {
          memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
          v21 = 0;
          if ( GetCustomSecurityDescriptor(v24, (const unsigned __int16 *)v7, pSecurityDescriptor) >= 0 )
          {
            *(_QWORD *)&SecurityAttributes.nLength = 24;
            SecurityAttributes.lpSecurityDescriptor = pSecurityDescriptor;
            *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
            hKey = 0;
            dwDisposition = 0;
            v8 = RegCreateKeyExW(
                   HKEY_LOCAL_MACHINE,
                   SubKey,
                   0,
                   (LPWSTR)&Data,
                   0,
                   0x2011Fu,
                   &SecurityAttributes,
                   &hKey,
                   &dwDisposition);
            v9 = v8 < 0;
            if ( v8 > 0 )
              v9 = 1;
            if ( !v9 )
              RegCloseKey(hKey);
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::GetImpl'::`2'::impl) )
            {
              pDacl = 0;
              bDaclPresent[0] = 0;
              bDaclDefaulted = 0;
              if ( GetSecurityDescriptorDacl(pSecurityDescriptor, bDaclPresent, &pDacl, &bDaclDefaulted) )
              {
                v10 = pDacl;
                if ( pDacl )
                  goto LABEL_21;
              }
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800108f0  push    rbp
0x1800108f2  push    rbx
0x1800108f3  push    r14
0x1800108f5  lea     rbp, [rsp-470h]
0x1800108fd  sub     rsp, 570h
0x180010904  mov     rax, cs:__security_cookie
0x18001090b  xor     rax, rsp
0x18001090e  mov     [rbp+480h+var_20], rax
0x180010915  mov     rbx, rcx
0x180010918  xor     edx, edx; Val
0x18001091a  lea     rcx, [rbp+480h+var_440]; void *
0x18001091e  mov     r8d, 208h; Size
0x180010924  xor     r14d, r14d
0x180010927  call    memset_0
0x18001092c  lea     rax, [rsp+580h+dwDisposition]
0x180010931  mov     [rsp+580h+dwDisposition], r14d
0x180010936  xor     r9d, r9d; TokenInformationLength
0x180010939  mov     [rsp+580h+ReturnLength], rax; ReturnLength
0x18001093e  xor     r8d, r8d; TokenInformation
0x180010941  mov     qword ptr [rsp+580h+bDaclPresent], r14
0x180010946  mov     edx, 1; TokenInformationClass
0x18001094b  mov     rcx, rbx; TokenHandle
0x18001094e  call    cs:__imp_GetTokenInformation
0x180010954  call    cs:__imp_GetLastError
0x18001095a  cmp     eax, 7Ah ; 'z'
0x18001095d  jz      loc_180010AEF
0x180010963  mov     rcx, [rbp+480h+var_20]
0x18001096a  xor     rcx, rsp; StackCookie
0x18001096d  call    __security_check_cookie
0x180010972  add     rsp, 570h
0x180010979  pop     r14
0x18001097b  pop     rbx
0x18001097c  pop     rbp
0x18001097d  retn
0x18001097e  mov     rcx, rdi; hMem
0x180010981  call    cs:__imp_LocalFree
0x180010987  test    esi, esi
0x180010989  js      short loc_1800109FA
0x18001098b  xor     edx, edx; Val
0x18001098d  lea     rcx, [rbp+480h+SubKey]; void *
0x180010994  mov     r8d, 208h; Size
0x18001099a  call    memset_0
0x18001099f  mov     eax, 7FFFFFFEh
0x1800109a4  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800109ab  lea     r8, [rbp+480h+SubKey]
0x1800109b2  test    rax, rax
0x1800109b5  jz      short loc_1800109D4
0x1800109b7  movzx   ecx, word ptr [rdx]
0x1800109ba  test    cx, cx
0x1800109bd  jz      short loc_1800109D4
0x1800109bf  mov     [r8], cx
0x1800109c3  add     rdx, 2
0x1800109c7  add     r8, 2
0x1800109cb  dec     rax
0x1800109ce  sub     rbx, 1
0x1800109d2  jnz     short loc_1800109B2
0x1800109d4  test    rbx, rbx
0x1800109d7  lea     rcx, [r8-2]
0x1800109db  mov     edx, 8007007Ah
0x1800109e0  cmovnz  rcx, r8
0x1800109e4  cmovnz  edx, r14d; unsigned __int16 *
0x1800109e8  mov     [rcx], r14w
0x1800109ec  jnz     loc_180010BDB
0x1800109f2  test    edx, edx
0x1800109f4  jns     loc_180010BF2
0x1800109fa  mov     rsi, [rsp+580h+arg_8]
0x180010a02  mov     rdi, [rsp+580h+arg_10]
0x180010a0a  jmp     loc_180010963
0x180010a0f  lea     rax, [rbp+480h+pSecurityDescriptor]
0x180010a13  mov     qword ptr [rsp+580h+SecurityAttributes.nLength], 18h
0x180010a1c  mov     [rbp+480h+SecurityAttributes.lpSecurityDescriptor], rax
0x180010a20  lea     r9, Data; lpClass
0x180010a27  lea     rax, [rsp+580h+dwDisposition]
0x180010a2c  mov     qword ptr [rbp+480h+SecurityAttributes.bInheritHandle], r14
0x180010a30  mov     [rsp+580h+lpdwDisposition], rax; lpdwDisposition
0x180010a35  lea     rdx, [rbp+480h+SubKey]; lpSubKey
0x180010a3c  lea     rax, [rsp+580h+hKey]
0x180010a41  mov     [rsp+580h+hKey], r14
0x180010a46  mov     [rsp+580h+phkResult], rax; phkResult
0x180010a4b  xor     r8d, r8d; Reserved
0x180010a4e  lea     rax, [rsp+580h+SecurityAttributes]
0x180010a53  mov     [rsp+580h+dwDisposition], r14d
0x180010a58  mov     [rsp+580h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180010a5d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010a64  mov     [rsp+580h+samDesired], 2011Fh; samDesired
0x180010a6c  mov     dword ptr [rsp+580h+ReturnLength], r14d; dwOptions
0x180010a71  call    cs:__imp_RegCreateKeyExW
0x180010a77  test    eax, eax
0x180010a79  jle     short loc_180010A85
0x180010a7b  movzx   eax, ax
0x180010a7e  or      eax, 80070000h
0x180010a83  test    eax, eax
0x180010a85  js      short loc_180010A92
0x180010a87  mov     rcx, [rsp+580h+hKey]; hKey
0x180010a8c  call    cs:__imp_RegCloseKey
0x180010a92  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::GetImpl(void)'::`2'::impl
0x180010a99  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::__private_IsEnabled(void)
0x180010a9e  test    al, al
0x180010aa0  jz      loc_1800109FA
0x180010aa6  lea     r9, [rsp+580h+bDaclDefaulted]; lpbDaclDefaulted
0x180010aab  mov     [rsp+580h+pDacl], r14
0x180010ab0  lea     r8, [rsp+580h+pDacl]; pDacl
0x180010ab5  mov     [rsp+580h+bDaclPresent], r14d
0x180010aba  lea     rdx, [rsp+580h+bDaclPresent]; lpbDaclPresent
0x180010abf  mov     [rsp+580h+bDaclDefaulted], r14d
0x180010ac4  lea     rcx, [rbp+480h+pSecurityDescriptor]; pSecurityDescriptor
0x180010ac8  call    cs:__imp_GetSecurityDescriptorDacl
0x180010ace  test    eax, eax
0x180010ad0  jz      loc_1800109FA
0x180010ad6  mov     rcx, [rsp+580h+pDacl]; hMem
0x180010adb  test    rcx, rcx
0x180010ade  jz      loc_1800109FA
0x180010ae4  call    cs:__imp_LocalFree
0x180010aea  jmp     loc_1800109FA
0x180010aef  mov     edx, [rsp+580h+dwDisposition]; uBytes
0x180010af3  mov     ecx, 40h ; '@'; uFlags
0x180010af8  mov     [rsp+580h+arg_10], rdi
0x180010b00  call    cs:__imp_LocalAlloc
0x180010b06  mov     rdi, rax
0x180010b09  test    rax, rax
0x180010b0c  jz      loc_180010A02
0x180010b12  mov     r9d, [rsp+580h+dwDisposition]; TokenInformationLength
0x180010b17  lea     rax, [rsp+580h+dwDisposition]
0x180010b1c  mov     [rsp+580h+arg_8], rsi
0x180010b24  mov     r8, rdi; TokenInformation
0x180010b27  mov     edx, 1; TokenInformationClass
0x180010b2c  mov     [rsp+580h+ReturnLength], rax; ReturnLength
0x180010b31  mov     rcx, rbx; TokenHandle
0x180010b34  mov     esi, 80004005h
0x180010b39  call    cs:__imp_GetTokenInformation
0x180010b3f  mov     ebx, 104h
0x180010b44  test    eax, eax
0x180010b46  jz      loc_18001097E
0x180010b4c  mov     r9d, 12h
0x180010b52  lea     rdx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B; struct _SID_IDENTIFIER_AUTHORITY *
0x180010b59  mov     r8d, 1; unsigned __int8
0x180010b5f  lea     rcx, [rbp+480h+var_4C0]; this
0x180010b63  call    ??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x180010b68  mov     rcx, [rdi]; pSid1
0x180010b6b  lea     rdx, [rbp+480h+pSid2]; pSid2
0x180010b6f  call    cs:__imp_EqualSid
0x180010b75  test    eax, eax
0x180010b77  jnz     short loc_180010BCA
0x180010b79  mov     rcx, [rdi]; Sid
0x180010b7c  lea     rdx, [rsp+580h+bDaclPresent]; StringSid
0x180010b81  call    cs:__imp_ConvertSidToStringSidW
0x180010b87  test    eax, eax
0x180010b89  jz      short loc_180010BCA
0x180010b8b  lea     rcx, [rbp+480h+var_4C0]; this
0x180010b8f  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180010b94  mov     r8, qword ptr [rsp+580h+bDaclPresent]; unsigned __int16 *
0x180010b99  lea     rcx, [rbp+480h+var_440]; unsigned __int16 *
0x180010b9d  mov     edx, ebx; unsigned __int64
0x180010b9f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010ba4  mov     esi, eax
0x180010ba6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::GetImpl(void)'::`2'::impl
0x180010bad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::__private_IsEnabled(void)
0x180010bb2  test    al, al
0x180010bb4  jz      loc_18001097E
0x180010bba  mov     rcx, qword ptr [rsp+580h+bDaclPresent]; hMem
0x180010bbf  call    cs:__imp_LocalFree
0x180010bc5  jmp     loc_18001097E
0x180010bca  lea     rcx, [rbp+480h+var_4C0]; this
0x180010bce  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180010bd3  mov     rcx, rdi
0x180010bd6  jmp     loc_180010AE4
0x180010bdb  lea     r8, [rbp+480h+var_440]; unsigned __int16 *
0x180010bdf  lea     rcx, [rbp+480h+SubKey]; unsigned __int16 *
0x180010be6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010beb  mov     edx, eax
0x180010bed  jmp     loc_1800109F2
0x180010bf2  xorps   xmm0, xmm0
0x180010bf5  lea     r8, [rbp+480h+pSecurityDescriptor]; void *
0x180010bf9  xor     eax, eax
0x180010bfb  lea     rcx, [rbp+480h+var_440]; unsigned __int16 *
0x180010bff  movups  [rbp+480h+pSecurityDescriptor], xmm0
0x180010c03  mov     [rbp+480h+var_4D0], rax
0x180010c07  movups  [rbp+480h+var_4E0], xmm0
0x180010c0b  call    ?GetCustomSecurityDescriptor@@YAJPEBG0PEAX@Z; GetCustomSecurityDescriptor(ushort const *,ushort const *,void *)
0x180010c10  test    eax, eax
0x180010c12  js      loc_1800109FA
0x180010c18  jmp     loc_180010A0F
```
