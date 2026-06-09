# ThemeAppModelWrapper::InstallThemePackFromExtension(Microsoft::WRL::ComPtr<IThemeManager2>,Windows::Internal::StateRepository::IAppExtension *)

- ea: `0x18026ba2c`
- end: `0x18026c01e`
- name: `?InstallThemePackFromExtension@ThemeAppModelWrapper@@SAJV?$ComPtr@UIThemeManager2@@@WRL@Microsoft@@PEAUIAppExtension@StateRepository@Internal@Windows@@@Z`
- size: `1522`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180112930`
- `0x180115490`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x180019a20`
- `0x18002012c`
- `0x1800212b0`
- `0x1800234c4`
- `0x1800670c4`
- `0x18010be98`
- `0x180268ab8`
- `0x180269220`
- `0x18026a114`
- `0x18026a1e8`
- `0x18026b11c`
- `0x18026ba2c`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18026badf`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18026badf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026bc6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026bcb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026bddc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026beb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026bf04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026bf39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026bc6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026bcb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026bddc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026beb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026bf04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026bf39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026be24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026be24`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18026bb54`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18026bb54`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall ThemeAppModelWrapper::InstallThemePackFromExtension(
        __int64 *a1,
        struct Windows::Internal::StateRepository::IAppExtension *a2)
{
  int v4; // ebx
  int ThemePackFromExtension; // eax
  __int64 v6; // rbx
  int ActivationFactory; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 *); // rbx
  __int64 v10; // rax
  int v11; // eax
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rdi
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  int v18; // eax
  struct Windows::Storage::IStorageFile *v19; // rdi
  __int64 (__fastcall *v20)(struct Windows::Storage::IStorageFile *, __int64, HSTRING, __int64); // rbx
  int v21; // eax
  __int64 v22; // rdi
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, _QWORD, PCWSTR, _QWORD); // rbx
  PCWSTR StringRawBuffer; // rax
  int v29; // eax
  unsigned __int64 v30; // r9
  __int64 v31; // rdx
  int ThemeAppxMapping; // eax
  int v34; // [rsp+20h] [rbp-E0h]
  int *v35; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  struct Windows::Storage::IStorageFile *v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v42; // [rsp+70h] [rbp-90h] BYREF
  int v43[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h] BYREF
  __int64 v45; // [rsp+88h] [rbp-78h] BYREF
  __int64 v46; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v47[2]; // [rsp+98h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v49; // [rsp+C0h] [rbp-40h]
  WCHAR sourceString[264]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v47[1] = a1;
  if ( a2 )
  {
    v37 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    ThemePackFromExtension = ThemeAppModelWrapper::GetThemePackFromExtension(a2, &v37);
    v4 = ThemePackFromExtension;
    if ( ThemePackFromExtension < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19C,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
        (const char *)(unsigned int)ThemePackFromExtension,
        v34);
LABEL_44:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      goto LABEL_45;
    }
    v38 = 0;
    if ( !(unsigned int)GetTempPath2W(260, sourceString) )
    {
      v4 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A1,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
        (const char *)0x8000FFFFLL,
        v34);
LABEL_43:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      goto LABEL_44;
    }
    v39 = 0;
    v49 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Storage.StorageFolder",
      0x1Eu,
      0x1Du);
    v6 = v49;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    ActivationFactory = RoGetActivationFactory(v6, &GUID_08f327ff_85d5_48b9_aee9_28511e339f9f, &v39);
    v4 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A3,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v34);
