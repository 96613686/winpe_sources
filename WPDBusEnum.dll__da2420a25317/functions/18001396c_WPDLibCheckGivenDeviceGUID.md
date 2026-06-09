# WPDLibCheckGivenDeviceGUID

- ea: `0x18001396c`
- end: `0x180013e95`
- name: `WPDLibCheckGivenDeviceGUID`
- size: `1321`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800069d0`

## callees

- `0x180004300`
- `0x180004390`
- `0x180005670`
- `0x180005f60`
- `0x180006090`
- `0x1800097d0`
- `0x1800124c0`
- `0x180012b88`
- `0x180012ef8`
- `0x18001396c`
- `0x180015024`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013cae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013ce1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013cee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013d17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013d63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013d6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013e3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013e49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013e63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013cae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013ce1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013cee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013d17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013d63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013d6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013e3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013e49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013e63`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180013dfa`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180013dfa`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180013e22`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180013e22`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x180013be1`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x180013be1`
- `WTSAPI32!WTSFreeMemory` at `0x180013d7c`
- `WTSAPI32!WTSFreeMemory` at `0x180013d7c`

## pseudocode

```c
__int64 __fastcall WPDLibCheckGivenDeviceGUID(
        __int64 a1,
        int a2,
        struct _ACL **a3,
        _QWORD *a4,
        DWORD *a5,
        _DWORD *a6,
        DWORD *a7)
{
  DWORD v8; // r14d
  int v9; // ebx
  __int64 v10; // r8
  const WCHAR *v11; // rcx
  __int64 v12; // rdx
  wchar_t *v13; // rax
  wchar_t *v14; // rcx
  int v16; // r15d
  int v17; // r12d
  struct _ACL *v18; // rsi
  ULONG v19; // eax
  struct _ACL *v20; // rbx
  ULONG UserInformation; // edi
  int v22; // eax
  DWORD v23; // r13d
  ULONG v24; // r14d
  __int64 v25; // r10
  __int64 v26; // r11
  ULONG v27; // ecx
  WCHAR **v28; // r12
  WCHAR *v29; // rcx
  void *v30; // rbx
  void *v31; // rcx
  DWORD SecurityDescriptorLength; // eax
  HLOCAL v33; // rcx
  HLOCAL v34; // [rsp+80h] [rbp-80h] BYREF
  DWORD pCount; // [rsp+88h] [rbp-78h] BYREF
  ULONG v36; // [rsp+8Ch] [rbp-74h] BYREF
  ULONG StringSecurityDescriptorLen; // [rsp+90h] [rbp-70h] BYREF
  DWORD v38; // [rsp+94h] [rbp-6Ch]
  int v39; // [rsp+98h] [rbp-68h]
  HLOCAL hMem; // [rsp+A0h] [rbp-60h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+A8h] [rbp-58h] BYREF
  DWORD v42; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v43[3]; // [rsp+B4h] [rbp-4Ch] BYREF
  struct _ACL **v44; // [rsp+C0h] [rbp-40h]
  _QWORD *v45; // [rsp+C8h] [rbp-38h]
  DWORD *v46; // [rsp+D0h] [rbp-30h]
  DWORD *v47; // [rsp+D8h] [rbp-28h]
  wchar_t pszDest[256]; // [rsp+E0h] [rbp-20h] BYREF

  *a3 = 0;
  v8 = 0;
  *a4 = 0;
  v43[0] = 1;
  *a5 = 0;
  *a6 = 0;
  v45 = a4;
  v44 = a3;
  v46 = a5;
  v34 = a6;
  v47 = a7;
  hMem = 0;
  ppSessionInfo = 0;
  *(_QWORD *)&v43[1] = 0;
  v38 = 0;
  pCount = 0;
  if ( a7 )
    *a7 = 0;
  if ( a1 )
  {
    if ( !StringCchPrintfW(
            pszDest,
            0x100u,
            L"%ws\\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
            L"SOFTWARE\\Policies\\Microsoft\\Windows\\RemovableStorageDevices",
            *(_DWORD *)a1,
            *(unsigned __int16 *)(a1 + 4),
            *(unsigned __int16 *)(a1 + 6),
            *(unsigned __int8 *)(a1 + 8),
            *(unsigned __int8 *)(a1 + 9),
            *(unsigned __int8 *)(a1 + 10),
            *(unsigned __int8 *)(a1 + 11),
            *(unsigned __int8 *)(a1 + 12),
            *(unsigned __int8 *)(a1 + 13),
            *(unsigned __int8 *)(a1 + 14),
            *(unsigned __int8 *)(a1 + 15)) )
    {
      v9 = 0;
      goto LABEL_15;
    }
    return 87;
  }
  v10 = 2147483646;
  v11 = L"SOFTWARE\\Policies\\Microsoft\\Windows\\RemovableStorageDevices";
  v12 = 256;
  v13 = pszDest;
  do
  {
    if ( !v10 )
      break;
    if ( !*v11 )
      break;
    *v13++ = *v11++;
    --v10;
    --v12;
  }
  while ( v12 );
  v14 = v13 - 1;
  if ( v12 )
    v14 = v13;
  *v14 = 0;
  if ( !v12 )
    return 87;
  v9 = 1;
LABEL_15:
  v39 = v9;
  v36 = 0;
  StringSecurityDescriptorLen = 1;
  v16 = 0;
  v17 = 0;
  BuildAuditPolicyACL(0, 0, (HLOCAL *)&ppSessionInfo);
  v18 = (struct _ACL *)ppSessionInfo;
  if ( ppSessionInfo )
  {
    v17 = 1;
    v36 = 1;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::GetImpl'::`2'::impl) )
      v8 = 1;
    v38 = v8;
    pCount = v8;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::GetImpl'::`2'::impl) )
  {
    v19 = BuildMachineAccessDACL(pszDest, (__int64)&hMem, (__int64)v43);
  }
  else
  {
    v19 = BuildMachineAccessDACL(pszDest, (__int64)&hMem, (__int64)&pCount);
    v8 = pCount;
    v38 = pCount;
  }
  v20 = (struct _ACL *)hMem;
  UserInformation = v19;
  if ( hMem )
    v16 = 1;
  if ( a2 || v16 && v17 )
    goto LABEL_61;
  ppSessionInfo = 0;
  pCount = 0;
  *(_DWORD *)v34 = v16 ^ 1;
  if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
    v22 = 0;
    v23 = 0;
    LODWORD(hMem) = 0;
    if ( pCount )
    {
      v24 = v36;
      do
      {
        v36 = 0;
        if ( (unsigned int)SessionNotActive((unsigned int)ppSessionInfo[v23].State) )
        {
          v27 = *(_DWORD *)(v26 + 8 * v25);
          v42 = 0;
          v34 = 0;
          UserInformation = GetUserInformation(v27, pszDest, &v34, &v42, (LSTATUS *)&v36);
          if ( !UserInformation )
          {
            v28 = (WCHAR **)v34;
            if ( v34 )
            {
              if ( !v16 )
              {
                UserInformation = v36;
                v34 = 0;
                if ( !v36 )
                {
                  if ( v42 )
                  {
                    LODWORD(hMem) = 1;
                    StringSecurityDescriptorLen = v36;
                  }
                  UserInformation = BuildUserPolicyACL(v42, *v28, v20, &v34);
                  if ( !UserInformation )
                  {
                    if ( v20 )
                      LocalFree(v20);
                    v20 = (struct _ACL *)v34;
                  }
                }
              }
              if ( !v24 )
              {
                v29 = *v28;
                v34 = 0;
                if ( !(unsigned int)BuildAuditPolicyACL(v29, v18, &v34) )
                {
                  if ( v18 )
                    LocalFree(v18);
                  v18 = (struct _ACL *)v34;
                }
              }
              LocalFree(v28);
            }
          }
        }
        ++v23;
      }
      while ( v23 < pCount );
      v8 = v38;
      v22 = (int)hMem;
    }
    if ( v16 )
      goto LABEL_59;
    if ( !v22 )
    {
      LocalFree(v20);
      v20 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::GetImpl'::`2'::impl) )
        goto LABEL_54;
      v8 = v18 != 0;
    }
    if ( v20 )
    {
LABEL_56:
      v34 = 0;
      UserInformation = AddSystemToACL(v20, (PACL *)&v34);
      LocalFree(v20);
      if ( UserInformation )
        v20 = 0;
      else
        v20 = (struct _ACL *)v34;
LABEL_59:
      WTSFreeMemory(ppSessionInfo);
      goto LABEL_61;
    }
