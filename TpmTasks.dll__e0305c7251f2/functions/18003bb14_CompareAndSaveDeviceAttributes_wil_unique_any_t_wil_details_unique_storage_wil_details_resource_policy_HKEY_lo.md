# CompareAndSaveDeviceAttributes(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,int *,ushort * *)

- ea: `0x18003bb14`
- end: `0x18003c01f`
- name: `?CompareAndSaveDeviceAttributes@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAHPEAPEAG@Z`
- size: `1291`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003b72c`

## callees

- `0x1800078b0`
- `0x180015198`
- `0x18001a42c`
- `0x18001bddc`
- `0x18003a794`
- `0x18003b9a0`
- `0x18003bb14`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bcbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bcbc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003bccd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003bccd`
- `SHLWAPI!StrCmpIW` at `0x18003be4b`
- `SHLWAPI!StrCmpIW` at `0x18003be63`
- `SHLWAPI!StrCmpIW` at `0x18003be7b`
- `SHLWAPI!StrCmpIW` at `0x18003be4b`
- `SHLWAPI!StrCmpIW` at `0x18003be63`
- `SHLWAPI!StrCmpIW` at `0x18003be7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bc6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003be0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003be96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bf1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bf5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bf6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bfd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bc6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003be0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003be96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bf1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bf5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bf6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bfd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bcf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003be38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bebf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bcf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003be38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bebf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003bcaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003bcaf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003bba2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003bba2`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003bb56`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003bb56`

## string_xrefs

