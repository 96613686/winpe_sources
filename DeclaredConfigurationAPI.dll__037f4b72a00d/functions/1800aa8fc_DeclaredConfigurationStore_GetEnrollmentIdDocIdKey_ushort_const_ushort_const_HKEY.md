# DeclaredConfigurationStore_GetEnrollmentIdDocIdKey(ushort const *,ushort const *,HKEY__ * *)

- ea: `0x1800aa8fc`
- end: `0x1800aab5a`
- name: `?DeclaredConfigurationStore_GetEnrollmentIdDocIdKey@@YAJPEBG0PEAPEAUHKEY__@@@Z`
- size: `606`
- prototype: `__int64 __fastcall(OLECHAR *psz, const unsigned __int16 *, HKEY *)`
- caller_count: `7`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800a9e90`
- `0x1800aa100`
- `0x1800aa434`
- `0x1800aab60`
- `0x1800ab0f0`
- `0x1800ab610`
- `0x1800abbe0`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x18001d0b0`
- `0x18004d1ac`
- `0x180058b08`
- `0x1800725e0`
- `0x1800a0264`
- `0x1800aa8fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800aaa53`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800aaa53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aaa61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aaac6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aaa61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aaac6`
- `RPCRT4!UuidFromStringW` at `0x1800aa92f`
- `RPCRT4!UuidFromStringW` at `0x1800aa92f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800aa994`
- `OLEAUT32!__imp_SysAllocString` at `0x1800aa9c9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800aaab5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800aa994`
- `OLEAUT32!__imp_SysAllocString` at `0x1800aa9c9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800aaab5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aaaab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aaaab`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800aaa73`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800aaa73`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x1800aaa32`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x1800aaa32`
- `dmEnrollEngine!GetEnrollmentType` at `0x1800aa970`
- `dmEnrollEngine!GetEnrollmentType` at `0x1800aa970`

## string_xrefs

- `0x1800aa947`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`
- `0x1800aa9e3`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`
- `0x1800aab1e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DeclaredConfigurationStore_GetEnrollmentIdDocIdKey(
        OLECHAR *psz,
        const unsigned __int16 *a2,
        HKEY *a3)
{
  RPC_STATUS EnrollmentIdSidStateDocIdKey; // ebx
  __int64 v7; // rdx
  int EnrollmentType; // eax
  BSTR v9; // rax
  BSTR v10; // rax
  OLECHAR *v11; // rdi
  int CurrentUserSid; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  BSTR v15; // rbx
  HLOCAL hMem; // [rsp+20h] [rbp-60h] BYREF
  int v18; // [rsp+28h] [rbp-58h] BYREF
  UUID v19; // [rsp+30h] [rbp-50h] BYREF
  BSTR v20; // [rsp+40h] [rbp-40h] BYREF
  BSTR v21; // [rsp+48h] [rbp-38h]
  int v22; // [rsp+50h] [rbp-30h]
  int v23; // [rsp+54h] [rbp-2Ch]
  UUID Uuid; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  Uuid = 0;
  EnrollmentIdSidStateDocIdKey = UuidFromStringW(psz, &Uuid);
  if ( EnrollmentIdSidStateDocIdKey >= 0 )
  {
    v18 = 63;
    v19 = Uuid;
    EnrollmentType = GetEnrollmentType(&v19, &v18);
    EnrollmentIdSidStateDocIdKey = EnrollmentType;
    if ( EnrollmentType == -2147024894 )
    {
      EnrollmentIdSidStateDocIdKey = -2102525946;
LABEL_7:
      v7 = 65;
      goto LABEL_3;
    }
    if ( EnrollmentType < 0 )
      goto LABEL_7;
    v9 = SysAllocString(psz);
    if ( !v9 )
    {
      EnrollmentIdSidStateDocIdKey = -2147024882;
      v7 = 67;
      goto LABEL_3;
    }
    v21 = 0;
    v22 = 0;
    v20 = v9;
    v23 = v18;
    v10 = SysAllocString(L"Device");
    v11 = v10;
    if ( !v10 )
    {
      EnrollmentIdSidStateDocIdKey = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
        (const char *)0x8007000ELL,
        (int)hMem);
LABEL_28:
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v20);
      return (unsigned int)EnrollmentIdSidStateDocIdKey;
    }
    v21 = v10;
    v22 = 0;
    *(_QWORD *)&v19.Data1 = 0;
    EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                                     (struct DeclaredConfigurationScopeData *)&v20,
                                     a2,
                                     a3,
                                     0);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      hMem = 0;
      CurrentUserSid = DmGetCurrentUserSid((unsigned __int16 **)&hMem);
      EnrollmentIdSidStateDocIdKey = CurrentUserSid;
      if ( CurrentUserSid < 0 )
      {
        v13 = 98;
LABEL_25:
        v14 = (unsigned int)CurrentUserSid;
        goto LABEL_26;
      }
      if ( !(unsigned int)_o__wcsicmp(L"S-1-5-18", hMem) )
      {
        LocalFree(hMem);
        hMem = 0;
        EnrollmentIdSidStateDocIdKey = DmGetActiveUserSid((unsigned __int16 **)&hMem);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless>::GetImpl'::`2'::impl)
          && EnrollmentIdSidStateDocIdKey == -2102788088 )
        {
          EnrollmentIdSidStateDocIdKey = -2147023728;
LABEL_20:
          v14 = (unsigned int)EnrollmentIdSidStateDocIdKey;
          v13 = 113;
LABEL_26:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v13,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
            (const char *)v14,
            (int)hMem);
          goto LABEL_27;
        }
        if ( EnrollmentIdSidStateDocIdKey < 0 )
          goto LABEL_20;
      }
      SysFreeString(v11);
      v15 = SysAllocString((const OLECHAR *)hMem);
      v21 = v15;
      LocalFree(hMem);
      hMem = 0;
      if ( !v15 )
      {
        EnrollmentIdSidStateDocIdKey = -2147024882;
        v14 = 2147942414LL;
        v13 = 123;
        goto LABEL_26;
      }
      v22 = 1;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v19,
        0);
      CurrentUserSid = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                         (struct DeclaredConfigurationScopeData *)&v20,
                         a2,
                         a3,
                         0);
      EnrollmentIdSidStateDocIdKey = CurrentUserSid;
      if ( CurrentUserSid < 0 )
      {
        v13 = 135;
        goto LABEL_25;
      }
    }
