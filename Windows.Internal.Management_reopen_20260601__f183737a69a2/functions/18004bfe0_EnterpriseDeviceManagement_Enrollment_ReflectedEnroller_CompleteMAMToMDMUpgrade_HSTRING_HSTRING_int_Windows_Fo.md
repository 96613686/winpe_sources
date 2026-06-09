# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::CompleteMAMToMDMUpgrade(HSTRING__ *,HSTRING__ *,int,Windows::Foundation::IAsyncAction * *)

- ea: `0x18004bfe0`
- end: `0x18004c270`
- name: `?CompleteMAMToMDMUpgrade@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJPEAUHSTRING__@@0HPEAPEAUIAsyncAction@Foundation@Windows@@@Z`
- size: `656`
- prototype: `int(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *__hidden this, HSTRING, HSTRING, int, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004eb0`
- `0x180017298`
- `0x180017860`
- `0x180017b70`
- `0x180017bf0`
- `0x1800184e8`
- `0x180018738`
- `0x180038c94`
- `0x180041a98`
- `0x180042dec`
- `0x180044e80`
- `0x18004bfe0`
- `0x18005a0dc`
- `0x180095efc`
- `0x180096754`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c024`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c1b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c024`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c1b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004c12e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004c12e`
- `RPCRT4!UuidFromStringW` at `0x18004c043`
- `RPCRT4!UuidFromStringW` at `0x18004c1d6`
- `RPCRT4!UuidFromStringW` at `0x18004c043`
- `RPCRT4!UuidFromStringW` at `0x18004c1d6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18004c24f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18004c24f`
- `dmEnrollEngine!__imp_SwitchAADLinkedEnrollment` at `0x18004c206`
- `dmEnrollEngine!__imp_SwitchAADLinkedEnrollment` at `0x18004c206`
- `dmEnrollEngine!__imp_SetEnrollmentDormant` at `0x18004c083`
- `dmEnrollEngine!__imp_SetEnrollmentDormant` at `0x18004c083`
- `policymanager!EnterprisePolicyManagerStore_SetEnrollmentDormantState` at `0x18004c09c`
- `policymanager!EnterprisePolicyManagerStore_SetEnrollmentDormantState` at `0x18004c09c`

## pseudocode

```c
HRESULT __fastcall EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::CompleteMAMToMDMUpgrade(
        EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *this,
        HSTRING a2,
        HSTRING a3,
        int a4,
        struct Windows::Foundation::IAsyncAction **a5)
{
  unsigned __int16 *StringRawBuffer; // rdi
  HRESULT result; // eax
  CEnrollmentLogger *Logger; // rax
  bool v11; // sf
  int CallingProcess; // eax
  __int64 v13; // rax
  HRESULT v14; // ebx
  __int64 v15; // rax
  __int64 v16; // r8
  unsigned __int16 *v17; // rbx
  __int64 v18; // rax
  int lpData; // [rsp+20h] [rbp-E0h]
  int v20[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v21; // [rsp+40h] [rbp-C0h] BYREF
  UUID v22; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING *string[2]; // [rsp+60h] [rbp-A0h] BYREF
  UUID Uuid; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v25[48]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR sourceString[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v20[0] = a4;
  StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(a3, 0);
  Uuid = 0;
  result = UuidFromStringW(StringRawBuffer, &Uuid);
  if ( result < 0 )
    return result;
  Logger = CEnrollmentLogger::GetLogger();
  CEnrollmentLogger::LogCompleteMAMToMDMUpgrade(Logger, a4);
  if ( a4 )
  {
    *(UUID *)string = Uuid;
    result = SetEnrollmentDormant(string, 0);
    if ( result < 0 )
      return result;
    result = EnterprisePolicyManagerStore_SetEnrollmentDormantState(StringRawBuffer, 0);
  }
  else
  {
    v17 = (unsigned __int16 *)WindowsGetStringRawBuffer(a2, 0);
    *(_OWORD *)string = 0;
    result = UuidFromStringW(v17, (UUID *)string);
    if ( result < 0 )
      return result;
    v21 = *(_OWORD *)string;
    v22 = Uuid;
    result = SwitchAADLinkedEnrollment(&v22, &v21);
    if ( result < 0 )
      return result;
    v18 = -1;
    do
      ++v18;
    while ( v17[v18] );
    result = RegSetKeyValueW(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Enrollments\\Substitute",
               StringRawBuffer,
               1u,
               v17,
               2 * v18 + 2);
    v11 = result < 0;
    if ( result <= 0 )
      goto LABEL_6;
    result = (unsigned __int16)result | 0x80070000;
  }
  v11 = result < 0;
LABEL_6:
  if ( !v11 )
  {
    CallingProcess = GetCallingProcess(this, sourceString);
    if ( CallingProcess < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x348,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\enroller.cpp",
        (const char *)(unsigned int)CallingProcess,
        lpData);
    wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(string);
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
      string,
      0);
    if ( !(unsigned __int8)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(string) )
    {
      v13 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(&v22);
      std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
        string,
        v13);
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(&v22);
    }
    v14 = WindowsCreateString(sourceString, 0x104u, string[0]);
    if ( v14 >= 0 )
    {
      v15 = lambda_3ff306aa666b731442f985851ad8569b_::_lambda_3ff306aa666b731442f985851ad8569b_(v25, &Uuid, v20, string);
      LODWORD(v21) = 3;
      *(_QWORD *)((char *)&v21 + 4) = 128;
      v14 = Windows::Internal::MakeAsyncAction_Microsoft::WRL::AsyncCausalityOptions__CompleteMAMToMDMUpgradeOperationName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows::Internal::ComTaskPoolHandler__lambda_3ff306aa666b731442f985851ad8569b___(
              &v21,
              a5,
              v16,
              v15);
      lambda_9392614d0feddfd4e6683ca6cd2e3a39_::__lambda_9392614d0feddfd4e6683ca6cd2e3a39_(v25);
    }
    std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(string);
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x18004bfe0  push    rbp
0x18004bfe2  push    rbx
0x18004bfe3  push    rsi
0x18004bfe4  push    rdi
0x18004bfe5  push    r12
0x18004bfe7  push    r14
0x18004bfe9  push    r15
0x18004bfeb  lea     rbp, [rsp-1D0h]
0x18004bff3  sub     rsp, 2D0h
0x18004bffa  mov     rax, cs:__security_cookie
0x18004c001  xor     rax, rsp
0x18004c004  mov     [rbp+200h+var_40], rax
0x18004c00b  mov     r15, [rbp+200h+arg_20]
0x18004c012  mov     ebx, r9d
0x18004c015  mov     rsi, rdx
0x18004c018  mov     [rsp+300h+var_2D0], ebx
0x18004c01c  mov     r14, rcx
0x18004c01f  xor     edx, edx; length
0x18004c021  mov     rcx, r8; string
0x18004c024  call    cs:__imp_WindowsGetStringRawBuffer
0x18004c02b  nop     dword ptr [rax+rax+00h]
0x18004c030  xorps   xmm0, xmm0
0x18004c033  lea     rdx, [rsp+300h+Uuid]; Uuid
0x18004c038  mov     rcx, rax; StringUuid
0x18004c03b  mov     rdi, rax
0x18004c03e  movups  xmmword ptr [rsp+300h+Uuid.Data1], xmm0
0x18004c043  call    cs:__imp_UuidFromStringW
0x18004c04a  nop     dword ptr [rax+rax+00h]
0x18004c04f  xor     r12d, r12d
0x18004c052  test    eax, eax
0x18004c054  js      loc_18004C190
0x18004c05a  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18004c05f  mov     edx, ebx; int
0x18004c061  mov     rcx, rax; this
0x18004c064  call    ?LogCompleteMAMToMDMUpgrade@CEnrollmentLogger@@QEAAXH@Z; CEnrollmentLogger::LogCompleteMAMToMDMUpgrade(int)
0x18004c069  test    ebx, ebx
0x18004c06b  jz      loc_18004C1B2
0x18004c071  movaps  xmm0, xmmword ptr [rsp+300h+Uuid.Data1]
0x18004c076  lea     rcx, [rsp+300h+string]
0x18004c07b  xor     edx, edx
0x18004c07d  movdqa  xmmword ptr [rsp+300h+string], xmm0
0x18004c083  call    cs:__imp_SetEnrollmentDormant
0x18004c08a  nop     dword ptr [rax+rax+00h]
0x18004c08f  test    eax, eax
0x18004c091  js      loc_18004C190
0x18004c097  xor     edx, edx
0x18004c099  mov     rcx, rdi
0x18004c09c  call    cs:__imp_?EnterprisePolicyManagerStore_SetEnrollmentDormantState@@YAJPEBGH@Z; EnterprisePolicyManagerStore_SetEnrollmentDormantState(ushort const *,int)
0x18004c0a3  nop     dword ptr [rax+rax+00h]
0x18004c0a8  test    eax, eax
0x18004c0aa  js      loc_18004C190
0x18004c0b0  lea     rdx, [rbp+200h+sourceString]
0x18004c0b4  mov     rcx, r14
0x18004c0b7  call    GetCallingProcess
0x18004c0bc  test    eax, eax
0x18004c0be  jns     short loc_18004C0DB
0x18004c0c0  mov     rcx, [rbp+208h]; this
0x18004c0c7  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18004c0ce  mov     r9d, eax; char *
0x18004c0d1  mov     edx, 348h; void *
0x18004c0d6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004c0db  lea     rcx, [rsp+300h+string]
0x18004c0e0  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18004c0e5  xor     edx, edx
0x18004c0e7  lea     rcx, [rsp+300h+string]
0x18004c0ec  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18004c0f1  lea     rcx, [rsp+300h+string]
0x18004c0f6  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18004c0fb  test    al, al
0x18004c0fd  jnz     short loc_18004C120
0x18004c0ff  lea     rcx, [rsp+300h+var_2B0]
0x18004c104  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x18004c109  mov     rdx, rax
0x18004c10c  lea     rcx, [rsp+300h+string]
0x18004c111  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18004c116  lea     rcx, [rsp+300h+var_2B0]
0x18004c11b  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18004c120  mov     r8, [rsp+300h+string]; string
0x18004c125  lea     rcx, [rbp+200h+sourceString]; sourceString
0x18004c129  mov     edx, 104h; length
0x18004c12e  call    cs:__imp_WindowsCreateString
0x18004c135  nop     dword ptr [rax+rax+00h]
0x18004c13a  mov     ebx, eax
0x18004c13c  test    eax, eax
0x18004c13e  js      short loc_18004C184
0x18004c140  lea     r9, [rsp+300h+string]
0x18004c145  lea     r8, [rsp+300h+var_2D0]
0x18004c14a  lea     rdx, [rsp+300h+Uuid]
0x18004c14f  lea     rcx, [rbp+200h+var_280]
0x18004c153  call    _lambda_3ff306aa666b731442f985851ad8569b____lambda_3ff306aa666b731442f985851ad8569b_
0x18004c158  mov     r9, rax
0x18004c15b  mov     dword ptr [rsp+300h+var_2C0], 3
0x18004c163  mov     rdx, r15
0x18004c166  mov     qword ptr [rsp+300h+var_2C0+4], 80h
0x18004c16f  lea     rcx, [rsp+300h+var_2C0]
0x18004c174  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__CompleteMAMToMDMUpgradeOperationName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_3ff306aa666b731442f985851ad8569b___
0x18004c179  lea     rcx, [rbp+200h+var_280]
0x18004c17d  mov     ebx, eax
0x18004c17f  call    _lambda_9392614d0feddfd4e6683ca6cd2e3a39_____lambda_9392614d0feddfd4e6683ca6cd2e3a39_
0x18004c184  lea     rcx, [rsp+300h+string]
0x18004c189  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18004c18e  mov     eax, ebx
0x18004c190  mov     rcx, [rbp+200h+var_40]
0x18004c197  xor     rcx, rsp; StackCookie
0x18004c19a  call    __security_check_cookie
0x18004c19f  add     rsp, 2D0h
0x18004c1a6  pop     r15
0x18004c1a8  pop     r14
0x18004c1aa  pop     r12
0x18004c1ac  pop     rdi
0x18004c1ad  pop     rsi
0x18004c1ae  pop     rbx
0x18004c1af  pop     rbp
0x18004c1b0  retn
0x18004c1b2  xor     edx, edx; length
0x18004c1b4  mov     rcx, rsi; string
0x18004c1b7  call    cs:__imp_WindowsGetStringRawBuffer
0x18004c1be  nop     dword ptr [rax+rax+00h]
0x18004c1c3  xorps   xmm0, xmm0
0x18004c1c6  lea     rdx, [rsp+300h+string]; Uuid
0x18004c1cb  mov     rcx, rax; StringUuid
0x18004c1ce  mov     rbx, rax
0x18004c1d1  movups  xmmword ptr [rsp+300h+string], xmm0
0x18004c1d6  call    cs:__imp_UuidFromStringW
0x18004c1dd  nop     dword ptr [rax+rax+00h]
0x18004c1e2  test    eax, eax
0x18004c1e4  js      short loc_18004C190
0x18004c1e6  movaps  xmm0, xmmword ptr [rsp+300h+string]
0x18004c1eb  lea     rdx, [rsp+300h+var_2C0]
0x18004c1f0  movaps  xmm1, xmmword ptr [rsp+300h+Uuid.Data1]
0x18004c1f5  lea     rcx, [rsp+300h+var_2B0]
0x18004c1fa  movdqa  [rsp+300h+var_2C0], xmm0
0x18004c200  movdqa  [rsp+300h+var_2B0], xmm1
0x18004c206  call    cs:__imp_SwitchAADLinkedEnrollment
0x18004c20d  nop     dword ptr [rax+rax+00h]
0x18004c212  test    eax, eax
0x18004c214  js      loc_18004C190
0x18004c21a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004c21e  inc     rax
0x18004c221  cmp     [rbx+rax*2], r12w
0x18004c226  jnz     short loc_18004C21E
0x18004c228  lea     eax, ds:2[rax*2]
0x18004c22f  mov     r9d, 1; dwType
0x18004c235  mov     [rsp+300h+cbData], eax; cbData
0x18004c239  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Enrollments\\Subst"...
0x18004c240  mov     r8, rdi; lpValueName
0x18004c243  mov     [rsp+300h+lpData], rbx; lpData
0x18004c248  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004c24f  call    cs:__imp_RegSetKeyValueW
0x18004c256  nop     dword ptr [rax+rax+00h]
0x18004c25b  test    eax, eax
0x18004c25d  jle     loc_18004C0AA
0x18004c263  movzx   eax, ax
0x18004c266  or      eax, 80070000h
0x18004c26b  jmp     loc_18004C0A8
```
