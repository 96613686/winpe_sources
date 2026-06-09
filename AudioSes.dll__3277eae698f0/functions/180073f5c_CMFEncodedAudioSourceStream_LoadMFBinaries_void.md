# CMFEncodedAudioSourceStream::LoadMFBinaries(void)

- ea: `0x180073f5c`
- end: `0x18007410d`
- name: `?LoadMFBinaries@CMFEncodedAudioSourceStream@@AEAAJXZ`
- size: `433`
- prototype: `__int64 __fastcall(CMFEncodedAudioSourceStream *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004cdbc`

## callees

- `0x18000a9cc`
- `0x1800516a4`
- `0x180073f5c`
- `0x180074114`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180073f7f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180073fd8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180073f7f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180073fd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180074015`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180074033`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180074054`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180074075`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180074099`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800740bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800740e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180074015`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180074033`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180074054`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180074075`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180074099`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800740bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800740e1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180073fa5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180073fa5`

## string_xrefs

- `0x180073f76`: `MFPlat.dll`
- `0x180073fcf`: `MFReadWrite.dll`
- `0x18007402c`: `MFCreateSourceReaderFromURL`
- `0x180074092`: `MFCreateMediaType`
- `0x1800740b6`: `MFCreateWaveFormatExFromMFMediaType`
- `0x18007404d`: `MFCreateMFByteStreamOnStreamEx`
- `0x18007406e`: `MFCreateSourceReaderFromByteStream`

## pseudocode

```c
__int64 __fastcall CMFEncodedAudioSourceStream::LoadMFBinaries(CMFEncodedAudioSourceStream *this)
{
  HMODULE *v2; // rdi
  const char *v3; // r9
  __int64 v4; // rdx
  HMODULE *v6; // rsi
  FARPROC ProcAddress; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hLibModule; // [rsp+30h] [rbp+8h] BYREF

  v2 = (HMODULE *)((char *)this + 88);
  hLibModule = LoadLibraryExW(L"MFPlat.dll", 0, 0x800u);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
    v2,
    &hLibModule);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( !*v2 )
  {
    v4 = 33;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\client\\audioplayer\\lib\\mfencodedaudiosourcestream.cpp",
             v3);
  }
  v6 = (HMODULE *)((char *)this + 96);
  hLibModule = LoadLibraryExW(L"MFReadWrite.dll", 0, 0x800u);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
    (char *)this + 96,
    &hLibModule);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hLibModule);
  if ( !*((_QWORD *)this + 12) )
  {
    v4 = 36;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\client\\audioplayer\\lib\\mfencodedaudiosourcestream.cpp",
             v3);
  }
  ProcAddress = GetProcAddress(*v2, "MFStartup");
  *((_QWORD *)this + 13) = ProcAddress;
  if ( !ProcAddress )
  {
    v4 = 39;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\client\\audioplayer\\lib\\mfencodedaudiosourcestream.cpp",
             v3);
  }
  v8 = GetProcAddress(*v6, "MFCreateSourceReaderFromURL");
  *((_QWORD *)this + 14) = v8;
  if ( !v8 )
  {
    v4 = 42;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\client\\audioplayer\\lib\\mfencodedaudiosourcestream.cpp",
             v3);
  }
  v9 = GetProcAddress(*v2, "MFCreateMFByteStreamOnStreamEx");
  *((_QWORD *)this + 15) = v9;
  if ( !v9 )
  {
    v4 = 45;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\client\\audioplayer\\lib\\mfencodedaudiosourcestream.cpp",
             v3);
  }
  v10 = GetProcAddress(*v6, "MFCreateSourceReaderFromByteStream");
  *((_QWORD *)this + 16) = v10;
  if ( !v10 )
  {
    v4 = 48;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\client\\audioplayer\\lib\\mfencodedaudiosourcestream.cpp",
             v3);
  }
  v11 = GetProcAddress(*v2, "MFCreateMediaType");
  *((_QWORD *)this + 17) = v11;
  if ( !v11 )
  {
    v4 = 51;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\client\\audioplayer\\lib\\mfencodedaudiosourcestream.cpp",
             v3);
  }
  v12 = GetProcAddress(*v2, "MFCreateWaveFormatExFromMFMediaType");
  *((_QWORD *)this + 18) = v12;
  if ( !v12 )
  {
    v4 = 54;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\client\\audioplayer\\lib\\mfencodedaudiosourcestream.cpp",
             v3);
  }
  v13 = GetProcAddress(*v2, "MFShutdown");
  *((_QWORD *)this + 19) = v13;
  if ( !v13 )
  {
    v4 = 57;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\client\\audioplayer\\lib\\mfencodedaudiosourcestream.cpp",
             v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180073f5c  mov     [rsp+arg_8], rbx
0x180073f61  mov     [rsp+arg_10], rsi
0x180073f66  push    rdi
0x180073f67  sub     rsp, 20h
0x180073f6b  mov     rbx, rcx
0x180073f6e  mov     esi, 800h
0x180073f73  mov     r8d, esi; dwFlags
0x180073f76  lea     rcx, LibFileName; "MFPlat.dll"
0x180073f7d  xor     edx, edx; hFile
0x180073f7f  call    cs:__imp_LoadLibraryExW
0x180073f85  lea     rdi, [rbx+58h]
0x180073f89  mov     [rsp+28h+hLibModule], rax
0x180073f8e  mov     rcx, rdi
0x180073f91  lea     rdx, [rsp+28h+hLibModule]
0x180073f96  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x180073f9b  mov     rcx, [rsp+28h+hLibModule]; hLibModule
0x180073fa0  test    rcx, rcx
0x180073fa3  jz      short loc_180073FAB
0x180073fa5  call    cs:__imp_FreeLibrary
0x180073fab  cmp     qword ptr [rdi], 0
0x180073faf  jnz     short loc_180073FCC
0x180073fb1  mov     edx, 21h ; '!'; void *
0x180073fb6  mov     rcx, [rsp+28h]; this
0x180073fbb  lea     r8, aAvcoreAudiocor_67; "avcore\\audiocore\\client\\audioplayer"...
0x180073fc2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180073fc7  jmp     loc_1800740FD
0x180073fcc  mov     r8d, esi; dwFlags
0x180073fcf  lea     rcx, aMfreadwriteDll; "MFReadWrite.dll"
0x180073fd6  xor     edx, edx; hFile
0x180073fd8  call    cs:__imp_LoadLibraryExW
0x180073fde  lea     rsi, [rbx+60h]
0x180073fe2  mov     [rsp+28h+hLibModule], rax
0x180073fe7  mov     rcx, rsi
0x180073fea  lea     rdx, [rsp+28h+hLibModule]
0x180073fef  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x180073ff4  lea     rcx, [rsp+28h+hLibModule]
0x180073ff9  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180073ffe  cmp     qword ptr [rsi], 0
0x180074002  jnz     short loc_18007400B
0x180074004  mov     edx, 24h ; '$'
0x180074009  jmp     short loc_180073FB6
0x18007400b  mov     rcx, [rdi]; hModule
0x18007400e  lea     rdx, aMfstartup; "MFStartup"
0x180074015  call    cs:__imp_GetProcAddress
0x18007401b  mov     [rbx+68h], rax
0x18007401f  test    rax, rax
0x180074022  jnz     short loc_180074029
0x180074024  lea     edx, [rax+27h]
0x180074027  jmp     short loc_180073FB6
0x180074029  mov     rcx, [rsi]; hModule
0x18007402c  lea     rdx, aMfcreatesource_0; "MFCreateSourceReaderFromURL"
0x180074033  call    cs:__imp_GetProcAddress
0x180074039  mov     [rbx+70h], rax
0x18007403d  test    rax, rax
0x180074040  jnz     short loc_18007404A
0x180074042  lea     edx, [rax+2Ah]
0x180074045  jmp     loc_180073FB6
0x18007404a  mov     rcx, [rdi]; hModule
0x18007404d  lea     rdx, aMfcreatemfbyte; "MFCreateMFByteStreamOnStreamEx"
0x180074054  call    cs:__imp_GetProcAddress
0x18007405a  mov     [rbx+78h], rax
0x18007405e  test    rax, rax
0x180074061  jnz     short loc_18007406B
0x180074063  lea     edx, [rax+2Dh]
0x180074066  jmp     loc_180073FB6
0x18007406b  mov     rcx, [rsi]; hModule
0x18007406e  lea     rdx, aMfcreatesource; "MFCreateSourceReaderFromByteStream"
0x180074075  call    cs:__imp_GetProcAddress
0x18007407b  mov     [rbx+80h], rax
0x180074082  test    rax, rax
0x180074085  jnz     short loc_18007408F
0x180074087  lea     edx, [rax+30h]
0x18007408a  jmp     loc_180073FB6
0x18007408f  mov     rcx, [rdi]; hModule
0x180074092  lea     rdx, aMfcreatemediat; "MFCreateMediaType"
0x180074099  call    cs:__imp_GetProcAddress
0x18007409f  mov     [rbx+88h], rax
0x1800740a6  test    rax, rax
0x1800740a9  jnz     short loc_1800740B3
0x1800740ab  lea     edx, [rax+33h]
0x1800740ae  jmp     loc_180073FB6
0x1800740b3  mov     rcx, [rdi]; hModule
0x1800740b6  lea     rdx, aMfcreatewavefo; "MFCreateWaveFormatExFromMFMediaType"
0x1800740bd  call    cs:__imp_GetProcAddress
0x1800740c3  mov     [rbx+90h], rax
0x1800740ca  test    rax, rax
0x1800740cd  jnz     short loc_1800740D7
0x1800740cf  lea     edx, [rax+36h]
0x1800740d2  jmp     loc_180073FB6
0x1800740d7  mov     rcx, [rdi]; hModule
0x1800740da  lea     rdx, aMfshutdown; "MFShutdown"
0x1800740e1  call    cs:__imp_GetProcAddress
0x1800740e7  mov     [rbx+98h], rax
0x1800740ee  test    rax, rax
0x1800740f1  jnz     short loc_1800740FB
0x1800740f3  lea     edx, [rax+39h]
0x1800740f6  jmp     loc_180073FB6
0x1800740fb  xor     eax, eax
0x1800740fd  mov     rbx, [rsp+28h+arg_8]
0x180074102  mov     rsi, [rsp+28h+arg_10]
0x180074107  add     rsp, 20h
0x18007410b  pop     rdi
0x18007410c  retn
```
