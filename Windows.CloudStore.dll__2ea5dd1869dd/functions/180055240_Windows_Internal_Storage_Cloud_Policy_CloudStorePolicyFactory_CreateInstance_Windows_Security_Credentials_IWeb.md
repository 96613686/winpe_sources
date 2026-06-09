# Windows::Internal::Storage::Cloud::Policy::CloudStorePolicyFactory::CreateInstance(Windows::Security::Credentials::IWebAccount *,HSTRING__ *,Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy * *)

- ea: `0x180055240`
- end: `0x180055578`
- name: `?CreateInstance@CloudStorePolicyFactory@Policy@Cloud@Storage@Internal@Windows@@UEAAJPEAUIWebAccount@Credentials@Security@6@PEAUHSTRING__@@PEAPEAUICloudStorePolicy@23456@@Z`
- size: `824`
- prototype: `int(Windows::Internal::Storage::Cloud::Policy::CloudStorePolicyFactory *__hidden this, struct Windows::Security::Credentials::IWebAccount *, HSTRING, struct Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000dfe4`
- `0x180016cf4`
- `0x180032a50`
- `0x180047904`
- `0x180054d4c`
- `0x180055240`
- `0x180055580`
- `0x1800556d8`
- `0x180062040`
- `0x18011aa04`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800554f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800554f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005549b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005549b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800553a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800553a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800552cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055474`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055510`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800552cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055474`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055510`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::Storage::Cloud::Policy::CloudStorePolicyFactory::CreateInstance(
        Windows::Internal::Storage::Cloud::Policy::CloudStorePolicyFactory *this,
        struct Windows::Security::Credentials::IWebAccount *a2,
        HSTRING a3,
        struct Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy **a4)
{
  char v7; // si
  unsigned __int16 **v8; // rdx
  int CallingProcessHandle; // edi
  bool *v10; // r8
  char *v11; // rcx
  PCWSTR v12; // rax
  struct Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy **v13; // rax
  const char *v14; // r9
  struct Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy *v15; // rcx
  __int64 result; // rax
  int v17; // eax
  struct Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy **v18; // rax
  struct Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy *v19; // rcx
  int v20; // eax
  unsigned __int16 **v21; // rdx
  int CallingProcessPackageFamilyName; // eax
  const WCHAR *v23; // rax
  struct Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy **v24; // rax
  struct Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy *v25; // rcx
  PCWSTR StringRawBuffer; // rax
  struct Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy **v27; // rax
  struct Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy *v28; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-78h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-78h]
  HANDLE hObject; // [rsp+30h] [rbp-68h] BYREF
  __int64 v32; // [rsp+38h] [rbp-60h] BYREF
  LPVOID *p_pv; // [rsp+40h] [rbp-58h] BYREF
  __int64 v34; // [rsp+48h] [rbp-50h] BYREF
  char v35; // [rsp+50h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  LPVOID pv; // [rsp+B8h] [rbp+20h] BYREF

  *a4 = 0;
  v32 = 0;
  v7 = 0;
  LOBYTE(pv) = 0;
  hObject = 0;
  try
  {
    CallingProcessHandle = CallerIdentity::GetCallingProcessHandle();
    if ( CallingProcessHandle >= 0 )
    {
      CallingProcessHandle = CallerIdentity::IsProcessAppContainer(hObject, &pv, v10);
      v7 = (char)pv;
    }
    v11 = (char *)hObject;
    hObject = 0;
    if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v11);
    if ( CallingProcessHandle < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D2,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorepolicy.cpp",
        (const char *)(unsigned int)CallingProcessHandle,
        bIgnoreCase);
    if ( v7 )
    {
      if ( a3 )
      {
        LOBYTE(pv) = 0;
        v20 = CallerIdentity::CheckCallerCapability(
                (CallerIdentity *)L"activitySystem",
                (const unsigned __int16 *)&pv,
                v10);
        if ( v20 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1E2,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorepolicy.cpp",
            (const char *)(unsigned int)v20,
            bIgnoreCase);
        if ( (_BYTE)pv )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
          v27 = (struct Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy **)Windows::Internal::Storage::Cloud::Policy::CloudStorePolicy_CreateInstance(
                                                                                          &pv,
                                                                                          a2,
                                                                                          StringRawBuffer);
          v28 = *v27;
          *v27 = 0;
          *a4 = v28;
          wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&pv);
          wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v32);
          result = 0;
        }
        else
        {
          pv = 0;
          p_pv = &pv;
          v34 = 0;
          v35 = 1;
          CallingProcessPackageFamilyName = CallerIdentity::GetCallingProcessPackageFamilyName(
                                              (CallerIdentity *)&v34,
                                              v21);
          if ( CallingProcessPackageFamilyName < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1F0,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorepolicy.cpp",
              (const char *)(unsigned int)CallingProcessPackageFamilyName,
              bIgnoreCase);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pv);
          v23 = WindowsGetStringRawBuffer(a3, 0);
          if ( CompareStringOrdinal(v23, -1, (LPCWCH)pv, -1, 1) != 2 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1F3,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorepolicy.cpp",
              (const char *)0x80070005LL,
              bIgnoreCasea);
          v24 = (struct Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy **)Windows::Internal::Storage::Cloud::Policy::CloudStorePolicy_CreateInstance(
                                                                                          &hObject,
                                                                                          a2,
                                                                                          pv);
          v25 = *v24;
          *v24 = 0;
          *a4 = v25;
          wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&hObject);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
          wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v32);
          result = 0;
        }
      }
      else
      {
        pv = 0;
        p_pv = &pv;
        v34 = 0;
        v35 = 1;
        v17 = CallerIdentity::GetCallingProcessPackageFamilyName((CallerIdentity *)&v34, v8);
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1DA,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorepolicy.cpp",
            (const char *)(unsigned int)v17,
            bIgnoreCase);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pv);
        v18 = (struct Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy **)Windows::Internal::Storage::Cloud::Policy::CloudStorePolicy_CreateInstance(
                                                                                        &hObject,
                                                                                        a2,
                                                                                        pv);
        v19 = *v18;
        *v18 = 0;
        *a4 = v19;
        if ( hObject )
          (*(void (__fastcall **)(HANDLE))(*(_QWORD *)hObject + 16LL))(hObject);
        if ( pv )
          CoTaskMemFree(pv);
        result = 0;
      }
    }
    else
    {
      v12 = WindowsGetStringRawBuffer(a3, 0);
      v13 = (struct Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy **)Windows::Internal::Storage::Cloud::Policy::CloudStorePolicy_CreateInstance(
                                                                                      &pv,
                                                                                      a2,
                                                                                      v12);
      v15 = *v13;
      *v13 = 0;
      *a4 = v15;
      if ( pv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
      result = 0;
    }
  }
  catch ( ... )
  {
    LODWORD(pv) = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0x201,
                    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorepolicy.cpp",
                    v14);
    return (unsigned int)pv;
  }
  return result;
}

