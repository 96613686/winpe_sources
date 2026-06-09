# CLocationPermissionManagerCam::DetermineAccessByPfn(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18007a20c`
- end: `0x18007a503`
- name: `?DetermineAccessByPfn@CLocationPermissionManagerCam@@AEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `759`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1801173f0`

## callees

- `0x180007218`
- `0x180012310`
- `0x18001bb40`
- `0x180020c64`
- `0x1800526dc`
- `0x180056b3c`
- `0x18007a20c`
- `0x1800a98c0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a2f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a340`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a38e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a2f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a340`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a38e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a306`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a353`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a3a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a306`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a353`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a3a1`

## string_xrefs

- `0x18007a243`: `Windows.Internal.CapabilityAccess.CapabilityAccess`
- `0x18007a277`: `CLocationPermissionManagerCam::DetermineAccessByPfn`
- `0x18007a3e3`: `CLocationPermissionManagerCam::DetermineAccessByPfn`
- `0x18007a456`: `CLocationPermissionManagerCam::DetermineAccessByPfn`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall CLocationPermissionManagerCam::DetermineAccessByPfn(__int64 a1, __int64 a2, __int64 a3)
{
  HSTRING *v5; // rax
  int v6; // eax
  __int64 v8; // r15
  __int64 v9; // rdx
  __int64 v10; // rax
  const WCHAR *v11; // rsi
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rbx
  HSTRING v14; // r13
  unsigned __int64 v15; // rbx
  HSTRING v16; // rsi
  __int64 v17; // rdx
  const WCHAR *v18; // rbx
  int v19; // eax
  __int64 v20; // rdx
  bool v21; // bl
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rcx
  char *v27; // [rsp+28h] [rbp-91h]
  int v28; // [rsp+30h] [rbp-89h]
  __int64 (__fastcall *v29)(__int64, HSTRING, HSTRING, HSTRING, __int64 *); // [rsp+40h] [rbp-79h]
  HSTRING v30; // [rsp+58h] [rbp-61h] BYREF
  HSTRING_HEADER v31; // [rsp+60h] [rbp-59h] BYREF
  HSTRING string; // [rsp+78h] [rbp-41h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-39h] BYREF
  HSTRING v34; // [rsp+98h] [rbp-21h] BYREF
  HSTRING_HEADER v35; // [rsp+A0h] [rbp-19h] BYREF
  int v36; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v37; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v38; // [rsp+C8h] [rbp+Fh] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+118h] [rbp+5Fh]

  v38 = 0;
  v5 = Windows::Internal::StringReference::StringReference(&v30, L"Windows.Internal.CapabilityAccess.CapabilityAccess");
  v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(
         *v5,
         &v38);
  if ( v6 < 0 )
  {
    LODWORD(v27) = v6;
    wil::details::in1diag5::Log_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationpermissionmanagercam.cpp",
      "CLocationPermissionManagerCam::DetermineAccessByPfn",
      "hr",
      v27,
      v28);
LABEL_3:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    return 0;
  }
  v37 = 0;
  v8 = v38;
  v29 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v38 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v9);
  v11 = (const WCHAR *)v10;
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(v10 + 2 * v13) );
  if ( v13 > 0xFFFFFFFF )
  {
    LODWORD(v13) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v11, v13, &hstringHeader, &string);
  v14 = string;
  v15 = -1;
  do
    ++v15;
  while ( c_szCapabilityLocation[v15] );
  if ( v15 > 0xFFFFFFFF )
  {
    LODWORD(v15) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(c_szCapabilityLocation, v15, &v35, &v34);
  v16 = v34;
  v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v17);
  do
    ++v12;
  while ( v18[v12] );
  if ( v12 > 0xFFFFFFFF )
  {
    LODWORD(v12) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v18, v12, &v31, &v30);
  v19 = v29(v8, v30, v16, v14, &v37);
  v21 = 0;
  if ( v19 < 0 )
  {
    v22 = 213;
LABEL_18:
    LODWORD(v27) = v19;
    wil::details::in1diag5::Log_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationpermissionmanagercam.cpp",
      "CLocationPermissionManagerCam::DetermineAccessByPfn",
      "hr",
      v27,
      v28);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    goto LABEL_3;
  }
  LOBYTE(v20) = 1;
  v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 88LL))(v37, v20);
  if ( v19 < 0 )
  {
    v22 = 222;
    goto LABEL_18;
  }
  v36 = 0;
  v23 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v37 + 152LL))(v37, &v36);
  if ( v23 >= 0 )
  {
    if ( (unsigned int)dword_1801DDEF8 > 5 )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v24);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v25);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v26,
        &byte_1801B41B7);
    }
    v21 = v36 == 3;
  }
  else
  {
    LODWORD(v27) = v23;
    wil::details::in1diag5::Log_Hr(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationpermissionmanagercam.cpp",
      "CLocationPermissionManagerCam::DetermineAccessByPfn",
      "hr",
      v27,
      v28);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  return v21;
}

