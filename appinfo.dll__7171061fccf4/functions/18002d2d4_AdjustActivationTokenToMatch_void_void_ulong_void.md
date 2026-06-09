# AdjustActivationTokenToMatch(void *,void *,ulong,void * *)

- ea: `0x18002d2d4`
- end: `0x18002d84d`
- name: `?AdjustActivationTokenToMatch@@YAJPEAX0KPEAPEAX@Z`
- size: `1401`
- prototype: `LONG __fastcall(void *, void *, char, void **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b6c0`

## callees

- `0x18001d764`
- `0x18001e7bc`
- `0x18001efc0`
- `0x18001f940`
- `0x18002a8e8`
- `0x18002b084`
- `0x18002ce70`
- `0x18002d2d4`
- `0x180038b44`
- `0x18003bbc4`
- `0x18003bff0`
- `0x18003e7c4`
- `0x18003eb5c`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18002d333`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18002d333`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18002d3eb`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18002d3eb`
- `ntdll!RtlQueryPackageClaims` at `0x18002d41c`
- `ntdll!RtlQueryPackageClaims` at `0x18002d41c`
- `ntdll!NtQuerySecurityAttributesToken` at `0x18002d533`
- `ntdll!NtQuerySecurityAttributesToken` at `0x18002d533`
- `ext-ms-win-desktopappx-l1-1-5!DoesPackageHaveUIAccessCapability` at `0x18002d38c`
- `ext-ms-win-desktopappx-l1-1-5!DoesPackageHaveUIAccessCapability` at `0x18002d38c`

## pseudocode

