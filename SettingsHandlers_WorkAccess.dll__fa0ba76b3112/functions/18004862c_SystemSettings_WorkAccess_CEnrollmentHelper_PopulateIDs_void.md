# SystemSettings::WorkAccess::CEnrollmentHelper::PopulateIDs(void)

- ea: `0x18004862c`
- end: `0x180048bc2`
- name: `?PopulateIDs@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJXZ`
- size: `1430`
- prototype: `__int64(void)`
- caller_count: `11`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180026be8`
- `0x1800294b0`
- `0x18002a3dc`
- `0x18002dff8`
- `0x18002e0b4`
- `0x18002e280`
- `0x18002e534`
- `0x1800339a0`
- `0x18003e2f0`
- `0x180042080`
- `0x180043740`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x1800096ec`
- `0x180023164`
- `0x1800236d8`
- `0x1800236fc`
- `0x1800257a4`
- `0x180027ab0`
- `0x1800291ec`
- `0x180029234`
- `0x180029708`
- `0x180029764`
- `0x18003ab34`
- `0x18003ab74`
- `0x180045528`
- `0x18004586c`
- `0x180045c2c`
- `0x18004862c`
- `0x18004cba0`
- `0x18004cbdc`
- `0x18004cc18`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004898c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180048a06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004898c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180048a06`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x1800486c8`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x1800486c8`
- `OLEAUT32!__imp_SysAllocString` at `0x18004889c`
- `OLEAUT32!__imp_SysAllocString` at `0x18004889c`

## string_xrefs

- `0x180048a89`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180048ac0`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180048ae2`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180048b03`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180048b2d`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180048b51`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180048b76`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 SystemSettings::WorkAccess::CEnrollmentHelper::PopulateIDs(void)
{
  __int64 v0; // rax
  __int64 v1; // rcx
  volatile signed __int32 *v2; // rbx
  __int64 DatabaseManagerInstance; // rdi
  __int64 (__fastcall *v4)(__int64, __int64, __int64 *); // rbx
  int v5; // eax
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  __int64 v10; // rdx
  unsigned __int64 v11; // r9
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, unsigned __int16 **); // rbx
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  const unsigned __int16 *v18; // rax
  int v19; // eax
  int CurrentUserSidString; // eax
  __int64 v21; // rbx
  unsigned __int16 *v22; // rax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, unsigned __int16 **); // rbx
  int v25; // eax
  void *v26; // rcx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, PCNZWCH *); // rbx
  HRESULT String; // eax
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rax
  const WCHAR *v34; // rax
  __int64 v35; // rdx
  HRESULT v36; // eax
  __int64 v37; // rdi
  unsigned int (__fastcall *v38)(__int64, __int64 *); // rbx
  void *p_sourceString; // rcx
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // rdx
  unsigned __int16 *v44; // [rsp+20h] [rbp-99h] BYREF
  __int64 v45; // [rsp+28h] [rbp-91h] BYREF
  unsigned int v46; // [rsp+30h] [rbp-89h] BYREF
  PCNZWCH sourceString; // [rsp+38h] [rbp-81h] BYREF
  __int64 v48; // [rsp+40h] [rbp-79h] BYREF
  OLECHAR *psz; // [rsp+48h] [rbp-71h] BYREF
  unsigned __int16 *v50; // [rsp+50h] [rbp-69h] BYREF
  volatile signed __int32 *v51; // [rsp+58h] [rbp-61h]
  __int64 v52; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v53[32]; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v54[32]; // [rsp+88h] [rbp-31h] BYREF
  _BYTE v55[32]; // [rsp+A8h] [rbp-11h] BYREF
  _BYTE v56[32]; // [rsp+C8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  SystemSettings::WorkAccess::CEnrollmentHelper::_value = 0;
  SystemSettings::WorkAccess::CEnrollmentHelper::_appCspValue = 0;
  if ( !SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton )
  {
    v0 = std::make_shared<SystemSettings::WorkAccess::CAccountEnthusiastData,>(&v50);
    std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData>::operator=(v1, v0);
    v2 = v51;
    if ( v51 )
    {
      if ( !_InterlockedDecrement(v51 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
        if ( !_InterlockedDecrement(v2 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
      }
    }
  }
  v48 = 0;
  v45 = 0;
  v52 = 0;
  DatabaseManagerInstance = GetDatabaseManagerInstance();
  v4 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 32LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
  v5 = v4(DatabaseManagerInstance, 222306401, &v48);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 162;
    goto LABEL_13;
  }
  v8 = v48;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v48 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
  v5 = v9(v8, &v45);
  v6 = v5;
  if ( v5 == 1 )
  {
    v6 = -2147023728;
    goto LABEL_60;
  }
  if ( v5 )
  {
    if ( v5 >= 0 )
      goto LABEL_60;
    v7 = 166;
LABEL_13:
    v11 = (unsigned int)v5;
    goto LABEL_59;
  }
  LOBYTE(v10) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::GetImpl'::`2'::impl,
    v10);
  while ( 1 )
  {
    v46 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v45 + 48LL))(v45, &v46);
    if ( v6 < 0 )
      break;
    if ( ((v46 - 24) & 0xFFFFFFFD) != 0 )
    {
      if ( SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton )
      {
        v44 = 0;
        v12 = v45;
        v13 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v45 + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v44,
          0);
        v14 = v13(v12, &v44);
        v6 = v14;
        if ( v14 < 0 )
        {
          v42 = 193;
          goto LABEL_50;
        }
        v14 = SystemSettings::WorkAccess::CEnrollmentHelper::SetEnrollmentID(v44);
        v6 = v14;
        if ( v14 < 0 )
        {
          v42 = 194;
LABEL_50:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v42,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
            (const char *)(unsigned int)v14,
            (int)v44);
          goto LABEL_44;
        }
        v15 = std::wstring::wstring(v56, v44);
        v17 = std::operator+<unsigned short>(v55, v16, v15);
        std::operator+<unsigned short>(v53, v17);
        std::wstring::_Tidy_deallocate(v55);
        std::wstring::_Tidy_deallocate(v56);
        v18 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v53);
        v19 = SystemSettings::WorkAccess::CEnrollmentHelper::SetEnrollmentIDWithBraces(v18);
        v6 = v19;
        if ( v19 < 0 )
        {
          v41 = 197;
          goto LABEL_47;
        }
        v19 = SystemSettings::WorkAccess::CEnrollmentHelper::SetEnrollmentType(v46);
        v6 = v19;
        if ( v19 < 0 )
        {
          v41 = 199;
LABEL_47:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v41,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
            (const char *)(unsigned int)v19,
            (int)v44);
