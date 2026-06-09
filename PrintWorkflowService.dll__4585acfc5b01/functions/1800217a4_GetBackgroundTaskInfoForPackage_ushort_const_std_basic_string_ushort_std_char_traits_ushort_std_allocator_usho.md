# GetBackgroundTaskInfoForPackage(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800217a4`
- end: `0x180021c0d`
- name: `?GetBackgroundTaskInfoForPackage@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z`
- size: `1129`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180022f14`

## callees

- `0x1800024e4`
- `0x180007484`
- `0x180012784`
- `0x1800127a4`
- `0x1800147fc`
- `0x1800217a4`
- `0x18002220c`
- `0x1800235d4`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021895`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021900`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021a4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021895`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021900`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021a4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021850`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800218bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021a0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021af3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021b03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021b13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021850`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800218bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021a0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021af3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021b03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021b13`

## string_xrefs

- `0x180021946`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180021b5e`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180021b75`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180021b8c`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180021ba1`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180021bb6`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`

## pseudocode

```c
__int64 __fastcall GetBackgroundTaskInfoForPackage(unsigned __int16 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // r8
  int InstalledWorkflowPackageForFamily; // eax
  struct Windows::Internal::StateRepository::IPackage *v10; // rdi
  struct Windows::Internal::StateRepository::IApplicationExtension *v11; // rbx
  __int64 (__fastcall *v12)(struct Windows::Internal::StateRepository::IPackage *, HSTRING *); // rsi
  int v13; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 (__fastcall *v15)(struct Windows::Internal::StateRepository::IApplicationExtension *, HSTRING *); // rdi
  int v16; // eax
  __int64 v17; // rdx
  int v18; // eax
  int v19; // eax
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rdi
  int v22; // eax
  PCWSTR v23; // rax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  const char *v27; // r9
  __int64 result; // rax
  int v29; // [rsp+20h] [rbp-E8h]
  HSTRING v30; // [rsp+40h] [rbp-C8h] BYREF
  HSTRING v31; // [rsp+48h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B8h] BYREF
  UINT32 v33[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+60h] [rbp-A8h] BYREF
  struct Windows::Internal::StateRepository::IApplicationExtension *v35; // [rsp+68h] [rbp-A0h] BYREF
  struct Windows::Internal::StateRepository::IPackage *v36; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v37[2]; // [rsp+78h] [rbp-90h] BYREF
  PCWSTR v38; // [rsp+88h] [rbp-80h] BYREF
  __int64 v39; // [rsp+90h] [rbp-78h] BYREF
  __int64 v40; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v41[3]; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v42[3]; // [rsp+B8h] [rbp-50h] BYREF
  __int16 v43; // [rsp+D0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]
  UINT32 length; // [rsp+118h] [rbp+10h] BYREF
  UINT32 v46; // [rsp+120h] [rbp+18h] BYREF

  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2) = 0;
  *(_QWORD *)(v8 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8) = 0;
  v36 = 0;
  v35 = 0;
  InstalledWorkflowPackageForFamily = GetInstalledWorkflowPackageForFamily(a1, &v36, &v35);
  try
  {
    if ( InstalledWorkflowPackageForFamily < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x103,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)(unsigned int)InstalledWorkflowPackageForFamily,
        v29);
    v10 = v36;
    if ( !v36 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x107,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)0x80070490LL,
        v29);
    v11 = v35;
    if ( !v35 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x108,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)0x80070490LL,
        v29);
    string = 0;
    v12 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *, HSTRING *))(*(_QWORD *)v36 + 112LL);
    WindowsDeleteString(0);
    string = 0;
    v13 = v12(v10, &string);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)(unsigned int)v13,
        v29);
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    std::wstring::_Append<unsigned short>(a2, StringRawBuffer, length);
    v31 = 0;
    v15 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IApplicationExtension *, HSTRING *))(*(_QWORD *)v11 + 160LL);
    WindowsDeleteString(0);
    v31 = 0;
    v16 = v15(v11, &v31);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x115,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)(unsigned int)v16,
        v29);
    v46 = 0;
    v38 = WindowsGetStringRawBuffer(v31, &v46);
    v41[0] = a3;
    v41[1] = &v38;
    v41[2] = &v46;
    v42[0] = retaddr;
    v42[1] = "onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp";
    v42[2] = 0;
    v43 = 285;
    v37[0] = off_180060DC8;
    v37[1] = v41;
    v18 = wil::details::ResultFromException(v42, v17, v37);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)(unsigned int)v18,
        v29);
    *(_QWORD *)(a4 + 16) = 0;
    *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4) = 0;
    v30 = 0;
    v34 = 0;
    v19 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IApplicationExtension *, __int64 *))(*(_QWORD *)v11 + 72LL))(
            v11,
            &v34);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x123,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)(unsigned int)v19,
        v29);
    v20 = v34;
    if ( !v34 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x124,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)0x8000FFFFLL,
        v29);
    v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 392LL);
    WindowsDeleteString(v30);
    v30 = 0;
    v22 = v21(v20, &v30);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x126,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)(unsigned int)v22,
        v29);
    if ( v30 )
    {
      v33[0] = 0;
      v23 = WindowsGetStringRawBuffer(v30, v33);
      std::wstring::_Append<unsigned short>(a4, v23, v33[0]);
    }
    if ( (unsigned int)dword_180083038 > 5 )
    {
      *(_QWORD *)v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
      v39 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
      v40 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      v37[0] = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v24,
        (unsigned int)word_180072902,
        v25,
        v26,
        (__int64)v37,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)v33);
    }
    if ( v34 )
      winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v34);
    WindowsDeleteString(v30);
    v30 = 0;
    WindowsDeleteString(v31);
    v31 = 0;
    WindowsDeleteString(string);
    string = 0;
    winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v35);
    winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v36);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x135,
                           (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
                           v27);
  }
  return result;
}

```

