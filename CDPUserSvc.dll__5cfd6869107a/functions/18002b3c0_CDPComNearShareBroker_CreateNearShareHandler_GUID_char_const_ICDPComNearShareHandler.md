# CDPComNearShareBroker::CreateNearShareHandler(_GUID,char const *,ICDPComNearShareHandler * *)

- ea: `0x18002b3c0`
- end: `0x18002b5ae`
- name: `?CreateNearShareHandler@CDPComNearShareBroker@@UEAAJU_GUID@@PEBDPEAPEAUICDPComNearShareHandler@@@Z`
- size: `494`
- prototype: `__int64 __fastcall(CDPComNearShareBroker *__hidden this, struct _GUID *__struct_ptr, const char *, struct ICDPComNearShareHandler **)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002a4c`
- `0x180003678`
- `0x1800049f4`
- `0x180004a58`
- `0x18000ecb8`
- `0x180015288`
- `0x1800198bc`
- `0x18002b3c0`
- `0x18002b5b4`
- `0x18002b614`
- `0x18002c570`
- `0x180041054`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b437`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b437`

## string_xrefs

- `0x18002b44c`: `..\cdpcomnearsharebroker.cpp`
- `0x18002b505`: `..\cdpcomnearsharebroker.cpp`
- `0x18002b541`: `..\cdpcomnearsharebroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall CDPComNearShareBroker::CreateNearShareHandler(
        CDPComNearShareBroker *this,
        struct _GUID *a2,
        const char *a3,
        struct ICDPComNearShareHandler **a4)
{
  __int64 v7; // rbx
  int ActivationFactory; // eax
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING_HEADER *, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, struct ICDPComNearShareHandler **)); // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rax
  int v15; // eax
  int v16; // eax
  int v18; // [rsp+20h] [rbp-C8h]
  __int64 (__fastcall ***v19)(_QWORD, GUID *, struct ICDPComNearShareHandler **); // [rsp+30h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+38h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+58h] [rbp-90h]
  _BYTE v23[16]; // [rsp+60h] [rbp-88h] BYREF
  __int64 v24; // [rsp+70h] [rbp-78h]
  _BYTE v25[32]; // [rsp+80h] [rbp-68h] BYREF
  _BYTE v26[32]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v20 = 0;
  v22 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.Internal.DataTransfer.NearShare.ShareReceiverHandler",
    0x4Eu,
    0x4Du);
  v7 = v22;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  ActivationFactory = RoGetActivationFactory(v7, &GUID_a235541c_83ba_4bc6_b96a_7a563d8445db, &v20);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"..\\cdpcomnearsharebroker.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v18);
  v19 = 0;
  std::string::string((__int64)v23, (__int64)a3);
  v9 = std::_String_val<std::_Simple_types<char>>::_Myptr(v23);
  std::wstring::wstring(v25, v9, v9 + v24);
  v10 = v20;
  v11 = *(__int64 (__fastcall **)(__int64, HSTRING_HEADER *, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, struct ICDPComNearShareHandler **)))(*(_QWORD *)v20 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  hstringHeader.Reserved.Reserved1 = (PVOID)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25, v12, v13);
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v26, &hstringHeader);
  *(struct _GUID *)&hstringHeader.Reserved.Reserved1 = *a2;
  v15 = v11(v10, &hstringHeader, *(_QWORD *)(v14 + 24), &v19);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"..\\cdpcomnearsharebroker.cpp",
      (const char *)(unsigned int)v15,
      v18);
  v16 = (**v19)(v19, &GUID_a7224b82_30f6_497a_be79_58e991488b67, a4);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"..\\cdpcomnearsharebroker.cpp",
      (const char *)(unsigned int)v16,
      v18);
  std::wstring::_Tidy_deallocate(v25);
  std::string::_Tidy_deallocate(v23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  return 0;
}

```

## disassembly

