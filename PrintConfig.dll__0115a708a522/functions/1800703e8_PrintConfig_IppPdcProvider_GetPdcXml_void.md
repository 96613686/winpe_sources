# PrintConfig::IppPdcProvider::GetPdcXml(void *)

- ea: `0x1800703e8`
- end: `0x1800707d5`
- name: `?GetPdcXml@IppPdcProvider@PrintConfig@@CA?AV?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@PEAX@Z`
- size: `1005`
- prototype: `LPVOID *__fastcall(LPVOID *, __int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800700e0`
- `0x1801601f0`

## callees

- `0x180003400`
- `0x180004564`
- `0x1800060e8`
- `0x18000f830`
- `0x18000fa4c`
- `0x180018f58`
- `0x180019698`
- `0x180020c8c`
- `0x180022928`
- `0x180027550`
- `0x180038b40`
- `0x1800417e4`
- `0x180041a70`
- `0x180041a80`
- `0x18004c53c`
- `0x18006ed20`
- `0x1800703e8`
- `0x180157788`
- `0x1801cb010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18007054a`
- `OLEAUT32!__imp_SysAllocString` at `0x18007054a`
- `OLEAUT32!__imp_VariantInit` at `0x18007053b`
- `OLEAUT32!__imp_VariantInit` at `0x18007053b`
- `OLEAUT32!__imp_VariantClear` at `0x1800705a5`
- `OLEAUT32!__imp_VariantClear` at `0x1800705a5`
- `ole32!CoCreateInstance` at `0x1800704a5`
- `ole32!CoCreateInstance` at `0x1800704a5`

## string_xrefs

