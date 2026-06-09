# UnenrollAsyncImpl

- ea: `0x180069a94`
- end: `0x180069da9`
- name: `UnenrollAsyncImpl`
- size: `789`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005b7b8`
- `0x180069a50`

## callees

- `0x180004eb0`
- `0x18000539c`
- `0x180017b70`
- `0x180018508`
- `0x180018738`
- `0x180038c94`
- `0x180041bd0`
- `0x18004ac2c`
- `0x18004ac9c`
- `0x18004ace8`
- `0x18005a0dc`
- `0x180069a94`
- `0x180069db0`
- `0x18006a698`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180069cf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180069cf8`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180069ad7`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180069ad7`
- `RPCRT4!UuidFromStringW` at `0x180069ae5`
- `RPCRT4!UuidFromStringW` at `0x180069b8f`
- `RPCRT4!UuidFromStringW` at `0x180069ae5`
- `RPCRT4!UuidFromStringW` at `0x180069b8f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180069b67`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180069b67`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180069c3a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180069c3a`
- `dmEnrollEngine!GetEnrollmentType` at `0x180069b16`
- `dmEnrollEngine!GetEnrollmentType` at `0x180069bb6`
- `dmEnrollEngine!GetEnrollmentType` at `0x180069b16`
- `dmEnrollEngine!GetEnrollmentType` at `0x180069bb6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall UnenrollAsyncImpl(OLECHAR *lpValueName, __int64 a2, __int64 a3)
{
  HRESULT result; // eax
  int EnrollmentType; // ebx
  LSTATUS ValueW; // eax
  int v9; // eax
  int CallingProcess; // eax
  HSTRING *v11; // rdi
  _DWORD *v12; // rax
  __int64 v13; // r8
  std::_Ref_count_base *v14; // rbx
  int v15; // edi
  int pdwType; // [rsp+20h] [rbp-E0h]
  _DWORD v17[4]; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING *string[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 pcbData; // [rsp+60h] [rbp-A0h] BYREF
  GUID iid; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 StringUuid[2]; // [rsp+80h] [rbp-80h] BYREF
  GUID v22; // [rsp+84h] [rbp-7Ch]
  HSTRING *v23; // [rsp+98h] [rbp-68h]
  std::_Ref_count_base *v24; // [rsp+A0h] [rbp-60h]
  WCHAR sourceString[264]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  iid = 0;
  if ( *lpValueName == 123 )
    result = IIDFromString(lpValueName, &iid);
  else
    result = UuidFromStringW(lpValueName, &iid);
  if ( result < 0 )
    return result;
  v17[0] = 0;
  *(GUID *)string = iid;
  EnrollmentType = GetEnrollmentType(string, v17);
  if ( EnrollmentType < 0 )
  {
    LODWORD(pcbData) = 78;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Enrollments\\Substitute",
               lpValueName,
               2u,
               0,
               StringUuid,
               (LPDWORD)&pcbData);
    EnrollmentType = ValueW;
    if ( ValueW > 0 )
      EnrollmentType = (unsigned __int16)ValueW | 0x80070000;
    if ( EnrollmentType < 0 )
      return EnrollmentType;
    EnrollmentType = UuidFromStringW(StringUuid, &iid);
    if ( EnrollmentType < 0 )
      return EnrollmentType;
    *(GUID *)string = iid;
    EnrollmentType = GetEnrollmentType(string, v17);
    if ( EnrollmentType < 0 )
      return EnrollmentType;
  }
  if ( v17[0] == 3 )
  {
    v9 = AccessCheckSecureAssessment();
LABEL_21:
    EnrollmentType = v9;
    goto LABEL_22;
  }
  if ( v17[0] != 13 )
  {
    if ( v17[0] == 23 )
      v9 = AccessCheckForCapability();
    else
      v9 = Windows::Internal::Management::Enrollment::Enroller::AccessCheck(v17[0]);
    goto LABEL_21;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment>::GetImpl'::`2'::impl) )
  {
    *(GUID *)string = iid;
    result = UnenrollDualEnrollment((struct _GUID *)string);
    if ( result < 0 )
      return result;
    goto LABEL_23;
  }
LABEL_22:
  if ( EnrollmentType < 0 )
    return EnrollmentType;
