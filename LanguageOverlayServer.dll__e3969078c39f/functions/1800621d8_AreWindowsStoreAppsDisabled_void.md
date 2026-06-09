# _AreWindowsStoreAppsDisabled(void)

- ea: `0x1800621d8`
- end: `0x1800623ca`
- name: `?_AreWindowsStoreAppsDisabled@@YA_NXZ`
- size: `498`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180061e88`
- `0x180062098`

## callees

- `0x180003a00`
- `0x180012a98`
- `0x180034b30`
- `0x180034d9c`
- `0x18003771c`
- `0x18004b9c0`
- `0x1800621d8`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006222e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006222e`

## string_xrefs

- `0x180062227`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`
- `0x18006238d`: `onecore\base\languageoverlay\common\policyutils.cpp`
- `0x1800623a2`: `onecore\base\languageoverlay\common\policyutils.cpp`
- `0x1800623b7`: `onecore\base\languageoverlay\common\policyutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool _AreWindowsStoreAppsDisabled(void)
{
  HRESULT v0; // eax
  int v1; // edx
  unsigned int v2; // r8d
  int v3; // eax
  unsigned int v4; // r8d
  wil::details::in1diag3 *v5; // rcx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, PVOID, PVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rsi
  PVOID Reserved1; // rbx
  unsigned int v9; // r8d
  HSTRING_HEADER *v10; // rax
  int v11; // eax
  DWORD v12; // edx
  int v13; // r8d
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // rbx
  int v15; // eax
  const char *v16; // r9
  bool v17; // bl
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // rcx
  _QWORD *v19; // rcx
  bool result; // al
  int v21; // [rsp+20h] [rbp-78h]
  _BYTE v22[8]; // [rsp+30h] [rbp-68h] BYREF
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-60h] BYREF
  _QWORD *v24; // [rsp+40h] [rbp-58h] BYREF
  HSTRING_HEADER v25; // [rsp+48h] [rbp-50h] BYREF
  __int64 v26; // [rsp+60h] [rbp-38h] BYREF
  HSTRING_HEADER v27; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v24 = 0;
  v23 = 0;
  v22[0] = 0;
  v26 = 0;
  v0 = WindowsCreateStringReference(
         L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager",
         0x47u,
         &v25,
         (HSTRING *)&v26);
  try
  {
    if ( v0 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v0, v1, v2);
    }
    else
    {
      v3 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>(
             v26,
             (__int64 *)&v24);
      v5 = retaddr;
      if ( v3 >= 0 )
      {
        v6 = (__int64)v24;
        v7 = *(__int64 (__fastcall **)(__int64, PVOID, PVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*v24 + 184LL);
        Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &v25,
                      (const WCHAR **)&off_18006DB00,
                      v4)[1].Reserved.Reserved1;
        v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v27, (const WCHAR **)off_18006DAF8, v9);
        v11 = v7(v6, v10[1].Reserved.Reserved1, Reserved1, &v23);
        if ( v11 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x12B,
            (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
            (const char *)(unsigned int)v11,
            v21);
        v14 = v23;
        v15 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(v23, v12, v13);
        if ( v15 >= 0 )
          v15 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _BYTE *))(*v14)[8])(
                  v14,
                  v22);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x12F,
            (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
            (const char *)(unsigned int)v15,
            v21);
        v17 = v22[0] != 0;
        v18 = v23;
        if ( v23 )
        {
          v23 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v18)[2])(v18);
        }
        v19 = v24;
        if ( v24 )
        {
          v24 = 0;
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v19 + 16LL))(v19, *v19);
        }
        return v17;
      }
    }
    wil::details::in1diag3::Throw_Hr(
      v5,
      (void *)0x126,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
      (const char *)(unsigned int)v3,
      v21);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
      v16);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800621d8  mov     r11, rsp