LABEL_42:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      goto LABEL_43;
    }
    v40 = 0;
    v8 = v39;
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v39 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
    v11 = v9(v8, *(_QWORD *)(v10 + 24), &v40);
    v4 = v11;
    if ( v11 >= 0 )
    {
      v14 = v40;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      v4 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFolder *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *>>(v14);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 64LL))(v14, &v38);
        if ( v4 >= 0 )
        {
          v41 = 0;
          v15 = Microsoft::WRL::ComPtr<Windows::Storage::IStorageFolder>::As<Windows::Storage::IStorageItem>(&v37, &v41);
          v4 = v15;
          if ( v15 >= 0 )
          {
            string = 0;
            v16 = v41;
            v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v41 + 88LL);
            WindowsDeleteString(0);
            string = 0;
            v18 = v17(v16, &string);
            v4 = v18;
            if ( v18 >= 0 )
            {
              *(_QWORD *)v43 = 0;
              v19 = v37;
              v20 = *(__int64 (__fastcall **)(struct Windows::Storage::IStorageFile *, __int64, HSTRING, __int64))(*(_QWORD *)v37 + 96LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v43);
              v35 = v43;
              v21 = v20(v19, v38, string, 1);
              v4 = v21;
              if ( v21 >= 0 )
              {
                v44 = 0;
                v22 = *(_QWORD *)v43;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                v4 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(
                       v22,
                       8);
                if ( v4 < 0
                  || (v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 64LL))(v22, &v44), v4 < 0) )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x1B6,
                    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\theme"
                                  "appmodelwrapper.cpp",
                    (const char *)(unsigned int)v4,
                    (int)v43);
                }
                else
                {
                  v45 = 0;
                  v23 = Microsoft::WRL::ComPtr<Windows::Storage::IStorageFolder>::As<Windows::Storage::IStorageItem>(
                          &v44,
                          &v45);
                  v4 = v23;
                  if ( v23 >= 0 )
                  {
                    v42 = 0;
                    v24 = v45;
                    v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v45 + 96LL);
                    WindowsDeleteString(0);
                    v42 = 0;
                    v4 = v25(v24, &v42);
                    v46 = 0;
                    if ( v4 >= 0 )
                    {
                      v26 = *a1;
                      v27 = *(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, _QWORD))(*(_QWORD *)*a1 + 136LL);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                      StringRawBuffer = WindowsGetStringRawBuffer(v42, 0);
                      LODWORD(v35) = 4;
                      v4 = v27(v26, 0, StringRawBuffer, 0);
                    }
                    v29 = CleanupStorageItem(&v45);
                    if ( v29 < 0 )
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0x1C8,
                        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\t"
                                      "hemeappmodelwrapper.cpp",
                        (const char *)(unsigned int)v29,
                        (int)v35);
                    if ( v4 >= 0 )
                    {
                      v47[0] = v46;
                      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v47);
                      ThemeAppxMapping = ThemeAppModelWrapper::CreateThemeAppxMapping(v47, a2);
                      v4 = ThemeAppxMapping;
                      if ( ThemeAppxMapping >= 0 )
                      {
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                        WindowsDeleteString(v42);
                        v42 = 0;
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v43);
                        WindowsDeleteString(string);
                        string = 0;
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
                        v4 = 0;
                        goto LABEL_45;
                      }
                      v30 = (unsigned int)ThemeAppxMapping;
                      v31 = 462;
                    }
                    else
                    {
                      v30 = (unsigned int)v4;
                      v31 = 459;
                    }
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v31,
                      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\the"
                                    "meappmodelwrapper.cpp",
                      (const char *)v30,
                      (int)v35);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                    WindowsDeleteString(v42);
                    v42 = 0;
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x1BB,
                      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\the"
                                    "meappmodelwrapper.cpp",
                      (const char *)(unsigned int)v23,
                      (int)v43);
                  }
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1B4,
                  (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeap"
                                "pmodelwrapper.cpp",
                  (const char *)(unsigned int)v21,
                  (int)v43);
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v43);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1AF,
                (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
                (const char *)(unsigned int)v18,
                v34);
            }
            WindowsDeleteString(string);
            string = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1AC,
              (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
              (const char *)(unsigned int)v15,
              v34);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
          goto LABEL_41;
        }
      }
      v12 = (unsigned int)v4;
      v13 = 424;
    }
    else
    {
      v12 = (unsigned int)v11;
      v13 = 422;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
      (const char *)v12,
      v34);
LABEL_41:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    goto LABEL_42;
  }
  v4 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19A,
    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
    (const char *)0x80070057LL,
    v34);
