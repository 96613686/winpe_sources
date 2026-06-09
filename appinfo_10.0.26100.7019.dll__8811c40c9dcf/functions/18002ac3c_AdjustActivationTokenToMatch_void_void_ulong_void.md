# AdjustActivationTokenToMatch(void *,void *,ulong,void * *)

- ea: `0x18002ac3c`
- end: `0x18002b1d6`
- name: `?AdjustActivationTokenToMatch@@YAJPEAX0KPEAPEAX@Z`
- size: `1434`
- prototype: `int(void *, void *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019334`

## callees

- `0x18001b0c4`
- `0x18001b8cc`
- `0x18001c0ac`
- `0x180027f88`
- `0x180028820`
- `0x180028a38`
- `0x18002a750`
- `0x18002ac3c`
- `0x180035d08`
- `0x180038dac`
- `0x1800391c4`
- `0x18003b384`
- `0x18003b754`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18002ac9b`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18002ac9b`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18002ad5f`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18002ad5f`
- `ntdll!RtlQueryPackageClaims` at `0x18002ad96`
- `ntdll!RtlQueryPackageClaims` at `0x18002ad96`
- `ntdll!NtQuerySecurityAttributesToken` at `0x18002aeb3`
- `ntdll!NtQuerySecurityAttributesToken` at `0x18002aeb3`
- `ext-ms-win-desktopappx-l1-1-5!DoesPackageHaveUIAccessCapability` at `0x18002acfa`
- `ext-ms-win-desktopappx-l1-1-5!DoesPackageHaveUIAccessCapability` at `0x18002acfa`

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
  void *v24; // rcx
  int v25; // esi
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  int v29; // edi
  int v30; // r8d
  int v31; // [rsp+20h] [rbp-F0h]
  int v32; // [rsp+20h] [rbp-F0h]
  int v33; // [rsp+28h] [rbp-E8h]
  int v34; // [rsp+30h] [rbp-E0h]
  int v35; // [rsp+38h] [rbp-D8h]
  bool v36; // [rsp+50h] [rbp-C0h]
  size_t Size; // [rsp+90h] [rbp-80h] BYREF
  __int64 v38; // [rsp+98h] [rbp-78h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-70h] BYREF
  UINT32 packageFullNameLength; // [rsp+A8h] [rbp-68h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+ACh] [rbp-64h] BYREF
  _QWORD v42[2]; // [rsp+B0h] [rbp-60h] BYREF
  _BYTE v43[16]; // [rsp+C0h] [rbp-50h] BYREF
  WCHAR packageFullName[128]; // [rsp+D0h] [rbp-40h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+1D0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+218h]

  packageFullNameLength = 128;
  applicationUserModelIdLength = 131;
  v39 = 0;
  *a4 = 0;
  result = GetPackageFullNameFromToken(a2, &packageFullNameLength, packageFullName);
  if ( result == 15700 )
    return 0;
  v10 = result <= 0;
  if ( result )
    goto LABEL_4;
  if ( (a3 & 4) != 0 )
  {
    LODWORD(v38) = 0;
    LOBYTE(v9) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialUIAccess>::ReportUsage(
      &`wil::Feature<__WilFeatureTraits_Feature_CentennialUIAccess>::GetImpl'::`2'::impl,
      v9);
    if ( !(unsigned __int8)IsDoesPackageHaveUIAccessCapabilityPresent() )
      goto LABEL_11;
    HaveUIAccessCapability = DoesPackageHaveUIAccessCapability(packageFullName, &v38);
    if ( HaveUIAccessCapability < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x146D,
        v12,
        (const char *)(unsigned int)HaveUIAccessCapability,
        v31);
      goto LABEL_11;
    }
    if ( !(_DWORD)v38 )
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
        (unsigned int)&WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids,
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
  v15 = RtlQueryPackageClaims(a2, 0, 0, 0, 0, 0, &v39, 0);
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
    if ( (v39 & 4) == 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return -1073741637;
      v14 = 24;
      goto LABEL_63;
    }
    v38 = 0;
    v42[1] = L"WIN://SYSAPPGROUPID";
    v17 = 0;
    v42[0] = 2621478;
    v18 = 0;
    LODWORD(Size) = 0;
    for ( i = NtQuerySecurityAttributesToken(a2, v42, 1, 0, 0, &Size);
          ;
          i = NtQuerySecurityAttributesToken(a2, v42, 1, v23, Size, &Size) )
    {
      v25 = i;
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
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
        return v25;
      }
      v21 = Size;
      v22 = operator new[]((unsigned int)Size, (const struct std::nothrow_t *)&std::nothrow);
      v23 = v22;
      if ( v22 )
        memset_0(v22, 0, v21);
      else
        v23 = 0;
      v24 = v18;
      v18 = v23;
      if ( v24 )
        operator delete(v24);
      if ( !v23 )
      {
        v25 = -1073741801;
        goto LABEL_59;
      }
    }
    if ( !*((_DWORD *)v18 + 1)
      || (v26 = *((_QWORD *)v18 + 1)) == 0
      || *(_WORD *)(v26 + 16) != 3
      || (v27 = *(_QWORD *)(v26 + 32)) == 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          (unsigned int)&WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids,
          (unsigned int)packageFullName,
          (__int64)applicationUserModelId);
      v25 = -1073741811;
      goto LABEL_58;
    }
    v28 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            v43,
            *(_QWORD *)(v27 + 8),
            (unsigned __int64)(unsigned __int16)*(_DWORD *)v27 >> 1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v38,
      v28);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v43);
    v17 = v38;
    if ( !v38 )
    {
      v25 = -1073741801;
      goto LABEL_58;
    }
