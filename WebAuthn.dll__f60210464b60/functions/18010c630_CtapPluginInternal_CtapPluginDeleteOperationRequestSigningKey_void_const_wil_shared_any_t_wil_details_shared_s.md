# CtapPluginInternal::CtapPluginDeleteOperationRequestSigningKey(void * const,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>)

- ea: `0x18010c630`
- end: `0x18010c8ca`
- name: `?CtapPluginDeleteOperationRequestSigningKey@CtapPluginInternal@@YAJQEAXV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180043ad4`

## callees

- `0x180017620`
- `0x18001ee7c`
- `0x180020584`
- `0x180020614`
- `0x180036da4`
- `0x180042e40`
- `0x180046ac0`
- `0x18006f750`
- `0x18008f720`
- `0x18010c630`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x18010c7a0`
- `ncrypt!NCryptOpenKey` at `0x18010c7a0`
- `ncrypt!NCryptOpenStorageProvider` at `0x18010c6fb`
- `ncrypt!NCryptOpenStorageProvider` at `0x18010c6fb`
- `ncrypt!NCryptDeleteKey` at `0x18010c80f`
- `ncrypt!NCryptDeleteKey` at `0x18010c80f`

## string_xrefs

- `0x18010c6a7`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010c70f`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010c7b4`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010c823`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CtapPluginInternal::CtapPluginDeleteOperationRequestSigningKey(
        __int64 a1,
        std::_Ref_count_base **a2)
{
  std::_Ref_count_base *v4; // rdi
  int v5; // edx
  int v6; // r8d
  int v7; // eax
  unsigned int v8; // edi
  __int64 result; // rax
  SECURITY_STATUS v10; // eax
  unsigned int v11; // edi
  const WCHAR *v12; // rdi
  SECURITY_STATUS v13; // eax
  unsigned int v14; // edi
  const char *v15; // r9
  SECURITY_STATUS v16; // eax
  unsigned int v17; // edi
  wil::reg::reg_view_details *dwFlags; // [rsp+20h] [rbp-58h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-58h]
  DWORD dwFlagsb; // [rsp+20h] [rbp-58h]
  _BYTE v21[8]; // [rsp+30h] [rbp-48h] BYREF
  std::_Ref_count_base *v22[2]; // [rsp+38h] [rbp-40h] BYREF
  int v23[4]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+90h] [rbp+18h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+98h] [rbp+20h] BYREF

  *(_OWORD *)v23 = 0;
  v4 = *a2;
  if ( *a2 )
    v4 = *(std::_Ref_count_base **)v4;
  *(_OWORD *)v22 = 0;
  std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::operator=(
    v23,
    v22);
  if ( v22[1] )
    std::_Ref_count_base::_Decref(v22[1]);
  v22[0] = v4;
  LODWORD(dwFlags) = 268435462;
  v7 = wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>,wil::err_returncode_policy>(
         (int)v22,
         v5,
         v6,
         (int)v23,
         dwFlags);
  v8 = v7;
  if ( v7 >= 0 )
  {
    phProvider = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &phProvider,
      0);
    v10 = NCryptOpenStorageProvider(&phProvider, 0, 0);
    v11 = v10;
    if ( v10 >= 0 )
    {
      try
      {
        wil::impersonate_token(v21, a1);
        phKey = 0;
        if ( *(_QWORD *)v23 )
          v12 = **(const WCHAR ***)v23;
        else
          v12 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
          &phKey,
          0);
        v13 = NCryptOpenKey(phProvider, &phKey, v12, 0, 0);
        v14 = v13;
        if ( v13 >= 0 )
        {
          v16 = NCryptDeleteKey(phKey, 0);
          v17 = v16;
          if ( v16 >= 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v21);
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
            std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(v23);
            std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(a2);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xF1C,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)(unsigned int)v16,
              dwFlagsb);
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v21);
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
            std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(v23);
            std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(a2);
            result = v17;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF1A,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)v13,
            dwFlagsb);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v21);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
          std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(v23);
          std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(a2);
          result = v14;
        }
      }
      catch ( ... )
      {
        LODWORD(phProvider) = wil::details::in1diag3::Return_CaughtException(
                                retaddr,
                                (void *)0xF20,
                                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                v15);
        std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(a2);
        return (unsigned int)phProvider;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF14,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)v10,
        dwFlagsa);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(v23);
      std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(a2);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF11,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)v7,
      dwFlagsa);
    std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(v23);
    std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(a2);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18010c630  mov     [rsp+arg_8], rdx
