# TileNotification::RecursePayload(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet> &,TileNotification::RecursedPayloadInfo *)

- ea: `0x1801db28c`
- end: `0x1801db726`
- name: `?RecursePayload@TileNotification@@AEAAJAEAV?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@PEAURecursedPayloadInfo@1@@Z`
- size: `1178`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801db28c`
- `0x1801db72c`
- `0x18028e0bc`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x1800c1508`
- `0x1800c18c4`
- `0x1800db6c0`
- `0x180160738`
- `0x180161204`
- `0x1801db28c`
- `0x1801db72c`
- `0x180201e50`
- `0x18028d3ec`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801db475`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801db475`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801db487`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801db4e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801db487`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801db4e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801db45c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801db45c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801db3c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801db421`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801db5d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801db5ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801db68c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801db6c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801db3c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801db421`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801db5d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801db5ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801db68c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801db6c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801db56a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801db56a`

## string_xrefs

- `0x1801db2da`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotification.cpp`
- `0x1801db322`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotification.cpp`
- `0x1801db369`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotification.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall TileNotification::RecursePayload(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  __int64 (__fastcall ***v19)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v20)(_QWORD, GUID *, __int64 *); // rbx
  int v21; // eax
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v23)(_QWORD, GUID *, __int64 *); // rdi
  int v24; // eax
  int v25; // eax
  int v26; // eax
  PCWSTR StringRawBuffer; // rax
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  int v34; // [rsp+20h] [rbp-59h] BYREF
  HSTRING v35; // [rsp+28h] [rbp-51h] BYREF
  HSTRING string1; // [rsp+30h] [rbp-49h] BYREF
  __int64 v37; // [rsp+38h] [rbp-41h] BYREF
  __int64 (__fastcall ***v38)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-39h] BYREF
  __int64 v39; // [rsp+48h] [rbp-31h] BYREF
  __int64 v40; // [rsp+50h] [rbp-29h] BYREF
  __int64 v41; // [rsp+58h] [rbp-21h] BYREF
  INT32 result; // [rsp+60h] [rbp-19h] BYREF
  INT32 v43; // [rsp+64h] [rbp-15h] BYREF
  __int64 v44; // [rsp+68h] [rbp-11h] BYREF
  HSTRING string; // [rsp+70h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v44 = 0;
  v5 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>>(
         a2,
         &v44);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39D,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotification.cpp",
      (const char *)(unsigned int)v5,
      v34);
    goto LABEL_48;
  }
  v37 = 0;
  v7 = v44;
  v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  v9 = v8(v7, &v37);
  v6 = v9;
  if ( v9 < 0 )
  {
    v10 = 928;
    goto LABEL_5;
  }
  LOBYTE(v34) = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v37 + 56LL))(v37, &v34);
  v6 = v9;
  if ( v9 < 0 )
  {
    v10 = 931;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotification.cpp",
      (const char *)(unsigned int)v9,
      v34);
LABEL_6:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    goto LABEL_48;
  }
  while ( (_BYTE)v34 )
  {
    v39 = 0;
    v11 = v37;
    v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    v13 = v12(v11, &v39);
    v6 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A7,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotification.cpp",
        (const char *)(unsigned int)v13,
        v34);
      goto LABEL_46;
    }
    v35 = 0;
    v38 = 0;
    v14 = v39;
    v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 48LL);
    WindowsDeleteString(0);
    v35 = 0;
    v16 = v15(v14, &v35);
    v6 = v16;
    if ( v16 < 0 )
    {
      v32 = 939;
      goto LABEL_43;
    }
    v17 = v39;
    v18 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v39 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    v16 = v18(v17, &v38);
    v6 = v16;
    if ( v16 < 0 )
    {
      v32 = 940;
LABEL_43:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotification.cpp",
        (const char *)(unsigned int)v16,
        v34);
      goto LABEL_44;
    }
    string1 = 0;
    v19 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v38;
    v20 = (*v38)[4];
    WindowsDeleteString(0);
    string1 = 0;
    v21 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), HSTRING *))v20)(v19, &string1);
    v6 = v21;
    if ( v21 < 0 )
    {
      v30 = 943;
LABEL_39:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotification.cpp",
        (const char *)(unsigned int)v21,
        v34);
      goto LABEL_40;
    }
    result = 0;
    if ( WindowsCreateStringReference(L"Windows.Foundation.Collections.ValueSet", 0x27u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    if ( WindowsCompareStringOrdinal(string1, string, &result) < 0 || result )
    {
      v41 = 0;
      v26 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v38, &v41);
      v6 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3C7,
          (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotification.cpp",
          (const char *)(unsigned int)v26,
          v34);
        goto LABEL_37;
      }
      string = 0;
      *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0u;
      StringRawBuffer = WindowsGetStringRawBuffer(v35, 0);
      v28 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              &string,
              StringRawBuffer,
              -1);
      v6 = v28;
      if ( v28 < 0 )
      {
        v31 = 970;
LABEL_35:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotification.cpp",
          (const char *)(unsigned int)v28,
          v34);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
LABEL_37:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
LABEL_40:
        WindowsDeleteString(string1);
        string1 = 0;
LABEL_44:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
        WindowsDeleteString(v35);
        v35 = 0;
LABEL_46:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
        goto LABEL_6;
      }
      v28 = TileNotification::CheckForKnownProperties(v29, (__int64)&string, &v41, a3);
      v6 = v28;
      if ( v28 < 0 )
      {
        v31 = 972;
        goto LABEL_35;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    }
    else
    {
      v40 = 0;
      v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v38;
      v23 = **v38;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      v24 = v23(v22, &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &v40);
      v6 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B6,
          (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotification.cpp",
          (const char *)(unsigned int)v24,
          v34);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
        goto LABEL_40;
      }
      v43 = 0;
      if ( WindowsCompareStringOrdinal(v35, string2, &v43) < 0 || v43 )
      {
        TileNotification::RecursePayload(a1, &v40, a3);
      }
      else
      {
        v25 = TileNotification::RecurseOrderedNodes(a1, (__int64)&v40, a3);
        if ( v25 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x3BC,
            (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotification.cpp",
            (const char *)(unsigned int)v25,
            v34);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    }
    v21 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v37 + 64LL))(v37, &v34);
    v6 = v21;
    if ( v21 < 0 )
    {
      v30 = 975;
      goto LABEL_39;
    }
    WindowsDeleteString(string1);
    string1 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    WindowsDeleteString(v35);
    v35 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  v6 = 0;
LABEL_48:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  return v6;
}

```