LABEL_43:
          std::wstring::_Tidy_deallocate(v53);
LABEL_44:
          p_sourceString = &v44;
          goto LABEL_57;
        }
        if ( ((1LL << v46) & 0x4000040) != 0 )
        {
          psz = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &psz,
            0);
          CurrentUserSidString = GetCurrentUserSidString(&psz);
          v6 = CurrentUserSidString;
          if ( CurrentUserSidString < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xCD,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
              (const char *)(unsigned int)CurrentUserSidString,
              (int)v44);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
            goto LABEL_43;
          }
          v21 = SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton;
          v22 = SysAllocString(psz);
          _bstr_t::Assign((_bstr_t *)(v21 + 40), v22);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
        }
        else
        {
          v50 = 0;
          v23 = v45;
          v24 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v45 + 112LL);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v50,
            0);
          v25 = v24(v23, &v50);
          v6 = v25;
          if ( v25 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xD3,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
              (const char *)(unsigned int)v25,
              (int)v44);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
            goto LABEL_43;
          }
          _bstr_t::Assign(
            (_bstr_t *)(SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton + 40),
            v50);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
        }
        std::wstring::_Tidy_deallocate(v53);
        v26 = &v44;
        goto LABEL_39;
      }
    }
    else if ( SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton )
    {
      sourceString = 0;
      v27 = v45;
      v28 = *(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v45 + 32LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &sourceString,
        0);
      String = v28(v27, &sourceString);
      v6 = String;
      if ( String < 0 )
      {
        v43 = 181;
LABEL_55:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v43,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
          (const char *)(unsigned int)String,
          (int)v44);
LABEL_56:
        p_sourceString = &sourceString;
LABEL_57:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(p_sourceString);
        goto LABEL_60;
      }
      if ( SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton )
      {
        v30 = -1;
        do
          ++v30;
        while ( sourceString[v30] );
        String = WindowsCreateString(
                   sourceString,
                   v30,
                   (HSTRING *)(SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton + 24));
        v6 = String;
        if ( String < 0 )
        {
          v43 = 182;
          goto LABEL_55;
        }
      }
      v31 = std::wstring::wstring(v55, sourceString);
      v33 = std::operator+<unsigned short>(v56, v32, v31);
      std::operator+<unsigned short>(v54, v33);
      std::wstring::_Tidy_deallocate(v56);
      std::wstring::_Tidy_deallocate(v55);
      v34 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54);
      if ( SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton )
      {
        v35 = -1;
        do
          ++v35;
        while ( v34[v35] );
        v36 = WindowsCreateString(
                v34,
                v35,
                (HSTRING *)(SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton + 32));
        v6 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB9,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
            (const char *)(unsigned int)v36,
            (int)v44);
          std::wstring::_Tidy_deallocate(v54);
          goto LABEL_56;
        }
      }
      std::wstring::_Tidy_deallocate(v54);
      v26 = &sourceString;
