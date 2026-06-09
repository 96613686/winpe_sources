# AppServiceResourceHandler::GetResourceInternal(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,ICDPResourceHandlerCallback *)

- ea: `0x180028a64`
- end: `0x180028eac`
- name: `?GetResourceInternal@AppServiceResourceHandler@@AEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAVICDPResourceHandlerCallback@@@Z`
- size: `1096`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003f490`

## callees

- `0x180002a4c`
- `0x180003678`
- `0x1800041b0`
- `0x180004a58`
- `0x1800097d0`
- `0x18000ecb8`
- `0x18001e0f0`
- `0x180020cc4`
- `0x180025160`
- `0x180028a64`
- `0x180029304`
- `0x180029330`
- `0x18002c570`
- `0x18003eecc`
- `0x1800401d8`
- `0x180040854`
- `0x1800411c4`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028acd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028af6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028acd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028af6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028bd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028bea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028c86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028c9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028dda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028dee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028e49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028e5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028bd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028bea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028c86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028c9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028dda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028dee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028e49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028e5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall AppServiceResourceHandler::GetResourceInternal(__int64 a1, __int64 a2, __int64 *a3)
{
  std::_Ref_count_base *v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int ResourceRequestValueSet; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  AppServiceHelper *v17; // rbx
  int ResourceValFromResponseValueSet; // r14d
  __int64 v19; // rcx
  __int64 v20; // rdi
  __int64 v21; // rbx
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // [rsp+40h] [rbp-C8h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B8h] BYREF
  HSTRING v29; // [rsp+58h] [rbp-B0h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v30; // [rsp+60h] [rbp-A8h] BYREF
  AppServiceHelper *v31; // [rsp+68h] [rbp-A0h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v32; // [rsp+70h] [rbp-98h] BYREF
  std::_Ref_count_base *v33[2]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v34[32]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v35[32]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v36[32]; // [rsp+C8h] [rbp-40h] BYREF

  *(_OWORD *)v33 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, a1 + 40);
  std::_Tree<std::_Tmap_traits<std::string,std::shared_ptr<CDPAppSvcApplication>,std::less<std::string>,std::allocator<std::pair<std::string const,std::shared_ptr<CDPAppSvcApplication>>>,0>>::find(
    a1 + 48,
    &v26,
    a2);
  if ( v26 == *(_QWORD *)(a1 + 48) )
  {
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return 2147750145LL;
  }
  else
  {
    std::shared_ptr<CDPAppSvcApplication>::operator=(v33, v26 + 64);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v7 = v33[0];
    v8 = std::_String_val<std::_Simple_types<char>>::_Myptr((char *)v33[0] + 32);
    std::string::string((__int64)v35, v8);
    cdp::UTF8toHSTRING(&v29, v35);
    std::string::_Tidy_deallocate(v35);
    v9 = std::_String_val<std::_Simple_types<char>>::_Myptr((char *)v7 + 64);
    std::string::string((__int64)v36, v9);
    cdp::UTF8toHSTRING(&string, v36);
    std::string::_Tidy_deallocate(v36);
    v30 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    ResourceRequestValueSet = AppServiceResourceHandler::ConstructGetResourceRequestValueSet(v10, a2, v33, &v30);
    if ( ResourceRequestValueSet >= 0 )
    {
      v32 = 0;
      v31 = 0;
      v14 = Microsoft::WRL::Details::MakeAndInitialize<AppServiceHelper,AppServiceHelper,>(&v31);
      if ( v14 >= 0 )
      {
        v17 = v31;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
        ResourceValFromResponseValueSet = AppServiceHelper::OpenAppServiceAndSendMessageAsync(
                                            v17,
                                            v29,
                                            string,
                                            0,
                                            0,
                                            v30,
                                            &v32,
                                            0);
        std::string::string(v34);
        if ( ResourceValFromResponseValueSet >= 0 )
          ResourceValFromResponseValueSet = AppServiceResourceHandler::GetResourceValFromResponseValueSet(
                                              v19,
                                              v32,
                                              v33,
                                              v34);
        v20 = std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
        v21 = *a3;
        v22 = std::_String_val<std::_Simple_types<char>>::_Myptr(v34);
        v23 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, __int64, __int64))(v21 + 24))(
                a3,
                (unsigned int)ResourceValFromResponseValueSet,
                1,
                v20,
                v22);
        if ( v23 >= 0 )
        {
          std::string::_Tidy_deallocate(v34);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(v29);
          v29 = 0;
          if ( v33[1] )
            std::_Ref_count_base::_Decref(v33[1]);
          return 0;
        }
        else
        {
          LODWORD(v26) = v23;
          LODWORD(SRWLock) = 206;
          Log<long &,char const (&)[40],int>(v25, v24, &v26, "..\\appsvcresourcehandler.cpp", &SRWLock);
          std::string::_Tidy_deallocate(v34);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(v29);
          v29 = 0;
          if ( v33[1] )
            std::_Ref_count_base::_Decref(v33[1]);
          return (unsigned int)v26;
        }
      }
      else
      {
        LODWORD(v26) = v14;
        LODWORD(SRWLock) = 195;
        Log<long &,char const (&)[40],int>(v16, v15, &v26, "..\\appsvcresourcehandler.cpp", &SRWLock);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v29);
        v29 = 0;
        if ( v33[1] )
          std::_Ref_count_base::_Decref(v33[1]);
        return (unsigned int)v26;
      }
    }
    else
    {
      LODWORD(v26) = ResourceRequestValueSet;
      LODWORD(SRWLock) = 192;
      Log<long &,char const (&)[40],int>(v13, v12, &v26, "..\\appsvcresourcehandler.cpp", &SRWLock);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v29);
      v29 = 0;
      if ( v33[1] )
        std::_Ref_count_base::_Decref(v33[1]);
      return (unsigned int)v26;
    }
  }
}

```