LABEL_23:
  RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Enrollments\\Substitute", lpValueName);
  CallingProcess = GetCallingProcess(a2, sourceString);
  if ( CallingProcess < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2AF,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\enroller.cpp",
      (const char *)(unsigned int)CallingProcess,
      pdwType);
  *(_OWORD *)string = 0;
  wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
    string,
    0);
  v11 = string[0];
  if ( !string[0] )
  {
    v12 = operator new(0x18u);
    *(_OWORD *)v12 = 0;
    v12[2] = 1;
    v12[3] = 1;
    *(_QWORD *)v12 = &std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::`vftable';
    *((_QWORD *)v12 + 2) = 0;
    *(_QWORD *)&pcbData = v12 + 4;
    *((_QWORD *)&pcbData + 1) = v12;
    std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
      string,
      &pcbData);
    if ( *((_QWORD *)&pcbData + 1) )
      std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&pcbData + 1));
    v11 = string[0];
  }
  EnrollmentType = WindowsCreateString(sourceString, 0x104u, v11);
  if ( EnrollmentType < 0 )
  {
    if ( string[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)string[1]);
    return EnrollmentType;
  }
  *(_DWORD *)StringUuid = v17[0];
  v22 = iid;
  v14 = (std::_Ref_count_base *)string[1];
  if ( string[1] )
    _InterlockedAdd((volatile signed __int32 *)string[1] + 2, 1u);
  v23 = v11;
  v24 = v14;
  LODWORD(pcbData) = 3;
  *(_QWORD *)((char *)&pcbData + 4) = 128;
  v15 = Windows::Internal::MakeAsyncAction_Microsoft::WRL::AsyncCausalityOptions__UnenrollAsyncOperationName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows::Internal::ComTaskPoolHandler__lambda_9392614d0feddfd4e6683ca6cd2e3a39___(
          &pcbData,
          a3,
          v13,
          StringUuid);
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  return v15;
}

```

## disassembly

```asm
0x180069a94  push    rbp
0x180069a96  push    rbx
0x180069a97  push    rsi
0x180069a98  push    rdi
0x180069a99  push    r14
0x180069a9b  lea     rbp, [rsp-1F0h]
0x180069aa3  sub     rsp, 2F0h
0x180069aaa  mov     rax, cs:__security_cookie
0x180069ab1  xor     rax, rsp
0x180069ab4  mov     [rbp+210h+var_30], rax
0x180069abb  mov     r14, r8
0x180069abe  mov     rsi, rdx
0x180069ac1  mov     rdi, rcx
0x180069ac4  xorps   xmm0, xmm0
0x180069ac7  movups  xmmword ptr [rsp+310h+iid.Data1], xmm0
0x180069acc  lea     rdx, [rsp+310h+iid]; Uuid
0x180069ad1  cmp     word ptr [rcx], 7Bh ; '{'
0x180069ad5  jnz     short loc_180069AE5
0x180069ad7  call    cs:__imp_IIDFromString
0x180069ade  nop     dword ptr [rax+rax+00h]
0x180069ae3  jmp     short loc_180069AF1
0x180069ae5  call    cs:__imp_UuidFromStringW
0x180069aec  nop     dword ptr [rax+rax+00h]
0x180069af1  test    eax, eax
0x180069af3  js      loc_180069D8B
0x180069af9  mov     [rsp+310h+var_2D0], 0
0x180069b01  movaps  xmm0, xmmword ptr [rsp+310h+iid.Data1]
0x180069b06  movdqa  xmmword ptr [rsp+310h+string], xmm0
0x180069b0c  lea     rdx, [rsp+310h+var_2D0]
0x180069b11  lea     rcx, [rsp+310h+string]
0x180069b16  call    cs:__imp_GetEnrollmentType
0x180069b1d  nop     dword ptr [rax+rax+00h]
0x180069b22  mov     ebx, eax
0x180069b24  test    eax, eax
0x180069b26  jns     loc_180069BCF
0x180069b2c  mov     [rsp+310h+var_2B0], 4Eh ; 'N'
0x180069b34  lea     rax, [rsp+310h+var_2B0]
0x180069b39  mov     [rsp+310h+pcbData], rax; pcbData
0x180069b3e  lea     rax, [rbp+210h+StringUuid]
0x180069b42  mov     [rsp+310h+pvData], rax; pvData
0x180069b47  mov     [rsp+310h+pdwType], 0; pdwType
0x180069b50  mov     r9d, 2; dwFlags
0x180069b56  mov     r8, rdi; lpValue
0x180069b59  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Enrollments\\Subst"...
0x180069b60  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180069b67  call    cs:__imp_RegGetValueW
0x180069b6e  nop     dword ptr [rax+rax+00h]
0x180069b73  mov     ebx, eax
0x180069b75  test    eax, eax
0x180069b77  jle     short loc_180069B82
0x180069b79  movzx   ebx, ax
0x180069b7c  or      ebx, 80070000h
0x180069b82  test    ebx, ebx
0x180069b84  js      short loc_180069BC8
0x180069b86  lea     rdx, [rsp+310h+iid]; Uuid
0x180069b8b  lea     rcx, [rbp+210h+StringUuid]; StringUuid
0x180069b8f  call    cs:__imp_UuidFromStringW
0x180069b96  nop     dword ptr [rax+rax+00h]
0x180069b9b  mov     ebx, eax
0x180069b9d  test    eax, eax
0x180069b9f  js      short loc_180069BC8
0x180069ba1  movaps  xmm0, xmmword ptr [rsp+310h+iid.Data1]
0x180069ba6  movdqa  xmmword ptr [rsp+310h+string], xmm0
0x180069bac  lea     rdx, [rsp+310h+var_2D0]
0x180069bb1  lea     rcx, [rsp+310h+string]
0x180069bb6  call    cs:__imp_GetEnrollmentType
0x180069bbd  nop     dword ptr [rax+rax+00h]
0x180069bc2  mov     ebx, eax
0x180069bc4  test    eax, eax
0x180069bc6  jns     short loc_180069BCF
0x180069bc8  mov     eax, ebx
0x180069bca  jmp     loc_180069D8B
0x180069bcf  mov     ecx, [rsp+310h+var_2D0]
0x180069bd3  cmp     ecx, 3
0x180069bd6  jz      short loc_180069C1E
0x180069bd8  cmp     ecx, 0Dh
0x180069bdb  jz      short loc_180069BF0
0x180069bdd  cmp     ecx, 17h
0x180069be0  jz      short loc_180069BE9
0x180069be2  call    ?AccessCheck@Enroller@Enrollment@Management@Internal@Windows@@SAJW4EnrollmentEnrollType@@@Z; Windows::Internal::Management::Enrollment::Enroller::AccessCheck(EnrollmentEnrollType)
0x180069be7  jmp     short loc_180069C23
0x180069be9  call    ?AccessCheckForCapability@@YAJW4EnrollmentEnrollType@@PEBG@Z; AccessCheckForCapability(EnrollmentEnrollType,ushort const *)
0x180069bee  jmp     short loc_180069C23
0x180069bf0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment> `wil::Feature<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment>::GetImpl(void)'::`2'::impl
0x180069bf7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment>::__private_IsEnabled(void)
0x180069bfc  test    al, al
0x180069bfe  jz      short loc_180069C25
0x180069c00  movaps  xmm0, xmmword ptr [rsp+310h+iid.Data1]
0x180069c05  movdqa  xmmword ptr [rsp+310h+string], xmm0
0x180069c0b  lea     rcx, [rsp+310h+string]; struct _GUID
0x180069c10  call    ?UnenrollDualEnrollment@@YAJU_GUID@@@Z; UnenrollDualEnrollment(_GUID)
0x180069c15  test    eax, eax
0x180069c17  jns     short loc_180069C29
0x180069c19  jmp     loc_180069D8B
0x180069c1e  call    ?AccessCheckSecureAssessment@@YAJW4EnrollmentEnrollType@@@Z; AccessCheckSecureAssessment(EnrollmentEnrollType)
0x180069c23  mov     ebx, eax
0x180069c25  test    ebx, ebx
0x180069c27  js      short loc_180069BC8
0x180069c29  mov     r8, rdi; lpValueName
0x180069c2c  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Enrollments\\Subst"...
0x180069c33  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180069c3a  call    cs:__imp_RegDeleteKeyValueW
0x180069c41  nop     dword ptr [rax+rax+00h]
0x180069c46  lea     rdx, [rbp+210h+sourceString]
0x180069c4a  mov     rcx, rsi
0x180069c4d  call    GetCallingProcess
0x180069c52  mov     rcx, [rbp+218h]; this
0x180069c59  test    eax, eax
0x180069c5b  jns     short loc_180069C71
0x180069c5d  mov     r9d, eax; char *
0x180069c60  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180069c67  mov     edx, 2AFh; void *
0x180069c6c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180069c71  xorps   xmm1, xmm1
0x180069c74  movdqu  xmmword ptr [rsp+310h+string], xmm1
0x180069c7a  xor     edx, edx
0x180069c7c  lea     rcx, [rsp+310h+string]
0x180069c81  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x180069c86  mov     esi, 1
0x180069c8b  mov     rdi, [rsp+310h+string]
0x180069c90  test    rdi, rdi
0x180069c93  jnz     short loc_180069CEC
0x180069c95  lea     ecx, [rsi+17h]; Size
0x180069c98  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180069c9d  mov     qword ptr [rsp+310h+var_2B0], rax
0x180069ca2  xorps   xmm0, xmm0
0x180069ca5  movups  xmmword ptr [rax], xmm0
0x180069ca8  mov     [rax+8], esi
0x180069cab  mov     [rax+0Ch], esi
0x180069cae  lea     rcx, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::`vftable'
0x180069cb5  mov     [rax], rcx
0x180069cb8  lea     rcx, [rax+10h]
0x180069cbc  mov     [rcx], rdi
0x180069cbf  mov     qword ptr [rsp+310h+var_2B0], rcx
0x180069cc4  mov     [rsp+310h+var_2A8], rax
0x180069cc9  lea     rdx, [rsp+310h+var_2B0]
0x180069cce  lea     rcx, [rsp+310h+string]
0x180069cd3  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x180069cd8  mov     rcx, [rsp+310h+var_2A8]; this
0x180069cdd  test    rcx, rcx
0x180069ce0  jz      short loc_180069CE7
0x180069ce2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180069ce7  mov     rdi, [rsp+310h+string]
0x180069cec  mov     r8, rdi; string
0x180069cef  mov     edx, 104h; length
0x180069cf4  lea     rcx, [rbp+210h+sourceString]; sourceString
0x180069cf8  call    cs:__imp_WindowsCreateString
0x180069cff  nop     dword ptr [rax+rax+00h]
0x180069d04  mov     ebx, eax
0x180069d06  test    eax, eax
0x180069d08  jns     short loc_180069D22
0x180069d0a  mov     rcx, [rsp+310h+string+8]; this
0x180069d0f  test    rcx, rcx
0x180069d12  jz      loc_180069BC8
0x180069d18  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180069d1d  jmp     loc_180069BC8
0x180069d22  mov     eax, [rsp+310h+var_2D0]
0x180069d26  mov     dword ptr [rbp+210h+StringUuid], eax
0x180069d29  movaps  xmm0, xmmword ptr [rsp+310h+iid.Data1]
0x180069d2e  movdqu  [rbp+210h+var_28C], xmm0
0x180069d33  mov     rbx, [rsp+310h+string+8]
0x180069d38  test    rbx, rbx
0x180069d3b  jz      short loc_180069D41
0x180069d3d  lock add [rbx+8], esi
0x180069d41  mov     [rbp+210h+var_278], rdi
0x180069d45  mov     [rbp+210h+var_270], rbx
0x180069d49  mov     [rsp+310h+var_2B0], 3
0x180069d51  mov     qword ptr [rsp+310h+var_2B0+4], 80h
0x180069d5a  lea     r9, [rbp+210h+StringUuid]
0x180069d5e  mov     rdx, r14
0x180069d61  lea     rcx, [rsp+310h+var_2B0]
0x180069d66  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__UnenrollAsyncOperationName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_9392614d0feddfd4e6683ca6cd2e3a39___
0x180069d6b  mov     edi, eax
0x180069d6d  mov     rcx, [rbp+210h+var_270]; this
0x180069d71  test    rcx, rcx
0x180069d74  jz      short loc_180069D7C
0x180069d76  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180069d7b  nop
0x180069d7c  test    rbx, rbx
0x180069d7f  jz      short loc_180069D89
0x180069d81  mov     rcx, rbx; this
0x180069d84  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180069d89  mov     eax, edi
0x180069d8b  mov     rcx, [rbp+210h+var_30]
0x180069d92  xor     rcx, rsp; StackCookie
0x180069d95  call    __security_check_cookie
0x180069d9a  add     rsp, 2F0h
0x180069da1  pop     r14
0x180069da3  pop     rdi
0x180069da4  pop     rsi
0x180069da5  pop     rbx
0x180069da6  pop     rbp
0x180069da7  retn
```
