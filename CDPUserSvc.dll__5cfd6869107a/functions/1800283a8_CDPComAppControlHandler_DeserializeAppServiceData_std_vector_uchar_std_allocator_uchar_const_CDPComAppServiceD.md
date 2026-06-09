# CDPComAppControlHandler::DeserializeAppServiceData(std::vector<uchar,std::allocator<uchar>> const &,CDPComAppServiceDataFormat)

- ea: `0x1800283a8`
- end: `0x180028626`
- name: `?DeserializeAppServiceData@CDPComAppControlHandler@@CA?AV?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBV?$vector@EV?$allocator@E@std@@@std@@W4CDPComAppServiceDataFormat@@@Z`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004bdac`

## callees

- `0x180003678`
- `0x180004a58`
- `0x180004a98`
- `0x180005028`
- `0x1800198bc`
- `0x1800283a8`
- `0x18002862c`
- `0x180028670`
- `0x1800286ac`
- `0x1800289cc`
- `0x18002c570`
- `0x18002d204`
- `0x180041054`
- `0x180042ce0`
- `0x180043d60`
- `0x18005c800`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800285a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800285a3`

## string_xrefs

- `0x18002843d`: `..\cdpcomappcontrolhandler.cpp`
- `0x18002846d`: `..\cdpcomappcontrolhandler.cpp`
- `0x1800284b5`: `..\cdpcomappcontrolhandler.cpp`
- `0x180028515`: `..\cdpcomappcontrolhandler.cpp`
- `0x18002854f`: `..\cdpcomappcontrolhandler.cpp`
- `0x180028590`: `..\cdpcomappcontrolhandler.cpp`
- `0x1800285c3`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu","text":"Unrecognized protocol format %u"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall CDPComAppControlHandler::DeserializeAppServiceData(_QWORD *a1, _QWORD *a2, int a3)
{
  int v6; // eax
  __int64 v7; // r15
  const char *v8; // rdi
  __int64 (__fastcall *v9)(const char *, _QWORD, __int64, _QWORD *); // rbx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  DWORD CurrentThreadId; // eax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rax
  int v19; // [rsp+20h] [rbp-79h]
  _BYTE pExceptionObject[56]; // [rsp+50h] [rbp-49h] BYREF
  const char *v21; // [rsp+88h] [rbp-11h] BYREF
  int v22; // [rsp+90h] [rbp-9h]
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v24; // [rsp+C0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  *a1 = 0;
  if ( a3 == 1 )
  {
    v21 = 0;
    v24 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Internal.RemoteSystems.RemoteSystemInterop",
      0x3Au,
      0x39u);
    v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::RemoteSystems::IRemoteSystemInteropStatics>>(
           v24,
           (__int64)&v21);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1D2,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v6,
        v19);
    v7 = *a2;
    if ( a2[1] - *a2 > 0xFFFFFFFF )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1D5,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)0x8004010ELL,
        v19);
    v8 = v21;
    v9 = *(__int64 (__fastcall **)(const char *, _QWORD, __int64, _QWORD *))(*(_QWORD *)v21 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
    v10 = v9(v8, (unsigned int)(*((_DWORD *)a2 + 2) - *(_DWORD *)a2), v7, a1);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1D7,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v10,
        v19);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  }
  else
  {
    if ( a3 )
    {
      v21 = "..\\cdpcomappcontrolhandler.cpp";
      v22 = 482;
      CurrentThreadId = GetCurrentThreadId();
      cdp::detail::StringFormat(
        &hstringHeader,
        "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Unrecognized protocol format %u\"}",
        -2089418750,
        "..\\cdpcomappcontrolhandler.cpp",
        482,
        CurrentThreadId,
        a3);
      shared::LogMessage(1, &hstringHeader);
      std::string::_Tidy_deallocate(&hstringHeader);
      v15 = cdp::ExceptionStackFromSourceLocationInfo(&hstringHeader, &v21);
      v18 = cdp::ErrorCodeToString(2205548546LL, v16, v17, v15);
      ConnectedDevices::Exception::Exception(pExceptionObject, 2205548546LL, v18);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    v24 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.Collections.ValueSet",
      0x28u,
      0x27u);
    v11 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
            v24,
            a1);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1DB,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v11,
        v19);
    std::string::string(&v21, *a2, a2[1]);
    v12 = PropertySetHelper::DeserializeJsonToPropertySet(&v21, *a1);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1DE,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v12,
        v19);
    std::string::_Tidy_deallocate(&v21);
  }
  return a1;
}

