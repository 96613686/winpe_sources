# StoreAppProvider::GetExists(ushort const *,ushort * *)

- ea: `0x180054aa8`
- end: `0x1800550ff`
- name: `?GetExists@StoreAppProvider@@CAJPEBGPEAPEAG@Z`
- size: `1623`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180049b00`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x18001d244`
- `0x18001ec78`
- `0x1800549bc`
- `0x180054a08`
- `0x180054aa8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054ccd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054d5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054ec4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054f46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054fc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054ccd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054d5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054ec4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054f46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054fc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054d02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054d02`

## string_xrefs

- `0x180054b04`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x180054b3e`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x180054b94`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x180054c04`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x180054dff`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x180054ea4`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x180054fb1`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x18005502f`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x18005509f`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall StoreAppProvider::GetExists(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  int v20; // eax
  PCWSTR StringRawBuffer; // rax
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rcx
  unsigned __int16 *v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  int v40; // [rsp+20h] [rbp-59h] BYREF
  __int64 v41; // [rsp+28h] [rbp-51h] BYREF
  __int64 v42; // [rsp+30h] [rbp-49h] BYREF
  HSTRING string; // [rsp+38h] [rbp-41h] BYREF
  __int64 v44; // [rsp+40h] [rbp-39h] BYREF
  __int64 v45; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v46; // [rsp+50h] [rbp-29h] BYREF
  __int64 v47; // [rsp+58h] [rbp-21h]
  __int64 v48; // [rsp+60h] [rbp-19h]
  __int64 v49; // [rsp+68h] [rbp-11h] BYREF
  HSTRING v50[3]; // [rsp+70h] [rbp-9h] BYREF
  HSTRING v51; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v49 = 0;
  Windows::Internal::StringReference::StringReference(&v51, (const unsigned __int16 (*)[45])a2);
  v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(
         (__int64)v51,
         &v49);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v42 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49 + 88LL))(v49, &v42);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v41 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 48LL))(v42, &v41);
      v5 = v8;
      if ( v8 >= 0 )
      {
        LOBYTE(v40) = 0;
        v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 56LL))(v41, &v40);
        v5 = v11;
        if ( v11 >= 0 )
        {
          v46 = 0;
          v47 = 0;
          v48 = 0;
          if ( (_BYTE)v40 )
          {
            while ( 1 )
            {
              v45 = 0;
              v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 48LL))(v41, &v45);
              v5 = v14;
              if ( v14 < 0 )
                break;
              v44 = 0;
              v15 = v45;
              v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 48LL);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
              v17 = v16(v15, &v44);
              v5 = v17;
              if ( v17 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x60,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
                  (const char *)(unsigned int)v17,
                  v40);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v46);
                v36 = v41;
                if ( v41 )
                {
                  v41 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                }
                v37 = v42;
                if ( v42 )
                {
                  v42 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                }
                goto LABEL_31;
              }
              string = 0;
              v18 = v44;
              v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v44 + 48LL);
              WindowsDeleteString(0);
              string = 0;
              v20 = v19(v18, &string);
              v5 = v20;
              if ( v20 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x63,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
                  (const char *)(unsigned int)v20,
                  v40);
                WindowsDeleteString(string);
                string = 0;
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v46);
                v34 = v41;
                if ( v41 )
                {
                  v41 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                }
                v35 = v42;
                if ( v42 )
                {
                  v42 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                }
                goto LABEL_31;
              }
              memset(v50, 0, sizeof(v50));
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                v50,
                StringRawBuffer,
                -1);
              if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                                   v50,
                                   a1,
                                   -1) == 2 )
              {
                v28 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                        &v46,
                        L"1",
                        -1);
                v5 = v28;
                if ( v28 >= 0 )
                {
                  v31 = v46;
                  v46 = 0;
                  v48 = 0;
                  v47 = 0;
                  *a2 = v31;
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v50);
                  WindowsDeleteString(string);
                  string = 0;
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v46);
                  v32 = v41;
                  if ( v41 )
                  {
                    v41 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                  }
                  v33 = v42;
                  if ( v42 )
                  {
                    v42 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                  }
                  v5 = 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x6A,
                    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
                    (const char *)(unsigned int)v28,
                    v40);
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v50);
                  WindowsDeleteString(string);
                  string = 0;
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v46);
                  v29 = v41;
                  if ( v41 )
                  {
                    v41 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                  }
                  v30 = v42;
                  if ( v42 )
                  {
                    v42 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                  }
                }
                goto LABEL_31;
              }
              v22 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 64LL))(v41, &v40);
              v5 = v22;
              if ( v22 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x6F,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
                  (const char *)(unsigned int)v22,
                  v40);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v50);
                WindowsDeleteString(string);
                string = 0;
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v46);
                v26 = v41;
                if ( v41 )
                {
                  v41 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                }
                v27 = v42;
                if ( v42 )
                {
                  v42 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
                }
                goto LABEL_31;
              }
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v50);
              WindowsDeleteString(string);
              string = 0;
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
              if ( !(_BYTE)v40 )
                goto LABEL_26;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5D,
              (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
              (const char *)(unsigned int)v14,
              v40);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v46);
            v38 = v41;
            if ( v41 )
            {
              v41 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
            }
            v39 = v42;
            if ( v42 )
            {
              v42 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
            }
          }
          else
          {
LABEL_26:
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v46);
            v23 = v41;
            if ( v41 )
            {
              v41 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            }
            v24 = v42;
            if ( v42 )
            {
              v42 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
            }
            v5 = -2147024894;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x56,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
            (const char *)(unsigned int)v11,
            v40);
          v12 = v41;
          if ( v41 )
          {
            v41 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          }
          v13 = v42;
          if ( v42 )
          {
            v42 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x53,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
          (const char *)(unsigned int)v8,
          v40);
        v9 = v41;
        if ( v41 )
        {
          v41 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        v10 = v42;
        if ( v42 )
        {
          v42 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
        (const char *)(unsigned int)v6,
        v40);
      v7 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
      (const char *)(unsigned int)v4,
      v40);
  }
