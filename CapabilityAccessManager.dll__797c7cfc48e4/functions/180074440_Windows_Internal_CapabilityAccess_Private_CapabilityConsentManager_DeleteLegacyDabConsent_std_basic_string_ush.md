# Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::DeleteLegacyDabConsent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180074440`
- end: `0x180074612`
- name: `?DeleteLegacyDabConsent@CapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `466`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180074618`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x18001c5fc`
- `0x1800210d4`
- `0x1800257a4`
- `0x180029408`
- `0x18002a564`
- `0x180043060`
- `0x1800473fc`
- `0x1800672c0`
- `0x180074440`
- `0x18007bbd8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800745be`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800745be`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180074488`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180074488`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::DeleteLegacyDabConsent(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 result; // rax
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rdx
  unsigned __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // r8
  const WCHAR *v19; // rax
  unsigned int v20; // eax
  __int64 v21; // [rsp+20h] [rbp-50h] BYREF
  _QWORD Src[2]; // [rsp+28h] [rbp-48h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-38h]
  unsigned __int64 v24; // [rsp+40h] [rbp-30h]
  _BYTE v25[16]; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v26; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  result = *(_QWORD *)(a1 + 72);
  if ( *(_QWORD *)(result + 472) )
  {
    v21 = 0;
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
    v7 = AppContainerDeriveSidFromMoniker(v6, &v21);
    if ( v7 >= 0 )
    {
      Windows::Internal::CapabilityAccess::Private::GetSidStringFromSid(v25, v21);
      std::wstring::wstring(Src, a2);
      if ( v23 >= v24 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
      }
      else
      {
        ++v23;
        v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
        *(_DWORD *)(v8 + 2 * v9) = 92;
      }
      v10 = std::_WChar_traits<unsigned short>::length(&stru_1800DBEE0);
      std::wstring::_Append<unsigned short>(Src, v11, v10);
      if ( v23 >= v24 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
      }
      else
      {
        ++v23;
        v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
        *(_DWORD *)(v12 + 2 * v13) = 92;
      }
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
      std::wstring::_Append<unsigned short>(Src, v14, v26);
      if ( v23 >= v24 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
      }
      else
      {
        ++v23;
        v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
        *(_DWORD *)(v15 + 2 * v16) = 92;
      }
      v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*(_QWORD *)(a1 + 72) + 456LL);
      std::wstring::_Append<unsigned short>(Src, v17, *(_QWORD *)(v18 + 472));
      v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
      v20 = RegDeleteTreeW(HKEY_USERS, v19);
      if ( v20 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0xB53,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentmanager.cpp",
          (const char *)v20,
          v21);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(v25);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB45,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentmanager.cpp",
        (const char *)(unsigned int)v7,
        v21);
    }
    return wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v21);
  }
  return result;
}

