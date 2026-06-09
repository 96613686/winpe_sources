# AdjustActivationTokenToMatch(void *,void *,ulong,void * *)

- ea: `0x1800296bc`
- end: `0x180029c56`
- name: `?AdjustActivationTokenToMatch@@YAJPEAX0KPEAPEAX@Z`
- size: `1434`
- prototype: `int(void *, void *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019704`

## callees

- `0x18001b494`
- `0x18001bc9c`
- `0x18001c488`
- `0x180026a18`
- `0x1800272b0`
- `0x1800274c8`
- `0x1800291e0`
- `0x1800296bc`
- `0x180036100`
- `0x18003978c`
- `0x180039ba4`
- `0x18003c504`
- `0x18003c8d4`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800297df`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800297df`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18002971b`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18002971b`
- `ntdll!RtlQueryPackageClaims` at `0x180029816`
- `ntdll!RtlQueryPackageClaims` at `0x180029816`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180029933`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180029933`
- `ext-ms-win-desktopappx-l1-1-5!DoesPackageHaveUIAccessCapability` at `0x18002977a`
- `ext-ms-win-desktopappx-l1-1-5!DoesPackageHaveUIAccessCapability` at `0x18002977a`

## pseudocode

```c
LONG __fastcall AdjustActivationTokenToMatch(void *a1, void *a2, char a3, void **a4)
{
  LONG result; // eax
  __int64 v8; // rdx
  bool v9; // cc
  int HaveUIAccessCapability; // eax
  unsigned int v11; // r8d
  _QWORD *v12; // rcx
  int v13; // edx
  int v14; // ebx
  int v15; // r8d
  void *v16; // rbx
  int i; // eax
  int v18; // r8d
  unsigned int v19; // r15d
  void *v20; // rax
  void *v21; // rsi
  void *v22; // rcx
  int v23; // esi
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // edi
  int v28; // r8d
  int v29; // [rsp+20h] [rbp-F0h]
  size_t Size; // [rsp+90h] [rbp-80h] BYREF
  __int64 v31; // [rsp+98h] [rbp-78h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-70h] BYREF
  UINT32 packageFullNameLength; // [rsp+A8h] [rbp-68h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+ACh] [rbp-64h] BYREF
  _QWORD v35[2]; // [rsp+B0h] [rbp-60h] BYREF
  _BYTE v36[16]; // [rsp+C0h] [rbp-50h] BYREF
  WCHAR packageFullName[128]; // [rsp+D0h] [rbp-40h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+1D0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+218h]

  packageFullNameLength = 128;
  applicationUserModelIdLength = 131;
  v32 = 0;
  *a4 = 0;
  result = GetPackageFullNameFromToken(a2, &packageFullNameLength, packageFullName);
  if ( result == 15700 )
    return 0;
  v9 = result <= 0;
  if ( result )
    goto LABEL_4;
  if ( (a3 & 4) != 0 )
  {
    LODWORD(v31) = 0;
    LOBYTE(v8) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialUIAccess>::ReportUsage(
      &`wil::Feature<__WilFeatureTraits_Feature_CentennialUIAccess>::GetImpl'::`2'::impl,
      v8);
    if ( !(unsigned __int8)IsDoesPackageHaveUIAccessCapabilityPresent() )
      goto LABEL_11;
    HaveUIAccessCapability = DoesPackageHaveUIAccessCapability(packageFullName, &v31);
    if ( HaveUIAccessCapability < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1571,
        v11,
        (const char *)(unsigned int)HaveUIAccessCapability,
        v29);
      goto LABEL_11;
    }
    if ( !(_DWORD)v31 )
    {
LABEL_11:
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return -1073741637;
      v13 = 22;
LABEL_61:
      WPP_SF_SS(
        v12[2],
        v13,
        (unsigned int)&WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids,
        (unsigned int)packageFullName,
        (__int64)applicationUserModelId);
      return -1073741637;
    }
  }
  result = GetApplicationUserModelIdFromToken(a2, &applicationUserModelIdLength, applicationUserModelId);
  v9 = result <= 0;
  if ( result )
  {
LABEL_4:
    if ( !v9 )
      return (unsigned __int16)result | 0xC0070000;
    return result;
  }
  v14 = RtlQueryPackageClaims(a2, 0, 0, 0, 0, 0, &v32, 0);
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DSS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        v15,
        v14,
        (__int64)packageFullName,
        (__int64)applicationUserModelId);
    return v14;
  }
  else
  {
    if ( (v32 & 4) == 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return -1073741637;
      v13 = 24;
      goto LABEL_61;
    }
    v31 = 0;
    v35[1] = L"WIN://SYSAPPGROUPID";
    v35[0] = 2621478;
    v16 = 0;
    LODWORD(Size) = 0;
    for ( i = NtQuerySecurityAttributesToken(a2, v35, 1, 0, 0, &Size);
          ;
          i = NtQuerySecurityAttributesToken(a2, v35, 1, v21, Size, &Size) )
    {
      v23 = i;
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
            v18,
            i,
            (__int64)packageFullName,
            (__int64)applicationUserModelId);
        if ( v16 )
LABEL_56:
          operator delete(v16);
LABEL_57:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
        return v23;
      }
      v19 = Size;
      v20 = operator new[]((unsigned int)Size, (const struct std::nothrow_t *)&std::nothrow);
      v21 = v20;
      if ( v20 )
        memset_0(v20, 0, v19);
      else
        v21 = 0;
      v22 = v16;
      v16 = v21;
      if ( v22 )
        operator delete(v22);
      if ( !v21 )
      {
        v23 = -1073741801;
        goto LABEL_57;
      }
    }
    if ( !*((_DWORD *)v16 + 1)
      || (v24 = *((_QWORD *)v16 + 1)) == 0
      || *(_WORD *)(v24 + 16) != 3
      || (v25 = *(_QWORD *)(v24 + 32)) == 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          (unsigned int)&WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids,
          (unsigned int)packageFullName,
          (__int64)applicationUserModelId);
      v23 = -1073741811;
      goto LABEL_56;
    }
    v26 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            v36,
            *(_QWORD *)(v25 + 8),
            (unsigned __int64)(unsigned __int16)*(_DWORD *)v25 >> 1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v31,
      v26);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v36);
    if ( !v31 )
    {
      v23 = -1073741801;
      goto LABEL_56;
    }