LABEL_39:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v26);
    }
    v37 = v48;
    v38 = *(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v48 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
    if ( v38(v37, &v45) )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
      return 0;
    }
  }
  v11 = (unsigned int)v6;
  v7 = 175;
LABEL_59:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
    (const char *)v11,
    (int)v44);
LABEL_60:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004862c  push    rbp
0x18004862e  push    rbx
0x18004862f  push    rsi
0x180048630  push    rdi
0x180048631  push    r14
0x180048633  lea     rbp, [rsp-37h]
0x180048638  sub     rsp, 0F0h
0x18004863f  mov     rax, cs:__security_cookie
0x180048646  xor     rax, rsp
0x180048649  mov     [rbp+57h+var_28], rax
0x18004864d  xor     esi, esi
0x18004864f  mov     cs:?_value@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA, rsi; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_value
0x180048656  mov     cs:?_appCspValue@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA, rsi; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_appCspValue
0x18004865d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180048661  cmp     cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A, rsi; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x180048668  jnz     short loc_1800486BB
0x18004866a  lea     rcx, [rbp+57h+var_C0]
0x18004866e  call    ??$make_shared@VCAccountEnthusiastData@WorkAccess@SystemSettings@@$$V@std@@YA?AV?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@0@XZ; std::make_shared<SystemSettings::WorkAccess::CAccountEnthusiastData,>(void)
0x180048673  mov     rdx, rax
0x180048676  call    ??4?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData>::operator=(std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> &&)
0x18004867b  mov     rbx, [rbp+57h+var_B8]
0x18004867f  test    rbx, rbx
0x180048682  jz      short loc_1800486BB
0x180048684  mov     eax, r14d
0x180048687  lock xadd [rbx+8], eax
0x18004868c  add     eax, r14d
0x18004868f  jnz     short loc_1800486BB
0x180048691  mov     rax, [rbx]
0x180048694  mov     rcx, rbx
0x180048697  mov     rax, [rax]
0x18004869a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004869f  mov     eax, r14d
0x1800486a2  lock xadd [rbx+0Ch], eax
0x1800486a7  add     eax, r14d
0x1800486aa  jnz     short loc_1800486BB
0x1800486ac  mov     rax, [rbx]
0x1800486af  mov     rcx, rbx
0x1800486b2  mov     rax, [rax+8]
0x1800486b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800486bb  mov     [rbp+57h+var_D0], rsi
0x1800486bf  mov     [rsp+110h+var_E8], rsi
0x1800486c4  mov     [rbp+57h+var_B0], rsi
0x1800486c8  call    cs:__imp_GetDatabaseManagerInstance
0x1800486cf  nop     dword ptr [rax+rax+00h]
0x1800486d4  mov     rdi, rax
0x1800486d7  mov     rcx, [rax]
0x1800486da  mov     rbx, [rcx+20h]
0x1800486de  lea     rcx, [rbp+57h+var_D0]
0x1800486e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800486e7  lea     r8, [rbp+57h+var_D0]
0x1800486eb  mov     edx, 0D402061h
0x1800486f0  mov     rcx, rdi
0x1800486f3  mov     rax, rbx
0x1800486f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800486fb  mov     ebx, eax
0x1800486fd  test    eax, eax
0x1800486ff  jns     short loc_180048708
0x180048701  mov     edx, 0A2h
0x180048706  jmp     short loc_18004874D
0x180048708  mov     rdi, [rbp+57h+var_D0]
0x18004870c  mov     rax, [rdi]
0x18004870f  mov     rbx, [rax+18h]
0x180048713  lea     rcx, [rsp+110h+var_E8]
0x180048718  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004871d  lea     rdx, [rsp+110h+var_E8]
0x180048722  mov     rcx, rdi
0x180048725  mov     rax, rbx
0x180048728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004872d  mov     ebx, eax
0x18004872f  cmp     eax, 1
0x180048732  jnz     short loc_18004873E
0x180048734  mov     ebx, 80070490h
0x180048739  jmp     loc_180048B87
0x18004873e  test    eax, eax
0x180048740  jz      short loc_180048755
0x180048742  jns     loc_180048B87
0x180048748  mov     edx, 0A6h
0x18004874d  mov     r9d, eax
0x180048750  jmp     loc_180048B76
0x180048755  mov     dl, 1
0x180048757  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WPJRecoveryFix56099781@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WPJRecoveryFix56099781@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WPJRecoveryFix56099781> `wil::Feature<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::GetImpl(void)'::`2'::impl
0x18004875e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WPJRecoveryFix56099781@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180048763  mov     [rsp+110h+var_E0], esi
0x180048767  mov     rcx, [rsp+110h+var_E8]
0x18004876c  mov     rax, [rcx]
0x18004876f  lea     rdx, [rsp+110h+var_E0]
0x180048774  mov     rax, [rax+30h]
0x180048778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004877d  mov     ebx, eax
0x18004877f  test    eax, eax
0x180048781  js      loc_180048B6E
0x180048787  mov     eax, [rsp+110h+var_E0]
0x18004878b  add     eax, 0FFFFFFE8h
0x18004878e  test    eax, 0FFFFFFFDh
0x180048793  jz      loc_180048927
0x180048799  cmp     cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A, rsi; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x1800487a0  jz      loc_180048A30
0x1800487a6  mov     [rsp+110h+var_F0], rsi; int
0x1800487ab  mov     rdi, [rsp+110h+var_E8]
0x1800487b0  mov     rax, [rdi]
0x1800487b3  mov     rbx, [rax+20h]
0x1800487b7  xor     edx, edx
0x1800487b9  lea     rcx, [rsp+110h+var_F0]
0x1800487be  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800487c3  lea     rdx, [rsp+110h+var_F0]
0x1800487c8  mov     rcx, rdi
0x1800487cb  mov     rax, rbx
0x1800487ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800487d3  mov     ebx, eax
0x1800487d5  test    eax, eax
0x1800487d7  js      loc_180048B18
0x1800487dd  mov     rcx, [rsp+110h+var_F0]; unsigned __int16 *
0x1800487e2  call    ?SetEnrollmentID@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJQEBG@Z; SystemSettings::WorkAccess::CEnrollmentHelper::SetEnrollmentID(ushort const * const)
0x1800487e7  mov     ebx, eax
0x1800487e9  test    eax, eax
0x1800487eb  js      loc_180048AFE
0x1800487f1  mov     rdx, [rsp+110h+var_F0]
0x1800487f6  lea     rcx, [rbp+57h+var_48]
0x1800487fa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800487ff  nop
0x180048800  mov     r8, rax
0x180048803  lea     rcx, [rbp+57h+var_68]
0x180048807  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@G$$QEAV10@@Z; std::operator+<ushort>(ushort,std::wstring &&)
0x18004880c  nop
0x18004880d  mov     rdx, rax
0x180048810  lea     rcx, [rbp+57h+var_A8]
0x180048814  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@G@Z; std::operator+<ushort>(std::wstring &&,ushort)
0x180048819  nop
0x18004881a  lea     rcx, [rbp+57h+var_68]
0x18004881e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048823  nop
0x180048824  lea     rcx, [rbp+57h+var_48]
0x180048828  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004882d  lea     rcx, [rbp+57h+var_A8]
0x180048831  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180048836  mov     rcx, rax; unsigned __int16 *
0x180048839  call    ?SetEnrollmentIDWithBraces@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJQEBG@Z; SystemSettings::WorkAccess::CEnrollmentHelper::SetEnrollmentIDWithBraces(ushort const * const)
0x18004883e  mov     ebx, eax
0x180048840  test    eax, eax
0x180048842  js      loc_180048AF7
0x180048848  mov     ecx, [rsp+110h+var_E0]
0x18004884c  call    ?SetEnrollmentType@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJW4EnrollmentEnrollType@@@Z; SystemSettings::WorkAccess::CEnrollmentHelper::SetEnrollmentType(EnrollmentEnrollType)
0x180048851  mov     ebx, eax
0x180048853  test    eax, eax
0x180048855  js      loc_180048ADD
0x18004885b  mov     ecx, [rsp+110h+var_E0]
0x18004885f  mov     eax, 1
0x180048864  shl     rax, cl
0x180048867  test    rax, 4000040h
0x18004886d  jz      short loc_1800488C0
0x18004886f  mov     [rbp+57h+psz], rsi
0x180048873  xor     edx, edx
0x180048875  lea     rcx, [rbp+57h+psz]
0x180048879  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004887e  lea     rcx, [rbp+57h+psz]; StringSid
0x180048882  call    ?GetCurrentUserSidString@@YAJPEAPEAG@Z; GetCurrentUserSidString(ushort * *)
0x180048887  mov     ebx, eax
0x180048889  test    eax, eax
0x18004888b  js      loc_180048A82
0x180048891  mov     rbx, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x180048898  mov     rcx, [rbp+57h+psz]; psz
0x18004889c  call    cs:__imp_SysAllocString
0x1800488a3  nop     dword ptr [rax+rax+00h]
0x1800488a8  mov     rdx, rax; unsigned __int16 *
0x1800488ab  lea     rcx, [rbx+28h]; this
0x1800488af  call    ?Assign@_bstr_t@@QEAAXPEAG@Z; _bstr_t::Assign(ushort *)
0x1800488b4  nop
0x1800488b5  lea     rcx, [rbp+57h+psz]
0x1800488b9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800488be  jmp     short loc_180048913
0x1800488c0  mov     [rbp+57h+var_C0], rsi
0x1800488c4  mov     rdi, [rsp+110h+var_E8]
0x1800488c9  mov     rax, [rdi]
0x1800488cc  mov     rbx, [rax+70h]
0x1800488d0  xor     edx, edx
0x1800488d2  lea     rcx, [rbp+57h+var_C0]
0x1800488d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800488db  lea     rdx, [rbp+57h+var_C0]
0x1800488df  mov     rcx, rdi
0x1800488e2  mov     rax, rbx
0x1800488e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488ea  mov     ebx, eax
0x1800488ec  test    eax, eax
0x1800488ee  js      loc_180048AB9
0x1800488f4  mov     rcx, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x1800488fb  add     rcx, 28h ; '('; this
0x1800488ff  mov     rdx, [rbp+57h+var_C0]; unsigned __int16 *
0x180048903  call    ?Assign@_bstr_t@@QEAAXPEAG@Z; _bstr_t::Assign(ushort *)
0x180048908  nop
0x180048909  lea     rcx, [rbp+57h+var_C0]
0x18004890d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180048912  nop
0x180048913  lea     rcx, [rbp+57h+var_A8]
0x180048917  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004891c  nop
0x18004891d  lea     rcx, [rsp+110h+var_F0]
0x180048922  jmp     loc_180048A2B
0x180048927  cmp     cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A, rsi; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x18004892e  jz      loc_180048A30
0x180048934  mov     [rsp+110h+sourceString], rsi
0x180048939  mov     rdi, [rsp+110h+var_E8]
0x18004893e  mov     rax, [rdi]
0x180048941  mov     rbx, [rax+20h]
0x180048945  xor     edx, edx
0x180048947  lea     rcx, [rsp+110h+sourceString]
0x18004894c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180048951  lea     rdx, [rsp+110h+sourceString]
0x180048956  mov     rcx, rdi
0x180048959  mov     rax, rbx
0x18004895c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048961  mov     ebx, eax
0x180048963  test    eax, eax
0x180048965  js      loc_180048B49
0x18004896b  mov     r8, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x180048972  test    r8, r8
0x180048975  jz      short loc_1800489A2
0x180048977  mov     rcx, [rsp+110h+sourceString]; sourceString
0x18004897c  mov     rdx, r14
0x18004897f  inc     rdx; length
0x180048982  cmp     [rcx+rdx*2], si
0x180048986  jnz     short loc_18004897F
0x180048988  add     r8, 18h; string
0x18004898c  call    cs:__imp_WindowsCreateString
0x180048993  nop     dword ptr [rax+rax+00h]
0x180048998  mov     ebx, eax
0x18004899a  test    eax, eax
0x18004899c  js      loc_180048B1F
0x1800489a2  mov     rdx, [rsp+110h+sourceString]
0x1800489a7  lea     rcx, [rbp+57h+var_68]
0x1800489ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800489b0  nop
0x1800489b1  mov     r8, rax
0x1800489b4  lea     rcx, [rbp+57h+var_48]
0x1800489b8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@G$$QEAV10@@Z; std::operator+<ushort>(ushort,std::wstring &&)
0x1800489bd  nop
0x1800489be  mov     rdx, rax
0x1800489c1  lea     rcx, [rbp+57h+var_88]
0x1800489c5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@G@Z; std::operator+<ushort>(std::wstring &&,ushort)
0x1800489ca  nop
0x1800489cb  lea     rcx, [rbp+57h+var_48]
0x1800489cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800489d4  nop
0x1800489d5  lea     rcx, [rbp+57h+var_68]
0x1800489d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800489de  lea     rcx, [rbp+57h+var_88]
0x1800489e2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800489e7  mov     r8, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x1800489ee  test    r8, r8
0x1800489f1  jz      short loc_180048A1C
0x1800489f3  mov     rdx, r14
0x1800489f6  inc     rdx; length
0x1800489f9  cmp     [rax+rdx*2], si
0x1800489fd  jnz     short loc_1800489F6
0x1800489ff  add     r8, 20h ; ' '; string
0x180048a03  mov     rcx, rax; sourceString
0x180048a06  call    cs:__imp_WindowsCreateString
0x180048a0d  nop     dword ptr [rax+rax+00h]
0x180048a12  mov     ebx, eax
0x180048a14  test    eax, eax
0x180048a16  js      loc_180048B26
0x180048a1c  lea     rcx, [rbp+57h+var_88]
0x180048a20  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048a25  nop
0x180048a26  lea     rcx, [rsp+110h+sourceString]
0x180048a2b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180048a30  mov     rdi, [rbp+57h+var_D0]
0x180048a34  mov     rax, [rdi]
0x180048a37  mov     rbx, [rax+18h]
0x180048a3b  lea     rcx, [rsp+110h+var_E8]
0x180048a40  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048a45  lea     rdx, [rsp+110h+var_E8]
0x180048a4a  mov     rcx, rdi
0x180048a4d  mov     rax, rbx
0x180048a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a55  test    eax, eax
0x180048a57  jz      loc_180048763
0x180048a5d  lea     rcx, [rbp+57h+var_B0]
0x180048a61  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048a66  nop
0x180048a67  lea     rcx, [rsp+110h+var_E8]
0x180048a6c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048a71  nop
0x180048a72  lea     rcx, [rbp+57h+var_D0]
0x180048a76  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048a7b  xor     eax, eax
0x180048a7d  jmp     loc_180048BA7
0x180048a82  mov     rcx, [rbp+5Fh]; this
0x180048a86  mov     r9d, eax; char *
0x180048a89  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180048a90  mov     edx, 0CDh; void *
0x180048a95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048a9a  nop
0x180048a9b  lea     rcx, [rbp+57h+psz]
0x180048a9f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180048aa4  nop
0x180048aa5  lea     rcx, [rbp+57h+var_A8]
0x180048aa9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048aae  nop
0x180048aaf  lea     rcx, [rsp+110h+var_F0]
0x180048ab4  jmp     loc_180048B67
  ... truncated ...
```