LABEL_45:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18026ba2c  mov     [rsp-8+arg_10], rbx
0x18026ba31  push    rbp
0x18026ba32  push    rsi
0x18026ba33  push    rdi
0x18026ba34  push    r14
0x18026ba36  push    r15
0x18026ba38  lea     rbp, [rsp-1F0h]
0x18026ba40  sub     rsp, 2F0h
0x18026ba47  mov     rax, cs:__security_cookie
0x18026ba4e  xor     rax, rsp
0x18026ba51  mov     [rbp+210h+var_30], rax
0x18026ba58  mov     rsi, rdx
0x18026ba5b  mov     r14, rcx
0x18026ba5e  mov     [rbp+210h+var_270], rcx
0x18026ba62  xor     r15d, r15d
0x18026ba65  test    rdx, rdx
0x18026ba68  jnz     short loc_18026BA8F
0x18026ba6a  mov     rcx, [rbp+218h]; this
0x18026ba71  mov     ebx, 80070057h
0x18026ba76  mov     r9d, ebx; char *
0x18026ba79  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026ba80  mov     edx, 19Ah; void *
0x18026ba85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ba8a  jmp     loc_18026BFED
0x18026ba8f  mov     [rsp+310h+var_2C8], r15
0x18026ba94  lea     rcx, [rsp+310h+var_2C8]
0x18026ba99  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026ba9e  lea     rdx, [rsp+310h+var_2C8]; struct Windows::Storage::IStorageFile **
0x18026baa3  mov     rcx, rsi; struct Windows::Internal::StateRepository::IAppExtension *
0x18026baa6  call    ?GetThemePackFromExtension@ThemeAppModelWrapper@@SAJPEAUIAppExtension@StateRepository@Internal@Windows@@PEAPEAUIStorageFile@Storage@5@@Z; ThemeAppModelWrapper::GetThemePackFromExtension(Windows::Internal::StateRepository::IAppExtension *,Windows::Storage::IStorageFile * *)
0x18026baab  mov     ebx, eax
0x18026baad  test    eax, eax
0x18026baaf  jns     short loc_18026BAD1
0x18026bab1  mov     rcx, [rbp+218h]; this
0x18026bab8  mov     r9d, eax; char *
0x18026babb  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026bac2  mov     edx, 19Ch; void *
0x18026bac7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bacc  jmp     loc_18026BFE2
0x18026bad1  mov     [rsp+310h+var_2C0], r15
0x18026bad6  lea     rdx, [rbp+210h+sourceString]
0x18026bada  mov     ecx, 104h
0x18026badf  call    cs:__imp_GetTempPath2W
0x18026bae6  nop     dword ptr [rax+rax+00h]
0x18026baeb  test    eax, eax
0x18026baed  jnz     short loc_18026BB14
0x18026baef  mov     rcx, [rbp+218h]; this
0x18026baf6  mov     ebx, 8000FFFFh
0x18026bafb  mov     r9d, ebx; char *
0x18026bafe  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026bb05  mov     edx, 1A1h; void *
0x18026bb0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bb0f  jmp     loc_18026BFD7
0x18026bb14  mov     [rsp+310h+var_2B8], r15
0x18026bb19  mov     [rbp+210h+var_250], r15
0x18026bb1d  mov     r9d, 1Dh; unsigned int
0x18026bb23  lea     r8d, [r9+1]; unsigned int
0x18026bb27  lea     rdx, ?RuntimeClass_Windows_Storage_StorageFolder@@3QBGB; "Windows.Storage.StorageFolder"
0x18026bb2e  lea     rcx, [rbp+210h+hstringHeader]; hstringHeader
0x18026bb32  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18026bb37  mov     rbx, [rbp+210h+var_250]
0x18026bb3b  lea     rcx, [rsp+310h+var_2B8]
0x18026bb40  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026bb45  lea     r8, [rsp+310h+var_2B8]
0x18026bb4a  lea     rdx, _GUID_08f327ff_85d5_48b9_aee9_28511e339f9f
0x18026bb51  mov     rcx, rbx
0x18026bb54  call    cs:__imp_RoGetActivationFactory
0x18026bb5b  nop     dword ptr [rax+rax+00h]
0x18026bb60  mov     ebx, eax
0x18026bb62  test    eax, eax
0x18026bb64  jns     short loc_18026BB86
0x18026bb66  mov     rcx, [rbp+218h]; this
0x18026bb6d  mov     r9d, eax; char *
0x18026bb70  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026bb77  mov     edx, 1A3h; void *
0x18026bb7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bb81  jmp     loc_18026BFCC
0x18026bb86  mov     [rsp+310h+var_2B0], r15
0x18026bb8b  mov     rdi, [rsp+310h+var_2B8]
0x18026bb90  mov     rax, [rdi]
0x18026bb93  mov     rbx, [rax+30h]
0x18026bb97  lea     rcx, [rsp+310h+var_2B0]
0x18026bb9c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026bba1  lea     rdx, [rbp+210h+sourceString]; sourceString
0x18026bba5  lea     rcx, [rbp+210h+hstringHeader]; hstringHeader
0x18026bba9  call    ??$?0$0BAE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BAE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[260])
0x18026bbae  nop
0x18026bbaf  lea     r8, [rsp+310h+var_2B0]
0x18026bbb4  mov     rdx, [rax+18h]
0x18026bbb8  mov     rcx, rdi
0x18026bbbb  mov     rax, rbx
0x18026bbbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026bbc3  mov     ebx, eax
0x18026bbc5  test    eax, eax
0x18026bbc7  jns     short loc_18026BBD6
0x18026bbc9  mov     r9d, eax
0x18026bbcc  mov     edx, 1A6h
0x18026bbd1  jmp     loc_18026BFAD
0x18026bbd6  mov     rdi, [rsp+310h+var_2B0]
0x18026bbdb  lea     rcx, [rsp+310h+var_2C0]
0x18026bbe0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026bbe5  mov     rcx, rdi
0x18026bbe8  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFolder@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFolder *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> *,tagCOWAIT_FLAGS,void *)
0x18026bbed  mov     ebx, eax
0x18026bbef  test    eax, eax
0x18026bbf1  js      loc_18026BFA5
0x18026bbf7  mov     rax, [rdi]
0x18026bbfa  lea     rdx, [rsp+310h+var_2C0]
0x18026bbff  mov     rcx, rdi
0x18026bc02  mov     rax, [rax+40h]
0x18026bc06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026bc0b  mov     ebx, eax
0x18026bc0d  test    eax, eax
0x18026bc0f  js      loc_18026BFA5
0x18026bc15  mov     [rsp+310h+var_2A8], r15
0x18026bc1a  lea     rdx, [rsp+310h+var_2A8]
0x18026bc1f  lea     rcx, [rsp+310h+var_2C8]
0x18026bc24  call    ??$As@UIStorageItem@Storage@Windows@@@?$ComPtr@UIStorageFolder@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIStorageItem@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::IStorageFolder>::As<Windows::Storage::IStorageItem>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem>>)
0x18026bc29  mov     ebx, eax
0x18026bc2b  test    eax, eax
0x18026bc2d  jns     short loc_18026BC5A
0x18026bc2f  mov     rcx, [rbp+218h]; this
0x18026bc36  mov     r9d, eax; char *
0x18026bc39  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026bc40  mov     edx, 1ACh; void *
0x18026bc45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bc4a  nop
0x18026bc4b  lea     rcx, [rsp+310h+var_2A8]
0x18026bc50  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026bc55  jmp     loc_18026BFC1
0x18026bc5a  mov     [rsp+310h+string], r15
0x18026bc5f  mov     rdi, [rsp+310h+var_2A8]
0x18026bc64  mov     rax, [rdi]
0x18026bc67  mov     rbx, [rax+58h]
0x18026bc6b  xor     ecx, ecx; string
0x18026bc6d  call    cs:__imp_WindowsDeleteString
0x18026bc74  nop     dword ptr [rax+rax+00h]
0x18026bc79  mov     [rsp+310h+string], r15
0x18026bc7e  lea     rdx, [rsp+310h+string]
0x18026bc83  mov     rcx, rdi
0x18026bc86  mov     rax, rbx
0x18026bc89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026bc8e  mov     ebx, eax
0x18026bc90  test    eax, eax
0x18026bc92  jns     short loc_18026BCC8
0x18026bc94  mov     rcx, [rbp+218h]; this
0x18026bc9b  mov     r9d, eax; char *
0x18026bc9e  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026bca5  mov     edx, 1AFh; void *
0x18026bcaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bcaf  nop
0x18026bcb0  mov     rcx, [rsp+310h+string]; string
0x18026bcb5  call    cs:__imp_WindowsDeleteString
0x18026bcbc  nop     dword ptr [rax+rax+00h]
0x18026bcc1  mov     [rsp+310h+string], r15
0x18026bcc6  jmp     short loc_18026BC4B
0x18026bcc8  mov     qword ptr [rsp+310h+var_298], r15
0x18026bccd  mov     rdi, [rsp+310h+var_2C8]
0x18026bcd2  mov     rax, [rdi]
0x18026bcd5  mov     rbx, [rax+60h]
0x18026bcd9  lea     rcx, [rsp+310h+var_298]
0x18026bcde  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026bce3  lea     rax, [rsp+310h+var_298]
0x18026bce8  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x18026bced  mov     r9d, 1
0x18026bcf3  mov     r8, [rsp+310h+string]
0x18026bcf8  mov     rdx, [rsp+310h+var_2C0]
0x18026bcfd  mov     rcx, rdi
0x18026bd00  mov     rax, rbx
0x18026bd03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026bd08  mov     ebx, eax
0x18026bd0a  test    eax, eax
0x18026bd0c  jns     short loc_18026BD39
0x18026bd0e  mov     rcx, [rbp+218h]; this
0x18026bd15  mov     r9d, eax; char *
0x18026bd18  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026bd1f  mov     edx, 1B4h; void *
0x18026bd24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bd29  nop
0x18026bd2a  lea     rcx, [rsp+310h+var_298]
0x18026bd2f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026bd34  jmp     loc_18026BCB0
0x18026bd39  mov     [rbp+210h+var_290], r15
0x18026bd3d  mov     rdi, qword ptr [rsp+310h+var_298]
0x18026bd42  lea     rcx, [rbp+210h+var_290]
0x18026bd46  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026bd4b  mov     edx, 8
0x18026bd50  mov     rcx, rdi
0x18026bd53  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)
0x18026bd58  mov     ebx, eax
0x18026bd5a  test    eax, eax
0x18026bd5c  js      loc_18026BF85
0x18026bd62  mov     rax, [rdi]
0x18026bd65  lea     rdx, [rbp+210h+var_290]
0x18026bd69  mov     rcx, rdi
0x18026bd6c  mov     rax, [rax+40h]
0x18026bd70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026bd75  mov     ebx, eax
0x18026bd77  test    eax, eax
0x18026bd79  js      loc_18026BF85
0x18026bd7f  mov     [rbp+210h+var_288], r15
0x18026bd83  lea     rdx, [rbp+210h+var_288]
0x18026bd87  lea     rcx, [rbp+210h+var_290]
0x18026bd8b  call    ??$As@UIStorageItem@Storage@Windows@@@?$ComPtr@UIStorageFolder@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIStorageItem@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::IStorageFolder>::As<Windows::Storage::IStorageItem>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem>>)
0x18026bd90  mov     ebx, eax
0x18026bd92  test    eax, eax
0x18026bd94  jns     short loc_18026BDCA
0x18026bd96  mov     rcx, [rbp+218h]; this
0x18026bd9d  mov     r9d, eax; char *
0x18026bda0  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026bda7  mov     edx, 1BBh; void *
0x18026bdac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bdb1  nop
0x18026bdb2  lea     rcx, [rbp+210h+var_288]
0x18026bdb6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026bdbb  nop
0x18026bdbc  lea     rcx, [rbp+210h+var_290]
0x18026bdc0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026bdc5  jmp     loc_18026BD2A
0x18026bdca  mov     [rsp+310h+var_2A0], r15
0x18026bdcf  mov     rdi, [rbp+210h+var_288]
0x18026bdd3  mov     rax, [rdi]
0x18026bdd6  mov     rbx, [rax+60h]
0x18026bdda  xor     ecx, ecx; string
0x18026bddc  call    cs:__imp_WindowsDeleteString
0x18026bde3  nop     dword ptr [rax+rax+00h]
0x18026bde8  mov     [rsp+310h+var_2A0], r15
0x18026bded  lea     rdx, [rsp+310h+var_2A0]
0x18026bdf2  mov     rcx, rdi
0x18026bdf5  mov     rax, rbx
0x18026bdf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026bdfd  mov     ebx, eax
0x18026bdff  mov     [rbp+210h+var_280], r15
0x18026be03  test    eax, eax
0x18026be05  js      short loc_18026BE5B
0x18026be07  mov     rdi, [r14]
0x18026be0a  mov     rax, [rdi]
0x18026be0d  mov     rbx, [rax+88h]
0x18026be14  lea     rcx, [rbp+210h+var_280]
0x18026be18  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026be1d  xor     edx, edx; length
0x18026be1f  mov     rcx, [rsp+310h+var_2A0]; string
0x18026be24  call    cs:__imp_WindowsGetStringRawBuffer
0x18026be2b  nop     dword ptr [rax+rax+00h]
0x18026be30  lea     rcx, [rbp+210h+var_280]
0x18026be34  mov     [rsp+310h+var_2E0], rcx
0x18026be39  mov     [rsp+310h+var_2E8], r15
0x18026be3e  mov     [rsp+310h+var_2F0], 4; int
0x18026be46  xor     r9d, r9d
0x18026be49  mov     r8, rax
0x18026be4c  xor     edx, edx
0x18026be4e  mov     rcx, rdi
0x18026be51  mov     rax, rbx
0x18026be54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026be59  mov     ebx, eax
0x18026be5b  lea     rcx, [rbp+210h+var_288]
0x18026be5f  call    ?CleanupStorageItem@@YAJAEBV?$ComPtr@UIStorageItem@Storage@Windows@@@WRL@Microsoft@@@Z; CleanupStorageItem(Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem> const &)
0x18026be64  mov     rcx, [rbp+218h]; this
0x18026be6b  test    eax, eax
0x18026be6d  jns     short loc_18026BE83
0x18026be6f  mov     r9d, eax; char *
0x18026be72  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026be79  mov     edx, 1C8h; void *
0x18026be7e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18026be83  test    ebx, ebx
0x18026be85  jns     short loc_18026BEC8
0x18026be87  mov     r9d, ebx; char *
0x18026be8a  mov     edx, 1CBh; void *
0x18026be8f  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026be96  mov     rcx, [rbp+218h]; this
0x18026be9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bea2  nop
0x18026bea3  lea     rcx, [rbp+210h+var_280]
0x18026bea7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026beac  nop
0x18026bead  mov     rcx, [rsp+310h+var_2A0]; string
0x18026beb2  call    cs:__imp_WindowsDeleteString
0x18026beb9  nop     dword ptr [rax+rax+00h]
0x18026bebe  mov     [rsp+310h+var_2A0], r15
0x18026bec3  jmp     loc_18026BDB2
0x18026bec8  mov     rax, [rbp+210h+var_280]
0x18026becc  mov     [rbp+210h+var_278], rax
0x18026bed0  lea     rcx, [rbp+210h+var_278]
0x18026bed4  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18026bed9  mov     rdx, rsi
0x18026bedc  lea     rcx, [rbp+210h+var_278]
0x18026bee0  call    ?CreateThemeAppxMapping@ThemeAppModelWrapper@@CAJV?$ComPtr@UITheme@@@WRL@Microsoft@@PEAUIAppExtension@StateRepository@Internal@Windows@@@Z; ThemeAppModelWrapper::CreateThemeAppxMapping(Microsoft::WRL::ComPtr<ITheme>,Windows::Internal::StateRepository::IAppExtension *)
0x18026bee5  mov     ebx, eax
0x18026bee7  test    eax, eax
0x18026bee9  jns     short loc_18026BEF5
0x18026beeb  mov     r9d, eax
0x18026beee  mov     edx, 1CEh
0x18026bef3  jmp     short loc_18026BE8F
0x18026bef5  lea     rcx, [rbp+210h+var_280]
0x18026bef9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026befe  nop
0x18026beff  mov     rcx, [rsp+310h+var_2A0]; string
0x18026bf04  call    cs:__imp_WindowsDeleteString
0x18026bf0b  nop     dword ptr [rax+rax+00h]
0x18026bf10  mov     [rsp+310h+var_2A0], r15
  ... truncated ...
```
