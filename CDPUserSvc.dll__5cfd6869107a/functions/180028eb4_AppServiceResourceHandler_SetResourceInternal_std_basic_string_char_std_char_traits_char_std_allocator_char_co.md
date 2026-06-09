# AppServiceResourceHandler::SetResourceInternal(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,ICDPResourceHandlerCallback *)

- ea: `0x180028eb4`
- end: `0x1800292fd`
- name: `?SetResourceInternal@AppServiceResourceHandler@@AEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0PEAVICDPResourceHandlerCallback@@@Z`
- size: `1097`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003f4d0`

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
- `0x180028eb4`
- `0x180029304`
- `0x180029330`
- `0x18002c570`
- `0x18003eecc`
- `0x180040424`
- `0x180040854`
- `0x1800411c4`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028f1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028f46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028f1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028f46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002902e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800290de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800290f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029232`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800292a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800292b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002902e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800290de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800290f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029232`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800292a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800292b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall AppServiceResourceHandler::SetResourceInternal(__int64 a1, __int64 a2, int a3, __int64 *a4)
{
  std::_Ref_count_base *v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rdx
  int v12; // ecx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  AppServiceHelper *v19; // rbx
  int ResourceValFromResponseValueSet; // r14d
  __int64 v21; // rcx
  __int64 v22; // rdi
  __int64 v23; // rbx
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // [rsp+40h] [rbp-D8h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+50h] [rbp-C8h] BYREF
  HSTRING v31; // [rsp+58h] [rbp-C0h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v32; // [rsp+60h] [rbp-B8h] BYREF
  AppServiceHelper *v33; // [rsp+68h] [rbp-B0h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v34; // [rsp+70h] [rbp-A8h] BYREF
  std::_Ref_count_base *v35[2]; // [rsp+78h] [rbp-A0h] BYREF
  _BYTE v36[32]; // [rsp+88h] [rbp-90h] BYREF
  _BYTE v37[32]; // [rsp+A8h] [rbp-70h] BYREF
  _BYTE v38[32]; // [rsp+C8h] [rbp-50h] BYREF

  *(_OWORD *)v35 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, a1 + 40);
  std::_Tree<std::_Tmap_traits<std::string,std::shared_ptr<CDPAppSvcApplication>,std::less<std::string>,std::allocator<std::pair<std::string const,std::shared_ptr<CDPAppSvcApplication>>>,0>>::find(
    a1 + 48,
    &v28,
    a2);
  if ( v28 == *(_QWORD *)(a1 + 48) )
  {
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return 2147750145LL;
  }
  else
  {
    std::shared_ptr<CDPAppSvcApplication>::operator=(v35, v28 + 64);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v9 = v35[0];
    v10 = std::_String_val<std::_Simple_types<char>>::_Myptr((char *)v35[0] + 32);
    std::string::string((__int64)v37, v10);
    cdp::UTF8toHSTRING(&v31, v37);
    std::string::_Tidy_deallocate(v37);
    v11 = std::_String_val<std::_Simple_types<char>>::_Myptr((char *)v9 + 64);
    std::string::string((__int64)v38, v11);
    cdp::UTF8toHSTRING(&string, v38);
    std::string::_Tidy_deallocate(v38);
    v32 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    v13 = AppServiceResourceHandler::ConstructSetResourceRequestValueSet(v12, a2, a3, (unsigned int)v35, (__int64)&v32);
    if ( v13 >= 0 )
    {
      v34 = 0;
      v33 = 0;
      v16 = Microsoft::WRL::Details::MakeAndInitialize<AppServiceHelper,AppServiceHelper,>(&v33);
      if ( v16 >= 0 )
      {
        v19 = v33;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
        ResourceValFromResponseValueSet = AppServiceHelper::OpenAppServiceAndSendMessageAsync(
                                            v19,
                                            v31,
                                            string,
                                            0,
                                            0,
                                            v32,
                                            &v34,
                                            0);
        std::string::string(v36);
        if ( ResourceValFromResponseValueSet >= 0 )
          ResourceValFromResponseValueSet = AppServiceResourceHandler::GetResourceValFromResponseValueSet(
                                              v21,
                                              v34,
                                              v35,
                                              v36);
        v22 = std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
        v23 = *a4;
        v24 = std::_String_val<std::_Simple_types<char>>::_Myptr(v36);
        v25 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, __int64, __int64))(v23 + 24))(
                a4,
                (unsigned int)ResourceValFromResponseValueSet,
                2,
                v22,
                v24);
        if ( v25 >= 0 )
        {
          std::string::_Tidy_deallocate(v36);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(v31);
          v31 = 0;
          if ( v35[1] )
            std::_Ref_count_base::_Decref(v35[1]);
          return 0;
        }
        else
        {
          LODWORD(v28) = v25;
          LODWORD(SRWLock) = 246;
          Log<long &,char const (&)[40],int>(v27, v26, &v28, "..\\appsvcresourcehandler.cpp", &SRWLock);
          std::string::_Tidy_deallocate(v36);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(v31);
          v31 = 0;
          if ( v35[1] )
            std::_Ref_count_base::_Decref(v35[1]);
          return (unsigned int)v28;
        }
      }
      else
      {
        LODWORD(v28) = v16;
        LODWORD(SRWLock) = 235;
        Log<long &,char const (&)[40],int>(v18, v17, &v28, "..\\appsvcresourcehandler.cpp", &SRWLock);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v31);
        v31 = 0;
        if ( v35[1] )
          std::_Ref_count_base::_Decref(v35[1]);
        return (unsigned int)v28;
      }
    }
    else
    {
      LODWORD(v28) = v13;
      LODWORD(SRWLock) = 232;
      Log<long &,char const (&)[40],int>(v15, v14, &v28, "..\\appsvcresourcehandler.cpp", &SRWLock);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v31);
      v31 = 0;
      if ( v35[1] )
        std::_Ref_count_base::_Decref(v35[1]);
      return (unsigned int)v28;
    }
  }
}

```