0x1800621db  mov     [r11+8], rbx
0x1800621df  mov     [r11+10h], rsi
0x1800621e3  push    rdi
0x1800621e4  sub     rsp, 90h
0x1800621eb  mov     rax, cs:__security_cookie
0x1800621f2  xor     rax, rsp
0x1800621f5  mov     [rsp+98h+var_10], rax
0x1800621fd  mov     qword ptr [r11-58h], 0
0x180062205  mov     qword ptr [r11-60h], 0
0x18006220d  mov     [rsp+98h+var_68], 0
0x180062212  mov     qword ptr [r11-38h], 0
0x18006221a  lea     r9, [r11-38h]; string
0x18006221e  lea     r8, [r11-50h]; hstringHeader
0x180062222  mov     edx, 47h ; 'G'; length
0x180062227  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_AppInstallManager@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x18006222e  call    cs:__imp_WindowsCreateStringReference
0x180062234  test    eax, eax
0x180062236  js      loc_180062382
0x18006223c  lea     rdx, [rsp+98h+var_58]
0x180062241  mov     rcx, [rsp+98h+var_38]
0x180062246  call    ??$ActivateInstance@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>)
0x18006224b  mov     rcx, [rsp+98h]
0x180062253  test    eax, eax
0x180062255  js      loc_18006238A
0x18006225b  mov     rdi, [rsp+98h+var_58]
0x180062260  mov     rax, [rdi]
0x180062263  mov     rsi, [rax+0B8h]
0x18006226a  mov     rcx, [rsp+98h+var_60]
0x18006226f  test    rcx, rcx
0x180062272  jz      short loc_18006228A
0x180062274  mov     [rsp+98h+var_60], 0
0x18006227d  mov     rax, [rcx]
0x180062280  mov     rax, [rax+10h]
0x180062284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062289  nop
0x18006228a  lea     rdx, off_18006DB00; "CN=Microsoft Corporation, O=Microsoft C"...
0x180062291  lea     rcx, [rsp+98h+var_50]
0x180062296  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18006229b  nop
0x18006229c  mov     rbx, [rax+18h]
0x1800622a0  lea     rdx, off_18006DAF8; "Microsoft.WindowsStore"
0x1800622a7  lea     rcx, [rsp+98h+var_30]
0x1800622ac  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800622b1  nop
0x1800622b2  lea     r9, [rsp+98h+var_60]
0x1800622b7  mov     r8, rbx
0x1800622ba  mov     rdx, [rax+18h]
0x1800622be  mov     rcx, rdi
0x1800622c1  mov     rax, rsi
0x1800622c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800622c9  mov     rcx, [rsp+98h]; this
0x1800622d1  test    eax, eax
0x1800622d3  js      loc_18006239F
0x1800622d9  mov     rbx, [rsp+98h+var_60]
0x1800622de  mov     rcx, rbx
0x1800622e1  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)
0x1800622e6  test    eax, eax
0x1800622e8  js      short loc_1800622FF
0x1800622ea  mov     rax, [rbx]
0x1800622ed  lea     rdx, [rsp+98h+var_68]
0x1800622f2  mov     rcx, rbx
0x1800622f5  mov     rax, [rax+40h]
0x1800622f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800622fe  nop
0x1800622ff  mov     rcx, [rsp+98h]; this
0x180062307  test    eax, eax
0x180062309  js      loc_1800623B4
0x18006230f  cmp     [rsp+98h+var_68], 0
0x180062314  setnz   bl
0x180062317  mov     rcx, [rsp+98h+var_60]
0x18006231c  test    rcx, rcx
0x18006231f  jz      short loc_180062337
0x180062321  mov     [rsp+98h+var_60], 0
0x18006232a  mov     rax, [rcx]
0x18006232d  mov     rax, [rax+10h]
0x180062331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062336  nop
0x180062337  mov     rcx, [rsp+98h+var_58]
0x18006233c  test    rcx, rcx
0x18006233f  jz      short loc_180062357
0x180062341  mov     [rsp+98h+var_58], 0
0x18006234a  mov     rdx, [rcx]
0x18006234d  mov     rax, [rdx+10h]
0x180062351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062356  nop
0x180062357  mov     al, bl
0x180062359  jmp     short loc_18006235D
0x18006235b  xor     al, al
0x18006235d  mov     rcx, [rsp+98h+var_10]
0x180062365  xor     rcx, rsp; StackCookie
0x180062368  call    __security_check_cookie
0x18006236d  lea     r11, [rsp+98h+var_8]
0x180062375  mov     rbx, [r11+10h]
0x180062379  mov     rsi, [r11+18h]
0x18006237d  mov     rsp, r11
0x180062380  pop     rdi
0x180062381  retn
0x180062382  mov     ecx, eax; this
0x180062384  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180062389  nop
0x18006238a  mov     r9d, eax; char *
0x18006238d  lea     r8, aOnecoreBaseLan_24; "onecore\\base\\languageoverlay\\common"...
0x180062394  mov     edx, 126h; void *
0x180062399  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006239f  mov     r9d, eax; char *
0x1800623a2  lea     r8, aOnecoreBaseLan_24; "onecore\\base\\languageoverlay\\common"...
0x1800623a9  mov     edx, 12Bh; void *
0x1800623ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800623b4  mov     r9d, eax; char *
0x1800623b7  lea     r8, aOnecoreBaseLan_24; "onecore\\base\\languageoverlay\\common"...
0x1800623be  mov     edx, 12Fh; void *
0x1800623c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
