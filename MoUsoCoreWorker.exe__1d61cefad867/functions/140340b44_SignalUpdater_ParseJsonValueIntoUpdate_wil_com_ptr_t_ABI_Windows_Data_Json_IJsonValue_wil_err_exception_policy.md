# SignalUpdater::ParseJsonValueIntoUpdate(wil::com_ptr_t<ABI::Windows::Data::Json::IJsonValue,wil::err_exception_policy> const &,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,UpdateDatabase &)

- ea: `0x140340b44`
- end: `0x14034115c`
- name: `?ParseJsonValueIntoUpdate@SignalUpdater@@CA?AV?$shared_ptr@VUpdate@@@std@@AEBV?$com_ptr_t@UIJsonValue@Json@Data@Windows@ABI@@Uerr_exception_policy@wil@@@wil@@V?$basic_zstring_view@_W@5@1AEAVUpdateDatabase@@@Z`
- size: `1560`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140340750`
- `0x140341164`

## callees

- `0x1400413a8`
- `0x140041a84`
- `0x140043354`
- `0x140045404`
- `0x1402c2b9c`
- `0x140340b44`
- `0x140341ff8`
- `0x14034234c`
- `0x140379070`
- `0x1403790d8`
- `0x14037b4b0`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140340e08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140340e45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140340e55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140340e65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140340f71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140340e08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140340e45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140340e55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140340e65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140340f71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140340be9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140340d1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140340d6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140340dc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140340edc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140340eea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140340ef8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140340f48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14034104e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140340be9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140340d1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140340d6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140340dc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140340edc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140340eea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140340ef8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140340f48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14034104e`

## string_xrefs