LABEL_27:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v19);
    goto LABEL_28;
  }
  v7 = 57;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
    (const char *)(unsigned int)EnrollmentIdSidStateDocIdKey,
    (int)hMem);
  return (unsigned int)EnrollmentIdSidStateDocIdKey;
}

```

## disassembly

```asm
0x1800aa8fc  push    rbp
0x1800aa8fe  push    rbx
0x1800aa8ff  push    rsi
0x1800aa900  push    rdi
0x1800aa901  push    r14
0x1800aa903  mov     rbp, rsp
0x1800aa906  sub     rsp, 80h
0x1800aa90d  mov     rax, cs:__security_cookie
0x1800aa914  xor     rax, rsp
0x1800aa917  mov     [rbp+var_10], rax
0x1800aa91b  mov     r14, r8
0x1800aa91e  mov     rsi, rdx
0x1800aa921  mov     rdi, rcx
0x1800aa924  xorps   xmm0, xmm0
0x1800aa927  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x1800aa92b  lea     rdx, [rbp+Uuid]; Uuid
0x1800aa92f  call    cs:__imp_UuidFromStringW
0x1800aa935  mov     ebx, eax
0x1800aa937  test    eax, eax
0x1800aa939  jns     short loc_1800AA958
0x1800aa93b  mov     edx, 39h ; '9'; void *
0x1800aa940  mov     rcx, [rbp+28h]; this
0x1800aa944  mov     r9d, ebx; char *
0x1800aa947  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800aa94e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa953  jmp     loc_1800AAB3E
0x1800aa958  mov     [rbp+var_58], 3Fh ; '?'
0x1800aa95f  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x1800aa963  movdqa  [rbp+var_50], xmm0
0x1800aa968  lea     rdx, [rbp+var_58]
0x1800aa96c  lea     rcx, [rbp+var_50]
0x1800aa970  call    cs:__imp_GetEnrollmentType
0x1800aa976  mov     ebx, eax
0x1800aa978  cmp     eax, 80070002h
0x1800aa97d  jnz     short loc_1800AA986
0x1800aa97f  mov     ebx, 82AE0006h
0x1800aa984  jmp     short loc_1800AA98A
0x1800aa986  test    eax, eax
0x1800aa988  jns     short loc_1800AA991
0x1800aa98a  mov     edx, 41h ; 'A'
0x1800aa98f  jmp     short loc_1800AA940
0x1800aa991  mov     rcx, rdi; psz
0x1800aa994  call    cs:__imp_SysAllocString
0x1800aa99a  test    rax, rax
0x1800aa99d  jnz     short loc_1800AA9A9
0x1800aa99f  mov     ebx, 8007000Eh
0x1800aa9a4  lea     edx, [rax+43h]
0x1800aa9a7  jmp     short loc_1800AA940
0x1800aa9a9  mov     [rbp+var_38], 0
0x1800aa9b1  mov     [rbp+var_30], 0
0x1800aa9b8  mov     [rbp+var_40], rax
0x1800aa9bc  mov     eax, [rbp+var_58]
0x1800aa9bf  mov     [rbp+var_2C], eax
0x1800aa9c2  lea     rcx, aDevice_2; "Device"
0x1800aa9c9  call    cs:__imp_SysAllocString
0x1800aa9cf  mov     rdi, rax
0x1800aa9d2  test    rax, rax
0x1800aa9d5  jnz     short loc_1800AA9F7
0x1800aa9d7  mov     rcx, [rbp+28h]; this
0x1800aa9db  mov     ebx, 8007000Eh
0x1800aa9e0  mov     r9d, ebx; char *
0x1800aa9e3  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800aa9ea  lea     edx, [rax+49h]; void *
0x1800aa9ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa9f2  jmp     loc_1800AAB35
0x1800aa9f7  mov     [rbp+var_38], rdi
0x1800aa9fb  mov     [rbp+var_30], 0
0x1800aaa02  mov     qword ptr [rbp+var_50], 0
0x1800aaa0a  xor     r9d, r9d; int
0x1800aaa0d  mov     r8, r14; HKEY *
0x1800aaa10  mov     rdx, rsi; unsigned __int16 *
0x1800aaa13  lea     rcx, [rbp+var_40]; struct DeclaredConfigurationScopeData *
0x1800aaa17  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x1800aaa1c  mov     ebx, eax
0x1800aaa1e  test    eax, eax
0x1800aaa20  jns     loc_1800AAB2B
0x1800aaa26  mov     [rbp+hMem], 0
0x1800aaa2e  lea     rcx, [rbp+hMem]
0x1800aaa32  call    cs:__imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x1800aaa38  mov     ebx, eax
0x1800aaa3a  test    eax, eax
0x1800aaa3c  jns     short loc_1800AAA48
0x1800aaa3e  mov     edx, 62h ; 'b'
0x1800aaa43  jmp     loc_1800AAB17
0x1800aaa48  mov     rdx, [rbp+hMem]
0x1800aaa4c  lea     rcx, aS1518; "S-1-5-18"
0x1800aaa53  call    cs:__imp__o__wcsicmp
0x1800aaa59  test    eax, eax
0x1800aaa5b  jnz     short loc_1800AAAA8
0x1800aaa5d  mov     rcx, [rbp+hMem]; hMem
0x1800aaa61  call    cs:__imp_LocalFree
0x1800aaa67  mov     [rbp+hMem], 0
0x1800aaa6f  lea     rcx, [rbp+hMem]
0x1800aaa73  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800aaa79  mov     ebx, eax
0x1800aaa7b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless> `wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless>::GetImpl(void)'::`2'::impl
0x1800aaa82  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless>::__private_IsEnabled(void)
0x1800aaa87  test    al, al
0x1800aaa89  jz      short loc_1800AAA9A
0x1800aaa8b  cmp     ebx, 82AA0008h
0x1800aaa91  jnz     short loc_1800AAA9A
0x1800aaa93  mov     ebx, 80070490h
0x1800aaa98  jmp     short loc_1800AAA9E
0x1800aaa9a  test    ebx, ebx
0x1800aaa9c  jns     short loc_1800AAAA8
0x1800aaa9e  mov     r9d, ebx
0x1800aaaa1  mov     edx, 71h ; 'q'
0x1800aaaa6  jmp     short loc_1800AAB1A
0x1800aaaa8  mov     rcx, rdi; bstrString
0x1800aaaab  call    cs:__imp_SysFreeString
0x1800aaab1  mov     rcx, [rbp+hMem]; psz
0x1800aaab5  call    cs:__imp_SysAllocString
0x1800aaabb  mov     rbx, rax
0x1800aaabe  mov     [rbp+var_38], rax
0x1800aaac2  mov     rcx, [rbp+hMem]; hMem
0x1800aaac6  call    cs:__imp_LocalFree
0x1800aaacc  mov     [rbp+hMem], 0
0x1800aaad4  test    rbx, rbx
0x1800aaad7  jnz     short loc_1800AAAE8
0x1800aaad9  mov     ebx, 8007000Eh
0x1800aaade  mov     r9d, ebx
0x1800aaae1  mov     edx, 7Bh ; '{'
0x1800aaae6  jmp     short loc_1800AAB1A
0x1800aaae8  mov     [rbp+var_30], 1
0x1800aaaef  xor     edx, edx
0x1800aaaf1  lea     rcx, [rbp+var_50]
0x1800aaaf5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800aaafa  xor     r9d, r9d; int
0x1800aaafd  mov     r8, r14; HKEY *
0x1800aab00  mov     rdx, rsi; unsigned __int16 *
0x1800aab03  lea     rcx, [rbp+var_40]; struct DeclaredConfigurationScopeData *
0x1800aab07  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x1800aab0c  mov     ebx, eax
0x1800aab0e  test    eax, eax
0x1800aab10  jns     short loc_1800AAB2B
0x1800aab12  mov     edx, 87h; void *
0x1800aab17  mov     r9d, eax; char *
0x1800aab1a  mov     rcx, [rbp+28h]; this
0x1800aab1e  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800aab25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aab2a  nop
0x1800aab2b  lea     rcx, [rbp+var_50]
0x1800aab2f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800aab34  nop
0x1800aab35  lea     rcx, [rbp+var_40]; this
0x1800aab39  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x1800aab3e  mov     eax, ebx
0x1800aab40  mov     rcx, [rbp+var_10]
0x1800aab44  xor     rcx, rsp; StackCookie
0x1800aab47  call    __security_check_cookie
0x1800aab4c  add     rsp, 80h
0x1800aab53  pop     r14
0x1800aab55  pop     rdi
0x1800aab56  pop     rsi
0x1800aab57  pop     rbx
0x1800aab58  pop     rbp
0x1800aab59  retn
```