- `0x18003bc14`: `DBUPDATE`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CompareAndSaveDeviceAttributes(__int64 a1, int *a2, unsigned __int16 **a3)
{
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, __int64, __int64, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rdi
  __int64 v12; // rbx
  int v13; // eax
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // r9
  __int64 v18; // rdx
  unsigned __int64 v19; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v21; // rdi
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v24)(_QWORD, GUID *, __int64 *); // rdi
  int v25; // eax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64 *); // rbx
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, __int64 *); // rbx
  int v32; // eax
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, HSTRING *); // rbx
  int v35; // eax
  const WCHAR *v36; // rsi
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, HSTRING *); // rbx
  int v39; // eax
  PCWSTR v40; // rax
  int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // rdx
  int v45; // [rsp+20h] [rbp-89h]
  _BYTE v46[8]; // [rsp+30h] [rbp-79h] BYREF
  HSTRING string; // [rsp+38h] [rbp-71h] BYREF
  __int64 (__fastcall ***v48)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-69h] BYREF
  HSTRING v49; // [rsp+48h] [rbp-61h] BYREF
  __int64 v50; // [rsp+50h] [rbp-59h] BYREF
  __int64 v51; // [rsp+58h] [rbp-51h] BYREF
  __int64 v52; // [rsp+60h] [rbp-49h] BYREF
  HSTRING v53; // [rsp+68h] [rbp-41h] BYREF
  int v54; // [rsp+70h] [rbp-39h] BYREF
  __int64 v55; // [rsp+78h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-29h] BYREF
  __int64 v57; // [rsp+98h] [rbp-11h]
  HSTRING_HEADER v58; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v59; // [rsp+B8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v55 = 0;
  *a2 = 1;
  ActivationFactory = RoInitialize(1);
  v7 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v57 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.Flighting.ClientAttributes",
      0x2Cu,
      0x2Bu);
    v9 = v57;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
    ActivationFactory = RoGetActivationFactory(v9, &GUID_41845433_1668_4264_8a63_315eb82ab0d6, &v55);
    v7 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v8 = 186;
      goto LABEL_5;
    }
    v48 = 0;
    v10 = v55;
    v11 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)v55 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
    v57 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"1.0", 4u, 3u);
    v12 = v57;
    v59 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v58, L"DBUPDATE", 9u, 8u);
    v13 = v11(v10, v59, v12, (__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v48);
    v7 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC6,
        (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsattributes.cpp",
        (const char *)(unsigned int)v13,
        v45);
LABEL_47:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
      goto LABEL_48;
    }
    string = 0;
    v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v48;
    v15 = (*v48)[6];
    WindowsDeleteString(0);
    string = 0;
    v16 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), HSTRING *))v15)(v14, &string);
    v7 = v16;
    if ( v16 >= 0 )
    {
      v19 = 2 * WindowsGetStringLen(string) + 2;
      ProcessHeap = GetProcessHeap();
      v21 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, (unsigned int)v19);
      if ( v21 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        StringCchCopyW(v21, v19 >> 1, StringRawBuffer);
        *a3 = v21;
        v51 = 0;
        v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v48;
        v24 = **v48;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
        v25 = v24(v23, &GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b, &v51);
        v7 = v25;
        if ( v25 >= 0 )
        {
          v50 = 0;
          v26 = v51;
          v27 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 48LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
          v28 = v27(v26, &v50);
          v7 = v28;
          if ( v28 >= 0 )
          {
            v46[0] = 0;
            v28 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v50 + 56LL))(v50, v46);
            v7 = v28;
            if ( v28 >= 0 )
            {
              while ( 1 )
              {
                if ( !v46[0] )
                  goto LABEL_44;
                v52 = 0;
                v30 = v50;
                v31 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 48LL);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
                v32 = v31(v30, &v52);
                v7 = v32;
                if ( v32 < 0 )
                  break;
                v49 = 0;
                v33 = v52;
                v34 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v52 + 48LL);
                WindowsDeleteString(0);
                v49 = 0;
                v35 = v34(v33, &v49);
                v7 = v35;
                if ( v35 < 0 )
                {
                  v43 = 237;
LABEL_40:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v43,
                    (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsattributes.cpp",
                    (const char *)(unsigned int)v35,
                    v45);
                  goto LABEL_37;
                }
                v36 = WindowsGetStringRawBuffer(v49, 0);
                if ( StrCmpIW(v36, L"App") && StrCmpIW(v36, L"AppVer") && StrCmpIW(v36, L"AttrDataVer") )
                {
                  v53 = 0;
                  v37 = v52;
                  v38 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v52 + 56LL);
                  WindowsDeleteString(0);
                  v53 = 0;
                  v39 = v38(v37, &v53);
                  v7 = v39;
                  if ( v39 < 0 )
                  {
                    v42 = 251;
LABEL_36:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v42,
                      (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsattributes.cpp",
                      (const char *)(unsigned int)v39,
                      v45);
                    WindowsDeleteString(v53);
                    v53 = 0;
LABEL_37:
                    WindowsDeleteString(v49);
                    v49 = 0;
LABEL_43:
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
                    goto LABEL_44;
                  }
                  v40 = WindowsGetStringRawBuffer(v53, 0);
                  v54 = 1;
                  v39 = CompareAndSaveAttributeValue(a1, v36, v40, &v54);
                  v7 = v39;
                  if ( v39 < 0 )
                  {
                    v42 = 260;
                    goto LABEL_36;
                  }
                  if ( v54 )
                    v41 = *a2;
                  else
                    v41 = 0;
                  *a2 = v41;
                  WindowsDeleteString(v53);
                }
                v35 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v50 + 64LL))(v50, v46);
                v7 = v35;
                if ( v35 < 0 )
                {
                  v43 = 265;
                  goto LABEL_40;
                }
                WindowsDeleteString(v49);
                v49 = 0;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xE9,
                (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsattributes.cpp",
                (const char *)(unsigned int)v32,
                v45);
              goto LABEL_43;
            }
            v29 = 227;
          }
          else
          {
            v29 = 223;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v29,
            (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsattributes.cpp",
            (const char *)(unsigned int)v28,
            v45);
LABEL_44:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xDB,
            (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsattributes.cpp",
            (const char *)(unsigned int)v25,
            v45);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
        goto LABEL_46;
      }
      v7 = -2147024882;
      v17 = 2147942414LL;
      v18 = 213;
    }
    else
    {
      v17 = (unsigned int)v16;
      v18 = 208;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsattributes.cpp",
      (const char *)v17,
      v45);
LABEL_46:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_47;
  }
  v8 = 183;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsattributes.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v45);
LABEL_48:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  return v7;
}