```

## disassembly

```asm
0x180055240  mov     rax, rsp
0x180055243  push    rbx
0x180055244  push    rsi
0x180055245  push    rdi
0x180055246  push    r12
0x180055248  push    r14
0x18005524a  push    r15
0x18005524c  sub     rsp, 68h
0x180055250  mov     rbx, r9
0x180055253  mov     r15, r8
0x180055256  mov     r14, rdx
0x180055259  xor     r12d, r12d
0x18005525c  mov     [r9], r12
0x18005525f  mov     [rax-60h], r12
0x180055263  mov     sil, r12b
0x180055266  mov     [rax+20h], r12b
0x18005526a  mov     [rax-68h], r12
0x18005526e  lea     r8, [rax-68h]
0x180055272  xor     edx, edx
0x180055274  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x180055279  mov     edi, eax
0x18005527b  test    eax, eax
0x18005527d  js      short loc_18005529B
0x18005527f  lea     rdx, [rsp+98h+pv]; void *
0x180055287  mov     rcx, [rsp+98h+hObject]; ProcessHandle
0x18005528c  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x180055291  mov     edi, eax
0x180055293  mov     sil, byte ptr [rsp+98h+pv]
0x18005529b  mov     rcx, [rsp+98h+hObject]; hObject
0x1800552a0  mov     [rsp+98h+hObject], r12
0x1800552a5  lea     rax, [rcx-1]
0x1800552a9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800552ad  jbe     loc_1800554F2
0x1800552b3  mov     rcx, [rsp+98h]; this
0x1800552bb  test    edi, edi
0x1800552bd  js      loc_1800553B1
0x1800552c3  test    sil, sil
0x1800552c6  jnz     short loc_180055319
0x1800552c8  xor     edx, edx; length
0x1800552ca  mov     rcx, r15; string
0x1800552cd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800552d3  mov     r8, rax
0x1800552d6  mov     rdx, r14
0x1800552d9  lea     rcx, [rsp+98h+pv]
0x1800552e1  call    ?CloudStorePolicy_CreateInstance@Policy@Cloud@Storage@Internal@Windows@@YA?AV?$com_ptr_t@UICloudStorePolicy@Policy@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@PEAUIWebAccount@Credentials@Security@5@PEBG@Z; Windows::Internal::Storage::Cloud::Policy::CloudStorePolicy_CreateInstance(Windows::Security::Credentials::IWebAccount *,ushort const *)
0x1800552e6  mov     rcx, [rax]
0x1800552e9  mov     [rax], r12
0x1800552ec  mov     [rbx], rcx
0x1800552ef  mov     rcx, [rsp+98h+pv]
0x1800552f7  test    rcx, rcx
0x1800552fa  jz      short loc_180055309
0x1800552fc  mov     rax, [rcx]
0x1800552ff  mov     rax, [rax+10h]
0x180055303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055308  nop
0x180055309  xor     eax, eax
0x18005530b  add     rsp, 68h
0x18005530f  pop     r15
0x180055311  pop     r14
0x180055313  pop     r12
0x180055315  pop     rdi
0x180055316  pop     rsi
0x180055317  pop     rbx
0x180055318  retn
0x180055319  test    r15, r15
0x18005531c  jnz     loc_1800553DB
0x180055322  mov     [rsp+98h+pv], r12
0x18005532a  lea     rax, [rsp+98h+pv]
0x180055332  mov     [rsp+98h+var_58], rax
0x180055337  mov     [rsp+98h+var_50], r12
0x18005533c  mov     [rsp+98h+var_48], 1
0x180055341  lea     rcx, [rsp+98h+var_50]; this
0x180055346  call    ?GetCallingProcessPackageFamilyName@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageFamilyName(ushort * *)
0x18005534b  mov     rcx, [rsp+98h]; this
0x180055353  test    eax, eax
0x180055355  js      short loc_1800553C6
0x180055357  lea     rcx, [rsp+98h+var_58]
0x18005535c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180055361  mov     r8, [rsp+98h+pv]
0x180055369  mov     rdx, r14
0x18005536c  lea     rcx, [rsp+98h+hObject]
0x180055371  call    ?CloudStorePolicy_CreateInstance@Policy@Cloud@Storage@Internal@Windows@@YA?AV?$com_ptr_t@UICloudStorePolicy@Policy@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@PEAUIWebAccount@Credentials@Security@5@PEBG@Z; Windows::Internal::Storage::Cloud::Policy::CloudStorePolicy_CreateInstance(Windows::Security::Credentials::IWebAccount *,ushort const *)
0x180055376  mov     rcx, [rax]
0x180055379  mov     [rax], r12
0x18005537c  mov     [rbx], rcx
0x18005537f  mov     rcx, [rsp+98h+hObject]
0x180055384  test    rcx, rcx
0x180055387  jz      short loc_180055396
0x180055389  mov     rax, [rcx]
0x18005538c  mov     rax, [rax+10h]
0x180055390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055395  nop
0x180055396  mov     rcx, [rsp+98h+pv]; pv
0x18005539e  test    rcx, rcx
0x1800553a1  jz      short loc_1800553AA
0x1800553a3  call    cs:__imp_CoTaskMemFree
0x1800553a9  nop
0x1800553aa  xor     eax, eax
0x1800553ac  jmp     loc_18005530B
0x1800553b1  mov     r9d, edi; char *
0x1800553b4  lea     r8, aOnecoreuapShel_67; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800553bb  mov     edx, 1D2h; void *
0x1800553c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800553c6  mov     r9d, eax; char *
0x1800553c9  lea     r8, aOnecoreuapShel_67; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800553d0  mov     edx, 1DAh; void *
0x1800553d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800553db  mov     byte ptr [rsp+98h+pv], r12b
0x1800553e3  lea     rdx, [rsp+98h+pv]; unsigned __int16 *
0x1800553eb  lea     rcx, aActivitysystem; "activitySystem"
0x1800553f2  call    ?CheckCallerCapability@CallerIdentity@@YAJPEBGPEA_N@Z; CallerIdentity::CheckCallerCapability(ushort const *,bool *)
0x1800553f7  mov     rcx, [rsp+98h]; this
0x1800553ff  test    eax, eax
0x180055401  jns     loc_1800554FD
0x180055407  mov     r9d, eax; char *
0x18005540a  lea     r8, aOnecoreuapShel_67; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180055411  mov     edx, 1E2h; void *
0x180055416  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005541b  mov     [rsp+98h+pv], r12
0x180055423  lea     rax, [rsp+98h+pv]
0x18005542b  mov     [rsp+98h+var_58], rax
0x180055430  mov     [rsp+98h+var_50], r12
0x180055435  mov     [rsp+98h+var_48], 1
0x18005543a  lea     rcx, [rsp+98h+var_50]; this
0x18005543f  call    ?GetCallingProcessPackageFamilyName@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageFamilyName(ushort * *)
0x180055444  mov     rcx, [rsp+98h]; this
0x18005544c  test    eax, eax
0x18005544e  jns     short loc_180055465
0x180055450  mov     r9d, eax; char *
0x180055453  lea     r8, aOnecoreuapShel_67; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005545a  mov     edx, 1F0h; void *
0x18005545f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180055465  lea     rcx, [rsp+98h+var_58]
0x18005546a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005546f  xor     edx, edx; length
0x180055471  mov     rcx, r15; string
0x180055474  call    cs:__imp_WindowsGetStringRawBuffer
0x18005547a  mov     rdi, [rsp+98h]
0x180055482  mov     [rsp+98h+bIgnoreCase], 1; int
0x18005548a  or      edx, 0FFFFFFFFh; cchCount1
0x18005548d  mov     r9d, edx; cchCount2
0x180055490  mov     r8, [rsp+98h+pv]; lpString2
0x180055498  mov     rcx, rax; lpString1
0x18005549b  call    cs:__imp_CompareStringOrdinal
0x1800554a1  cmp     eax, 2
0x1800554a4  jnz     loc_180055551
0x1800554aa  mov     r8, [rsp+98h+pv]
0x1800554b2  mov     rdx, r14
0x1800554b5  lea     rcx, [rsp+98h+hObject]
0x1800554ba  call    ?CloudStorePolicy_CreateInstance@Policy@Cloud@Storage@Internal@Windows@@YA?AV?$com_ptr_t@UICloudStorePolicy@Policy@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@PEAUIWebAccount@Credentials@Security@5@PEBG@Z; Windows::Internal::Storage::Cloud::Policy::CloudStorePolicy_CreateInstance(Windows::Security::Credentials::IWebAccount *,ushort const *)
0x1800554bf  mov     rcx, [rax]
0x1800554c2  mov     [rax], r12
0x1800554c5  mov     [rbx], rcx
0x1800554c8  lea     rcx, [rsp+98h+hObject]
0x1800554cd  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800554d2  nop
0x1800554d3  lea     rcx, [rsp+98h+pv]
0x1800554db  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800554e0  nop
0x1800554e1  lea     rcx, [rsp+98h+var_60]
0x1800554e6  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800554eb  xor     eax, eax
0x1800554ed  jmp     loc_18005530B
0x1800554f2  call    cs:__imp_CloseHandle
0x1800554f8  jmp     loc_1800552B3
0x1800554fd  cmp     byte ptr [rsp+98h+pv], r12b
0x180055505  jz      loc_18005541B
0x18005550b  xor     edx, edx; length
0x18005550d  mov     rcx, r15; string
0x180055510  call    cs:__imp_WindowsGetStringRawBuffer
0x180055516  mov     r8, rax
0x180055519  mov     rdx, r14
0x18005551c  lea     rcx, [rsp+98h+pv]
0x180055524  call    ?CloudStorePolicy_CreateInstance@Policy@Cloud@Storage@Internal@Windows@@YA?AV?$com_ptr_t@UICloudStorePolicy@Policy@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@PEAUIWebAccount@Credentials@Security@5@PEBG@Z; Windows::Internal::Storage::Cloud::Policy::CloudStorePolicy_CreateInstance(Windows::Security::Credentials::IWebAccount *,ushort const *)
0x180055529  mov     rcx, [rax]
0x18005552c  mov     [rax], r12
0x18005552f  mov     [rbx], rcx
0x180055532  lea     rcx, [rsp+98h+pv]
0x18005553a  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18005553f  nop
0x180055540  lea     rcx, [rsp+98h+var_60]
0x180055545  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18005554a  xor     eax, eax
0x18005554c  jmp     loc_18005530B
0x180055551  mov     r9d, 80070005h; char *
0x180055557  lea     r8, aOnecoreuapShel_67; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005555e  mov     edx, 1F3h; void *
0x180055563  mov     rcx, rdi; this
0x180055566  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005556c  mov     eax, dword ptr [rsp+98h+pv]
0x180055573  jmp     loc_18005530B
```