## disassembly

```asm
0x180028eb4  push    rbx
0x180028eb6  push    rdi
0x180028eb7  push    r14
0x180028eb9  push    r15
0x180028ebb  sub     rsp, 0F8h
0x180028ec2  mov     rax, cs:__security_cookie
0x180028ec9  xor     rax, rsp
0x180028ecc  mov     [rsp+118h+var_30], rax
0x180028ed4  mov     r15, r9
0x180028ed7  mov     r14, r8
0x180028eda  mov     rdi, rdx
0x180028edd  mov     rbx, rcx
0x180028ee0  xorps   xmm0, xmm0
0x180028ee3  movdqu  xmmword ptr [rsp+118h+var_A0], xmm0
0x180028ee9  lea     rdx, [rcx+28h]
0x180028eed  lea     rcx, [rsp+118h+SRWLock]
0x180028ef2  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180028ef7  mov     r8, rdi
0x180028efa  lea     rdx, [rsp+118h+var_D8]
0x180028eff  lea     rcx, [rbx+30h]
0x180028f03  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UCDPAppSvcApplication@@@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UCDPAppSvcApplication@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UCDPAppSvcApplication@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::string,std::shared_ptr<CDPAppSvcApplication>,std::less<std::string>,std::allocator<std::pair<std::string const,std::shared_ptr<CDPAppSvcApplication>>>,0>>::find(std::string const &)
0x180028f08  mov     rdx, [rsp+118h+var_D8]
0x180028f0d  cmp     rdx, [rbx+30h]
0x180028f11  jnz     short loc_180028F2E
0x180028f13  mov     rcx, [rsp+118h+SRWLock]; SRWLock
0x180028f18  test    rcx, rcx
0x180028f1b  jz      short loc_180028F24
0x180028f1d  call    cs:__imp_ReleaseSRWLockExclusive
0x180028f23  nop
0x180028f24  mov     eax, 80041101h
0x180028f29  jmp     loc_1800292DE
0x180028f2e  add     rdx, 40h ; '@'
0x180028f32  lea     rcx, [rsp+118h+var_A0]
0x180028f37  call    ??4?$shared_ptr@UCDPAppSvcApplication@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CDPAppSvcApplication>::operator=(std::shared_ptr<CDPAppSvcApplication> const &)
0x180028f3c  mov     rcx, [rsp+118h+SRWLock]; SRWLock
0x180028f41  test    rcx, rcx
0x180028f44  jz      short loc_180028F4C
0x180028f46  call    cs:__imp_ReleaseSRWLockExclusive
0x180028f4c  mov     rbx, [rsp+118h+var_A0]
0x180028f51  lea     rcx, [rbx+20h]
0x180028f55  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180028f5a  mov     rdx, rax
0x180028f5d  lea     rcx, [rsp+118h+var_70]
0x180028f65  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028f6a  nop
0x180028f6b  lea     rdx, [rsp+118h+var_70]
0x180028f73  lea     rcx, [rsp+118h+var_C0]
0x180028f78  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x180028f7d  nop
0x180028f7e  lea     rcx, [rsp+118h+var_70]
0x180028f86  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180028f8b  lea     rcx, [rbx+40h]
0x180028f8f  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180028f94  mov     rdx, rax
0x180028f97  lea     rcx, [rsp+118h+var_50]
0x180028f9f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028fa4  nop
0x180028fa5  lea     rdx, [rsp+118h+var_50]
0x180028fad  lea     rcx, [rsp+118h+string]
0x180028fb2  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x180028fb7  nop
0x180028fb8  lea     rcx, [rsp+118h+var_50]
0x180028fc0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180028fc5  mov     [rsp+118h+var_B8], 0
0x180028fce  lea     rcx, [rsp+118h+var_B8]
0x180028fd3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028fd8  lea     rax, [rsp+118h+var_B8]
0x180028fdd  mov     [rsp+118h+var_F8], rax
0x180028fe2  lea     r9, [rsp+118h+var_A0]
0x180028fe7  mov     r8, r14
0x180028fea  mov     rdx, rdi
0x180028fed  call    ?ConstructSetResourceRequestValueSet@AppServiceResourceHandler@@AEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0AEBV?$shared_ptr@UCDPAppSvcApplication@@@3@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; AppServiceResourceHandler::ConstructSetResourceRequestValueSet(std::string const &,std::string const &,std::shared_ptr<CDPAppSvcApplication> const &,Windows::Foundation::Collections::IPropertySet * *)
0x180028ff2  test    eax, eax
0x180028ff4  jns     short loc_18002906C
0x180028ff6  mov     dword ptr [rsp+118h+var_D8], eax
0x180028ffa  mov     dword ptr [rsp+118h+SRWLock], 0E8h
0x180029002  lea     rax, [rsp+118h+SRWLock]
0x180029007  mov     [rsp+118h+var_F8], rax
0x18002900c  lea     r9, aAppsvcresource; "..\\appsvcresourcehandler.cpp"
0x180029013  lea     r8, [rsp+118h+var_D8]
0x180029018  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x18002901d  nop
0x18002901e  lea     rcx, [rsp+118h+var_B8]
0x180029023  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029028  nop
0x180029029  mov     rcx, [rsp+118h+string]; string
0x18002902e  call    cs:__imp_WindowsDeleteString
0x180029034  mov     [rsp+118h+string], 0
0x18002903d  mov     rcx, [rsp+118h+var_C0]; string
0x180029042  call    cs:__imp_WindowsDeleteString
0x180029048  mov     [rsp+118h+var_C0], 0
0x180029051  mov     rcx, [rsp+118h+var_A0+8]; this
0x180029059  test    rcx, rcx
0x18002905c  jz      short loc_180029063
0x18002905e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029063  mov     eax, dword ptr [rsp+118h+var_D8]
0x180029067  jmp     loc_1800292DE
0x18002906c  mov     [rsp+118h+var_A8], 0
0x180029075  mov     [rsp+118h+var_B0], 0
0x18002907e  lea     rcx, [rsp+118h+var_B0]
0x180029083  call    ??$MakeAndInitialize@VAppServiceHelper@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VAppServiceHelper@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppServiceHelper,AppServiceHelper,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<AppServiceHelper>>)
0x180029088  test    eax, eax
0x18002908a  jns     loc_18002911C
0x180029090  mov     dword ptr [rsp+118h+var_D8], eax
0x180029094  mov     dword ptr [rsp+118h+SRWLock], 0EBh
0x18002909c  lea     rax, [rsp+118h+SRWLock]
0x1800290a1  mov     [rsp+118h+var_F8], rax
0x1800290a6  lea     r9, aAppsvcresource; "..\\appsvcresourcehandler.cpp"
0x1800290ad  lea     r8, [rsp+118h+var_D8]
0x1800290b2  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x1800290b7  nop
0x1800290b8  lea     rcx, [rsp+118h+var_B0]
0x1800290bd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800290c2  nop
0x1800290c3  lea     rcx, [rsp+118h+var_A8]
0x1800290c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800290cd  nop
0x1800290ce  lea     rcx, [rsp+118h+var_B8]
0x1800290d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800290d8  nop
0x1800290d9  mov     rcx, [rsp+118h+string]; string
0x1800290de  call    cs:__imp_WindowsDeleteString
0x1800290e4  mov     [rsp+118h+string], 0
0x1800290ed  mov     rcx, [rsp+118h+var_C0]; string
0x1800290f2  call    cs:__imp_WindowsDeleteString
0x1800290f8  mov     [rsp+118h+var_C0], 0
0x180029101  mov     rcx, [rsp+118h+var_A0+8]; this
0x180029109  test    rcx, rcx
0x18002910c  jz      short loc_180029113
0x18002910e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029113  mov     eax, dword ptr [rsp+118h+var_D8]
0x180029117  jmp     loc_1800292DE
0x18002911c  mov     rbx, [rsp+118h+var_B0]
0x180029121  lea     rcx, [rsp+118h+var_A8]
0x180029126  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002912b  mov     rax, [rsp+118h+var_B8]
0x180029130  mov     [rsp+118h+var_E0], 0; HSTRING *
0x180029139  lea     rcx, [rsp+118h+var_A8]
0x18002913e  mov     [rsp+118h+var_E8], rcx; struct Windows::Foundation::Collections::IPropertySet **
0x180029143  mov     [rsp+118h+var_F0], rax; struct Windows::Foundation::Collections::IPropertySet *
0x180029148  mov     [rsp+118h+var_F8], 0; HSTRING
0x180029151  xor     r9d, r9d; HSTRING
0x180029154  mov     r8, [rsp+118h+string]; HSTRING
0x180029159  mov     rdx, [rsp+118h+var_C0]; HSTRING
0x18002915e  mov     rcx, rbx; this
0x180029161  call    ?OpenAppServiceAndSendMessageAsync@AppServiceHelper@@QEAAJPEAUHSTRING__@@000PEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU3456@PEAPEAU2@@Z; AppServiceHelper::OpenAppServiceAndSendMessageAsync(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IPropertySet * *,HSTRING__ * *)
0x180029166  mov     r14d, eax
0x180029169  lea     rcx, [rsp+118h+var_90]
0x180029171  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180029176  nop
0x180029177  test    r14d, r14d
0x18002917a  js      short loc_180029196
0x18002917c  lea     r9, [rsp+118h+var_90]
0x180029184  lea     r8, [rsp+118h+var_A0]
0x180029189  mov     rdx, [rsp+118h+var_A8]
0x18002918e  call    ?GetResourceValFromResponseValueSet@AppServiceResourceHandler@@AEAAJPEAUIPropertySet@Collections@Foundation@Windows@@AEBV?$shared_ptr@UCDPAppSvcApplication@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@7@@Z; AppServiceResourceHandler::GetResourceValFromResponseValueSet(Windows::Foundation::Collections::IPropertySet *,std::shared_ptr<CDPAppSvcApplication> const &,std::string &)
0x180029193  mov     r14d, eax
0x180029196  mov     rcx, rdi
0x180029199  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002919e  mov     rdi, rax
0x1800291a1  mov     rbx, [r15]
0x1800291a4  lea     rcx, [rsp+118h+var_90]
0x1800291ac  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800291b1  mov     [rsp+118h+var_F8], rax
0x1800291b6  mov     r9, rdi
0x1800291b9  mov     r8d, 2
0x1800291bf  mov     edx, r14d
0x1800291c2  mov     rcx, r15
0x1800291c5  mov     rax, [rbx+18h]
0x1800291c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291ce  test    eax, eax
0x1800291d0  jns     loc_18002926D
0x1800291d6  mov     dword ptr [rsp+118h+var_D8], eax
0x1800291da  mov     dword ptr [rsp+118h+SRWLock], 0F6h
0x1800291e2  lea     rax, [rsp+118h+SRWLock]
0x1800291e7  mov     [rsp+118h+var_F8], rax
0x1800291ec  lea     r9, aAppsvcresource; "..\\appsvcresourcehandler.cpp"
0x1800291f3  lea     r8, [rsp+118h+var_D8]
0x1800291f8  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x1800291fd  nop
0x1800291fe  lea     rcx, [rsp+118h+var_90]
0x180029206  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002920b  nop
0x18002920c  lea     rcx, [rsp+118h+var_B0]
0x180029211  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029216  nop
0x180029217  lea     rcx, [rsp+118h+var_A8]
0x18002921c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029221  nop
0x180029222  lea     rcx, [rsp+118h+var_B8]
0x180029227  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002922c  nop
0x18002922d  mov     rcx, [rsp+118h+string]; string
0x180029232  call    cs:__imp_WindowsDeleteString
0x180029238  mov     [rsp+118h+string], 0
0x180029241  mov     rcx, [rsp+118h+var_C0]; string
0x180029246  call    cs:__imp_WindowsDeleteString
0x18002924c  mov     [rsp+118h+var_C0], 0
0x180029255  mov     rcx, [rsp+118h+var_A0+8]; this
0x18002925d  test    rcx, rcx
0x180029260  jz      short loc_180029267
0x180029262  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029267  mov     eax, dword ptr [rsp+118h+var_D8]
0x18002926b  jmp     short loc_1800292DE
0x18002926d  lea     rcx, [rsp+118h+var_90]
0x180029275  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002927a  nop
0x18002927b  lea     rcx, [rsp+118h+var_B0]
0x180029280  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029285  nop
0x180029286  lea     rcx, [rsp+118h+var_A8]
0x18002928b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029290  nop
0x180029291  lea     rcx, [rsp+118h+var_B8]
0x180029296  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002929b  nop
0x18002929c  mov     rcx, [rsp+118h+string]; string
0x1800292a1  call    cs:__imp_WindowsDeleteString
0x1800292a7  mov     [rsp+118h+string], 0
0x1800292b0  mov     rcx, [rsp+118h+var_C0]; string
0x1800292b5  call    cs:__imp_WindowsDeleteString
0x1800292bb  mov     [rsp+118h+var_C0], 0
0x1800292c4  mov     rcx, [rsp+118h+var_A0+8]; this
0x1800292cc  test    rcx, rcx
0x1800292cf  jz      short loc_1800292D6
0x1800292d1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800292d6  xor     eax, eax
0x1800292d8  jmp     short loc_1800292DE
0x1800292da  mov     eax, dword ptr [rsp+118h+SRWLock]
0x1800292de  mov     rcx, [rsp+118h+var_30]
0x1800292e6  xor     rcx, rsp; StackCookie
0x1800292e9  call    __security_check_cookie
0x1800292ee  add     rsp, 0F8h
0x1800292f5  pop     r15
0x1800292f7  pop     r14
0x1800292f9  pop     rdi
0x1800292fa  pop     rbx
0x1800292fb  retn
```