```asm
0x18002b3c0  mov     [rsp+arg_0], rbx
0x18002b3c5  push    rsi
0x18002b3c6  push    rdi
0x18002b3c7  push    r14
0x18002b3c9  sub     rsp, 0D0h
0x18002b3d0  mov     rax, cs:__security_cookie
0x18002b3d7  xor     rax, rsp
0x18002b3da  mov     [rsp+0E8h+var_28], rax
0x18002b3e2  mov     rsi, r9
0x18002b3e5  mov     rdi, r8
0x18002b3e8  mov     r14, rdx
0x18002b3eb  mov     [rsp+0E8h+var_B0], 0
0x18002b3f4  mov     [rsp+0E8h+var_90], 0
0x18002b3fd  mov     r9d, 4Dh ; 'M'; unsigned int
0x18002b403  lea     r8d, [r9+1]; unsigned int
0x18002b407  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Internal_DataTransfer_NearShare_ShareReceiverHandler@@3QBGB; "Windows.ApplicationModel.Internal.DataT"...
0x18002b40e  lea     rcx, [rsp+0E8h+hstringHeader]; hstringHeader
0x18002b413  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002b418  nop
0x18002b419  mov     rbx, [rsp+0E8h+var_90]
0x18002b41e  lea     rcx, [rsp+0E8h+var_B0]
0x18002b423  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b428  lea     r8, [rsp+0E8h+var_B0]
0x18002b42d  lea     rdx, _GUID_a235541c_83ba_4bc6_b96a_7a563d8445db
0x18002b434  mov     rcx, rbx
0x18002b437  call    cs:__imp_RoGetActivationFactory
0x18002b43d  mov     rcx, [rsp+0E8h]; this
0x18002b445  test    eax, eax
0x18002b447  jns     short loc_18002B45E
0x18002b449  mov     r9d, eax; char *
0x18002b44c  lea     r8, aCdpcomnearshar; "..\\cdpcomnearsharebroker.cpp"
0x18002b453  mov     edx, 19h; void *
0x18002b458  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002b45e  mov     [rsp+0E8h+var_B8], 0
0x18002b467  mov     rdx, rdi
0x18002b46a  lea     rcx, [rsp+0E8h+var_88]
0x18002b46f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002b474  nop
0x18002b475  lea     rcx, [rsp+0E8h+var_88]
0x18002b47a  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002b47f  mov     r8, [rsp+0E8h+var_78]
0x18002b484  add     r8, rax
0x18002b487  mov     rdx, rax
0x18002b48a  lea     rcx, [rsp+0E8h+var_68]
0x18002b492  call    ??$?0V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@1@0AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::allocator<ushort> const &)
0x18002b497  nop
0x18002b498  mov     rdi, [rsp+0E8h+var_B0]
0x18002b49d  mov     rax, [rdi]
0x18002b4a0  mov     rbx, [rax+30h]
0x18002b4a4  lea     rcx, [rsp+0E8h+var_B8]
0x18002b4a9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b4ae  lea     rcx, [rsp+0E8h+var_68]
0x18002b4b6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b4bb  mov     qword ptr [rsp+0E8h+hstringHeader.Reserved], rax
0x18002b4c0  lea     rdx, [rsp+0E8h+hstringHeader]
0x18002b4c5  lea     rcx, [rsp+0E8h+var_48]
0x18002b4cd  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002b4d2  nop
0x18002b4d3  movups  xmm0, xmmword ptr [r14]
0x18002b4d7  movdqu  xmmword ptr [rsp+0E8h+hstringHeader.Reserved], xmm0
0x18002b4dd  lea     r9, [rsp+0E8h+var_B8]
0x18002b4e2  mov     r8, [rax+18h]
0x18002b4e6  lea     rdx, [rsp+0E8h+hstringHeader]
0x18002b4eb  mov     rcx, rdi
0x18002b4ee  mov     rax, rbx
0x18002b4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4f6  mov     rcx, [rsp+0E8h]; this
0x18002b4fe  test    eax, eax
0x18002b500  jns     short loc_18002B517
0x18002b502  mov     r9d, eax; char *
0x18002b505  lea     r8, aCdpcomnearshar; "..\\cdpcomnearsharebroker.cpp"
0x18002b50c  mov     edx, 1Dh; void *
0x18002b511  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002b517  mov     rcx, [rsp+0E8h+var_B8]
0x18002b51c  mov     rax, [rcx]
0x18002b51f  mov     r8, rsi
0x18002b522  lea     rdx, _GUID_a7224b82_30f6_497a_be79_58e991488b67
0x18002b529  mov     rax, [rax]
0x18002b52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b531  nop
0x18002b532  mov     rcx, [rsp+0E8h]; this
0x18002b53a  test    eax, eax
0x18002b53c  jns     short loc_18002B553
0x18002b53e  mov     r9d, eax; char *
0x18002b541  lea     r8, aCdpcomnearshar; "..\\cdpcomnearsharebroker.cpp"
0x18002b548  mov     edx, 1Eh; void *
0x18002b54d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002b553  lea     rcx, [rsp+0E8h+var_68]
0x18002b55b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b560  nop
0x18002b561  lea     rcx, [rsp+0E8h+var_88]
0x18002b566  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002b56b  nop
0x18002b56c  lea     rcx, [rsp+0E8h+var_B8]
0x18002b571  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b576  nop
0x18002b577  lea     rcx, [rsp+0E8h+var_B0]
0x18002b57c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b581  xor     eax, eax
0x18002b583  jmp     short loc_18002B589
0x18002b585  mov     eax, dword ptr [rsp+0E8h+var_B8]
0x18002b589  mov     rcx, [rsp+0E8h+var_28]
0x18002b591  xor     rcx, rsp; StackCookie
0x18002b594  call    __security_check_cookie
0x18002b599  mov     rbx, [rsp+0E8h+arg_0]
0x18002b5a1  add     rsp, 0D0h
0x18002b5a8  pop     r14
0x18002b5aa  pop     rdi
0x18002b5ab  pop     rsi
0x18002b5ac  retn
```
