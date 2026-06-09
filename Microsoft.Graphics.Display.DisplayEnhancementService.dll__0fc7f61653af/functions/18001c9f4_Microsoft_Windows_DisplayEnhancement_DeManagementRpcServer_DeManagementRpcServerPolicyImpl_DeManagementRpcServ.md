# Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerPolicyImpl::DeManagementRpcServerPolicyImpl(void)

- ea: `0x18001c9f4`
- end: `0x18001cbd0`
- name: `??0DeManagementRpcServerPolicyImpl@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@QEAA@XZ`
- size: `476`
- prototype: `Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerPolicyImpl *__fastcall(Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerPolicyImpl *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180011b04`

## callees

- `0x180005860`
- `0x180009014`
- `0x18000f9f0`
- `0x180013138`
- `0x180019ff4`
- `0x18001c9f4`
- `0x18001cbd8`

## import_xrefs

- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18001ca5a`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18001ca5a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001cb5f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001cb5f`

## string_xrefs

- `0x18001ca92`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserverpolicy.cpp`
- `0x18001cb98`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserverpolicy.cpp`
- `0x18001cbbe`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserverpolicy.cpp`
- `0x18001ca86`: `Failed to find the DEM transient object security descriptor, falling back to default low box SD`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerPolicyImpl *__fastcall Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerPolicyImpl::DeManagementRpcServerPolicyImpl(
        Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerPolicyImpl *this)
{
  char *v2; // rsi
  int v3; // ebx
  WCHAR *v4; // rax
  const wchar_t *v5; // rcx
  __int64 v6; // rdx
  const char *v7; // r9
  unsigned int v9; // eax
  int v10; // [rsp+20h] [rbp-E0h]
  const char *v11; // [rsp+28h] [rbp-D8h]
  char *v12; // [rsp+30h] [rbp-D0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  char v14; // [rsp+40h] [rbp-C0h]
  Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerPolicyImpl *v15; // [rsp+48h] [rbp-B8h]
  WCHAR StringSecurityDescriptor[184]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v15 = this;
  *(_QWORD *)this = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerPolicyImpl::`vftable';
  v2 = (char *)this + 8;
  *((_QWORD *)this + 1) = 0;
  v12 = (char *)this + 8;
  SecurityDescriptor = 0;
  v14 = 1;
  v3 = QueryTransientObjectSecurityDescriptor(9, L"DeManagementRPC\\Interface", &SecurityDescriptor) | 0x10000000;
  __1__out_param_t_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___details_wil__QEAA_XZ(&v12);
  if ( v3 == -805306316 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementr"
                    "pcserverpolicy.cpp",
      (const char *)0xD0000034LL,
      (int)"Failed to find the DEM transient object security descriptor, falling back to default low box SD",
      v11);
    v4 = StringSecurityDescriptor;
    v5 = L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1024-1502825166-1963708"
          "345-2616377461-2562897074-4192028372-3968301570-1997628692-1435953622)";
    v6 = 2;
    do
    {
      *(_OWORD *)v4 = *(_OWORD *)v5;
      *((_OWORD *)v4 + 1) = *((_OWORD *)v5 + 1);
      *((_OWORD *)v4 + 2) = *((_OWORD *)v5 + 2);
      *((_OWORD *)v4 + 3) = *((_OWORD *)v5 + 3);
      *((_OWORD *)v4 + 4) = *((_OWORD *)v5 + 4);
      *((_OWORD *)v4 + 5) = *((_OWORD *)v5 + 5);
      *((_OWORD *)v4 + 6) = *((_OWORD *)v5 + 6);
      *((_OWORD *)v4 + 7) = *((_OWORD *)v5 + 7);
      v4 += 64;
      v5 += 64;
      --v6;
    }
    while ( v6 );
    *(_OWORD *)v4 = *(_OWORD *)v5;
    *((_OWORD *)v4 + 1) = *((_OWORD *)v5 + 1);
    *((_OWORD *)v4 + 2) = *((_OWORD *)v5 + 2);
    *((_OWORD *)v4 + 3) = *((_OWORD *)v5 + 3);
    *((_OWORD *)v4 + 4) = *((_OWORD *)v5 + 4);
    *((_OWORD *)v4 + 5) = *((_OWORD *)v5 + 5);
    *(_OWORD *)(v4 + 46) = *(_OWORD *)(v5 + 46);
    v12 = v2;
    SecurityDescriptor = 0;
    v14 = 1;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagemen"
                      "trpcserverpolicy.cpp",
        v7);
    __1__out_param_t_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___details_wil__QEAA_XZ(&v12);
  }
  else if ( v3 < 0 )
  {
    v9 = wil::verify_hresult<long>((unsigned int)v3);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementr"
                    "pcserverpolicy.cpp",
      (const char *)v9,
      v10);
  }
  return this;
}

