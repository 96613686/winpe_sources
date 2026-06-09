# AssignedAccessAdminHelperImpl::EnumDismAppxPackages__lambda_216d28b001ace92039570967d5b74c9d___

- ea: `0x1400627ec`
- end: `0x14006298e`
- name: `AssignedAccessAdminHelperImpl::EnumDismAppxPackages__lambda_216d28b001ace92039570967d5b74c9d___`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x140062f80`

## callees

- `0x140005f30`
- `0x14000d850`
- `0x14002a2c0`
- `0x14002a3e8`
- `0x140044f18`
- `0x1400496fc`
- `0x14005eaf0`
- `0x14005ffc0`
- `0x1400627ec`
- `0x140062994`

## import_xrefs

- `DismApi!DismCloseSession` at `0x14006296c`
- `DismApi!DismCloseSession` at `0x14006296c`
- `DismApi!DismInitialize` at `0x14006281a`
- `DismApi!DismInitialize` at `0x14006281a`
- `DismApi!DismOpenSession` at `0x140062856`
- `DismApi!DismOpenSession` at `0x140062856`
- `DismApi!_DismGetProvisionedAppxPackages` at `0x140062894`
- `DismApi!_DismGetProvisionedAppxPackages` at `0x140062894`

## string_xrefs

- `0x14006282d`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccessadminhelperimpl.cpp`
- `0x140062867`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccessadminhelperimpl.cpp`
- `0x1400628a5`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccessadminhelperimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AssignedAccessAdminHelperImpl::EnumDismAppxPackages__lambda_216d28b001ace92039570967d5b74c9d___(
        __int64 a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // eax
  unsigned int v5; // ebx
  int ProvisionedAppxPackages; // eax
  __int64 v7; // r14
  unsigned int i; // esi
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdi
  __int64 v13; // rdx
  unsigned int v15; // [rsp+20h] [rbp-79h] BYREF
  unsigned int v16; // [rsp+24h] [rbp-75h] BYREF
  __int64 v17; // [rsp+28h] [rbp-71h] BYREF
  unsigned int v18; // [rsp+30h] [rbp-69h]
  char v19; // [rsp+34h] [rbp-65h]
  _BYTE v20[32]; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v21[32]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v22[32]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v23[32]; // [rsp+98h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v3 = DismInitialize(2, 0, 0);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccessadminhelperimpl.cpp",
      (const char *)(unsigned int)v3,
      v15);
  v16 = -1073479676;
  v4 = DismOpenSession(L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}", 0, 0, &v16);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccessadminhelperimpl.cpp",
      (const char *)(unsigned int)v4,
      v15);
  v5 = v16;
  v18 = v16;
  v19 = 1;
  v15 = 0;
  v17 = 0;
  ProvisionedAppxPackages = _DismGetProvisionedAppxPackages(v16, &v17, &v15);
  if ( ProvisionedAppxPackages < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccessadminhelperimpl.cpp",
      (const char *)(unsigned int)ProvisionedAppxPackages,
      v15);
  v7 = v17;
  for ( i = 0; i < v15; ++i )
  {
    v9 = 68LL * i;
    std::wstring::wstring((__int64)v22, *(_QWORD *)(v9 + v7 + 8));
    std::wstring::wstring((__int64)v21, *(_QWORD *)(v9 + v7 + 16));
    v10 = std::operator+<unsigned short>(v23, v22);
    std::operator+<unsigned short>(v20, v10, v21);
    std::wstring::_Tidy_deallocate(v23);
    v12 = *a2;
    v13 = *(_QWORD *)(*a2 + 8LL);
    if ( v13 == *(_QWORD *)(*a2 + 16LL) )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(*a2, v13, v20);
    }
    else
    {
      std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring &>(
        v11,
        v13,
        v20);
      *(_QWORD *)(v12 + 8) += 32LL;
    }
    std::wstring::_Tidy_deallocate(v20);
    std::wstring::_Tidy_deallocate(v21);
    std::wstring::_Tidy_deallocate(v22);
  }
  wil::details::unique_storage<wil::details::resource_policy<_DismAppxPackage *,long (*)(void *),&long DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismAppxPackage *,_DismAppxPackage *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DismAppxPackage *,long (*)(void *),&long DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismAppxPackage *,_DismAppxPackage *,0,std::nullptr_t>>(&v17);
  return DismCloseSession(v5);
}

```

## disassembly