- `0x140341094`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x1403410a9`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x1403410e1`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x1403410f6`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x14034110b`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x140341120`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x140341135`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x14034114a`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\SignalUpdater.cpp`
- `0x1403410bb`: `JSON payload improperly formatted`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
WCHAR *__fastcall SignalUpdater::ParseJsonValueIntoUpdate(
        WCHAR *a1,
        __int64 **a2,
        __int128 *a3,
        __int128 *a4,
        __int64 a5)
{
  int v9; // eax
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, _QWORD, HSTRING *); // rdi
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rdi
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, _QWORD, __int64 *); // rdi
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rbx
  int (__fastcall *v26)(__int64, _QWORD, __int64 *); // rdi
  __int64 v27; // rax
  __int64 v28; // rbx
  __int64 (__fastcall *v29)(__int64, _QWORD, HSTRING *); // rdi
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rbx
  __int64 (__fastcall *v33)(__int64, _QWORD, HSTRING *); // rdi
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rbx
  __int64 (__fastcall *v37)(__int64, _QWORD, HSTRING *); // rdi
  __int64 v38; // rax
  int v39; // eax
  PCWSTR v40; // rax
  __int64 v41; // rdi
  __int64 v42; // rax
  __int64 v43; // rdx
  void (*v44)(void); // rax
  _QWORD *updated; // rax
  volatile signed __int32 *v46; // rbx
  int v48; // [rsp+20h] [rbp-E0h]
  PCWSTR StringRawBuffer; // [rsp+58h] [rbp-A8h] BYREF
  PCWSTR pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  volatile signed __int32 *pExceptionObject_8; // [rsp+68h] [rbp-98h]
  _BYTE v52[40]; // [rsp+80h] [rbp-80h] BYREF
  PCWSTR v53; // [rsp+A8h] [rbp-58h] BYREF
  PCWSTR v54; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v55; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v56; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v57; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v58; // [rsp+D0h] [rbp-30h] BYREF
  int v59; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING v60; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING string; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING v62; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v63; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  StringRawBuffer = a1;
  v59 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, int *))(**a2 + 48))(*a2, &v59);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
      (const char *)(unsigned int)v9,
      v48);
  if ( v59 != 5 )
  {
    std::invalid_argument::invalid_argument(
      (std::invalid_argument *)&pExceptionObject,
      "JSON payload improperly formatted");
    throw (std::invalid_argument *)&pExceptionObject;
  }
  v56 = 0;
  v10 = *a2;
  v11 = **a2;
  v56 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v11 + 96))(v10, &v56);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
      (const char *)(unsigned int)v12,
      v48);
  v55 = 0;
  v13 = v56;
  v14 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v56 + 80LL);
  WindowsDeleteString(0);
  v55 = 0;
  v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v52, &SignalState::sc_signalCollectIdKey);
  v16 = v14(v13, *(_QWORD *)(v15 + 24), &v55);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x94,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
      (const char *)(unsigned int)v16,
      v48);
  v63 = 0;
  v17 = v56;
  v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v56 + 64LL);
  v63 = 0;
  v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v52, &SignalState::sc_signalsKey);
  v20 = v18(v17, *(_QWORD *)(v19 + 24), &v63);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
      (const char *)(unsigned int)v20,
      v48);
  v58 = 0;
  v21 = v56;
  v22 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v56 + 48LL);
  v58 = 0;
  v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v52, &SignalState::sc_signalsKey);
  v24 = v22(v21, *(_QWORD *)(v23 + 24), &v58);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
      (const char *)(unsigned int)v24,
      v48);
  v57 = 0;
  v25 = v56;
  v26 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v56 + 64LL);
  v57 = 0;
  v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v52, &SignalState::sc_modelCabKey);
  if ( v26(v25, *(_QWORD *)(v27 + 24), &v57) < 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v55, 0);
    updated = (_QWORD *)std::make_shared<SignalUpdate,wchar_t const *,wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,wil::com_ptr_t<ABI::Windows::Data::Json::IJsonValue,wil::err_exception_policy> const &,wil::com_ptr_t<ABI::Windows::Data::Json::IJsonValue,wil::err_exception_policy> &,UpdateDatabase &>(
                          (unsigned int)&pExceptionObject,
                          (unsigned int)&StringRawBuffer,
                          (_DWORD)a4,
                          (_DWORD)a3,
                          (__int64)a2,
                          (__int64)&v58,
                          a5);
    *(_QWORD *)a1 = 0;
    *((_QWORD *)a1 + 1) = 0;
    *(_QWORD *)a1 = *updated;
    *((_QWORD *)a1 + 1) = updated[1];
    *updated = 0;
    updated[1] = 0;
    v46 = pExceptionObject_8;
    if ( pExceptionObject_8 )
    {
      if ( _InterlockedExchangeAdd(pExceptionObject_8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
        if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
      }
    }
    if ( v57 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    if ( v58 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    if ( v63 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    WindowsDeleteString(v55);
    v55 = 0;
    if ( v56 )
    {
      v44 = *(void (**)(void))(*(_QWORD *)v56 + 16LL);
      goto LABEL_33;
    }
  }
  else
  {
    v62 = 0;
    v28 = v57;
    v29 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v57 + 80LL);
    WindowsDeleteString(0);
    v62 = 0;
    v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v52, &SignalState::sc_modelIdKey);
    v31 = v29(v28, *(_QWORD *)(v30 + 24), &v62);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
        (const char *)(unsigned int)v31,
        v48);
    string = 0;
    v32 = v57;
    v33 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v57 + 80LL);
    WindowsDeleteString(0);
    string = 0;
    v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v52, &SignalState::sc_modelFileNameKey);
    v35 = v33(v32, *(_QWORD *)(v34 + 24), &string);
    if ( v35 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
        (const char *)(unsigned int)v35,
        v48);
    v60 = 0;
    v36 = v57;
    v37 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v57 + 80LL);
    WindowsDeleteString(0);
    v60 = 0;
    v38 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v52, &SignalState::sc_modelFileUrlKey);
    v39 = v37(v36, *(_QWORD *)(v38 + 24), &v60);
    if ( v39 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\SignalUpdater.cpp",
        (const char *)(unsigned int)v39,
        v48);
    v40 = WindowsGetStringRawBuffer(string, 0);
    pExceptionObject = v40;
    v41 = -1;
    do
      ++v41;
    while ( v40[v41] );
    pExceptionObject_8 = (volatile signed __int32 *)v41;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v52, &pExceptionObject);
    v53 = WindowsGetStringRawBuffer(v60, 0);
    v54 = WindowsGetStringRawBuffer(v62, 0);
    StringRawBuffer = WindowsGetStringRawBuffer(v55, 0);
    pExceptionObject = (PCWSTR)operator new(0x218u);
    v42 = std::_Ref_count_obj2<ModelUpdate>::_Ref_count_obj2<ModelUpdate>(
            (__int64)pExceptionObject,
            (__int64 *)&StringRawBuffer,
            a4,
            a3,
            (__int64)a2,
            (__int64)&v58,
            (__int64 *)&v54,
            (__int64 *)&v53,
            (__int64)v52,
            a5);
    *(_QWORD *)a1 = v42 + 16;
    *((_QWORD *)a1 + 1) = v42;
    std::wstring::~wstring(v52, v43);
    WindowsDeleteString(v60);
    v60 = 0;
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v62);
    v62 = 0;
    if ( v57 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    if ( v58 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    if ( v63 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    WindowsDeleteString(v55);
    v55 = 0;
    if ( v56 )
    {
      v44 = *(void (**)(void))(*(_QWORD *)v56 + 16LL);
LABEL_33:
      v44();
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140340b44  push    rbp
0x140340b46  push    rbx
0x140340b47  push    rsi
0x140340b48  push    rdi
0x140340b49  push    r12
0x140340b4b  push    r13
0x140340b4d  push    r14
0x140340b4f  push    r15
0x140340b51  lea     rbp, [rsp-18h]
0x140340b56  sub     rsp, 118h
0x140340b5d  mov     rax, cs:__security_cookie
0x140340b64  xor     rax, rsp
0x140340b67  mov     [rbp+50h+var_50], rax
0x140340b6b  mov     r12, r9
0x140340b6e  mov     r15, r8
0x140340b71  mov     r14, rdx
0x140340b74  mov     rsi, rcx
0x140340b77  mov     [rsp+150h+var_F8], rcx
0x140340b7c  mov     r13, [rbp+50h+arg_20]
0x140340b83  xor     ebx, ebx
0x140340b85  mov     [rbp+50h+var_78], ebx
0x140340b88  mov     rcx, [rdx]
0x140340b8b  mov     rax, [rcx]
0x140340b8e  lea     rdx, [rbp+50h+var_78]
0x140340b92  mov     rax, [rax+30h]
0x140340b96  call    _guard_dispatch_icall
0x140340b9b  mov     rcx, [rbp+58h]; this
0x140340b9f  test    eax, eax
0x140340ba1  js      loc_1403410A6
0x140340ba7  cmp     [rbp+50h+var_78], 5
0x140340bab  jnz     loc_1403410BB
0x140340bb1  mov     [rbp+50h+var_90], rbx
0x140340bb5  mov     rcx, [r14]
0x140340bb8  mov     rax, [rcx]
0x140340bbb  mov     [rbp+50h+var_90], rbx
0x140340bbf  lea     rdx, [rbp+50h+var_90]
0x140340bc3  mov     rax, [rax+60h]
0x140340bc7  call    _guard_dispatch_icall
0x140340bcc  mov     rcx, [rbp+58h]; this
0x140340bd0  test    eax, eax
0x140340bd2  js      loc_1403410DE
0x140340bd8  mov     [rbp+50h+var_98], rbx
0x140340bdc  mov     rbx, [rbp+50h+var_90]
0x140340be0  mov     rax, [rbx]
0x140340be3  mov     rdi, [rax+50h]
0x140340be7  xor     ecx, ecx; string
0x140340be9  call    cs:__imp_WindowsDeleteString
0x140340bef  mov     [rbp+50h+var_98], 0
0x140340bf7  lea     rdx, ?sc_signalCollectIdKey@SignalState@@2QEB_WEB; wchar_t const * const SignalState::sc_signalCollectIdKey
0x140340bfe  lea     rcx, [rbp+50h+var_D0]
0x140340c02  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x140340c07  nop
0x140340c08  lea     r8, [rbp+50h+var_98]
0x140340c0c  mov     rdx, [rax+18h]
0x140340c10  mov     rcx, rbx
0x140340c13  mov     rax, rdi
0x140340c16  call    _guard_dispatch_icall
0x140340c1b  mov     rcx, [rbp+58h]; this
0x140340c1f  test    eax, eax
0x140340c21  js      loc_1403410F3
0x140340c27  mov     [rbp+50h+var_58], 0
0x140340c2f  mov     rbx, [rbp+50h+var_90]
0x140340c33  mov     rax, [rbx]
0x140340c36  mov     rdi, [rax+40h]
0x140340c3a  mov     [rbp+50h+var_58], 0
0x140340c42  lea     rdx, ?sc_signalsKey@SignalState@@2QEB_WEB; wchar_t const * const SignalState::sc_signalsKey
0x140340c49  lea     rcx, [rbp+50h+var_D0]
0x140340c4d  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x140340c52  nop
0x140340c53  lea     r8, [rbp+50h+var_58]
0x140340c57  mov     rdx, [rax+18h]
0x140340c5b  mov     rcx, rbx
0x140340c5e  mov     rax, rdi
0x140340c61  call    _guard_dispatch_icall
0x140340c66  mov     rcx, [rbp+58h]; this
0x140340c6a  test    eax, eax
0x140340c6c  js      loc_140341108
0x140340c72  mov     [rbp+50h+var_80], 0
0x140340c7a  mov     rbx, [rbp+50h+var_90]
0x140340c7e  mov     rax, [rbx]
0x140340c81  mov     rdi, [rax+30h]
0x140340c85  mov     [rbp+50h+var_80], 0
0x140340c8d  lea     rdx, ?sc_signalsKey@SignalState@@2QEB_WEB; wchar_t const * const SignalState::sc_signalsKey
0x140340c94  lea     rcx, [rbp+50h+var_D0]
0x140340c98  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x140340c9d  nop
0x140340c9e  lea     r8, [rbp+50h+var_80]
0x140340ca2  mov     rdx, [rax+18h]
0x140340ca6  mov     rcx, rbx
0x140340ca9  mov     rax, rdi
0x140340cac  call    _guard_dispatch_icall
0x140340cb1  mov     rcx, [rbp+58h]; this
0x140340cb5  test    eax, eax
0x140340cb7  js      loc_14034111D
0x140340cbd  mov     [rbp+50h+var_88], 0
0x140340cc5  mov     rbx, [rbp+50h+var_90]
0x140340cc9  mov     rax, [rbx]
0x140340ccc  mov     rdi, [rax+40h]
0x140340cd0  mov     [rbp+50h+var_88], 0
0x140340cd8  lea     rdx, ?sc_modelCabKey@SignalState@@2QEB_WEB; wchar_t const * const SignalState::sc_modelCabKey
0x140340cdf  lea     rcx, [rbp+50h+var_D0]
0x140340ce3  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x140340ce8  nop
0x140340ce9  lea     r8, [rbp+50h+var_88]
0x140340ced  mov     rdx, [rax+18h]
0x140340cf1  mov     rcx, rbx
0x140340cf4  mov     rax, rdi
0x140340cf7  call    _guard_dispatch_icall
0x140340cfc  shr     eax, 1Fh
0x140340cff  xor     al, 1
0x140340d01  jz      loc_140340F6B
0x140340d07  mov     [rbp+50h+var_60], 0
0x140340d0f  mov     rbx, [rbp+50h+var_88]
0x140340d13  mov     rax, [rbx]
0x140340d16  mov     rdi, [rax+50h]
0x140340d1a  xor     ecx, ecx; string
0x140340d1c  call    cs:__imp_WindowsDeleteString
0x140340d22  mov     [rbp+50h+var_60], 0
0x140340d2a  lea     rdx, ?sc_modelIdKey@SignalState@@2QEB_WEB; wchar_t const * const SignalState::sc_modelIdKey
0x140340d31  lea     rcx, [rbp+50h+var_D0]
0x140340d35  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x140340d3a  nop
0x140340d3b  lea     r8, [rbp+50h+var_60]
0x140340d3f  mov     rdx, [rax+18h]
0x140340d43  mov     rcx, rbx
0x140340d46  mov     rax, rdi
0x140340d49  call    _guard_dispatch_icall
0x140340d4e  mov     rcx, [rbp+58h]; this
0x140340d52  test    eax, eax
0x140340d54  js      loc_140341132
0x140340d5a  mov     [rbp+50h+string], 0
0x140340d62  mov     rbx, [rbp+50h+var_88]
0x140340d66  mov     rax, [rbx]
0x140340d69  mov     rdi, [rax+50h]
0x140340d6d  xor     ecx, ecx; string
0x140340d6f  call    cs:__imp_WindowsDeleteString
0x140340d75  mov     [rbp+50h+string], 0
0x140340d7d  lea     rdx, ?sc_modelFileNameKey@SignalState@@2QEB_WEB; wchar_t const * const SignalState::sc_modelFileNameKey
0x140340d84  lea     rcx, [rbp+50h+var_D0]
0x140340d88  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x140340d8d  nop
0x140340d8e  lea     r8, [rbp+50h+string]
0x140340d92  mov     rdx, [rax+18h]
0x140340d96  mov     rcx, rbx
0x140340d99  mov     rax, rdi
0x140340d9c  call    _guard_dispatch_icall
0x140340da1  mov     rcx, [rbp+58h]; this
0x140340da5  test    eax, eax
0x140340da7  js      loc_140341147
0x140340dad  mov     [rbp+50h+var_70], 0
0x140340db5  mov     rbx, [rbp+50h+var_88]
0x140340db9  mov     rax, [rbx]
0x140340dbc  mov     rdi, [rax+50h]
0x140340dc0  xor     ecx, ecx; string
0x140340dc2  call    cs:__imp_WindowsDeleteString
0x140340dc8  mov     [rbp+50h+var_70], 0
0x140340dd0  lea     rdx, ?sc_modelFileUrlKey@SignalState@@2QEB_WEB; wchar_t const * const SignalState::sc_modelFileUrlKey
0x140340dd7  lea     rcx, [rbp+50h+var_D0]
0x140340ddb  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x140340de0  nop
0x140340de1  lea     r8, [rbp+50h+var_70]
0x140340de5  mov     rdx, [rax+18h]
0x140340de9  mov     rcx, rbx
0x140340dec  mov     rax, rdi
0x140340def  call    _guard_dispatch_icall
0x140340df4  mov     rcx, [rbp+58h]; this
0x140340df8  xor     ebx, ebx
0x140340dfa  test    eax, eax
0x140340dfc  js      loc_140341091
0x140340e02  xor     edx, edx; length
0x140340e04  mov     rcx, [rbp+50h+string]; string
0x140340e08  call    cs:__imp_WindowsGetStringRawBuffer
0x140340e0e  mov     qword ptr [rsp+150h+pExceptionObject], rax
0x140340e13  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140340e17  inc     rdi
0x140340e1a  cmp     [rax+rdi*2], bx
0x140340e1e  jnz     short loc_140340E17
0x140340e20  mov     qword ptr [rsp+150h+pExceptionObject+8], rdi
0x140340e25  movaps  xmm0, [rsp+150h+pExceptionObject]
0x140340e2a  movdqa  [rsp+150h+pExceptionObject], xmm0
0x140340e30  lea     rdx, [rsp+150h+pExceptionObject]
0x140340e35  lea     rcx, [rbp+50h+var_D0]
0x140340e39  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x140340e3e  nop
0x140340e3f  xor     edx, edx; length
0x140340e41  mov     rcx, [rbp+50h+var_70]; string
0x140340e45  call    cs:__imp_WindowsGetStringRawBuffer
0x140340e4b  mov     [rbp+50h+var_A8], rax
0x140340e4f  xor     edx, edx; length
0x140340e51  mov     rcx, [rbp+50h+var_60]; string
0x140340e55  call    cs:__imp_WindowsGetStringRawBuffer
0x140340e5b  mov     [rbp+50h+var_A0], rax
0x140340e5f  xor     edx, edx; length
0x140340e61  mov     rcx, [rbp+50h+var_98]; string
0x140340e65  call    cs:__imp_WindowsGetStringRawBuffer
0x140340e6b  mov     [rsp+150h+var_F8], rax
0x140340e70  mov     ecx, 218h; Size
0x140340e75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140340e7a  mov     qword ptr [rsp+150h+pExceptionObject], rax
0x140340e7f  mov     [rsp+150h+var_108], r13
0x140340e84  lea     rcx, [rbp+50h+var_D0]
0x140340e88  mov     [rsp+150h+var_110], rcx
0x140340e8d  lea     rcx, [rbp+50h+var_A8]
0x140340e91  mov     [rsp+150h+var_118], rcx
0x140340e96  lea     rcx, [rbp+50h+var_A0]
0x140340e9a  mov     [rsp+150h+var_120], rcx
0x140340e9f  lea     rcx, [rbp+50h+var_80]
0x140340ea3  mov     [rsp+150h+var_128], rcx
0x140340ea8  mov     [rsp+150h+var_130], r14
0x140340ead  mov     r9, r15
0x140340eb0  mov     r8, r12
0x140340eb3  lea     rdx, [rsp+150h+var_F8]
0x140340eb8  mov     rcx, rax
0x140340ebb  call    ??$?0PEB_WAEBV?$basic_zstring_view@_W@wil@@AEBV01@AEBV?$com_ptr_t@UIJsonValue@Json@Data@Windows@ABI@@Uerr_exception_policy@wil@@@1@AEAV21@PEB_WPEB_WVpath@filesystem@std@@AEAVUpdateDatabase@@@?$_Ref_count_obj2@VModelUpdate@@@std@@QEAA@$$QEAPEB_WAEBV?$basic_zstring_view@_W@wil@@1AEBV?$com_ptr_t@UIJsonValue@Json@Data@Windows@ABI@@Uerr_exception_policy@wil@@@3@AEAV43@00$$QEAVpath@filesystem@1@AEAVUpdateDatabase@@@Z; std::_Ref_count_obj2<ModelUpdate>::_Ref_count_obj2<ModelUpdate>(wchar_t const * &&,wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,wil::com_ptr_t<ABI::Windows::Data::Json::IJsonValue,wil::err_exception_policy> const &,wil::com_ptr_t<ABI::Windows::Data::Json::IJsonValue,wil::err_exception_policy> &,wchar_t const * &&,wchar_t const * &&,std::filesystem::path &&,UpdateDatabase &)
0x140340ec0  mov     rcx, rax
0x140340ec3  add     rax, 10h
0x140340ec7  mov     [rsi], rax
0x140340eca  mov     [rsi+8], rcx
0x140340ece  lea     rcx, [rbp+50h+var_D0]
0x140340ed2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140340ed7  nop
0x140340ed8  mov     rcx, [rbp+50h+var_70]; string
0x140340edc  call    cs:__imp_WindowsDeleteString
0x140340ee2  mov     [rbp+50h+var_70], rbx
0x140340ee6  mov     rcx, [rbp+50h+string]; string
0x140340eea  call    cs:__imp_WindowsDeleteString
0x140340ef0  mov     [rbp+50h+string], rbx
0x140340ef4  mov     rcx, [rbp+50h+var_60]; string
0x140340ef8  call    cs:__imp_WindowsDeleteString
0x140340efe  mov     [rbp+50h+var_60], rbx
0x140340f02  mov     rcx, [rbp+50h+var_88]
0x140340f06  test    rcx, rcx
0x140340f09  jz      short loc_140340F18
0x140340f0b  mov     rax, [rcx]
0x140340f0e  mov     rax, [rax+10h]
0x140340f12  call    _guard_dispatch_icall
0x140340f17  nop
0x140340f18  mov     rcx, [rbp+50h+var_80]
0x140340f1c  test    rcx, rcx
0x140340f1f  jz      short loc_140340F2E
0x140340f21  mov     rax, [rcx]
0x140340f24  mov     rax, [rax+10h]
0x140340f28  call    _guard_dispatch_icall
0x140340f2d  nop
0x140340f2e  mov     rcx, [rbp+50h+var_58]
0x140340f32  test    rcx, rcx
0x140340f35  jz      short loc_140340F44
0x140340f37  mov     rax, [rcx]
0x140340f3a  mov     rax, [rax+10h]
0x140340f3e  call    _guard_dispatch_icall
0x140340f43  nop
0x140340f44  mov     rcx, [rbp+50h+var_98]; string
0x140340f48  call    cs:__imp_WindowsDeleteString
0x140340f4e  mov     [rbp+50h+var_98], rbx
0x140340f52  mov     rcx, [rbp+50h+var_90]
0x140340f56  test    rcx, rcx
0x140340f59  jz      loc_14034106E
0x140340f5f  mov     rax, [rcx]
0x140340f62  mov     rax, [rax+10h]
0x140340f66  jmp     loc_140341068
0x140340f6b  xor     edx, edx; length
0x140340f6d  mov     rcx, [rbp+50h+var_98]; string
0x140340f71  call    cs:__imp_WindowsGetStringRawBuffer
0x140340f77  mov     [rsp+150h+var_F8], rax
0x140340f7c  mov     [rsp+150h+var_120], r13
0x140340f81  lea     rax, [rbp+50h+var_80]
0x140340f85  mov     [rsp+150h+var_128], rax
0x140340f8a  mov     [rsp+150h+var_130], r14
0x140340f8f  mov     r9, r15
0x140340f92  mov     r8, r12
0x140340f95  lea     rdx, [rsp+150h+var_F8]
0x140340f9a  lea     rcx, [rsp+150h+pExceptionObject]
0x140340f9f  call    ??$make_shared@VSignalUpdate@@PEB_WAEBV?$basic_zstring_view@_W@wil@@AEBV23@AEBV?$com_ptr_t@UIJsonValue@Json@Data@Windows@ABI@@Uerr_exception_policy@wil@@@3@AEAV43@AEAVUpdateDatabase@@@std@@YA?AV?$shared_ptr@VSignalUpdate@@@0@$$QEAPEB_WAEBV?$basic_zstring_view@_W@wil@@1AEBV?$com_ptr_t@UIJsonValue@Json@Data@Windows@ABI@@Uerr_exception_policy@wil@@@3@AEAV43@AEAVUpdateDatabase@@@Z; std::make_shared<SignalUpdate,wchar_t const *,wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,wil::com_ptr_t<ABI::Windows::Data::Json::IJsonValue,wil::err_exception_policy> const &,wil::com_ptr_t<ABI::Windows::Data::Json::IJsonValue,wil::err_exception_policy> &,UpdateDatabase &>(wchar_t const * &&,wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,wil::com_ptr_t<ABI::Windows::Data::Json::IJsonValue,wil::err_exception_policy> const &,wil::com_ptr_t<ABI::Windows::Data::Json::IJsonValue,wil::err_exception_policy> &,UpdateDatabase &)
0x140340fa4  mov     rcx, rax
0x140340fa7  xor     r14d, r14d
0x140340faa  mov     [rsi], r14
0x140340fad  mov     [rsi+8], r14
0x140340fb1  mov     rax, [rax]
0x140340fb4  mov     [rsi], rax
0x140340fb7  mov     rax, [rcx+8]
0x140340fbb  mov     [rsi+8], rax
0x140340fbf  mov     [rcx], r14
0x140340fc2  mov     [rcx+8], r14
0x140340fc6  mov     rbx, qword ptr [rsp+150h+pExceptionObject+8]
0x140340fcb  test    rbx, rbx
0x140340fce  jz      short loc_140341008
0x140340fd0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140340fd4  mov     eax, edi
0x140340fd6  lock xadd [rbx+8], eax
0x140340fdb  add     eax, edi
0x140340fdd  jnz     short loc_140341008
0x140340fdf  mov     rax, [rbx]
0x140340fe2  mov     rcx, rbx
0x140340fe5  mov     rax, [rax]
0x140340fe8  call    _guard_dispatch_icall
0x140340fed  mov     eax, edi
0x140340fef  lock xadd [rbx+0Ch], eax
0x140340ff4  add     eax, edi
0x140340ff6  jnz     short loc_140341008
0x140340ff8  mov     rax, [rbx]
  ... truncated ...
```