0x18010c635  push    rbx
0x18010c636  push    rsi
0x18010c637  push    rdi
0x18010c638  sub     rsp, 60h
0x18010c63c  mov     rbx, rdx
0x18010c63f  mov     rsi, rcx
0x18010c642  xorps   xmm0, xmm0
0x18010c645  xorps   xmm1, xmm1
0x18010c648  movdqu  xmmword ptr [rsp+78h+var_30], xmm1
0x18010c64e  mov     rdi, [rdx]
0x18010c651  test    rdi, rdi
0x18010c654  jz      short loc_18010C659
0x18010c656  mov     rdi, [rdi]
0x18010c659  movdqu  xmmword ptr [rsp+78h+var_40], xmm0
0x18010c65f  lea     rdx, [rsp+78h+var_40]
0x18010c664  lea     rcx, [rsp+78h+var_30]
0x18010c669  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &&)
0x18010c66e  mov     rcx, [rsp+78h+var_40+8]; this
0x18010c673  test    rcx, rcx
0x18010c676  jz      short loc_18010C67D
0x18010c678  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18010c67d  mov     [rsp+78h+var_40], rdi
0x18010c682  mov     [rsp+78h+dwFlags], 10000006h; int
0x18010c68a  lea     r9, [rsp+78h+var_30]; int
0x18010c68f  lea     rcx, [rsp+78h+var_40]; int
0x18010c694  call    ??$get_value_with_type@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &,ulong)
0x18010c699  mov     edi, eax
0x18010c69b  test    eax, eax
0x18010c69d  jns     short loc_18010C6D3
0x18010c69f  mov     rcx, [rsp+78h]; this
0x18010c6a4  mov     r9d, eax; char *
0x18010c6a7  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010c6ae  mov     edx, 0F11h; void *
0x18010c6b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010c6b8  nop
0x18010c6b9  lea     rcx, [rsp+78h+var_30]
0x18010c6be  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x18010c6c3  nop
0x18010c6c4  mov     rcx, rbx
0x18010c6c7  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x18010c6cc  mov     eax, edi
0x18010c6ce  jmp     loc_18010C8C2
0x18010c6d3  mov     [rsp+78h+phProvider], 0
0x18010c6df  xor     edx, edx
0x18010c6e1  lea     rcx, [rsp+78h+phProvider]
0x18010c6e9  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18010c6ee  xor     r8d, r8d; dwFlags
0x18010c6f1  xor     edx, edx; pszProviderName
0x18010c6f3  lea     rcx, [rsp+78h+phProvider]; phProvider
0x18010c6fb  call    cs:__imp_NCryptOpenStorageProvider
0x18010c701  mov     edi, eax
0x18010c703  test    eax, eax
0x18010c705  jns     short loc_18010C749
0x18010c707  mov     rcx, [rsp+78h]; this
0x18010c70c  mov     r9d, eax; char *
0x18010c70f  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010c716  mov     edx, 0F14h; void *
0x18010c71b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010c720  nop
0x18010c721  lea     rcx, [rsp+78h+phProvider]
0x18010c729  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18010c72e  nop
0x18010c72f  lea     rcx, [rsp+78h+var_30]
0x18010c734  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x18010c739  nop
0x18010c73a  mov     rcx, rbx
0x18010c73d  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x18010c742  mov     eax, edi
0x18010c744  jmp     loc_18010C8C2
0x18010c749  mov     rdx, rsi
0x18010c74c  lea     rcx, [rsp+78h+var_48]
0x18010c751  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x18010c756  mov     [rsp+78h+phKey], 0
0x18010c762  mov     rax, qword ptr [rsp+78h+var_30]
0x18010c767  test    rax, rax
0x18010c76a  jz      short loc_18010C771
0x18010c76c  mov     rdi, [rax]
0x18010c76f  jmp     short loc_18010C773
0x18010c771  xor     edi, edi
0x18010c773  xor     edx, edx
0x18010c775  lea     rcx, [rsp+78h+phKey]
0x18010c77d  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18010c782  mov     [rsp+78h+dwFlags], 0; int
0x18010c78a  xor     r9d, r9d; dwLegacyKeySpec
0x18010c78d  mov     r8, rdi; pszKeyName
0x18010c790  lea     rdx, [rsp+78h+phKey]; phKey
0x18010c798  mov     rcx, [rsp+78h+phProvider]; hProvider
0x18010c7a0  call    cs:__imp_NCryptOpenKey
0x18010c7a6  mov     edi, eax
0x18010c7a8  test    eax, eax
0x18010c7aa  jns     short loc_18010C805
0x18010c7ac  mov     rcx, [rsp+78h]; this
0x18010c7b1  mov     r9d, eax; char *
0x18010c7b4  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010c7bb  mov     edx, 0F1Ah; void *
0x18010c7c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010c7c5  lea     rcx, [rsp+78h+phKey]
0x18010c7cd  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18010c7d2  lea     rcx, [rsp+78h+var_48]
0x18010c7d7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18010c7dc  nop
0x18010c7dd  lea     rcx, [rsp+78h+phProvider]
0x18010c7e5  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18010c7ea  nop
0x18010c7eb  lea     rcx, [rsp+78h+var_30]
0x18010c7f0  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x18010c7f5  nop
0x18010c7f6  mov     rcx, rbx
0x18010c7f9  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x18010c7fe  mov     eax, edi
0x18010c800  jmp     loc_18010C8C2
0x18010c805  xor     edx, edx; dwFlags
0x18010c807  mov     rcx, [rsp+78h+phKey]; hKey
0x18010c80f  call    cs:__imp_NCryptDeleteKey
0x18010c815  mov     edi, eax
0x18010c817  test    eax, eax
0x18010c819  jns     short loc_18010C871
0x18010c81b  mov     rcx, [rsp+78h]; this
0x18010c820  mov     r9d, eax; char *
0x18010c823  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010c82a  mov     edx, 0F1Ch; void *
0x18010c82f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010c834  lea     rcx, [rsp+78h+phKey]
0x18010c83c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18010c841  lea     rcx, [rsp+78h+var_48]
0x18010c846  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18010c84b  nop
0x18010c84c  lea     rcx, [rsp+78h+phProvider]
0x18010c854  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18010c859  nop
0x18010c85a  lea     rcx, [rsp+78h+var_30]
0x18010c85f  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x18010c864  nop
0x18010c865  mov     rcx, rbx
0x18010c868  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x18010c86d  mov     eax, edi
0x18010c86f  jmp     short loc_18010C8C2
0x18010c871  lea     rcx, [rsp+78h+phKey]
0x18010c879  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18010c87e  lea     rcx, [rsp+78h+var_48]
0x18010c883  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18010c888  nop
0x18010c889  lea     rcx, [rsp+78h+phProvider]
0x18010c891  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18010c896  nop
0x18010c897  lea     rcx, [rsp+78h+var_30]
0x18010c89c  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x18010c8a1  nop
0x18010c8a2  mov     rcx, rbx
0x18010c8a5  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x18010c8aa  xor     eax, eax
0x18010c8ac  jmp     short loc_18010C8C2
0x18010c8ae  mov     rcx, [rsp+78h+arg_8]
0x18010c8b6  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x18010c8bb  mov     eax, dword ptr [rsp+78h+phProvider]
0x18010c8c2  add     rsp, 60h
0x18010c8c6  pop     rdi
0x18010c8c7  pop     rsi
0x18010c8c8  pop     rbx
0x18010c8c9  retn
```
