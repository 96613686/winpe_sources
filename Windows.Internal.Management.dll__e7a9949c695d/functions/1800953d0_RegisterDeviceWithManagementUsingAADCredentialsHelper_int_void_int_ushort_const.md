# RegisterDeviceWithManagementUsingAADCredentialsHelper(int,void *,int,ushort const *)

- ea: `0x1800953d0`
- end: `0x180095635`
- name: `?RegisterDeviceWithManagementUsingAADCredentialsHelper@@YAJHPEAXHPEBG@Z`
- size: `613`
- prototype: `__int64 __fastcall(int, void *, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180034b40`

## callees

- `0x180008880`
- `0x18000889c`
- `0x18000a2a4`
- `0x18000af20`
- `0x180017204`
- `0x180019ec8`
- `0x180024cf0`
- `0x18003b1ec`
- `0x18006db38`
- `0x180093684`
- `0x18009380c`
- `0x1800938d8`
- `0x1800950dc`
- `0x1800951c0`
- `0x180095218`
- `0x1800953d0`
- `0x18009563c`
- `0x180095d04`

## import_xrefs

- `DMCmnUtils!DmInvalidateAadUserToken` at `0x1800955b1`
- `DMCmnUtils!DmInvalidateAadUserToken` at `0x1800955b1`
- `dsreg!DsrGetJoinInfo` at `0x1800954e3`
- `dsreg!DsrGetJoinInfo` at `0x1800954e3`
- `dsreg!DsrFreeJoinInfo` at `0x1800955e1`
- `dsreg!DsrFreeJoinInfo` at `0x1800955e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RegisterDeviceWithManagementUsingAADCredentialsHelper(
        int a1,
        void *a2,
        int a3,
        struct _DSREG_JOIN_INFO *a4)
{
  int SystemSecurityDescriptor; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // r8
  const char *v11; // r9
  wchar_t *v12; // rbx
  char *v13; // rdx
  wchar_t *v14; // rax
  unsigned __int16 v15; // dx
  unsigned __int16 *v16; // rax
  int v17; // r14d
  int v18; // esi
  int v19; // edi
  CEnrollmentLogger *v20; // rax
  CEnrollmentLogger *Logger; // rax
  int v22; // r8d
  int lpMutexAttributes; // [rsp+20h] [rbp-60h]
  int lpMutexAttributesa; // [rsp+20h] [rbp-60h]
  wchar_t *Str; // [rsp+30h] [rbp-50h] BYREF
  __int64 v27; // [rsp+38h] [rbp-48h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v29[8]; // [rsp+48h] [rbp-38h] BYREF
  struct _DSREG_JOIN_INFO **v30; // [rsp+50h] [rbp-30h]
  char v31; // [rsp+58h] [rbp-28h]
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  int v34; // [rsp+B0h] [rbp+30h] BYREF
  void *v35; // [rsp+B8h] [rbp+38h] BYREF
  struct _DSREG_JOIN_INFO *v36; // [rsp+C8h] [rbp+48h] BYREF

  v36 = a4;
  v35 = a2;
  v34 = a1;
  SecurityDescriptor = 0;
  SystemSecurityDescriptor = anonymous_namespace_::GetSystemSecurityDescriptor(&SecurityDescriptor);
  v8 = SystemSecurityDescriptor;
  if ( SystemSecurityDescriptor >= 0 )
  {
    *(_QWORD *)&MutexAttributes.nLength = 24;
    *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
    MutexAttributes.lpSecurityDescriptor = SecurityDescriptor;
    v35 = 0;
    v9 = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
           (__int64)&v35,
           (const WCHAR *)L"Global\\RegisterDeviceWithManagement-4C06D03A-BD79-458A-8889-FD9FECCAA86C",
           v6,
           v7,
           &MutexAttributes);
    v8 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E0,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\aadhelper\\aadhelper.cpp",
        (const char *)(unsigned int)v9,
        lpMutexAttributesa);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v35);
      goto LABEL_24;
    }
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v35,
      v29);
    v34 = 0;
    if ( (int)anonymous_namespace_::IsAlreadyEnrolled(&v34) >= 0 && v34 )
    {
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v29);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v35);
      v8 = -2145910774;
      goto LABEL_24;
    }
    v36 = 0;
    if ( (unsigned int)DsrGetJoinInfo(0, &v36) )
    {
      v18 = -2147024760;
      goto LABEL_23;
    }
    v30 = &v36;
    v31 = 1;
    v12 = 0;
    Str = 0;
    v13 = (char *)*((_QWORD *)v36 + 7);
    if ( v13 && *(_WORD *)v13 )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v27,
        v13,
        v10,
        v11);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &Str,
        v27);
      v27 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
      v12 = Str;
      if ( !Str )
      {
        v18 = 14;
LABEL_21:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
        DsrFreeJoinInfo(v36);
LABEL_23:
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogAutoEnrollAttempt(Logger, v18, v22);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v29);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v35);
        v8 = v18;
        goto LABEL_24;
      }
      v14 = wcsstr(Str, L"https://");
      if ( v14 )
      {
        v16 = wcschr(v14 + 9, v15);
        if ( v16 )
          v16[1] = 0;
      }
    }
    v17 = 0;
    do
    {
      v18 = RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal(v12, v36, 0, 0, a3);
      if ( v18 != -2145910782 )
        break;
      if ( (unsigned int)++v17 >= 2 )
        break;
      v19 = DmInvalidateAadUserToken(L"de50c81f-5f80-4771-b66b-cebd28ccdfc1", v12, 0);
      v20 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogAutoEnrollAttemptRetryOnFailure(v20, v19);
    }
    while ( v19 >= 0 );
    goto LABEL_21;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1D9,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\aadhelper\\aadhelper.cpp",
    (const char *)(unsigned int)SystemSecurityDescriptor,
    lpMutexAttributes);
LABEL_24:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&SecurityDescriptor);
  return v8;
}

```