## disassembly

```asm
0x1800217a4  mov     [rsp+arg_0], rbx
0x1800217a9  mov     [rsp+arg_18], rsi
0x1800217ae  push    rdi
0x1800217af  push    r12
0x1800217b1  push    r13
0x1800217b3  push    r14
0x1800217b5  push    r15
0x1800217b7  sub     rsp, 0E0h
0x1800217be  mov     r14, r9
0x1800217c1  mov     r13, r8
0x1800217c4  mov     r15, rdx
0x1800217c7  mov     r12, rcx
0x1800217ca  xor     esi, esi
0x1800217cc  mov     [rdx+10h], rsi
0x1800217d0  mov     rcx, rdx
0x1800217d3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800217d8  mov     [rax], si
0x1800217db  mov     [r8+10h], rsi
0x1800217df  mov     rcx, r8
0x1800217e2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800217e7  mov     [rax], si
0x1800217ea  mov     [rsp+108h+var_98], rsi
0x1800217ef  mov     [rsp+108h+var_A0], rsi
0x1800217f4  lea     r8, [rsp+108h+var_A0]; struct Windows::Internal::StateRepository::IApplicationExtension **
0x1800217f9  lea     rdx, [rsp+108h+var_98]; struct Windows::Internal::StateRepository::IPackage **
0x1800217fe  mov     rcx, r12; unsigned __int16 *
0x180021801  call    ?GetInstalledWorkflowPackageForFamily@@YAJPEBGPEAPEAUIPackage@StateRepository@Internal@Windows@@PEAPEAUIApplicationExtension@234@@Z; GetInstalledWorkflowPackageForFamily(ushort const *,Windows::Internal::StateRepository::IPackage * *,Windows::Internal::StateRepository::IApplicationExtension * *)
0x180021806  mov     rcx, [rsp+108h]; this
0x18002180e  test    eax, eax
0x180021810  js      loc_180021B5B
0x180021816  mov     rcx, [rsp+108h]; this
0x18002181e  mov     rdi, [rsp+108h+var_98]
0x180021823  test    rdi, rdi
0x180021826  jz      loc_180021B6F
0x18002182c  mov     rcx, [rsp+108h]; this
0x180021834  mov     rbx, [rsp+108h+var_A0]
0x180021839  test    rbx, rbx
0x18002183c  jz      loc_180021B86
0x180021842  mov     [rsp+108h+string], rsi
0x180021847  mov     rax, [rdi]
0x18002184a  mov     rsi, [rax+70h]
0x18002184e  xor     ecx, ecx; string
0x180021850  call    cs:__imp_WindowsDeleteString
0x180021856  mov     [rsp+108h+string], 0
0x18002185f  lea     rdx, [rsp+108h+string]
0x180021864  mov     rcx, rdi
0x180021867  mov     rax, rsi
0x18002186a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002186f  mov     rcx, [rsp+108h]; this
0x180021877  xor     esi, esi
0x180021879  test    eax, eax
0x18002187b  js      loc_180021B9E
0x180021881  mov     [rsp+108h+length], esi
0x180021888  lea     rdx, [rsp+108h+length]; length
0x180021890  mov     rcx, [rsp+108h+string]; string
0x180021895  call    cs:__imp_WindowsGetStringRawBuffer
0x18002189b  mov     r8d, [rsp+108h+length]
0x1800218a3  mov     rdx, rax
0x1800218a6  mov     rcx, r15
0x1800218a9  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800218ae  mov     [rsp+108h+var_C0], rsi
0x1800218b3  mov     rax, [rbx]
0x1800218b6  mov     rdi, [rax+0A0h]
0x1800218bd  xor     ecx, ecx; string
0x1800218bf  call    cs:__imp_WindowsDeleteString
0x1800218c5  mov     [rsp+108h+var_C0], rsi
0x1800218ca  lea     rdx, [rsp+108h+var_C0]
0x1800218cf  mov     rcx, rbx
0x1800218d2  mov     rax, rdi
0x1800218d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218da  mov     rcx, [rsp+108h]; this
0x1800218e2  xor     edi, edi
0x1800218e4  test    eax, eax
0x1800218e6  js      loc_180021BB3
0x1800218ec  mov     [rsp+108h+arg_10], edi
0x1800218f3  lea     rdx, [rsp+108h+arg_10]; length
0x1800218fb  mov     rcx, [rsp+108h+var_C0]; string
0x180021900  call    cs:__imp_WindowsGetStringRawBuffer
0x180021906  mov     [rsp+108h+var_80], rax
0x18002190e  mov     [rsp+108h+var_68], r13
0x180021916  lea     rax, [rsp+108h+var_80]
0x18002191e  mov     [rsp+108h+var_60], rax
0x180021926  lea     rax, [rsp+108h+arg_10]
0x18002192e  mov     [rsp+108h+var_58], rax
0x180021936  mov     rax, [rsp+108h]
0x18002193e  mov     [rsp+108h+var_50], rax
0x180021946  lea     rsi, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x18002194d  mov     [rsp+108h+var_48], rsi
0x180021955  mov     [rsp+108h+var_40], rdi
0x18002195d  mov     eax, 11Dh
0x180021962  mov     [rsp+108h+var_38], ax
0x18002196a  lea     rax, off_180060DC8
0x180021971  mov     [rsp+108h+var_90], rax
0x180021976  lea     rax, [rsp+108h+var_68]
0x18002197e  mov     [rsp+108h+var_88], rax
0x180021986  lea     r8, [rsp+108h+var_90]
0x18002198b  lea     rcx, [rsp+108h+var_50]
0x180021993  call    ?ResultFromException@details@wil@@YAJAEBUDiagnosticsInfo@2@W4SupportedExceptions@2@AEAUIFunctor@12@@Z; wil::details::ResultFromException(wil::DiagnosticsInfo const &,wil::SupportedExceptions,wil::details::IFunctor &)
0x180021998  mov     rcx, [rsp+108h]; this
0x1800219a0  test    eax, eax
0x1800219a2  js      loc_180021BC7
0x1800219a8  mov     [r14+10h], rdi
0x1800219ac  mov     rcx, r14
0x1800219af  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800219b4  mov     [rax], di
0x1800219b7  mov     [rsp+108h+var_C8], rdi
0x1800219bc  mov     [rsp+108h+var_A8], rdi
0x1800219c1  mov     rax, [rbx]
0x1800219c4  lea     rdx, [rsp+108h+var_A8]
0x1800219c9  mov     rcx, rbx
0x1800219cc  mov     rax, [rax+48h]
0x1800219d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219d5  mov     rcx, [rsp+108h]; this
0x1800219dd  test    eax, eax
0x1800219df  js      loc_180021BD8
0x1800219e5  mov     rcx, [rsp+108h]; this
0x1800219ed  mov     rbx, [rsp+108h+var_A8]
0x1800219f2  test    rbx, rbx
0x1800219f5  jz      loc_180021BE8
0x1800219fb  mov     rax, [rbx]
0x1800219fe  mov     rdi, [rax+188h]
0x180021a05  mov     rcx, [rsp+108h+var_C8]; string
0x180021a0a  call    cs:__imp_WindowsDeleteString
0x180021a10  mov     [rsp+108h+var_C8], 0
0x180021a19  lea     rdx, [rsp+108h+var_C8]
0x180021a1e  mov     rcx, rbx
0x180021a21  mov     rax, rdi
0x180021a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a29  mov     rcx, [rsp+108h]; this
0x180021a31  xor     ebx, ebx
0x180021a33  test    eax, eax
0x180021a35  js      loc_180021BFB
0x180021a3b  mov     rcx, [rsp+108h+var_C8]; string
0x180021a40  test    rcx, rcx
0x180021a43  jz      short loc_180021A64
0x180021a45  mov     [rsp+108h+var_B0], ebx
0x180021a49  lea     rdx, [rsp+108h+var_B0]; length
0x180021a4e  call    cs:__imp_WindowsGetStringRawBuffer
0x180021a54  mov     r8d, [rsp+108h+var_B0]
0x180021a59  mov     rdx, rax
0x180021a5c  mov     rcx, r14
0x180021a5f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180021a64  mov     eax, cs:dword_180083038
0x180021a6a  cmp     eax, 5
0x180021a6d  jbe     short loc_180021ADC
0x180021a6f  mov     rcx, r14
0x180021a72  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021a77  mov     qword ptr [rsp+108h+var_B0], rax
0x180021a7c  mov     rcx, r13
0x180021a7f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021a84  mov     [rsp+108h+var_78], rax
0x180021a8c  mov     rcx, r15
0x180021a8f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021a94  mov     [rsp+108h+var_70], rax
0x180021a9c  mov     [rsp+108h+var_90], r12
0x180021aa1  lea     rax, [rsp+108h+var_B0]
0x180021aa6  mov     [rsp+108h+var_D0], rax
0x180021aab  lea     rax, [rsp+108h+var_78]
0x180021ab3  mov     [rsp+108h+var_D8], rax
0x180021ab8  lea     rax, [rsp+108h+var_70]
0x180021ac0  mov     [rsp+108h+var_E0], rax
0x180021ac5  lea     rax, [rsp+108h+var_90]
0x180021aca  mov     [rsp+108h+var_E8], rax
0x180021acf  lea     rdx, word_180072902
0x180021ad6  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180021adb  nop
0x180021adc  cmp     [rsp+108h+var_A8], rbx
0x180021ae1  jz      short loc_180021AEE
0x180021ae3  lea     rcx, [rsp+108h+var_A8]
0x180021ae8  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180021aed  nop
0x180021aee  mov     rcx, [rsp+108h+var_C8]; string
0x180021af3  call    cs:__imp_WindowsDeleteString
0x180021af9  mov     [rsp+108h+var_C8], rbx
0x180021afe  mov     rcx, [rsp+108h+var_C0]; string
0x180021b03  call    cs:__imp_WindowsDeleteString
0x180021b09  mov     [rsp+108h+var_C0], rbx
0x180021b0e  mov     rcx, [rsp+108h+string]; string
0x180021b13  call    cs:__imp_WindowsDeleteString
0x180021b19  mov     [rsp+108h+string], rbx
0x180021b1e  lea     rcx, [rsp+108h+var_A0]
0x180021b23  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180021b28  nop
0x180021b29  lea     rcx, [rsp+108h+var_98]
0x180021b2e  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180021b33  xor     eax, eax
0x180021b35  jmp     short loc_180021B3E
0x180021b37  mov     eax, [rsp+108h+length]
0x180021b3e  lea     r11, [rsp+108h+var_28]
0x180021b46  mov     rbx, [r11+30h]
0x180021b4a  mov     rsi, [r11+48h]
0x180021b4e  mov     rsp, r11
0x180021b51  pop     r15
0x180021b53  pop     r14
0x180021b55  pop     r13
0x180021b57  pop     r12
0x180021b59  pop     rdi
0x180021b5a  retn
0x180021b5b  mov     r9d, eax; char *
0x180021b5e  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180021b65  mov     edx, 103h; void *
0x180021b6a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021b6f  mov     r9d, 80070490h; char *
0x180021b75  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180021b7c  mov     edx, 107h; void *
0x180021b81  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021b86  mov     r9d, 80070490h; char *
0x180021b8c  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180021b93  mov     edx, 108h; void *
0x180021b98  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021b9e  mov     r9d, eax; char *
0x180021ba1  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180021ba8  mov     edx, 10Ch; void *
0x180021bad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021bb3  mov     r9d, eax; char *
0x180021bb6  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180021bbd  mov     edx, 115h; void *
0x180021bc2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021bc7  mov     r9d, eax; char *
0x180021bca  mov     r8, rsi; unsigned int
0x180021bcd  mov     edx, 11Dh; void *
0x180021bd2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021bd8  mov     r9d, eax; char *
0x180021bdb  mov     r8, rsi; unsigned int
0x180021bde  mov     edx, 123h; void *
0x180021be3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021be8  mov     r9d, 8000FFFFh; char *
0x180021bee  mov     r8, rsi; unsigned int
0x180021bf1  mov     edx, 124h; void *
0x180021bf6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021bfb  mov     r9d, eax; char *
0x180021bfe  mov     r8, rsi; unsigned int
0x180021c01  mov     edx, 126h; void *
0x180021c06  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