```c
LONG __fastcall AdjustActivationTokenToMatch(void *a1, void *a2, char a3, void **a4)
{
  LONG result; // eax
  __int64 v9; // rdx
  bool v10; // cc
  int HaveUIAccessCapability; // eax
  unsigned int v12; // r8d
  _QWORD *v13; // rcx
  int v14; // edx
  int v15; // ebx
  int v16; // r8d
  __int64 v17; // rdi
  void *v18; // rbx
  int i; // eax
  int v20; // r8d
  unsigned int v21; // r15d
  void *v22; // rax
  void *v23; // rsi
  int v24; // esi
  __int64 v25; // rax
  unsigned __int16 *v26; // rdx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r8d
  int v30; // edi
  int v31; // [rsp+20h] [rbp-F0h]
  size_t Size; // [rsp+90h] [rbp-80h] BYREF
  __int64 v33; // [rsp+98h] [rbp-78h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-70h] BYREF
  UINT32 packageFullNameLength; // [rsp+A8h] [rbp-68h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+ACh] [rbp-64h] BYREF
  _QWORD v37[2]; // [rsp+B0h] [rbp-60h] BYREF
  _BYTE v38[16]; // [rsp+C0h] [rbp-50h] BYREF
  WCHAR packageFullName[128]; // [rsp+D0h] [rbp-40h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+1D0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+218h]

  packageFullNameLength = 128;
  applicationUserModelIdLength = 131;
  v34 = 0;
  *a4 = 0;
  result = GetPackageFullNameFromToken(a2, &packageFullNameLength, packageFullName);
  if ( result == 15700 )
    return 0;
  v10 = result <= 0;
  if ( result )
    goto LABEL_4;
  if ( (a3 & 4) != 0 )
  {
    LODWORD(v33) = 0;
    LOBYTE(v9) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialUIAccess>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CentennialUIAccess>::GetImpl'::`2'::impl,
      v9);
    if ( !(unsigned __int8)IsDoesPackageHaveUIAccessCapabilityPresent() )
      goto LABEL_11;
    HaveUIAccessCapability = DoesPackageHaveUIAccessCapability(packageFullName, &v33);
    if ( HaveUIAccessCapability < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x17B9,
        v12,
        (const char *)(unsigned int)HaveUIAccessCapability,
        v31);
      goto LABEL_11;
    }
    if ( !(_DWORD)v33 )
    {
LABEL_11:
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return -1073741637;
      v14 = 22;
LABEL_63:
      WPP_SF_SS(
        v13[2],
        v14,
        (unsigned int)WPP_b23fa736e9853481a42645a0499c03f5_Traceguids,
        (unsigned int)packageFullName,
        (__int64)applicationUserModelId);
      return -1073741637;
    }
  }
  result = GetApplicationUserModelIdFromToken(a2, &applicationUserModelIdLength, applicationUserModelId);
  v10 = result <= 0;
  if ( result )
  {
LABEL_4:
    if ( !v10 )
      return (unsigned __int16)result | 0xC0070000;
    return result;
  }
  v15 = RtlQueryPackageClaims(a2, 0, 0, 0, 0, 0, &v34, 0);
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DSS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        v16,
        v15,
        (__int64)packageFullName,
        (__int64)applicationUserModelId);
    return v15;
  }
  else
  {
    if ( (v34 & 4) == 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return -1073741637;
      v14 = 24;
      goto LABEL_63;
    }
    v33 = 0;
    v37[1] = L"WIN://SYSAPPGROUPID";
    v17 = 0;
    v37[0] = 2621478;
    v18 = 0;
    LODWORD(Size) = 0;
    for ( i = NtQuerySecurityAttributesToken(a2, v37, 1, 0, 0, &Size);
          ;
          i = NtQuerySecurityAttributesToken(a2, v37, 1, v23, Size, &Size) )
    {
      v24 = i;
      if ( !i )
        break;
      if ( i == -1073741275 )
        goto LABEL_37;
      if ( i != -1073741789 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_DSS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            v20,
            i,
            (__int64)packageFullName,
            (__int64)applicationUserModelId);
        if ( v18 )
LABEL_58:
          operator delete(v18);
LABEL_59:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
        return v24;
      }
      v21 = Size;
      v22 = operator new[]((unsigned int)Size, (const struct std::nothrow_t *)std::nothrow);
      v23 = v22;
      if ( v22 )
        memset_0(v22, 0, v21);
      else
        v23 = 0;
      if ( v18 )
        operator delete(v18);
      if ( !v23 )
      {
        v24 = -1073741801;
        goto LABEL_59;
      }
      v18 = v23;
    }
    if ( !*((_DWORD *)v18 + 1)
      || (v25 = *((_QWORD *)v18 + 1)) == 0
      || *(_WORD *)(v25 + 16) != 3
      || (v26 = *(unsigned __int16 **)(v25 + 32)) == 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          (unsigned int)WPP_b23fa736e9853481a42645a0499c03f5_Traceguids,
          (unsigned int)packageFullName,
          (__int64)applicationUserModelId);
      v24 = -1073741811;
      goto LABEL_58;
    }
    v27 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            v38,
            *((_QWORD *)v26 + 1),
            (unsigned __int64)*v26 >> 1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v33,
      v27);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v38);
    v17 = v33;
    if ( !v33 )
    {
      v24 = -1073741801;
      goto LABEL_58;
    }
LABEL_37:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl'::`2'::impl) )
      v28 = AdjustActivationToken(
              a1,
              1,
              0,
              0,
              (v34 & 0x8000) != 0,
              (v34 & 0x20000) != 0,
              (v34 & 0x2000) != 0,
              (v34 & 0x80000) != 0,
              (v34 & 0x100000) != 0,
              (v34 & 0x10) != 0,
              (v34 & 0x200000) != 0,
              0,
              packageFullName,
              applicationUserModelId,
              0,
              0,
              v17,
              a4);
    else
      v28 = AdjustActivationToken(
              a1,
              1,
              0,
              0,
              (v34 & 0x8000) != 0,
              (v34 & 0x20000) != 0,
              (v34 & 0x2000) != 0,
              (v34 & 0x80000) != 0,
              (v34 & 0x100000) != 0,
              (v34 & 0x10) != 0,
              0,
              0,
              packageFullName,
              applicationUserModelId,
              0,
              0,
              v17,
              a4);
    v30 = v28;
    if ( v28 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DSS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        v29,
        v28,
        (__int64)packageFullName,
        (__int64)applicationUserModelId);
    if ( v18 )
      operator delete(v18);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
    return v30;
  }
}

