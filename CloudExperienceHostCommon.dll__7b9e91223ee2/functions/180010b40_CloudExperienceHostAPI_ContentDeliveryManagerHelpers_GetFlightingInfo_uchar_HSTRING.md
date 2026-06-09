# CloudExperienceHostAPI::ContentDeliveryManagerHelpers::GetFlightingInfo(uchar *,HSTRING__ * *)

- ea: `0x180010b40`
- end: `0x180010c85`
- name: `?GetFlightingInfo@ContentDeliveryManagerHelpers@CloudExperienceHostAPI@@UEAAJPEAEPEAPEAUHSTRING__@@@Z`
- size: `325`
- prototype: `int(CloudExperienceHostAPI::ContentDeliveryManagerHelpers *__hidden this, unsigned __int8 *, HSTRING *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180005174`
- `0x180010b40`
- `0x180010c8c`
- `0x1800128a4`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180010c31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180010c31`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010b7e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010b7e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CloudExperienceHostAPI::ContentDeliveryManagerHelpers::GetFlightingInfo(
        CloudExperienceHostAPI::ContentDeliveryManagerHelpers *this,
        unsigned __int8 *a2,
        HSTRING *a3)
{
  HRESULT v5; // eax
  int v6; // eax
  __int64 v7; // rbx
  int v8; // eax
  HRESULT String; // eax
  const char *v10; // r9
  __int64 result; // rax
  int v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v14; // [rsp+58h] [rbp+10h] BYREF
  LPVOID v15; // [rsp+60h] [rbp+18h] BYREF
  PCNZWCH sourceString; // [rsp+68h] [rbp+20h] BYREF

  *a2 = 0;
  *a3 = 0;
  v15 = 0;
  v5 = CoCreateInstance(&CLSID_FlightSettingsAPIBroker, 0, 1u, &GUID_e833feb2_c58a_45e4_8d93_08874744febb, &v15);
  try
  {
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\contentdeliverymanagerhelpers.cpp",
        (const char *)(unsigned int)v5,
        v12);
    LOWORD(v14) = 0;
    v6 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v15 + 24LL))(v15, &v14);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\contentdeliverymanagerhelpers.cpp",
        (const char *)(unsigned int)v6,
        v12);
    v7 = -1;
    if ( (_WORD)v14 == 0xFFFF )
    {
      *a2 = 1;
      sourceString = 0;
      v8 = (*(__int64 (__fastcall **)(LPVOID, PCNZWCH *))(*(_QWORD *)v15 + 48LL))(v15, &sourceString);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4E,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\contentdeliverymanagerhelpers.cpp",
          (const char *)(unsigned int)v8,
          v12);
      do
        ++v7;
      while ( sourceString[v7] );
      String = WindowsCreateString(sourceString, v7, a3);
      if ( String < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4F,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\contentdeliverymanagerhelpers.cpp",
          (const char *)(unsigned int)String,
          v12);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceString);
    }
    else
    {
      *a2 = 0;
    }
    wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v15);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x54,
                           (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\contentdeliverymanagerhelpers.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180010b40  mov     r11, rsp
0x180010b43  mov     [r11+8], rbx
0x180010b47  push    rsi
0x180010b48  push    rdi
0x180010b49  push    r14
0x180010b4b  sub     rsp, 30h
0x180010b4f  mov     rsi, r8
0x180010b52  mov     rdi, rdx
0x180010b55  xor     r14d, r14d
0x180010b58  mov     [rdx], r14b
0x180010b5b  mov     [r8], r14
0x180010b5e  mov     [r11+18h], r14
0x180010b62  lea     rax, [r11+18h]
0x180010b66  mov     [r11-28h], rax
0x180010b6a  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x180010b71  xor     edx, edx; pUnkOuter
0x180010b73  lea     r8d, [r14+1]; dwClsContext
0x180010b77  lea     rcx, CLSID_FlightSettingsAPIBroker; rclsid
0x180010b7e  call    cs:__imp_CoCreateInstance
0x180010b84  mov     rcx, [rsp+48h]; this
0x180010b89  test    eax, eax
0x180010b8b  jns     short loc_180010BA0
0x180010b8d  mov     r9d, eax; char *
0x180010b90  lea     r8, aOnecoreuapShel_25; "onecoreuap\\shell\\cloudexperiencehost"...
0x180010b97  lea     edx, [r14+45h]; void *
0x180010b9b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010ba0  mov     word ptr [rsp+48h+arg_8], r14w
0x180010ba6  mov     rcx, [rsp+48h+arg_10]
0x180010bab  mov     rax, [rcx]
0x180010bae  lea     rdx, [rsp+48h+arg_8]
0x180010bb3  mov     rax, [rax+18h]
0x180010bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bbc  mov     rcx, [rsp+48h]; this
0x180010bc1  test    eax, eax
0x180010bc3  jns     short loc_180010BD9
0x180010bc5  mov     r9d, eax; char *
0x180010bc8  lea     r8, aOnecoreuapShel_25; "onecoreuap\\shell\\cloudexperiencehost"...
0x180010bcf  mov     edx, 48h ; 'H'; void *
0x180010bd4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010bd9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180010bdd  cmp     word ptr [rsp+48h+arg_8], bx
0x180010be2  jnz     short loc_180010C61
0x180010be4  mov     byte ptr [rdi], 1
0x180010be7  mov     [rsp+48h+sourceString], r14
0x180010bec  mov     rcx, [rsp+48h+arg_10]
0x180010bf1  mov     rax, [rcx]
0x180010bf4  lea     rdx, [rsp+48h+sourceString]
0x180010bf9  mov     rax, [rax+30h]
0x180010bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c02  mov     rcx, [rsp+48h]; this
0x180010c07  test    eax, eax
0x180010c09  jns     short loc_180010C1D
0x180010c0b  mov     r9d, eax; char *
0x180010c0e  lea     r8, aOnecoreuapShel_25; "onecoreuap\\shell\\cloudexperiencehost"...
0x180010c15  lea     edx, [rbx+4Fh]; void *
0x180010c18  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010c1d  mov     rcx, [rsp+48h+sourceString]; sourceString
0x180010c22  inc     rbx
0x180010c25  cmp     [rcx+rbx*2], r14w
0x180010c2a  jnz     short loc_180010C22
0x180010c2c  mov     r8, rsi; string
0x180010c2f  mov     edx, ebx; length
0x180010c31  call    cs:__imp_WindowsCreateString
0x180010c37  mov     rcx, [rsp+48h]; this
0x180010c3c  test    eax, eax
0x180010c3e  jns     short loc_180010C55
0x180010c40  mov     r9d, eax; char *
0x180010c43  lea     r8, aOnecoreuapShel_25; "onecoreuap\\shell\\cloudexperiencehost"...
0x180010c4a  mov     edx, 4Fh ; 'O'; void *
0x180010c4f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010c55  lea     rcx, [rsp+48h+sourceString]
0x180010c5a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010c5f  jmp     short loc_180010C64
0x180010c61  mov     [rdi], r14b
0x180010c64  lea     rcx, [rsp+48h+arg_10]
0x180010c69  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180010c6e  xor     eax, eax
0x180010c70  jmp     short loc_180010C76
0x180010c72  mov     eax, [rsp+48h+arg_8]
0x180010c76  mov     rbx, [rsp+48h+arg_0]
0x180010c7b  add     rsp, 30h
0x180010c7f  pop     r14
0x180010c81  pop     rdi
0x180010c82  pop     rsi
0x180010c83  retn
```