LABEL_37:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl'::`2'::impl) )
      v36 = (v39 & 0x200000) != 0;
    else
      v36 = 0;
    LOBYTE(v35) = (v39 & 0x80000) != 0;
    LOBYTE(v34) = (v39 & 0x2000) != 0;
    LOBYTE(v33) = (v39 & 0x20000) != 0;
    LOBYTE(v32) = (v39 & 0x8000) != 0;
    v29 = AdjustActivationToken(
            a1,
            1,
            0,
            0,
            v32,
            v33,
            v34,
            v35,
            (v39 & 0x100000) != 0,
            (v39 & 0x10) != 0,
            v36,
            0,
            packageFullName,
            applicationUserModelId,
            0,
            0,
            v17,
            a4);
    if ( v29 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DSS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        v30,
        v29,
        (__int64)packageFullName,
        (__int64)applicationUserModelId);
    if ( v18 )
      operator delete(v18);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
    return v29;
  }
}

```

## disassembly

```asm
0x18002ac3c  mov     [rsp-8+arg_10], rbx
0x18002ac41  push    rbp
0x18002ac42  push    rsi
0x18002ac43  push    rdi
0x18002ac44  push    r12
0x18002ac46  push    r13
0x18002ac48  push    r14
0x18002ac4a  push    r15
0x18002ac4c  lea     rbp, [rsp-1E0h]
0x18002ac54  sub     rsp, 2F0h
0x18002ac5b  mov     rax, cs:__security_cookie
0x18002ac62  xor     rax, rsp
0x18002ac65  mov     [rbp+210h+var_40], rax
0x18002ac6c  mov     r14, rdx
0x18002ac6f  mov     [rbp+210h+packageFullNameLength], 80h
0x18002ac76  mov     ebx, r8d
0x18002ac79  mov     [rbp+210h+applicationUserModelIdLength], 83h
0x18002ac80  mov     r13, rcx
0x18002ac83  lea     r8, [rbp+210h+packageFullName]; packageFullName
0x18002ac87  xor     r15d, r15d
0x18002ac8a  lea     rdx, [rbp+210h+packageFullNameLength]; packageFullNameLength
0x18002ac8e  mov     rcx, r14; token
0x18002ac91  mov     [rbp+210h+var_280], r15
0x18002ac95  mov     r12, r9
0x18002ac98  mov     [r9], r15
0x18002ac9b  call    cs:__imp_GetPackageFullNameFromToken
0x18002aca2  nop     dword ptr [rax+rax+00h]
0x18002aca7  cmp     eax, 3D54h
0x18002acac  jnz     short loc_18002ACB5
0x18002acae  xor     eax, eax
0x18002acb0  jmp     loc_18002B1AB
0x18002acb5  test    eax, eax
0x18002acb7  jz      short loc_18002ACCC
0x18002acb9  jle     loc_18002B1AB
0x18002acbf  movzx   eax, ax
0x18002acc2  or      eax, 0C0070000h
0x18002acc7  jmp     loc_18002B1AB
0x18002accc  mov     esi, 1
0x18002acd1  test    bl, 4
0x18002acd4  jz      short loc_18002AD51
0x18002acd6  mov     dword ptr [rbp+210h+var_288], r15d
0x18002acda  mov     dl, sil
0x18002acdd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CentennialUIAccess@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialUIAccess@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialUIAccess> `wil::Feature<__WilFeatureTraits_Feature_CentennialUIAccess>::GetImpl(void)'::`2'::impl
0x18002ace4  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialUIAccess@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialUIAccess>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002ace9  call    IsDoesPackageHaveUIAccessCapabilityPresent
0x18002acee  test    al, al
0x18002acf0  jz      short loc_18002AD26
0x18002acf2  lea     rdx, [rbp+210h+var_288]
0x18002acf6  lea     rcx, [rbp+210h+packageFullName]
0x18002acfa  call    cs:__imp_DoesPackageHaveUIAccessCapability
0x18002ad01  nop     dword ptr [rax+rax+00h]
0x18002ad06  test    eax, eax
0x18002ad08  jns     short loc_18002AD20
0x18002ad0a  mov     rcx, [rbp+218h]; this
0x18002ad11  mov     r9d, eax; char *
0x18002ad14  mov     edx, 146Dh; void *
0x18002ad19  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ad1e  jmp     short loc_18002AD26
0x18002ad20  cmp     dword ptr [rbp+210h+var_288], r15d
0x18002ad24  jnz     short loc_18002AD51
0x18002ad26  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad2d  lea     rax, WPP_GLOBAL_Control
0x18002ad34  cmp     rcx, rax
0x18002ad37  jz      loc_18002B1A6
0x18002ad3d  test    [rcx+1Ch], sil
0x18002ad41  jz      loc_18002B1A6
0x18002ad47  mov     edx, 16h
0x18002ad4c  jmp     loc_18002B186
0x18002ad51  lea     r8, [rbp+210h+applicationUserModelId]; applicationUserModelId
0x18002ad58  mov     rcx, r14; token
0x18002ad5b  lea     rdx, [rbp+210h+applicationUserModelIdLength]; applicationUserModelIdLength
0x18002ad5f  call    cs:__imp_GetApplicationUserModelIdFromToken
0x18002ad66  nop     dword ptr [rax+rax+00h]
0x18002ad6b  test    eax, eax
0x18002ad6d  jnz     loc_18002ACB9
0x18002ad73  mov     [rsp+320h+var_2E8], r15
0x18002ad78  lea     rax, [rbp+210h+var_280]
0x18002ad7c  mov     [rsp+320h+var_2F0], rax
0x18002ad81  xor     r9d, r9d
0x18002ad84  mov     [rsp+320h+var_2F8], r15
0x18002ad89  xor     r8d, r8d
0x18002ad8c  xor     edx, edx
0x18002ad8e  mov     [rsp+320h+var_300], r15
0x18002ad93  mov     rcx, r14
0x18002ad96  call    cs:__imp_RtlQueryPackageClaims
0x18002ad9d  nop     dword ptr [rax+rax+00h]
0x18002ada2  mov     ebx, eax
0x18002ada4  test    eax, eax
0x18002ada6  jz      short loc_18002ADEE
0x18002ada8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002adaf  lea     rax, WPP_GLOBAL_Control
0x18002adb6  cmp     rcx, rax
0x18002adb9  jz      short loc_18002ADE7
0x18002adbb  test    [rcx+1Ch], sil
0x18002adbf  jz      short loc_18002ADE7
0x18002adc1  mov     rcx, [rcx+10h]
0x18002adc5  lea     rax, [rbp+210h+applicationUserModelId]
0x18002adcc  mov     [rsp+320h+var_2F8], rax
0x18002add1  mov     edx, 17h
0x18002add6  lea     rax, [rbp+210h+packageFullName]
0x18002adda  mov     r9d, ebx
0x18002addd  mov     [rsp+320h+var_300], rax
0x18002ade2  call    WPP_SF_DSS
0x18002ade7  mov     eax, ebx
0x18002ade9  jmp     loc_18002B1AB
0x18002adee  test    byte ptr [rbp+210h+var_280], 4
0x18002adf2  jz      loc_18002B168
0x18002adf8  lea     rax, aWinSysappgroup; "WIN://SYSAPPGROUPID"
0x18002adff  mov     [rbp+210h+var_288], r15
0x18002ae03  mov     [rbp+210h+var_268], rax
0x18002ae07  mov     rdi, r15
0x18002ae0a  lea     rax, [rbp+210h+Size]
0x18002ae0e  mov     [rbp+210h+var_270], 280026h
0x18002ae16  mov     [rsp+320h+var_2F8], rax
0x18002ae1b  mov     rbx, r15
0x18002ae1e  mov     dword ptr [rsp+320h+var_300], r15d
0x18002ae23  xor     r9d, r9d
0x18002ae26  mov     dword ptr [rbp+210h+Size], r15d
0x18002ae2a  mov     r8d, esi
0x18002ae2d  jmp     short loc_18002AEAC
0x18002ae2f  cmp     esi, 0C0000225h
0x18002ae35  jz      loc_18002AF30
0x18002ae3b  cmp     esi, 0C0000023h
0x18002ae41  jnz     loc_18002AFE6
0x18002ae47  mov     r15d, dword ptr [rbp+210h+Size]
0x18002ae4b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ae52  mov     ecx, r15d; unsigned __int64
0x18002ae55  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002ae5a  mov     rsi, rax
0x18002ae5d  test    rax, rax
0x18002ae60  jz      short loc_18002AE74
0x18002ae62  mov     r8d, r15d; Size
0x18002ae65  xor     edx, edx; Val
0x18002ae67  mov     rcx, rax; void *
0x18002ae6a  call    memset_0
0x18002ae6f  xor     r15d, r15d
0x18002ae72  jmp     short loc_18002AE7A
0x18002ae74  xor     r15d, r15d
0x18002ae77  mov     esi, r15d
0x18002ae7a  mov     rcx, rbx; Block
0x18002ae7d  mov     rbx, rsi
0x18002ae80  test    rcx, rcx
0x18002ae83  jz      short loc_18002AE8A
0x18002ae85  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ae8a  test    rsi, rsi
0x18002ae8d  jz      loc_18002AFDC
0x18002ae93  lea     rax, [rbp+210h+Size]
0x18002ae97  mov     r9, rsi
0x18002ae9a  mov     [rsp+320h+var_2F8], rax
0x18002ae9f  mov     r8d, 1
0x18002aea5  mov     eax, dword ptr [rbp+210h+Size]
0x18002aea8  mov     dword ptr [rsp+320h+var_300], eax
0x18002aeac  lea     rdx, [rbp+210h+var_270]
0x18002aeb0  mov     rcx, r14
0x18002aeb3  call    cs:__imp_NtQuerySecurityAttributesToken
0x18002aeba  nop     dword ptr [rax+rax+00h]
0x18002aebf  mov     esi, eax
0x18002aec1  test    eax, eax
0x18002aec3  jnz     loc_18002AE2F
0x18002aec9  cmp     [rbx+4], r15d
0x18002aecd  jz      loc_18002B110
0x18002aed3  mov     rax, [rbx+8]
0x18002aed7  test    rax, rax
0x18002aeda  jz      loc_18002B110
0x18002aee0  cmp     word ptr [rax+10h], 3
0x18002aee5  jnz     loc_18002B110
0x18002aeeb  mov     rcx, [rax+20h]
0x18002aeef  test    rcx, rcx
0x18002aef2  jz      loc_18002B110
0x18002aef8  mov     eax, [rcx]
0x18002aefa  mov     rdx, [rcx+8]
0x18002aefe  lea     rcx, [rbp+210h+var_260]
0x18002af02  movzx   r8d, ax
0x18002af06  shr     r8, 1
0x18002af09  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002af0e  mov     rdx, rax
0x18002af11  lea     rcx, [rbp+210h+var_288]
0x18002af15  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002af1a  lea     rcx, [rbp+210h+var_260]
0x18002af1e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002af23  mov     rdi, [rbp+210h+var_288]
0x18002af27  test    rdi, rdi
0x18002af2a  jz      loc_18002B109
0x18002af30  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x18002af37  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x18002af3c  mov     [rsp+320h+var_298], r12
0x18002af44  test    al, al
0x18002af46  mov     rax, [rbp+210h+var_280]
0x18002af4a  mov     r14d, 1
0x18002af50  mov     [rsp+320h+var_2A0], rdi
0x18002af58  mov     r10d, eax
0x18002af5b  mov     [rsp+320h+var_2A8], r15
0x18002af60  mov     r9d, eax
0x18002af63  mov     r8d, eax
0x18002af66  mov     [rsp+320h+var_2B0], r15
0x18002af6b  mov     edx, eax
0x18002af6d  jz      loc_18002B033
0x18002af73  lea     rcx, [rbp+210h+applicationUserModelId]
0x18002af7a  shr     r10d, 14h
0x18002af7e  mov     [rsp+320h+var_2B8], rcx
0x18002af83  and     r10b, r14b
0x18002af86  shr     r9d, 13h
0x18002af8a  lea     rcx, [rbp+210h+packageFullName]
0x18002af8e  mov     [rsp+320h+var_2C0], rcx
0x18002af93  and     r9b, r14b
0x18002af96  mov     [rsp+320h+var_2C8], r15b
0x18002af9b  mov     esi, eax
0x18002af9d  shr     esi, 15h
0x18002afa0  mov     r11d, eax
0x18002afa3  shr     r11d, 4
0x18002afa7  and     sil, r14b
0x18002afaa  mov     [rsp+320h+var_2D0], sil
0x18002afaf  and     r11b, r14b
0x18002afb2  mov     [rsp+320h+var_2D8], r11b
0x18002afb7  mov     [rsp+320h+var_2E0], r10b
0x18002afbc  shr     r8d, 0Dh
0x18002afc0  and     r8b, r14b
0x18002afc3  mov     byte ptr [rsp+320h+var_2E8], r9b
0x18002afc8  shr     edx, 11h
0x18002afcb  and     dl, r14b
0x18002afce  mov     byte ptr [rsp+320h+var_2F0], r8b
0x18002afd3  mov     byte ptr [rsp+320h+var_2F8], dl
0x18002afd7  jmp     loc_18002B08C
0x18002afdc  mov     esi, 0C0000017h
0x18002afe1  jmp     loc_18002B15B
0x18002afe6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002afed  lea     rax, WPP_GLOBAL_Control
0x18002aff4  cmp     rcx, rax
0x18002aff7  jz      short loc_18002B025
0x18002aff9  test    byte ptr [rcx+1Ch], 1
0x18002affd  jz      short loc_18002B025
0x18002afff  mov     rcx, [rcx+10h]
0x18002b003  lea     rax, [rbp+210h+applicationUserModelId]
0x18002b00a  mov     [rsp+320h+var_2F8], rax
0x18002b00f  mov     edx, 1Ah
0x18002b014  lea     rax, [rbp+210h+packageFullName]
0x18002b018  mov     r9d, esi
0x18002b01b  mov     [rsp+320h+var_300], rax
0x18002b020  call    WPP_SF_DSS
0x18002b025  test    rbx, rbx
0x18002b028  jz      loc_18002B15B
0x18002b02e  jmp     loc_18002B153
0x18002b033  lea     r11, [rbp+210h+applicationUserModelId]
0x18002b03a  shr     r10d, 4
0x18002b03e  mov     [rsp+320h+var_2B8], r11
0x18002b043  and     r10b, r14b
0x18002b046  shr     r9d, 14h
0x18002b04a  lea     r11, [rbp+210h+packageFullName]
0x18002b04e  mov     [rsp+320h+var_2C0], r11
0x18002b053  and     r9b, r14b
0x18002b056  mov     [rsp+320h+var_2C8], r15b
0x18002b05b  mov     ecx, eax
0x18002b05d  mov     [rsp+320h+var_2D0], r15b
0x18002b062  mov     [rsp+320h+var_2D8], r10b
0x18002b067  mov     [rsp+320h+var_2E0], r9b
0x18002b06c  shr     r8d, 13h
0x18002b070  shr     edx, 0Dh
0x18002b073  and     r8b, r14b
0x18002b076  and     dl, r14b
0x18002b079  mov     byte ptr [rsp+320h+var_2E8], r8b
0x18002b07e  shr     ecx, 11h
0x18002b081  and     cl, r14b
0x18002b084  mov     byte ptr [rsp+320h+var_2F0], dl
0x18002b088  mov     byte ptr [rsp+320h+var_2F8], cl
0x18002b08c  shr     eax, 0Fh
0x18002b08f  xor     r9d, r9d
0x18002b092  and     al, r14b
0x18002b095  xor     r8d, r8d
0x18002b098  mov     edx, r14d
0x18002b09b  mov     byte ptr [rsp+320h+var_300], al
0x18002b09f  mov     rcx, r13
0x18002b0a2  call    ?AdjustActivationToken@@YAJPEAXW4RuntimeBehavior@AppModel@@_N222222222PEBG3PEA_KPEAU_GUID@@3PEAPEAX@Z; AdjustActivationToken(void *,AppModel::RuntimeBehavior,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,ushort const *,ushort const *,unsigned __int64 *,_GUID *,ushort const *,void * *)
0x18002b0a7  mov     edi, eax
0x18002b0a9  test    eax, eax
0x18002b0ab  jz      short loc_18002B0EC
0x18002b0ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b0b4  lea     rax, WPP_GLOBAL_Control
0x18002b0bb  cmp     rcx, rax
0x18002b0be  jz      short loc_18002B0EC
0x18002b0c0  test    [rcx+1Ch], r14b
0x18002b0c4  jz      short loc_18002B0EC
0x18002b0c6  mov     rcx, [rcx+10h]
0x18002b0ca  lea     rax, [rbp+210h+applicationUserModelId]
0x18002b0d1  mov     [rsp+320h+var_2F8], rax
0x18002b0d6  mov     edx, 1Bh
0x18002b0db  lea     rax, [rbp+210h+packageFullName]
0x18002b0df  mov     r9d, edi
0x18002b0e2  mov     [rsp+320h+var_300], rax
0x18002b0e7  call    WPP_SF_DSS
0x18002b0ec  test    rbx, rbx
0x18002b0ef  jz      short loc_18002B0F9
0x18002b0f1  mov     rcx, rbx; Block
0x18002b0f4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002b0f9  lea     rcx, [rbp+210h+var_288]
0x18002b0fd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b102  mov     eax, edi
0x18002b104  jmp     loc_18002B1AB
0x18002b109  mov     esi, 0C0000017h
0x18002b10e  jmp     short loc_18002B153
0x18002b110  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
