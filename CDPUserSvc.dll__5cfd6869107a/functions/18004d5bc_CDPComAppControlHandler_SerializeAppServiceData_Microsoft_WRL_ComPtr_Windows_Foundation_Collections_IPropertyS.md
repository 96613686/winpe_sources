# CDPComAppControlHandler::SerializeAppServiceData(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet> const &,CDPComAppServiceDataFormat)

- ea: `0x18004d5bc`
- end: `0x18004d85e`
- name: `?SerializeAppServiceData@CDPComAppControlHandler@@CA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@W4CDPComAppServiceDataFormat@@@Z`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004bdac`

## callees

- `0x180002a4c`
- `0x180003678`
- `0x180004a58`
- `0x1800198bc`
- `0x180027694`
- `0x180028670`
- `0x18002c570`
- `0x180041054`
- `0x18004abac`
- `0x18004b7d0`
- `0x18004b860`
- `0x18004d5bc`
- `0x18004d864`
- `0x18004e3b8`
- `0x180064010`

## string_xrefs

- `0x18004d7af`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004d7e3`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004d7f8`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004d80d`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004d822`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004d837`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004d84c`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004d7d7`: `Unrecognized protocol format %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall CDPComAppControlHandler::SerializeAppServiceData(_QWORD *a1, _QWORD *a2, int a3)
{
  int v5; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, _QWORD); // rbx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rax
  unsigned int v15; // eax
  int v16; // r8d
  int v17; // [rsp+20h] [rbp-39h]
  char *v18; // [rsp+28h] [rbp-31h]
  unsigned int v19; // [rsp+30h] [rbp-29h] BYREF
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-21h] BYREF
  int v21; // [rsp+40h] [rbp-19h]
  __int64 v22; // [rsp+48h] [rbp-11h] BYREF
  __int64 v23; // [rsp+50h] [rbp-9h] BYREF
  _QWORD v24[2]; // [rsp+58h] [rbp-1h] BYREF
  __int128 hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  __m128i hstringHeader_16; // [rsp+78h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v24[1] = a1;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v21 = 1;
  if ( a3 == 1 )
  {
    v23 = 0;
    hstringHeader_16.m128i_i64[1] = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      (HSTRING_HEADER *)&hstringHeader,
      L"Windows.System.Internal.RemoteSystems.RemoteSystemInterop",
      0x3Au,
      0x39u);
    v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::RemoteSystems::IRemoteSystemInteropStatics>>(
           hstringHeader_16.m128i_i64[1],
           (__int64)&v23);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1AC,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v5,
        v17);
    v20 = 0;
    v22 = 0;
    v24[0] = 0;
    v19 = 0;
    v6 = v23;
    v7 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v23 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    v8 = v7(v6, *a2, &v20);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1B3,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v8,
        v17);
    v9 = Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(
           &v20,
           (__int64)&v22);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1B5,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v9,
        v17);
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v22 + 24LL))(v22, v24);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1B6,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v10,
        v17);
    v11 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), unsigned int *))(*v20)[7])(
            v20,
            &v19);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1B7,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v11,
        v17);
    std::vector<unsigned char>::assign<unsigned char *,0>(a1, v24[0], v24[0] + v19);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  }
  else
  {
    if ( a3 )
    {
      v15 = wil::verify_hresult<long>(2205548546LL);
      LODWORD(v18) = v16;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)v15,
        (int)"Unrecognized protocol format %u",
        v18);
    }
    hstringHeader = 0;
    hstringHeader_16 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(hstringHeader) = 0;
    v12 = PropertySetHelper::SerializePropertySetToJson(
            (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD))*a2,
            (__int64)&hstringHeader);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1BF,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v12,
        v17);
    v13 = std::_String_val<std::_Simple_types<char>>::_Myptr(&hstringHeader);
    std::vector<unsigned char>::assign<std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,0>(
      a1,
      v13,
      v13 + hstringHeader_16.m128i_i64[0]);
    std::string::_Tidy_deallocate(&hstringHeader);
  }
  return a1;
}

```

## disassembly