```

## disassembly

```asm
0x18003bb14  mov     [rsp-8+arg_18], rbx
0x18003bb19  push    rbp
0x18003bb1a  push    rsi
0x18003bb1b  push    rdi
0x18003bb1c  push    r12
0x18003bb1e  push    r13
0x18003bb20  push    r14
0x18003bb22  push    r15
0x18003bb24  lea     rbp, [rsp-27h]
0x18003bb29  sub     rsp, 0D0h
0x18003bb30  mov     rax, cs:__security_cookie
0x18003bb37  xor     rax, rsp
0x18003bb3a  mov     [rbp+57h+var_40], rax
0x18003bb3e  mov     r15, r8
0x18003bb41  mov     r14, rdx
0x18003bb44  mov     r12, rcx
0x18003bb47  xor     r13d, r13d
0x18003bb4a  mov     [rbp+57h+var_88], r13
0x18003bb4e  lea     eax, [r13+1]
0x18003bb52  mov     [rdx], eax
0x18003bb54  mov     ecx, eax
0x18003bb56  call    cs:__imp_RoInitialize
0x18003bb5c  mov     ebx, eax
0x18003bb5e  test    eax, eax
0x18003bb60  jns     short loc_18003BB69
0x18003bb62  mov     edx, 0B7h
0x18003bb67  jmp     short loc_18003BBB3
0x18003bb69  mov     [rbp+57h+var_68], r13
0x18003bb6d  mov     r9d, 2Bh ; '+'; unsigned int
0x18003bb73  lea     r8d, [r9+1]; unsigned int
0x18003bb77  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_ClientAttributes@@3QBGB; "Windows.Internal.Flighting.ClientAttrib"...
0x18003bb7e  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18003bb82  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003bb87  mov     rbx, [rbp+57h+var_68]
0x18003bb8b  lea     rcx, [rbp+57h+var_88]
0x18003bb8f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003bb94  lea     r8, [rbp+57h+var_88]
0x18003bb98  lea     rdx, _GUID_41845433_1668_4264_8a63_315eb82ab0d6
0x18003bb9f  mov     rcx, rbx
0x18003bba2  call    cs:__imp_RoGetActivationFactory
0x18003bba8  mov     ebx, eax
0x18003bbaa  test    eax, eax
0x18003bbac  jns     short loc_18003BBCB
0x18003bbae  mov     edx, 0BAh; void *
0x18003bbb3  lea     r8, aOnecoreBaseSec_5; "onecore\\base\\secureboot\\servicing\\l"...
0x18003bbba  mov     r9d, eax; char *
0x18003bbbd  mov     rcx, [rbp+5Fh]; this
0x18003bbc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bbc6  jmp     loc_18003BFED
0x18003bbcb  mov     [rbp+57h+var_C0], r13
0x18003bbcf  mov     rsi, [rbp+57h+var_88]
0x18003bbd3  mov     rax, [rsi]
0x18003bbd6  mov     rdi, [rax+30h]
0x18003bbda  lea     rcx, [rbp+57h+var_C0]
0x18003bbde  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003bbe3  mov     [rbp+57h+var_68], r13
0x18003bbe7  mov     r9d, 3; unsigned int
0x18003bbed  lea     r8d, [r9+1]; unsigned int
0x18003bbf1  lea     rdx, a10; "1.0"
0x18003bbf8  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18003bbfc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003bc01  nop
0x18003bc02  mov     rbx, [rbp+57h+var_68]
0x18003bc06  mov     [rbp+57h+var_48], r13
0x18003bc0a  mov     r9d, 8; unsigned int
0x18003bc10  lea     r8d, [r9+1]; unsigned int
0x18003bc14  lea     rdx, aDbupdate; "DBUPDATE"
0x18003bc1b  lea     rcx, [rbp+57h+var_60]; hstringHeader
0x18003bc1f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003bc24  nop
0x18003bc25  lea     r9, [rbp+57h+var_C0]
0x18003bc29  mov     r8, rbx
0x18003bc2c  mov     rdx, [rbp+57h+var_48]
0x18003bc30  mov     rcx, rsi
0x18003bc33  mov     rax, rdi
0x18003bc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc3b  mov     ebx, eax
0x18003bc3d  test    eax, eax
0x18003bc3f  jns     short loc_18003BC5E
0x18003bc41  mov     rcx, [rbp+5Fh]; this
0x18003bc45  mov     r9d, eax; char *
0x18003bc48  lea     r8, aOnecoreBaseSec_5; "onecore\\base\\secureboot\\servicing\\l"...
0x18003bc4f  mov     edx, 0C6h; void *
0x18003bc54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bc59  jmp     loc_18003BFE3
0x18003bc5e  mov     [rbp+57h+string], r13
0x18003bc62  mov     rdi, [rbp+57h+var_C0]
0x18003bc66  mov     rax, [rdi]
0x18003bc69  mov     rbx, [rax+30h]
0x18003bc6d  xor     ecx, ecx; string
0x18003bc6f  call    cs:__imp_WindowsDeleteString
0x18003bc75  mov     [rbp+57h+string], r13
0x18003bc79  lea     rdx, [rbp+57h+string]
0x18003bc7d  mov     rcx, rdi
0x18003bc80  mov     rax, rbx
0x18003bc83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc88  mov     ebx, eax
0x18003bc8a  test    eax, eax
0x18003bc8c  jns     short loc_18003BCAB
0x18003bc8e  mov     r9d, eax; char *
0x18003bc91  mov     edx, 0D0h; void *
0x18003bc96  lea     r8, aOnecoreBaseSec_5; "onecore\\base\\secureboot\\servicing\\l"...
0x18003bc9d  mov     rcx, [rbp+5Fh]; this
0x18003bca1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bca6  jmp     loc_18003BFD5
0x18003bcab  mov     rcx, [rbp+57h+string]; string
0x18003bcaf  call    cs:__imp_WindowsGetStringLen
0x18003bcb5  lea     ebx, ds:2[rax*2]
0x18003bcbc  call    cs:__imp_GetProcessHeap
0x18003bcc2  mov     rcx, rax; hHeap
0x18003bcc5  mov     r8d, ebx; dwBytes
0x18003bcc8  mov     edx, 8; dwFlags
0x18003bccd  call    cs:__imp_HeapAlloc
0x18003bcd3  mov     rdi, rax
0x18003bcd6  test    rax, rax
0x18003bcd9  jnz     short loc_18003BCEA
0x18003bcdb  mov     ebx, 8007000Eh
0x18003bce0  mov     r9d, ebx
0x18003bce3  mov     edx, 0D5h
0x18003bce8  jmp     short loc_18003BC96
0x18003bcea  xor     edx, edx; length
0x18003bcec  mov     rcx, [rbp+57h+string]; string
0x18003bcf0  call    cs:__imp_WindowsGetStringRawBuffer
0x18003bcf6  shr     rbx, 1
0x18003bcf9  mov     r8, rax; unsigned __int16 *
0x18003bcfc  mov     rdx, rbx; unsigned __int64
0x18003bcff  mov     rcx, rdi; unsigned __int16 *
0x18003bd02  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003bd07  mov     [r15], rdi
0x18003bd0a  mov     [rbp+57h+var_A8], r13
0x18003bd0e  mov     rbx, [rbp+57h+var_C0]
0x18003bd12  mov     rax, [rbx]
0x18003bd15  mov     rdi, [rax]
0x18003bd18  lea     rcx, [rbp+57h+var_A8]
0x18003bd1c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003bd21  lea     r8, [rbp+57h+var_A8]
0x18003bd25  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x18003bd2c  mov     rcx, rbx
0x18003bd2f  mov     rax, rdi
0x18003bd32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd37  mov     ebx, eax
0x18003bd39  test    eax, eax
0x18003bd3b  jns     short loc_18003BD5A
0x18003bd3d  mov     rcx, [rbp+5Fh]; this
0x18003bd41  mov     r9d, eax; char *
0x18003bd44  lea     r8, aOnecoreBaseSec_5; "onecore\\base\\secureboot\\servicing\\l"...
0x18003bd4b  mov     edx, 0DBh; void *
0x18003bd50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bd55  jmp     loc_18003BFCB
0x18003bd5a  mov     [rbp+57h+var_B0], r13
0x18003bd5e  mov     rdi, [rbp+57h+var_A8]
0x18003bd62  mov     rax, [rdi]
0x18003bd65  mov     rbx, [rax+30h]
0x18003bd69  lea     rcx, [rbp+57h+var_B0]
0x18003bd6d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003bd72  lea     rdx, [rbp+57h+var_B0]
0x18003bd76  mov     rcx, rdi
0x18003bd79  mov     rax, rbx
0x18003bd7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd81  mov     ebx, eax
0x18003bd83  test    eax, eax
0x18003bd85  jns     short loc_18003BDA4
0x18003bd87  mov     edx, 0DFh; void *
0x18003bd8c  lea     r8, aOnecoreBaseSec_5; "onecore\\base\\secureboot\\servicing\\l"...
0x18003bd93  mov     r9d, eax; char *
0x18003bd96  mov     rcx, [rbp+5Fh]; this
0x18003bd9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bd9f  jmp     loc_18003BFC1
0x18003bda4  mov     [rbp+57h+var_D0], r13b
0x18003bda8  mov     rcx, [rbp+57h+var_B0]
0x18003bdac  mov     rax, [rcx]
0x18003bdaf  lea     rdx, [rbp+57h+var_D0]
0x18003bdb3  mov     rax, [rax+38h]
0x18003bdb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdbc  mov     ebx, eax
0x18003bdbe  test    eax, eax
0x18003bdc0  jns     loc_18003BF30
0x18003bdc6  mov     edx, 0E3h
0x18003bdcb  jmp     short loc_18003BD8C
0x18003bdcd  mov     [rbp+57h+var_A0], r13
0x18003bdd1  mov     rdi, [rbp+57h+var_B0]
0x18003bdd5  mov     rax, [rdi]
0x18003bdd8  mov     rbx, [rax+30h]
0x18003bddc  lea     rcx, [rbp+57h+var_A0]
0x18003bde0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003bde5  lea     rdx, [rbp+57h+var_A0]
0x18003bde9  mov     rcx, rdi
0x18003bdec  mov     rax, rbx
0x18003bdef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdf4  mov     ebx, eax
0x18003bdf6  test    eax, eax
0x18003bdf8  js      loc_18003BF9E
0x18003bdfe  mov     [rbp+57h+var_B8], r13
0x18003be02  mov     rdi, [rbp+57h+var_A0]
0x18003be06  mov     rax, [rdi]
0x18003be09  mov     rbx, [rax+30h]
0x18003be0d  xor     ecx, ecx; string
0x18003be0f  call    cs:__imp_WindowsDeleteString
0x18003be15  mov     [rbp+57h+var_B8], r13
0x18003be19  lea     rdx, [rbp+57h+var_B8]
0x18003be1d  mov     rcx, rdi
0x18003be20  mov     rax, rbx
0x18003be23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be28  mov     ebx, eax
0x18003be2a  test    eax, eax
0x18003be2c  js      loc_18003BF97
0x18003be32  xor     edx, edx; length
0x18003be34  mov     rcx, [rbp+57h+var_B8]; string
0x18003be38  call    cs:__imp_WindowsGetStringRawBuffer
0x18003be3e  mov     rsi, rax
0x18003be41  lea     rdx, psz2; "App"
0x18003be48  mov     rcx, rax; psz1
0x18003be4b  call    cs:__imp_StrCmpIW
0x18003be51  test    eax, eax
0x18003be53  jz      loc_18003BEFF
0x18003be59  lea     rdx, aAppver; "AppVer"
0x18003be60  mov     rcx, rsi; psz1
0x18003be63  call    cs:__imp_StrCmpIW
0x18003be69  test    eax, eax
0x18003be6b  jz      loc_18003BEFF
0x18003be71  lea     rdx, aAttrdataver; "AttrDataVer"
0x18003be78  mov     rcx, rsi; psz1
0x18003be7b  call    cs:__imp_StrCmpIW
0x18003be81  test    eax, eax
0x18003be83  jz      short loc_18003BEFF
0x18003be85  mov     [rbp+57h+var_98], r13
0x18003be89  mov     rdi, [rbp+57h+var_A0]
0x18003be8d  mov     rax, [rdi]
0x18003be90  mov     rbx, [rax+38h]
0x18003be94  xor     ecx, ecx; string
0x18003be96  call    cs:__imp_WindowsDeleteString
0x18003be9c  mov     [rbp+57h+var_98], r13
0x18003bea0  lea     rdx, [rbp+57h+var_98]
0x18003bea4  mov     rcx, rdi
0x18003bea7  mov     rax, rbx
0x18003beaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003beaf  mov     ebx, eax
0x18003beb1  test    eax, eax
0x18003beb3  js      loc_18003BF76
0x18003beb9  xor     edx, edx; length
0x18003bebb  mov     rcx, [rbp+57h+var_98]; string
0x18003bebf  call    cs:__imp_WindowsGetStringRawBuffer
0x18003bec5  mov     [rbp+57h+var_90], 1
0x18003becc  lea     r9, [rbp+57h+var_90]
0x18003bed0  mov     r8, rax
0x18003bed3  mov     rdx, rsi
0x18003bed6  mov     rcx, r12
0x18003bed9  call    ?CompareAndSaveAttributeValue@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG1PEAH@Z; CompareAndSaveAttributeValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *,ushort const *,int *)
0x18003bede  mov     ebx, eax
0x18003bee0  test    eax, eax
0x18003bee2  js      short loc_18003BF3F
0x18003bee4  cmp     [rbp+57h+var_90], r13d
0x18003bee8  jz      short loc_18003BEEF
0x18003beea  mov     eax, [r14]
0x18003beed  jmp     short loc_18003BEF2
0x18003beef  mov     eax, r13d
0x18003bef2  mov     [r14], eax
0x18003bef5  mov     rcx, [rbp+57h+var_98]; string
0x18003bef9  call    cs:__imp_WindowsDeleteString
0x18003beff  mov     rcx, [rbp+57h+var_B0]
0x18003bf03  mov     rax, [rcx]
0x18003bf06  lea     rdx, [rbp+57h+var_D0]
0x18003bf0a  mov     rax, [rax+40h]
0x18003bf0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf13  mov     ebx, eax
0x18003bf15  test    eax, eax
0x18003bf17  js      short loc_18003BF7D
0x18003bf19  mov     rcx, [rbp+57h+var_B8]; string
0x18003bf1d  call    cs:__imp_WindowsDeleteString
0x18003bf23  mov     [rbp+57h+var_B8], r13
0x18003bf27  lea     rcx, [rbp+57h+var_A0]
0x18003bf2b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003bf30  cmp     [rbp+57h+var_D0], r13b
0x18003bf34  jnz     loc_18003BDCD
0x18003bf3a  jmp     loc_18003BFC1
0x18003bf3f  mov     edx, 104h; void *
0x18003bf44  lea     r8, aOnecoreBaseSec_5; "onecore\\base\\secureboot\\servicing\\l"...
0x18003bf4b  mov     r9d, eax; char *
0x18003bf4e  mov     rcx, [rbp+5Fh]; this
0x18003bf52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bf57  nop
0x18003bf58  mov     rcx, [rbp+57h+var_98]; string
0x18003bf5c  call    cs:__imp_WindowsDeleteString
0x18003bf62  mov     [rbp+57h+var_98], r13
0x18003bf66  mov     rcx, [rbp+57h+var_B8]; string
0x18003bf6a  call    cs:__imp_WindowsDeleteString
0x18003bf70  mov     [rbp+57h+var_B8], r13
0x18003bf74  jmp     short loc_18003BFB7
0x18003bf76  mov     edx, 0FBh
0x18003bf7b  jmp     short loc_18003BF44
0x18003bf7d  mov     edx, 109h; void *
0x18003bf82  lea     r8, aOnecoreBaseSec_5; "onecore\\base\\secureboot\\servicing\\l"...
0x18003bf89  mov     r9d, eax; char *
0x18003bf8c  mov     rcx, [rbp+5Fh]; this
0x18003bf90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bf95  jmp     short loc_18003BF66
0x18003bf97  mov     edx, 0EDh
0x18003bf9c  jmp     short loc_18003BF82
0x18003bf9e  mov     rcx, [rbp+5Fh]; this
0x18003bfa2  mov     r9d, eax; char *
  ... truncated ...
```