- `0x1800706f8`: `printscan\print\drivers\usermode\config\printconfig\ipppdcprovider.cpp`
- `0x180070711`: `printscan\print\drivers\usermode\config\printconfig\ipppdcprovider.cpp`
- `0x180070726`: `printscan\print\drivers\usermode\config\printconfig\ipppdcprovider.cpp`
- `0x18007073b`: `printscan\print\drivers\usermode\config\printconfig\ipppdcprovider.cpp`
- `0x180070750`: `printscan\print\drivers\usermode\config\printconfig\ipppdcprovider.cpp`
- `0x180070765`: `printscan\print\drivers\usermode\config\printconfig\ipppdcprovider.cpp`
- `0x18007077a`: `printscan\print\drivers\usermode\config\printconfig\ipppdcprovider.cpp`
- `0x1800707ae`: `printscan\print\drivers\usermode\config\printconfig\ipppdcprovider.cpp`
- `0x1800707c3`: `printscan\print\drivers\usermode\config\printconfig\ipppdcprovider.cpp`
- `0x1800706a8`: `PrintConfig::IppPdcProvider::GetPdcXml`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
LPVOID *__fastcall PrintConfig::IppPdcProvider::GetPdcXml(LPVOID *a1, void *a2)
{
  wchar_t *v4; // r8
  int FilenameByRole; // eax
  HRESULT Instance; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  LPVOID v10; // rsi
  __int64 v11; // r14
  const OLECHAR *v12; // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD *); // rbx
  _QWORD *v16; // rax
  _QWORD *v17; // rdx
  unsigned int v18; // eax
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, OLECHAR **); // rbx
  OLECHAR **v22; // rdx
  unsigned int v23; // eax
  int v24; // eax
  __int64 v26; // r9
  __int64 v27; // r8
  unsigned int v28; // eax
  __int64 v29; // rdx
  const char *v30; // r8
  int ppv; // [rsp+28h] [rbp-69h]
  int ppva; // [rsp+28h] [rbp-69h]
  _WORD v33[2]; // [rsp+48h] [rbp-49h] BYREF
  int v34; // [rsp+4Ch] [rbp-45h]
  OLECHAR *v35; // [rsp+50h] [rbp-41h] BYREF
  __int64 v36; // [rsp+58h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-31h] BYREF
  VARIANTARG pExceptionObject; // [rsp+78h] [rbp-19h] BYREF
  __int64 v39; // [rsp+98h] [rbp+7h]
  LPVOID *v40; // [rsp+A0h] [rbp+Fh]
  __int64 v41; // [rsp+A8h] [rbp+17h] BYREF
  OLECHAR *psz[2]; // [rsp+B0h] [rbp+1Fh] BYREF
  __int64 v43; // [rsp+C0h] [rbp+2Fh]
  unsigned __int64 v44; // [rsp+C8h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v39 = -2;
  v40 = a1;
  v34 = 0;
  *(_OWORD *)psz = 0;
  v43 = 0;
  v44 = 7;
  LOWORD(psz[0]) = 0;
  std::wstring::resize((void **)psz, (void *)0x104);
  v4 = (wchar_t *)psz;
  if ( v44 > 7 )
    v4 = psz[0];
  FilenameByRole = GetFilenameByRole(a2, 0x15u, v4, v43);
  if ( FilenameByRole < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      99,
      (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ipppdcprovider.cpp",
      (const char *)(unsigned int)FilenameByRole,
      ppv);
  *a1 = 0;
  v34 = 1;
  Instance = CoCreateInstance(
               &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
               0,
               1u,
               &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
               a1);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      102,
      (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ipppdcprovider.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a1 + 504LL))(*a1, 0);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      103,
      (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ipppdcprovider.cpp",
      (const char *)(unsigned int)v7,
      ppva);
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a1 + 544LL))(*a1, 0);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      104,
      (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ipppdcprovider.cpp",
      (const char *)(unsigned int)v8,
      ppva);
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a1 + 560LL))(*a1, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      105,
      (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ipppdcprovider.cpp",
      (const char *)(unsigned int)v9,
      ppva);
  v33[0] = 0;
  v10 = *a1;
  v11 = *(_QWORD *)*a1;
  v12 = (const OLECHAR *)psz;
  if ( v44 > 7 )
    v12 = psz[0];
  VariantInit(&pvarg);
  pvarg.llVal = (LONGLONG)SysAllocString(v12);
  pvarg.vt = 8;
  if ( !pvarg.llVal )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, -2147024882);
    throw (hr_error *)&pExceptionObject;
  }
  pExceptionObject = pvarg;
  v13 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, _WORD *))(v11 + 464))(v10, &pExceptionObject, v33);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      107,
      (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ipppdcprovider.cpp",
      (const char *)(unsigned int)v13,
      ppva);
  VariantClear(&pvarg);
  if ( v33[0] != 0xFFFF )
  {
    Microsoft::WRL::ComPtr<IXMLDOMParseError>::ComPtr<IXMLDOMParseError>(&v36);
    v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Get((__int64)a1);
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v14 + 480LL);
    v16 = Microsoft::WRL::ComPtr<IXMLDOMParseError>::operator&((__int64)&v36, &v41);
    v17 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXMLDOMParseError>>::operator IXMLDOMParseError * *((_QWORD **)v16);
    v18 = v15(v14, v17);
    v19 = wil::verify_hresult<long>(v18);
    if ( v19 >= 0 )
    {
      Microsoft::WRL::ComPtr<IXMLDOMParseError>::ComPtr<IXMLDOMParseError>(&v35);
      v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Get((__int64)&v36);
      v21 = *(__int64 (__fastcall **)(__int64, OLECHAR **))(*(_QWORD *)v20 + 72LL);
      v22 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(&v35);
      v23 = v21(v20, v22);
      v24 = wil::verify_hresult<long>(v23);
      if ( v24 >= 0 )
      {
        std::wstring::c_str(psz);
        v26 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Get((__int64)&v35);
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "PrintConfig::IppPdcProvider::GetPdcXml",
          L"Failed to parse PrintDeviceCapabilities ('%ws'). Reason: %ws",
          v27,
          v26);
        PrintConfig::IppPdcProvider::ClearPdcCacheInternal();
        std::wstring::c_str(psz);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Get((__int64)&v35);
        v28 = wil::verify_hresult<long>(0x80004005);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          118,
          (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ipppdcprovider.cpp",
          (const char *)v28,
          (unsigned __int64)"Failed to parse PrintDeviceCapabilities ('%ws'). Reason: %ws",
          v30,
          v29);
      }
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        113,
        (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ipppdcprovider.cpp",
        (const char *)(unsigned int)v24,
        ppva);
    }
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      111,
      (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ipppdcprovider.cpp",
      (const char *)(unsigned int)v19,
      ppva);
  }
  std::wstring::~wstring((char **)psz);
  return a1;
}

