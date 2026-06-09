# Windows::Internal::AssignedAccess::DeviceConfigurationOperationBuilderFactory::RuntimeClassInitialize(Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *,bool)

- ea: `0x1800345f4`
- end: `0x1800348af`
- name: `?RuntimeClassInitialize@DeviceConfigurationOperationBuilderFactory@AssignedAccess@Internal@Windows@@QEAAJPEAUIAssignedAccessConfiguration@234@_N@Z`
- size: `699`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::DeviceConfigurationOperationBuilderFactory *__hidden this, struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *, bool)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002b8e0`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180010c98`
- `0x180021514`
- `0x180021548`
- `0x1800221e0`
- `0x180022d00`
- `0x180022e34`
- `0x180024544`
- `0x18002be50`
- `0x1800301b0`
- `0x1800345f4`
- `0x180096010`

## string_xrefs

- `0x1800347cc`: `AssignedAccessConfiguration`
- `0x1800347d3`: `SOFTWARE\Microsoft\Windows\AssignedAccessConfiguration`
- `0x180034781`: `onecoreuap\base\embedded\sys\lockdown\inc\assignedaccessconfigurationhelper.h`
- `0x180034639`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180034686`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x18003473a`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x1800347ac`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x1800347ec`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::AssignedAccess::DeviceConfigurationOperationBuilderFactory::RuntimeClassInitialize(
        Windows::Internal::AssignedAccess::DeviceConfigurationOperationBuilderFactory *this,
        struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *a2,
        char a3)
{
  int v7; // edi
  __int64 v8; // rdx
  char v9; // al
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rdx
  int UserInfoIf__lambda_1b1ae764da3b428e482f7810fbe3be4a; // eax
  int v14; // ebx
  int RedirectedPathIfNeeded; // eax
  unsigned __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // [rsp+20h] [rbp-29h] BYREF
  __int64 v20; // [rsp+28h] [rbp-21h] BYREF
  int v21; // [rsp+30h] [rbp-19h] BYREF
  __int64 v22; // [rsp+38h] [rbp-11h] BYREF
  Windows::Internal::AssignedAccess::DeviceConfigurationOperationBuilderFactory *v23; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v24[32]; // [rsp+48h] [rbp-1h] BYREF
  _BYTE v25[32]; // [rsp+68h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C6,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
      (const char *)0x80070057LL,
      v19);
    return 2147942487LL;
  }
  wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>::operator=(
    (char *)this + 248,
    a2);
  *((_BYTE *)this + 22) = a3;
  v7 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *, char *))(*(_QWORD *)a2 + 56LL))(
         a2,
         (char *)this + 17);
  if ( v7 >= 0 )
  {
    LOWORD(v19) = 0;
    v7 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *, int *))(*(_QWORD *)a2 + 48LL))(
           a2,
           &v19);
    if ( v7 < 0 )
    {
      v8 = 461;
      goto LABEL_5;
    }
    v7 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *, char *))(*(_QWORD *)a2 + 112LL))(
           a2,
           (char *)&v19 + 1);
    if ( v7 < 0 )
    {
      v8 = 462;
      goto LABEL_5;
    }
    if ( (_BYTE)v19 || (v9 = 0, BYTE1(v19)) )
      v9 = 1;
    *((_BYTE *)this + 18) = v9;
    v10 = *(_QWORD *)a2;
    v22 = 0;
    v11 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *, __int64 *))(v10 + 80))(
            a2,
            &v22);
    v7 = v11;
    if ( v11 >= 0 )
    {
      v21 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 56LL))(v22, &v21);
      v7 = v11;
      if ( v11 >= 0 )
      {
        *((_BYTE *)this + 16) = v21 == 0;
        v23 = this;
        v20 = 0;
        UserInfoIf__lambda_1b1ae764da3b428e482f7810fbe3be4a = Windows::Internal::AssignedAccess::AssignedAccessConfigurationHelper::FindUserInfoIf__lambda_1b1ae764da3b428e482f7810fbe3be4a___(
                                                                &v23,
                                                                a2,
                                                                &v20);
        v14 = UserInfoIf__lambda_1b1ae764da3b428e482f7810fbe3be4a;
        if ( UserInfoIf__lambda_1b1ae764da3b428e482f7810fbe3be4a >= 0 )
          v14 = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x26,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\inc\\assignedaccessconfigurationhelper.h",
            (const char *)(unsigned int)UserInfoIf__lambda_1b1ae764da3b428e482f7810fbe3be4a,
            v19);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v20);
        if ( v14 >= 0 )
        {
          v20 = 0;
          RedirectedPathIfNeeded = Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(
                                     (__int64)L"SOFTWARE\\Microsoft\\Windows\\AssignedAccessConfiguration",
                                     (__int64)L"AssignedAccessConfiguration",
                                     (__int64)&v20);
          v7 = RedirectedPathIfNeeded;
          if ( RedirectedPathIfNeeded >= 0 )
          {
            v16 = -1;
            do
              ++v16;
            while ( *(_WORD *)(v20 + 2 * v16) );
            std::wstring::_Assign<unsigned short>((__int64)this + 184, v20, v16);
            v17 = std::operator+<unsigned short>(v25, (char *)this + 184, L"\\");
            v18 = std::operator+<unsigned short>(v24, v17, L"Snapshot");
            std::wstring::operator=((char *)this + 216, v18);
            std::wstring::_Tidy_deallocate(v24);
            std::wstring::_Tidy_deallocate(v25);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
            v7 = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x20D,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
              (const char *)(unsigned int)RedirectedPathIfNeeded,
              v19);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x20B,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
            (const char *)(unsigned int)v14,
            v19);
          v7 = v14;
        }
        goto LABEL_28;
      }
      v12 = 468;
    }
    else
    {
      v12 = 466;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
      (const char *)(unsigned int)v11,
      v19);