```

## disassembly

```asm
0x18001c9f4  push    rbp
0x18001c9f6  push    rbx
0x18001c9f7  push    rsi
0x18001c9f8  push    rdi
0x18001c9f9  lea     rbp, [rsp-0D8h]
0x18001ca01  sub     rsp, 1D8h
0x18001ca08  mov     rax, cs:__security_cookie
0x18001ca0f  xor     rax, rsp
0x18001ca12  mov     [rbp+0F0h+var_30], rax
0x18001ca19  mov     rdi, rcx
0x18001ca1c  mov     [rsp+1F0h+var_1A8], rcx
0x18001ca21  lea     rax, ??_7DeManagementRpcServerPolicyImpl@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerPolicyImpl::`vftable'
0x18001ca28  mov     [rcx], rax
0x18001ca2b  lea     rsi, [rcx+8]
0x18001ca2f  mov     qword ptr [rsi], 0
0x18001ca36  mov     [rsp+1F0h+var_1C0], rsi
0x18001ca3b  mov     [rsp+1F0h+SecurityDescriptor], 0
0x18001ca44  mov     [rsp+1F0h+var_1B0], 1
0x18001ca49  lea     r8, [rsp+1F0h+SecurityDescriptor]
0x18001ca4e  lea     rdx, aDemanagementrp; "DeManagementRPC\\Interface"
0x18001ca55  mov     ecx, 9
0x18001ca5a  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x18001ca60  mov     ebx, eax
0x18001ca62  bts     ebx, 1Ch
0x18001ca66  lea     rcx, [rsp+1F0h+var_1C0]
0x18001ca6b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x18001ca70  mov     r9d, 0D0000034h; char *
0x18001ca76  cmp     ebx, r9d
0x18001ca79  jnz     loc_18001CB92
0x18001ca7f  mov     rcx, [rbp+0F8h]; this
0x18001ca86  lea     rax, aFailedToFindTh; "Failed to find the DEM transient object"...
0x18001ca8d  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x18001ca92  lea     r8, aOnecoreuapDriv_30; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18001ca99  mov     edx, 16h; void *
0x18001ca9e  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001caa3  lea     rax, [rsp+1F0h+StringSecurityDescriptor]
0x18001caa8  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18001caaf  mov     edx, 2
0x18001cab4  lea     r8d, [rdx+7Eh]
0x18001cab8  movups  xmm0, xmmword ptr [rcx]
0x18001cabb  movups  xmmword ptr [rax], xmm0
0x18001cabe  movups  xmm1, xmmword ptr [rcx+10h]
0x18001cac2  movups  xmmword ptr [rax+10h], xmm1
0x18001cac6  movups  xmm0, xmmword ptr [rcx+20h]
0x18001caca  movups  xmmword ptr [rax+20h], xmm0
0x18001cace  movups  xmm1, xmmword ptr [rcx+30h]
0x18001cad2  movups  xmmword ptr [rax+30h], xmm1
0x18001cad6  movups  xmm0, xmmword ptr [rcx+40h]
0x18001cada  movups  xmmword ptr [rax+40h], xmm0
0x18001cade  movups  xmm1, xmmword ptr [rcx+50h]
0x18001cae2  movups  xmmword ptr [rax+50h], xmm1
0x18001cae6  movups  xmm0, xmmword ptr [rcx+60h]
0x18001caea  movups  xmmword ptr [rax+60h], xmm0
0x18001caee  movups  xmm1, xmmword ptr [rcx+70h]
0x18001caf2  movups  xmmword ptr [rax+70h], xmm1
0x18001caf6  add     rax, r8
0x18001caf9  add     rcx, r8
0x18001cafc  sub     rdx, 1
0x18001cb00  jnz     short loc_18001CAB8
0x18001cb02  movups  xmm0, xmmword ptr [rcx]
0x18001cb05  movups  xmmword ptr [rax], xmm0
0x18001cb08  movups  xmm1, xmmword ptr [rcx+10h]
0x18001cb0c  movups  xmmword ptr [rax+10h], xmm1
0x18001cb10  movups  xmm0, xmmword ptr [rcx+20h]
0x18001cb14  movups  xmmword ptr [rax+20h], xmm0
0x18001cb18  movups  xmm1, xmmword ptr [rcx+30h]
0x18001cb1c  movups  xmmword ptr [rax+30h], xmm1
0x18001cb20  movups  xmm0, xmmword ptr [rcx+40h]
0x18001cb24  movups  xmmword ptr [rax+40h], xmm0
0x18001cb28  movups  xmm1, xmmword ptr [rcx+50h]
0x18001cb2c  movups  xmmword ptr [rax+50h], xmm1
0x18001cb30  movups  xmm0, xmmword ptr [rcx+5Ch]
0x18001cb34  movups  xmmword ptr [rax+5Ch], xmm0
0x18001cb38  mov     [rsp+1F0h+var_1C0], rsi
0x18001cb3d  mov     [rsp+1F0h+SecurityDescriptor], rdx
0x18001cb42  mov     [rsp+1F0h+var_1B0], 1
0x18001cb47  mov     rbx, [rbp+0F8h]
0x18001cb4e  xor     r9d, r9d; SecurityDescriptorSize
0x18001cb51  lea     r8, [rsp+1F0h+SecurityDescriptor]; SecurityDescriptor
0x18001cb56  lea     edx, [r9+1]; StringSDRevision
0x18001cb5a  lea     rcx, [rsp+1F0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18001cb5f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001cb65  test    eax, eax
0x18001cb67  jz      short loc_18001CB98
0x18001cb69  lea     rcx, [rsp+1F0h+var_1C0]
0x18001cb6e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x18001cb73  nop
0x18001cb74  mov     rax, rdi
0x18001cb77  mov     rcx, [rbp+0F0h+var_30]
0x18001cb7e  xor     rcx, rsp; StackCookie
0x18001cb81  call    __security_check_cookie
0x18001cb86  add     rsp, 1D8h
0x18001cb8d  pop     rdi
0x18001cb8e  pop     rsi
0x18001cb8f  pop     rbx
0x18001cb90  pop     rbp
0x18001cb91  retn
0x18001cb92  test    ebx, ebx
0x18001cb94  js      short loc_18001CBAD
0x18001cb96  jmp     short loc_18001CB74
0x18001cb98  lea     r8, aOnecoreuapDriv_30; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18001cb9f  mov     edx, 25h ; '%'; void *
0x18001cba4  mov     rcx, rbx; this
0x18001cba7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001cbad  mov     ecx, ebx
0x18001cbaf  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001cbb4  mov     r9d, eax; char *
0x18001cbb7  mov     rcx, [rbp+0F8h]; this
0x18001cbbe  lea     r8, aOnecoreuapDriv_30; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18001cbc5  mov     edx, 29h ; ')'; void *
0x18001cbca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