```

## disassembly

```asm
0x1800703e8  mov     rax, rsp
0x1800703eb  push    rbp
0x1800703ec  push    rdi
0x1800703ed  push    r14
0x1800703ef  lea     rbp, [rax-5Fh]
0x1800703f3  sub     rsp, 0D0h
0x1800703fa  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x180070402  mov     [rax+18h], rbx
0x180070406  mov     [rax+20h], rsi
0x18007040a  mov     rax, cs:__security_cookie
0x180070411  xor     rax, rsp
0x180070414  mov     [rbp+57h+var_18], rax
0x180070418  mov     rbx, rdx
0x18007041b  mov     rdi, rcx
0x18007041e  mov     [rbp+57h+var_48], rcx
0x180070422  mov     [rbp+57h+var_9C], 0
0x180070429  xorps   xmm0, xmm0
0x18007042c  movups  xmmword ptr [rbp+57h+psz], xmm0
0x180070430  mov     [rbp+57h+var_28], 0
0x180070438  mov     [rbp+57h+var_20], 7
0x180070440  xor     eax, eax
0x180070442  mov     word ptr [rbp+57h+psz], ax
0x180070446  mov     edx, 104h
0x18007044b  lea     rcx, [rbp+57h+psz]; Src
0x18007044f  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180070454  lea     r8, [rbp+57h+psz]
0x180070458  cmp     [rbp+57h+var_20], 7
0x18007045d  cmova   r8, [rbp+57h+psz]
0x180070462  mov     r9d, dword ptr [rbp+57h+var_28]
0x180070466  mov     edx, 15h
0x18007046b  mov     rcx, rbx
0x18007046e  call    GetFilenameByRole
0x180070473  mov     rcx, [rbp+5Fh]; this
0x180070477  test    eax, eax
0x180070479  js      loc_180070723
0x18007047f  mov     qword ptr [rdi], 0
0x180070486  mov     r8d, 1; dwClsContext
0x18007048c  mov     [rbp+57h+var_9C], r8d
0x180070490  mov     [rsp+0E0h+ppv], rdi; int
0x180070495  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18007049c  xor     edx, edx; pUnkOuter
0x18007049e  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x1800704a5  call    cs:__imp_CoCreateInstance
0x1800704ac  nop     dword ptr [rax+rax+00h]
0x1800704b1  mov     rcx, [rbp+5Fh]; this
0x1800704b5  test    eax, eax
0x1800704b7  js      loc_180070738
0x1800704bd  mov     rcx, [rdi]
0x1800704c0  mov     rax, [rcx]
0x1800704c3  xor     edx, edx
0x1800704c5  mov     rax, [rax+1F8h]
0x1800704cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800704d1  mov     rcx, [rbp+5Fh]; this
0x1800704d5  test    eax, eax
0x1800704d7  js      loc_18007074D
0x1800704dd  mov     rcx, [rdi]
0x1800704e0  mov     rax, [rcx]
0x1800704e3  xor     edx, edx
0x1800704e5  mov     rax, [rax+220h]
0x1800704ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800704f1  mov     rcx, [rbp+5Fh]; this
0x1800704f5  test    eax, eax
0x1800704f7  js      loc_180070762
0x1800704fd  mov     rcx, [rdi]
0x180070500  mov     rax, [rcx]
0x180070503  xor     edx, edx
0x180070505  mov     rax, [rax+230h]
0x18007050c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070511  mov     rcx, [rbp+5Fh]; this
0x180070515  test    eax, eax
0x180070517  js      loc_180070777
0x18007051d  xor     eax, eax
0x18007051f  mov     [rbp+57h+var_A0], ax
0x180070523  mov     rsi, [rdi]
0x180070526  mov     r14, [rsi]
0x180070529  lea     rbx, [rbp+57h+psz]
0x18007052d  cmp     [rbp+57h+var_20], 7
0x180070532  cmova   rbx, [rbp+57h+psz]
0x180070537  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18007053b  call    cs:__imp_VariantInit
0x180070542  nop     dword ptr [rax+rax+00h]
0x180070547  mov     rcx, rbx; psz
0x18007054a  call    cs:__imp_SysAllocString
0x180070551  nop     dword ptr [rax+rax+00h]
0x180070556  mov     qword ptr [rbp+57h+pvarg+8], rax
0x18007055a  mov     ecx, 8
0x18007055f  mov     word ptr [rbp+57h+pvarg], cx
0x180070563  test    rax, rax
0x180070566  jz      loc_18007078C
0x18007056c  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180070570  movaps  [rbp+57h+pExceptionObject], xmm0
0x180070574  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180070579  movsd   [rbp+57h+var_60], xmm1
0x18007057e  lea     r8, [rbp+57h+var_A0]
0x180070582  lea     rdx, [rbp+57h+pExceptionObject]
0x180070586  mov     rcx, rsi
0x180070589  mov     rax, [r14+1D0h]
0x180070590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070595  mov     rcx, [rbp+5Fh]; this
0x180070599  test    eax, eax
0x18007059b  js      loc_1800707AB
0x1800705a1  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800705a5  call    cs:__imp_VariantClear
0x1800705ac  nop     dword ptr [rax+rax+00h]
0x1800705b1  or      eax, 0FFFFFFFFh
0x1800705b4  cmp     ax, [rbp+57h+var_A0]
0x1800705b8  jz      loc_180070658
0x1800705be  lea     rcx, [rbp+57h+var_90]
0x1800705c2  call    ??0?$ComPtr@UIXMLDOMParseError@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IXMLDOMParseError>::ComPtr<IXMLDOMParseError>(void)
0x1800705c7  nop
0x1800705c8  mov     rcx, rdi
0x1800705cb  call    ?Get@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAPEBGXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Get(void)
0x1800705d0  mov     rdi, rax
0x1800705d3  mov     rcx, [rax]
0x1800705d6  mov     rbx, [rcx+1E0h]
0x1800705dd  lea     rdx, [rbp+57h+var_40]
0x1800705e1  lea     rcx, [rbp+57h+var_90]
0x1800705e5  call    ??I?$ComPtr@UIXMLDOMParseError@@@WRL@Microsoft@@QEAA?AV?$ComPtrRef@V?$ComPtr@UIXMLDOMParseError@@@WRL@Microsoft@@@Details@12@XZ; Microsoft::WRL::ComPtr<IXMLDOMParseError>::operator&(void)
0x1800705ea  mov     rcx, rax
0x1800705ed  call    ??B?$ComPtrRef@V?$ComPtr@UIXMLDOMParseError@@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAPEAUIXMLDOMParseError@@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXMLDOMParseError>>::operator IXMLDOMParseError * *(void)
0x1800705f2  mov     rdx, rax
0x1800705f5  mov     rcx, rdi
0x1800705f8  mov     rax, rbx
0x1800705fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070600  mov     ecx, eax
0x180070602  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180070607  mov     rcx, [rbp+5Fh]; this
0x18007060b  test    eax, eax
0x18007060d  js      loc_1800707C0
0x180070613  lea     rcx, [rbp+57h+var_98]
0x180070617  call    ??0?$ComPtr@UIXMLDOMParseError@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IXMLDOMParseError>::ComPtr<IXMLDOMParseError>(void)
0x18007061c  nop
0x18007061d  lea     rcx, [rbp+57h+var_90]
0x180070621  call    ?Get@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAPEBGXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Get(void)
0x180070626  mov     rdi, rax
0x180070629  mov     rcx, [rax]
0x18007062c  mov     rbx, [rcx+48h]
0x180070630  lea     rcx, [rbp+57h+var_98]
0x180070634  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator&(void)
0x180070639  mov     rdx, rax
0x18007063c  mov     rcx, rdi
0x18007063f  mov     rax, rbx
0x180070642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070647  mov     ecx, eax
0x180070649  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18007064e  test    eax, eax
0x180070650  js      loc_18007070A
0x180070656  jmp     short loc_180070689
0x180070658  lea     rcx, [rbp+57h+psz]
0x18007065c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180070661  mov     rax, rdi
0x180070664  mov     rcx, [rbp+57h+var_18]
0x180070668  xor     rcx, rsp; StackCookie
0x18007066b  call    __security_check_cookie
0x180070670  lea     r11, [rsp+0E0h+var_10]
0x180070678  mov     rbx, [r11+30h]
0x18007067c  mov     rsi, [r11+38h]
0x180070680  mov     rsp, r11
0x180070683  pop     r14
0x180070685  pop     rdi
0x180070686  pop     rbp
0x180070687  retn
0x180070689  lea     rcx, [rbp+57h+psz]
0x18007068d  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180070692  mov     r8, rax
0x180070695  lea     rcx, [rbp+57h+var_98]
0x180070699  call    ?Get@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAPEBGXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Get(void)
0x18007069e  mov     r9, rax
0x1800706a1  lea     rdx, aFailedToParseP_1; "Failed to parse PrintDeviceCapabilities"...
0x1800706a8  lea     rcx, aPrintconfigIpp; "PrintConfig::IppPdcProvider::GetPdcXml"
0x1800706af  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800706b4  call    ?ClearPdcCacheInternal@IppPdcProvider@PrintConfig@@CAXXZ; PrintConfig::IppPdcProvider::ClearPdcCacheInternal(void)
0x1800706b9  lea     rcx, [rbp+57h+psz]
0x1800706bd  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800706c2  mov     r8, rax
0x1800706c5  lea     rcx, [rbp+57h+var_98]
0x1800706c9  call    ?Get@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAPEBGXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Get(void)
0x1800706ce  mov     rdx, rax
0x1800706d1  mov     ecx, 80004005h
0x1800706d6  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800706db  mov     r9d, eax; char *
0x1800706de  mov     rcx, [rbp+5Fh]; this
0x1800706e2  mov     [rsp+0E0h+var_B0], rdx
0x1800706e7  mov     [rsp+0E0h+var_B8], r8; char *
0x1800706ec  lea     rax, aFailedToParseP; "Failed to parse PrintDeviceCapabilities"...
0x1800706f3  mov     [rsp+0E0h+ppv], rax; int
0x1800706f8  lea     r8, aPrintscanPrint_14; "printscan\\print\\drivers\\usermode\\co"...
0x1800706ff  mov     edx, 76h ; 'v'; void *
0x180070704  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007070a  mov     rcx, [rbp+5Fh]; this
0x18007070e  mov     r9d, eax; char *
0x180070711  lea     r8, aPrintscanPrint_14; "printscan\\print\\drivers\\usermode\\co"...
0x180070718  mov     edx, 71h ; 'q'; void *
0x18007071d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070723  mov     r9d, eax; char *
0x180070726  lea     r8, aPrintscanPrint_14; "printscan\\print\\drivers\\usermode\\co"...
0x18007072d  mov     edx, 63h ; 'c'; void *
0x180070732  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070738  mov     r9d, eax; char *
0x18007073b  lea     r8, aPrintscanPrint_14; "printscan\\print\\drivers\\usermode\\co"...
0x180070742  mov     edx, 66h ; 'f'; void *
0x180070747  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007074d  mov     r9d, eax; char *
0x180070750  lea     r8, aPrintscanPrint_14; "printscan\\print\\drivers\\usermode\\co"...
0x180070757  mov     edx, 67h ; 'g'; void *
0x18007075c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070762  mov     r9d, eax; char *
0x180070765  lea     r8, aPrintscanPrint_14; "printscan\\print\\drivers\\usermode\\co"...
0x18007076c  mov     edx, 68h ; 'h'; void *
0x180070771  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070777  mov     r9d, eax; char *
0x18007077a  lea     r8, aPrintscanPrint_14; "printscan\\print\\drivers\\usermode\\co"...
0x180070781  mov     edx, 69h ; 'i'; void *
0x180070786  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007078c  mov     edx, 8007000Eh; int
0x180070791  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180070795  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007079a  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800707a1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800707a5  call    _CxxThrowException_0
0x1800707ab  mov     r9d, eax; char *
0x1800707ae  lea     r8, aPrintscanPrint_14; "printscan\\print\\drivers\\usermode\\co"...
0x1800707b5  mov     edx, 6Bh ; 'k'; void *
0x1800707ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800707c0  mov     r9d, eax; char *
0x1800707c3  lea     r8, aPrintscanPrint_14; "printscan\\print\\drivers\\usermode\\co"...
0x1800707ca  mov     edx, 6Fh ; 'o'; void *
0x1800707cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
