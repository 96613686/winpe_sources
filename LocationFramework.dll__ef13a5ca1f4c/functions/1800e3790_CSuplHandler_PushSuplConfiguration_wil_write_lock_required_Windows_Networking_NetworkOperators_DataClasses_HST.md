# CSuplHandler::PushSuplConfiguration(wil::write_lock_required,Windows::Networking::NetworkOperators::DataClasses,HSTRING__ *,HSTRING__ *)

- ea: `0x1800e3790`
- end: `0x1800e3e2c`
- name: `?PushSuplConfiguration@CSuplHandler@@AEAAJUwrite_lock_required@wil@@W4DataClasses@NetworkOperators@Networking@Windows@@PEAUHSTRING__@@2@Z`
- size: `1692`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, HSTRING, HSTRING)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e3000`

## callees

- `0x1800037bc`
- `0x1800041fc`
- `0x180020504`
- `0x180020994`
- `0x180020c64`
- `0x180044674`
- `0x18004ce9c`
- `0x180060988`
- `0x18006334c`
- `0x18006d5ec`
- `0x180081ef4`
- `0x18009c344`
- `0x1800a48d8`
- `0x1800a98c0`
- `0x1800a98e4`
- `0x1800a9dd0`
- `0x1800aa5ac`
- `0x1800e2680`
- `0x1800e2a9c`
- `0x1800e2ae4`
- `0x1800e2e50`
- `0x1800e2f80`
- `0x1800e3790`
- `0x1800e429c`
- `0x1800e4698`
- `0x1800e4884`
- `0x18015e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800e3942`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800e3961`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800e3942`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800e3961`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3a9d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800e3a93`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800e3a93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e392f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3953`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3a64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e392f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3953`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3a64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800e38c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800e38c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800e38db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800e38f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800e38db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800e38f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e38aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e38b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3de8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3dfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e38aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e38b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3de8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3dfa`

## string_xrefs

- `0x1800e3817`: `SYSTEM\CurrentControlSet\Services\lfsvc\Components\SUPL`
- `0x1800e3af1`: `SYSTEM\CurrentControlSet\Services\lfsvc\Components\SUPL`
- `0x1800e3b8e`: `SYSTEM\CurrentControlSet\Services\lfsvc\Components\SUPL\RootCertificate`

## pseudocode