```

## disassembly

```asm
0x180074440  push    rbp
0x180074442  push    rbx
0x180074443  push    rdi
0x180074444  mov     rbp, rsp
0x180074447  sub     rsp, 70h
0x18007444b  mov     rax, cs:__security_cookie
0x180074452  xor     rax, rsp
0x180074455  mov     [rbp+var_8], rax
0x180074459  mov     rbx, rdx
0x18007445c  mov     rdi, rcx
0x18007445f  mov     rax, [rcx+48h]
0x180074463  cmp     qword ptr [rax+1D8h], 0
0x18007446b  jz      loc_1800745FE
0x180074471  mov     [rbp+var_50], 0
0x180074479  mov     rcx, r8
0x18007447c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180074481  lea     rdx, [rbp+var_50]
0x180074485  mov     rcx, rax
0x180074488  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x18007448e  mov     rcx, [rbp+18h]; this
0x180074492  test    eax, eax
0x180074494  jns     short loc_1800744AF
0x180074496  mov     r9d, eax; char *
0x180074499  lea     r8, aOnecoreBaseDev_35; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800744a0  mov     edx, 0B45h; void *
0x1800744a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800744aa  jmp     loc_1800745F5
0x1800744af  mov     rdx, [rbp+var_50]
0x1800744b3  lea     rcx, [rbp+var_28]
0x1800744b7  call    ?GetSidStringFromSid@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAX@Z; Windows::Internal::CapabilityAccess::Private::GetSidStringFromSid(void * const)
0x1800744bc  nop
0x1800744bd  mov     rdx, rbx
0x1800744c0  lea     rcx, [rbp+Src]
0x1800744c4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800744c9  nop
0x1800744ca  mov     rdx, [rbp+var_38]
0x1800744ce  lea     rcx, [rbp+Src]; Src
0x1800744d2  cmp     rdx, [rbp+var_30]
0x1800744d6  jnb     short loc_1800744EF
0x1800744d8  lea     rax, [rdx+1]
0x1800744dc  mov     [rbp+var_38], rax
0x1800744e0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800744e5  mov     ebx, 5Ch ; '\'
0x1800744ea  mov     [rax+rdx*2], ebx
0x1800744ed  jmp     short loc_1800744FC
0x1800744ef  mov     ebx, 5Ch ; '\'
0x1800744f4  mov     r9d, ebx
0x1800744f7  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1800744fc  lea     rcx, stru_1800DBEE0
0x180074503  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180074508  mov     r8, rax
0x18007450b  mov     rdx, rcx
0x18007450e  lea     rcx, [rbp+Src]
0x180074512  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180074517  mov     rdx, [rbp+var_38]
0x18007451b  lea     rcx, [rbp+Src]; Src
0x18007451f  cmp     rdx, [rbp+var_30]
0x180074523  jnb     short loc_18007453B
0x180074525  lea     rax, [rdx+1]
0x180074529  mov     [rbp+var_38], rax
0x18007452d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180074532  mov     dword ptr [rax+rdx*2], 5Ch ; '\'
0x180074539  jmp     short loc_180074543
0x18007453b  mov     r9d, ebx
0x18007453e  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180074543  lea     rcx, [rbp+var_28]
0x180074547  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007454c  mov     rdx, rax
0x18007454f  mov     r8, [rbp+var_18]
0x180074553  lea     rcx, [rbp+Src]
0x180074557  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18007455c  mov     rdx, [rbp+var_38]
0x180074560  lea     rcx, [rbp+Src]; Src
0x180074564  cmp     rdx, [rbp+var_30]
0x180074568  jnb     short loc_180074580
0x18007456a  lea     rax, [rdx+1]
0x18007456e  mov     [rbp+var_38], rax
0x180074572  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180074577  mov     dword ptr [rax+rdx*2], 5Ch ; '\'
0x18007457e  jmp     short loc_180074588
0x180074580  mov     r9d, ebx
0x180074583  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180074588  mov     r8, [rdi+48h]
0x18007458c  lea     rcx, [r8+1C8h]
0x180074593  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180074598  mov     r8, [r8+1D8h]
0x18007459f  mov     rdx, rax
0x1800745a2  lea     rcx, [rbp+Src]
0x1800745a6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800745ab  lea     rcx, [rbp+Src]
0x1800745af  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800745b4  mov     rdx, rax; lpSubKey
0x1800745b7  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800745be  call    cs:__imp_RegDeleteTreeW
0x1800745c4  mov     rcx, [rbp+18h]; this
0x1800745c8  test    eax, eax
0x1800745ca  jz      short loc_1800745E1
0x1800745cc  mov     r9d, eax; char *
0x1800745cf  lea     r8, aOnecoreBaseDev_35; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800745d6  mov     edx, 0B53h; void *
0x1800745db  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800745e0  nop
0x1800745e1  lea     rcx, [rbp+Src]
0x1800745e5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800745ea  nop
0x1800745eb  lea     rcx, [rbp+var_28]
0x1800745ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800745f4  nop
0x1800745f5  lea     rcx, [rbp+var_50]
0x1800745f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800745fe  mov     rcx, [rbp+var_8]
0x180074602  xor     rcx, rsp; StackCookie
0x180074605  call    __security_check_cookie
0x18007460a  add     rsp, 70h
0x18007460e  pop     rdi
0x18007460f  pop     rbx
0x180074610  pop     rbp
0x180074611  retn
```
