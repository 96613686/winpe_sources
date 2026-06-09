# AdjustActivationTokenToMatch(void *,void *,ulong,void * *)

- ea: `0x1800295ec`
- end: `0x180029b86`
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
- `0x180026948`
- `0x1800271e0`
- `0x1800273f8`
- `0x180029110`
- `0x1800295ec`
- `0x180035db8`
- `0x18003944c`
- `0x180039828`
- `0x18003bfc4`
- `0x18003c394`
- `0x1800444ba`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18002970f`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18002970f`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18002964b`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18002964b`
- `ntdll!RtlQueryPackageClaims` at `0x180029746`
- `ntdll!RtlQueryPackageClaims` at `0x180029746`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180029863`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180029863`
- `ext-ms-win-desktopappx-l1-1-5!DoesPackageHaveUIAccessCapability` at `0x1800296aa`
- `ext-ms-win-desktopappx-l1-1-5!DoesPackageHaveUIAccessCapability` at `0x1800296aa`

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
        (void *)0x153A,
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
        (unsigned int)&WPP_063934a2c6ca383cf9bd298d4f16efdb_Traceguids,
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
          (unsigned int)&WPP_063934a2c6ca383cf9bd298d4f16efdb_Traceguids,
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
0x1800295ec  mov     [rsp-8+arg_10], rbx
0x1800295f1  push    rbp
0x1800295f2  push    rsi
0x1800295f3  push    rdi
0x1800295f4  push    r12
0x1800295f6  push    r13
0x1800295f8  push    r14
0x1800295fa  push    r15
0x1800295fc  lea     rbp, [rsp-1E0h]
0x180029604  sub     rsp, 2F0h
0x18002960b  mov     rax, cs:__security_cookie
0x180029612  xor     rax, rsp
0x180029615  mov     [rbp+210h+var_40], rax
0x18002961c  mov     r14, rdx
0x18002961f  mov     [rbp+210h+packageFullNameLength], 80h
0x180029626  mov     ebx, r8d
0x180029629  mov     [rbp+210h+applicationUserModelIdLength], 83h
0x180029630  mov     r13, rcx
0x180029633  lea     r8, [rbp+210h+packageFullName]; packageFullName
0x180029637  xor     r15d, r15d
0x18002963a  lea     rdx, [rbp+210h+packageFullNameLength]; packageFullNameLength
0x18002963e  mov     rcx, r14; token
0x180029641  mov     [rbp+210h+var_280], r15
0x180029645  mov     r12, r9
0x180029648  mov     [r9], r15
0x18002964b  call    cs:__imp_GetPackageFullNameFromToken
0x180029652  nop     dword ptr [rax+rax+00h]
0x180029657  cmp     eax, 3D54h
0x18002965c  jnz     short loc_180029665
0x18002965e  xor     eax, eax
0x180029660  jmp     loc_180029B5B
0x180029665  test    eax, eax
0x180029667  jz      short loc_18002967C
0x180029669  jle     loc_180029B5B
0x18002966f  movzx   eax, ax
0x180029672  or      eax, 0C0070000h
0x180029677  jmp     loc_180029B5B
0x18002967c  mov     esi, 1
0x180029681  test    bl, 4
0x180029684  jz      short loc_180029701
0x180029686  mov     dword ptr [rbp+210h+var_288], r15d
0x18002968a  mov     dl, sil
0x18002968d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CentennialUIAccess@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialUIAccess@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialUIAccess> `wil::Feature<__WilFeatureTraits_Feature_CentennialUIAccess>::GetImpl(void)'::`2'::impl
0x180029694  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialUIAccess@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialUIAccess>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180029699  call    IsDoesPackageHaveUIAccessCapabilityPresent
0x18002969e  test    al, al
0x1800296a0  jz      short loc_1800296D6
0x1800296a2  lea     rdx, [rbp+210h+var_288]
0x1800296a6  lea     rcx, [rbp+210h+packageFullName]
0x1800296aa  call    cs:__imp_DoesPackageHaveUIAccessCapability
0x1800296b1  nop     dword ptr [rax+rax+00h]
0x1800296b6  test    eax, eax
0x1800296b8  jns     short loc_1800296D0
0x1800296ba  mov     rcx, [rbp+218h]; this
0x1800296c1  mov     r9d, eax; char *
0x1800296c4  mov     edx, 153Ah; void *
0x1800296c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800296ce  jmp     short loc_1800296D6
0x1800296d0  cmp     dword ptr [rbp+210h+var_288], r15d
0x1800296d4  jnz     short loc_180029701
0x1800296d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800296dd  lea     rax, WPP_GLOBAL_Control
0x1800296e4  cmp     rcx, rax
0x1800296e7  jz      loc_180029B56
0x1800296ed  test    [rcx+1Ch], sil
0x1800296f1  jz      loc_180029B56
0x1800296f7  mov     edx, 16h
0x1800296fc  jmp     loc_180029B36
0x180029701  lea     r8, [rbp+210h+applicationUserModelId]; applicationUserModelId
0x180029708  mov     rcx, r14; token
0x18002970b  lea     rdx, [rbp+210h+applicationUserModelIdLength]; applicationUserModelIdLength
0x18002970f  call    cs:__imp_GetApplicationUserModelIdFromToken
0x180029716  nop     dword ptr [rax+rax+00h]
0x18002971b  test    eax, eax
0x18002971d  jnz     loc_180029669
0x180029723  mov     [rsp+320h+var_2E8], r15
0x180029728  lea     rax, [rbp+210h+var_280]
0x18002972c  mov     [rsp+320h+var_2F0], rax
0x180029731  xor     r9d, r9d
0x180029734  mov     [rsp+320h+var_2F8], r15
0x180029739  xor     r8d, r8d
0x18002973c  xor     edx, edx
0x18002973e  mov     [rsp+320h+var_300], r15
0x180029743  mov     rcx, r14
0x180029746  call    cs:__imp_RtlQueryPackageClaims
0x18002974d  nop     dword ptr [rax+rax+00h]
0x180029752  mov     ebx, eax
0x180029754  test    eax, eax
0x180029756  jz      short loc_18002979E
0x180029758  mov     rcx, cs:WPP_GLOBAL_Control
0x18002975f  lea     rax, WPP_GLOBAL_Control
0x180029766  cmp     rcx, rax
0x180029769  jz      short loc_180029797
0x18002976b  test    [rcx+1Ch], sil
0x18002976f  jz      short loc_180029797
0x180029771  mov     rcx, [rcx+10h]
0x180029775  lea     rax, [rbp+210h+applicationUserModelId]
0x18002977c  mov     [rsp+320h+var_2F8], rax
0x180029781  mov     edx, 17h
0x180029786  lea     rax, [rbp+210h+packageFullName]
0x18002978a  mov     r9d, ebx
0x18002978d  mov     [rsp+320h+var_300], rax
0x180029792  call    WPP_SF_DSS
0x180029797  mov     eax, ebx
0x180029799  jmp     loc_180029B5B
0x18002979e  test    byte ptr [rbp+210h+var_280], 4
0x1800297a2  jz      loc_180029B18
0x1800297a8  lea     rax, aWinSysappgroup; "WIN://SYSAPPGROUPID"
0x1800297af  mov     [rbp+210h+var_288], r15
0x1800297b3  mov     [rbp+210h+var_268], rax
0x1800297b7  mov     rdi, r15
0x1800297ba  lea     rax, [rbp+210h+Size]
0x1800297be  mov     [rbp+210h+var_270], 280026h
0x1800297c6  mov     [rsp+320h+var_2F8], rax
0x1800297cb  mov     rbx, r15
0x1800297ce  mov     dword ptr [rsp+320h+var_300], r15d
0x1800297d3  xor     r9d, r9d
0x1800297d6  mov     dword ptr [rbp+210h+Size], r15d
0x1800297da  mov     r8d, esi
0x1800297dd  jmp     short loc_18002985C
0x1800297df  cmp     esi, 0C0000225h
0x1800297e5  jz      loc_1800298E0
0x1800297eb  cmp     esi, 0C0000023h
0x1800297f1  jnz     loc_180029996
0x1800297f7  mov     r15d, dword ptr [rbp+210h+Size]
0x1800297fb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029802  mov     ecx, r15d; unsigned __int64
0x180029805  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002980a  mov     rsi, rax
0x18002980d  test    rax, rax
0x180029810  jz      short loc_180029824
0x180029812  mov     r8d, r15d; Size
0x180029815  xor     edx, edx; Val
0x180029817  mov     rcx, rax; void *
0x18002981a  call    memset_0
0x18002981f  xor     r15d, r15d
0x180029822  jmp     short loc_18002982A
0x180029824  xor     r15d, r15d
0x180029827  mov     esi, r15d
0x18002982a  mov     rcx, rbx; Block
0x18002982d  mov     rbx, rsi
0x180029830  test    rcx, rcx
0x180029833  jz      short loc_18002983A
0x180029835  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002983a  test    rsi, rsi
0x18002983d  jz      loc_18002998C
0x180029843  lea     rax, [rbp+210h+Size]
0x180029847  mov     r9, rsi
0x18002984a  mov     [rsp+320h+var_2F8], rax
0x18002984f  mov     r8d, 1
0x180029855  mov     eax, dword ptr [rbp+210h+Size]
0x180029858  mov     dword ptr [rsp+320h+var_300], eax
0x18002985c  lea     rdx, [rbp+210h+var_270]
0x180029860  mov     rcx, r14
0x180029863  call    cs:__imp_NtQuerySecurityAttributesToken
0x18002986a  nop     dword ptr [rax+rax+00h]
0x18002986f  mov     esi, eax
0x180029871  test    eax, eax
0x180029873  jnz     loc_1800297DF
0x180029879  cmp     [rbx+4], r15d
0x18002987d  jz      loc_180029AC0
0x180029883  mov     rax, [rbx+8]
0x180029887  test    rax, rax
0x18002988a  jz      loc_180029AC0
0x180029890  cmp     word ptr [rax+10h], 3
0x180029895  jnz     loc_180029AC0
0x18002989b  mov     rcx, [rax+20h]
0x18002989f  test    rcx, rcx
0x1800298a2  jz      loc_180029AC0
0x1800298a8  mov     eax, [rcx]
0x1800298aa  mov     rdx, [rcx+8]
0x1800298ae  lea     rcx, [rbp+210h+var_260]
0x1800298b2  movzx   r8d, ax
0x1800298b6  shr     r8, 1
0x1800298b9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800298be  mov     rdx, rax
0x1800298c1  lea     rcx, [rbp+210h+var_288]
0x1800298c5  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800298ca  lea     rcx, [rbp+210h+var_260]
0x1800298ce  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800298d3  mov     rdi, [rbp+210h+var_288]
0x1800298d7  test    rdi, rdi
0x1800298da  jz      loc_180029AB9
0x1800298e0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x1800298e7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x1800298ec  mov     [rsp+320h+var_298], r12
0x1800298f4  test    al, al
0x1800298f6  mov     rax, [rbp+210h+var_280]
0x1800298fa  mov     r14d, 1
0x180029900  mov     [rsp+320h+var_2A0], rdi
0x180029908  mov     r10d, eax
0x18002990b  mov     [rsp+320h+var_2A8], r15
0x180029910  mov     r9d, eax
0x180029913  mov     r8d, eax
0x180029916  mov     [rsp+320h+var_2B0], r15
0x18002991b  mov     edx, eax
0x18002991d  jz      loc_1800299E3
0x180029923  lea     rcx, [rbp+210h+applicationUserModelId]
0x18002992a  shr     r10d, 14h
0x18002992e  mov     [rsp+320h+var_2B8], rcx
0x180029933  and     r10b, r14b
0x180029936  shr     r9d, 13h
0x18002993a  lea     rcx, [rbp+210h+packageFullName]
0x18002993e  mov     [rsp+320h+var_2C0], rcx
0x180029943  and     r9b, r14b
0x180029946  mov     [rsp+320h+var_2C8], r15b
0x18002994b  mov     esi, eax
0x18002994d  shr     esi, 15h
0x180029950  mov     r11d, eax
0x180029953  shr     r11d, 4
0x180029957  and     sil, r14b
0x18002995a  mov     [rsp+320h+var_2D0], sil
0x18002995f  and     r11b, r14b
0x180029962  mov     [rsp+320h+var_2D8], r11b
0x180029967  mov     [rsp+320h+var_2E0], r10b
0x18002996c  shr     r8d, 0Dh
0x180029970  and     r8b, r14b
0x180029973  mov     byte ptr [rsp+320h+var_2E8], r9b
0x180029978  shr     edx, 11h
0x18002997b  and     dl, r14b
0x18002997e  mov     byte ptr [rsp+320h+var_2F0], r8b
0x180029983  mov     byte ptr [rsp+320h+var_2F8], dl
0x180029987  jmp     loc_180029A3C
0x18002998c  mov     esi, 0C0000017h
0x180029991  jmp     loc_180029B0B
0x180029996  mov     rcx, cs:WPP_GLOBAL_Control
0x18002999d  lea     rax, WPP_GLOBAL_Control
0x1800299a4  cmp     rcx, rax
0x1800299a7  jz      short loc_1800299D5
0x1800299a9  test    byte ptr [rcx+1Ch], 1
0x1800299ad  jz      short loc_1800299D5
0x1800299af  mov     rcx, [rcx+10h]
0x1800299b3  lea     rax, [rbp+210h+applicationUserModelId]
0x1800299ba  mov     [rsp+320h+var_2F8], rax
0x1800299bf  mov     edx, 1Ah
0x1800299c4  lea     rax, [rbp+210h+packageFullName]
0x1800299c8  mov     r9d, esi
0x1800299cb  mov     [rsp+320h+var_300], rax
0x1800299d0  call    WPP_SF_DSS
0x1800299d5  test    rbx, rbx
0x1800299d8  jz      loc_180029B0B
0x1800299de  jmp     loc_180029B03
0x1800299e3  lea     r11, [rbp+210h+applicationUserModelId]
0x1800299ea  shr     r10d, 4
0x1800299ee  mov     [rsp+320h+var_2B8], r11
0x1800299f3  and     r10b, r14b
0x1800299f6  shr     r9d, 14h
0x1800299fa  lea     r11, [rbp+210h+packageFullName]
0x1800299fe  mov     [rsp+320h+var_2C0], r11
0x180029a03  and     r9b, r14b
0x180029a06  mov     [rsp+320h+var_2C8], r15b
0x180029a0b  mov     ecx, eax
0x180029a0d  mov     [rsp+320h+var_2D0], r15b
0x180029a12  mov     [rsp+320h+var_2D8], r10b
0x180029a17  mov     [rsp+320h+var_2E0], r9b
0x180029a1c  shr     r8d, 13h
0x180029a20  shr     edx, 0Dh
0x180029a23  and     r8b, r14b
0x180029a26  and     dl, r14b
0x180029a29  mov     byte ptr [rsp+320h+var_2E8], r8b
0x180029a2e  shr     ecx, 11h
0x180029a31  and     cl, r14b
0x180029a34  mov     byte ptr [rsp+320h+var_2F0], dl
0x180029a38  mov     byte ptr [rsp+320h+var_2F8], cl
0x180029a3c  shr     eax, 0Fh
0x180029a3f  xor     r9d, r9d
0x180029a42  and     al, r14b
0x180029a45  xor     r8d, r8d
0x180029a48  mov     edx, r14d
0x180029a4b  mov     byte ptr [rsp+320h+var_300], al
0x180029a4f  mov     rcx, r13
0x180029a52  call    ?AdjustActivationToken@@YAJPEAXW4RuntimeBehavior@AppModel@@_N222222222PEBG3PEA_KPEAU_GUID@@3PEAPEAX@Z; AdjustActivationToken(void *,AppModel::RuntimeBehavior,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,ushort const *,ushort const *,unsigned __int64 *,_GUID *,ushort const *,void * *)
0x180029a57  mov     edi, eax
0x180029a59  test    eax, eax
0x180029a5b  jz      short loc_180029A9C
0x180029a5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a64  lea     rax, WPP_GLOBAL_Control
0x180029a6b  cmp     rcx, rax
0x180029a6e  jz      short loc_180029A9C
0x180029a70  test    [rcx+1Ch], r14b
0x180029a74  jz      short loc_180029A9C
0x180029a76  mov     rcx, [rcx+10h]
0x180029a7a  lea     rax, [rbp+210h+applicationUserModelId]
0x180029a81  mov     [rsp+320h+var_2F8], rax
0x180029a86  mov     edx, 1Bh
0x180029a8b  lea     rax, [rbp+210h+packageFullName]
0x180029a8f  mov     r9d, edi
0x180029a92  mov     [rsp+320h+var_300], rax
0x180029a97  call    WPP_SF_DSS
0x180029a9c  test    rbx, rbx
0x180029a9f  jz      short loc_180029AA9
0x180029aa1  mov     rcx, rbx; Block
0x180029aa4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029aa9  lea     rcx, [rbp+210h+var_288]
0x180029aad  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029ab2  mov     eax, edi
0x180029ab4  jmp     loc_180029B5B
0x180029ab9  mov     esi, 0C0000017h
0x180029abe  jmp     short loc_180029B03
0x180029ac0  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
