# _lambda_471a3c324b82b50dfe5e1297adafe4ed_::operator()

- ea: `0x18042d6b8`
- end: `0x18042da6d`
- name: `_lambda_471a3c324b82b50dfe5e1297adafe4ed_::operator()`
- size: `949`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1804314b0`

## callees

- `0x18000d6cc`
- `0x180010110`
- `0x1800432f0`
- `0x18007153c`
- `0x180071568`
- `0x1800c4bc8`
- `0x1800c6184`
- `0x18014c7f0`
- `0x1801c2e38`
- `0x1802856f4`
- `0x1803a4cb0`
- `0x1803ed984`
- `0x18042aba0`
- `0x18042d6b8`
- `0x180432f70`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x18042d712`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x18042d712`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18042d709`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18042d736`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18042d75c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18042d796`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18042d709`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18042d736`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18042d75c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18042d796`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042d853`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042d891`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042d8df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042d93b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042d9c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042da2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042d853`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042d891`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042d8df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042d93b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042d9c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042da2c`

## string_xrefs

- `0x18042d6f2`: `s_ReadAllTextAsync.MakeAsyncOperation`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall lambda_471a3c324b82b50dfe5e1297adafe4ed_::operator()(__int64 a1, HSTRING *a2, __int64 a3)
{
  const WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v6; // rax
  const struct _GUID *v7; // rdx
  const unsigned __int16 *v8; // rax
  const struct _GUID *v9; // rdx
  unsigned int StorageItemFromPathOrMsUri_PartialTrustCaller; // eax
  const unsigned __int16 *v11; // rax
  const struct _GUID *v12; // rdx
  int v13; // eax
  unsigned int v14; // ebx
  unsigned int AllTextUsingFileAsync; // eax
  int v16; // eax
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // rbx
  int v20; // eax
  __int64 v21; // rbx
  int v22; // eax
  int EntireFileIntoDataReaderSync; // eax
  int AllTextSync; // eax
  int v25; // eax
  unsigned int v27[4]; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING v28[2]; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v30; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v31[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v32[192]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  *(_OWORD *)v28 = *(_OWORD *)(a1 + 24);
  LOBYTE(a3) = 1;
  WinRTStorageTelemetry::WatchCurrentThread(v32, "s_ReadAllTextAsync.MakeAsyncOperation", a3, v28);
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)a1, 0);
  if ( PathIsURLW(StringRawBuffer) )
  {
    v30 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    v6 = WindowsGetStringRawBuffer(*(HSTRING *)a1, 0);
    if ( (int)CreateStorageItemFromPathOrMsUri_PartialTrustCaller(v6, v7, (void **)&v30) >= 0 )
    {
      *(_QWORD *)v27 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
      if ( (int)CFileIOStatics::s_ReadAllTextUsingFileAsync(
                  v30,
                  *(unsigned int *)(a1 + 16),
                  *(unsigned int *)(a1 + 20),
                  v27) >= 0 )
      {
        string = 0;
        WindowsDeleteString(0);
        string = 0;
        v17 = *(_QWORD *)v27;
        v18 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(*(_QWORD *)v27);
        if ( v18 >= 0 )
          v18 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 64LL))(v17, &string);
        if ( v18 >= 0 )
        {
          v28[0] = string;
          v22 = Microsoft::WRL::Wrappers::HString::Set(a2 + 2, v28);
        }
        else
        {
          WindowsDeleteString(string);
          string = 0;
          v19 = *(_QWORD *)v27;
          v20 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(*(_QWORD *)v27);
          if ( v20 >= 0 )
            v20 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 64LL))(v19, &string);
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x4D3,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\storagehelpers.cpp",
            (const char *)(unsigned int)v20,
            v27[0]);
          WindowsDeleteString(string);
          string = 0;
          v21 = *(_QWORD *)v27;
          v22 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(*(_QWORD *)v27);
          if ( v22 >= 0 )
            v22 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v21 + 64LL))(v21, &string);
        }
        v14 = Windows::Internal::CResultBase::MapErrorIfCanceled((Windows::Internal::CResultBase *)a2, v22);
        WindowsDeleteString(string);
        string = 0;
      }
      else
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
        AllTextUsingFileAsync = CFileIOStatics::s_ReadAllTextUsingFileAsync(
                                  v30,
                                  *(unsigned int *)(a1 + 16),
                                  *(unsigned int *)(a1 + 20),
                                  v27);
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x4D0,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storagehelpers.cpp",
          (const char *)AllTextUsingFileAsync,
          v27[0]);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
        v16 = CFileIOStatics::s_ReadAllTextUsingFileAsync(
                v30,
                *(unsigned int *)(a1 + 16),
                *(unsigned int *)(a1 + 20),
                v27);
        v14 = Windows::Internal::CResultBase::MapErrorIfCanceled((Windows::Internal::CResultBase *)a2, v16);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      v8 = WindowsGetStringRawBuffer(*(HSTRING *)a1, 0);
      StorageItemFromPathOrMsUri_PartialTrustCaller = CreateStorageItemFromPathOrMsUri_PartialTrustCaller(
                                                        v8,
                                                        v9,
                                                        (void **)&v30);
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x4CD,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storagehelpers.cpp",
        (const char *)StorageItemFromPathOrMsUri_PartialTrustCaller,
        v27[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      v11 = WindowsGetStringRawBuffer(*(HSTRING *)a1, 0);
      v13 = CreateStorageItemFromPathOrMsUri_PartialTrustCaller(v11, v12, (void **)&v30);
      v14 = Windows::Internal::CResultBase::MapErrorIfCanceled((Windows::Internal::CResultBase *)a2, v13);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  }
  else
  {
    v27[0] = anonymous_namespace_::EncodingToByteOrderMark(*(unsigned int *)(a1 + 16), *(unsigned int *)(a1 + 20));
    LODWORD(string) = 0;
    v28[0] = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
    EntireFileIntoDataReaderSync = CPathIOStatics::s_LoadEntireFileIntoDataReaderSync(*(HSTRING *)a1);
    v14 = EntireFileIntoDataReaderSync;
    if ( EntireFileIntoDataReaderSync >= 0 )
    {
      v31[0] = 0;
      WindowsDeleteString(0);
      v31[0] = 0;
      AllTextSync = anonymous_namespace_::CStorageHelpers::s_ReadAllTextSync(v28[0], (unsigned int)string, v27[0], v31);
      v14 = AllTextSync;
      if ( AllTextSync >= 0 )
      {
        v30 = v31[0];
        v25 = Microsoft::WRL::Wrappers::HString::Set(a2 + 2, &v30);
        v14 = Windows::Internal::CResultBase::MapErrorIfCanceled((Windows::Internal::CResultBase *)a2, v25);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4DF,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storagehelpers.cpp",
          (const char *)(unsigned int)AllTextSync,
          v27[0]);
      }
      WindowsDeleteString(v31[0]);
      v31[0] = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4DC,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storagehelpers.cpp",
        (const char *)(unsigned int)EntireFileIntoDataReaderSync,
        v27[0]);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
  }
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v32);
  return v14;
}

