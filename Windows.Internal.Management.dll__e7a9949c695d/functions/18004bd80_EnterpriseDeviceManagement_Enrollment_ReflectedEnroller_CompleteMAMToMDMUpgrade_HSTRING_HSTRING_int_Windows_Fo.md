# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::CompleteMAMToMDMUpgrade(HSTRING__ *,HSTRING__ *,int,Windows::Foundation::IAsyncAction * *)

- ea: `0x18004bd80`
- end: `0x18004bfd5`
- name: `?CompleteMAMToMDMUpgrade@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJPEAUHSTRING__@@0HPEAPEAUIAsyncAction@Foundation@Windows@@@Z`
- size: `597`
- prototype: `int(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *__hidden this, HSTRING, HSTRING, int, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004d50`
- `0x180016b54`
- `0x180017074`
- `0x18001736c`
- `0x1800173ec`
- `0x180019b2c`
- `0x180019f1c`
- `0x180039990`
- `0x180042030`
- `0x180043198`
- `0x180045104`
- `0x18004bd80`
- `0x180059730`
- `0x180093684`
- `0x180093ebc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004bdc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004bf38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004bdc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004bf38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004beb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004beb6`
- `RPCRT4!UuidFromStringW` at `0x18004bddd`
- `RPCRT4!UuidFromStringW` at `0x18004bf51`
- `RPCRT4!UuidFromStringW` at `0x18004bddd`
- `RPCRT4!UuidFromStringW` at `0x18004bf51`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18004bfba`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18004bfba`
- `dmEnrollEngine!__imp_SwitchAADLinkedEnrollment` at `0x18004bf7b`
- `dmEnrollEngine!__imp_SwitchAADLinkedEnrollment` at `0x18004bf7b`
- `dmEnrollEngine!__imp_SetEnrollmentDormant` at `0x18004be17`
- `dmEnrollEngine!__imp_SetEnrollmentDormant` at `0x18004be17`
- `policymanager!EnterprisePolicyManagerStore_SetEnrollmentDormantState` at `0x18004be2a`
- `policymanager!EnterprisePolicyManagerStore_SetEnrollmentDormantState` at `0x18004be2a`

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
  _QWORD *v13; // rax
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
        (void *)0x35C,
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
0x18004bd80  push    rbp
0x18004bd82  push    rbx
0x18004bd83  push    rsi
0x18004bd84  push    rdi
0x18004bd85  push    r12
0x18004bd87  push    r14
0x18004bd89  push    r15
0x18004bd8b  lea     rbp, [rsp-1D0h]
0x18004bd93  sub     rsp, 2D0h
0x18004bd9a  mov     rax, cs:__security_cookie
0x18004bda1  xor     rax, rsp
0x18004bda4  mov     [rbp+200h+var_40], rax
0x18004bdab  mov     r15, [rbp+200h+arg_20]
0x18004bdb2  mov     ebx, r9d
0x18004bdb5  mov     rsi, rdx
0x18004bdb8  mov     [rsp+300h+var_2D0], ebx
0x18004bdbc  mov     r14, rcx
0x18004bdbf  xor     edx, edx; length
0x18004bdc1  mov     rcx, r8; string
0x18004bdc4  call    cs:__imp_WindowsGetStringRawBuffer
0x18004bdca  xorps   xmm0, xmm0
0x18004bdcd  lea     rdx, [rsp+300h+Uuid]; Uuid
0x18004bdd2  mov     rcx, rax; StringUuid
0x18004bdd5  mov     rdi, rax
0x18004bdd8  movups  xmmword ptr [rsp+300h+Uuid.Data1], xmm0
0x18004bddd  call    cs:__imp_UuidFromStringW
0x18004bde3  xor     r12d, r12d
0x18004bde6  test    eax, eax
0x18004bde8  js      loc_18004BF12
0x18004bdee  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18004bdf3  mov     edx, ebx; int
0x18004bdf5  mov     rcx, rax; this
0x18004bdf8  call    ?LogCompleteMAMToMDMUpgrade@CEnrollmentLogger@@QEAAXH@Z; CEnrollmentLogger::LogCompleteMAMToMDMUpgrade(int)
0x18004bdfd  test    ebx, ebx
0x18004bdff  jz      loc_18004BF33
0x18004be05  movaps  xmm0, xmmword ptr [rsp+300h+Uuid.Data1]
0x18004be0a  lea     rcx, [rsp+300h+string]
0x18004be0f  xor     edx, edx
0x18004be11  movdqa  xmmword ptr [rsp+300h+string], xmm0
0x18004be17  call    cs:__imp_SetEnrollmentDormant
0x18004be1d  test    eax, eax
0x18004be1f  js      loc_18004BF12
0x18004be25  xor     edx, edx
0x18004be27  mov     rcx, rdi
0x18004be2a  call    cs:__imp_?EnterprisePolicyManagerStore_SetEnrollmentDormantState@@YAJPEBGH@Z; EnterprisePolicyManagerStore_SetEnrollmentDormantState(ushort const *,int)
0x18004be30  test    eax, eax
0x18004be32  js      loc_18004BF12
0x18004be38  lea     rdx, [rbp+200h+sourceString]
0x18004be3c  mov     rcx, r14
0x18004be3f  call    GetCallingProcess
0x18004be44  test    eax, eax
0x18004be46  jns     short loc_18004BE63
0x18004be48  mov     rcx, [rbp+208h]; this
0x18004be4f  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18004be56  mov     r9d, eax; char *
0x18004be59  mov     edx, 35Ch; void *
0x18004be5e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004be63  lea     rcx, [rsp+300h+string]
0x18004be68  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18004be6d  xor     edx, edx
0x18004be6f  lea     rcx, [rsp+300h+string]
0x18004be74  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18004be79  lea     rcx, [rsp+300h+string]
0x18004be7e  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18004be83  test    al, al
0x18004be85  jnz     short loc_18004BEA8
0x18004be87  lea     rcx, [rsp+300h+var_2B0]
0x18004be8c  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x18004be91  mov     rdx, rax
0x18004be94  lea     rcx, [rsp+300h+string]
0x18004be99  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18004be9e  lea     rcx, [rsp+300h+var_2B0]
0x18004bea3  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18004bea8  mov     r8, [rsp+300h+string]; string
0x18004bead  lea     rcx, [rbp+200h+sourceString]; sourceString
0x18004beb1  mov     edx, 104h; length
0x18004beb6  call    cs:__imp_WindowsCreateString
0x18004bebc  mov     ebx, eax
0x18004bebe  test    eax, eax
0x18004bec0  js      short loc_18004BF06
0x18004bec2  lea     r9, [rsp+300h+string]
0x18004bec7  lea     r8, [rsp+300h+var_2D0]
0x18004becc  lea     rdx, [rsp+300h+Uuid]
0x18004bed1  lea     rcx, [rbp+200h+var_280]
0x18004bed5  call    _lambda_3ff306aa666b731442f985851ad8569b____lambda_3ff306aa666b731442f985851ad8569b_
0x18004beda  mov     r9, rax
0x18004bedd  mov     dword ptr [rsp+300h+var_2C0], 3
0x18004bee5  mov     rdx, r15
0x18004bee8  mov     qword ptr [rsp+300h+var_2C0+4], 80h
0x18004bef1  lea     rcx, [rsp+300h+var_2C0]
0x18004bef6  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__CompleteMAMToMDMUpgradeOperationName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_3ff306aa666b731442f985851ad8569b___
0x18004befb  lea     rcx, [rbp+200h+var_280]
0x18004beff  mov     ebx, eax
0x18004bf01  call    _lambda_9392614d0feddfd4e6683ca6cd2e3a39_____lambda_9392614d0feddfd4e6683ca6cd2e3a39_
0x18004bf06  lea     rcx, [rsp+300h+string]
0x18004bf0b  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18004bf10  mov     eax, ebx
0x18004bf12  mov     rcx, [rbp+200h+var_40]
0x18004bf19  xor     rcx, rsp; StackCookie
0x18004bf1c  call    __security_check_cookie
0x18004bf21  add     rsp, 2D0h
0x18004bf28  pop     r15
0x18004bf2a  pop     r14
0x18004bf2c  pop     r12
0x18004bf2e  pop     rdi
0x18004bf2f  pop     rsi
0x18004bf30  pop     rbx
0x18004bf31  pop     rbp
0x18004bf32  retn
0x18004bf33  xor     edx, edx; length
0x18004bf35  mov     rcx, rsi; string
0x18004bf38  call    cs:__imp_WindowsGetStringRawBuffer
0x18004bf3e  xorps   xmm0, xmm0
0x18004bf41  lea     rdx, [rsp+300h+string]; Uuid
0x18004bf46  mov     rcx, rax; StringUuid
0x18004bf49  mov     rbx, rax
0x18004bf4c  movups  xmmword ptr [rsp+300h+string], xmm0
0x18004bf51  call    cs:__imp_UuidFromStringW
0x18004bf57  test    eax, eax
0x18004bf59  js      short loc_18004BF12
0x18004bf5b  movaps  xmm0, xmmword ptr [rsp+300h+string]
0x18004bf60  lea     rdx, [rsp+300h+var_2C0]
0x18004bf65  movaps  xmm1, xmmword ptr [rsp+300h+Uuid.Data1]
0x18004bf6a  lea     rcx, [rsp+300h+var_2B0]
0x18004bf6f  movdqa  [rsp+300h+var_2C0], xmm0
0x18004bf75  movdqa  [rsp+300h+var_2B0], xmm1
0x18004bf7b  call    cs:__imp_SwitchAADLinkedEnrollment
0x18004bf81  test    eax, eax
0x18004bf83  js      short loc_18004BF12
0x18004bf85  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004bf89  inc     rax
0x18004bf8c  cmp     [rbx+rax*2], r12w
0x18004bf91  jnz     short loc_18004BF89
0x18004bf93  lea     eax, ds:2[rax*2]
0x18004bf9a  mov     r9d, 1; dwType
0x18004bfa0  mov     [rsp+300h+cbData], eax; cbData
0x18004bfa4  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Enrollments\\Subst"...
0x18004bfab  mov     r8, rdi; lpValueName
0x18004bfae  mov     [rsp+300h+lpData], rbx; lpData
0x18004bfb3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004bfba  call    cs:__imp_RegSetKeyValueW
0x18004bfc0  test    eax, eax
0x18004bfc2  jle     loc_18004BE32
0x18004bfc8  movzx   eax, ax
0x18004bfcb  or      eax, 80070000h
0x18004bfd0  jmp     loc_18004BE30
```