```asm
0x1400627ec  push    rbp
0x1400627ee  push    rbx
0x1400627ef  push    rsi
0x1400627f0  push    rdi
0x1400627f1  push    r14
0x1400627f3  push    r15
0x1400627f5  lea     rbp, [rsp-2Fh]
0x1400627fa  sub     rsp, 0C8h
0x140062801  mov     rax, cs:__security_cookie
0x140062808  xor     rax, rsp
0x14006280b  mov     [rbp+57h+var_38], rax
0x14006280f  mov     r15, rdx
0x140062812  xor     r8d, r8d
0x140062815  xor     edx, edx
0x140062817  lea     ecx, [rdx+2]
0x14006281a  call    cs:__imp_DismInitialize
0x140062820  mov     rcx, [rbp+5Fh]; this
0x140062824  xor     edi, edi
0x140062826  test    eax, eax
0x140062828  jns     short loc_14006283F
0x14006282a  mov     r9d, eax; char *
0x14006282d  lea     r8, aPcshellShellSy_20; "pcshell\\shell\\systemsettings\\adminfl"...
0x140062834  mov     edx, 0D1h; void *
0x140062839  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006283f  mov     [rbp+57h+var_CC], 0C0040004h
0x140062846  lea     r9, [rbp+57h+var_CC]
0x14006284a  xor     r8d, r8d
0x14006284d  xor     edx, edx
0x14006284f  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x140062856  call    cs:__imp_DismOpenSession
0x14006285c  mov     rcx, [rbp+5Fh]; this
0x140062860  test    eax, eax
0x140062862  jns     short loc_140062879
0x140062864  mov     r9d, eax; char *
0x140062867  lea     r8, aPcshellShellSy_20; "pcshell\\shell\\systemsettings\\adminfl"...
0x14006286e  mov     edx, 0D3h; void *
0x140062873  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140062879  mov     ebx, [rbp+57h+var_CC]
0x14006287c  mov     [rbp+57h+var_C0], ebx
0x14006287f  mov     [rbp+57h+var_BC], 1
0x140062883  mov     [rbp+57h+var_D0], edi
0x140062886  mov     [rbp+57h+var_C8], rdi
0x14006288a  lea     r8, [rbp+57h+var_D0]
0x14006288e  lea     rdx, [rbp+57h+var_C8]
0x140062892  mov     ecx, ebx
0x140062894  call    cs:__imp__DismGetProvisionedAppxPackages
0x14006289a  mov     rcx, [rbp+5Fh]; this
0x14006289e  test    eax, eax
0x1400628a0  jns     short loc_1400628B7
0x1400628a2  mov     r9d, eax; char *
0x1400628a5  lea     r8, aPcshellShellSy_20; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400628ac  mov     edx, 0DCh; void *
0x1400628b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400628b7  mov     r14, [rbp+57h+var_C8]
0x1400628bb  mov     esi, edi
0x1400628bd  cmp     [rbp+57h+var_D0], edi
0x1400628c0  jbe     loc_140062960
0x1400628c6  mov     eax, esi
0x1400628c8  imul    rdi, rax, 44h ; 'D'
0x1400628cc  mov     rdx, [rdi+r14+8]
0x1400628d1  lea     rcx, [rbp+57h+var_78]
0x1400628d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400628da  nop
0x1400628db  mov     rdx, [rdi+r14+10h]
0x1400628e0  lea     rcx, [rbp+57h+var_98]
0x1400628e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400628e9  nop
0x1400628ea  lea     rdx, [rbp+57h+var_78]
0x1400628ee  lea     rcx, [rbp+57h+var_58]
0x1400628f2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1400628f7  nop
0x1400628f8  lea     r8, [rbp+57h+var_98]
0x1400628fc  mov     rdx, rax
0x1400628ff  lea     rcx, [rbp+57h+var_B8]
0x140062903  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x140062908  nop
0x140062909  lea     rcx, [rbp+57h+var_58]
0x14006290d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140062912  mov     rdi, [r15]
0x140062915  mov     rdx, [rdi+8]
0x140062919  lea     r8, [rbp+57h+var_B8]
0x14006291d  cmp     rdx, [rdi+10h]
0x140062921  jz      short loc_14006292F
0x140062923  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@?$_Default_allocator_traits@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@SAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAV31@@Z; std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring &>(std::allocator<std::wstring> &,std::wstring * const,std::wstring &)
0x140062928  add     qword ptr [rdi+8], 20h ; ' '
0x14006292d  jmp     short loc_140062938
0x14006292f  mov     rcx, rdi
0x140062932  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x140062937  nop
0x140062938  lea     rcx, [rbp+57h+var_B8]
0x14006293c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140062941  nop
0x140062942  lea     rcx, [rbp+57h+var_98]
0x140062946  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006294b  nop
0x14006294c  lea     rcx, [rbp+57h+var_78]
0x140062950  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140062955  inc     esi
0x140062957  cmp     esi, [rbp+57h+var_D0]
0x14006295a  jb      loc_1400628C6
0x140062960  lea     rcx, [rbp+57h+var_C8]
0x140062964  call    ??1?$unique_storage@U?$resource_policy@PEAU_DismAppxPackage@@P6AJPEAX@Z$1?DismDelete@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DismAppxPackage *,long (*)(void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismAppxPackage *,_DismAppxPackage *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DismAppxPackage *,long (*)(void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismAppxPackage *,_DismAppxPackage *,0,std::nullptr_t>>(void)
0x140062969  nop
0x14006296a  mov     ecx, ebx
0x14006296c  call    cs:__imp_DismCloseSession
0x140062972  mov     rcx, [rbp+57h+var_38]
0x140062976  xor     rcx, rsp; StackCookie
0x140062979  call    __security_check_cookie
0x14006297e  add     rsp, 0C8h
0x140062985  pop     r15
0x140062987  pop     r14
0x140062989  pop     rdi
0x14006298a  pop     rsi
0x14006298b  pop     rbx
0x14006298c  pop     rbp
0x14006298d  retn
```