```

## disassembly

```asm
0x1800283a8  mov     [rsp-8+arg_18], rbx
0x1800283ad  push    rbp
0x1800283ae  push    rsi
0x1800283af  push    rdi
0x1800283b0  push    r14
0x1800283b2  push    r15
0x1800283b4  lea     rbp, [rsp-37h]
0x1800283b9  sub     rsp, 0D0h
0x1800283c0  mov     rax, cs:__security_cookie
0x1800283c7  xor     rax, rsp
0x1800283ca  mov     [rbp+57h+var_28], rax
0x1800283ce  mov     edi, r8d
0x1800283d1  mov     r14, rdx
0x1800283d4  mov     rsi, rcx
0x1800283d7  mov     [rbp+57h+var_A8], rcx
0x1800283db  mov     [rbp+57h+var_B0], 0
0x1800283e2  mov     qword ptr [rcx], 0
0x1800283e9  mov     r15d, 1
0x1800283ef  mov     [rbp+57h+var_B0], r15d
0x1800283f3  cmp     r8d, r15d
0x1800283f6  jnz     loc_1800284D5
0x1800283fc  mov     [rbp+57h+var_68], 0
0x180028404  mov     [rbp+57h+var_30], 0
0x18002840c  lea     r9d, [r15+38h]; unsigned int
0x180028410  lea     r8d, [r15+39h]; unsigned int
0x180028414  lea     rdx, ?RuntimeClass_Windows_System_Internal_RemoteSystems_RemoteSystemInterop@@3QBGB; "Windows.System.Internal.RemoteSystems.R"...
0x18002841b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002841f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180028424  nop
0x180028425  lea     rdx, [rbp+57h+var_68]
0x180028429  mov     rcx, [rbp+57h+var_30]
0x18002842d  call    ??$GetActivationFactory@V?$ComPtr@UIRemoteSystemInteropStatics@RemoteSystems@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIRemoteSystemInteropStatics@RemoteSystems@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::RemoteSystems::IRemoteSystemInteropStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::RemoteSystems::IRemoteSystemInteropStatics>>)
0x180028432  mov     rcx, [rbp+5Fh]; this
0x180028436  test    eax, eax
0x180028438  jns     short loc_18002844F
0x18002843a  mov     r9d, eax; char *
0x18002843d  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x180028444  mov     edx, 1D2h; void *
0x180028449  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002844f  mov     r15, [r14]
0x180028452  mov     rcx, [rbp+5Fh]; this
0x180028456  mov     rax, [r14+8]
0x18002845a  sub     rax, r15
0x18002845d  mov     edx, 0FFFFFFFFh
0x180028462  cmp     rax, rdx
0x180028465  jbe     short loc_18002847F
0x180028467  mov     r9d, 8004010Eh; char *
0x18002846d  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x180028474  mov     edx, 1D5h; void *
0x180028479  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002847f  mov     rdi, [rbp+57h+var_68]
0x180028483  mov     rax, [rdi]
0x180028486  mov     rbx, [rax+38h]
0x18002848a  mov     rcx, rsi
0x18002848d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028492  mov     edx, [r14+8]
0x180028496  sub     edx, [r14]
0x180028499  mov     r9, rsi
0x18002849c  mov     r8, r15
0x18002849f  mov     rcx, rdi
0x1800284a2  mov     rax, rbx
0x1800284a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284aa  mov     rcx, [rbp+5Fh]; this
0x1800284ae  test    eax, eax
0x1800284b0  jns     short loc_1800284C7
0x1800284b2  mov     r9d, eax; char *
0x1800284b5  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x1800284bc  mov     edx, 1D7h; void *
0x1800284c1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800284c7  lea     rcx, [rbp+57h+var_68]
0x1800284cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800284d0  jmp     loc_18002856A
0x1800284d5  test    edi, edi
0x1800284d7  jnz     loc_180028590
0x1800284dd  mov     [rbp+57h+var_30], 0
0x1800284e5  lea     r9d, [rdi+27h]; unsigned int
0x1800284e9  lea     r8d, [rdi+28h]; unsigned int
0x1800284ed  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x1800284f4  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800284f8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800284fd  nop
0x1800284fe  mov     rdx, rsi
0x180028501  mov     rcx, [rbp+57h+var_30]
0x180028505  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x18002850a  mov     rcx, [rbp+5Fh]; this
0x18002850e  test    eax, eax
0x180028510  jns     short loc_180028527
0x180028512  mov     r9d, eax; char *
0x180028515  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18002851c  mov     edx, 1DBh; void *
0x180028521  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180028527  mov     r8, [r14+8]
0x18002852b  mov     rdx, [r14]
0x18002852e  lea     rcx, [rbp+57h+var_68]
0x180028532  call    ??$?0V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@0AEBV?$allocator@D@1@@Z; std::string::string(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::allocator<char> const &)
0x180028537  nop
0x180028538  mov     rdx, [rsi]
0x18002853b  lea     rcx, [rbp+57h+var_68]
0x18002853f  call    ?DeserializeJsonToPropertySet@PropertySetHelper@@SAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAUIPropertySet@Collections@Foundation@Windows@@@Z; PropertySetHelper::DeserializeJsonToPropertySet(std::string const &,Windows::Foundation::Collections::IPropertySet *)
0x180028544  mov     rcx, [rbp+5Fh]; this
0x180028548  test    eax, eax
0x18002854a  jns     short loc_180028561
0x18002854c  mov     r9d, eax; char *
0x18002854f  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x180028556  mov     edx, 1DEh; void *
0x18002855b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180028561  lea     rcx, [rbp+57h+var_68]
0x180028565  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002856a  mov     rax, rsi
0x18002856d  mov     rcx, [rbp+57h+var_28]
0x180028571  xor     rcx, rsp; StackCookie
0x180028574  call    __security_check_cookie
0x180028579  mov     rbx, [rsp+0F0h+arg_18]
0x180028581  add     rsp, 0D0h
0x180028588  pop     r15
0x18002858a  pop     r14
0x18002858c  pop     rdi
0x18002858d  pop     rsi
0x18002858e  pop     rbp
0x18002858f  retn
0x180028590  lea     rbx, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x180028597  mov     [rbp+57h+var_68], rbx
0x18002859b  mov     esi, 1E2h
0x1800285a0  mov     [rbp+57h+var_60], esi
0x1800285a3  call    cs:__imp_GetCurrentThreadId
0x1800285a9  mov     eax, eax
0x1800285ab  mov     [rsp+0F0h+var_C0], edi
0x1800285af  mov     [rsp+0F0h+var_C8], rax
0x1800285b4  mov     [rsp+0F0h+var_D0], esi
0x1800285b8  mov     r9, rbx
0x1800285bb  mov     ebx, 83760002h
0x1800285c0  mov     r8d, ebx
0x1800285c3  lea     rdx, aHr0x08xFileSLi_7; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800285ca  lea     rcx, [rbp+57h+hstringHeader]
0x1800285ce  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x1800285d3  mov     [rbp+57h+var_B0], 3
0x1800285da  lea     rdx, [rbp+57h+hstringHeader]
0x1800285de  mov     ecx, r15d
0x1800285e1  call    ?LogMessage@shared@@YAXW4CDPLogLevel@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::LogMessage(CDPLogLevel,std::string &)
0x1800285e6  nop
0x1800285e7  lea     rcx, [rbp+57h+hstringHeader]
0x1800285eb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800285f0  lea     rdx, [rbp+57h+var_68]
0x1800285f4  lea     rcx, [rbp+57h+hstringHeader]
0x1800285f8  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800285fd  mov     r9, rax
0x180028600  mov     ecx, ebx
0x180028602  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180028607  mov     r8, rax
0x18002860a  mov     edx, ebx
0x18002860c  lea     rcx, [rbp+57h+pExceptionObject]
0x180028610  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180028615  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18002861c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180028620  call    _CxxThrowException_0
```