LABEL_28:
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v22);
    return (unsigned int)v7;
  }
  v8 = 457;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
    (const char *)(unsigned int)v7,
    v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800345f4  mov     [rsp-8+arg_10], rbx
0x1800345f9  mov     [rsp-8+arg_18], rsi
0x1800345fe  push    rbp
0x1800345ff  push    rdi
0x180034600  push    r14
0x180034602  lea     rbp, [rsp-47h]
0x180034607  sub     rsp, 90h
0x18003460e  mov     rax, cs:__security_cookie
0x180034615  xor     rax, rsp
0x180034618  mov     [rbp+57h+var_18], rax
0x18003461c  mov     dil, r8b
0x18003461f  mov     rbx, rdx
0x180034622  mov     rsi, rcx
0x180034625  xor     r14d, r14d
0x180034628  test    rdx, rdx
0x18003462b  jnz     short loc_180034651
0x18003462d  mov     rcx, [rbp+5Fh]; this
0x180034631  mov     ebx, 80070057h
0x180034636  mov     r9d, ebx; char *
0x180034639  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180034640  mov     edx, 1C6h; void *
0x180034645  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003464a  mov     eax, ebx
0x18003464c  jmp     loc_18003488B
0x180034651  add     rcx, 0F8h
0x180034658  call    ??4?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>::operator=(Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *)
0x18003465d  mov     [rsi+16h], dil
0x180034661  mov     rax, [rbx]
0x180034664  lea     rdx, [rsi+11h]
0x180034668  mov     rcx, rbx
0x18003466b  mov     rax, [rax+38h]
0x18003466f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034674  mov     edi, eax
0x180034676  test    eax, eax
0x180034678  jns     short loc_180034697
0x18003467a  mov     edx, 1C9h; void *
0x18003467f  mov     rcx, [rbp+5Fh]; this
0x180034683  mov     r9d, edi; char *
0x180034686  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18003468d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034692  jmp     loc_180034889
0x180034697  mov     [rbp+57h+var_80], r14b
0x18003469b  mov     [rbp+57h+var_7F], r14b
0x18003469f  mov     rax, [rbx]
0x1800346a2  lea     rdx, [rbp+57h+var_80]
0x1800346a6  mov     rcx, rbx
0x1800346a9  mov     rax, [rax+30h]
0x1800346ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800346b2  mov     edi, eax
0x1800346b4  test    eax, eax
0x1800346b6  jns     short loc_1800346BF
0x1800346b8  mov     edx, 1CDh
0x1800346bd  jmp     short loc_18003467F
0x1800346bf  mov     rax, [rbx]
0x1800346c2  lea     rdx, [rbp+57h+var_7F]
0x1800346c6  mov     rcx, rbx
0x1800346c9  mov     rax, [rax+70h]
0x1800346cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800346d2  mov     edi, eax
0x1800346d4  test    eax, eax
0x1800346d6  jns     short loc_1800346DF
0x1800346d8  mov     edx, 1CEh
0x1800346dd  jmp     short loc_18003467F
0x1800346df  cmp     [rbp+57h+var_80], r14b
0x1800346e3  jnz     short loc_1800346EE
0x1800346e5  cmp     [rbp+57h+var_7F], r14b
0x1800346e9  mov     al, r14b
0x1800346ec  jz      short loc_1800346F0
0x1800346ee  mov     al, 1
0x1800346f0  mov     [rsi+12h], al
0x1800346f3  mov     rax, [rbx]
0x1800346f6  mov     [rbp+57h+var_68], r14
0x1800346fa  lea     rdx, [rbp+57h+var_68]
0x1800346fe  mov     rcx, rbx
0x180034701  mov     rax, [rax+50h]
0x180034705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003470a  mov     edi, eax
0x18003470c  test    eax, eax
0x18003470e  jns     short loc_180034717
0x180034710  mov     edx, 1D2h
0x180034715  jmp     short loc_18003473A
0x180034717  mov     [rbp+57h+var_70], r14d
0x18003471b  mov     rcx, [rbp+57h+var_68]
0x18003471f  mov     rax, [rcx]
0x180034722  lea     rdx, [rbp+57h+var_70]
0x180034726  mov     rax, [rax+38h]
0x18003472a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003472f  mov     edi, eax
0x180034731  test    eax, eax
0x180034733  jns     short loc_180034752
0x180034735  mov     edx, 1D4h; void *
0x18003473a  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180034741  mov     r9d, eax; char *
0x180034744  mov     rcx, [rbp+5Fh]; this
0x180034748  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003474d  jmp     loc_180034880
0x180034752  cmp     [rbp+57h+var_70], r14d
0x180034756  setz    al
0x180034759  mov     [rsi+10h], al
0x18003475c  mov     [rbp+57h+var_60], rsi
0x180034760  mov     [rbp+57h+var_78], r14
0x180034764  lea     r8, [rbp+57h+var_78]
0x180034768  mov     rdx, rbx
0x18003476b  lea     rcx, [rbp+57h+var_60]
0x18003476f  call    Windows__Internal__AssignedAccess__AssignedAccessConfigurationHelper__FindUserInfoIf__lambda_1b1ae764da3b428e482f7810fbe3be4a___
0x180034774  mov     ebx, eax
0x180034776  test    eax, eax
0x180034778  jns     short loc_180034795
0x18003477a  mov     rcx, [rbp+5Fh]; this
0x18003477e  mov     r9d, eax; char *
0x180034781  lea     r8, aOnecoreuapBase_91; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180034788  mov     edx, 26h ; '&'; void *
0x18003478d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034792  nop
0x180034793  jmp     short loc_180034798
0x180034795  mov     ebx, r14d
0x180034798  lea     rcx, [rbp+57h+var_78]
0x18003479c  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800347a1  test    ebx, ebx
0x1800347a3  jns     short loc_1800347C4
0x1800347a5  mov     rcx, [rbp+5Fh]; this
0x1800347a9  mov     r9d, ebx; char *
0x1800347ac  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800347b3  mov     edx, 20Bh; void *
0x1800347b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800347bd  mov     edi, ebx
0x1800347bf  jmp     loc_180034880
0x1800347c4  mov     [rbp+57h+var_78], r14
0x1800347c8  lea     r8, [rbp+57h+var_78]
0x1800347cc  lea     rdx, aAssignedaccess_6; "AssignedAccessConfiguration"
0x1800347d3  lea     rcx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\AssignedA"...
0x1800347da  call    ?GetRedirectedPathIfNeeded@PersistentLocationHelper@AssignedAccess@Internal@Windows@@SAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800347df  mov     edi, eax
0x1800347e1  test    eax, eax
0x1800347e3  jns     short loc_180034809
0x1800347e5  mov     rcx, [rbp+5Fh]; this
0x1800347e9  mov     r9d, eax; char *
0x1800347ec  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800347f3  mov     edx, 20Dh; void *
0x1800347f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800347fd  nop
0x1800347fe  lea     rcx, [rbp+57h+var_78]
0x180034802  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034807  jmp     short loc_180034880
0x180034809  mov     rdx, [rbp+57h+var_78]
0x18003480d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180034811  inc     r8
0x180034814  cmp     [rdx+r8*2], r14w
0x180034819  jnz     short loc_180034811
0x18003481b  lea     rbx, [rsi+0B8h]
0x180034822  mov     rcx, rbx
0x180034825  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18003482a  lea     r8, S; "\\"
0x180034831  mov     rdx, rbx
0x180034834  lea     rcx, [rbp+57h+var_38]
0x180034838  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18003483d  nop
0x18003483e  lea     r8, aSnapshot; "Snapshot"
0x180034845  mov     rdx, rax
0x180034848  lea     rcx, [rbp+57h+var_58]
0x18003484c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180034851  lea     rcx, [rsi+0D8h]
0x180034858  mov     rdx, rax
0x18003485b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180034860  lea     rcx, [rbp+57h+var_58]
0x180034864  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034869  nop
0x18003486a  lea     rcx, [rbp+57h+var_38]
0x18003486e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034873  nop
0x180034874  lea     rcx, [rbp+57h+var_78]
0x180034878  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003487d  mov     edi, r14d
0x180034880  lea     rcx, [rbp+57h+var_68]
0x180034884  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180034889  mov     eax, edi
0x18003488b  mov     rcx, [rbp+57h+var_18]
0x18003488f  xor     rcx, rsp; StackCookie
0x180034892  call    __security_check_cookie
0x180034897  lea     r11, [rsp+0A0h+var_10]
0x18003489f  mov     rbx, [r11+30h]
0x1800348a3  mov     rsi, [r11+38h]
0x1800348a7  mov     rsp, r11
0x1800348aa  pop     r14
0x1800348ac  pop     rdi
0x1800348ad  pop     rbp
0x1800348ae  retn
```
