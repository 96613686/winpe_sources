# RegisterDeviceWithManagementUsingAADCredentialsHelper(int,void *,int,ushort const *)

- ea: `0x180097d10`
- end: `0x180097f88`
- name: `?RegisterDeviceWithManagementUsingAADCredentialsHelper@@YAJHPEAXHPEBG@Z`
- size: `632`
- prototype: `__int64 __fastcall(int, void *, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180033c10`

## callees

- `0x1800089e8`
- `0x180008a08`
- `0x18000a5c4`
- `0x18000b2c0`
- `0x1800179f8`
- `0x1800186d4`
- `0x180023380`
- `0x18003a588`
- `0x18006ef5c`
- `0x180095efc`
- `0x180096088`
- `0x180096154`
- `0x180097a08`
- `0x180097af0`
- `0x180097b50`
- `0x180097d10`
- `0x180097f90`
- `0x1800986e4`

## import_xrefs

- `DMCmnUtils!DmInvalidateAadUserToken` at `0x180097ef7`
- `DMCmnUtils!DmInvalidateAadUserToken` at `0x180097ef7`
- `dsreg!DsrGetJoinInfo` at `0x180097e23`
- `dsreg!DsrGetJoinInfo` at `0x180097e23`
- `dsreg!DsrFreeJoinInfo` at `0x180097f2d`
- `dsreg!DsrFreeJoinInfo` at `0x180097f2d`

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
  wchar_t *v10; // rbx
  _WORD *v11; // rdx
  wchar_t *v12; // rax
  unsigned __int16 v13; // dx
  unsigned __int16 *v14; // rax
  int v15; // r14d
  int v16; // esi
  int v17; // edi
  CEnrollmentLogger *v18; // rax
  CEnrollmentLogger *Logger; // rax
  int v20; // r8d
  int lpMutexAttributes; // [rsp+20h] [rbp-60h]
  int lpMutexAttributesa; // [rsp+20h] [rbp-60h]
  wchar_t *Str; // [rsp+30h] [rbp-50h] BYREF
  __int64 v25; // [rsp+38h] [rbp-48h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v27[8]; // [rsp+48h] [rbp-38h] BYREF
  struct _DSREG_JOIN_INFO **v28; // [rsp+50h] [rbp-30h]
  char v29; // [rsp+58h] [rbp-28h]
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  int v32; // [rsp+B0h] [rbp+30h] BYREF
  void *v33; // [rsp+B8h] [rbp+38h] BYREF
  struct _DSREG_JOIN_INFO *v34; // [rsp+C8h] [rbp+48h] BYREF

  v34 = a4;
  v33 = a2;
  v32 = a1;
  SecurityDescriptor = 0;
  SystemSecurityDescriptor = anonymous_namespace_::GetSystemSecurityDescriptor(&SecurityDescriptor);
  v8 = SystemSecurityDescriptor;
  if ( SystemSecurityDescriptor >= 0 )
  {
    *(_QWORD *)&MutexAttributes.nLength = 24;
    *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
    MutexAttributes.lpSecurityDescriptor = SecurityDescriptor;
    v33 = 0;
    v9 = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
           (__int64)&v33,
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v33);
      goto LABEL_24;
    }
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v33,
      v27);
    v32 = 0;
    if ( (int)anonymous_namespace_::IsAlreadyEnrolled(&v32) >= 0 && v32 )
    {
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v27);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v33);
      v8 = -2145910774;
      goto LABEL_24;
    }
    v34 = 0;
    if ( (unsigned int)DsrGetJoinInfo(0, &v34) )
    {
      v16 = -2147024760;
      goto LABEL_23;
    }
    v28 = &v34;
    v29 = 1;
    v10 = 0;
    Str = 0;
    v11 = (_WORD *)*((_QWORD *)v34 + 7);
    if ( v11 && *v11 )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v25);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &Str,
        v25);
      v25 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
      v10 = Str;
      if ( !Str )
      {
        v16 = 14;
LABEL_21:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
        DsrFreeJoinInfo(v34);
LABEL_23:
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogAutoEnrollAttempt(Logger, v16, v20);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v27);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v33);
        v8 = v16;
        goto LABEL_24;
      }
      v12 = wcsstr(Str, L"https://");
      if ( v12 )
      {
        v14 = wcschr(v12 + 9, v13);
        if ( v14 )
          v14[1] = 0;
      }
    }
    v15 = 0;
    do
    {
      v16 = RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal(v10, v34, 0, 0, a3);
      if ( v16 != -2145910782 )
        break;
      if ( (unsigned int)++v15 >= 2 )
        break;
      v17 = DmInvalidateAadUserToken(L"de50c81f-5f80-4771-b66b-cebd28ccdfc1", v10, 0);
      v18 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogAutoEnrollAttemptRetryOnFailure(v18, v17);
    }
    while ( v17 >= 0 );
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
0x180097d10  mov     rax, rsp
0x180097d13  mov     [rax+18h], rbx
0x180097d17  mov     [rax+20h], r9
0x180097d1b  mov     [rax+10h], rdx
0x180097d1f  mov     [rax+8], ecx
0x180097d22  push    rbp
0x180097d23  push    rsi
0x180097d24  push    rdi
0x180097d25  push    r14
0x180097d27  push    r15
0x180097d29  mov     rbp, rsp
0x180097d2c  sub     rsp, 80h
0x180097d33  mov     r15d, r8d
0x180097d36  mov     [rbp+SecurityDescriptor], 0
0x180097d3e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180097d42  call    _anonymous_namespace___GetSystemSecurityDescriptor
0x180097d47  mov     ebx, eax
0x180097d49  test    eax, eax
0x180097d4b  jns     short loc_180097D6A
0x180097d4d  mov     rcx, [rbp+28h]; this
0x180097d51  mov     r9d, eax; char *
0x180097d54  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180097d5b  mov     edx, 1D9h; void *
0x180097d60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097d65  jmp     loc_180097F65
0x180097d6a  mov     qword ptr [rbp+MutexAttributes.nLength], 18h
0x180097d72  mov     qword ptr [rbp+MutexAttributes.bInheritHandle], 0
0x180097d7a  mov     rax, [rbp+SecurityDescriptor]
0x180097d7e  mov     [rbp+MutexAttributes.lpSecurityDescriptor], rax
0x180097d82  mov     [rbp+arg_8], 0
0x180097d8a  lea     rax, [rbp+MutexAttributes]
0x180097d8e  mov     [rsp+80h+lpMutexAttributes], rax; int
0x180097d93  lea     rdx, aGlobalRegister; "Global\\RegisterDeviceWithManagement-4C"...
0x180097d9a  lea     rcx, [rbp+arg_8]; int
0x180097d9e  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180097da3  mov     ebx, eax
0x180097da5  test    eax, eax
0x180097da7  jns     short loc_180097DD0
0x180097da9  mov     rcx, [rbp+28h]; this
0x180097dad  mov     r9d, eax; char *
0x180097db0  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180097db7  mov     edx, 1E0h; void *
0x180097dbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097dc1  nop
0x180097dc2  lea     rcx, [rbp+arg_8]
0x180097dc6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180097dcb  jmp     loc_180097F65
0x180097dd0  lea     rdx, [rbp+var_38]
0x180097dd4  lea     rcx, [rbp+arg_8]
0x180097dd8  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180097ddd  nop
0x180097dde  mov     [rbp+arg_0], 0
0x180097de5  lea     rcx, [rbp+arg_0]
0x180097de9  call    _anonymous_namespace___IsAlreadyEnrolled
0x180097dee  test    eax, eax
0x180097df0  js      short loc_180097E15
0x180097df2  cmp     [rbp+arg_0], 0
0x180097df6  jz      short loc_180097E15
0x180097df8  lea     rcx, [rbp+var_38]
0x180097dfc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180097e01  nop
0x180097e02  lea     rcx, [rbp+arg_8]
0x180097e06  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180097e0b  mov     ebx, 8018000Ah
0x180097e10  jmp     loc_180097F65
0x180097e15  mov     [rbp+arg_18], 0
0x180097e1d  lea     rdx, [rbp+arg_18]
0x180097e21  xor     ecx, ecx
0x180097e23  call    cs:__imp_DsrGetJoinInfo
0x180097e2a  nop     dword ptr [rax+rax+00h]
0x180097e2f  test    eax, eax
0x180097e31  jnz     loc_180097F3B
0x180097e37  lea     rax, [rbp+arg_18]
0x180097e3b  mov     [rbp+var_30], rax
0x180097e3f  mov     [rbp+var_28], 1
0x180097e43  xor     ebx, ebx
0x180097e45  mov     [rbp+Str], rbx
0x180097e49  mov     rax, [rbp+arg_18]
0x180097e4d  mov     rdx, [rax+38h]
0x180097e51  test    rdx, rdx
0x180097e54  jz      short loc_180097EB5
0x180097e56  xor     eax, eax
0x180097e58  cmp     ax, [rdx]
0x180097e5b  jz      short loc_180097EB5
0x180097e5d  lea     rcx, [rbp+var_48]
0x180097e61  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180097e66  mov     rdx, [rbp+var_48]
0x180097e6a  lea     rcx, [rbp+Str]
0x180097e6e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180097e73  mov     [rbp+var_48], rbx
0x180097e77  lea     rcx, [rbp+var_48]
0x180097e7b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180097e80  mov     rbx, [rbp+Str]
0x180097e84  test    rbx, rbx
0x180097e87  jz      loc_180097F1A
0x180097e8d  lea     rdx, aHttps; "https://"
0x180097e94  mov     rcx, rbx; Str
0x180097e97  call    ?wcsstr@@YAPEAGPEAGPEBG@Z; wcsstr(ushort *,ushort const *)
0x180097e9c  test    rax, rax
0x180097e9f  jz      short loc_180097EB5
0x180097ea1  lea     rcx, [rax+12h]; unsigned __int16 *
0x180097ea5  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x180097eaa  test    rax, rax
0x180097ead  jz      short loc_180097EB5
0x180097eaf  xor     ecx, ecx
0x180097eb1  mov     [rax+2], cx
0x180097eb5  xor     r14d, r14d
0x180097eb8  mov     [rsp+80h+var_58], 0; unsigned __int16 *
0x180097ec1  mov     dword ptr [rsp+80h+lpMutexAttributes], r15d; int
0x180097ec6  xor     r9d, r9d; void *
0x180097ec9  xor     r8d, r8d; int
0x180097ecc  mov     rdx, [rbp+arg_18]; struct _DSREG_JOIN_INFO *
0x180097ed0  mov     rcx, rbx; unsigned __int16 *
0x180097ed3  call    ?RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal@@YAJPEBGPEAU_DSREG_JOIN_INFO@@HPEAXH0@Z; RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal(ushort const *,_DSREG_JOIN_INFO *,int,void *,int,ushort const *)
0x180097ed8  mov     esi, eax
0x180097eda  cmp     eax, 80180002h
0x180097edf  jnz     short loc_180097F1F
0x180097ee1  inc     r14d
0x180097ee4  cmp     r14d, 2
0x180097ee8  jnb     short loc_180097F1F
0x180097eea  xor     r8d, r8d
0x180097eed  mov     rdx, rbx
0x180097ef0  lea     rcx, aDe50c81f5f8047; "de50c81f-5f80-4771-b66b-cebd28ccdfc1"
0x180097ef7  call    cs:__imp_?DmInvalidateAadUserToken@@YAJPEBG00@Z; DmInvalidateAadUserToken(ushort const *,ushort const *,ushort const *)
0x180097efe  nop     dword ptr [rax+rax+00h]
0x180097f03  mov     edi, eax
0x180097f05  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180097f0a  mov     edx, edi; int
0x180097f0c  mov     rcx, rax; this
0x180097f0f  call    ?LogAutoEnrollAttemptRetryOnFailure@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogAutoEnrollAttemptRetryOnFailure(long)
0x180097f14  test    edi, edi
0x180097f16  jns     short loc_180097EB8
0x180097f18  jmp     short loc_180097F1F
0x180097f1a  mov     esi, 0Eh
0x180097f1f  lea     rcx, [rbp+Str]
0x180097f23  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180097f28  nop
0x180097f29  mov     rcx, [rbp+arg_18]
0x180097f2d  call    cs:__imp_DsrFreeJoinInfo
0x180097f34  nop     dword ptr [rax+rax+00h]
0x180097f39  jmp     short loc_180097F40
0x180097f3b  mov     esi, 80070088h
0x180097f40  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180097f45  mov     edx, esi; int
0x180097f47  mov     rcx, rax; this
0x180097f4a  call    ?LogAutoEnrollAttempt@CEnrollmentLogger@@QEAAXJH@Z; CEnrollmentLogger::LogAutoEnrollAttempt(long,int)
0x180097f4f  nop
0x180097f50  lea     rcx, [rbp+var_38]
0x180097f54  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180097f59  nop
0x180097f5a  lea     rcx, [rbp+arg_8]
0x180097f5e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180097f63  mov     ebx, esi
0x180097f65  lea     rcx, [rbp+SecurityDescriptor]
0x180097f69  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180097f6e  mov     eax, ebx
0x180097f70  mov     rbx, [rsp+80h+arg_10]
0x180097f78  add     rsp, 80h
0x180097f7f  pop     r15
0x180097f81  pop     r14
0x180097f83  pop     rdi
0x180097f84  pop     rsi
0x180097f85  pop     rbp
0x180097f86  retn
```