```

## disassembly

```asm
0x18002d2d4  mov     [rsp-8+arg_10], rbx
0x18002d2d9  push    rbp
0x18002d2da  push    rsi
0x18002d2db  push    rdi
0x18002d2dc  push    r12
0x18002d2de  push    r13
0x18002d2e0  push    r14
0x18002d2e2  push    r15
0x18002d2e4  lea     rbp, [rsp-1E0h]
0x18002d2ec  sub     rsp, 2F0h
0x18002d2f3  mov     rax, cs:__security_cookie
0x18002d2fa  xor     rax, rsp
0x18002d2fd  mov     [rbp+210h+var_40], rax
0x18002d304  mov     r14, rdx
0x18002d307  mov     [rbp+210h+packageFullNameLength], 80h
0x18002d30e  mov     ebx, r8d
0x18002d311  mov     [rbp+210h+applicationUserModelIdLength], 83h
0x18002d318  mov     r13, rcx
0x18002d31b  lea     r8, [rbp+210h+packageFullName]; packageFullName
0x18002d31f  xor     r15d, r15d
0x18002d322  lea     rdx, [rbp+210h+packageFullNameLength]; packageFullNameLength
0x18002d326  mov     rcx, r14; token
0x18002d329  mov     [rbp+210h+var_280], r15
0x18002d32d  mov     r12, r9
0x18002d330  mov     [r9], r15
0x18002d333  call    cs:__imp_GetPackageFullNameFromToken
0x18002d339  cmp     eax, 3D54h
0x18002d33e  jnz     short loc_18002D347
0x18002d340  xor     eax, eax
0x18002d342  jmp     loc_18002D823
0x18002d347  test    eax, eax
0x18002d349  jz      short loc_18002D35E
0x18002d34b  jle     loc_18002D823
0x18002d351  movzx   eax, ax
0x18002d354  or      eax, 0C0070000h
0x18002d359  jmp     loc_18002D823
0x18002d35e  mov     esi, 1
0x18002d363  test    bl, 4
0x18002d366  jz      short loc_18002D3DD
0x18002d368  mov     dword ptr [rbp+210h+var_288], r15d
0x18002d36c  mov     dl, sil
0x18002d36f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CentennialUIAccess@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialUIAccess@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialUIAccess> `wil::Feature<__WilFeatureTraits_Feature_CentennialUIAccess>::GetImpl(void)'::`2'::impl
0x18002d376  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialUIAccess@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialUIAccess>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002d37b  call    IsDoesPackageHaveUIAccessCapabilityPresent
0x18002d380  test    al, al
0x18002d382  jz      short loc_18002D3B2
0x18002d384  lea     rdx, [rbp+210h+var_288]
0x18002d388  lea     rcx, [rbp+210h+packageFullName]
0x18002d38c  call    cs:__imp_DoesPackageHaveUIAccessCapability
0x18002d392  test    eax, eax
0x18002d394  jns     short loc_18002D3AC
0x18002d396  mov     rcx, [rbp+218h]; this
0x18002d39d  mov     r9d, eax; char *
0x18002d3a0  mov     edx, 17B9h; void *
0x18002d3a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d3aa  jmp     short loc_18002D3B2
0x18002d3ac  cmp     dword ptr [rbp+210h+var_288], r15d
0x18002d3b0  jnz     short loc_18002D3DD
0x18002d3b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3b9  lea     rax, WPP_GLOBAL_Control
0x18002d3c0  cmp     rcx, rax
0x18002d3c3  jz      loc_18002D81E
0x18002d3c9  test    [rcx+1Ch], sil
0x18002d3cd  jz      loc_18002D81E
0x18002d3d3  mov     edx, 16h
0x18002d3d8  jmp     loc_18002D7FE
0x18002d3dd  lea     r8, [rbp+210h+applicationUserModelId]; applicationUserModelId
0x18002d3e4  mov     rcx, r14; token
0x18002d3e7  lea     rdx, [rbp+210h+applicationUserModelIdLength]; applicationUserModelIdLength
0x18002d3eb  call    cs:__imp_GetApplicationUserModelIdFromToken
0x18002d3f1  test    eax, eax
0x18002d3f3  jnz     loc_18002D34B
0x18002d3f9  mov     [rsp+320h+var_2E8], r15
0x18002d3fe  lea     rax, [rbp+210h+var_280]
0x18002d402  mov     [rsp+320h+var_2F0], rax
0x18002d407  xor     r9d, r9d
0x18002d40a  mov     [rsp+320h+var_2F8], r15
0x18002d40f  xor     r8d, r8d
0x18002d412  xor     edx, edx
0x18002d414  mov     [rsp+320h+var_300], r15
0x18002d419  mov     rcx, r14
0x18002d41c  call    cs:__imp_RtlQueryPackageClaims
0x18002d422  mov     ebx, eax
0x18002d424  test    eax, eax
0x18002d426  jz      short loc_18002D46E
0x18002d428  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d42f  lea     rax, WPP_GLOBAL_Control
0x18002d436  cmp     rcx, rax
0x18002d439  jz      short loc_18002D467
0x18002d43b  test    [rcx+1Ch], sil
0x18002d43f  jz      short loc_18002D467
0x18002d441  mov     rcx, [rcx+10h]
0x18002d445  lea     rax, [rbp+210h+applicationUserModelId]
0x18002d44c  mov     [rsp+320h+var_2F8], rax
0x18002d451  mov     edx, 17h
0x18002d456  lea     rax, [rbp+210h+packageFullName]
0x18002d45a  mov     r9d, ebx
0x18002d45d  mov     [rsp+320h+var_300], rax
0x18002d462  call    WPP_SF_DSS
0x18002d467  mov     eax, ebx
0x18002d469  jmp     loc_18002D823
0x18002d46e  test    byte ptr [rbp+210h+var_280], 4
0x18002d472  jz      loc_18002D7E0
0x18002d478  lea     rax, aWinSysappgroup; "WIN://SYSAPPGROUPID"
0x18002d47f  mov     [rbp+210h+var_288], r15
0x18002d483  mov     [rbp+210h+var_268], rax
0x18002d487  mov     rdi, r15
0x18002d48a  lea     rax, [rbp+210h+Size]
0x18002d48e  mov     [rbp+210h+var_270], 280026h
0x18002d496  mov     [rsp+320h+var_2F8], rax
0x18002d49b  mov     rbx, r15
0x18002d49e  mov     dword ptr [rsp+320h+var_300], r15d
0x18002d4a3  xor     r9d, r9d
0x18002d4a6  mov     dword ptr [rbp+210h+Size], r15d
0x18002d4aa  mov     r8d, esi
0x18002d4ad  jmp     short loc_18002D52C
0x18002d4af  cmp     esi, 0C0000225h
0x18002d4b5  jz      loc_18002D5A8
0x18002d4bb  cmp     esi, 0C0000023h
0x18002d4c1  jnz     loc_18002D65E
0x18002d4c7  mov     r15d, dword ptr [rbp+210h+Size]
0x18002d4cb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002d4d2  mov     ecx, r15d; unsigned __int64
0x18002d4d5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002d4da  mov     rsi, rax
0x18002d4dd  test    rax, rax
0x18002d4e0  jz      short loc_18002D4F4
0x18002d4e2  mov     r8d, r15d; Size
0x18002d4e5  xor     edx, edx; Val
0x18002d4e7  mov     rcx, rax; void *
0x18002d4ea  call    memset_0
0x18002d4ef  xor     r15d, r15d
0x18002d4f2  jmp     short loc_18002D4FA
0x18002d4f4  xor     r15d, r15d
0x18002d4f7  mov     esi, r15d
0x18002d4fa  test    rbx, rbx
0x18002d4fd  jz      short loc_18002D507
0x18002d4ff  mov     rcx, rbx; Block
0x18002d502  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d507  test    rsi, rsi
0x18002d50a  jz      loc_18002D654
0x18002d510  mov     eax, dword ptr [rbp+210h+Size]
0x18002d513  lea     rcx, [rbp+210h+Size]
0x18002d517  mov     [rsp+320h+var_2F8], rcx
0x18002d51c  mov     rbx, rsi
0x18002d51f  mov     dword ptr [rsp+320h+var_300], eax
0x18002d523  mov     r9, rsi
0x18002d526  mov     r8d, 1
0x18002d52c  lea     rdx, [rbp+210h+var_270]
0x18002d530  mov     rcx, r14
0x18002d533  call    cs:__imp_NtQuerySecurityAttributesToken
0x18002d539  mov     esi, eax
0x18002d53b  test    eax, eax
0x18002d53d  jnz     loc_18002D4AF
0x18002d543  cmp     [rbx+4], r15d
0x18002d547  jz      loc_18002D788
0x18002d54d  mov     rax, [rbx+8]
0x18002d551  test    rax, rax
0x18002d554  jz      loc_18002D788
0x18002d55a  cmp     word ptr [rax+10h], 3
0x18002d55f  jnz     loc_18002D788
0x18002d565  mov     rdx, [rax+20h]
0x18002d569  test    rdx, rdx
0x18002d56c  jz      loc_18002D788
0x18002d572  movzx   r8d, word ptr [rdx]
0x18002d576  lea     rcx, [rbp+210h+var_260]
0x18002d57a  mov     rdx, [rdx+8]
0x18002d57e  shr     r8, 1
0x18002d581  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002d586  mov     rdx, rax
0x18002d589  lea     rcx, [rbp+210h+var_288]
0x18002d58d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002d592  lea     rcx, [rbp+210h+var_260]
0x18002d596  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d59b  mov     rdi, [rbp+210h+var_288]
0x18002d59f  test    rdi, rdi
0x18002d5a2  jz      loc_18002D781
0x18002d5a8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x18002d5af  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x18002d5b4  mov     [rsp+320h+var_298], r12
0x18002d5bc  test    al, al
0x18002d5be  mov     rax, [rbp+210h+var_280]
0x18002d5c2  mov     r14d, 1
0x18002d5c8  mov     [rsp+320h+var_2A0], rdi
0x18002d5d0  mov     r10d, eax
0x18002d5d3  mov     [rsp+320h+var_2A8], r15
0x18002d5d8  mov     r9d, eax
0x18002d5db  mov     r8d, eax
0x18002d5de  mov     [rsp+320h+var_2B0], r15
0x18002d5e3  mov     edx, eax
0x18002d5e5  jz      loc_18002D6AB
0x18002d5eb  lea     rcx, [rbp+210h+applicationUserModelId]
0x18002d5f2  shr     r10d, 14h
0x18002d5f6  mov     [rsp+320h+var_2B8], rcx
0x18002d5fb  and     r10b, r14b
0x18002d5fe  shr     r9d, 13h
0x18002d602  lea     rcx, [rbp+210h+packageFullName]
0x18002d606  mov     [rsp+320h+var_2C0], rcx
0x18002d60b  and     r9b, r14b
0x18002d60e  mov     [rsp+320h+var_2C8], r15b
0x18002d613  mov     esi, eax
0x18002d615  shr     esi, 15h
0x18002d618  mov     r11d, eax
0x18002d61b  shr     r11d, 4
0x18002d61f  and     sil, r14b
0x18002d622  mov     [rsp+320h+var_2D0], sil
0x18002d627  and     r11b, r14b
0x18002d62a  mov     [rsp+320h+var_2D8], r11b
0x18002d62f  mov     [rsp+320h+var_2E0], r10b
0x18002d634  shr     r8d, 0Dh
0x18002d638  and     r8b, r14b
0x18002d63b  mov     byte ptr [rsp+320h+var_2E8], r9b
0x18002d640  shr     edx, 11h
0x18002d643  and     dl, r14b
0x18002d646  mov     byte ptr [rsp+320h+var_2F0], r8b
0x18002d64b  mov     byte ptr [rsp+320h+var_2F8], dl
0x18002d64f  jmp     loc_18002D704
0x18002d654  mov     esi, 0C0000017h
0x18002d659  jmp     loc_18002D7D3
0x18002d65e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d665  lea     rax, WPP_GLOBAL_Control
0x18002d66c  cmp     rcx, rax
0x18002d66f  jz      short loc_18002D69D
0x18002d671  test    byte ptr [rcx+1Ch], 1
0x18002d675  jz      short loc_18002D69D
0x18002d677  mov     rcx, [rcx+10h]
0x18002d67b  lea     rax, [rbp+210h+applicationUserModelId]
0x18002d682  mov     [rsp+320h+var_2F8], rax
0x18002d687  mov     edx, 1Ah
0x18002d68c  lea     rax, [rbp+210h+packageFullName]
0x18002d690  mov     r9d, esi
0x18002d693  mov     [rsp+320h+var_300], rax
0x18002d698  call    WPP_SF_DSS
0x18002d69d  test    rbx, rbx
0x18002d6a0  jz      loc_18002D7D3
0x18002d6a6  jmp     loc_18002D7CB
0x18002d6ab  lea     r11, [rbp+210h+applicationUserModelId]
0x18002d6b2  shr     r10d, 4
0x18002d6b6  mov     [rsp+320h+var_2B8], r11
0x18002d6bb  and     r10b, r14b
0x18002d6be  shr     r9d, 14h
0x18002d6c2  lea     r11, [rbp+210h+packageFullName]
0x18002d6c6  mov     [rsp+320h+var_2C0], r11
0x18002d6cb  and     r9b, r14b
0x18002d6ce  mov     [rsp+320h+var_2C8], r15b
0x18002d6d3  mov     ecx, eax
0x18002d6d5  mov     [rsp+320h+var_2D0], r15b
0x18002d6da  mov     [rsp+320h+var_2D8], r10b
0x18002d6df  mov     [rsp+320h+var_2E0], r9b
0x18002d6e4  shr     r8d, 13h
0x18002d6e8  shr     edx, 0Dh
0x18002d6eb  and     r8b, r14b
0x18002d6ee  and     dl, r14b
0x18002d6f1  mov     byte ptr [rsp+320h+var_2E8], r8b
0x18002d6f6  shr     ecx, 11h
0x18002d6f9  and     cl, r14b
0x18002d6fc  mov     byte ptr [rsp+320h+var_2F0], dl
0x18002d700  mov     byte ptr [rsp+320h+var_2F8], cl
0x18002d704  shr     eax, 0Fh
0x18002d707  xor     r9d, r9d
0x18002d70a  and     al, r14b
0x18002d70d  xor     r8d, r8d
0x18002d710  mov     edx, r14d
0x18002d713  mov     byte ptr [rsp+320h+var_300], al
0x18002d717  mov     rcx, r13
0x18002d71a  call    ?AdjustActivationToken@@YAJPEAXW4RuntimeBehavior@AppModel@@_N222222222PEBG3PEA_KPEAU_GUID@@3PEAPEAX@Z; AdjustActivationToken(void *,AppModel::RuntimeBehavior,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,ushort const *,ushort const *,unsigned __int64 *,_GUID *,ushort const *,void * *)
0x18002d71f  mov     edi, eax
0x18002d721  test    eax, eax
0x18002d723  jz      short loc_18002D764
0x18002d725  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d72c  lea     rax, WPP_GLOBAL_Control
0x18002d733  cmp     rcx, rax
0x18002d736  jz      short loc_18002D764
0x18002d738  test    [rcx+1Ch], r14b
0x18002d73c  jz      short loc_18002D764
0x18002d73e  mov     rcx, [rcx+10h]
0x18002d742  lea     rax, [rbp+210h+applicationUserModelId]
0x18002d749  mov     [rsp+320h+var_2F8], rax
0x18002d74e  mov     edx, 1Bh
0x18002d753  lea     rax, [rbp+210h+packageFullName]
0x18002d757  mov     r9d, edi
0x18002d75a  mov     [rsp+320h+var_300], rax
0x18002d75f  call    WPP_SF_DSS
0x18002d764  test    rbx, rbx
0x18002d767  jz      short loc_18002D771
0x18002d769  mov     rcx, rbx; Block
0x18002d76c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d771  lea     rcx, [rbp+210h+var_288]
0x18002d775  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d77a  mov     eax, edi
0x18002d77c  jmp     loc_18002D823
0x18002d781  mov     esi, 0C0000017h
0x18002d786  jmp     short loc_18002D7CB
0x18002d788  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d78f  lea     rax, WPP_GLOBAL_Control
0x18002d796  cmp     rcx, rax
0x18002d799  jz      short loc_18002D7C6
0x18002d79b  test    byte ptr [rcx+1Ch], 1
0x18002d79f  jz      short loc_18002D7C6
0x18002d7a1  mov     rcx, [rcx+10h]
  ... truncated ...
```