LABEL_37:
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl'::`2'::impl);
    v27 = AdjustActivationToken(a1, 1, 0, 0);
    if ( v27 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DSS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        v28,
        v27,
        (__int64)packageFullName,
        (__int64)applicationUserModelId);
    if ( v16 )
      operator delete(v16);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
    return v27;
  }
}

```

## disassembly

```asm
0x1800296bc  mov     [rsp-8+arg_10], rbx
0x1800296c1  push    rbp
0x1800296c2  push    rsi
0x1800296c3  push    rdi
0x1800296c4  push    r12
0x1800296c6  push    r13
0x1800296c8  push    r14
0x1800296ca  push    r15
0x1800296cc  lea     rbp, [rsp-1E0h]
0x1800296d4  sub     rsp, 2F0h
0x1800296db  mov     rax, cs:__security_cookie
0x1800296e2  xor     rax, rsp
0x1800296e5  mov     [rbp+210h+var_40], rax
0x1800296ec  mov     r14, rdx
0x1800296ef  mov     [rbp+210h+packageFullNameLength], 80h
0x1800296f6  mov     ebx, r8d
0x1800296f9  mov     [rbp+210h+applicationUserModelIdLength], 83h
0x180029700  mov     r13, rcx
0x180029703  lea     r8, [rbp+210h+packageFullName]; packageFullName
0x180029707  xor     r15d, r15d
0x18002970a  lea     rdx, [rbp+210h+packageFullNameLength]; packageFullNameLength
0x18002970e  mov     rcx, r14; token
0x180029711  mov     [rbp+210h+var_280], r15
0x180029715  mov     r12, r9
0x180029718  mov     [r9], r15
0x18002971b  call    cs:__imp_GetPackageFullNameFromToken
0x180029722  nop     dword ptr [rax+rax+00h]
0x180029727  cmp     eax, 3D54h
0x18002972c  jnz     short loc_180029735
0x18002972e  xor     eax, eax
0x180029730  jmp     loc_180029C2B
0x180029735  test    eax, eax
0x180029737  jz      short loc_18002974C
0x180029739  jle     loc_180029C2B
0x18002973f  movzx   eax, ax
0x180029742  or      eax, 0C0070000h
0x180029747  jmp     loc_180029C2B
0x18002974c  mov     esi, 1
0x180029751  test    bl, 4
0x180029754  jz      short loc_1800297D1
0x180029756  mov     dword ptr [rbp+210h+var_288], r15d
0x18002975a  mov     dl, sil
0x18002975d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CentennialUIAccess@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialUIAccess@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialUIAccess> `wil::Feature<__WilFeatureTraits_Feature_CentennialUIAccess>::GetImpl(void)'::`2'::impl
0x180029764  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialUIAccess@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialUIAccess>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180029769  call    IsDoesPackageHaveUIAccessCapabilityPresent
0x18002976e  test    al, al
0x180029770  jz      short loc_1800297A6
0x180029772  lea     rdx, [rbp+210h+var_288]
0x180029776  lea     rcx, [rbp+210h+packageFullName]
0x18002977a  call    cs:__imp_DoesPackageHaveUIAccessCapability
0x180029781  nop     dword ptr [rax+rax+00h]
0x180029786  test    eax, eax
0x180029788  jns     short loc_1800297A0
0x18002978a  mov     rcx, [rbp+218h]; this
0x180029791  mov     r9d, eax; char *
0x180029794  mov     edx, 1571h; void *
0x180029799  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002979e  jmp     short loc_1800297A6
0x1800297a0  cmp     dword ptr [rbp+210h+var_288], r15d
0x1800297a4  jnz     short loc_1800297D1
0x1800297a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297ad  lea     rax, WPP_GLOBAL_Control
0x1800297b4  cmp     rcx, rax
0x1800297b7  jz      loc_180029C26
0x1800297bd  test    [rcx+1Ch], sil
0x1800297c1  jz      loc_180029C26
0x1800297c7  mov     edx, 16h
0x1800297cc  jmp     loc_180029C06
0x1800297d1  lea     r8, [rbp+210h+applicationUserModelId]; applicationUserModelId
0x1800297d8  mov     rcx, r14; token
0x1800297db  lea     rdx, [rbp+210h+applicationUserModelIdLength]; applicationUserModelIdLength
0x1800297df  call    cs:__imp_GetApplicationUserModelIdFromToken
0x1800297e6  nop     dword ptr [rax+rax+00h]
0x1800297eb  test    eax, eax
0x1800297ed  jnz     loc_180029739
0x1800297f3  mov     [rsp+320h+var_2E8], r15
0x1800297f8  lea     rax, [rbp+210h+var_280]
0x1800297fc  mov     [rsp+320h+var_2F0], rax
0x180029801  xor     r9d, r9d
0x180029804  mov     [rsp+320h+var_2F8], r15
0x180029809  xor     r8d, r8d
0x18002980c  xor     edx, edx
0x18002980e  mov     [rsp+320h+var_300], r15
0x180029813  mov     rcx, r14
0x180029816  call    cs:__imp_RtlQueryPackageClaims
0x18002981d  nop     dword ptr [rax+rax+00h]
0x180029822  mov     ebx, eax
0x180029824  test    eax, eax
0x180029826  jz      short loc_18002986E
0x180029828  mov     rcx, cs:WPP_GLOBAL_Control
0x18002982f  lea     rax, WPP_GLOBAL_Control
0x180029836  cmp     rcx, rax
0x180029839  jz      short loc_180029867
0x18002983b  test    [rcx+1Ch], sil
0x18002983f  jz      short loc_180029867
0x180029841  mov     rcx, [rcx+10h]
0x180029845  lea     rax, [rbp+210h+applicationUserModelId]
0x18002984c  mov     [rsp+320h+var_2F8], rax
0x180029851  mov     edx, 17h
0x180029856  lea     rax, [rbp+210h+packageFullName]
0x18002985a  mov     r9d, ebx
0x18002985d  mov     [rsp+320h+var_300], rax
0x180029862  call    WPP_SF_DSS
0x180029867  mov     eax, ebx
0x180029869  jmp     loc_180029C2B
0x18002986e  test    byte ptr [rbp+210h+var_280], 4
0x180029872  jz      loc_180029BE8
0x180029878  lea     rax, aWinSysappgroup; "WIN://SYSAPPGROUPID"
0x18002987f  mov     [rbp+210h+var_288], r15
0x180029883  mov     [rbp+210h+var_268], rax
0x180029887  mov     rdi, r15
0x18002988a  lea     rax, [rbp+210h+Size]
0x18002988e  mov     [rbp+210h+var_270], 280026h
0x180029896  mov     [rsp+320h+var_2F8], rax
0x18002989b  mov     rbx, r15
0x18002989e  mov     dword ptr [rsp+320h+var_300], r15d
0x1800298a3  xor     r9d, r9d
0x1800298a6  mov     dword ptr [rbp+210h+Size], r15d
0x1800298aa  mov     r8d, esi
0x1800298ad  jmp     short loc_18002992C
0x1800298af  cmp     esi, 0C0000225h
0x1800298b5  jz      loc_1800299B0
0x1800298bb  cmp     esi, 0C0000023h
0x1800298c1  jnz     loc_180029A66
0x1800298c7  mov     r15d, dword ptr [rbp+210h+Size]
0x1800298cb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800298d2  mov     ecx, r15d; unsigned __int64
0x1800298d5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800298da  mov     rsi, rax
0x1800298dd  test    rax, rax
0x1800298e0  jz      short loc_1800298F4
0x1800298e2  mov     r8d, r15d; Size
0x1800298e5  xor     edx, edx; Val
0x1800298e7  mov     rcx, rax; void *
0x1800298ea  call    memset_0
0x1800298ef  xor     r15d, r15d
0x1800298f2  jmp     short loc_1800298FA
0x1800298f4  xor     r15d, r15d
0x1800298f7  mov     esi, r15d
0x1800298fa  mov     rcx, rbx; Block
0x1800298fd  mov     rbx, rsi
0x180029900  test    rcx, rcx
0x180029903  jz      short loc_18002990A
0x180029905  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002990a  test    rsi, rsi
0x18002990d  jz      loc_180029A5C
0x180029913  lea     rax, [rbp+210h+Size]
0x180029917  mov     r9, rsi
0x18002991a  mov     [rsp+320h+var_2F8], rax
0x18002991f  mov     r8d, 1
0x180029925  mov     eax, dword ptr [rbp+210h+Size]
0x180029928  mov     dword ptr [rsp+320h+var_300], eax
0x18002992c  lea     rdx, [rbp+210h+var_270]
0x180029930  mov     rcx, r14
0x180029933  call    cs:__imp_NtQuerySecurityAttributesToken
0x18002993a  nop     dword ptr [rax+rax+00h]
0x18002993f  mov     esi, eax
0x180029941  test    eax, eax
0x180029943  jnz     loc_1800298AF
0x180029949  cmp     [rbx+4], r15d
0x18002994d  jz      loc_180029B90
0x180029953  mov     rax, [rbx+8]
0x180029957  test    rax, rax
0x18002995a  jz      loc_180029B90
0x180029960  cmp     word ptr [rax+10h], 3
0x180029965  jnz     loc_180029B90
0x18002996b  mov     rcx, [rax+20h]
0x18002996f  test    rcx, rcx
0x180029972  jz      loc_180029B90
0x180029978  mov     eax, [rcx]
0x18002997a  mov     rdx, [rcx+8]
0x18002997e  lea     rcx, [rbp+210h+var_260]
0x180029982  movzx   r8d, ax
0x180029986  shr     r8, 1
0x180029989  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002998e  mov     rdx, rax
0x180029991  lea     rcx, [rbp+210h+var_288]
0x180029995  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002999a  lea     rcx, [rbp+210h+var_260]
0x18002999e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800299a3  mov     rdi, [rbp+210h+var_288]
0x1800299a7  test    rdi, rdi
0x1800299aa  jz      loc_180029B89
0x1800299b0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x1800299b7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x1800299bc  mov     [rsp+320h+var_298], r12
0x1800299c4  test    al, al
0x1800299c6  mov     rax, [rbp+210h+var_280]
0x1800299ca  mov     r14d, 1
0x1800299d0  mov     [rsp+320h+var_2A0], rdi
0x1800299d8  mov     r10d, eax
0x1800299db  mov     [rsp+320h+var_2A8], r15
0x1800299e0  mov     r9d, eax
0x1800299e3  mov     r8d, eax
0x1800299e6  mov     [rsp+320h+var_2B0], r15
0x1800299eb  mov     edx, eax
0x1800299ed  jz      loc_180029AB3
0x1800299f3  lea     rcx, [rbp+210h+applicationUserModelId]
0x1800299fa  shr     r10d, 14h
0x1800299fe  mov     [rsp+320h+var_2B8], rcx
0x180029a03  and     r10b, r14b
0x180029a06  shr     r9d, 13h
0x180029a0a  lea     rcx, [rbp+210h+packageFullName]
0x180029a0e  mov     [rsp+320h+var_2C0], rcx
0x180029a13  and     r9b, r14b
0x180029a16  mov     [rsp+320h+var_2C8], r15b
0x180029a1b  mov     esi, eax
0x180029a1d  shr     esi, 15h
0x180029a20  mov     r11d, eax
0x180029a23  shr     r11d, 4
0x180029a27  and     sil, r14b
0x180029a2a  mov     [rsp+320h+var_2D0], sil
0x180029a2f  and     r11b, r14b
0x180029a32  mov     [rsp+320h+var_2D8], r11b
0x180029a37  mov     [rsp+320h+var_2E0], r10b
0x180029a3c  shr     r8d, 0Dh
0x180029a40  and     r8b, r14b
0x180029a43  mov     byte ptr [rsp+320h+var_2E8], r9b
0x180029a48  shr     edx, 11h
0x180029a4b  and     dl, r14b
0x180029a4e  mov     byte ptr [rsp+320h+var_2F0], r8b
0x180029a53  mov     byte ptr [rsp+320h+var_2F8], dl
0x180029a57  jmp     loc_180029B0C
0x180029a5c  mov     esi, 0C0000017h
0x180029a61  jmp     loc_180029BDB
0x180029a66  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a6d  lea     rax, WPP_GLOBAL_Control
0x180029a74  cmp     rcx, rax
0x180029a77  jz      short loc_180029AA5
0x180029a79  test    byte ptr [rcx+1Ch], 1
0x180029a7d  jz      short loc_180029AA5
0x180029a7f  mov     rcx, [rcx+10h]
0x180029a83  lea     rax, [rbp+210h+applicationUserModelId]
0x180029a8a  mov     [rsp+320h+var_2F8], rax
0x180029a8f  mov     edx, 1Ah
0x180029a94  lea     rax, [rbp+210h+packageFullName]
0x180029a98  mov     r9d, esi
0x180029a9b  mov     [rsp+320h+var_300], rax
0x180029aa0  call    WPP_SF_DSS
0x180029aa5  test    rbx, rbx
0x180029aa8  jz      loc_180029BDB
0x180029aae  jmp     loc_180029BD3
0x180029ab3  lea     r11, [rbp+210h+applicationUserModelId]
0x180029aba  shr     r10d, 4
0x180029abe  mov     [rsp+320h+var_2B8], r11
0x180029ac3  and     r10b, r14b
0x180029ac6  shr     r9d, 14h
0x180029aca  lea     r11, [rbp+210h+packageFullName]
0x180029ace  mov     [rsp+320h+var_2C0], r11
0x180029ad3  and     r9b, r14b
0x180029ad6  mov     [rsp+320h+var_2C8], r15b
0x180029adb  mov     ecx, eax
0x180029add  mov     [rsp+320h+var_2D0], r15b
0x180029ae2  mov     [rsp+320h+var_2D8], r10b
0x180029ae7  mov     [rsp+320h+var_2E0], r9b
0x180029aec  shr     r8d, 13h
0x180029af0  shr     edx, 0Dh
0x180029af3  and     r8b, r14b
0x180029af6  and     dl, r14b
0x180029af9  mov     byte ptr [rsp+320h+var_2E8], r8b
0x180029afe  shr     ecx, 11h
0x180029b01  and     cl, r14b
0x180029b04  mov     byte ptr [rsp+320h+var_2F0], dl
0x180029b08  mov     byte ptr [rsp+320h+var_2F8], cl
0x180029b0c  shr     eax, 0Fh
0x180029b0f  xor     r9d, r9d
0x180029b12  and     al, r14b
0x180029b15  xor     r8d, r8d
0x180029b18  mov     edx, r14d
0x180029b1b  mov     byte ptr [rsp+320h+var_300], al
0x180029b1f  mov     rcx, r13
0x180029b22  call    ?AdjustActivationToken@@YAJPEAXW4RuntimeBehavior@AppModel@@_N222222222PEBG3PEA_KPEAU_GUID@@3PEAPEAX@Z; AdjustActivationToken(void *,AppModel::RuntimeBehavior,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,ushort const *,ushort const *,unsigned __int64 *,_GUID *,ushort const *,void * *)
0x180029b27  mov     edi, eax
0x180029b29  test    eax, eax
0x180029b2b  jz      short loc_180029B6C
0x180029b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029b34  lea     rax, WPP_GLOBAL_Control
0x180029b3b  cmp     rcx, rax
0x180029b3e  jz      short loc_180029B6C
0x180029b40  test    [rcx+1Ch], r14b
0x180029b44  jz      short loc_180029B6C
0x180029b46  mov     rcx, [rcx+10h]
0x180029b4a  lea     rax, [rbp+210h+applicationUserModelId]
0x180029b51  mov     [rsp+320h+var_2F8], rax
0x180029b56  mov     edx, 1Bh
0x180029b5b  lea     rax, [rbp+210h+packageFullName]
0x180029b5f  mov     r9d, edi
0x180029b62  mov     [rsp+320h+var_300], rax
0x180029b67  call    WPP_SF_DSS
0x180029b6c  test    rbx, rbx
0x180029b6f  jz      short loc_180029B79
0x180029b71  mov     rcx, rbx; Block
0x180029b74  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029b79  lea     rcx, [rbp+210h+var_288]
0x180029b7d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029b82  mov     eax, edi
0x180029b84  jmp     loc_180029C2B
0x180029b89  mov     esi, 0C0000017h
0x180029b8e  jmp     short loc_180029BD3
0x180029b90  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