LABEL_31:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
  return v5;
}

```

## disassembly

```asm
0x180054aa8  mov     [rsp-8+arg_10], rbx
0x180054aad  mov     [rsp-8+arg_18], rsi
0x180054ab2  push    rbp
0x180054ab3  push    rdi
0x180054ab4  push    r12
0x180054ab6  push    r14
0x180054ab8  push    r15
0x180054aba  lea     rbp, [rsp-37h]
0x180054abf  sub     rsp, 0B0h
0x180054ac6  mov     rax, cs:__security_cookie
0x180054acd  xor     rax, rsp
0x180054ad0  mov     [rbp+57h+var_28], rax
0x180054ad4  mov     rsi, rdx
0x180054ad7  mov     r14, rcx
0x180054ada  xor     r15d, r15d
0x180054add  mov     [rbp+57h+var_68], r15
0x180054ae1  lea     rcx, [rbp+57h+var_48]; string
0x180054ae5  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x180054aea  lea     rdx, [rbp+57h+var_68]
0x180054aee  mov     rcx, [rbp+57h+var_48]
0x180054af2  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>)
0x180054af7  mov     ebx, eax
0x180054af9  test    eax, eax
0x180054afb  jns     short loc_180054B19
0x180054afd  mov     rcx, [rbp+5Fh]; this
0x180054b01  mov     r9d, eax; char *
0x180054b04  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\flightsetting"...
0x180054b0b  lea     edx, [r15+4Dh]; void *
0x180054b0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054b14  jmp     loc_180054DC5
0x180054b19  mov     [rbp+57h+var_A0], r15
0x180054b1d  mov     rcx, [rbp+57h+var_68]
0x180054b21  mov     rax, [rcx]
0x180054b24  lea     rdx, [rbp+57h+var_A0]
0x180054b28  mov     rax, [rax+58h]
0x180054b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b31  mov     ebx, eax
0x180054b33  test    eax, eax
0x180054b35  jns     short loc_180054B6F
0x180054b37  mov     rcx, [rbp+5Fh]; this
0x180054b3b  mov     r9d, eax; char *
0x180054b3e  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\flightsetting"...
0x180054b45  mov     edx, 50h ; 'P'; void *
0x180054b4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054b4f  nop
0x180054b50  mov     rcx, [rbp+57h+var_A0]
0x180054b54  test    rcx, rcx
0x180054b57  jz      short loc_180054B6A
0x180054b59  mov     [rbp+57h+var_A0], r15
0x180054b5d  mov     rax, [rcx]
0x180054b60  mov     rax, [rax+10h]
0x180054b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b69  nop
0x180054b6a  jmp     loc_180054DC5
0x180054b6f  mov     [rbp+57h+var_A8], r15
0x180054b73  mov     rcx, [rbp+57h+var_A0]
0x180054b77  mov     rax, [rcx]
0x180054b7a  lea     rdx, [rbp+57h+var_A8]
0x180054b7e  mov     rax, [rax+30h]
0x180054b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b87  mov     ebx, eax
0x180054b89  test    eax, eax
0x180054b8b  jns     short loc_180054BDF
0x180054b8d  mov     rcx, [rbp+5Fh]; this
0x180054b91  mov     r9d, eax; char *
0x180054b94  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\flightsetting"...
0x180054b9b  mov     edx, 53h ; 'S'; void *
0x180054ba0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054ba5  nop
0x180054ba6  mov     rcx, [rbp+57h+var_A8]
0x180054baa  test    rcx, rcx
0x180054bad  jz      short loc_180054BC0
0x180054baf  mov     [rbp+57h+var_A8], r15
0x180054bb3  mov     rax, [rcx]
0x180054bb6  mov     rax, [rax+10h]
0x180054bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bbf  nop
0x180054bc0  mov     rcx, [rbp+57h+var_A0]
0x180054bc4  test    rcx, rcx
0x180054bc7  jz      short loc_180054BDA
0x180054bc9  mov     [rbp+57h+var_A0], r15
0x180054bcd  mov     rax, [rcx]
0x180054bd0  mov     rax, [rax+10h]
0x180054bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bd9  nop
0x180054bda  jmp     loc_180054DC5
0x180054bdf  mov     byte ptr [rbp+57h+var_B0], r15b
0x180054be3  mov     rcx, [rbp+57h+var_A8]
0x180054be7  mov     rax, [rcx]
0x180054bea  lea     rdx, [rbp+57h+var_B0]
0x180054bee  mov     rax, [rax+38h]
0x180054bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bf7  mov     ebx, eax
0x180054bf9  test    eax, eax
0x180054bfb  jns     short loc_180054C4F
0x180054bfd  mov     rcx, [rbp+5Fh]; this
0x180054c01  mov     r9d, eax; char *
0x180054c04  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\flightsetting"...
0x180054c0b  mov     edx, 56h ; 'V'; void *
0x180054c10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054c15  nop
0x180054c16  mov     rcx, [rbp+57h+var_A8]
0x180054c1a  test    rcx, rcx
0x180054c1d  jz      short loc_180054C30
0x180054c1f  mov     [rbp+57h+var_A8], r15
0x180054c23  mov     rax, [rcx]
0x180054c26  mov     rax, [rax+10h]
0x180054c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c2f  nop
0x180054c30  mov     rcx, [rbp+57h+var_A0]
0x180054c34  test    rcx, rcx
0x180054c37  jz      short loc_180054C4A
0x180054c39  mov     [rbp+57h+var_A0], r15
0x180054c3d  mov     rax, [rcx]
0x180054c40  mov     rax, [rax+10h]
0x180054c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c49  nop
0x180054c4a  jmp     loc_180054DC5
0x180054c4f  mov     [rbp+57h+var_80], r15
0x180054c53  mov     [rbp+57h+var_78], r15
0x180054c57  mov     [rbp+57h+var_70], r15
0x180054c5b  cmp     byte ptr [rbp+57h+var_B0], r15b
0x180054c5f  jz      loc_180054D82
0x180054c65  or      r12, 0FFFFFFFFFFFFFFFFh
0x180054c69  mov     [rbp+57h+var_88], r15
0x180054c6d  mov     rcx, [rbp+57h+var_A8]
0x180054c71  mov     rax, [rcx]
0x180054c74  lea     rdx, [rbp+57h+var_88]
0x180054c78  mov     rax, [rax+30h]
0x180054c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c81  mov     ebx, eax
0x180054c83  test    eax, eax
0x180054c85  js      loc_180055098
0x180054c8b  mov     [rbp+57h+var_90], r15
0x180054c8f  mov     rdi, [rbp+57h+var_88]
0x180054c93  mov     rax, [rdi]
0x180054c96  mov     rbx, [rax+30h]
0x180054c9a  lea     rcx, [rbp+57h+var_90]
0x180054c9e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180054ca3  lea     rdx, [rbp+57h+var_90]
0x180054ca7  mov     rcx, rdi
0x180054caa  mov     rax, rbx
0x180054cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054cb2  mov     ebx, eax
0x180054cb4  test    eax, eax
0x180054cb6  js      loc_180055028
0x180054cbc  mov     [rbp+57h+string], r15
0x180054cc0  mov     rdi, [rbp+57h+var_90]
0x180054cc4  mov     rax, [rdi]
0x180054cc7  mov     rbx, [rax+30h]
0x180054ccb  xor     ecx, ecx; string
0x180054ccd  call    cs:__imp_WindowsDeleteString
0x180054cd3  mov     [rbp+57h+string], r15
0x180054cd7  lea     rdx, [rbp+57h+string]
0x180054cdb  mov     rcx, rdi
0x180054cde  mov     rax, rbx
0x180054ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ce6  mov     ebx, eax
0x180054ce8  test    eax, eax
0x180054cea  js      loc_180054FAA
0x180054cf0  mov     [rbp+57h+var_60], r15
0x180054cf4  mov     [rbp+57h+var_58], r15
0x180054cf8  mov     [rbp+57h+var_50], r15
0x180054cfc  xor     edx, edx; length
0x180054cfe  mov     rcx, [rbp+57h+string]; string
0x180054d02  call    cs:__imp_WindowsGetStringRawBuffer
0x180054d08  mov     r8, r12
0x180054d0b  mov     rdx, rax
0x180054d0e  lea     rcx, [rbp+57h+var_60]
0x180054d12  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180054d17  mov     r8, r12
0x180054d1a  mov     rdx, r14
0x180054d1d  lea     rcx, [rbp+57h+var_60]
0x180054d21  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x180054d26  cmp     eax, 2
0x180054d29  jz      loc_180054E80
0x180054d2f  mov     rcx, [rbp+57h+var_A8]
0x180054d33  mov     rax, [rcx]
0x180054d36  lea     rdx, [rbp+57h+var_B0]
0x180054d3a  mov     rax, [rax+40h]
0x180054d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054d43  mov     ebx, eax
0x180054d45  test    eax, eax
0x180054d47  js      loc_180054DF8
0x180054d4d  lea     rcx, [rbp+57h+var_60]
0x180054d51  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180054d56  nop
0x180054d57  mov     rcx, [rbp+57h+string]; string
0x180054d5b  call    cs:__imp_WindowsDeleteString
0x180054d61  mov     [rbp+57h+string], r15
0x180054d65  lea     rcx, [rbp+57h+var_90]
0x180054d69  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180054d6e  nop
0x180054d6f  lea     rcx, [rbp+57h+var_88]
0x180054d73  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180054d78  cmp     byte ptr [rbp+57h+var_B0], r15b
0x180054d7c  jnz     loc_180054C69
0x180054d82  lea     rcx, [rbp+57h+var_80]
0x180054d86  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180054d8b  nop
0x180054d8c  mov     rcx, [rbp+57h+var_A8]
0x180054d90  test    rcx, rcx
0x180054d93  jz      short loc_180054DA6
0x180054d95  mov     [rbp+57h+var_A8], r15
0x180054d99  mov     rax, [rcx]
0x180054d9c  mov     rax, [rax+10h]
0x180054da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054da5  nop
0x180054da6  mov     rcx, [rbp+57h+var_A0]
0x180054daa  test    rcx, rcx
0x180054dad  jz      short loc_180054DC0
0x180054daf  mov     [rbp+57h+var_A0], r15
0x180054db3  mov     rax, [rcx]
0x180054db6  mov     rax, [rax+10h]
0x180054dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054dbf  nop
0x180054dc0  mov     ebx, 80070002h
0x180054dc5  lea     rcx, [rbp+57h+var_68]
0x180054dc9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180054dce  mov     eax, ebx
0x180054dd0  mov     rcx, [rbp+57h+var_28]
0x180054dd4  xor     rcx, rsp; StackCookie
0x180054dd7  call    __security_check_cookie
0x180054ddc  lea     r11, [rsp+0D0h+var_20]
0x180054de4  mov     rbx, [r11+40h]
0x180054de8  mov     rsi, [r11+48h]
0x180054dec  mov     rsp, r11
0x180054def  pop     r15
0x180054df1  pop     r14
0x180054df3  pop     r12
0x180054df5  pop     rdi
0x180054df6  pop     rbp
0x180054df7  retn
0x180054df8  mov     rcx, [rbp+5Fh]; this
0x180054dfc  mov     r9d, eax; char *
0x180054dff  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\flightsetting"...
0x180054e06  mov     edx, 6Fh ; 'o'; void *
0x180054e0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054e10  nop
0x180054e11  lea     rcx, [rbp+57h+var_60]
0x180054e15  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180054e1a  nop
0x180054e1b  mov     rcx, [rbp+57h+string]; string
0x180054e1f  call    cs:__imp_WindowsDeleteString
0x180054e25  mov     [rbp+57h+string], r15
0x180054e29  lea     rcx, [rbp+57h+var_90]
0x180054e2d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180054e32  nop
0x180054e33  lea     rcx, [rbp+57h+var_88]
0x180054e37  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180054e3c  nop
0x180054e3d  lea     rcx, [rbp+57h+var_80]
0x180054e41  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180054e46  nop
0x180054e47  mov     rcx, [rbp+57h+var_A8]
0x180054e4b  test    rcx, rcx
0x180054e4e  jz      short loc_180054E61
0x180054e50  mov     [rbp+57h+var_A8], r15
0x180054e54  mov     rax, [rcx]
0x180054e57  mov     rax, [rax+10h]
0x180054e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e60  nop
0x180054e61  mov     rcx, [rbp+57h+var_A0]
0x180054e65  test    rcx, rcx
0x180054e68  jz      short loc_180054E7B
0x180054e6a  mov     [rbp+57h+var_A0], r15
0x180054e6e  mov     rax, [rcx]
0x180054e71  mov     rax, [rax+10h]
0x180054e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e7a  nop
0x180054e7b  jmp     loc_180054DC5
0x180054e80  mov     r8, r12
0x180054e83  lea     rdx, a1; "1"
0x180054e8a  lea     rcx, [rbp+57h+var_80]
0x180054e8e  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180054e93  mov     ebx, eax
0x180054e95  test    eax, eax
0x180054e97  jns     loc_180054F25
0x180054e9d  mov     rcx, [rbp+5Fh]; this
0x180054ea1  mov     r9d, eax; char *
0x180054ea4  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\flightsetting"...
0x180054eab  mov     edx, 6Ah ; 'j'; void *
0x180054eb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054eb5  nop
0x180054eb6  lea     rcx, [rbp+57h+var_60]
0x180054eba  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180054ebf  nop
0x180054ec0  mov     rcx, [rbp+57h+string]; string
0x180054ec4  call    cs:__imp_WindowsDeleteString
0x180054eca  mov     [rbp+57h+string], r15
0x180054ece  lea     rcx, [rbp+57h+var_90]
0x180054ed2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180054ed7  nop
0x180054ed8  lea     rcx, [rbp+57h+var_88]
0x180054edc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180054ee1  nop
0x180054ee2  lea     rcx, [rbp+57h+var_80]
0x180054ee6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180054eeb  nop
0x180054eec  mov     rcx, [rbp+57h+var_A8]
  ... truncated ...
```
