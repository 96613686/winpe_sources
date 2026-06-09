# UnenrollAsyncImpl

- ea: `0x18006890c`
- end: `0x180068bf0`
- name: `UnenrollAsyncImpl`
- size: `740`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005ad24`
- `0x1800688d0`

## callees

- `0x180004d50`
- `0x18000523c`
- `0x18001736c`
- `0x180019b4c`
- `0x180019f1c`
- `0x180039990`
- `0x180042168`
- `0x18004aa4c`
- `0x18004aab4`
- `0x18004ab00`
- `0x180059730`
- `0x18006890c`
- `0x180068bf8`
- `0x1800694a0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180068b46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180068b46`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18006894f`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18006894f`
- `RPCRT4!UuidFromStringW` at `0x180068957`
- `RPCRT4!UuidFromStringW` at `0x1800689ef`
- `RPCRT4!UuidFromStringW` at `0x180068957`
- `RPCRT4!UuidFromStringW` at `0x1800689ef`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800689cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800689cd`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180068a8e`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180068a8e`
- `dmEnrollEngine!GetEnrollmentType` at `0x180068982`
- `dmEnrollEngine!GetEnrollmentType` at `0x180068a10`
- `dmEnrollEngine!GetEnrollmentType` at `0x180068982`
- `dmEnrollEngine!GetEnrollmentType` at `0x180068a10`

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
      (void *)0x2C3,
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
0x18006890c  push    rbp
0x18006890e  push    rbx
0x18006890f  push    rsi
0x180068910  push    rdi
0x180068911  push    r14
0x180068913  lea     rbp, [rsp-1F0h]
0x18006891b  sub     rsp, 2F0h
0x180068922  mov     rax, cs:__security_cookie
0x180068929  xor     rax, rsp
0x18006892c  mov     [rbp+210h+var_30], rax
0x180068933  mov     r14, r8
0x180068936  mov     rsi, rdx
0x180068939  mov     rdi, rcx
0x18006893c  xorps   xmm0, xmm0
0x18006893f  movups  xmmword ptr [rsp+310h+iid.Data1], xmm0
0x180068944  lea     rdx, [rsp+310h+iid]; Uuid
0x180068949  cmp     word ptr [rcx], 7Bh ; '{'
0x18006894d  jnz     short loc_180068957
0x18006894f  call    cs:__imp_IIDFromString
0x180068955  jmp     short loc_18006895D
0x180068957  call    cs:__imp_UuidFromStringW
0x18006895d  test    eax, eax
0x18006895f  js      loc_180068BD3
0x180068965  mov     [rsp+310h+var_2D0], 0
0x18006896d  movaps  xmm0, xmmword ptr [rsp+310h+iid.Data1]
0x180068972  movdqa  xmmword ptr [rsp+310h+string], xmm0
0x180068978  lea     rdx, [rsp+310h+var_2D0]
0x18006897d  lea     rcx, [rsp+310h+string]
0x180068982  call    cs:__imp_GetEnrollmentType
0x180068988  mov     ebx, eax
0x18006898a  test    eax, eax
0x18006898c  jns     loc_180068A23
0x180068992  mov     [rsp+310h+var_2B0], 4Eh ; 'N'
0x18006899a  lea     rax, [rsp+310h+var_2B0]
0x18006899f  mov     [rsp+310h+pcbData], rax; pcbData
0x1800689a4  lea     rax, [rbp+210h+StringUuid]
0x1800689a8  mov     [rsp+310h+pvData], rax; pvData
0x1800689ad  mov     [rsp+310h+pdwType], 0; pdwType
0x1800689b6  mov     r9d, 2; dwFlags
0x1800689bc  mov     r8, rdi; lpValue
0x1800689bf  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Enrollments\\Subst"...
0x1800689c6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800689cd  call    cs:__imp_RegGetValueW
0x1800689d3  mov     ebx, eax
0x1800689d5  test    eax, eax
0x1800689d7  jle     short loc_1800689E2
0x1800689d9  movzx   ebx, ax
0x1800689dc  or      ebx, 80070000h
0x1800689e2  test    ebx, ebx
0x1800689e4  js      short loc_180068A1C
0x1800689e6  lea     rdx, [rsp+310h+iid]; Uuid
0x1800689eb  lea     rcx, [rbp+210h+StringUuid]; StringUuid
0x1800689ef  call    cs:__imp_UuidFromStringW
0x1800689f5  mov     ebx, eax
0x1800689f7  test    eax, eax
0x1800689f9  js      short loc_180068A1C
0x1800689fb  movaps  xmm0, xmmword ptr [rsp+310h+iid.Data1]
0x180068a00  movdqa  xmmword ptr [rsp+310h+string], xmm0
0x180068a06  lea     rdx, [rsp+310h+var_2D0]
0x180068a0b  lea     rcx, [rsp+310h+string]
0x180068a10  call    cs:__imp_GetEnrollmentType
0x180068a16  mov     ebx, eax
0x180068a18  test    eax, eax
0x180068a1a  jns     short loc_180068A23
0x180068a1c  mov     eax, ebx
0x180068a1e  jmp     loc_180068BD3
0x180068a23  mov     ecx, [rsp+310h+var_2D0]
0x180068a27  cmp     ecx, 3
0x180068a2a  jz      short loc_180068A72
0x180068a2c  cmp     ecx, 0Dh
0x180068a2f  jz      short loc_180068A44
0x180068a31  cmp     ecx, 17h
0x180068a34  jz      short loc_180068A3D
0x180068a36  call    ?AccessCheck@Enroller@Enrollment@Management@Internal@Windows@@SAJW4EnrollmentEnrollType@@@Z; Windows::Internal::Management::Enrollment::Enroller::AccessCheck(EnrollmentEnrollType)
0x180068a3b  jmp     short loc_180068A77
0x180068a3d  call    ?AccessCheckForCapability@@YAJW4EnrollmentEnrollType@@PEBG@Z; AccessCheckForCapability(EnrollmentEnrollType,ushort const *)
0x180068a42  jmp     short loc_180068A77
0x180068a44  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment> `wil::Feature<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment>::GetImpl(void)'::`2'::impl
0x180068a4b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment>::__private_IsEnabled(void)
0x180068a50  test    al, al
0x180068a52  jz      short loc_180068A79
0x180068a54  movaps  xmm0, xmmword ptr [rsp+310h+iid.Data1]
0x180068a59  movdqa  xmmword ptr [rsp+310h+string], xmm0
0x180068a5f  lea     rcx, [rsp+310h+string]; struct _GUID
0x180068a64  call    ?UnenrollDualEnrollment@@YAJU_GUID@@@Z; UnenrollDualEnrollment(_GUID)
0x180068a69  test    eax, eax
0x180068a6b  jns     short loc_180068A7D
0x180068a6d  jmp     loc_180068BD3
0x180068a72  call    ?AccessCheckSecureAssessment@@YAJW4EnrollmentEnrollType@@@Z; AccessCheckSecureAssessment(EnrollmentEnrollType)
0x180068a77  mov     ebx, eax
0x180068a79  test    ebx, ebx
0x180068a7b  js      short loc_180068A1C
0x180068a7d  mov     r8, rdi; lpValueName
0x180068a80  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Enrollments\\Subst"...
0x180068a87  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180068a8e  call    cs:__imp_RegDeleteKeyValueW
0x180068a94  lea     rdx, [rbp+210h+sourceString]
0x180068a98  mov     rcx, rsi
0x180068a9b  call    GetCallingProcess
0x180068aa0  mov     rcx, [rbp+218h]; this
0x180068aa7  test    eax, eax
0x180068aa9  jns     short loc_180068ABF
0x180068aab  mov     r9d, eax; char *
0x180068aae  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180068ab5  mov     edx, 2C3h; void *
0x180068aba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180068abf  xorps   xmm1, xmm1
0x180068ac2  movdqu  xmmword ptr [rsp+310h+string], xmm1
0x180068ac8  xor     edx, edx
0x180068aca  lea     rcx, [rsp+310h+string]
0x180068acf  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x180068ad4  mov     esi, 1
0x180068ad9  mov     rdi, [rsp+310h+string]
0x180068ade  test    rdi, rdi
0x180068ae1  jnz     short loc_180068B3A
0x180068ae3  lea     ecx, [rsi+17h]; Size
0x180068ae6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180068aeb  mov     qword ptr [rsp+310h+var_2B0], rax
0x180068af0  xorps   xmm0, xmm0
0x180068af3  movups  xmmword ptr [rax], xmm0
0x180068af6  mov     [rax+8], esi
0x180068af9  mov     [rax+0Ch], esi
0x180068afc  lea     rcx, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::`vftable'
0x180068b03  mov     [rax], rcx
0x180068b06  lea     rcx, [rax+10h]
0x180068b0a  mov     [rcx], rdi
0x180068b0d  mov     qword ptr [rsp+310h+var_2B0], rcx
0x180068b12  mov     [rsp+310h+var_2A8], rax
0x180068b17  lea     rdx, [rsp+310h+var_2B0]
0x180068b1c  lea     rcx, [rsp+310h+string]
0x180068b21  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x180068b26  mov     rcx, [rsp+310h+var_2A8]; this
0x180068b2b  test    rcx, rcx
0x180068b2e  jz      short loc_180068B35
0x180068b30  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180068b35  mov     rdi, [rsp+310h+string]
0x180068b3a  mov     r8, rdi; string
0x180068b3d  mov     edx, 104h; length
0x180068b42  lea     rcx, [rbp+210h+sourceString]; sourceString
0x180068b46  call    cs:__imp_WindowsCreateString
0x180068b4c  mov     ebx, eax
0x180068b4e  test    eax, eax
0x180068b50  jns     short loc_180068B6A
0x180068b52  mov     rcx, [rsp+310h+string+8]; this
0x180068b57  test    rcx, rcx
0x180068b5a  jz      loc_180068A1C
0x180068b60  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180068b65  jmp     loc_180068A1C
0x180068b6a  mov     eax, [rsp+310h+var_2D0]
0x180068b6e  mov     dword ptr [rbp+210h+StringUuid], eax
0x180068b71  movaps  xmm0, xmmword ptr [rsp+310h+iid.Data1]
0x180068b76  movdqu  [rbp+210h+var_28C], xmm0
0x180068b7b  mov     rbx, [rsp+310h+string+8]
0x180068b80  test    rbx, rbx
0x180068b83  jz      short loc_180068B89
0x180068b85  lock add [rbx+8], esi
0x180068b89  mov     [rbp+210h+var_278], rdi
0x180068b8d  mov     [rbp+210h+var_270], rbx
0x180068b91  mov     [rsp+310h+var_2B0], 3
0x180068b99  mov     qword ptr [rsp+310h+var_2B0+4], 80h
0x180068ba2  lea     r9, [rbp+210h+StringUuid]
0x180068ba6  mov     rdx, r14
0x180068ba9  lea     rcx, [rsp+310h+var_2B0]
0x180068bae  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__UnenrollAsyncOperationName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_9392614d0feddfd4e6683ca6cd2e3a39___
0x180068bb3  mov     edi, eax
0x180068bb5  mov     rcx, [rbp+210h+var_270]; this
0x180068bb9  test    rcx, rcx
0x180068bbc  jz      short loc_180068BC4
0x180068bbe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180068bc3  nop
0x180068bc4  test    rbx, rbx
0x180068bc7  jz      short loc_180068BD1
0x180068bc9  mov     rcx, rbx; this
0x180068bcc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180068bd1  mov     eax, edi
0x180068bd3  mov     rcx, [rbp+210h+var_30]
0x180068bda  xor     rcx, rsp; StackCookie
0x180068bdd  call    __security_check_cookie
0x180068be2  add     rsp, 2F0h
0x180068be9  pop     r14
0x180068beb  pop     rdi
0x180068bec  pop     rsi
0x180068bed  pop     rbx
0x180068bee  pop     rbp
0x180068bef  retn
```