```

## disassembly

```asm
0x18007a20c  mov     [rsp-8+arg_0], rbx
0x18007a211  push    rbp
0x18007a212  push    rsi
0x18007a213  push    rdi
0x18007a214  push    r12
0x18007a216  push    r13
0x18007a218  push    r14
0x18007a21a  push    r15
0x18007a21c  lea     rbp, [rsp-27h]
0x18007a221  sub     rsp, 0E0h
0x18007a228  mov     rax, cs:__security_cookie
0x18007a22f  xor     rax, rsp
0x18007a232  mov     [rbp+57h+var_40], rax
0x18007a236  mov     r14, r8
0x18007a239  mov     r12, rdx
0x18007a23c  xor     r13d, r13d
0x18007a23f  mov     [rbp+57h+var_48], r13
0x18007a243  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x18007a24a  lea     rcx, [rbp+57h+var_B8]; string
0x18007a24e  call    ??$?0$0DD@@StringReference@Internal@Windows@@QEAA@AEAY0DD@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[51])
0x18007a253  lea     rdx, [rbp+57h+var_48]
0x18007a257  mov     rcx, [rax]
0x18007a25a  call    ??$GetActivationFactory@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>)
0x18007a25f  test    eax, eax
0x18007a261  jns     short loc_18007A2A0
0x18007a263  mov     rcx, [rbp+5Fh]; this
0x18007a267  mov     dword ptr [rsp+110h+var_E8], eax; char *
0x18007a26b  lea     rax, aHr; "hr"
0x18007a272  mov     [rsp+110h+var_F0], rax; char *
0x18007a277  lea     r9, aClocationpermi; "CLocationPermissionManagerCam::Determin"...
0x18007a27e  lea     r8, aOnecoreuapDriv_33; "onecoreuap\\drivers\\mobilepc\\location"...
0x18007a285  mov     edx, 0C8h; void *
0x18007a28a  call    ?Log_Hr@in1diag5@details@wil@@YAJPEAXIPEBD11J@Z; wil::details::in1diag5::Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18007a28f  nop
0x18007a290  lea     rcx, [rbp+57h+var_48]
0x18007a294  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007a299  xor     al, al
0x18007a29b  jmp     loc_18007A4DC
0x18007a2a0  mov     [rbp+57h+var_50], r13
0x18007a2a4  mov     r15, [rbp+57h+var_48]
0x18007a2a8  mov     rax, [r15]
0x18007a2ab  mov     rax, [rax+30h]
0x18007a2af  mov     [rbp+57h+var_D0], rax
0x18007a2b3  lea     rcx, [rbp+57h+var_50]
0x18007a2b7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007a2bc  mov     rcx, r14
0x18007a2bf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007a2c4  mov     rsi, rax
0x18007a2c7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007a2cb  mov     rbx, rdi
0x18007a2ce  inc     rbx
0x18007a2d1  cmp     [rax+rbx*2], r13w
0x18007a2d6  jnz     short loc_18007A2CE
0x18007a2d8  mov     eax, 0FFFFFFFFh
0x18007a2dd  cmp     rbx, rax
0x18007a2e0  jbe     short loc_18007A2F9
0x18007a2e2  mov     ebx, eax
0x18007a2e4  xor     r9d, r9d; lpArguments
0x18007a2e7  xor     r8d, r8d; nNumberOfArguments
0x18007a2ea  lea     edx, [r9+1]; dwExceptionFlags
0x18007a2ee  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007a2f3  call    cs:__imp_RaiseException
0x18007a2f9  lea     r9, [rbp+57h+string]; string
0x18007a2fd  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18007a301  mov     edx, ebx; length
0x18007a303  mov     rcx, rsi; sourceString
0x18007a306  call    cs:__imp_WindowsCreateStringReference
0x18007a30c  mov     r13, [rbp+57h+string]
0x18007a310  mov     rsi, cs:?c_szCapabilityLocation@@3QEBGEB; ushort const * const c_szCapabilityLocation
0x18007a317  mov     rbx, rdi
0x18007a31a  xor     eax, eax
0x18007a31c  inc     rbx
0x18007a31f  cmp     [rsi+rbx*2], ax
0x18007a323  jnz     short loc_18007A31C
0x18007a325  mov     eax, 0FFFFFFFFh
0x18007a32a  cmp     rbx, rax
0x18007a32d  jbe     short loc_18007A346
0x18007a32f  mov     ebx, eax
0x18007a331  xor     r9d, r9d; lpArguments
0x18007a334  xor     r8d, r8d; nNumberOfArguments
0x18007a337  lea     edx, [r9+1]; dwExceptionFlags
0x18007a33b  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007a340  call    cs:__imp_RaiseException
0x18007a346  lea     r9, [rbp+57h+var_78]; string
0x18007a34a  lea     r8, [rbp+57h+var_70]; hstringHeader
0x18007a34e  mov     edx, ebx; length
0x18007a350  mov     rcx, rsi; sourceString
0x18007a353  call    cs:__imp_WindowsCreateStringReference
0x18007a359  mov     rsi, [rbp+57h+var_78]
0x18007a35d  mov     rcx, r12
0x18007a360  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007a365  mov     rbx, rax
0x18007a368  xor     eax, eax
0x18007a36a  inc     rdi
0x18007a36d  cmp     [rbx+rdi*2], ax
0x18007a371  jnz     short loc_18007A36A
0x18007a373  mov     eax, 0FFFFFFFFh
0x18007a378  cmp     rdi, rax
0x18007a37b  jbe     short loc_18007A394
0x18007a37d  mov     edi, eax
0x18007a37f  xor     r9d, r9d; lpArguments
0x18007a382  xor     r8d, r8d; nNumberOfArguments
0x18007a385  lea     edx, [r9+1]; dwExceptionFlags
0x18007a389  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007a38e  call    cs:__imp_RaiseException
0x18007a394  lea     r9, [rbp+57h+var_B8]; string
0x18007a398  lea     r8, [rbp+57h+var_B0]; hstringHeader
0x18007a39c  mov     edx, edi; length
0x18007a39e  mov     rcx, rbx; sourceString
0x18007a3a1  call    cs:__imp_WindowsCreateStringReference
0x18007a3a7  lea     rax, [rbp+57h+var_50]
0x18007a3ab  mov     [rsp+110h+var_F0], rax
0x18007a3b0  mov     r9, r13
0x18007a3b3  mov     r8, rsi
0x18007a3b6  mov     rdx, [rbp+57h+var_B8]
0x18007a3ba  mov     rcx, r15
0x18007a3bd  mov     rax, [rbp+57h+var_D0]
0x18007a3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a3c6  xor     ebx, ebx
0x18007a3c8  test    eax, eax
0x18007a3ca  jns     short loc_18007A407
0x18007a3cc  mov     edx, 0D5h; void *
0x18007a3d1  mov     dword ptr [rsp+110h+var_E8], eax; char *
0x18007a3d5  lea     rax, aHr; "hr"
0x18007a3dc  lea     r8, aOnecoreuapDriv_33; "onecoreuap\\drivers\\mobilepc\\location"...
0x18007a3e3  lea     r9, aClocationpermi; "CLocationPermissionManagerCam::Determin"...
0x18007a3ea  mov     [rsp+110h+var_F0], rax; char *
0x18007a3ef  mov     rcx, [rbp+5Fh]; this
0x18007a3f3  call    ?Log_Hr@in1diag5@details@wil@@YAJPEAXIPEBD11J@Z; wil::details::in1diag5::Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18007a3f8  nop
0x18007a3f9  lea     rcx, [rbp+57h+var_50]
0x18007a3fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007a402  jmp     loc_18007A290
0x18007a407  mov     rcx, [rbp+57h+var_50]
0x18007a40b  mov     rax, [rcx]
0x18007a40e  mov     dl, 1
0x18007a410  mov     rax, [rax+58h]
0x18007a414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a419  test    eax, eax
0x18007a41b  jns     short loc_18007A424
0x18007a41d  mov     edx, 0DEh
0x18007a422  jmp     short loc_18007A3D1
0x18007a424  mov     [rbp+57h+var_58], ebx
0x18007a427  mov     rcx, [rbp+57h+var_50]
0x18007a42b  mov     rax, [rcx]
0x18007a42e  lea     rdx, [rbp+57h+var_58]
0x18007a432  mov     rax, [rax+98h]
0x18007a439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a43e  test    eax, eax
0x18007a440  jns     short loc_18007A470
0x18007a442  mov     rcx, [rbp+5Fh]; this
0x18007a446  mov     dword ptr [rsp+110h+var_E8], eax; char *
0x18007a44a  lea     rax, aHr; "hr"
0x18007a451  mov     [rsp+110h+var_F0], rax; char *
0x18007a456  lea     r9, aClocationpermi; "CLocationPermissionManagerCam::Determin"...
0x18007a45d  lea     r8, aOnecoreuapDriv_33; "onecoreuap\\drivers\\mobilepc\\location"...
0x18007a464  mov     edx, 0E7h; void *
0x18007a469  call    ?Log_Hr@in1diag5@details@wil@@YAJPEAXIPEBD11J@Z; wil::details::in1diag5::Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18007a46e  jmp     short loc_18007A4C7
0x18007a470  mov     eax, cs:dword_1801DDEF8
0x18007a476  cmp     eax, 5
0x18007a479  jbe     short loc_18007A4C0
0x18007a47b  mov     eax, [rbp+57h+var_58]
0x18007a47e  mov     dword ptr [rbp+57h+var_D0], eax
0x18007a481  mov     rcx, r14
0x18007a484  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007a489  mov     [rbp+57h+var_C8], rax
0x18007a48d  mov     rcx, r12
0x18007a490  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007a495  mov     [rbp+57h+var_C0], rax
0x18007a499  lea     rax, [rbp+57h+var_D0]
0x18007a49d  mov     qword ptr [rsp+110h+var_E0], rax
0x18007a4a2  lea     rax, [rbp+57h+var_C8]
0x18007a4a6  mov     [rsp+110h+var_E8], rax
0x18007a4ab  lea     rax, [rbp+57h+var_C0]
0x18007a4af  mov     [rsp+110h+var_F0], rax
0x18007a4b4  lea     rdx, byte_1801B41B7
0x18007a4bb  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18007a4c0  cmp     [rbp+57h+var_58], 3
0x18007a4c4  setz    bl
0x18007a4c7  lea     rcx, [rbp+57h+var_50]
0x18007a4cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007a4d0  nop
0x18007a4d1  lea     rcx, [rbp+57h+var_48]
0x18007a4d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007a4da  mov     al, bl
0x18007a4dc  mov     rcx, [rbp+57h+var_40]
0x18007a4e0  xor     rcx, rsp; StackCookie
0x18007a4e3  call    __security_check_cookie
0x18007a4e8  mov     rbx, [rsp+110h+arg_0]
0x18007a4f0  add     rsp, 0E0h
0x18007a4f7  pop     r15
0x18007a4f9  pop     r14
0x18007a4fb  pop     r13
0x18007a4fd  pop     r12
0x18007a4ff  pop     rdi
0x18007a500  pop     rsi
0x18007a501  pop     rbp
0x18007a502  retn
```