LABEL_54:
    if ( !v18 || v39 )
      goto LABEL_59;
    goto LABEL_56;
  }
  UserInformation = GetLastError();
LABEL_61:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::GetImpl'::`2'::impl) )
  {
    if ( !v18 || !v43[0] || (v8 = 1, !StringSecurityDescriptorLen) )
      v8 = 0;
  }
  if ( UserInformation )
    goto LABEL_71;
  if ( !v20 )
    goto LABEL_75;
  UserInformation = GetSecurityDescriptorForACL(v20, v18, &v43[1]);
  if ( UserInformation )
  {
LABEL_71:
    if ( v20 )
      LocalFree(v20);
    v33 = *(HLOCAL *)&v43[1];
    if ( !*(_QWORD *)&v43[1] )
      goto LABEL_75;
    goto LABEL_74;
  }
  v34 = 0;
  StringSecurityDescriptorLen = 0;
  *v44 = v20;
  v30 = *(void **)&v43[1];
  v31 = *(void **)&v43[1];
  *v45 = *(_QWORD *)&v43[1];
  SecurityDescriptorLength = GetSecurityDescriptorLength(v31);
  UserInformation = 0;
  *v46 = SecurityDescriptorLength;
  if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v30, 1u, 4u, (LPWSTR *)&v34, &StringSecurityDescriptorLen) )
  {
    v33 = v34;
LABEL_74:
    LocalFree(v33);
  }