## disassembly

```asm
0x180028a64  mov     [rsp+arg_18], rbx
0x180028a69  push    rdi
0x180028a6a  push    r14
0x180028a6c  push    r15
0x180028a6e  sub     rsp, 0F0h
0x180028a75  mov     rax, cs:__security_cookie
0x180028a7c  xor     rax, rsp
0x180028a7f  mov     [rsp+108h+var_20], rax
0x180028a87  mov     r15, r8
0x180028a8a  mov     rdi, rdx
0x180028a8d  mov     rbx, rcx
0x180028a90  xorps   xmm0, xmm0
0x180028a93  movdqu  xmmword ptr [rsp+108h+var_90], xmm0
0x180028a99  lea     rdx, [rcx+28h]
0x180028a9d  lea     rcx, [rsp+108h+SRWLock]
0x180028aa2  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180028aa7  mov     r8, rdi
0x180028aaa  lea     rdx, [rsp+108h+var_C8]
0x180028aaf  lea     rcx, [rbx+30h]
0x180028ab3  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UCDPAppSvcApplication@@@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UCDPAppSvcApplication@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UCDPAppSvcApplication@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::string,std::shared_ptr<CDPAppSvcApplication>,std::less<std::string>,std::allocator<std::pair<std::string const,std::shared_ptr<CDPAppSvcApplication>>>,0>>::find(std::string const &)
0x180028ab8  mov     rdx, [rsp+108h+var_C8]
0x180028abd  cmp     rdx, [rbx+30h]
0x180028ac1  jnz     short loc_180028ADE
0x180028ac3  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x180028ac8  test    rcx, rcx
0x180028acb  jz      short loc_180028AD4
0x180028acd  call    cs:__imp_ReleaseSRWLockExclusive
0x180028ad3  nop
0x180028ad4  mov     eax, 80041101h
0x180028ad9  jmp     loc_180028E86
0x180028ade  add     rdx, 40h ; '@'
0x180028ae2  lea     rcx, [rsp+108h+var_90]
0x180028ae7  call    ??4?$shared_ptr@UCDPAppSvcApplication@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CDPAppSvcApplication>::operator=(std::shared_ptr<CDPAppSvcApplication> const &)
0x180028aec  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x180028af1  test    rcx, rcx
0x180028af4  jz      short loc_180028AFC
0x180028af6  call    cs:__imp_ReleaseSRWLockExclusive
0x180028afc  mov     rbx, [rsp+108h+var_90]
0x180028b01  lea     rcx, [rbx+20h]
0x180028b05  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180028b0a  mov     rdx, rax
0x180028b0d  lea     rcx, [rsp+108h+var_60]
0x180028b15  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028b1a  nop
0x180028b1b  lea     rdx, [rsp+108h+var_60]
0x180028b23  lea     rcx, [rsp+108h+var_B0]
0x180028b28  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x180028b2d  nop
0x180028b2e  lea     rcx, [rsp+108h+var_60]
0x180028b36  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180028b3b  lea     rcx, [rbx+40h]
0x180028b3f  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180028b44  mov     rdx, rax
0x180028b47  lea     rcx, [rsp+108h+var_40]
0x180028b4f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028b54  nop
0x180028b55  lea     rdx, [rsp+108h+var_40]
0x180028b5d  lea     rcx, [rsp+108h+string]
0x180028b62  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x180028b67  nop
0x180028b68  lea     rcx, [rsp+108h+var_40]
0x180028b70  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180028b75  mov     [rsp+108h+var_A8], 0
0x180028b7e  lea     rcx, [rsp+108h+var_A8]
0x180028b83  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028b88  lea     r9, [rsp+108h+var_A8]
0x180028b8d  lea     r8, [rsp+108h+var_90]
0x180028b92  mov     rdx, rdi
0x180028b95  call    ?ConstructGetResourceRequestValueSet@AppServiceResourceHandler@@AEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$shared_ptr@UCDPAppSvcApplication@@@3@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; AppServiceResourceHandler::ConstructGetResourceRequestValueSet(std::string const &,std::shared_ptr<CDPAppSvcApplication> const &,Windows::Foundation::Collections::IPropertySet * *)
0x180028b9a  test    eax, eax
0x180028b9c  jns     short loc_180028C14
0x180028b9e  mov     dword ptr [rsp+108h+var_C8], eax
0x180028ba2  mov     dword ptr [rsp+108h+SRWLock], 0C0h
0x180028baa  lea     rax, [rsp+108h+SRWLock]
0x180028baf  mov     [rsp+108h+var_E8], rax
0x180028bb4  lea     r9, aAppsvcresource; "..\\appsvcresourcehandler.cpp"
0x180028bbb  lea     r8, [rsp+108h+var_C8]
0x180028bc0  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180028bc5  nop
0x180028bc6  lea     rcx, [rsp+108h+var_A8]
0x180028bcb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028bd0  nop
0x180028bd1  mov     rcx, [rsp+108h+string]; string
0x180028bd6  call    cs:__imp_WindowsDeleteString
0x180028bdc  mov     [rsp+108h+string], 0
0x180028be5  mov     rcx, [rsp+108h+var_B0]; string
0x180028bea  call    cs:__imp_WindowsDeleteString
0x180028bf0  mov     [rsp+108h+var_B0], 0
0x180028bf9  mov     rcx, [rsp+108h+var_90+8]; this
0x180028c01  test    rcx, rcx
0x180028c04  jz      short loc_180028C0B
0x180028c06  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180028c0b  mov     eax, dword ptr [rsp+108h+var_C8]
0x180028c0f  jmp     loc_180028E86
0x180028c14  mov     [rsp+108h+var_98], 0
0x180028c1d  mov     [rsp+108h+var_A0], 0
0x180028c26  lea     rcx, [rsp+108h+var_A0]
0x180028c2b  call    ??$MakeAndInitialize@VAppServiceHelper@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VAppServiceHelper@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppServiceHelper,AppServiceHelper,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<AppServiceHelper>>)
0x180028c30  test    eax, eax
0x180028c32  jns     loc_180028CC4
0x180028c38  mov     dword ptr [rsp+108h+var_C8], eax
0x180028c3c  mov     dword ptr [rsp+108h+SRWLock], 0C3h
0x180028c44  lea     rax, [rsp+108h+SRWLock]
0x180028c49  mov     [rsp+108h+var_E8], rax
0x180028c4e  lea     r9, aAppsvcresource; "..\\appsvcresourcehandler.cpp"
0x180028c55  lea     r8, [rsp+108h+var_C8]
0x180028c5a  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180028c5f  nop
0x180028c60  lea     rcx, [rsp+108h+var_A0]
0x180028c65  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028c6a  nop
0x180028c6b  lea     rcx, [rsp+108h+var_98]
0x180028c70  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028c75  nop
0x180028c76  lea     rcx, [rsp+108h+var_A8]
0x180028c7b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028c80  nop
0x180028c81  mov     rcx, [rsp+108h+string]; string
0x180028c86  call    cs:__imp_WindowsDeleteString
0x180028c8c  mov     [rsp+108h+string], 0
0x180028c95  mov     rcx, [rsp+108h+var_B0]; string
0x180028c9a  call    cs:__imp_WindowsDeleteString
0x180028ca0  mov     [rsp+108h+var_B0], 0
0x180028ca9  mov     rcx, [rsp+108h+var_90+8]; this
0x180028cb1  test    rcx, rcx
0x180028cb4  jz      short loc_180028CBB
0x180028cb6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180028cbb  mov     eax, dword ptr [rsp+108h+var_C8]
0x180028cbf  jmp     loc_180028E86
0x180028cc4  mov     rbx, [rsp+108h+var_A0]
0x180028cc9  lea     rcx, [rsp+108h+var_98]
0x180028cce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028cd3  mov     rax, [rsp+108h+var_A8]
0x180028cd8  mov     [rsp+108h+var_D0], 0; HSTRING *
0x180028ce1  lea     rcx, [rsp+108h+var_98]
0x180028ce6  mov     [rsp+108h+var_D8], rcx; struct Windows::Foundation::Collections::IPropertySet **
0x180028ceb  mov     [rsp+108h+var_E0], rax; struct Windows::Foundation::Collections::IPropertySet *
0x180028cf0  mov     [rsp+108h+var_E8], 0; HSTRING
0x180028cf9  xor     r9d, r9d; HSTRING
0x180028cfc  mov     r8, [rsp+108h+string]; HSTRING
0x180028d01  mov     rdx, [rsp+108h+var_B0]; HSTRING
0x180028d06  mov     rcx, rbx; this
0x180028d09  call    ?OpenAppServiceAndSendMessageAsync@AppServiceHelper@@QEAAJPEAUHSTRING__@@000PEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU3456@PEAPEAU2@@Z; AppServiceHelper::OpenAppServiceAndSendMessageAsync(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IPropertySet * *,HSTRING__ * *)
0x180028d0e  mov     r14d, eax
0x180028d11  lea     rcx, [rsp+108h+var_80]
0x180028d19  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180028d1e  nop
0x180028d1f  test    r14d, r14d
0x180028d22  js      short loc_180028D3E
0x180028d24  lea     r9, [rsp+108h+var_80]
0x180028d2c  lea     r8, [rsp+108h+var_90]
0x180028d31  mov     rdx, [rsp+108h+var_98]
0x180028d36  call    ?GetResourceValFromResponseValueSet@AppServiceResourceHandler@@AEAAJPEAUIPropertySet@Collections@Foundation@Windows@@AEBV?$shared_ptr@UCDPAppSvcApplication@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@7@@Z; AppServiceResourceHandler::GetResourceValFromResponseValueSet(Windows::Foundation::Collections::IPropertySet *,std::shared_ptr<CDPAppSvcApplication> const &,std::string &)
0x180028d3b  mov     r14d, eax
0x180028d3e  mov     rcx, rdi
0x180028d41  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180028d46  mov     rdi, rax
0x180028d49  mov     rbx, [r15]
0x180028d4c  lea     rcx, [rsp+108h+var_80]
0x180028d54  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180028d59  mov     [rsp+108h+var_E8], rax
0x180028d5e  mov     r9, rdi
0x180028d61  mov     r8d, 1
0x180028d67  mov     edx, r14d
0x180028d6a  mov     rcx, r15
0x180028d6d  mov     rax, [rbx+18h]
0x180028d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d76  test    eax, eax
0x180028d78  jns     loc_180028E15
0x180028d7e  mov     dword ptr [rsp+108h+var_C8], eax
0x180028d82  mov     dword ptr [rsp+108h+SRWLock], 0CEh
0x180028d8a  lea     rax, [rsp+108h+SRWLock]
0x180028d8f  mov     [rsp+108h+var_E8], rax
0x180028d94  lea     r9, aAppsvcresource; "..\\appsvcresourcehandler.cpp"
0x180028d9b  lea     r8, [rsp+108h+var_C8]
0x180028da0  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180028da5  nop
0x180028da6  lea     rcx, [rsp+108h+var_80]
0x180028dae  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180028db3  nop
0x180028db4  lea     rcx, [rsp+108h+var_A0]
0x180028db9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028dbe  nop
0x180028dbf  lea     rcx, [rsp+108h+var_98]
0x180028dc4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028dc9  nop
0x180028dca  lea     rcx, [rsp+108h+var_A8]
0x180028dcf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028dd4  nop
0x180028dd5  mov     rcx, [rsp+108h+string]; string
0x180028dda  call    cs:__imp_WindowsDeleteString
0x180028de0  mov     [rsp+108h+string], 0
0x180028de9  mov     rcx, [rsp+108h+var_B0]; string
0x180028dee  call    cs:__imp_WindowsDeleteString
0x180028df4  mov     [rsp+108h+var_B0], 0
0x180028dfd  mov     rcx, [rsp+108h+var_90+8]; this
0x180028e05  test    rcx, rcx
0x180028e08  jz      short loc_180028E0F
0x180028e0a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180028e0f  mov     eax, dword ptr [rsp+108h+var_C8]
0x180028e13  jmp     short loc_180028E86
0x180028e15  lea     rcx, [rsp+108h+var_80]
0x180028e1d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180028e22  nop
0x180028e23  lea     rcx, [rsp+108h+var_A0]
0x180028e28  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028e2d  nop
0x180028e2e  lea     rcx, [rsp+108h+var_98]
0x180028e33  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028e38  nop
0x180028e39  lea     rcx, [rsp+108h+var_A8]
0x180028e3e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028e43  nop
0x180028e44  mov     rcx, [rsp+108h+string]; string
0x180028e49  call    cs:__imp_WindowsDeleteString
0x180028e4f  mov     [rsp+108h+string], 0
0x180028e58  mov     rcx, [rsp+108h+var_B0]; string
0x180028e5d  call    cs:__imp_WindowsDeleteString
0x180028e63  mov     [rsp+108h+var_B0], 0
0x180028e6c  mov     rcx, [rsp+108h+var_90+8]; this
0x180028e74  test    rcx, rcx
0x180028e77  jz      short loc_180028E7E
0x180028e79  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180028e7e  xor     eax, eax
0x180028e80  jmp     short loc_180028E86
0x180028e82  mov     eax, dword ptr [rsp+108h+SRWLock]
0x180028e86  mov     rcx, [rsp+108h+var_20]
0x180028e8e  xor     rcx, rsp; StackCookie
0x180028e91  call    __security_check_cookie
0x180028e96  mov     rbx, [rsp+108h+arg_18]
0x180028e9e  add     rsp, 0F0h
0x180028ea5  pop     r15
0x180028ea7  pop     r14
0x180028ea9  pop     rdi
0x180028eaa  retn
```