```c
__int64 __fastcall CSuplHandler::PushSuplConfiguration(__int64 a1, __int64 a2, unsigned int a3, HSTRING a4, HSTRING a5)
{
  unsigned int v8; // r13d
  int StringWithSubkey; // ebx
  unsigned int v10; // r9d
  int SuplRootCertificate; // ebx
  unsigned int v12; // r12d
  UINT32 StringLen; // r14d
  const wchar_t *StringRawBuffer; // rax
  unsigned int v15; // r14d
  const wchar_t *v16; // rax
  unsigned int v17; // r15d
  int IsCompatibleWithImsi; // eax
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  int v22; // r8d
  void **p_Block; // rax
  __int16 *v24; // rdx
  const WCHAR *v25; // rax
  signed int LastError; // eax
  int StringWithSubkeyA; // eax
  int v28; // r8d
  int v29; // r9d
  int v30; // eax
  unsigned int v31; // esi
  __int64 v32; // rdx
  _WORD *v33; // r9
  unsigned __int64 v34; // r8
  const unsigned __int16 *v35; // rax
  int SuplRootCertificateSize; // eax
  _DWORD *v37; // rbx
  __int64 **v38; // r15
  unsigned int v39; // ebx
  unsigned int *v40; // r14
  const unsigned __int16 *v41; // rax
  char *v42; // rdx
  unsigned int v43; // r8d
  unsigned __int8 *v44; // r9
  __int64 *v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rcx
  int lpMultiByteStr; // [rsp+20h] [rbp-E0h]
  unsigned int v50; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v51; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v52; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v53[2]; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v54; // [rsp+58h] [rbp-A8h]
  _BYTE v55[32]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v56; // [rsp+80h] [rbp-80h] BYREF
  void *Block; // [rsp+88h] [rbp-78h] BYREF
  HSTRING string; // [rsp+90h] [rbp-70h] BYREF
  UINT32 length; // [rsp+98h] [rbp-68h] BYREF
  HSTRING newString; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v61[40]; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD v62[2]; // [rsp+D0h] [rbp-30h] BYREF
  CHAR MultiByteStr[260]; // [rsp+D8h] [rbp-28h] BYREF
  char v64[830]; // [rsp+1DCh] [rbp+DCh] BYREF
  _BYTE v65[6]; // [rsp+51Ah] [rbp+41Ah] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+568h] [rbp+468h]

  v54 = a5;
  v51 = 0;
  memset_0(v62, 0, 0x414u);
  v8 = 1;
  v56 = 1;
  v53[0] = 0;
  v52 = 0;
  newString = 0;
  string = 0;
  Block = 0;
  StringWithSubkey = CspRegistry::ReadStringWithSubkey(
                       L"SYSTEM\\CurrentControlSet\\Services\\lfsvc\\Components\\SUPL",
                       L"FullVersion",
                       (unsigned __int16 **)&Block);
  if ( StringWithSubkey >= 0 )
  {
    StringWithSubkey = CspRegistry::ParseSuplVersion((const unsigned __int16 *)Block, &v56, v53, &v52);
    v8 = v56;
  }
  operator delete(Block);
  if ( StringWithSubkey < 0 )
  {
    CspRegistry::ReadDword(L"Version", &v56);
    v8 = v56;
  }
  if ( (unsigned int)CSuplHandler::IsCDMA(a3) && (*(_DWORD *)(a1 + 164) < 2u || v8 < 2) )
  {
    SuplRootCertificate = -2147024846;
    goto LABEL_69;
  }
  v12 = 0;
  v62[1] = 6;
  v62[0] = 1044;
  if ( !a4 )
    goto LABEL_30;
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(newString);
  newString = 0;
  StringLen = WindowsGetStringLen(a4);
  SuplRootCertificate = WindowsSubstringWithSpecifiedLength(a4, 0, 3u, &newString);
  if ( SuplRootCertificate < 0
    || (SuplRootCertificate = WindowsSubstringWithSpecifiedLength(a4, 3u, StringLen - 4, &string),
        SuplRootCertificate < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x179,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\gnssadapter\\suplhandler.cpp",
      (const char *)(unsigned int)SuplRootCertificate,
      lpMultiByteStr);
    goto LABEL_69;
  }
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(newString, &length);
  v15 = wcstol(StringRawBuffer, 0, 10);
  v16 = WindowsGetStringRawBuffer(string, &length);
  v17 = wcstol(v16, 0, 10);
  IsCompatibleWithImsi = CspRegistry::IsCompatibleWithImsi(v15, v17);
  SuplRootCertificate = IsCompatibleWithImsi;
  if ( (unsigned int)dword_1801DDEF8 > 4 )
  {
    v56 = v17;
    v50 = v15;
    LODWORD(Block) = IsCompatibleWithImsi;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1801DDEF8,
      (unsigned int)&unk_1801AFE78,
      v19,
      v20,
      (__int64)&Block,
      (__int64)&v50,
      (__int64)&v56);
  }
  if ( SuplRootCertificate >= 0 )
  {
    if ( SuplRootCertificate == 1 )
    {
      SuplRootCertificate = -2147023728;
      goto LABEL_69;
    }
    CspRegistry::ReadDword(L"DisableHslpFromUicc", &v51);
    v21 = StringCchPrintfA(v64, 0x104u, "h-slp.mnc%3.3d.mcc%3.3d.pub.3gppnetwork.org", v17, v15);
    SuplRootCertificate = v21;
    if ( v21 < 0 )
    {
      if ( (unsigned int)dword_1801DDF30 <= 4 )
        goto LABEL_69;
      LODWORD(Block) = v21;
      p_Block = &Block;
      v24 = (__int16 *)&dword_1801AFE44;
      goto LABEL_21;
    }
    if ( !v51 && v54 )
    {
      LODWORD(Block) = 0;
      v25 = WindowsGetStringRawBuffer(v54, (UINT32 *)&Block);
      if ( !WideCharToMultiByte(0xFDE9u, 0, v25, -1, MultiByteStr, 260, 0, 0) )
      {
        LastError = GetLastError();
        SuplRootCertificate = LastError;
        if ( LastError > 0 )
          SuplRootCertificate = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)dword_1801DDF30 <= 4 )
          goto LABEL_69;
        v50 = SuplRootCertificate;
        p_Block = (void **)&v50;
        v24 = word_1801AFC2A;
LABEL_21:
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1801DDF30,
          (_DWORD)v24,
          v22,
          v10,
          (__int64)p_Block);
        goto LABEL_69;
      }
      v12 = 2;
    }
LABEL_30:
    if ( !MultiByteStr[0] )
    {
      StringWithSubkeyA = CspRegistry::ReadStringWithSubkeyA(
                            L"SYSTEM\\CurrentControlSet\\Services\\lfsvc\\Components\\SUPL",
                            L"Addr",
                            MultiByteStr,
                            v10);
      if ( StringWithSubkeyA >= 0 )
      {
        v12 = 1;
      }
      else if ( (unsigned int)dword_1801DDF30 > 4 )
      {
        LODWORD(Block) = StringWithSubkeyA;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1801DDF30,
          (unsigned int)byte_1801AFF5B,
          v28,
          v29,
          (__int64)&Block);
      }
      if ( !MultiByteStr[0] )
      {
        if ( !a4 )
        {
          SuplRootCertificate = -2147024809;
          goto LABEL_69;
        }
        v30 = StringCchCopyA(MultiByteStr, 0x104u, v64);
        if ( v30 < 0 )
        {
          SuplRootCertificate = v30;
          goto LABEL_69;
        }
        v12 = 3;
      }
    }
    SuplRootCertificate = CSuplHandler::PurgeAllCertificates(a1);
    if ( SuplRootCertificate < 0 )
      goto LABEL_42;
    v31 = 0;
    while ( 1 )
    {
      std::wstring::wstring(v61, L"SYSTEM\\CurrentControlSet\\Services\\lfsvc\\Components\\SUPL\\RootCertificate");
      if ( v31 )
      {
        v33 = v65;
        v34 = v31 + 1LL;
        do
        {
          *--v33 = v34 % 0xA + 48;
          v34 /= 0xAu;
        }
        while ( v34 );
        std::wstring::wstring(v55, v33, v65);
        std::wstring::append(v61, v55);
        std::wstring::_Tidy_deallocate(v55);
      }
      v56 = 0;
      v35 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v61, v32);
      SuplRootCertificateSize = CspRegistry::GetSuplRootCertificateSize(v35, &v56);
      SuplRootCertificate = SuplRootCertificateSize;
      if ( SuplRootCertificateSize >= 0 )
      {
        v39 = v56 + 788;
        v40 = (unsigned int *)operator new[](v56 + 788);
        Block = v40;
        *v40 = v39;
        v40[1] = 6;
        v40[68] = v56;
        v40[2] = 1;
        v41 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v61, v40 + 3);
        SuplRootCertificate = CspRegistry::ReadSuplRootCertificate(v41, v42, v43, v44, v43);
        if ( SuplRootCertificate < 0 )
          goto LABEL_67;
        v38 = (__int64 **)(a1 + 120);
        SuplRootCertificate = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *))(**(_QWORD **)(a1 + 120) + 152LL))(
                                *(_QWORD *)(a1 + 120),
                                *v40,
                                v40);
        if ( SuplRootCertificate < 0 )
        {
          *(_DWORD *)(a1 + 960) = 1;
LABEL_67:
          std::unique_ptr<__MIDL___MIDL_itf_wifipe_0000_0000_0006 [0]>::~unique_ptr<__MIDL___MIDL_itf_wifipe_0000_0000_0006 [0]>(&Block);
LABEL_68:
          std::wstring::_Tidy_deallocate(v61);
          break;
        }
        v37 = (_DWORD *)(a1 + 164);
        if ( *(_DWORD *)(a1 + 164) < 2u )
        {
          std::unique_ptr<__MIDL___MIDL_itf_wifipe_0000_0000_0006 [0]>::~unique_ptr<__MIDL___MIDL_itf_wifipe_0000_0000_0006 [0]>(&Block);
          std::wstring::_Tidy_deallocate(v61);
LABEL_59:
          v45 = *v38;
          v46 = **v38;
          if ( *v37 >= 5u )
            (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v46 + 56))(v45, v8, v53[0], v52);
          else
            (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))(v46 + 48))(v45, v8, 0);
          SuplRootCertificate = (*(__int64 (__fastcall **)(__int64 *, _DWORD *, _QWORD))(**v38 + 144))(*v38, v62, v12);
          if ( (unsigned int)dword_1801DDF30 > 4 )
          {
            v54 = (HSTRING)v64;
            *(_QWORD *)v53 = MultiByteStr;
            LODWORD(Block) = v12;
            v50 = SuplRootCertificate;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v47,
              &word_1801AFD36);
          }
          if ( SuplRootCertificate < 0 )
LABEL_42:
            *(_DWORD *)(a1 + 960) = 1;
          break;
        }
        std::unique_ptr<__MIDL___MIDL_itf_wifipe_0000_0000_0006 [0]>::~unique_ptr<__MIDL___MIDL_itf_wifipe_0000_0000_0006 [0]>(&Block);
      }
      else
      {
        if ( !v31 || SuplRootCertificateSize != -2147024894 )
          goto LABEL_68;
        v37 = (_DWORD *)(a1 + 164);
        v38 = (__int64 **)(a1 + 120);
      }
      ++v31;
      std::wstring::_Tidy_deallocate(v61);
      if ( v31 >= 6 )
        goto LABEL_59;
    }
  }
LABEL_69:
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(newString);
  return (unsigned int)SuplRootCertificate;
}

```