## disassembly

```asm
0x1800953d0  mov     rax, rsp
0x1800953d3  mov     [rax+18h], rbx
0x1800953d7  mov     [rax+20h], r9
0x1800953db  mov     [rax+10h], rdx
0x1800953df  mov     [rax+8], ecx
0x1800953e2  push    rbp
0x1800953e3  push    rsi
0x1800953e4  push    rdi
0x1800953e5  push    r14
0x1800953e7  push    r15
0x1800953e9  mov     rbp, rsp
0x1800953ec  sub     rsp, 80h
0x1800953f3  mov     r15d, r8d
0x1800953f6  mov     [rbp+SecurityDescriptor], 0
0x1800953fe  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180095402  call    _anonymous_namespace___GetSystemSecurityDescriptor
0x180095407  mov     ebx, eax
0x180095409  test    eax, eax
0x18009540b  jns     short loc_18009542A
0x18009540d  mov     rcx, [rbp+28h]; this
0x180095411  mov     r9d, eax; char *
0x180095414  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18009541b  mov     edx, 1D9h; void *
0x180095420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095425  jmp     loc_180095613
0x18009542a  mov     qword ptr [rbp+MutexAttributes.nLength], 18h
0x180095432  mov     qword ptr [rbp+MutexAttributes.bInheritHandle], 0
0x18009543a  mov     rax, [rbp+SecurityDescriptor]
0x18009543e  mov     [rbp+MutexAttributes.lpSecurityDescriptor], rax
0x180095442  mov     [rbp+arg_8], 0
0x18009544a  lea     rax, [rbp+MutexAttributes]
0x18009544e  mov     [rsp+80h+lpMutexAttributes], rax; int
0x180095453  lea     rdx, aGlobalRegister; "Global\\RegisterDeviceWithManagement-4C"...
0x18009545a  lea     rcx, [rbp+arg_8]; int
0x18009545e  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180095463  mov     ebx, eax
0x180095465  test    eax, eax
0x180095467  jns     short loc_180095490
0x180095469  mov     rcx, [rbp+28h]; this
0x18009546d  mov     r9d, eax; char *
0x180095470  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180095477  mov     edx, 1E0h; void *
0x18009547c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095481  nop
0x180095482  lea     rcx, [rbp+arg_8]
0x180095486  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009548b  jmp     loc_180095613
0x180095490  lea     rdx, [rbp+var_38]
0x180095494  lea     rcx, [rbp+arg_8]
0x180095498  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18009549d  nop
0x18009549e  mov     [rbp+arg_0], 0
0x1800954a5  lea     rcx, [rbp+arg_0]
0x1800954a9  call    _anonymous_namespace___IsAlreadyEnrolled
0x1800954ae  test    eax, eax
0x1800954b0  js      short loc_1800954D5
0x1800954b2  cmp     [rbp+arg_0], 0
0x1800954b6  jz      short loc_1800954D5
0x1800954b8  lea     rcx, [rbp+var_38]
0x1800954bc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800954c1  nop
0x1800954c2  lea     rcx, [rbp+arg_8]
0x1800954c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800954cb  mov     ebx, 8018000Ah
0x1800954d0  jmp     loc_180095613
0x1800954d5  mov     [rbp+arg_18], 0
0x1800954dd  lea     rdx, [rbp+arg_18]
0x1800954e1  xor     ecx, ecx
0x1800954e3  call    cs:__imp_DsrGetJoinInfo
0x1800954e9  test    eax, eax
0x1800954eb  jnz     loc_1800955E9
0x1800954f1  lea     rax, [rbp+arg_18]
0x1800954f5  mov     [rbp+var_30], rax
0x1800954f9  mov     [rbp+var_28], 1
0x1800954fd  xor     ebx, ebx
0x1800954ff  mov     [rbp+Str], rbx
0x180095503  mov     rax, [rbp+arg_18]
0x180095507  mov     rdx, [rax+38h]
0x18009550b  test    rdx, rdx
0x18009550e  jz      short loc_18009556F
0x180095510  xor     eax, eax
0x180095512  cmp     ax, [rdx]
0x180095515  jz      short loc_18009556F
0x180095517  lea     rcx, [rbp+var_48]
0x18009551b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180095520  mov     rdx, [rbp+var_48]
0x180095524  lea     rcx, [rbp+Str]
0x180095528  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009552d  mov     [rbp+var_48], rbx
0x180095531  lea     rcx, [rbp+var_48]
0x180095535  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009553a  mov     rbx, [rbp+Str]
0x18009553e  test    rbx, rbx
0x180095541  jz      loc_1800955CE
0x180095547  lea     rdx, aHttps; "https://"
0x18009554e  mov     rcx, rbx; Str
0x180095551  call    ?wcsstr@@YAPEAGPEAGPEBG@Z; wcsstr(ushort *,ushort const *)
0x180095556  test    rax, rax
0x180095559  jz      short loc_18009556F
0x18009555b  lea     rcx, [rax+12h]; unsigned __int16 *
0x18009555f  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x180095564  test    rax, rax
0x180095567  jz      short loc_18009556F
0x180095569  xor     ecx, ecx
0x18009556b  mov     [rax+2], cx
0x18009556f  xor     r14d, r14d
0x180095572  mov     [rsp+80h+var_58], 0; unsigned __int16 *
0x18009557b  mov     dword ptr [rsp+80h+lpMutexAttributes], r15d; int
0x180095580  xor     r9d, r9d; void *
0x180095583  xor     r8d, r8d; int
0x180095586  mov     rdx, [rbp+arg_18]; struct _DSREG_JOIN_INFO *
0x18009558a  mov     rcx, rbx; unsigned __int16 *
0x18009558d  call    ?RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal@@YAJPEBGPEAU_DSREG_JOIN_INFO@@HPEAXH0@Z; RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal(ushort const *,_DSREG_JOIN_INFO *,int,void *,int,ushort const *)
0x180095592  mov     esi, eax
0x180095594  cmp     eax, 80180002h
0x180095599  jnz     short loc_1800955D3
0x18009559b  inc     r14d
0x18009559e  cmp     r14d, 2
0x1800955a2  jnb     short loc_1800955D3
0x1800955a4  xor     r8d, r8d
0x1800955a7  mov     rdx, rbx
0x1800955aa  lea     rcx, aDe50c81f5f8047; "de50c81f-5f80-4771-b66b-cebd28ccdfc1"
0x1800955b1  call    cs:__imp_?DmInvalidateAadUserToken@@YAJPEBG00@Z; DmInvalidateAadUserToken(ushort const *,ushort const *,ushort const *)
0x1800955b7  mov     edi, eax
0x1800955b9  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800955be  mov     edx, edi; int
0x1800955c0  mov     rcx, rax; this
0x1800955c3  call    ?LogAutoEnrollAttemptRetryOnFailure@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogAutoEnrollAttemptRetryOnFailure(long)
0x1800955c8  test    edi, edi
0x1800955ca  jns     short loc_180095572
0x1800955cc  jmp     short loc_1800955D3
0x1800955ce  mov     esi, 0Eh
0x1800955d3  lea     rcx, [rbp+Str]
0x1800955d7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800955dc  nop
0x1800955dd  mov     rcx, [rbp+arg_18]
0x1800955e1  call    cs:__imp_DsrFreeJoinInfo
0x1800955e7  jmp     short loc_1800955EE
0x1800955e9  mov     esi, 80070088h
0x1800955ee  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800955f3  mov     edx, esi; int
0x1800955f5  mov     rcx, rax; this
0x1800955f8  call    ?LogAutoEnrollAttempt@CEnrollmentLogger@@QEAAXJH@Z; CEnrollmentLogger::LogAutoEnrollAttempt(long,int)
0x1800955fd  nop
0x1800955fe  lea     rcx, [rbp+var_38]
0x180095602  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180095607  nop
0x180095608  lea     rcx, [rbp+arg_8]
0x18009560c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180095611  mov     ebx, esi
0x180095613  lea     rcx, [rbp+SecurityDescriptor]
0x180095617  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009561c  mov     eax, ebx
0x18009561e  mov     rbx, [rsp+80h+arg_10]
0x180095626  add     rsp, 80h
0x18009562d  pop     r15
0x18009562f  pop     r14
0x180095631  pop     rdi
0x180095632  pop     rsi
0x180095633  pop     rbp
0x180095634  retn
```
