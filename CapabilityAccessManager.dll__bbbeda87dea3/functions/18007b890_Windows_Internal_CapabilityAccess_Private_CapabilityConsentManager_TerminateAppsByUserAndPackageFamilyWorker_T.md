# Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::TerminateAppsByUserAndPackageFamilyWorker(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x18007b890`
- end: `0x18007bb50`
- name: `?TerminateAppsByUserAndPackageFamilyWorker@CapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `704`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x1800094c0`
- `0x180016450`
- `0x18001c3b4`
- `0x18001d00c`
- `0x180029408`
- `0x18002f260`
- `0x18004049c`
- `0x180042720`
- `0x180042fe8`
- `0x180065084`
- `0x180072b8c`
- `0x180072ba8`
- `0x18007b890`
- `0x18007bbb4`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18007b959`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18007bb26`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18007b959`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18007bb26`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18007b8ef`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18007b8ef`
- `RMCLIENT!HamFullTrustOpenPackageHandle` at `0x18007b9d6`
- `RMCLIENT!HamFullTrustOpenPackageHandle` at `0x18007b9d6`
- `RMCLIENT!HamFullTrustClosePackageHandle` at `0x18007ba8e`
- `RMCLIENT!HamFullTrustClosePackageHandle` at `0x18007ba8e`
- `RMCLIENT!HamFullTrustTerminatePackage` at `0x18007ba5e`
- `RMCLIENT!HamFullTrustTerminatePackage` at `0x18007ba5e`
- `RMCLIENT!HamConnectForFullTrust` at `0x18007b915`
- `RMCLIENT!HamConnectForFullTrust` at `0x18007b915`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::TerminateAppsByUserAndPackageFamilyWorker(
        PTP_CALLBACK_INSTANCE Instance,
        _QWORD *Context)
{
  int v3; // edi
  int v4; // eax
  __int64 v5; // r12
  unsigned int *i; // rsi
  unsigned int *v7; // r15
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // r10
  __int64 v13; // r8
  int v14; // eax
  __int64 v15; // r14
  const char *v16; // r9
  int v17; // [rsp+20h] [rbp-B8h]
  __int64 *v18; // [rsp+20h] [rbp-B8h]
  __int64 v19; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+38h] [rbp-A0h] BYREF
  PSID Sid; // [rsp+40h] [rbp-98h] BYREF
  _QWORD *v22; // [rsp+48h] [rbp-90h] BYREF
  __int128 v23; // [rsp+50h] [rbp-88h] BYREF
  __int64 v24; // [rsp+60h] [rbp-78h]
  int v25; // [rsp+68h] [rbp-70h]
  _BYTE v26[32]; // [rsp+70h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_cfc806497c6f3b00c985fb94e5feae7c_Traceguids);
  }
  v3 = RoInitialize(1);
  v25 = v3;
  v22 = Context;
  v19 = 0;
  v4 = HamConnectForFullTrust(
         tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::on_result,
         &v19);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0xF21,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentmanager.cpp",
      (const char *)(unsigned int)v4,
      v17);
    goto LABEL_8;
  }
  if ( v4 )
  {
LABEL_8:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long HamDisconnectForFullTrust(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long HamDisconnectForFullTrust(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
    std::unique_ptr<TerminateAppData>::~unique_ptr<TerminateAppData>(&v22);
    if ( v3 >= 0 )
      RoUninitialize();
    return;
  }
  try
  {
    Windows::Internal::CapabilityAccess::Private::GetSidFromSidString(&Sid);
    Windows::Internal::CapabilityAccess::Private::GetAllSessionIds(&v23);
    v15 = Context[4];
    v5 = Context[5];
LABEL_11:
    if ( v15 != v5 )
    {
      Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromFamilyNameAndUser(
        (__int64)v26,
        (__int64)Context,
        v15);
      v7 = (unsigned int *)*((_QWORD *)&v23 + 1);
      for ( i = (unsigned int *)v23; ; ++i )
      {
        if ( i == v7 )
        {
          std::wstring::_Tidy_deallocate(v26);
          v15 += 32;
          goto LABEL_11;
        }
        v20 = 0;
        v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
        v18 = &v20;
        v9 = HamFullTrustOpenPackageHandle(v19, v8, *i, Sid);
        if ( v9 < 0 )
          break;
        if ( !v9 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Context);
            v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
            WPP_SF_DSS(*(_QWORD *)(v12 + 16), v13, v11);
          }
          v14 = HamFullTrustTerminatePackage(v19, v20, 3, 6400);
          if ( v14 < 0 )
            wil::details::in1diag3::_Log_NtStatus(
              retaddr,
              (void *)0xF46,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentmanager.cpp",
              (const char *)(unsigned int)v14,
              (int)v18);
          v9 = HamFullTrustClosePackageHandle(v19, v20);
          if ( v9 < 0 )
          {
            v10 = 3911;
            goto LABEL_24;
          }
        }
LABEL_25:
        ;
      }
      v10 = 3895;
LABEL_24:
      wil::details::in1diag3::_Log_NtStatus(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentmanager.cpp",
        (const char *)(unsigned int)v9,
        (int)v18);
      goto LABEL_25;
    }
    if ( (_QWORD)v23 )
    {
      std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFFCuLL);
      v23 = 0;
      v24 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long HamDisconnectForFullTrust(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long HamDisconnectForFullTrust(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
    std::unique_ptr<TerminateAppData>::~unique_ptr<TerminateAppData>(&v22);
    if ( v3 >= 0 )
      RoUninitialize();
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xF4B,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentmanager.cpp",
      v16);
  }
}