```

## disassembly

```asm
0x18042d6b8  mov     [rsp-8+arg_10], rbx
0x18042d6bd  push    rbp
0x18042d6be  push    rsi
0x18042d6bf  push    rdi
0x18042d6c0  lea     rbp, [rsp-30h]
0x18042d6c5  sub     rsp, 130h
0x18042d6cc  mov     rax, cs:__security_cookie
0x18042d6d3  xor     rax, rsp
0x18042d6d6  mov     [rbp+40h+var_20], rax
0x18042d6da  mov     rdi, rdx
0x18042d6dd  mov     rbx, rcx
0x18042d6e0  movups  xmm0, xmmword ptr [rcx+18h]
0x18042d6e4  movdqu  xmmword ptr [rsp+140h+var_110], xmm0
0x18042d6ea  lea     r9, [rsp+140h+var_110]
0x18042d6ef  mov     r8b, 1
0x18042d6f2  lea     rdx, aSReadalltextas_0; "s_ReadAllTextAsync.MakeAsyncOperation"
0x18042d6f9  lea     rcx, [rsp+140h+var_E0]
0x18042d6fe  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBD_NU_GUID@@@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,bool,_GUID)
0x18042d703  nop
0x18042d704  xor     edx, edx; length
0x18042d706  mov     rcx, [rbx]; string
0x18042d709  call    cs:__imp_WindowsGetStringRawBuffer
0x18042d70f  mov     rcx, rax; pszPath
0x18042d712  call    cs:__imp_PathIsURLW
0x18042d718  xor     esi, esi
0x18042d71a  test    eax, eax
0x18042d71c  jz      loc_18042D960
0x18042d722  mov     [rsp+140h+var_F8], rsi
0x18042d727  lea     rcx, [rsp+140h+var_F8]
0x18042d72c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042d731  xor     edx, edx; length
0x18042d733  mov     rcx, [rbx]; string
0x18042d736  call    cs:__imp_WindowsGetStringRawBuffer
0x18042d73c  lea     r8, [rsp+140h+var_F8]; void **
0x18042d741  mov     rcx, rax; unsigned __int16 *
0x18042d744  call    ?CreateStorageItemFromPathOrMsUri_PartialTrustCaller@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; CreateStorageItemFromPathOrMsUri_PartialTrustCaller(ushort const *,_GUID const &,void * *)
0x18042d749  test    eax, eax
0x18042d74b  jns     short loc_18042D7BA
0x18042d74d  lea     rcx, [rsp+140h+var_F8]
0x18042d752  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042d757  xor     edx, edx; length
0x18042d759  mov     rcx, [rbx]; string
0x18042d75c  call    cs:__imp_WindowsGetStringRawBuffer
0x18042d762  lea     r8, [rsp+140h+var_F8]; void **
0x18042d767  mov     rcx, rax; unsigned __int16 *
0x18042d76a  call    ?CreateStorageItemFromPathOrMsUri_PartialTrustCaller@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; CreateStorageItemFromPathOrMsUri_PartialTrustCaller(ushort const *,_GUID const &,void * *)
0x18042d76f  mov     rcx, [rbp+48h]; this
0x18042d773  mov     r9d, eax; char *
0x18042d776  lea     r8, aOnecoreuapShel_155; "onecoreuap\\shell\\windows.storage\\sto"...
0x18042d77d  mov     edx, 4CDh; void *
0x18042d782  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18042d787  lea     rcx, [rsp+140h+var_F8]
0x18042d78c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042d791  xor     edx, edx; length
0x18042d793  mov     rcx, [rbx]; string
0x18042d796  call    cs:__imp_WindowsGetStringRawBuffer
0x18042d79c  lea     r8, [rsp+140h+var_F8]; void **
0x18042d7a1  mov     rcx, rax; unsigned __int16 *
0x18042d7a4  call    ?CreateStorageItemFromPathOrMsUri_PartialTrustCaller@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; CreateStorageItemFromPathOrMsUri_PartialTrustCaller(ushort const *,_GUID const &,void * *)
0x18042d7a9  mov     edx, eax; int
0x18042d7ab  mov     rcx, rdi; this
0x18042d7ae  call    ?MapErrorIfCanceled@CResultBase@Internal@Windows@@QEBAJJ@Z; Windows::Internal::CResultBase::MapErrorIfCanceled(long)
0x18042d7b3  mov     ebx, eax
0x18042d7b5  jmp     loc_18042D951
0x18042d7ba  mov     qword ptr [rsp+140h+var_120], rsi; int
0x18042d7bf  lea     rcx, [rsp+140h+var_120]
0x18042d7c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042d7c9  lea     r9, [rsp+140h+var_120]
0x18042d7ce  mov     r8d, [rbx+14h]
0x18042d7d2  mov     edx, [rbx+10h]
0x18042d7d5  mov     rcx, [rsp+140h+var_F8]
0x18042d7da  call    CFileIOStatics__s_ReadAllTextUsingFileAsync
0x18042d7df  test    eax, eax
0x18042d7e1  jns     short loc_18042D84C
0x18042d7e3  lea     rcx, [rsp+140h+var_120]
0x18042d7e8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042d7ed  lea     r9, [rsp+140h+var_120]
0x18042d7f2  mov     r8d, [rbx+14h]
0x18042d7f6  mov     edx, [rbx+10h]
0x18042d7f9  mov     rcx, [rsp+140h+var_F8]
0x18042d7fe  call    CFileIOStatics__s_ReadAllTextUsingFileAsync
0x18042d803  mov     rcx, [rbp+48h]; this
0x18042d807  mov     r9d, eax; char *
0x18042d80a  lea     r8, aOnecoreuapShel_155; "onecoreuap\\shell\\windows.storage\\sto"...
0x18042d811  mov     edx, 4D0h; void *
0x18042d816  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18042d81b  lea     rcx, [rsp+140h+var_120]
0x18042d820  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042d825  lea     r9, [rsp+140h+var_120]
0x18042d82a  mov     r8d, [rbx+14h]
0x18042d82e  mov     edx, [rbx+10h]
0x18042d831  mov     rcx, [rsp+140h+var_F8]
0x18042d836  call    CFileIOStatics__s_ReadAllTextUsingFileAsync
0x18042d83b  mov     edx, eax; int
0x18042d83d  mov     rcx, rdi; this
0x18042d840  call    ?MapErrorIfCanceled@CResultBase@Internal@Windows@@QEBAJJ@Z; Windows::Internal::CResultBase::MapErrorIfCanceled(long)
0x18042d845  mov     ebx, eax
0x18042d847  jmp     loc_18042D946
0x18042d84c  mov     [rsp+140h+string], rsi
0x18042d851  xor     ecx, ecx; string
0x18042d853  call    cs:__imp_WindowsDeleteString
0x18042d859  mov     [rsp+140h+string], rsi
0x18042d85e  mov     rbx, qword ptr [rsp+140h+var_120]
0x18042d863  mov     rcx, rbx
0x18042d866  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18042d86b  test    eax, eax
0x18042d86d  js      short loc_18042D884
0x18042d86f  mov     rax, [rbx]
0x18042d872  lea     rdx, [rsp+140h+string]
0x18042d877  mov     rcx, rbx
0x18042d87a  mov     rax, [rax+40h]
0x18042d87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d883  nop
0x18042d884  test    eax, eax
0x18042d886  jns     loc_18042D912
0x18042d88c  mov     rcx, [rsp+140h+string]; string
0x18042d891  call    cs:__imp_WindowsDeleteString
0x18042d897  mov     [rsp+140h+string], rsi
0x18042d89c  mov     rbx, qword ptr [rsp+140h+var_120]
0x18042d8a1  mov     rcx, rbx
0x18042d8a4  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18042d8a9  test    eax, eax
0x18042d8ab  js      short loc_18042D8C2
0x18042d8ad  mov     rax, [rbx]
0x18042d8b0  lea     rdx, [rsp+140h+string]
0x18042d8b5  mov     rcx, rbx
0x18042d8b8  mov     rax, [rax+40h]
0x18042d8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d8c1  nop
0x18042d8c2  mov     rcx, [rbp+48h]; this
0x18042d8c6  mov     r9d, eax; char *
0x18042d8c9  lea     r8, aOnecoreuapShel_155; "onecoreuap\\shell\\windows.storage\\sto"...
0x18042d8d0  mov     edx, 4D3h; void *
0x18042d8d5  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18042d8da  mov     rcx, [rsp+140h+string]; string
0x18042d8df  call    cs:__imp_WindowsDeleteString
0x18042d8e5  mov     [rsp+140h+string], rsi
0x18042d8ea  mov     rbx, qword ptr [rsp+140h+var_120]
0x18042d8ef  mov     rcx, rbx
0x18042d8f2  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18042d8f7  test    eax, eax
0x18042d8f9  js      short loc_18042D910
0x18042d8fb  mov     rax, [rbx]
0x18042d8fe  lea     rdx, [rsp+140h+string]
0x18042d903  mov     rcx, rbx
0x18042d906  mov     rax, [rax+40h]
0x18042d90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d90f  nop
0x18042d910  jmp     short loc_18042D92A
0x18042d912  mov     rax, [rsp+140h+string]
0x18042d917  mov     [rsp+140h+var_110], rax
0x18042d91c  lea     rcx, [rdi+10h]; newString
0x18042d920  lea     rdx, [rsp+140h+var_110]; HSTRING *
0x18042d925  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18042d92a  mov     edx, eax; int
0x18042d92c  mov     rcx, rdi; this
0x18042d92f  call    ?MapErrorIfCanceled@CResultBase@Internal@Windows@@QEBAJJ@Z; Windows::Internal::CResultBase::MapErrorIfCanceled(long)
0x18042d934  mov     ebx, eax
0x18042d936  mov     rcx, [rsp+140h+string]; string
0x18042d93b  call    cs:__imp_WindowsDeleteString
0x18042d941  mov     [rsp+140h+string], rsi
0x18042d946  lea     rcx, [rsp+140h+var_120]
0x18042d94b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042d950  nop
0x18042d951  lea     rcx, [rsp+140h+var_F8]
0x18042d956  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042d95b  jmp     loc_18042DA42
0x18042d960  mov     edx, [rbx+14h]
0x18042d963  mov     ecx, [rbx+10h]
0x18042d966  call    _anonymous_namespace___EncodingToByteOrderMark
0x18042d96b  mov     [rsp+140h+var_120], eax; int
0x18042d96f  mov     dword ptr [rsp+140h+string], esi
0x18042d973  mov     [rsp+140h+var_110], rsi
0x18042d978  lea     rcx, [rsp+140h+var_110]
0x18042d97d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042d982  lea     r9, [rsp+140h+var_120]
0x18042d987  lea     r8, [rsp+140h+var_110]
0x18042d98c  lea     rdx, [rsp+140h+string]
0x18042d991  mov     rcx, [rbx]; HSTRING
0x18042d994  call    CPathIOStatics__s_LoadEntireFileIntoDataReaderSync
0x18042d999  mov     ebx, eax
0x18042d99b  test    eax, eax
0x18042d99d  jns     short loc_18042D9B9
0x18042d99f  mov     rcx, [rbp+48h]; this
0x18042d9a3  mov     r9d, eax; char *
0x18042d9a6  lea     r8, aOnecoreuapShel_155; "onecoreuap\\shell\\windows.storage\\sto"...
0x18042d9ad  mov     edx, 4DCh; void *
0x18042d9b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18042d9b7  jmp     short loc_18042DA37
0x18042d9b9  mov     [rsp+140h+var_F0], rsi
0x18042d9be  xor     ecx, ecx; string
0x18042d9c0  call    cs:__imp_WindowsDeleteString
0x18042d9c6  mov     [rsp+140h+var_F0], rsi
0x18042d9cb  lea     r9, [rsp+140h+var_F0]
0x18042d9d0  mov     r8d, [rsp+140h+var_120]
0x18042d9d5  mov     edx, dword ptr [rsp+140h+string]
0x18042d9d9  mov     rcx, [rsp+140h+var_110]
0x18042d9de  call    _anonymous_namespace___CStorageHelpers__s_ReadAllTextSync
0x18042d9e3  mov     ebx, eax
0x18042d9e5  test    eax, eax
0x18042d9e7  jns     short loc_18042DA03
0x18042d9e9  mov     rcx, [rbp+48h]; this
0x18042d9ed  mov     r9d, eax; char *
0x18042d9f0  lea     r8, aOnecoreuapShel_155; "onecoreuap\\shell\\windows.storage\\sto"...
0x18042d9f7  mov     edx, 4DFh; void *
0x18042d9fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18042da01  jmp     short loc_18042DA27
0x18042da03  mov     rax, [rsp+140h+var_F0]
0x18042da08  mov     [rsp+140h+var_F8], rax
0x18042da0d  lea     rcx, [rdi+10h]; newString
0x18042da11  lea     rdx, [rsp+140h+var_F8]; HSTRING *
0x18042da16  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18042da1b  mov     edx, eax; int
0x18042da1d  mov     rcx, rdi; this
0x18042da20  call    ?MapErrorIfCanceled@CResultBase@Internal@Windows@@QEBAJJ@Z; Windows::Internal::CResultBase::MapErrorIfCanceled(long)
0x18042da25  mov     ebx, eax
0x18042da27  mov     rcx, [rsp+140h+var_F0]; string
0x18042da2c  call    cs:__imp_WindowsDeleteString
0x18042da32  mov     [rsp+140h+var_F0], rsi
0x18042da37  lea     rcx, [rsp+140h+var_110]
0x18042da3c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042da41  nop
0x18042da42  lea     rcx, [rsp+140h+var_E0]; this
0x18042da47  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18042da4c  mov     eax, ebx
0x18042da4e  mov     rcx, [rbp+40h+var_20]
0x18042da52  xor     rcx, rsp; StackCookie
0x18042da55  call    __security_check_cookie
0x18042da5a  mov     rbx, [rsp+140h+arg_10]
0x18042da62  add     rsp, 130h
0x18042da69  pop     rdi
0x18042da6a  pop     rsi
0x18042da6b  pop     rbp
0x18042da6c  retn
```
