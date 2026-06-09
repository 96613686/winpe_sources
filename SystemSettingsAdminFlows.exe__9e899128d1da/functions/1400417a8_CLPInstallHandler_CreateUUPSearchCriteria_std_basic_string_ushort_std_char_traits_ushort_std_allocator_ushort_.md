# CLPInstallHandler::CreateUUPSearchCriteria(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool *)

- ea: `0x1400417a8`
- end: `0x140041b01`
- name: `?CreateUUPSearchCriteria@CLPInstallHandler@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEA_N@Z`
- size: `857`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400415ac`

## callees

- `0x14000c214`
- `0x14001a2a0`
- `0x14002a2c0`
- `0x14002ae30`
- `0x14002bc78`
- `0x1400412a8`
- `0x1400417a8`
- `0x1400423bc`
- `0x14007d010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140041a1c`
- `ole32!CoTaskMemFree` at `0x140041a1c`
- `ext-ms-win-deployment-productenumerator-l1-1-0!PE_CreateProductEnumerator` at `0x1400417cc`
- `ext-ms-win-deployment-productenumerator-l1-1-0!PE_CreateProductEnumerator` at `0x1400417cc`

## string_xrefs

- `0x1400417e1`: `pcshell\shell\systemsettings\adminflows\languagepackinstaller\lib\lpinstallhandler.cpp`
- `0x140041822`: `pcshell\shell\systemsettings\adminflows\languagepackinstaller\lib\lpinstallhandler.cpp`
- `0x140041866`: `pcshell\shell\systemsettings\adminflows\languagepackinstaller\lib\lpinstallhandler.cpp`
- `0x140041895`: `pcshell\shell\systemsettings\adminflows\languagepackinstaller\lib\lpinstallhandler.cpp`
- `0x1400418f6`: `pcshell\shell\systemsettings\adminflows\languagepackinstaller\lib\lpinstallhandler.cpp`
- `0x14004197f`: `pcshell\shell\systemsettings\adminflows\languagepackinstaller\lib\lpinstallhandler.cpp`
- `0x1400419d9`: `pcshell\shell\systemsettings\adminflows\languagepackinstaller\lib\lpinstallhandler.cpp`
- `0x140041a00`: `' and IsInstalled=0 and RebootRequired=1 and DeploymentAction=*)`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CLPInstallHandler::CreateUUPSearchCriteria(__int64 a1, bool *a2)
{
  int v4; // eax
  int v5; // eax
  int v6; // eax
  const char *v7; // r9
  unsigned int v8; // edx
  unsigned int i; // r14d
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, int *); // rbx
  int v12; // eax
  __int64 *v13; // rdi
  int (__fastcall *v14)(__int64 *, const wchar_t *, __int64 *); // rbx
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rcx
  int IsUpdateCurrentVersionOnly; // eax
  void *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 result; // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  int v26[2]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v27; // [rsp+28h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-58h] BYREF
  __int64 v29; // [rsp+38h] [rbp-50h] BYREF
  LPVOID *p_pv; // [rsp+40h] [rbp-48h] BYREF
  __int64 v31; // [rsp+48h] [rbp-40h] BYREF
  char v32; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  unsigned int v34; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v35; // [rsp+A8h] [rbp+20h] BYREF

  v27 = 0;
  v4 = PE_CreateProductEnumerator(&v27);
  try
  {
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A2,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagepackinstaller\\lib\\lpinstallhandler.cpp",
        (const char *)(unsigned int)v4,
        v26[0]);
    v35 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 24LL))(v27, &v35);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A5,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagepackinstaller\\lib\\lpinstallhandler.cpp",
        (const char *)(unsigned int)v5,
        v26[0]);
    v34 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v35 + 24LL))(v35, &v34);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A8,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagepackinstaller\\lib\\lpinstallhandler.cpp",
        (const char *)(unsigned int)v6,
        v26[0]);
    v8 = v34;
    if ( !v34 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A9,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagepackinstaller\\lib\\lpinstallhandler.cpp",
        (const char *)0x8000FFFFLL,
        v26[0]);
    *a2 = 1;
    for ( i = 0; i < v8; ++i )
    {
      *(_QWORD *)v26 = 0;
      v10 = v35;
      v11 = *(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v35 + 32LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v26);
      v12 = v11(v10, i, v26);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B1,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagepackinstaller\\lib\\lpinstallhandler.cpp",
          (const char *)(unsigned int)v12,
          v26[0]);
      v29 = 0;
      v13 = *(__int64 **)v26;
      v14 = *(int (__fastcall **)(__int64 *, const wchar_t *, __int64 *))(**(_QWORD **)v26 + 40LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      if ( v14(v13, L"PrimaryOSProduct", &v29) >= 0 )
      {
        pv = 0;
        v15 = **(_QWORD **)v26;
        p_pv = &pv;
        v31 = 0;
        v32 = 1;
        v16 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v15 + 24))(*(_QWORD *)v26, &v31);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1B7,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagepackinstaller\\lib\\lpinstallhandler.cpp",
            (const char *)(unsigned int)v16,
            v26[0]);
        wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
        v17 = std::_WChar_traits<unsigned short>::length(L"(Product='");
        std::wstring::_Assign<unsigned short>(a1, v18, v17);
        std::wstring::append(a1, pv);
        IsUpdateCurrentVersionOnly = CLPInstallHandler::IsUpdateCurrentVersionOnly(a2);
        if ( IsUpdateCurrentVersionOnly < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1BC,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagepackinstaller\\lib\\lpinstallhandler.cpp",
            (const char *)(unsigned int)IsUpdateCurrentVersionOnly,
            v26[0]);
        if ( *a2 )
          std::wstring::append(a1, L"' and CurrentVersionOnly=1 and DeploymentAction=*)");
        else
          std::wstring::append(a1, L"' and IsInstalled=0 and RebootRequired=1 and DeploymentAction=*)");
        v20 = pv;
        pv = 0;
        if ( v20 )
          CoTaskMemFree(v20);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v26);
        v21 = v35;
        if ( v35 )
        {
          v35 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        v22 = v27;
        if ( v27 )
        {
          v27 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        return 0;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v26);
      v8 = v34;
    }
    v24 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    result = 2148469073LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1CD,
                           (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagepackinstaller\\lib\\lpinstallhandler.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x1400417a8  mov     [rsp+arg_0], rbx
0x1400417ad  push    rsi
0x1400417ae  push    rdi
0x1400417af  push    r12
0x1400417b1  push    r14
0x1400417b3  push    r15
0x1400417b5  sub     rsp, 60h
0x1400417b9  mov     r15, rdx
0x1400417bc  mov     rsi, rcx
0x1400417bf  xor     r12d, r12d
0x1400417c2  mov     [rsp+88h+var_60], r12
0x1400417c7  lea     rcx, [rsp+88h+var_60]
0x1400417cc  call    cs:__imp_PE_CreateProductEnumerator
0x1400417d2  mov     rcx, [rsp+88h]; this
0x1400417da  test    eax, eax
0x1400417dc  jns     short loc_1400417F2
0x1400417de  mov     r9d, eax; char *
0x1400417e1  lea     r8, aPcshellShellSy_24; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400417e8  mov     edx, 1A2h; void *
0x1400417ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400417f2  mov     [rsp+88h+arg_18], r12
0x1400417fa  mov     rcx, [rsp+88h+var_60]
0x1400417ff  mov     rax, [rcx]
0x140041802  lea     rdx, [rsp+88h+arg_18]
0x14004180a  mov     rax, [rax+18h]
0x14004180e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041813  mov     rcx, [rsp+88h]; this
0x14004181b  test    eax, eax
0x14004181d  jns     short loc_140041833
0x14004181f  mov     r9d, eax; char *
0x140041822  lea     r8, aPcshellShellSy_24; "pcshell\\shell\\systemsettings\\adminfl"...
0x140041829  mov     edx, 1A5h; void *
0x14004182e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140041833  mov     [rsp+88h+arg_10], r12d
0x14004183b  mov     rcx, [rsp+88h+arg_18]
0x140041843  mov     rax, [rcx]
0x140041846  lea     rdx, [rsp+88h+arg_10]
0x14004184e  mov     rax, [rax+18h]
0x140041852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041857  mov     rcx, [rsp+88h]; this
0x14004185f  test    eax, eax
0x140041861  jns     short loc_140041877
0x140041863  mov     r9d, eax; char *
0x140041866  lea     r8, aPcshellShellSy_24; "pcshell\\shell\\systemsettings\\adminfl"...
0x14004186d  mov     edx, 1A8h; void *
0x140041872  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140041877  mov     edx, [rsp+88h+arg_10]
0x14004187e  test    edx, edx
0x140041880  setz    al
0x140041883  mov     rcx, [rsp+88h]; this
0x14004188b  test    al, al
0x14004188d  jz      short loc_1400418A6
0x14004188f  mov     r9d, 8000FFFFh; char *
0x140041895  lea     r8, aPcshellShellSy_24; "pcshell\\shell\\systemsettings\\adminfl"...
0x14004189c  mov     edx, 1A9h; void *
0x1400418a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400418a6  mov     byte ptr [r15], 1
0x1400418aa  mov     r14d, r12d
0x1400418ad  cmp     r14d, edx
0x1400418b0  jnb     loc_140041A9F
0x1400418b6  mov     qword ptr [rsp+88h+var_68], r12; int
0x1400418bb  mov     rdi, [rsp+88h+arg_18]
0x1400418c3  mov     rax, [rdi]
0x1400418c6  mov     rbx, [rax+20h]
0x1400418ca  lea     rcx, [rsp+88h+var_68]
0x1400418cf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400418d4  lea     r8, [rsp+88h+var_68]
0x1400418d9  mov     edx, r14d
0x1400418dc  mov     rcx, rdi
0x1400418df  mov     rax, rbx
0x1400418e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400418e7  mov     rcx, [rsp+88h]; this
0x1400418ef  test    eax, eax
0x1400418f1  jns     short loc_140041907
0x1400418f3  mov     r9d, eax; char *
0x1400418f6  lea     r8, aPcshellShellSy_24; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400418fd  mov     edx, 1B1h; void *
0x140041902  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140041907  mov     [rsp+88h+var_50], r12
0x14004190c  mov     rdi, qword ptr [rsp+88h+var_68]
0x140041911  mov     rax, [rdi]
0x140041914  mov     rbx, [rax+28h]
0x140041918  lea     rcx, [rsp+88h+var_50]
0x14004191d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140041922  lea     r8, [rsp+88h+var_50]
0x140041927  lea     rdx, aPrimaryosprodu; "PrimaryOSProduct"
0x14004192e  mov     rcx, rdi
0x140041931  mov     rax, rbx
0x140041934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041939  test    eax, eax
0x14004193b  js      loc_140041A7B
0x140041941  mov     [rsp+88h+pv], r12
0x140041946  mov     rcx, qword ptr [rsp+88h+var_68]
0x14004194b  mov     rax, [rcx]
0x14004194e  lea     rdx, [rsp+88h+pv]
0x140041953  mov     [rsp+88h+var_48], rdx
0x140041958  mov     [rsp+88h+var_40], r12
0x14004195d  mov     [rsp+88h+var_38], 1
0x140041962  lea     rdx, [rsp+88h+var_40]
0x140041967  mov     rax, [rax+18h]
0x14004196b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041970  mov     rcx, [rsp+88h]; this
0x140041978  test    eax, eax
0x14004197a  jns     short loc_140041991
0x14004197c  mov     r9d, eax; char *
0x14004197f  lea     r8, aPcshellShellSy_24; "pcshell\\shell\\systemsettings\\adminfl"...
0x140041986  mov     edx, 1B7h; void *
0x14004198b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140041991  lea     rcx, [rsp+88h+var_48]
0x140041996  call    ??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x14004199b  lea     rcx, aProduct; "(Product='"
0x1400419a2  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1400419a7  mov     r8, rax
0x1400419aa  mov     rdx, rcx
0x1400419ad  mov     rcx, rsi
0x1400419b0  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1400419b5  mov     rdx, [rsp+88h+pv]
0x1400419ba  mov     rcx, rsi
0x1400419bd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1400419c2  mov     rcx, r15; bool *
0x1400419c5  call    ?IsUpdateCurrentVersionOnly@CLPInstallHandler@@CAJPEA_N@Z; CLPInstallHandler::IsUpdateCurrentVersionOnly(bool *)
0x1400419ca  mov     rcx, [rsp+88h]; this
0x1400419d2  test    eax, eax
0x1400419d4  jns     short loc_1400419EA
0x1400419d6  mov     r9d, eax; char *
0x1400419d9  lea     r8, aPcshellShellSy_24; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400419e0  mov     edx, 1BCh; void *
0x1400419e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400419ea  mov     rcx, rsi
0x1400419ed  cmp     [r15], r12b
0x1400419f0  jz      short loc_140041A00
0x1400419f2  lea     rdx, aAndCurrentvers; "' and CurrentVersionOnly=1 and Deployme"...
0x1400419f9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1400419fe  jmp     short loc_140041A0D
0x140041a00  lea     rdx, aAndIsinstalled; "' and IsInstalled=0 and RebootRequired="...
0x140041a07  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x140041a0c  nop
0x140041a0d  mov     rcx, [rsp+88h+pv]; pv
0x140041a12  mov     [rsp+88h+pv], r12
0x140041a17  test    rcx, rcx
0x140041a1a  jz      short loc_140041A23
0x140041a1c  call    cs:__imp_CoTaskMemFree
0x140041a22  nop
0x140041a23  lea     rcx, [rsp+88h+var_50]
0x140041a28  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140041a2d  nop
0x140041a2e  lea     rcx, [rsp+88h+var_68]
0x140041a33  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140041a38  nop
0x140041a39  mov     rcx, [rsp+88h+arg_18]
0x140041a41  test    rcx, rcx
0x140041a44  jz      short loc_140041A5B
0x140041a46  mov     [rsp+88h+arg_18], r12
0x140041a4e  mov     rax, [rcx]
0x140041a51  mov     rax, [rax+10h]
0x140041a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041a5a  nop
0x140041a5b  mov     rcx, [rsp+88h+var_60]
0x140041a60  test    rcx, rcx
0x140041a63  jz      short loc_140041A77
0x140041a65  mov     [rsp+88h+var_60], r12
0x140041a6a  mov     rax, [rcx]
0x140041a6d  mov     rax, [rax+10h]
0x140041a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041a76  nop
0x140041a77  xor     eax, eax
0x140041a79  jmp     short loc_140041AEB
0x140041a7b  lea     rcx, [rsp+88h+var_50]
0x140041a80  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140041a85  nop
0x140041a86  lea     rcx, [rsp+88h+var_68]
0x140041a8b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140041a90  inc     r14d
0x140041a93  mov     edx, [rsp+88h+arg_10]
0x140041a9a  jmp     loc_1400418AD
0x140041a9f  mov     rcx, [rsp+88h+arg_18]
0x140041aa7  test    rcx, rcx
0x140041aaa  jz      short loc_140041AC1
0x140041aac  mov     [rsp+88h+arg_18], r12
0x140041ab4  mov     rax, [rcx]
0x140041ab7  mov     rax, [rax+10h]
0x140041abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041ac0  nop
0x140041ac1  mov     rcx, [rsp+88h+var_60]
0x140041ac6  test    rcx, rcx
0x140041ac9  jz      short loc_140041ADD
0x140041acb  mov     [rsp+88h+var_60], r12
0x140041ad0  mov     rax, [rcx]
0x140041ad3  mov     rax, [rax+10h]
0x140041ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041adc  nop
0x140041add  mov     eax, 800F0951h
0x140041ae2  jmp     short loc_140041AEB
0x140041ae4  mov     eax, [rsp+88h+arg_10]
0x140041aeb  mov     rbx, [rsp+88h+arg_0]
0x140041af3  add     rsp, 60h
0x140041af7  pop     r15
0x140041af9  pop     r14
0x140041afb  pop     r12
0x140041afd  pop     rdi
0x140041afe  pop     rsi
0x140041aff  retn
```