## disassembly

```asm
0x1801db28c  push    rbp
0x1801db28e  push    rbx
0x1801db28f  push    rsi
0x1801db290  push    rdi
0x1801db291  push    r12
0x1801db293  push    r14
0x1801db295  push    r15
0x1801db297  lea     rbp, [rsp-27h]
0x1801db29c  sub     rsp, 0A0h
0x1801db2a3  mov     rax, cs:__security_cookie
0x1801db2aa  xor     rax, rsp
0x1801db2ad  mov     [rbp+57h+var_40], rax
0x1801db2b1  mov     r14, r8
0x1801db2b4  mov     rax, rdx
0x1801db2b7  mov     r15, rcx
0x1801db2ba  xor     r12d, r12d
0x1801db2bd  mov     [rbp+57h+var_68], r12
0x1801db2c1  lea     rdx, [rbp+57h+var_68]
0x1801db2c5  mov     rcx, rax
0x1801db2c8  call    ??$As@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>>>)
0x1801db2cd  mov     ebx, eax
0x1801db2cf  test    eax, eax
0x1801db2d1  jns     short loc_1801DB2F0
0x1801db2d3  mov     rcx, [rbp+5Fh]; this
0x1801db2d7  mov     r9d, eax; char *
0x1801db2da  lea     r8, aShellcommonShe_221; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801db2e1  mov     edx, 39Dh; void *
0x1801db2e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801db2eb  jmp     loc_1801DB6FD
0x1801db2f0  mov     [rbp+57h+var_98], r12
0x1801db2f4  mov     rdi, [rbp+57h+var_68]
0x1801db2f8  mov     rax, [rdi]
0x1801db2fb  mov     rbx, [rax+30h]
0x1801db2ff  lea     rcx, [rbp+57h+var_98]
0x1801db303  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801db308  lea     rdx, [rbp+57h+var_98]
0x1801db30c  mov     rcx, rdi
0x1801db30f  mov     rax, rbx
0x1801db312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801db317  mov     ebx, eax
0x1801db319  test    eax, eax
0x1801db31b  jns     short loc_1801DB344
0x1801db31d  mov     edx, 3A0h; void *
0x1801db322  lea     r8, aShellcommonShe_221; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801db329  mov     r9d, eax; char *
0x1801db32c  mov     rcx, [rbp+5Fh]; this
0x1801db330  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801db335  nop
0x1801db336  lea     rcx, [rbp+57h+var_98]
0x1801db33a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801db33f  jmp     loc_1801DB6FD
0x1801db344  mov     byte ptr [rbp+57h+var_B0], r12b
0x1801db348  mov     rcx, [rbp+57h+var_98]
0x1801db34c  mov     rax, [rcx]
0x1801db34f  lea     rdx, [rbp+57h+var_B0]
0x1801db353  mov     rax, [rax+38h]
0x1801db357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801db35c  mov     ebx, eax
0x1801db35e  test    eax, eax
0x1801db360  jns     short loc_1801DB369
0x1801db362  mov     edx, 3A3h
0x1801db367  jmp     short loc_1801DB322
0x1801db369  lea     rsi, aShellcommonShe_221; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801db370  cmp     byte ptr [rbp+57h+var_B0], r12b
0x1801db374  jz      loc_1801DB6F1
0x1801db37a  mov     [rbp+57h+var_88], r12
0x1801db37e  mov     rdi, [rbp+57h+var_98]
0x1801db382  mov     rax, [rdi]
0x1801db385  mov     rbx, [rax+30h]
0x1801db389  lea     rcx, [rbp+57h+var_88]
0x1801db38d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801db392  lea     rdx, [rbp+57h+var_88]
0x1801db396  mov     rcx, rdi
0x1801db399  mov     rax, rbx
0x1801db39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801db3a1  mov     ebx, eax
0x1801db3a3  test    eax, eax
0x1801db3a5  js      loc_1801DB6CE
0x1801db3ab  mov     [rbp+57h+var_A8], r12
0x1801db3af  mov     [rbp+57h+var_90], r12
0x1801db3b3  mov     rdi, [rbp+57h+var_88]
0x1801db3b7  mov     rax, [rdi]
0x1801db3ba  mov     rbx, [rax+30h]
0x1801db3be  xor     ecx, ecx; string
0x1801db3c0  call    cs:__imp_WindowsDeleteString
0x1801db3c6  mov     [rbp+57h+var_A8], r12
0x1801db3ca  lea     rdx, [rbp+57h+var_A8]
0x1801db3ce  mov     rcx, rdi
0x1801db3d1  mov     rax, rbx
0x1801db3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801db3d9  mov     ebx, eax
0x1801db3db  test    eax, eax
0x1801db3dd  js      loc_1801DB69F
0x1801db3e3  mov     rdi, [rbp+57h+var_88]
0x1801db3e7  mov     rax, [rdi]
0x1801db3ea  mov     rbx, [rax+38h]
0x1801db3ee  lea     rcx, [rbp+57h+var_90]
0x1801db3f2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801db3f7  lea     rdx, [rbp+57h+var_90]
0x1801db3fb  mov     rcx, rdi
0x1801db3fe  mov     rax, rbx
0x1801db401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801db406  mov     ebx, eax
0x1801db408  test    eax, eax
0x1801db40a  js      loc_1801DB698
0x1801db410  mov     [rbp+57h+string1], r12
0x1801db414  mov     rdi, [rbp+57h+var_90]
0x1801db418  mov     rax, [rdi]
0x1801db41b  mov     rbx, [rax+20h]
0x1801db41f  xor     ecx, ecx; string
0x1801db421  call    cs:__imp_WindowsDeleteString
0x1801db427  mov     [rbp+57h+string1], r12
0x1801db42b  lea     rdx, [rbp+57h+string1]
0x1801db42f  mov     rcx, rdi
0x1801db432  mov     rax, rbx
0x1801db435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801db43a  mov     ebx, eax
0x1801db43c  test    eax, eax
0x1801db43e  js      loc_1801DB673
0x1801db444  mov     [rbp+57h+result], r12d
0x1801db448  lea     r9, [rbp+57h+string]; string
0x1801db44c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1801db450  mov     edx, 27h ; '''; length
0x1801db455  lea     rcx, aWindowsFoundat_65; "Windows.Foundation.Collections.ValueSet"
0x1801db45c  call    cs:__imp_WindowsCreateStringReference
0x1801db462  test    eax, eax
0x1801db464  jns     short loc_1801DB47B
0x1801db466  xor     r9d, r9d; lpArguments
0x1801db469  xor     r8d, r8d; nNumberOfArguments
0x1801db46c  lea     edx, [r9+1]; dwExceptionFlags
0x1801db470  mov     ecx, 0C000000Dh; dwExceptionCode
0x1801db475  call    cs:__imp_RaiseException
0x1801db47b  lea     r8, [rbp+57h+result]; result
0x1801db47f  mov     rdx, [rbp+57h+string]; string2
0x1801db483  mov     rcx, [rbp+57h+string1]; string1
0x1801db487  call    cs:__imp_WindowsCompareStringOrdinal
0x1801db48d  test    eax, eax
0x1801db48f  js      loc_1801DB53D
0x1801db495  cmp     [rbp+57h+result], r12d
0x1801db499  jnz     loc_1801DB53D
0x1801db49f  mov     [rbp+57h+var_80], r12
0x1801db4a3  mov     rbx, [rbp+57h+var_90]
0x1801db4a7  mov     rax, [rbx]
0x1801db4aa  mov     rdi, [rax]
0x1801db4ad  lea     rcx, [rbp+57h+var_80]
0x1801db4b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801db4b6  lea     r8, [rbp+57h+var_80]
0x1801db4ba  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x1801db4c1  mov     rcx, rbx
0x1801db4c4  mov     rax, rdi
0x1801db4c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801db4cc  mov     ebx, eax
0x1801db4ce  test    eax, eax
0x1801db4d0  js      loc_1801DB605
0x1801db4d6  mov     [rbp+57h+var_6C], r12d
0x1801db4da  lea     r8, [rbp+57h+var_6C]; result
0x1801db4de  mov     rdx, cs:string2; string2
0x1801db4e5  mov     rcx, [rbp+57h+var_A8]; string1
0x1801db4e9  call    cs:__imp_WindowsCompareStringOrdinal
0x1801db4ef  test    eax, eax
0x1801db4f1  js      short loc_1801DB522
0x1801db4f3  cmp     [rbp+57h+var_6C], r12d
0x1801db4f7  jnz     short loc_1801DB522
0x1801db4f9  mov     r8, r14
0x1801db4fc  lea     rdx, [rbp+57h+var_80]
0x1801db500  mov     rcx, r15
0x1801db503  call    ?RecurseOrderedNodes@TileNotification@@AEAAJAEAV?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@PEAURecursedPayloadInfo@1@@Z; TileNotification::RecurseOrderedNodes(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet> &,TileNotification::RecursedPayloadInfo *)
0x1801db508  mov     rcx, [rbp+5Fh]; this
0x1801db50c  test    eax, eax
0x1801db50e  jns     short loc_1801DB532
0x1801db510  mov     r9d, eax; char *
0x1801db513  mov     r8, rsi; unsigned int
0x1801db516  mov     edx, 3BCh; void *
0x1801db51b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801db520  jmp     short loc_1801DB532
0x1801db522  mov     r8, r14
0x1801db525  lea     rdx, [rbp+57h+var_80]
0x1801db529  mov     rcx, r15
0x1801db52c  call    ?RecursePayload@TileNotification@@AEAAJAEAV?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@PEAURecursedPayloadInfo@1@@Z; TileNotification::RecursePayload(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet> &,TileNotification::RecursedPayloadInfo *)
0x1801db531  nop
0x1801db532  lea     rcx, [rbp+57h+var_80]
0x1801db536  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801db53b  jmp     short loc_1801DB5B7
0x1801db53d  mov     [rbp+57h+var_78], r12
0x1801db541  lea     rdx, [rbp+57h+var_78]
0x1801db545  lea     rcx, [rbp+57h+var_90]
0x1801db549  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x1801db54e  mov     ebx, eax
0x1801db550  test    eax, eax
0x1801db552  js      loc_1801DB653
0x1801db558  mov     [rbp+57h+string], r12
0x1801db55c  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r12
0x1801db560  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r12
0x1801db564  xor     edx, edx; length
0x1801db566  mov     rcx, [rbp+57h+var_A8]; string
0x1801db56a  call    cs:__imp_WindowsGetStringRawBuffer
0x1801db570  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801db574  mov     rdx, rax
0x1801db577  lea     rcx, [rbp+57h+string]
0x1801db57b  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1801db580  mov     ebx, eax
0x1801db582  test    eax, eax
0x1801db584  js      loc_1801DB633
0x1801db58a  mov     r9, r14
0x1801db58d  lea     r8, [rbp+57h+var_78]
0x1801db591  lea     rdx, [rbp+57h+string]
0x1801db595  call    ?CheckForKnownProperties@TileNotification@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAV?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@PEAURecursedPayloadInfo@1@@Z; TileNotification::CheckForKnownProperties(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue> &,TileNotification::RecursedPayloadInfo *)
0x1801db59a  mov     ebx, eax
0x1801db59c  test    eax, eax
0x1801db59e  js      loc_1801DB62C
0x1801db5a4  lea     rcx, [rbp+57h+string]
0x1801db5a8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801db5ad  nop
0x1801db5ae  lea     rcx, [rbp+57h+var_78]
0x1801db5b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801db5b7  mov     rcx, [rbp+57h+var_98]
0x1801db5bb  mov     rax, [rcx]
0x1801db5be  lea     rdx, [rbp+57h+var_B0]
0x1801db5c2  mov     rax, [rax+40h]
0x1801db5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801db5cb  mov     ebx, eax
0x1801db5cd  test    eax, eax
0x1801db5cf  js      short loc_1801DB625
0x1801db5d1  mov     rcx, [rbp+57h+string1]; string
0x1801db5d5  call    cs:__imp_WindowsDeleteString
0x1801db5db  mov     [rbp+57h+string1], r12
0x1801db5df  lea     rcx, [rbp+57h+var_90]
0x1801db5e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801db5e8  nop
0x1801db5e9  mov     rcx, [rbp+57h+var_A8]; string
0x1801db5ed  call    cs:__imp_WindowsDeleteString
0x1801db5f3  mov     [rbp+57h+var_A8], r12
0x1801db5f7  lea     rcx, [rbp+57h+var_88]
0x1801db5fb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801db600  jmp     loc_1801DB370
0x1801db605  mov     rcx, [rbp+5Fh]; this
0x1801db609  mov     r9d, eax; char *
0x1801db60c  mov     r8, rsi; unsigned int
0x1801db60f  mov     edx, 3B6h; void *
0x1801db614  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801db619  nop
0x1801db61a  lea     rcx, [rbp+57h+var_80]
0x1801db61e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801db623  jmp     short loc_1801DB688
0x1801db625  mov     edx, 3CFh
0x1801db62a  jmp     short loc_1801DB678
0x1801db62c  mov     edx, 3CCh
0x1801db631  jmp     short loc_1801DB638
0x1801db633  mov     edx, 3CAh; void *
0x1801db638  mov     r8, rsi; unsigned int
0x1801db63b  mov     r9d, eax; char *
0x1801db63e  mov     rcx, [rbp+5Fh]; this
0x1801db642  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801db647  nop
0x1801db648  lea     rcx, [rbp+57h+string]
0x1801db64c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801db651  jmp     short loc_1801DB668
0x1801db653  mov     rcx, [rbp+5Fh]; this
0x1801db657  mov     r9d, eax; char *
0x1801db65a  mov     r8, rsi; unsigned int
0x1801db65d  mov     edx, 3C7h; void *
0x1801db662  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801db667  nop
0x1801db668  lea     rcx, [rbp+57h+var_78]
0x1801db66c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801db671  jmp     short loc_1801DB688
0x1801db673  mov     edx, 3AFh; void *
0x1801db678  mov     r8, rsi; unsigned int
0x1801db67b  mov     r9d, eax; char *
0x1801db67e  mov     rcx, [rbp+5Fh]; this
0x1801db682  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801db687  nop
0x1801db688  mov     rcx, [rbp+57h+string1]; string
0x1801db68c  call    cs:__imp_WindowsDeleteString
0x1801db692  mov     [rbp+57h+string1], r12
0x1801db696  jmp     short loc_1801DB6B4
0x1801db698  mov     edx, 3ACh
0x1801db69d  jmp     short loc_1801DB6A4
0x1801db69f  mov     edx, 3ABh; void *
0x1801db6a4  mov     r8, rsi; unsigned int
0x1801db6a7  mov     r9d, eax; char *
0x1801db6aa  mov     rcx, [rbp+5Fh]; this
0x1801db6ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801db6b3  nop
0x1801db6b4  lea     rcx, [rbp+57h+var_90]
0x1801db6b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801db6bd  nop
0x1801db6be  mov     rcx, [rbp+57h+var_A8]; string
0x1801db6c2  call    cs:__imp_WindowsDeleteString
0x1801db6c8  mov     [rbp+57h+var_A8], r12
0x1801db6cc  jmp     short loc_1801DB6E3
0x1801db6ce  mov     rcx, [rbp+5Fh]; this
0x1801db6d2  mov     r9d, eax; char *
0x1801db6d5  mov     r8, rsi; unsigned int
0x1801db6d8  mov     edx, 3A7h; void *
0x1801db6dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801db6e2  nop
0x1801db6e3  lea     rcx, [rbp+57h+var_88]
0x1801db6e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801db6ec  jmp     loc_1801DB336
  ... truncated ...
```
