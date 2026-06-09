# ThemeAppModelWrapper::GetPublicFolderForTheme(Windows::Internal::StateRepository::IAppExtension *,Windows::Storage::IStorageFolder * *)

- ea: `0x18026aba4`
- end: `0x18026aff8`
- name: `?GetPublicFolderForTheme@ThemeAppModelWrapper@@CAJPEAUIAppExtension@StateRepository@Internal@Windows@@PEAPEAUIStorageFolder@Storage@5@@Z`
- size: `1108`
- prototype: `__int64 __fastcall(struct Windows::Internal::StateRepository::IAppExtension *, struct Windows::Storage::IStorageFolder **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18026b11c`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x180019a20`
- `0x18002012c`
- `0x18026983c`
- `0x18026aba4`
- `0x18026ecc0`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026add0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026ae12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026ae31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026ae73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026af7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026af8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026add0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026ae12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026ae31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026ae73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026af7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026af8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026aeb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026af19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026aeb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026af19`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18026ad34`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18026ad34`
- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_PartialTrustCaller` at `0x18026af51`
- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_PartialTrustCaller` at `0x18026af51`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ThemeAppModelWrapper::GetPublicFolderForTheme(
        struct Windows::Internal::StateRepository::IAppExtension *a1,
        struct Windows::Storage::IStorageFolder **a2)
{
  __int64 v4; // rdx
  unsigned int v5; // ebx
  __int64 (__fastcall *v6)(struct Windows::Internal::StateRepository::IAppExtension *, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rbx
  int ActivationFactory; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  int v21; // eax
  __int64 (__fastcall *v22)(struct Windows::Internal::StateRepository::IAppExtension *, HSTRING *); // rbx
  int v23; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int appended; // eax
  __int64 v26; // rdx
  const unsigned __int16 *v27; // rax
  HSTRING string; // [rsp+20h] [rbp-59h] BYREF
  HSTRING v30; // [rsp+28h] [rbp-51h] BYREF
  __int64 v31; // [rsp+30h] [rbp-49h] BYREF
  __int64 v32; // [rsp+38h] [rbp-41h] BYREF
  __int64 v33; // [rsp+40h] [rbp-39h] BYREF
  __int64 v34; // [rsp+48h] [rbp-31h] BYREF
  __int64 v35; // [rsp+50h] [rbp-29h] BYREF
  __int128 v36; // [rsp+58h] [rbp-21h] BYREF
  int v37; // [rsp+68h] [rbp-11h]
  _QWORD v38[3]; // [rsp+70h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v40; // [rsp+A0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( a1 )
  {
    if ( !a2 )
    {
      v4 = 623;
      goto LABEL_3;
    }
    *a2 = 0;
    v35 = 0;
    v6 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IAppExtension *, __int64 *))(*(_QWORD *)a1 + 136LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    v7 = v6(a1, &v35);
    v5 = v7;
    if ( v7 >= 0 )
    {
      v31 = 0;
      v8 = v35;
      v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 72LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      v10 = v9(v8, &v31);
      v5 = v10;
      if ( v10 >= 0 )
      {
        v32 = 0;
        v11 = v31;
        v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 72LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
        v13 = v12(v11, &v32);
        v5 = v13;
        if ( v13 >= 0 )
        {
          v33 = 0;
          v40 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"Windows.Internal.StateRepository.PackageLocation",
            0x31u,
            0x30u);
          v14 = v40;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
          ActivationFactory = RoGetActivationFactory(v14, &GUID_b8c8be3c_3a39_4e73_b4ba_c70d91d1b8ea, &v33);
          v5 = ActivationFactory;
          if ( ActivationFactory >= 0 )
          {
            v34 = 0;
            v16 = v33;
            v17 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v33 + 96LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
            v18 = v17(v16, v32, &v34);
            v5 = v18;
            if ( v18 >= 0 )
            {
              string = 0;
              v19 = v34;
              v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 88LL);
              WindowsDeleteString(0);
              string = 0;
              v21 = v20(v19, &string);
              v5 = v21;
              if ( v21 >= 0 )
              {
                v30 = 0;
                v22 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IAppExtension *, HSTRING *))(*(_QWORD *)a1 + 88LL);
                WindowsDeleteString(0);
                v30 = 0;
                v23 = v22(a1, &v30);
                v5 = v23;
                if ( v23 >= 0 )
                {
                  v36 = 0;
                  v37 = 0;
                  v38[1] = &v36;
                  v38[0] = &Common::StringBufferBuilder::`vftable';
                  v38[2] = &v36;
                  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                  appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v38, StringRawBuffer);
                  v5 = appended;
                  if ( appended >= 0 )
                  {
                    appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v38, L"\\");
                    v5 = appended;
                    if ( appended >= 0 )
                    {
                      v27 = WindowsGetStringRawBuffer(v30, 0);
                      appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v38, v27);
                      v5 = appended;
                      if ( appended >= 0 )
                      {
                        appended = CreateStorageItemFromPath_PartialTrustCaller(
                                     *((_QWORD *)&v36 + 1),
                                     64,
                                     &GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b,
                                     a2);
                        v5 = appended;
                        if ( appended >= 0 )
                        {
                          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v36);
                          WindowsDeleteString(v30);
                          v30 = 0;
                          WindowsDeleteString(string);
                          string = 0;
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
                          v5 = 0;
                          goto LABEL_36;
                        }
                        v26 = 654;
                      }
                      else
                      {
                        v26 = 652;
                      }
                    }
                    else
                    {
                      v26 = 651;
                    }
                  }
                  else
                  {
                    v26 = 650;
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v26,
                    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\theme"
                                  "appmodelwrapper.cpp",
                    (const char *)(unsigned int)appended,
                    (int)string);
                  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v36);
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x284,
                    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\theme"
                                  "appmodelwrapper.cpp",
                    (const char *)(unsigned int)v23,
                    (int)string);
                }
                WindowsDeleteString(v30);
                v30 = 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x280,
                  (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeap"
                                "pmodelwrapper.cpp",
                  (const char *)(unsigned int)v21,
                  (int)string);
              }
              WindowsDeleteString(string);
              string = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x27E,
                (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
                (const char *)(unsigned int)v18,
                (int)string);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x27C,
              (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
              (const char *)(unsigned int)ActivationFactory,
              (int)string);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x278,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
            (const char *)(unsigned int)v13,
            (int)string);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x276,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
          (const char *)(unsigned int)v10,
          (int)string);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x274,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
        (const char *)(unsigned int)v7,
        (int)string);
    }
LABEL_36:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    return v5;
  }
  v4 = 622;
LABEL_3:
  v5 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
    (const char *)0x80070057LL,
    (int)string);
  return v5;
}

```

## disassembly

```asm
0x18026aba4  mov     [rsp-8+arg_10], rbx
0x18026aba9  push    rbp
0x18026abaa  push    rsi
0x18026abab  push    rdi
0x18026abac  push    r14
0x18026abae  push    r15
0x18026abb0  lea     rbp, [rsp-37h]
0x18026abb5  sub     rsp, 0B0h
0x18026abbc  mov     rax, cs:__security_cookie
0x18026abc3  xor     rax, rsp
0x18026abc6  mov     [rbp+57h+var_28], rax
0x18026abca  mov     r14, rdx
0x18026abcd  mov     rsi, rcx
0x18026abd0  xor     r15d, r15d
0x18026abd3  test    rcx, rcx
0x18026abd6  jnz     short loc_18026ABFA
0x18026abd8  mov     edx, 26Eh; void *
0x18026abdd  mov     ebx, 80070057h
0x18026abe2  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026abe9  mov     r9d, ebx; char *
0x18026abec  mov     rcx, [rbp+5Fh]; this
0x18026abf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026abf5  jmp     loc_18026AFD2
0x18026abfa  test    r14, r14
0x18026abfd  jnz     short loc_18026AC06
0x18026abff  mov     edx, 26Fh
0x18026ac04  jmp     short loc_18026ABDD
0x18026ac06  mov     [rdx], r15
0x18026ac09  mov     [rbp+57h+var_80], r15
0x18026ac0d  mov     rax, [rcx]
0x18026ac10  mov     rbx, [rax+88h]
0x18026ac17  lea     rcx, [rbp+57h+var_80]
0x18026ac1b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026ac20  lea     rdx, [rbp+57h+var_80]
0x18026ac24  mov     rcx, rsi
0x18026ac27  mov     rax, rbx
0x18026ac2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ac2f  mov     ebx, eax
0x18026ac31  test    eax, eax
0x18026ac33  jns     short loc_18026AC52
0x18026ac35  mov     rcx, [rbp+5Fh]; this
0x18026ac39  mov     r9d, eax; char *
0x18026ac3c  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026ac43  mov     edx, 274h; void *
0x18026ac48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ac4d  jmp     loc_18026AFC9
0x18026ac52  mov     [rbp+57h+var_A0], r15
0x18026ac56  mov     rdi, [rbp+57h+var_80]
0x18026ac5a  mov     rax, [rdi]
0x18026ac5d  mov     rbx, [rax+48h]
0x18026ac61  lea     rcx, [rbp+57h+var_A0]
0x18026ac65  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026ac6a  lea     rdx, [rbp+57h+var_A0]
0x18026ac6e  mov     rcx, rdi
0x18026ac71  mov     rax, rbx
0x18026ac74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ac79  mov     ebx, eax
0x18026ac7b  test    eax, eax
0x18026ac7d  jns     short loc_18026ACA6
0x18026ac7f  mov     rcx, [rbp+5Fh]; this
0x18026ac83  mov     r9d, eax; char *
0x18026ac86  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026ac8d  mov     edx, 276h; void *
0x18026ac92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ac97  nop
0x18026ac98  lea     rcx, [rbp+57h+var_A0]
0x18026ac9c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026aca1  jmp     loc_18026AFC9
0x18026aca6  mov     [rbp+57h+var_98], r15
0x18026acaa  mov     rdi, [rbp+57h+var_A0]
0x18026acae  mov     rax, [rdi]
0x18026acb1  mov     rbx, [rax+48h]
0x18026acb5  lea     rcx, [rbp+57h+var_98]
0x18026acb9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026acbe  lea     rdx, [rbp+57h+var_98]
0x18026acc2  mov     rcx, rdi
0x18026acc5  mov     rax, rbx
0x18026acc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026accd  mov     ebx, eax
0x18026accf  test    eax, eax
0x18026acd1  jns     short loc_18026ACF7
0x18026acd3  mov     rcx, [rbp+5Fh]; this
0x18026acd7  mov     r9d, eax; char *
0x18026acda  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026ace1  mov     edx, 278h; void *
0x18026ace6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026aceb  nop
0x18026acec  lea     rcx, [rbp+57h+var_98]
0x18026acf0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026acf5  jmp     short loc_18026AC98
0x18026acf7  mov     [rbp+57h+var_90], r15
0x18026acfb  mov     [rbp+57h+var_30], r15
0x18026acff  mov     r9d, 30h ; '0'; unsigned int
0x18026ad05  lea     r8d, [r9+1]; unsigned int
0x18026ad09  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageLocation@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18026ad10  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18026ad14  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18026ad19  mov     rbx, [rbp+57h+var_30]
0x18026ad1d  lea     rcx, [rbp+57h+var_90]
0x18026ad21  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026ad26  lea     r8, [rbp+57h+var_90]
0x18026ad2a  lea     rdx, _GUID_b8c8be3c_3a39_4e73_b4ba_c70d91d1b8ea
0x18026ad31  mov     rcx, rbx
0x18026ad34  call    cs:__imp_RoGetActivationFactory
0x18026ad3b  nop     dword ptr [rax+rax+00h]
0x18026ad40  mov     ebx, eax
0x18026ad42  test    eax, eax
0x18026ad44  jns     short loc_18026AD6A
0x18026ad46  mov     rcx, [rbp+5Fh]; this
0x18026ad4a  mov     r9d, eax; char *
0x18026ad4d  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026ad54  mov     edx, 27Ch; void *
0x18026ad59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ad5e  nop
0x18026ad5f  lea     rcx, [rbp+57h+var_90]
0x18026ad63  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026ad68  jmp     short loc_18026ACEC
0x18026ad6a  mov     [rbp+57h+var_88], r15
0x18026ad6e  mov     rdi, [rbp+57h+var_90]
0x18026ad72  mov     rax, [rdi]
0x18026ad75  mov     rbx, [rax+60h]
0x18026ad79  lea     rcx, [rbp+57h+var_88]
0x18026ad7d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026ad82  lea     r8, [rbp+57h+var_88]
0x18026ad86  mov     rdx, [rbp+57h+var_98]
0x18026ad8a  mov     rcx, rdi
0x18026ad8d  mov     rax, rbx
0x18026ad90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ad95  mov     ebx, eax
0x18026ad97  test    eax, eax
0x18026ad99  jns     short loc_18026ADBF
0x18026ad9b  mov     rcx, [rbp+5Fh]; this
0x18026ad9f  mov     r9d, eax; char *
0x18026ada2  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026ada9  mov     edx, 27Eh; void *
0x18026adae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026adb3  nop
0x18026adb4  lea     rcx, [rbp+57h+var_88]
0x18026adb8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026adbd  jmp     short loc_18026AD5F
0x18026adbf  mov     [rbp+57h+string], r15
0x18026adc3  mov     rdi, [rbp+57h+var_88]
0x18026adc7  mov     rax, [rdi]
0x18026adca  mov     rbx, [rax+58h]
0x18026adce  xor     ecx, ecx; string
0x18026add0  call    cs:__imp_WindowsDeleteString
0x18026add7  nop     dword ptr [rax+rax+00h]
0x18026addc  mov     [rbp+57h+string], r15
0x18026ade0  lea     rdx, [rbp+57h+string]
0x18026ade4  mov     rcx, rdi
0x18026ade7  mov     rax, rbx
0x18026adea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026adef  mov     ebx, eax
0x18026adf1  test    eax, eax
0x18026adf3  jns     short loc_18026AE24
0x18026adf5  mov     rcx, [rbp+5Fh]; this
0x18026adf9  mov     r9d, eax; char *
0x18026adfc  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026ae03  mov     edx, 280h; void *
0x18026ae08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ae0d  nop
0x18026ae0e  mov     rcx, [rbp+57h+string]; string
0x18026ae12  call    cs:__imp_WindowsDeleteString
0x18026ae19  nop     dword ptr [rax+rax+00h]
0x18026ae1e  mov     [rbp+57h+string], r15
0x18026ae22  jmp     short loc_18026ADB4
0x18026ae24  mov     [rbp+57h+var_A8], r15
0x18026ae28  mov     rax, [rsi]
0x18026ae2b  mov     rbx, [rax+58h]
0x18026ae2f  xor     ecx, ecx; string
0x18026ae31  call    cs:__imp_WindowsDeleteString
0x18026ae38  nop     dword ptr [rax+rax+00h]
0x18026ae3d  mov     [rbp+57h+var_A8], r15
0x18026ae41  lea     rdx, [rbp+57h+var_A8]
0x18026ae45  mov     rcx, rsi
0x18026ae48  mov     rax, rbx
0x18026ae4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ae50  mov     ebx, eax
0x18026ae52  test    eax, eax
0x18026ae54  jns     short loc_18026AE85
0x18026ae56  mov     rcx, [rbp+5Fh]; this
0x18026ae5a  mov     r9d, eax; char *
0x18026ae5d  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026ae64  mov     edx, 284h; void *
0x18026ae69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ae6e  nop
0x18026ae6f  mov     rcx, [rbp+57h+var_A8]; string
0x18026ae73  call    cs:__imp_WindowsDeleteString
0x18026ae7a  nop     dword ptr [rax+rax+00h]
0x18026ae7f  mov     [rbp+57h+var_A8], r15
0x18026ae83  jmp     short loc_18026AE0E
0x18026ae85  xorps   xmm0, xmm0
0x18026ae88  movups  [rbp+57h+var_78], xmm0
0x18026ae8c  mov     [rbp+57h+var_68], r15d
0x18026ae90  lea     rax, [rbp+57h+var_78]
0x18026ae94  mov     [rbp+57h+var_58], rax
0x18026ae98  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x18026ae9f  mov     [rbp+57h+var_60], rax
0x18026aea3  lea     rax, [rbp+57h+var_78]
0x18026aea7  mov     [rbp+57h+var_50], rax
0x18026aeab  xor     edx, edx; length
0x18026aead  mov     rcx, [rbp+57h+string]; string
0x18026aeb1  call    cs:__imp_WindowsGetStringRawBuffer
0x18026aeb8  nop     dword ptr [rax+rax+00h]
0x18026aebd  mov     rdx, rax; unsigned __int16 *
0x18026aec0  lea     rcx, [rbp+57h+var_60]; this
0x18026aec4  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18026aec9  mov     ebx, eax
0x18026aecb  test    eax, eax
0x18026aecd  jns     short loc_18026AEF6
0x18026aecf  mov     edx, 28Ah; void *
0x18026aed4  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026aedb  mov     r9d, eax; char *
0x18026aede  mov     rcx, [rbp+5Fh]; this
0x18026aee2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026aee7  nop
0x18026aee8  lea     rcx, [rbp+57h+var_78]; this
0x18026aeec  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18026aef1  jmp     loc_18026AE6F
0x18026aef6  lea     rdx, Control; "\\"
0x18026aefd  lea     rcx, [rbp+57h+var_60]; this
0x18026af01  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18026af06  mov     ebx, eax
0x18026af08  test    eax, eax
0x18026af0a  jns     short loc_18026AF13
0x18026af0c  mov     edx, 28Bh
0x18026af11  jmp     short loc_18026AED4
0x18026af13  xor     edx, edx; length
0x18026af15  mov     rcx, [rbp+57h+var_A8]; string
0x18026af19  call    cs:__imp_WindowsGetStringRawBuffer
0x18026af20  nop     dword ptr [rax+rax+00h]
0x18026af25  mov     rdx, rax; unsigned __int16 *
0x18026af28  lea     rcx, [rbp+57h+var_60]; this
0x18026af2c  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18026af31  mov     ebx, eax
0x18026af33  test    eax, eax
0x18026af35  jns     short loc_18026AF3E
0x18026af37  mov     edx, 28Ch
0x18026af3c  jmp     short loc_18026AED4
0x18026af3e  mov     r9, r14
0x18026af41  lea     r8, _GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b
0x18026af48  mov     edx, 40h ; '@'
0x18026af4d  mov     rcx, qword ptr [rbp+57h+var_78+8]
0x18026af51  call    cs:__imp_CreateStorageItemFromPath_PartialTrustCaller
0x18026af58  nop     dword ptr [rax+rax+00h]
0x18026af5d  mov     ebx, eax
0x18026af5f  test    eax, eax
0x18026af61  jns     short loc_18026AF6D
0x18026af63  mov     edx, 28Eh
0x18026af68  jmp     loc_18026AED4
0x18026af6d  lea     rcx, [rbp+57h+var_78]; this
0x18026af71  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18026af76  nop
0x18026af77  mov     rcx, [rbp+57h+var_A8]; string
0x18026af7b  call    cs:__imp_WindowsDeleteString
0x18026af82  nop     dword ptr [rax+rax+00h]
0x18026af87  mov     [rbp+57h+var_A8], r15
0x18026af8b  mov     rcx, [rbp+57h+string]; string
0x18026af8f  call    cs:__imp_WindowsDeleteString
0x18026af96  nop     dword ptr [rax+rax+00h]
0x18026af9b  mov     [rbp+57h+string], r15
0x18026af9f  lea     rcx, [rbp+57h+var_88]
0x18026afa3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026afa8  nop
0x18026afa9  lea     rcx, [rbp+57h+var_90]
0x18026afad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026afb2  nop
0x18026afb3  lea     rcx, [rbp+57h+var_98]
0x18026afb7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026afbc  nop
0x18026afbd  lea     rcx, [rbp+57h+var_A0]
0x18026afc1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026afc6  mov     ebx, r15d
0x18026afc9  lea     rcx, [rbp+57h+var_80]
0x18026afcd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026afd2  mov     eax, ebx
0x18026afd4  mov     rcx, [rbp+57h+var_28]
0x18026afd8  xor     rcx, rsp; StackCookie
0x18026afdb  call    __security_check_cookie
0x18026afe0  mov     rbx, [rsp+0D0h+arg_10]
0x18026afe8  add     rsp, 0B0h
0x18026afef  pop     r15
0x18026aff1  pop     r14
0x18026aff3  pop     rdi
0x18026aff4  pop     rsi
0x18026aff5  pop     rbp
0x18026aff6  retn
```
