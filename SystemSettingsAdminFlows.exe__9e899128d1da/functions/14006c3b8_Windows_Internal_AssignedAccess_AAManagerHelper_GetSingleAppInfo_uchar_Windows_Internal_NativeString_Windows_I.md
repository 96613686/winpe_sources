# Windows::Internal::AssignedAccess::AAManagerHelper::GetSingleAppInfo(uchar &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::AssignedAccess::ConfigSource &)

- ea: `0x14006c3b8`
- end: `0x14006c729`
- name: `?GetSingleAppInfo@AAManagerHelper@AssignedAccess@Internal@Windows@@AEAAJAEAEAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@34@1AEAW4ConfigSource@234@@Z`
- size: `881`
- prototype: `__int64 __usercall@<rax>(Windows::Internal::AssignedAccess::AAManagerHelper *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14006c730`

## callees

- `0x14001f3d4`
- `0x14003ff9c`
- `0x1400407b0`
- `0x1400408dc`
- `0x140059d0c`
- `0x1400695a4`
- `0x140069728`
- `0x14006be04`
- `0x14006bfc0`
- `0x14006c028`
- `0x14006c298`
- `0x14006c3b8`
- `0x14007d010`

## string_xrefs

- `0x14006c45e`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\aamanagerhelper.cpp`
- `0x14006c491`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\aamanagerhelper.cpp`
- `0x14006c4e8`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\aamanagerhelper.cpp`
- `0x14006c556`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\aamanagerhelper.cpp`
- `0x14006c5b4`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\aamanagerhelper.cpp`
- `0x14006c62a`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\aamanagerhelper.cpp`
- `0x14006c6ac`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\aamanagerhelper.cpp`
- `0x14006c707`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\aamanagerhelper.cpp`
- `0x14006c699`: `shellcommondesktopbase\base\embedded\sys\lockdown\inc\assignedaccessconfigurationhelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::AAManagerHelper::GetSingleAppInfo(
        Windows::Internal::AssignedAccess::AAManagerHelper *this,
        _BYTE *a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5)
{
  int v9; // ebx
  _DWORD *v10; // r12
  int AssignedAccessConfiguration; // eax
  __int64 v12; // rcx
  int UserInfoIf__lambda_c76887d512334f593d0f5d124e2447dc; // eax
  struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *v14; // rsi
  int Sid; // eax
  const wchar_t *v16; // r13
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // rdi
  int v19; // eax
  int v20; // r12d
  int AumidForSingleAppUserInfo; // eax
  int v22; // edi
  const wchar_t *v23; // rdi
  int v24; // eax
  int v25; // r14d
  __int64 v26; // rdx
  __int64 v27; // rdx
  struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *v29; // [rsp+20h] [rbp-28h] BYREF
  STRSAFE_PCNZWCH pszSrc; // [rsp+28h] [rbp-20h] BYREF
  STRSAFE_PCNZWCH v31; // [rsp+30h] [rbp-18h] BYREF
  struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *v32[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]

  v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(a3, 0);
  if ( v9 < 0 )
  {
    v27 = 47;
    goto LABEL_37;
  }
  StringCchCopyNW(*(STRSAFE_LPWSTR *)a3, 1u, &Data, 0);
  *(_QWORD *)(a3 + 8) = 0;
  v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(a4, 0);
  if ( v9 < 0 )
  {
    v27 = 48;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\aamanagerhelper.cpp",
      (const char *)(unsigned int)v9,
      (int)v29);
    return (unsigned int)v9;
  }
  StringCchCopyNW(*(STRSAFE_LPWSTR *)a4, 1u, &Data, 0);
  v10 = a5;
  *(_QWORD *)(a4 + 8) = 0;
  *a2 = 0;
  v32[0] = 0;
  *a5 = 0;
  AssignedAccessConfiguration = Windows::Internal::AssignedAccess::AAManagerHelper::GetAssignedAccessConfiguration(
                                  this,
                                  v32);
  v9 = AssignedAccessConfiguration;
  if ( AssignedAccessConfiguration >= 0 )
  {
    v29 = 0;
    UserInfoIf__lambda_c76887d512334f593d0f5d124e2447dc = Windows::Internal::AssignedAccess::AssignedAccessConfigurationHelper::FindUserInfoIf__lambda_c76887d512334f593d0f5d124e2447dc___(
                                                            v12,
                                                            v32[0],
                                                            &v29);
    v9 = UserInfoIf__lambda_c76887d512334f593d0f5d124e2447dc;
    if ( UserInfoIf__lambda_c76887d512334f593d0f5d124e2447dc < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\aamanagerhelper.cpp",
        (const char *)(unsigned int)UserInfoIf__lambda_c76887d512334f593d0f5d124e2447dc,
        (int)v29);
LABEL_7:
      ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>((__int64 *)&v29);
      goto LABEL_34;
    }
    v14 = v29;
    if ( v29 )
    {
      *a2 = 1;
      pszSrc = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pszSrc,
        0);
      Sid = Windows::Internal::AssignedAccess::AssignedAccessUserInfoHelper::GetSid(v14, (unsigned __int16 **)&pszSrc);
      v9 = Sid;
      if ( Sid < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x46,
          (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\aamanagerhelper.cpp",
          (const char *)(unsigned int)Sid,
          (int)v29);
LABEL_11:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&pszSrc);
        goto LABEL_7;
      }
      v16 = pszSrc;
      v17 = -1;
      if ( pszSrc )
      {
        v18 = -1;
        do
          ++v18;
        while ( pszSrc[v18] );
        v19 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                a3,
                v18);
        v20 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x47,
            (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\aamanagerhelper.cpp",
            (const char *)(unsigned int)v19,
            (int)v29);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&pszSrc);
          ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>((__int64 *)&v29);
          v9 = v20;
          goto LABEL_34;
        }
        StringCchCopyNW(*(STRSAFE_LPWSTR *)a3, v18 + 1, v16, v18);
        v10 = a5;
        *(_QWORD *)(a3 + 8) = v18;
      }
      else
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a3);
      }
      v31 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v31,
        0);
      AumidForSingleAppUserInfo = Windows::Internal::AssignedAccess::AssignedAccessUserInfoHelper::GetAumidForSingleAppUserInfo(
                                    v14,
                                    (unsigned __int16 **)&v31);
      v22 = AumidForSingleAppUserInfo;
      if ( AumidForSingleAppUserInfo < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4A,
          (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\aamanagerhelper.cpp",
          (const char *)(unsigned int)AumidForSingleAppUserInfo,
          (int)v29);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v31);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&pszSrc);
        ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>((__int64 *)&v29);
        v9 = v22;
        goto LABEL_34;
      }
      v23 = v31;
      if ( v31 )
      {
        do
          ++v17;
        while ( v31[v17] );
        v24 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                a4,
                v17);
        v25 = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4B,
            (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\aamanagerhelper.cpp",
            (const char *)(unsigned int)v24,
            (int)v29);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v31);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&pszSrc);
          ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>((__int64 *)&v29);
          v9 = v25;
          goto LABEL_34;
        }
        StringCchCopyNW(*(STRSAFE_LPWSTR *)a4, v17 + 1, v23, v17);
        *(_QWORD *)(a4 + 8) = v17;
      }
      else
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a4);
      }
      if ( !v14 )
      {
        v9 = -2147467261;
        v26 = 57;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\inc\\assignedaccessconfigurationhelper.h",
          (const char *)(unsigned int)v9,
          (int)v29);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4D,
          (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\aamanagerhelper.cpp",
          (const char *)(unsigned int)v9,
          (int)v29);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v31);
        goto LABEL_11;
      }
      v9 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *, _DWORD *))(*(_QWORD *)v14 + 72LL))(
             v14,
             v10);
      if ( v9 < 0 )
      {
        v26 = 58;
        goto LABEL_31;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v31);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&pszSrc);
    }
    ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>((__int64 *)&v29);
    v9 = 0;
    goto LABEL_34;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x35,
    (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\aamanagerhelper.cpp",
    (const char *)(unsigned int)AssignedAccessConfiguration,
    (int)v29);
LABEL_34:
  ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>((__int64 *)v32);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14006c3b8  push    rbp
0x14006c3ba  push    rbx
0x14006c3bb  push    rsi
0x14006c3bc  push    rdi
0x14006c3bd  push    r12
0x14006c3bf  push    r13
0x14006c3c1  push    r14
0x14006c3c3  push    r15
0x14006c3c5  mov     rbp, rsp
0x14006c3c8  sub     rsp, 48h
0x14006c3cc  mov     rdi, rdx
0x14006c3cf  mov     rsi, rcx
0x14006c3d2  xor     edx, edx
0x14006c3d4  mov     rcx, r8
0x14006c3d7  mov     r15, r9
0x14006c3da  mov     r14, r8
0x14006c3dd  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x14006c3e2  xor     r13d, r13d
0x14006c3e5  mov     ebx, eax
0x14006c3e7  test    eax, eax
0x14006c3e9  js      loc_14006C6FE
0x14006c3ef  mov     rcx, [r14]; pszDest
0x14006c3f2  lea     r12d, [r13+1]
0x14006c3f6  mov     edx, r12d; cchDest
0x14006c3f9  lea     r8, Data; pszSrc
0x14006c400  xor     r9d, r9d; cchToCopy
0x14006c403  call    StringCchCopyNW
0x14006c408  xor     edx, edx
0x14006c40a  mov     [r14+8], r13
0x14006c40e  mov     rcx, r15
0x14006c411  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x14006c416  mov     ebx, eax
0x14006c418  test    eax, eax
0x14006c41a  js      loc_14006C6F7
0x14006c420  mov     rcx, [r15]; pszDest
0x14006c423  lea     r8, Data; pszSrc
0x14006c42a  xor     r9d, r9d; cchToCopy
0x14006c42d  mov     edx, r12d; cchDest
0x14006c430  call    StringCchCopyNW
0x14006c435  mov     r12, [rbp+arg_20]
0x14006c439  lea     rdx, [rbp+var_10]; struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration **
0x14006c43d  mov     [r15+8], r13
0x14006c441  mov     rcx, rsi; this
0x14006c444  mov     [rdi], r13b
0x14006c447  mov     [rbp+var_10], r13
0x14006c44b  mov     [r12], r13d
0x14006c44f  call    ?GetAssignedAccessConfiguration@AAManagerHelper@AssignedAccess@Internal@Windows@@AEAAJPEAPEAUIAssignedAccessConfiguration@234@@Z; Windows::Internal::AssignedAccess::AAManagerHelper::GetAssignedAccessConfiguration(Windows::Internal::AssignedAccess::IAssignedAccessConfiguration * *)
0x14006c454  mov     ebx, eax
0x14006c456  test    eax, eax
0x14006c458  jns     short loc_14006C476
0x14006c45a  mov     rcx, [rbp+40h]; this
0x14006c45e  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\base\\embedded"...
0x14006c465  mov     r9d, eax; char *
0x14006c468  lea     edx, [r13+35h]; void *
0x14006c46c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c471  jmp     loc_14006C6EC
0x14006c476  mov     rdx, [rbp+var_10]
0x14006c47a  lea     r8, [rbp+var_28]
0x14006c47e  mov     [rbp+var_28], r13
0x14006c482  call    Windows__Internal__AssignedAccess__AssignedAccessConfigurationHelper__FindUserInfoIf__lambda_c76887d512334f593d0f5d124e2447dc___
0x14006c487  mov     ebx, eax
0x14006c489  test    eax, eax
0x14006c48b  jns     short loc_14006C4B3
0x14006c48d  mov     rcx, [rbp+40h]; this
0x14006c491  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\base\\embedded"...
0x14006c498  mov     r9d, eax; char *
0x14006c49b  mov     edx, 40h ; '@'; void *
0x14006c4a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c4a5  lea     rcx, [rbp+var_28]
0x14006c4a9  call    ??1?$CComPtrBase@UICbsSession@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>(void)
0x14006c4ae  jmp     loc_14006C6EC
0x14006c4b3  mov     rsi, [rbp+var_28]
0x14006c4b7  test    rsi, rsi
0x14006c4ba  jz      loc_14006C6E0
0x14006c4c0  xor     edx, edx
0x14006c4c2  mov     byte ptr [rdi], 1
0x14006c4c5  lea     rcx, [rbp+pszSrc]
0x14006c4c9  mov     [rbp+pszSrc], r13
0x14006c4cd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x14006c4d2  lea     rdx, [rbp+pszSrc]; unsigned __int16 **
0x14006c4d6  mov     rcx, rsi; struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *
0x14006c4d9  call    ?GetSid@AssignedAccessUserInfoHelper@AssignedAccess@Internal@Windows@@SAJPEAUIAssignedAccessUserInfo@234@PEAPEAG@Z; Windows::Internal::AssignedAccess::AssignedAccessUserInfoHelper::GetSid(Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *,ushort * *)
0x14006c4de  mov     ebx, eax
0x14006c4e0  test    eax, eax
0x14006c4e2  jns     short loc_14006C507
0x14006c4e4  mov     rcx, [rbp+40h]; this
0x14006c4e8  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\base\\embedded"...
0x14006c4ef  mov     r9d, eax; char *
0x14006c4f2  mov     edx, 46h ; 'F'; void *
0x14006c4f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c4fc  lea     rcx, [rbp+pszSrc]
0x14006c500  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006c505  jmp     short loc_14006C4A5
0x14006c507  mov     r13, [rbp+pszSrc]
0x14006c50b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14006c50f  xor     eax, eax
0x14006c511  test    r13, r13
0x14006c514  jz      short loc_14006C584
0x14006c516  mov     rdi, rbx
0x14006c519  inc     rdi
0x14006c51c  cmp     [r13+rdi*2+0], ax
0x14006c522  jnz     short loc_14006C519
0x14006c524  mov     rdx, rdi
0x14006c527  mov     rcx, r14
0x14006c52a  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x14006c52f  mov     r12d, eax
0x14006c532  test    eax, eax
0x14006c534  js      short loc_14006C552
0x14006c536  mov     rcx, [r14]; pszDest
0x14006c539  lea     rdx, [rdi+1]; cchDest
0x14006c53d  mov     r9, rdi; cchToCopy
0x14006c540  mov     r8, r13; pszSrc
0x14006c543  call    StringCchCopyNW
0x14006c548  mov     r12, [rbp+arg_20]
0x14006c54c  mov     [r14+8], rdi
0x14006c550  jmp     short loc_14006C58C
0x14006c552  mov     rcx, [rbp+40h]; this
0x14006c556  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\base\\embedded"...
0x14006c55d  mov     r9d, r12d; char *
0x14006c560  mov     edx, 47h ; 'G'; void *
0x14006c565  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c56a  lea     rcx, [rbp+pszSrc]
0x14006c56e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006c573  lea     rcx, [rbp+var_28]
0x14006c577  call    ??1?$CComPtrBase@UICbsSession@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>(void)
0x14006c57c  mov     ebx, r12d
0x14006c57f  jmp     loc_14006C6EC
0x14006c584  mov     rcx, r14
0x14006c587  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14006c58c  xor     r13d, r13d
0x14006c58f  lea     rcx, [rbp+var_18]
0x14006c593  xor     edx, edx
0x14006c595  mov     [rbp+var_18], r13
0x14006c599  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x14006c59e  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x14006c5a2  mov     rcx, rsi; struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *
0x14006c5a5  call    ?GetAumidForSingleAppUserInfo@AssignedAccessUserInfoHelper@AssignedAccess@Internal@Windows@@SAJPEAUIAssignedAccessUserInfo@234@PEAPEAG@Z; Windows::Internal::AssignedAccess::AssignedAccessUserInfoHelper::GetAumidForSingleAppUserInfo(Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *,ushort * *)
0x14006c5aa  mov     edi, eax
0x14006c5ac  test    eax, eax
0x14006c5ae  jns     short loc_14006C5E9
0x14006c5b0  mov     rcx, [rbp+40h]; this
0x14006c5b4  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\base\\embedded"...
0x14006c5bb  mov     r9d, eax; char *
0x14006c5be  lea     edx, [r13+4Ah]; void *
0x14006c5c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c5c7  lea     rcx, [rbp+var_18]
0x14006c5cb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006c5d0  lea     rcx, [rbp+pszSrc]
0x14006c5d4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006c5d9  lea     rcx, [rbp+var_28]
0x14006c5dd  call    ??1?$CComPtrBase@UICbsSession@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>(void)
0x14006c5e2  mov     ebx, edi
0x14006c5e4  jmp     loc_14006C6EC
0x14006c5e9  mov     rdi, [rbp+var_18]
0x14006c5ed  test    rdi, rdi
0x14006c5f0  jz      short loc_14006C661
0x14006c5f2  inc     rbx
0x14006c5f5  cmp     [rdi+rbx*2], r13w
0x14006c5fa  jnz     short loc_14006C5F2
0x14006c5fc  mov     rdx, rbx
0x14006c5ff  mov     rcx, r15
0x14006c602  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x14006c607  mov     r14d, eax
0x14006c60a  test    eax, eax
0x14006c60c  js      short loc_14006C626
0x14006c60e  mov     rcx, [r15]; pszDest
0x14006c611  lea     rdx, [rbx+1]; cchDest
0x14006c615  mov     r9, rbx; cchToCopy
0x14006c618  mov     r8, rdi; pszSrc
0x14006c61b  call    StringCchCopyNW
0x14006c620  mov     [r15+8], rbx
0x14006c624  jmp     short loc_14006C669
0x14006c626  mov     rcx, [rbp+40h]; this
0x14006c62a  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\base\\embedded"...
0x14006c631  mov     r9d, r14d; char *
0x14006c634  mov     edx, 4Bh ; 'K'; void *
0x14006c639  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c63e  lea     rcx, [rbp+var_18]
0x14006c642  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006c647  lea     rcx, [rbp+pszSrc]
0x14006c64b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006c650  lea     rcx, [rbp+var_28]
0x14006c654  call    ??1?$CComPtrBase@UICbsSession@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>(void)
0x14006c659  mov     ebx, r14d
0x14006c65c  jmp     loc_14006C6EC
0x14006c661  mov     rcx, r15
0x14006c664  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14006c669  test    rsi, rsi
0x14006c66c  jnz     short loc_14006C678
0x14006c66e  mov     ebx, 80004003h
0x14006c673  lea     edx, [rsi+39h]
0x14006c676  jmp     short loc_14006C695
0x14006c678  mov     rax, [rsi]
0x14006c67b  mov     rdx, r12
0x14006c67e  mov     rcx, rsi
0x14006c681  mov     rax, [rax+48h]
0x14006c685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006c68a  mov     ebx, eax
0x14006c68c  test    eax, eax
0x14006c68e  jns     short loc_14006C6CE
0x14006c690  mov     edx, 3Ah ; ':'; void *
0x14006c695  mov     rcx, [rbp+40h]; this
0x14006c699  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x14006c6a0  mov     r9d, ebx; char *
0x14006c6a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c6a8  mov     rcx, [rbp+40h]; this
0x14006c6ac  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\base\\embedded"...
0x14006c6b3  mov     r9d, ebx; char *
0x14006c6b6  mov     edx, 4Dh ; 'M'; void *
0x14006c6bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c6c0  lea     rcx, [rbp+var_18]
0x14006c6c4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006c6c9  jmp     loc_14006C4FC
0x14006c6ce  lea     rcx, [rbp+var_18]
0x14006c6d2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006c6d7  lea     rcx, [rbp+pszSrc]
0x14006c6db  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006c6e0  lea     rcx, [rbp+var_28]
0x14006c6e4  call    ??1?$CComPtrBase@UICbsSession@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>(void)
0x14006c6e9  mov     ebx, r13d
0x14006c6ec  lea     rcx, [rbp+var_10]
0x14006c6f0  call    ??1?$CComPtrBase@UICbsSession@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>(void)
0x14006c6f5  jmp     short loc_14006C716
0x14006c6f7  mov     edx, 30h ; '0'
0x14006c6fc  jmp     short loc_14006C703
0x14006c6fe  mov     edx, 2Fh ; '/'; void *
0x14006c703  mov     rcx, [rbp+40h]; this
0x14006c707  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\base\\embedded"...
0x14006c70e  mov     r9d, ebx; char *
0x14006c711  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c716  mov     eax, ebx
0x14006c718  add     rsp, 48h
0x14006c71c  pop     r15
0x14006c71e  pop     r14
0x14006c720  pop     r13
0x14006c722  pop     r12
0x14006c724  pop     rdi
0x14006c725  pop     rsi
0x14006c726  pop     rbx
0x14006c727  pop     rbp
0x14006c728  retn
```