```

## disassembly

```asm
0x18007b890  push    rbx
0x18007b892  push    rsi
0x18007b893  push    rdi
0x18007b894  push    r12
0x18007b896  push    r14
0x18007b898  push    r15
0x18007b89a  sub     rsp, 0A8h
0x18007b8a1  mov     rax, cs:__security_cookie
0x18007b8a8  xor     rax, rsp
0x18007b8ab  mov     [rsp+0D8h+var_48], rax
0x18007b8b3  mov     rbx, rdx
0x18007b8b6  lea     rax, WPP_GLOBAL_Control
0x18007b8bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b8c4  cmp     rcx, rax
0x18007b8c7  jz      short loc_18007B8EA
0x18007b8c9  test    byte ptr [rcx+1Ch], 1
0x18007b8cd  jz      short loc_18007B8EA
0x18007b8cf  cmp     byte ptr [rcx+19h], 5
0x18007b8d3  jb      short loc_18007B8EA
0x18007b8d5  mov     edx, 2Ch ; ','
0x18007b8da  lea     r8, WPP_cfc806497c6f3b00c985fb94e5feae7c_Traceguids
0x18007b8e1  mov     rcx, [rcx+10h]
0x18007b8e5  call    WPP_SF_
0x18007b8ea  mov     ecx, 1
0x18007b8ef  call    cs:__imp_RoInitialize
0x18007b8f5  mov     edi, eax
0x18007b8f7  mov     [rsp+0D8h+var_70], eax
0x18007b8fb  mov     [rsp+0D8h+var_90], rbx
0x18007b900  mov     [rsp+0D8h+var_A8], 0
0x18007b909  lea     rdx, [rsp+0D8h+var_A8]
0x18007b90e  lea     rcx, ?on_result@?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@EEAAXAEBUTipReportingInfo@@@Z; tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::on_result(TipReportingInfo const &)
0x18007b915  call    cs:__imp_HamConnectForFullTrust
0x18007b91b  mov     rcx, [rsp+0D8h]; this
0x18007b923  test    eax, eax
0x18007b925  jns     short loc_18007B93D
0x18007b927  mov     r9d, eax; char *
0x18007b92a  lea     r8, aOnecoreBaseDev_35; "onecore\\base\\devices\\cam\\core\\capa"...
0x18007b931  mov     edx, 0F21h; void *
0x18007b936  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18007b93b  jmp     short loc_18007B93F
0x18007b93d  jz      short loc_18007B965
0x18007b93f  lea     rcx, [rsp+0D8h+var_A8]
0x18007b944  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?HamDisconnectForFullTrust@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&HamDisconnectForFullTrust(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&HamDisconnectForFullTrust(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007b949  nop
0x18007b94a  lea     rcx, [rsp+0D8h+var_90]
0x18007b94f  call    ??1?$unique_ptr@UTerminateAppData@@U?$default_delete@UTerminateAppData@@@std@@@std@@QEAA@XZ; std::unique_ptr<TerminateAppData>::~unique_ptr<TerminateAppData>(void)
0x18007b954  nop
0x18007b955  test    edi, edi
0x18007b957  js      short loc_18007B960
0x18007b959  call    cs:__imp_RoUninitialize
0x18007b95f  nop
0x18007b960  jmp     loc_18007BB2F
0x18007b965  mov     rdx, rbx
0x18007b968  lea     rcx, [rsp+0D8h+Sid]; Sid
0x18007b96d  call    ?GetSidFromSidString@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::GetSidFromSidString(std::wstring const &)
0x18007b972  nop
0x18007b973  lea     rcx, [rsp+0D8h+var_88]
0x18007b978  call    ?GetAllSessionIds@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@KV?$allocator@K@std@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::GetAllSessionIds(void)
0x18007b97d  nop
0x18007b97e  mov     r14, [rbx+20h]
0x18007b982  mov     r12, [rbx+28h]
0x18007b986  cmp     r14, r12
0x18007b989  jz      loc_18007BAD4
0x18007b98f  mov     r8, r14
0x18007b992  mov     rdx, rbx
0x18007b995  lea     rcx, [rsp+0D8h+var_68]
0x18007b99a  call    ?GetPackageFullNameFromFamilyNameAndUser@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@0@Z; Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromFamilyNameAndUser(std::wstring const &,std::wstring const &)
0x18007b99f  mov     rsi, qword ptr [rsp+0D8h+var_88]
0x18007b9a4  mov     r15, qword ptr [rsp+0D8h+var_88+8]
0x18007b9a9  jmp     loc_18007BAB8
0x18007b9ae  mov     [rsp+0D8h+var_A0], 0
0x18007b9b7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b9bc  mov     rdx, rax
0x18007b9bf  lea     rax, [rsp+0D8h+var_A0]
0x18007b9c4  mov     [rsp+0D8h+var_B8], rax
0x18007b9c9  mov     r9, [rsp+0D8h+Sid]
0x18007b9ce  mov     r8d, [rsi]
0x18007b9d1  mov     rcx, [rsp+0D8h+var_A8]
0x18007b9d6  call    cs:__imp_HamFullTrustOpenPackageHandle
0x18007b9dc  test    eax, eax
0x18007b9de  jns     short loc_18007B9EA
0x18007b9e0  mov     edx, 0F37h
0x18007b9e5  jmp     loc_18007BA9D
0x18007b9ea  jnz     loc_18007BAB4
0x18007b9f0  mov     r10, cs:WPP_GLOBAL_Control
0x18007b9f7  lea     rax, WPP_GLOBAL_Control
0x18007b9fe  cmp     r10, rax
0x18007ba01  jz      short loc_18007BA48
0x18007ba03  test    byte ptr [r10+1Ch], 1
0x18007ba08  jz      short loc_18007BA48
0x18007ba0a  cmp     byte ptr [r10+19h], 4
0x18007ba0f  jb      short loc_18007BA48
0x18007ba11  mov     rcx, rbx
0x18007ba14  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007ba19  mov     r8, rax
0x18007ba1c  lea     rcx, [rsp+0D8h+var_68]
0x18007ba21  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007ba26  mov     edx, 2Dh ; '-'
0x18007ba2b  mov     [rsp+0D8h+var_B0], rax; __int64
0x18007ba30  mov     [rsp+0D8h+var_B8], r8; int
0x18007ba35  mov     r9d, [rsi]
0x18007ba38  lea     r8, WPP_cfc806497c6f3b00c985fb94e5feae7c_Traceguids
0x18007ba3f  mov     rcx, [r10+10h]; LoggerHandle
0x18007ba43  call    WPP_SF_DSS
0x18007ba48  mov     r9d, 1900h
0x18007ba4e  mov     r8d, 3
0x18007ba54  mov     rdx, [rsp+0D8h+var_A0]
0x18007ba59  mov     rcx, [rsp+0D8h+var_A8]
0x18007ba5e  call    cs:__imp_HamFullTrustTerminatePackage
0x18007ba64  test    eax, eax
0x18007ba66  jns     short loc_18007BA84
0x18007ba68  mov     rcx, [rsp+0D8h]; this
0x18007ba70  mov     r9d, eax; char *
0x18007ba73  lea     r8, aOnecoreBaseDev_35; "onecore\\base\\devices\\cam\\core\\capa"...
0x18007ba7a  mov     edx, 0F46h; void *
0x18007ba7f  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18007ba84  mov     rdx, [rsp+0D8h+var_A0]
0x18007ba89  mov     rcx, [rsp+0D8h+var_A8]
0x18007ba8e  call    cs:__imp_HamFullTrustClosePackageHandle
0x18007ba94  test    eax, eax
0x18007ba96  jns     short loc_18007BAB4
0x18007ba98  mov     edx, 0F47h; void *
0x18007ba9d  mov     r9d, eax; char *
0x18007baa0  lea     r8, aOnecoreBaseDev_35; "onecore\\base\\devices\\cam\\core\\capa"...
0x18007baa7  mov     rcx, [rsp+0D8h]; this
0x18007baaf  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18007bab4  add     rsi, 4
0x18007bab8  lea     rcx, [rsp+0D8h+var_68]
0x18007babd  cmp     rsi, r15
0x18007bac0  jnz     loc_18007B9AE
0x18007bac6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007bacb  add     r14, 20h ; ' '
0x18007bacf  jmp     loc_18007B986
0x18007bad4  mov     rcx, qword ptr [rsp+0D8h+var_88]
0x18007bad9  test    rcx, rcx
0x18007badc  jz      short loc_18007BB01
0x18007bade  mov     rdx, [rsp+0D8h+var_78]
0x18007bae3  sub     rdx, rcx
0x18007bae6  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18007baea  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007baef  xorps   xmm0, xmm0
0x18007baf2  movdqu  [rsp+0D8h+var_88], xmm0
0x18007baf8  mov     [rsp+0D8h+var_78], 0
0x18007bb01  lea     rcx, [rsp+0D8h+Sid]
0x18007bb06  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007bb0b  nop
0x18007bb0c  lea     rcx, [rsp+0D8h+var_A8]
0x18007bb11  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?HamDisconnectForFullTrust@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&HamDisconnectForFullTrust(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&HamDisconnectForFullTrust(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007bb16  nop
0x18007bb17  lea     rcx, [rsp+0D8h+var_90]
0x18007bb1c  call    ??1?$unique_ptr@UTerminateAppData@@U?$default_delete@UTerminateAppData@@@std@@@std@@QEAA@XZ; std::unique_ptr<TerminateAppData>::~unique_ptr<TerminateAppData>(void)
0x18007bb21  nop
0x18007bb22  test    edi, edi
0x18007bb24  js      short loc_18007BB2D
0x18007bb26  call    cs:__imp_RoUninitialize
0x18007bb2c  nop
0x18007bb2d  jmp     short $+2
0x18007bb2f  mov     rcx, [rsp+0D8h+var_48]
0x18007bb37  xor     rcx, rsp; StackCookie
0x18007bb3a  call    __security_check_cookie
0x18007bb3f  add     rsp, 0A8h
0x18007bb46  pop     r15
0x18007bb48  pop     r14
0x18007bb4a  pop     r12
0x18007bb4c  pop     rdi
0x18007bb4d  pop     rsi
0x18007bb4e  pop     rbx
0x18007bb4f  retn
```
