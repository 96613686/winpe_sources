# DiagnosticRunner::ParseResultsToMap(ushort const *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> * *)

- ea: `0x18001fa50`
- end: `0x18002001d`
- name: `?ParseResultsToMap@DiagnosticRunner@@UEAAJPEBGPEAPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `1485`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001720`
- `0x180001e7c`
- `0x180003b84`
- `0x1800096dc`
- `0x18001f758`
- `0x18001fa50`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001fabe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001fabe`
- `OLEAUT32!__imp_SysAllocString` at `0x18001fac9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001fd26`
- `OLEAUT32!__imp_SysAllocString` at `0x18001fac9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001fd26`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fffe`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fffe`

## string_xrefs

- `0x18001faf8`: `Create xml document object`
- `0x18001fbd3`: `Create xml document - put async`
- `0x18001fca4`: `Create xml document - load xml document`
- `0x18001fd19`: `XPath`
- `0x18001fda4`: `Create xml document - set selectionlanguage`
- `0x18001fe6a`: `Create xml document - select rootcause note`
- `0x18001ff5d`: `Parse xml collection to Map`

## pseudocode

```c
__int64 __fastcall DiagnosticRunner::ParseResultsToMap(__int64 a1, const OLECHAR *a2, __int64 *a3)
{
  int v6; // ebx
  BSTR v7; // rax
  __int64 v8; // rdx
  const char *v9; // r8
  OLECHAR *v10; // r14
  __int64 v11; // r9
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // r9
  void *v22; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rsi
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // r9
  int v30; // [rsp+60h] [rbp-29h] BYREF
  __int64 v31; // [rsp+68h] [rbp-21h] BYREF
  const char *v32; // [rsp+70h] [rbp-19h] BYREF
  const char *v33; // [rsp+78h] [rbp-11h] BYREF
  const char *v34; // [rsp+80h] [rbp-9h] BYREF
  __int64 v35; // [rsp+88h] [rbp-1h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp+7h] BYREF
  __int64 v37; // [rsp+98h] [rbp+Fh] BYREF
  __int128 v38; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v39; // [rsp+B0h] [rbp+27h]
  __int16 v40; // [rsp+F8h] [rbp+6Fh] BYREF
  int v41; // [rsp+108h] [rbp+7Fh] BYREF

  ppv = 0;
  v40 = -1;
  v37 = 0;
  if ( a2 && a3 )
  {
    *a3 = 0;
    v6 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x15u, &IID_IXMLDOMDocument2, &ppv);
    v7 = SysAllocString(a2);
    v9 = "DiagnosticRunner::ParseResultsToMap";
    v10 = v7;
    if ( (unsigned int)dword_180039000 > 5
      && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180039000, v8, "DiagnosticRunner::ParseResultsToMap") )
    {
      v41 = 795;
      v34 = "Create xml document object";
      v31 = a1 + 64;
      v35 = a1 + 193;
      v32 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
      v33 = v9;
      v30 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        a1 + 64,
        (__int64)&unk_180031D10,
        (__int64)v9,
        v11,
        &v35,
        (__int64)&v30,
        &v34,
        &v33,
        &v32,
        (__int64)&v41,
        &v31);
    }
    if ( v10 )
    {
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const char *))(*(_QWORD *)ppv + 504LL))(ppv, 0, v9);
        if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180039000, v8, v9) )
        {
          v41 = 810;
          v33 = "DiagnosticRunner::ParseResultsToMap";
          v35 = a1 + 64;
          v32 = "Create xml document - put async";
          v34 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
          v31 = a1 + 193;
          v30 = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            a1 + 64,
            (__int64)byte_180031C9D,
            (__int64)v9,
            v12,
            &v31,
            (__int64)&v30,
            &v32,
            &v33,
            &v34,
            (__int64)&v41,
            &v35);
        }
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, v10, &v40);
          if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v13, v8, v9) )
          {
            v41 = 821;
            v35 = a1 + 64;
            v34 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
            v33 = "DiagnosticRunner::ParseResultsToMap";
            v32 = "Create xml document - load xml document";
            v31 = a1 + 193;
            v30 = v6;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v14,
              (__int64)word_180031C2A,
              (__int64)v9,
              v15,
              &v31,
              (__int64)&v30,
              &v32,
              &v33,
              &v34,
              (__int64)&v41,
              &v35);
          }
          if ( v6 >= 0 )
          {
            if ( v40 != -1 )
              goto LABEL_22;
            v38 = 0;
            *((_QWORD *)&v38 + 1) = SysAllocString(L"XPath");
            v39 = 0;
            LOWORD(v38) = 8;
            v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int128 *))(*(_QWORD *)ppv + 640LL))(
                   ppv,
                   L"SelectionLanguage",
                   &v38);
            if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v16, v8, v9) )
            {
              v41 = 837;
              v35 = a1 + 64;
              v34 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
              v33 = "DiagnosticRunner::ParseResultsToMap";
              v32 = "Create xml document - set selectionlanguage";
              v31 = a1 + 193;
              v30 = v6;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v17,
                (__int64)&byte_180031BB7,
                (__int64)v9,
                v18,
                &v31,
                (__int64)&v30,
                &v32,
                &v33,
                &v34,
                (__int64)&v41,
                &v35);
            }
            if ( v6 >= 0 )
            {
LABEL_22:
              v6 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int64 *))(*(_QWORD *)ppv + 288LL))(
                     ppv,
                     L"/Rootcauses/Rootcause",
                     &v37);
              if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v19, v8, v9) )
              {
                v41 = 848;
                v35 = a1 + 64;
                v34 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
                v33 = "DiagnosticRunner::ParseResultsToMap";
                v32 = "Create xml document - select rootcause note";
                v31 = a1 + 193;
                v30 = v6;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  v20,
                  (__int64)&dword_180031B44,
                  (__int64)v9,
                  v21,
                  &v31,
                  (__int64)&v30,
                  &v32,
                  &v33,
                  &v34,
                  (__int64)&v41,
                  &v35);
              }
              if ( v6 >= 0 && v37 )
              {
                v22 = operator new(0x10u);
                if ( v22 )
                  v25 = std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v22);
                else
                  v25 = 0;
                v6 = DiagnosticRunner::ParseNodeCollectionItemsToMap(a1, v37, v23, v24, v25);
                if ( v6 >= 0 )
                  *a3 = v25;
                if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v26, v8, v9) )
                {
                  v41 = 873;
                  v35 = a1 + 64;
                  v30 = v6;
                  v34 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
                  v33 = "DiagnosticRunner::ParseResultsToMap";
                  v32 = "Parse xml collection to Map";
                  v31 = a1 + 193;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                    v27,
                    (__int64)byte_180031AD1,
                    (__int64)v9,
                    v28,
                    &v31,
                    (__int64)&v30,
                    &v32,
                    &v33,
                    &v34,
                    (__int64)&v41,
                    &v35);
                }
                if ( v37 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                  v37 = 0;
                }
              }
            }
          }
        }
      }
    }
    else
    {
      v6 = -2147024882;
    }
    if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID, __int64, const char *))(*(_QWORD *)ppv + 16LL))(ppv, v8, v9);
      ppv = 0;
    }
  }
  else
  {
    v10 = 0;
    v6 = -2147024809;
  }
  SysFreeString(v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001fa50  mov     [rsp-8+arg_0], rbx
0x18001fa55  push    rbp
0x18001fa56  push    rsi
0x18001fa57  push    rdi
0x18001fa58  push    r14
0x18001fa5a  push    r15
0x18001fa5c  lea     rbp, [rsp-37h]
0x18001fa61  sub     rsp, 0C0h
0x18001fa68  or      eax, 0FFFFFFFFh
0x18001fa6b  mov     [rbp+57h+var_50], 0
0x18001fa73  mov     [rbp+57h+arg_8], ax
0x18001fa77  mov     r15, r8
0x18001fa7a  mov     [rbp+57h+var_48], 0
0x18001fa82  mov     rsi, rdx
0x18001fa85  mov     rdi, rcx
0x18001fa88  test    rdx, rdx
0x18001fa8b  jz      loc_18001FFF3
0x18001fa91  test    r8, r8
0x18001fa94  jz      loc_18001FFF3
0x18001fa9a  xor     edx, edx; pUnkOuter
0x18001fa9c  mov     qword ptr [r8], 0
0x18001faa3  lea     rax, [rbp+57h+var_50]
0x18001faa7  lea     r9, IID_IXMLDOMDocument2; riid
0x18001faae  mov     [rsp+0E0h+ppv], rax; ppv
0x18001fab3  lea     rcx, CLSID_DOMDocument60; rclsid
0x18001faba  lea     r8d, [rdx+15h]; dwClsContext
0x18001fabe  call    cs:__imp_CoCreateInstance
0x18001fac4  mov     rcx, rsi; psz
0x18001fac7  mov     ebx, eax
0x18001fac9  call    cs:__imp_SysAllocString
0x18001facf  mov     ecx, cs:dword_180039000
0x18001fad5  lea     rsi, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x18001fadc  lea     r8, aDiagnosticrunn_2; "DiagnosticRunner::ParseResultsToMap"
0x18001fae3  mov     r14, rax
0x18001fae6  cmp     ecx, 5
0x18001fae9  jbe     loc_18001FB73
0x18001faef  call    _tlgKeywordOn
0x18001faf4  test    al, al
0x18001faf6  jz      short loc_18001FB73
0x18001faf8  lea     rax, aCreateXmlDocum_3; "Create xml document object"
0x18001faff  mov     [rbp+57h+arg_18], 31Bh
0x18001fb06  mov     [rbp+57h+var_60], rax
0x18001fb0a  lea     rcx, [rdi+40h]
0x18001fb0e  lea     rax, [rdi+0C1h]
0x18001fb15  mov     [rbp+57h+var_78], rcx
0x18001fb19  mov     [rbp+57h+var_58], rax
0x18001fb1d  lea     rdx, unk_180031D10
0x18001fb24  lea     rax, [rbp+57h+var_78]
0x18001fb28  mov     [rbp+57h+var_70], rsi
0x18001fb2c  mov     [rsp+0E0h+var_90], rax
0x18001fb31  lea     rax, [rbp+57h+arg_18]
0x18001fb35  mov     [rsp+0E0h+var_98], rax
0x18001fb3a  lea     rax, [rbp+57h+var_70]
0x18001fb3e  mov     [rsp+0E0h+var_A0], rax
0x18001fb43  lea     rax, [rbp+57h+var_68]
0x18001fb47  mov     [rsp+0E0h+var_A8], rax
0x18001fb4c  lea     rax, [rbp+57h+var_60]
0x18001fb50  mov     [rsp+0E0h+var_B0], rax
0x18001fb55  lea     rax, [rbp+57h+var_80]
0x18001fb59  mov     [rsp+0E0h+var_B8], rax
0x18001fb5e  lea     rax, [rbp+57h+var_58]
0x18001fb62  mov     [rsp+0E0h+ppv], rax
0x18001fb67  mov     [rbp+57h+var_68], r8
0x18001fb6b  mov     [rbp+57h+var_80], ebx
0x18001fb6e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001fb73  test    r14, r14
0x18001fb76  jnz     short loc_18001FB82
0x18001fb78  mov     ebx, 8007000Eh
0x18001fb7d  jmp     loc_18001FFD4
0x18001fb82  test    ebx, ebx
0x18001fb84  js      loc_18001FFD4
0x18001fb8a  mov     rcx, [rbp+57h+var_50]
0x18001fb8e  xor     edx, edx
0x18001fb90  mov     rax, [rcx]
0x18001fb93  mov     rax, [rax+1F8h]
0x18001fb9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb9f  mov     ecx, cs:dword_180039000
0x18001fba5  mov     ebx, eax
0x18001fba7  cmp     ecx, 5
0x18001fbaa  jbe     loc_18001FC3F
0x18001fbb0  call    _tlgKeywordOn
0x18001fbb5  test    al, al
0x18001fbb7  jz      loc_18001FC3F
0x18001fbbd  lea     rax, aDiagnosticrunn_2; "DiagnosticRunner::ParseResultsToMap"
0x18001fbc4  mov     [rbp+57h+arg_18], 32Ah
0x18001fbcb  mov     [rbp+57h+var_68], rax
0x18001fbcf  lea     rcx, [rdi+40h]
0x18001fbd3  lea     rax, aCreateXmlDocum; "Create xml document - put async"
0x18001fbda  mov     [rbp+57h+var_58], rcx
0x18001fbde  mov     [rbp+57h+var_70], rax
0x18001fbe2  lea     rdx, byte_180031C9D
0x18001fbe9  lea     rax, [rdi+0C1h]
0x18001fbf0  mov     [rbp+57h+var_60], rsi
0x18001fbf4  mov     [rbp+57h+var_78], rax
0x18001fbf8  lea     rax, [rbp+57h+var_58]
0x18001fbfc  mov     [rsp+0E0h+var_90], rax
0x18001fc01  lea     rax, [rbp+57h+arg_18]
0x18001fc05  mov     [rsp+0E0h+var_98], rax
0x18001fc0a  lea     rax, [rbp+57h+var_60]
0x18001fc0e  mov     [rsp+0E0h+var_A0], rax
0x18001fc13  lea     rax, [rbp+57h+var_68]
0x18001fc17  mov     [rsp+0E0h+var_A8], rax
0x18001fc1c  lea     rax, [rbp+57h+var_70]
0x18001fc20  mov     [rsp+0E0h+var_B0], rax
0x18001fc25  lea     rax, [rbp+57h+var_80]
0x18001fc29  mov     [rsp+0E0h+var_B8], rax
0x18001fc2e  lea     rax, [rbp+57h+var_78]
0x18001fc32  mov     [rsp+0E0h+ppv], rax
0x18001fc37  mov     [rbp+57h+var_80], ebx
0x18001fc3a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001fc3f  test    ebx, ebx
0x18001fc41  js      loc_18001FFD4
0x18001fc47  mov     rcx, [rbp+57h+var_50]
0x18001fc4b  lea     r8, [rbp+57h+arg_8]
0x18001fc4f  mov     rdx, r14
0x18001fc52  mov     rax, [rcx]
0x18001fc55  mov     rax, [rax+208h]
0x18001fc5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc61  mov     ebx, eax
0x18001fc63  mov     eax, cs:dword_180039000
0x18001fc69  cmp     eax, 5
0x18001fc6c  jbe     loc_18001FD01
0x18001fc72  call    _tlgKeywordOn
0x18001fc77  test    al, al
0x18001fc79  jz      loc_18001FD01
0x18001fc7f  lea     rax, [rdi+40h]
0x18001fc83  mov     [rbp+57h+arg_18], 335h
0x18001fc8a  mov     [rbp+57h+var_58], rax
0x18001fc8e  lea     rdx, word_180031C2A
0x18001fc95  lea     rax, aDiagnosticrunn_2; "DiagnosticRunner::ParseResultsToMap"
0x18001fc9c  mov     [rbp+57h+var_60], rsi
0x18001fca0  mov     [rbp+57h+var_68], rax
0x18001fca4  lea     rax, aCreateXmlDocum_0; "Create xml document - load xml document"
0x18001fcab  mov     [rbp+57h+var_70], rax
0x18001fcaf  lea     rax, [rdi+0C1h]
0x18001fcb6  mov     [rbp+57h+var_78], rax
0x18001fcba  lea     rax, [rbp+57h+var_58]
0x18001fcbe  mov     [rsp+0E0h+var_90], rax
0x18001fcc3  lea     rax, [rbp+57h+arg_18]
0x18001fcc7  mov     [rsp+0E0h+var_98], rax
0x18001fccc  lea     rax, [rbp+57h+var_60]
0x18001fcd0  mov     [rsp+0E0h+var_A0], rax
0x18001fcd5  lea     rax, [rbp+57h+var_68]
0x18001fcd9  mov     [rsp+0E0h+var_A8], rax
0x18001fcde  lea     rax, [rbp+57h+var_70]
0x18001fce2  mov     [rsp+0E0h+var_B0], rax
0x18001fce7  lea     rax, [rbp+57h+var_80]
0x18001fceb  mov     [rsp+0E0h+var_B8], rax
0x18001fcf0  lea     rax, [rbp+57h+var_78]
0x18001fcf4  mov     [rsp+0E0h+ppv], rax
0x18001fcf9  mov     [rbp+57h+var_80], ebx
0x18001fcfc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001fd01  test    ebx, ebx
0x18001fd03  js      loc_18001FFD4
0x18001fd09  or      eax, 0FFFFFFFFh
0x18001fd0c  cmp     [rbp+57h+arg_8], ax
0x18001fd10  jnz     loc_18001FE09
0x18001fd16  xorps   xmm0, xmm0
0x18001fd19  lea     rcx, aXpath; "XPath"
0x18001fd20  movups  [rbp+57h+var_40], xmm0
0x18001fd24  xor     ebx, ebx
0x18001fd26  call    cs:__imp_SysAllocString
0x18001fd2c  mov     rcx, [rbp+57h+var_50]
0x18001fd30  lea     r8, [rbp+57h+var_40]
0x18001fd34  mov     qword ptr [rbp+57h+var_40+8], rax
0x18001fd38  lea     rdx, aSelectionlangu; "SelectionLanguage"
0x18001fd3f  lea     eax, [rbx+8]
0x18001fd42  mov     [rbp+57h+var_30], rbx
0x18001fd46  mov     word ptr [rbp+57h+var_40], ax
0x18001fd4a  mov     rax, [rcx]
0x18001fd4d  movups  xmm0, [rbp+57h+var_40]
0x18001fd51  mov     rax, [rax+280h]
0x18001fd58  movaps  [rbp+57h+var_40], xmm0
0x18001fd5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd61  mov     ebx, eax
0x18001fd63  mov     eax, cs:dword_180039000
0x18001fd69  cmp     eax, 5
0x18001fd6c  jbe     loc_18001FE01
0x18001fd72  call    _tlgKeywordOn
0x18001fd77  test    al, al
0x18001fd79  jz      loc_18001FE01
0x18001fd7f  lea     rax, [rdi+40h]
0x18001fd83  mov     [rbp+57h+arg_18], 345h
0x18001fd8a  mov     [rbp+57h+var_58], rax
0x18001fd8e  lea     rdx, byte_180031BB7
0x18001fd95  lea     rax, aDiagnosticrunn_2; "DiagnosticRunner::ParseResultsToMap"
0x18001fd9c  mov     [rbp+57h+var_60], rsi
0x18001fda0  mov     [rbp+57h+var_68], rax
0x18001fda4  lea     rax, aCreateXmlDocum_2; "Create xml document - set selectionlang"...
0x18001fdab  mov     [rbp+57h+var_70], rax
0x18001fdaf  lea     rax, [rdi+0C1h]
0x18001fdb6  mov     [rbp+57h+var_78], rax
0x18001fdba  lea     rax, [rbp+57h+var_58]
0x18001fdbe  mov     [rsp+0E0h+var_90], rax
0x18001fdc3  lea     rax, [rbp+57h+arg_18]
0x18001fdc7  mov     [rsp+0E0h+var_98], rax
0x18001fdcc  lea     rax, [rbp+57h+var_60]
0x18001fdd0  mov     [rsp+0E0h+var_A0], rax
0x18001fdd5  lea     rax, [rbp+57h+var_68]
0x18001fdd9  mov     [rsp+0E0h+var_A8], rax
0x18001fdde  lea     rax, [rbp+57h+var_70]
0x18001fde2  mov     [rsp+0E0h+var_B0], rax
0x18001fde7  lea     rax, [rbp+57h+var_80]
0x18001fdeb  mov     [rsp+0E0h+var_B8], rax
0x18001fdf0  lea     rax, [rbp+57h+var_78]
0x18001fdf4  mov     [rsp+0E0h+ppv], rax
0x18001fdf9  mov     [rbp+57h+var_80], ebx
0x18001fdfc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001fe01  test    ebx, ebx
0x18001fe03  js      loc_18001FFD4
0x18001fe09  mov     rcx, [rbp+57h+var_50]
0x18001fe0d  lea     r8, [rbp+57h+var_48]
0x18001fe11  lea     rdx, aRootcausesRoot; "/Rootcauses/Rootcause"
0x18001fe18  mov     rax, [rcx]
0x18001fe1b  mov     rax, [rax+120h]
0x18001fe22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe27  mov     ebx, eax
0x18001fe29  mov     eax, cs:dword_180039000
0x18001fe2f  cmp     eax, 5
0x18001fe32  jbe     loc_18001FEC7
0x18001fe38  call    _tlgKeywordOn
0x18001fe3d  test    al, al
0x18001fe3f  jz      loc_18001FEC7
0x18001fe45  lea     rax, [rdi+40h]
0x18001fe49  mov     [rbp+57h+arg_18], 350h
0x18001fe50  mov     [rbp+57h+var_58], rax
0x18001fe54  lea     rdx, dword_180031B44
0x18001fe5b  lea     rax, aDiagnosticrunn_2; "DiagnosticRunner::ParseResultsToMap"
0x18001fe62  mov     [rbp+57h+var_60], rsi
0x18001fe66  mov     [rbp+57h+var_68], rax
0x18001fe6a  lea     rax, aCreateXmlDocum_1; "Create xml document - select rootcause "...
0x18001fe71  mov     [rbp+57h+var_70], rax
0x18001fe75  lea     rax, [rdi+0C1h]
0x18001fe7c  mov     [rbp+57h+var_78], rax
0x18001fe80  lea     rax, [rbp+57h+var_58]
0x18001fe84  mov     [rsp+0E0h+var_90], rax
0x18001fe89  lea     rax, [rbp+57h+arg_18]
0x18001fe8d  mov     [rsp+0E0h+var_98], rax
0x18001fe92  lea     rax, [rbp+57h+var_60]
0x18001fe96  mov     [rsp+0E0h+var_A0], rax
0x18001fe9b  lea     rax, [rbp+57h+var_68]
0x18001fe9f  mov     [rsp+0E0h+var_A8], rax
0x18001fea4  lea     rax, [rbp+57h+var_70]
0x18001fea8  mov     [rsp+0E0h+var_B0], rax
0x18001fead  lea     rax, [rbp+57h+var_80]
0x18001feb1  mov     [rsp+0E0h+var_B8], rax
0x18001feb6  lea     rax, [rbp+57h+var_78]
0x18001feba  mov     [rsp+0E0h+ppv], rax
0x18001febf  mov     [rbp+57h+var_80], ebx
0x18001fec2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001fec7  test    ebx, ebx
0x18001fec9  js      loc_18001FFD4
0x18001fecf  cmp     [rbp+57h+var_48], 0
0x18001fed4  jz      loc_18001FFD4
0x18001feda  mov     ecx, 10h; Size
0x18001fedf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fee4  test    rax, rax
0x18001fee7  jz      short loc_18001FEF6
0x18001fee9  mov     rcx, rax
0x18001feec  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x18001fef1  mov     rsi, rax
0x18001fef4  jmp     short loc_18001FEF8
0x18001fef6  xor     esi, esi
0x18001fef8  mov     rdx, [rbp+57h+var_48]
0x18001fefc  mov     rcx, rdi
0x18001feff  mov     [rsp+0E0h+ppv], rsi
0x18001ff04  call    ?ParseNodeCollectionItemsToMap@DiagnosticRunner@@AEAAJPEAUIXMLDOMNodeList@@PEAG1PEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; DiagnosticRunner::ParseNodeCollectionItemsToMap(IXMLDOMNodeList *,ushort *,ushort *,std::map<std::wstring,std::wstring> *)
0x18001ff09  mov     ebx, eax
0x18001ff0b  test    eax, eax
0x18001ff0d  js      short loc_18001FF12
0x18001ff0f  mov     [r15], rsi
0x18001ff12  mov     eax, cs:dword_180039000
0x18001ff18  cmp     eax, 5
0x18001ff1b  jbe     loc_18001FFB7
0x18001ff21  call    _tlgKeywordOn
0x18001ff26  test    al, al
0x18001ff28  jz      loc_18001FFB7
0x18001ff2e  lea     rax, [rdi+40h]
0x18001ff32  mov     [rbp+57h+arg_18], 369h
0x18001ff39  mov     [rbp+57h+var_58], rax
0x18001ff3d  lea     rdx, byte_180031AD1
0x18001ff44  lea     rax, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x18001ff4b  mov     [rbp+57h+var_80], ebx
0x18001ff4e  mov     [rbp+57h+var_60], rax
0x18001ff52  lea     rax, aDiagnosticrunn_2; "DiagnosticRunner::ParseResultsToMap"
0x18001ff59  mov     [rbp+57h+var_68], rax
0x18001ff5d  lea     rax, aParseXmlCollec; "Parse xml collection to Map"
0x18001ff64  mov     [rbp+57h+var_70], rax
0x18001ff68  lea     rax, [rdi+0C1h]
0x18001ff6f  mov     [rbp+57h+var_78], rax
0x18001ff73  lea     rax, [rbp+57h+var_58]
0x18001ff77  mov     [rsp+0E0h+var_90], rax
0x18001ff7c  lea     rax, [rbp+57h+arg_18]
0x18001ff80  mov     [rsp+0E0h+var_98], rax
0x18001ff85  lea     rax, [rbp+57h+var_60]
0x18001ff89  mov     [rsp+0E0h+var_A0], rax
0x18001ff8e  lea     rax, [rbp+57h+var_68]
0x18001ff92  mov     [rsp+0E0h+var_A8], rax
0x18001ff97  lea     rax, [rbp+57h+var_70]
0x18001ff9b  mov     [rsp+0E0h+var_B0], rax
  ... truncated ...
```