```asm
0x18004d5bc  push    rbp
0x18004d5be  push    rbx
0x18004d5bf  push    rsi
0x18004d5c0  push    rdi
0x18004d5c1  push    r14
0x18004d5c3  lea     rbp, [rsp-37h]
0x18004d5c8  sub     rsp, 90h
0x18004d5cf  mov     rax, cs:__security_cookie
0x18004d5d6  xor     rax, rsp
0x18004d5d9  mov     [rbp+57h+var_28], rax
0x18004d5dd  mov     r14, rdx
0x18004d5e0  mov     rsi, rcx
0x18004d5e3  mov     [rbp+57h+var_50], rcx
0x18004d5e7  mov     [rbp+57h+var_70], 0
0x18004d5ee  mov     qword ptr [rcx], 0
0x18004d5f5  mov     qword ptr [rcx+8], 0
0x18004d5fd  mov     qword ptr [rcx+10h], 0
0x18004d605  mov     [rbp+57h+var_70], 1
0x18004d60c  cmp     r8d, 1
0x18004d610  jnz     loc_18004D735
0x18004d616  mov     [rbp+57h+var_60], 0
0x18004d61e  mov     [rbp+57h+var_30], 0
0x18004d626  lea     r9d, [r8+38h]; unsigned int
0x18004d62a  lea     r8d, [r9+1]; unsigned int
0x18004d62e  lea     rdx, ?RuntimeClass_Windows_System_Internal_RemoteSystems_RemoteSystemInterop@@3QBGB; "Windows.System.Internal.RemoteSystems.R"...
0x18004d635  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004d639  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004d63e  nop
0x18004d63f  lea     rdx, [rbp+57h+var_60]
0x18004d643  mov     rcx, [rbp+57h+var_30]
0x18004d647  call    ??$GetActivationFactory@V?$ComPtr@UIRemoteSystemInteropStatics@RemoteSystems@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIRemoteSystemInteropStatics@RemoteSystems@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::RemoteSystems::IRemoteSystemInteropStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::RemoteSystems::IRemoteSystemInteropStatics>>)
0x18004d64c  mov     rcx, [rbp+5Fh]; this
0x18004d650  test    eax, eax
0x18004d652  js      loc_18004D7F5
0x18004d658  mov     [rbp+57h+var_78], 0
0x18004d660  mov     [rbp+57h+var_68], 0
0x18004d668  mov     [rbp+57h+var_58], 0
0x18004d670  mov     [rbp+57h+var_80], 0
0x18004d677  mov     rdi, [rbp+57h+var_60]
0x18004d67b  mov     rax, [rdi]
0x18004d67e  mov     rbx, [rax+30h]
0x18004d682  lea     rcx, [rbp+57h+var_78]
0x18004d686  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d68b  lea     r8, [rbp+57h+var_78]
0x18004d68f  mov     rdx, [r14]
0x18004d692  mov     rcx, rdi
0x18004d695  mov     rax, rbx
0x18004d698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d69d  mov     rcx, [rbp+5Fh]; this
0x18004d6a1  test    eax, eax
0x18004d6a3  js      loc_18004D80A
0x18004d6a9  lea     rdx, [rbp+57h+var_68]
0x18004d6ad  lea     rcx, [rbp+57h+var_78]
0x18004d6b1  call    ??$As@UIBufferByteAccess@Streams@Storage@Windows@@@?$ComPtr@UIBuffer@Streams@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIBufferByteAccess@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBufferByteAccess>>)
0x18004d6b6  mov     rcx, [rbp+5Fh]; this
0x18004d6ba  test    eax, eax
0x18004d6bc  js      loc_18004D81F
0x18004d6c2  mov     rcx, [rbp+57h+var_68]
0x18004d6c6  mov     rax, [rcx]
0x18004d6c9  lea     rdx, [rbp+57h+var_58]
0x18004d6cd  mov     rax, [rax+18h]
0x18004d6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6d6  mov     rcx, [rbp+5Fh]; this
0x18004d6da  test    eax, eax
0x18004d6dc  js      loc_18004D834
0x18004d6e2  mov     rcx, [rbp+57h+var_78]
0x18004d6e6  mov     rax, [rcx]
0x18004d6e9  lea     rdx, [rbp+57h+var_80]
0x18004d6ed  mov     rax, [rax+38h]
0x18004d6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6f6  mov     rcx, [rbp+5Fh]; this
0x18004d6fa  test    eax, eax
0x18004d6fc  js      loc_18004D849
0x18004d702  mov     r8d, [rbp+57h+var_80]
0x18004d706  mov     rdx, [rbp+57h+var_58]
0x18004d70a  add     r8, rdx
0x18004d70d  mov     rcx, rsi
0x18004d710  call    ??$assign@PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEAE0@Z; std::vector<uchar>::assign<uchar *,0>(uchar *,uchar *)
0x18004d715  nop
0x18004d716  lea     rcx, [rbp+57h+var_68]
0x18004d71a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d71f  nop
0x18004d720  lea     rcx, [rbp+57h+var_78]
0x18004d724  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d729  nop
0x18004d72a  lea     rcx, [rbp+57h+var_60]
0x18004d72e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d733  jmp     short loc_18004D78F
0x18004d735  test    r8d, r8d
0x18004d738  jnz     loc_18004D7C1
0x18004d73e  xorps   xmm0, xmm0
0x18004d741  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x18004d745  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18004d74d  movdqu  xmmword ptr [rbp+1Fh], xmm1
0x18004d752  mov     byte ptr [rbp+57h+hstringHeader.Reserved], r8b
0x18004d756  lea     rdx, [rbp+57h+hstringHeader]
0x18004d75a  mov     rcx, [r14]
0x18004d75d  call    ?SerializePropertySetToJson@PropertySetHelper@@SAJPEAUIPropertySet@Collections@Foundation@Windows@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; PropertySetHelper::SerializePropertySetToJson(Windows::Foundation::Collections::IPropertySet *,std::string &)
0x18004d762  mov     rcx, [rbp+5Fh]; this
0x18004d766  test    eax, eax
0x18004d768  js      short loc_18004D7AC
0x18004d76a  lea     rcx, [rbp+57h+hstringHeader]
0x18004d76e  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004d773  mov     r8, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x18004d777  add     r8, rax
0x18004d77a  mov     rdx, rax
0x18004d77d  mov     rcx, rsi
0x18004d780  call    ??$assign@V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAAXV?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@1@0@Z; std::vector<uchar>::assign<std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,0>(std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::_String_iterator<std::_String_val<std::_Simple_types<char>>>)
0x18004d785  nop
0x18004d786  lea     rcx, [rbp+57h+hstringHeader]
0x18004d78a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004d78f  mov     rax, rsi
0x18004d792  mov     rcx, [rbp+57h+var_28]
0x18004d796  xor     rcx, rsp; StackCookie
0x18004d799  call    __security_check_cookie
0x18004d79e  add     rsp, 90h
0x18004d7a5  pop     r14
0x18004d7a7  pop     rdi
0x18004d7a8  pop     rsi
0x18004d7a9  pop     rbx
0x18004d7aa  pop     rbp
0x18004d7ab  retn
0x18004d7ac  mov     r9d, eax; char *
0x18004d7af  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004d7b6  mov     edx, 1BFh; void *
0x18004d7bb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004d7c1  mov     ecx, 83760002h
0x18004d7c6  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18004d7cb  mov     r9d, eax; char *
0x18004d7ce  mov     rcx, [rbp+5Fh]; this
0x18004d7d2  mov     dword ptr [rsp+0B0h+var_88], r8d; char *
0x18004d7d7  lea     rax, aUnrecognizedPr; "Unrecognized protocol format %u"
0x18004d7de  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x18004d7e3  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004d7ea  mov     edx, 1C4h; void *
0x18004d7ef  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004d7f5  mov     r9d, eax; char *
0x18004d7f8  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004d7ff  mov     edx, 1ACh; void *
0x18004d804  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004d80a  mov     r9d, eax; char *
0x18004d80d  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004d814  mov     edx, 1B3h; void *
0x18004d819  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004d81f  mov     r9d, eax; char *
0x18004d822  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004d829  mov     edx, 1B5h; void *
0x18004d82e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004d834  mov     r9d, eax; char *
0x18004d837  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004d83e  mov     edx, 1B6h; void *
0x18004d843  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004d849  mov     r9d, eax; char *
0x18004d84c  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004d853  mov     edx, 1B7h; void *
0x18004d858  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