## disassembly

```asm
0x1800e3790  mov     [rsp-8+arg_8], rbx
0x1800e3795  push    rbp
0x1800e3796  push    rsi
0x1800e3797  push    rdi
0x1800e3798  push    r12
0x1800e379a  push    r13
0x1800e379c  push    r14
0x1800e379e  push    r15
0x1800e37a0  lea     rbp, [rsp-430h]
0x1800e37a8  sub     rsp, 530h
0x1800e37af  mov     rax, cs:__security_cookie
0x1800e37b6  xor     rax, rsp
0x1800e37b9  mov     [rbp+460h+var_40], rax
0x1800e37c0  mov     rsi, r9
0x1800e37c3  mov     r14d, r8d
0x1800e37c6  mov     rdi, rcx
0x1800e37c9  mov     rax, [rbp+460h+arg_20]
0x1800e37d0  mov     [rsp+560h+var_508], rax
0x1800e37d5  xor     r15d, r15d
0x1800e37d8  mov     [rsp+560h+var_51C], r15d
0x1800e37dd  xor     edx, edx; Val
0x1800e37df  mov     r8d, 414h; Size
0x1800e37e5  lea     rcx, [rbp+460h+var_490]; void *
0x1800e37e9  call    memset_0
0x1800e37ee  lea     r13d, [r15+1]
0x1800e37f2  mov     [rbp+460h+var_4E0], r13d
0x1800e37f6  mov     [rsp+560h+var_510], r15d
0x1800e37fb  mov     [rsp+560h+var_518], r15d
0x1800e3800  mov     [rbp+460h+newString], r15
0x1800e3804  mov     [rbp+460h+string], r15
0x1800e3808  mov     [rbp+460h+Block], r15
0x1800e380c  lea     r8, [rbp+460h+Block]; unsigned __int16 **
0x1800e3810  lea     rdx, aFullversion; "FullVersion"
0x1800e3817  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\lf"...
0x1800e381e  call    ?ReadStringWithSubkey@CspRegistry@@CAJPEBG0PEAPEAG@Z; CspRegistry::ReadStringWithSubkey(ushort const *,ushort const *,ushort * *)
0x1800e3823  mov     ebx, eax
0x1800e3825  test    eax, eax
0x1800e3827  js      short loc_1800E3846
0x1800e3829  lea     r9, [rsp+560h+var_518]; unsigned int *
0x1800e382e  lea     r8, [rsp+560h+var_510]; unsigned int *
0x1800e3833  lea     rdx, [rbp+460h+var_4E0]; unsigned int *
0x1800e3837  mov     rcx, [rbp+460h+Block]; unsigned __int16 *
0x1800e383b  call    ?ParseSuplVersion@CspRegistry@@SAJPEBGPEAK11@Z; CspRegistry::ParseSuplVersion(ushort const *,ulong *,ulong *,ulong *)
0x1800e3840  mov     ebx, eax
0x1800e3842  mov     r13d, [rbp+460h+var_4E0]
0x1800e3846  mov     rcx, [rbp+460h+Block]; Block
0x1800e384a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e384f  test    ebx, ebx
0x1800e3851  jns     short loc_1800E3867
0x1800e3853  lea     rdx, [rbp+460h+var_4E0]; unsigned int *
0x1800e3857  lea     rcx, pwzName; "Version"
0x1800e385e  call    ?ReadDword@CspRegistry@@SAJPEBGPEAK@Z; CspRegistry::ReadDword(ushort const *,ulong *)
0x1800e3863  mov     r13d, [rbp+460h+var_4E0]
0x1800e3867  mov     ecx, r14d
0x1800e386a  call    ?IsCDMA@CSuplHandler@@CAHW4DataClasses@NetworkOperators@Networking@Windows@@@Z; CSuplHandler::IsCDMA(Windows::Networking::NetworkOperators::DataClasses)
0x1800e386f  test    eax, eax
0x1800e3871  jz      short loc_1800E388C
0x1800e3873  cmp     dword ptr [rdi+0A4h], 2
0x1800e387a  jb      short loc_1800E3882
0x1800e387c  cmp     r13d, 2
0x1800e3880  jnb     short loc_1800E388C
0x1800e3882  mov     ebx, 80070032h
0x1800e3887  jmp     loc_1800E3DE4
0x1800e388c  mov     r12d, r15d
0x1800e388f  mov     [rbp+460h+var_48C], 6
0x1800e3896  mov     [rbp+460h+var_490], 414h
0x1800e389d  test    rsi, rsi
0x1800e38a0  jz      loc_1800E3ADC
0x1800e38a6  mov     rcx, [rbp+460h+string]; string
0x1800e38aa  call    cs:__imp_WindowsDeleteString
0x1800e38b0  mov     [rbp+460h+string], r15
0x1800e38b4  mov     rcx, [rbp+460h+newString]; string
0x1800e38b8  call    cs:__imp_WindowsDeleteString
0x1800e38be  mov     [rbp+460h+newString], r15
0x1800e38c2  mov     rcx, rsi; string
0x1800e38c5  call    cs:__imp_WindowsGetStringLen
0x1800e38cb  mov     r14d, eax
0x1800e38ce  lea     r9, [rbp+460h+newString]; newString
0x1800e38d2  xor     edx, edx; startIndex
0x1800e38d4  lea     r8d, [rdx+3]; length
0x1800e38d8  mov     rcx, rsi; string
0x1800e38db  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x1800e38e1  mov     ebx, eax
0x1800e38e3  test    eax, eax
0x1800e38e5  js      short loc_1800E3903
0x1800e38e7  lea     r8d, [r14-4]; length
0x1800e38eb  lea     r9, [rbp+460h+string]; newString
0x1800e38ef  mov     edx, 3; startIndex
0x1800e38f4  mov     rcx, rsi; string
0x1800e38f7  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x1800e38fd  mov     ebx, eax
0x1800e38ff  test    eax, eax
0x1800e3901  jns     short loc_1800E3923
0x1800e3903  mov     rcx, [rbp+468h]; this
0x1800e390a  mov     r9d, ebx; char *
0x1800e390d  lea     r8, aOnecoreuapDriv_19; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800e3914  mov     edx, 179h; void *
0x1800e3919  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e391e  jmp     loc_1800E3DE4
0x1800e3923  mov     [rbp+460h+length], r15d
0x1800e3927  lea     rdx, [rbp+460h+length]; length
0x1800e392b  mov     rcx, [rbp+460h+newString]; string
0x1800e392f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e3935  mov     ebx, 0Ah
0x1800e393a  mov     r8d, ebx; Radix
0x1800e393d  xor     edx, edx; EndPtr
0x1800e393f  mov     rcx, rax; String
0x1800e3942  call    cs:__imp_wcstol
0x1800e3948  mov     r14d, eax
0x1800e394b  lea     rdx, [rbp+460h+length]; length
0x1800e394f  mov     rcx, [rbp+460h+string]; string
0x1800e3953  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e3959  mov     r8d, ebx; Radix
0x1800e395c  xor     edx, edx; EndPtr
0x1800e395e  mov     rcx, rax; String
0x1800e3961  call    cs:__imp_wcstol
0x1800e3967  mov     r15d, eax
0x1800e396a  mov     edx, eax; unsigned int
0x1800e396c  mov     ecx, r14d; unsigned int
0x1800e396f  call    ?IsCompatibleWithImsi@CspRegistry@@SAJKK@Z; CspRegistry::IsCompatibleWithImsi(ulong,ulong)
0x1800e3974  mov     ebx, eax
0x1800e3976  mov     ecx, cs:dword_1801DDEF8
0x1800e397c  cmp     ecx, 4
0x1800e397f  jbe     short loc_1800E39BC
0x1800e3981  mov     [rbp+460h+var_4E0], r15d
0x1800e3985  mov     [rsp+560h+var_520], r14d
0x1800e398a  mov     dword ptr [rbp+460h+Block], eax
0x1800e398d  lea     rax, [rbp+460h+var_4E0]
0x1800e3991  mov     [rsp+560h+lpDefaultChar], rax
0x1800e3996  lea     rax, [rsp+560h+var_520]
0x1800e399b  mov     qword ptr [rsp+560h+cbMultiByte], rax
0x1800e39a0  lea     rax, [rbp+460h+Block]
0x1800e39a4  mov     [rsp+560h+lpMultiByteStr], rax
0x1800e39a9  lea     rdx, unk_1801AFE78
0x1800e39b0  lea     rcx, dword_1801DDEF8
0x1800e39b7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800e39bc  test    ebx, ebx
0x1800e39be  js      loc_1800E3DE4
0x1800e39c4  cmp     ebx, 1
0x1800e39c7  jnz     short loc_1800E39D3
0x1800e39c9  mov     ebx, 80070490h
0x1800e39ce  jmp     loc_1800E3DE4
0x1800e39d3  lea     rdx, [rsp+560h+var_51C]; unsigned int *
0x1800e39d8  lea     rcx, aDisablehslpfro; "DisableHslpFromUicc"
0x1800e39df  call    ?ReadDword@CspRegistry@@SAJPEBGPEAK@Z; CspRegistry::ReadDword(ushort const *,ulong *)
0x1800e39e4  mov     dword ptr [rsp+560h+lpMultiByteStr], r14d
0x1800e39e9  mov     r9d, r15d
0x1800e39ec  lea     r8, aHSlpMnc33dMcc3; "h-slp.mnc%3.3d.mcc%3.3d.pub.3gppnetwork"...
0x1800e39f3  mov     edx, 104h; unsigned __int64
0x1800e39f8  lea     rcx, [rbp+460h+var_384]; char *
0x1800e39ff  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800e3a04  mov     ebx, eax
0x1800e3a06  xor     r15d, r15d
0x1800e3a09  test    eax, eax
0x1800e3a0b  jns     short loc_1800E3A40
0x1800e3a0d  mov     ecx, cs:dword_1801DDF30
0x1800e3a13  cmp     ecx, 4
0x1800e3a16  jbe     loc_1800E3DE4
0x1800e3a1c  mov     dword ptr [rbp+460h+Block], eax
0x1800e3a1f  lea     rax, [rbp+460h+Block]
0x1800e3a23  lea     rdx, dword_1801AFE44
0x1800e3a2a  mov     [rsp+560h+lpMultiByteStr], rax
0x1800e3a2f  lea     rcx, dword_1801DDF30
0x1800e3a36  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800e3a3b  jmp     loc_1800E3DE4
0x1800e3a40  cmp     [rsp+560h+var_51C], r15d
0x1800e3a45  jnz     loc_1800E3ADC
0x1800e3a4b  mov     rax, [rsp+560h+var_508]
0x1800e3a50  test    rax, rax
0x1800e3a53  jz      loc_1800E3ADC
0x1800e3a59  mov     dword ptr [rbp+460h+Block], r15d
0x1800e3a5d  lea     rdx, [rbp+460h+Block]; length
0x1800e3a61  mov     rcx, rax; string
0x1800e3a64  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e3a6a  mov     [rsp+560h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800e3a6f  mov     [rsp+560h+lpDefaultChar], r15; lpDefaultChar
0x1800e3a74  mov     [rsp+560h+cbMultiByte], 104h; cbMultiByte
0x1800e3a7c  lea     rcx, [rbp+460h+MultiByteStr]
0x1800e3a80  mov     [rsp+560h+lpMultiByteStr], rcx; lpMultiByteStr
0x1800e3a85  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800e3a89  mov     r8, rax; lpWideCharStr
0x1800e3a8c  xor     edx, edx; dwFlags
0x1800e3a8e  mov     ecx, 0FDE9h; CodePage
0x1800e3a93  call    cs:__imp_WideCharToMultiByte
0x1800e3a99  test    eax, eax
0x1800e3a9b  jnz     short loc_1800E3AD6
0x1800e3a9d  call    cs:__imp_GetLastError
0x1800e3aa3  mov     ebx, eax
0x1800e3aa5  test    eax, eax
0x1800e3aa7  jle     short loc_1800E3AB2
0x1800e3aa9  movzx   ebx, ax
0x1800e3aac  or      ebx, 80070000h
0x1800e3ab2  mov     eax, cs:dword_1801DDF30
0x1800e3ab8  cmp     eax, 4
0x1800e3abb  jbe     loc_1800E3DE4
0x1800e3ac1  mov     [rsp+560h+var_520], ebx
0x1800e3ac5  lea     rax, [rsp+560h+var_520]
0x1800e3aca  lea     rdx, word_1801AFC2A
0x1800e3ad1  jmp     loc_1800E3A2A
0x1800e3ad6  mov     r12d, 2
0x1800e3adc  cmp     [rbp+460h+MultiByteStr], r15b
0x1800e3ae0  jnz     loc_1800E3B6E
0x1800e3ae6  lea     r8, [rbp+460h+MultiByteStr]; char *
0x1800e3aea  lea     rdx, aAddr; "Addr"
0x1800e3af1  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\lf"...
0x1800e3af8  call    ?ReadStringWithSubkeyA@CspRegistry@@CAJPEBG0PEADK@Z; CspRegistry::ReadStringWithSubkeyA(ushort const *,ushort const *,char *,ulong)
0x1800e3afd  test    eax, eax
0x1800e3aff  jns     short loc_1800E3B2D
0x1800e3b01  mov     ecx, cs:dword_1801DDF30
0x1800e3b07  cmp     ecx, 4
0x1800e3b0a  jbe     short loc_1800E3B33
0x1800e3b0c  mov     dword ptr [rbp+460h+Block], eax
0x1800e3b0f  lea     rax, [rbp+460h+Block]
0x1800e3b13  mov     [rsp+560h+lpMultiByteStr], rax
0x1800e3b18  lea     rdx, byte_1801AFF5B
0x1800e3b1f  lea     rcx, dword_1801DDF30
0x1800e3b26  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800e3b2b  jmp     short loc_1800E3B33
0x1800e3b2d  mov     r12d, 1
0x1800e3b33  cmp     [rbp+460h+MultiByteStr], r15b
0x1800e3b37  jnz     short loc_1800E3B6E
0x1800e3b39  test    rsi, rsi
0x1800e3b3c  jnz     short loc_1800E3B48
0x1800e3b3e  mov     ebx, 80070057h
0x1800e3b43  jmp     loc_1800E3DE4
0x1800e3b48  lea     r8, [rbp+460h+var_384]; char *
0x1800e3b4f  mov     edx, 104h; unsigned __int64
0x1800e3b54  lea     rcx, [rbp+460h+MultiByteStr]; char *
0x1800e3b58  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800e3b5d  test    eax, eax
0x1800e3b5f  jns     short loc_1800E3B68
0x1800e3b61  mov     ebx, eax
0x1800e3b63  jmp     loc_1800E3DE4
0x1800e3b68  mov     r12d, 3
0x1800e3b6e  mov     rcx, rdi
0x1800e3b71  call    ?PurgeAllCertificates@CSuplHandler@@AEAAJUwrite_lock_required@wil@@@Z; CSuplHandler::PurgeAllCertificates(wil::write_lock_required)
0x1800e3b76  mov     ebx, eax
0x1800e3b78  test    eax, eax
0x1800e3b7a  jns     short loc_1800E3B8B
0x1800e3b7c  mov     dword ptr [rdi+3C0h], 1
0x1800e3b86  jmp     loc_1800E3DE4
0x1800e3b8b  mov     esi, r15d
0x1800e3b8e  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\lf"...
0x1800e3b95  lea     rcx, [rbp+460h+var_4B8]
0x1800e3b99  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e3b9e  nop
0x1800e3b9f  test    esi, esi
0x1800e3ba1  jz      short loc_1800E3C15
0x1800e3ba3  lea     r9, [rbp+460h+var_46]
0x1800e3baa  mov     r8d, esi
0x1800e3bad  inc     r8
0x1800e3bb0  sub     r9, 2
0x1800e3bb4  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800e3bbe  mul     r8
0x1800e3bc1  shr     rdx, 3
0x1800e3bc5  movzx   eax, dx
0x1800e3bc8  shl     ax, 2
0x1800e3bcc  lea     ecx, [rax+rdx]
0x1800e3bcf  add     cx, cx
0x1800e3bd2  sub     r8w, cx
0x1800e3bd6  add     r8w, 30h ; '0'
0x1800e3bdb  mov     [r9], r8w
0x1800e3bdf  mov     r8, rdx
0x1800e3be2  test    rdx, rdx
0x1800e3be5  jnz     short loc_1800E3BB0
0x1800e3be7  lea     r8, [rbp+460h+var_46]
0x1800e3bee  mov     rdx, r9
0x1800e3bf1  lea     rcx, [rsp+560h+var_500]
0x1800e3bf6  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x1800e3bfb  nop
0x1800e3bfc  lea     rdx, [rsp+560h+var_500]
0x1800e3c01  lea     rcx, [rbp+460h+var_4B8]
0x1800e3c05  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800e3c0a  nop
0x1800e3c0b  lea     rcx, [rsp+560h+var_500]
0x1800e3c10  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3c15  mov     [rbp+460h+var_4E0], r15d
0x1800e3c19  lea     rcx, [rbp+460h+var_4B8]
0x1800e3c1d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e3c22  mov     rcx, rax; unsigned __int16 *
0x1800e3c25  lea     rdx, [rbp+460h+var_4E0]; unsigned int *
0x1800e3c29  call    ?GetSuplRootCertificateSize@CspRegistry@@SAJPEBGPEAK@Z; CspRegistry::GetSuplRootCertificateSize(ushort const *,ulong *)
0x1800e3c2e  mov     ebx, eax
0x1800e3c30  test    eax, eax
0x1800e3c32  jns     short loc_1800E3C57
0x1800e3c34  test    esi, esi
0x1800e3c36  jz      loc_1800E3DDA
0x1800e3c3c  cmp     eax, 80070002h
0x1800e3c41  jnz     loc_1800E3DDA
0x1800e3c47  lea     rbx, [rdi+0A4h]
0x1800e3c4e  lea     r15, [rdi+78h]
0x1800e3c52  jmp     loc_1800E3CF1
0x1800e3c57  mov     ebx, [rbp+460h+var_4E0]
0x1800e3c5a  add     ebx, 314h
0x1800e3c60  mov     ecx, ebx; unsigned __int64
0x1800e3c62  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800e3c67  mov     r14, rax
0x1800e3c6a  mov     [rbp+460h+Block], rax
0x1800e3c6e  mov     [rax], ebx
0x1800e3c70  mov     dword ptr [rax+4], 6
  ... truncated ...
```