LABEL_75:
  if ( v47 )
    *v47 = v8;
  if ( v18 )
    LocalFree(v18);
  return UserInformation;
}

```

## disassembly

```asm
0x18001396c  mov     [rsp-8+arg_8], rbx
0x180013971  push    rbp
0x180013972  push    rsi
0x180013973  push    rdi
0x180013974  push    r12
0x180013976  push    r13
0x180013978  push    r14
0x18001397a  push    r15
0x18001397c  lea     rbp, [rsp-1F0h]
0x180013984  sub     rsp, 2F0h
0x18001398b  mov     rax, cs:__security_cookie
0x180013992  xor     rax, rsp
0x180013995  mov     [rbp+220h+var_40], rax
0x18001399c  mov     rax, [rbp+220h+arg_28]
0x1800139a3  xor     edi, edi
0x1800139a5  mov     [r8], rdi
0x1800139a8  mov     r13d, edx
0x1800139ab  mov     rdx, [rbp+220h+arg_20]
0x1800139b2  mov     r15, rcx
0x1800139b5  mov     rcx, [rbp+220h+arg_30]
0x1800139bc  mov     r14d, edi
0x1800139bf  mov     [r9], rdi
0x1800139c2  lea     r10d, [rdi+1]
0x1800139c6  mov     dword ptr [rbp+220h+var_26C], r10d
0x1800139ca  mov     [rdx], edi
0x1800139cc  mov     [rax], edi
0x1800139ce  mov     [rbp+220h+var_258], r9
0x1800139d2  mov     [rbp+220h+var_260], r8
0x1800139d6  mov     [rbp+220h+var_250], rdx
0x1800139da  mov     [rbp+220h+var_2A0], rax
0x1800139de  mov     [rbp+220h+var_248], rcx
0x1800139e2  mov     [rbp+220h+hMem], rdi
0x1800139e6  mov     [rbp+220h+ppSessionInfo], rdi
0x1800139ea  mov     qword ptr [rbp+220h+var_26C+4], rdi
0x1800139ee  mov     [rbp+220h+var_28C], edi
0x1800139f1  mov     [rbp+220h+var_298], edi
0x1800139f4  test    rcx, rcx
0x1800139f7  jz      short loc_1800139FB
0x1800139f9  mov     [rcx], edi
0x1800139fb  test    r15, r15
0x1800139fe  jz      loc_180013A93
0x180013a04  movzx   eax, byte ptr [r15+0Fh]
0x180013a09  movzx   ecx, byte ptr [r15+0Eh]
0x180013a0e  movzx   edx, byte ptr [r15+0Dh]
0x180013a13  movzx   r8d, byte ptr [r15+0Ch]
0x180013a18  movzx   r9d, byte ptr [r15+0Bh]
0x180013a1d  movzx   r10d, byte ptr [r15+0Ah]
0x180013a22  movzx   r11d, byte ptr [r15+9]
0x180013a27  movzx   ebx, byte ptr [r15+8]
0x180013a2c  movzx   edi, word ptr [r15+6]
0x180013a31  movzx   esi, word ptr [r15+4]
0x180013a36  mov     [rsp+320h+var_2B0], eax
0x180013a3a  mov     eax, [r15]
0x180013a3d  mov     [rsp+320h+var_2B8], ecx
0x180013a41  lea     rcx, [rbp+220h+pszDest]; pszDest
0x180013a45  mov     [rsp+320h+var_2C0], edx
0x180013a49  mov     edx, 100h; cchDest
0x180013a4e  mov     [rsp+320h+var_2C8], r8d
0x180013a53  lea     r8, aWs08x04x04x02x; "%ws\\{%08x-%04x-%04x-%02x%02x-%02x%02x%"...
0x180013a5a  mov     [rsp+320h+var_2D0], r9d
0x180013a5f  lea     r9, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180013a66  mov     [rsp+320h+var_2D8], r10d
0x180013a6b  mov     [rsp+320h+var_2E0], r11d
0x180013a70  mov     [rsp+320h+var_2E8], ebx
0x180013a74  mov     [rsp+320h+var_2F0], edi
0x180013a78  mov     dword ptr [rsp+320h+var_2F8], esi
0x180013a7c  mov     dword ptr [rsp+320h+pCount], eax
0x180013a80  call    StringCchPrintfW
0x180013a85  xor     edi, edi
0x180013a87  test    eax, eax
0x180013a89  jnz     short loc_180013ADC
0x180013a8b  mov     ebx, edi
0x180013a8d  lea     r10d, [rdi+1]
0x180013a91  jmp     short loc_180013AE9
0x180013a93  mov     r8d, 7FFFFFFEh
0x180013a99  lea     rcx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180013aa0  mov     edx, 100h
0x180013aa5  lea     rax, [rbp+220h+pszDest]
0x180013aa9  test    r8, r8
0x180013aac  jz      short loc_180013ACC
0x180013aae  movzx   r9d, word ptr [rcx]
0x180013ab2  test    r9w, r9w
0x180013ab6  jz      short loc_180013ACC
0x180013ab8  mov     [rax], r9w
0x180013abc  add     rcx, 2
0x180013ac0  add     rax, 2
0x180013ac4  sub     r8, r10
0x180013ac7  sub     rdx, r10
0x180013aca  jnz     short loc_180013AA9
0x180013acc  test    rdx, rdx
0x180013acf  lea     rcx, [rax-2]
0x180013ad3  cmovnz  rcx, rax
0x180013ad7  mov     [rcx], di
0x180013ada  jnz     short loc_180013AE6
0x180013adc  mov     eax, 57h ; 'W'
0x180013ae1  jmp     loc_180013E6B
0x180013ae6  mov     ebx, r10d
0x180013ae9  lea     r8, [rbp+220h+ppSessionInfo]
0x180013aed  mov     [rbp+220h+var_288], ebx
0x180013af0  xor     edx, edx
0x180013af2  mov     [rbp+220h+var_294], edi
0x180013af5  xor     ecx, ecx
0x180013af7  mov     [rbp+220h+StringSecurityDescriptorLen], r10d
0x180013afb  mov     r15d, edi
0x180013afe  mov     r12d, edi
0x180013b01  call    BuildAuditPolicyACL
0x180013b06  mov     rsi, [rbp+220h+ppSessionInfo]
0x180013b0a  test    rsi, rsi
0x180013b0d  jz      short loc_180013B36
0x180013b0f  mov     r12d, 1
0x180013b15  mov     [rbp+220h+var_294], r12d
0x180013b19  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6> `wil::Feature<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::GetImpl(void)'::`2'::impl
0x180013b20  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::__private_IsEnabled(void)
0x180013b25  test    al, al
0x180013b27  mov     eax, r12d
0x180013b2a  cmovz   r14d, eax
0x180013b2e  mov     [rbp+220h+var_28C], r14d
0x180013b32  mov     [rbp+220h+var_298], r14d
0x180013b36  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6> `wil::Feature<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::GetImpl(void)'::`2'::impl
0x180013b3d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::__private_IsEnabled(void)
0x180013b42  lea     rcx, [rbp+220h+pszDest]; lpSubKey
0x180013b46  mov     r9d, r12d
0x180013b49  mov     r8d, ebx
0x180013b4c  mov     edx, r13d
0x180013b4f  test    al, al
0x180013b51  jz      short loc_180013B6C
0x180013b53  lea     rax, [rbp+220h+var_26C]
0x180013b57  mov     [rsp+320h+var_2F8], rax; __int64
0x180013b5c  lea     rax, [rbp+220h+hMem]
0x180013b60  mov     [rsp+320h+pCount], rax; __int64
0x180013b65  call    BuildMachineAccessDACL
0x180013b6a  jmp     short loc_180013B8B
0x180013b6c  lea     rax, [rbp+220h+var_298]
0x180013b70  mov     [rsp+320h+var_2F8], rax; __int64
0x180013b75  lea     rax, [rbp+220h+hMem]
0x180013b79  mov     [rsp+320h+pCount], rax; __int64
0x180013b7e  call    BuildMachineAccessDACL
0x180013b83  mov     r14d, [rbp+220h+var_298]
0x180013b87  mov     [rbp+220h+var_28C], r14d
0x180013b8b  mov     rbx, [rbp+220h+hMem]
0x180013b8f  mov     edi, eax
0x180013b91  test    rbx, rbx
0x180013b94  mov     eax, 1
0x180013b99  cmovnz  r15d, eax
0x180013b9d  test    r13d, r13d
0x180013ba0  jnz     loc_180013D8E
0x180013ba6  test    r15d, r15d
0x180013ba9  jz      short loc_180013BB4
0x180013bab  test    r12d, r12d
0x180013bae  jnz     loc_180013D8E
0x180013bb4  mov     rcx, [rbp+220h+var_2A0]
0x180013bb8  lea     r9, [rbp+220h+ppSessionInfo]; ppSessionInfo
0x180013bbc  xor     r12d, r12d
0x180013bbf  mov     eax, r15d
0x180013bc2  xor     eax, 1
0x180013bc5  mov     [rbp+220h+ppSessionInfo], r12
0x180013bc9  xor     edx, edx; Reserved
0x180013bcb  mov     [rbp+220h+var_298], r12d
0x180013bcf  mov     [rcx], eax
0x180013bd1  lea     rax, [rbp+220h+var_298]
0x180013bd5  xor     ecx, ecx; hServer
0x180013bd7  mov     [rsp+320h+pCount], rax; pCount
0x180013bdc  lea     r8d, [r12+1]; Version
0x180013be1  call    cs:__imp_WTSEnumerateSessionsW
0x180013be7  test    eax, eax
0x180013be9  jz      loc_180013D84
0x180013bef  mov     eax, r12d
0x180013bf2  mov     r13d, r12d
0x180013bf5  mov     dword ptr [rbp+220h+hMem], eax
0x180013bf8  cmp     [rbp+220h+var_298], r12d
0x180013bfc  jbe     loc_180013D0B
0x180013c02  mov     r14d, [rbp+220h+var_294]
0x180013c06  mov     r11, [rbp+220h+ppSessionInfo]
0x180013c0a  mov     eax, r13d
0x180013c0d  mov     [rbp+220h+var_294], r12d
0x180013c11  lea     r10, [rax+rax*2]
0x180013c15  mov     ecx, [r11+r10*8+10h]
0x180013c1a  call    SessionNotActive
0x180013c1f  test    eax, eax
0x180013c21  jz      loc_180013CF7
0x180013c27  mov     eax, [rbp+220h+var_288]
0x180013c2a  lea     r9, [rbp+220h+var_270]
0x180013c2e  mov     ecx, [r11+r10*8]
0x180013c32  lea     r8, [rbp+220h+var_2A0]
0x180013c36  mov     dword ptr [rsp+320h+var_2F8], eax
0x180013c3a  lea     rdx, [rbp+220h+pszDest]
0x180013c3e  lea     rax, [rbp+220h+var_294]
0x180013c42  mov     [rbp+220h+var_270], r12d
0x180013c46  mov     [rsp+320h+pCount], rax
0x180013c4b  mov     [rbp+220h+var_2A0], r12
0x180013c4f  call    GetUserInformation
0x180013c54  mov     edi, eax
0x180013c56  test    eax, eax
0x180013c58  jnz     loc_180013CF7
0x180013c5e  mov     r12, [rbp+220h+var_2A0]
0x180013c62  test    r12, r12
0x180013c65  jz      loc_180013CF4
0x180013c6b  test    r15d, r15d
0x180013c6e  jnz     short loc_180013CB8
0x180013c70  mov     edi, [rbp+220h+var_294]
0x180013c73  mov     [rbp+220h+var_2A0], 0
0x180013c7b  test    edi, edi
0x180013c7d  jnz     short loc_180013CB8
0x180013c7f  mov     ecx, [rbp+220h+var_270]
0x180013c82  test    ecx, ecx
0x180013c84  jz      short loc_180013C90
0x180013c86  mov     dword ptr [rbp+220h+hMem], 1
0x180013c8d  mov     [rbp+220h+StringSecurityDescriptorLen], edi
0x180013c90  mov     rdx, [r12]
0x180013c94  lea     r9, [rbp+220h+var_2A0]
0x180013c98  mov     r8, rbx
0x180013c9b  call    BuildUserPolicyACL
0x180013ca0  mov     edi, eax
0x180013ca2  test    eax, eax
0x180013ca4  jnz     short loc_180013CB8
0x180013ca6  test    rbx, rbx
0x180013ca9  jz      short loc_180013CB4
0x180013cab  mov     rcx, rbx; hMem
0x180013cae  call    cs:__imp_LocalFree
0x180013cb4  mov     rbx, [rbp+220h+var_2A0]
0x180013cb8  test    r14d, r14d
0x180013cbb  jnz     short loc_180013CEB
0x180013cbd  mov     rcx, [r12]
0x180013cc1  lea     r8, [rbp+220h+var_2A0]
0x180013cc5  mov     rdx, rsi
0x180013cc8  mov     [rbp+220h+var_2A0], 0
0x180013cd0  call    BuildAuditPolicyACL
0x180013cd5  test    eax, eax
0x180013cd7  jnz     short loc_180013CEB
0x180013cd9  test    rsi, rsi
0x180013cdc  jz      short loc_180013CE7
0x180013cde  mov     rcx, rsi; hMem
0x180013ce1  call    cs:__imp_LocalFree
0x180013ce7  mov     rsi, [rbp+220h+var_2A0]
0x180013ceb  mov     rcx, r12; hMem
0x180013cee  call    cs:__imp_LocalFree
0x180013cf4  xor     r12d, r12d
0x180013cf7  inc     r13d
0x180013cfa  cmp     r13d, [rbp+220h+var_298]
0x180013cfe  jb      loc_180013C06
0x180013d04  mov     r14d, [rbp+220h+var_28C]
0x180013d08  mov     eax, dword ptr [rbp+220h+hMem]
0x180013d0b  test    r15d, r15d
0x180013d0e  jnz     short loc_180013D78
0x180013d10  test    eax, eax
0x180013d12  jnz     short loc_180013D3A
0x180013d14  mov     rcx, rbx; hMem
0x180013d17  call    cs:__imp_LocalFree
0x180013d1d  mov     rbx, r12
0x180013d20  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6> `wil::Feature<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::GetImpl(void)'::`2'::impl
0x180013d27  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::__private_IsEnabled(void)
0x180013d2c  test    al, al
0x180013d2e  jnz     short loc_180013D3F
0x180013d30  test    rsi, rsi
0x180013d33  mov     r14d, r12d
0x180013d36  setnz   r14b
0x180013d3a  test    rbx, rbx
0x180013d3d  jnz     short loc_180013D4A
0x180013d3f  test    rsi, rsi
0x180013d42  jz      short loc_180013D78
0x180013d44  cmp     [rbp+220h+var_288], r12d
0x180013d48  jnz     short loc_180013D78
0x180013d4a  lea     rdx, [rbp+220h+var_2A0]; NewAcl
0x180013d4e  mov     [rbp+220h+var_2A0], r12
0x180013d52  mov     rcx, rbx; OldAcl
0x180013d55  call    AddSystemToACL
0x180013d5a  mov     edi, eax
0x180013d5c  mov     rcx, rbx; hMem
0x180013d5f  test    eax, eax
0x180013d61  jnz     short loc_180013D6F
0x180013d63  call    cs:__imp_LocalFree
0x180013d69  mov     rbx, [rbp+220h+var_2A0]
0x180013d6d  jmp     short loc_180013D78
0x180013d6f  call    cs:__imp_LocalFree
0x180013d75  mov     rbx, r12
0x180013d78  mov     rcx, [rbp+220h+ppSessionInfo]; pMemory
0x180013d7c  call    cs:__imp_WTSFreeMemory
0x180013d82  jmp     short loc_180013D91
0x180013d84  call    cs:__imp_GetLastError
0x180013d8a  mov     edi, eax
0x180013d8c  jmp     short loc_180013D91
0x180013d8e  xor     r12d, r12d
0x180013d91  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6> `wil::Feature<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::GetImpl(void)'::`2'::impl
0x180013d98  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::__private_IsEnabled(void)
0x180013d9d  test    al, al
0x180013d9f  jz      short loc_180013DBB
0x180013da1  test    rsi, rsi
0x180013da4  jz      short loc_180013DB8
0x180013da6  cmp     dword ptr [rbp+220h+var_26C], r12d
0x180013daa  jz      short loc_180013DB8
0x180013dac  mov     r14d, 1
0x180013db2  cmp     [rbp+220h+StringSecurityDescriptorLen], r12d
0x180013db6  jnz     short loc_180013DBB
0x180013db8  mov     r14d, r12d
0x180013dbb  test    edi, edi
0x180013dbd  jnz     short loc_180013E32
0x180013dbf  test    rbx, rbx
0x180013dc2  jz      loc_180013E4F
0x180013dc8  lea     r8, [rbp+220h+var_26C+4]
0x180013dcc  mov     rdx, rsi; pSacl
  ... truncated ...
```
