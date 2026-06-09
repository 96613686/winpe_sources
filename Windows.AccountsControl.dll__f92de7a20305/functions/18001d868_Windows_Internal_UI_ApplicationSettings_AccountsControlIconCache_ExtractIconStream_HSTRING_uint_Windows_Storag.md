# Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache::ExtractIconStream(HSTRING__ *,uint,Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x18001d868`
- end: `0x18001db92`
- name: `?ExtractIconStream@AccountsControlIconCache@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAUHSTRING__@@IPEAPEAUIRandomAccessStream@Streams@Storage@5@@Z`
- size: `810`
- prototype: `int(Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache *__hidden this, HSTRING, unsigned int, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e240`

## callees

- `0x180006eac`
- `0x180007228`
- `0x18000d890`
- `0x18000e87c`
- `0x180011ffc`
- `0x1800181ec`
- `0x180018f90`
- `0x18001b8a4`
- `0x18001c434`
- `0x18001d868`
- `0x18001ea78`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001dac5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001dac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d8c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d8c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001da30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001da30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d9ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d9ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d976`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001db7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d976`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001db7b`
- `MrmCoreR!ResourceManagerQueueGetString` at `0x18001d9e2`
- `MrmCoreR!ResourceManagerQueueGetString` at `0x18001da6a`
- `MrmCoreR!ResourceManagerQueueGetString` at `0x18001d9e2`
- `MrmCoreR!ResourceManagerQueueGetString` at `0x18001da6a`

## string_xrefs

- `0x18001d91b`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontroliconcache.cpp`
- `0x18001d962`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontroliconcache.cpp`
- `0x18001db07`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontroliconcache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache::ExtractIconStream(
        Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache *this,
        HSTRING a2,
        unsigned int a3,
        struct Windows::Storage::Streams::IRandomAccessStream **a4)
{
  unsigned __int64 v8; // rsi
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // rdx
  __int64 v11; // r9
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  void *v15; // rbx
  __int64 v16; // rdx
  int StreamFromPath; // edi
  int String; // eax
  int v20; // r9d
  LPVOID v21; // rax
  signed int v22; // eax
  unsigned int v23; // eax
  Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache *v24; // rcx
  __int64 v25; // rdx
  int v26; // [rsp+20h] [rbp-79h]
  _BYTE v27[8]; // [rsp+30h] [rbp-69h] BYREF
  SIZE_T cb; // [rsp+38h] [rbp-61h] BYREF
  struct Windows::Storage::Streams::IRandomAccessStream *v29; // [rsp+40h] [rbp-59h] BYREF
  __int64 v30; // [rsp+48h] [rbp-51h]
  __int64 v31; // [rsp+50h] [rbp-49h] BYREF
  __int64 v32; // [rsp+58h] [rbp-41h]
  __int64 v33; // [rsp+60h] [rbp-39h]
  void *v34; // [rsp+68h] [rbp-31h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-29h] BYREF
  HSTRING v36; // [rsp+88h] [rbp-11h]
  unsigned __int16 v37[12]; // [rsp+90h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  *a4 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v31);
  v8 = -1;
  v32 = -1;
  v33 = -1;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v11 = -1;
  do
    ++v11;
  while ( StringRawBuffer[v11] );
  v12 = _AllocStringWorker<CTCoAllocPolicy>(&v31, v10, StringRawBuffer);
  v13 = v12;
  if ( v12 < 0 )
  {
    v14 = 142;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontroliconcache.cpp",
      (const char *)(unsigned int)v12,
      v26);
LABEL_14:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v31);
    return v13;
  }
  v12 = StringCchPrintfW(v37, 0xBu, L"%d", a3);
  v13 = v12;
  if ( v12 < 0 )
  {
    v14 = 145;
    goto LABEL_7;
  }
  v15 = 0;
  cb = 0;
  if ( (int)ATL::AtlMultiply<unsigned __int64>(&cb, 260) < 0
    || cb > 0x7FFFFFFF
    || (v15 = CoTaskMemAlloc((unsigned int)cb), (v34 = v15) == 0) )
  {
    v16 = 149;
LABEL_11:
    StreamFromPath = -2147024882;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontroliconcache.cpp",
      (const char *)(unsigned int)StreamFromPath,
      v26);
LABEL_13:
    CoTaskMemFree(v15);
    v13 = StreamFromPath;
    goto LABEL_14;
  }
  v30 = 0;
  v26 = 260;
  String = ResourceManagerQueueGetString(v31, L"TargetSize", v37, v15);
  StreamFromPath = String;
  if ( String >= 0 )
    goto LABEL_29;
  if ( String != -2147024774 )
  {
    v16 = 155;
    goto LABEL_12;
  }
  cb = 0;
  if ( (int)ATL::AtlMultiply<unsigned __int64>(&cb, v30) < 0 )
    goto LABEL_28;
  if ( cb <= 0x7FFFFFFF )
  {
    v21 = CoTaskMemRealloc(v15, (unsigned int)cb);
    if ( v21 )
      v15 = v21;
    v34 = v15;
    v20 = v30;
  }
  else
  {
    v21 = 0;
  }
  if ( !v21 )
  {
LABEL_28:
    v16 = 160;
    goto LABEL_11;
  }
  v26 = v20;
  StreamFromPath = ResourceManagerQueueGetString(v31, L"TargetSize", v37, v15);
  if ( StreamFromPath < 0 )
  {
    v16 = 162;
    goto LABEL_12;
  }
LABEL_29:
  v29 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  v36 = 0;
  LODWORD(cb) = 0;
  do
    ++v8;
  while ( *((_WORD *)v15 + v8) );
  v22 = ULongLongToUInt(v8, (unsigned int *)&cb);
  if ( v22 < 0 )
  {
    RaiseException(v22, 1u, 0, 0);
    __debugbreak();
  }
  v23 = Microsoft::WRL::Wrappers::HStringReference::AddOne(cb);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, (PCWSTR)v15, v23, cb);
  StreamFromPath = Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache::GetStreamFromPath(
                     v24,
                     v36,
                     &v29);
  if ( StreamFromPath < 0 )
  {
    v25 = 166;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontroliconcache.cpp",
      (const char *)(unsigned int)StreamFromPath,
      v26);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    goto LABEL_13;
  }
  v27[0] = 0;
  StreamFromPath = (*(__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Storage::Streams::IRandomAccessStream *, _BYTE *))(**((_QWORD **)this + 8) + 80LL))(
                     *((_QWORD *)this + 8),
                     a2,
                     v29,
                     v27);
  if ( StreamFromPath < 0 )
  {
    v25 = 169;
    goto LABEL_35;
  }
  StreamFromPath = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *, struct Windows::Storage::Streams::IRandomAccessStream **))(*(_QWORD *)v29 + 96LL))(
                     v29,
                     a4);
  if ( StreamFromPath < 0 )
  {
    v25 = 172;
    goto LABEL_35;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  CoTaskMemFree(v15);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v31);
  return 0;
}

```

## disassembly

```asm
0x18001d868  push    rbp
0x18001d86a  push    rbx
0x18001d86b  push    rsi
0x18001d86c  push    rdi
0x18001d86d  push    r12
0x18001d86f  push    r13
0x18001d871  push    r14
0x18001d873  push    r15
0x18001d875  lea     rbp, [rsp-1Fh]
0x18001d87a  sub     rsp, 0B8h
0x18001d881  mov     rax, cs:__security_cookie
0x18001d888  xor     rax, rsp
0x18001d88b  mov     [rbp+57h+var_48], rax
0x18001d88f  mov     r14, r9
0x18001d892  mov     edi, r8d
0x18001d895  mov     r15, rdx
0x18001d898  mov     r13, rcx
0x18001d89b  xor     r12d, r12d
0x18001d89e  mov     [r9], r12
0x18001d8a1  mov     [rbp+57h+var_A0], r12
0x18001d8a5  mov     [rbp+57h+var_98], r12
0x18001d8a9  mov     [rbp+57h+var_90], r12
0x18001d8ad  lea     rcx, [rbp+57h+var_A0]
0x18001d8b1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001d8b6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001d8ba  mov     [rbp+57h+var_98], rsi
0x18001d8be  mov     [rbp+57h+var_90], rsi
0x18001d8c2  xor     edx, edx; length
0x18001d8c4  mov     rcx, r15; string
0x18001d8c7  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d8cd  mov     r9, rsi
0x18001d8d0  inc     r9
0x18001d8d3  cmp     [rax+r9*2], r12w
0x18001d8d8  jnz     short loc_18001D8D0
0x18001d8da  lea     rcx, [rbp+57h+var_A0]
0x18001d8de  mov     [rsp+0F0h+var_C8], rcx
0x18001d8e3  mov     r8, rax
0x18001d8e6  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18001d8eb  mov     ebx, eax
0x18001d8ed  test    eax, eax
0x18001d8ef  jns     short loc_18001D8F8
0x18001d8f1  mov     edx, 8Eh
0x18001d8f6  jmp     short loc_18001D91B
0x18001d8f8  mov     r9d, edi
0x18001d8fb  lea     r8, Format; "%d"
0x18001d902  mov     edx, 0Bh; unsigned __int64
0x18001d907  lea     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18001d90b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d910  mov     ebx, eax
0x18001d912  test    eax, eax
0x18001d914  jns     short loc_18001D930
0x18001d916  mov     edx, 91h; void *
0x18001d91b  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\accountscontrol\\api"...
0x18001d922  mov     r9d, eax; char *
0x18001d925  mov     rcx, [rbp+5Fh]; this
0x18001d929  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d92e  jmp     short loc_18001D97E
0x18001d930  mov     rbx, r12
0x18001d933  mov     [rbp+57h+cb], r12
0x18001d937  mov     edi, 104h
0x18001d93c  mov     edx, edi
0x18001d93e  lea     rcx, [rbp+57h+cb]
0x18001d942  call    ??$AtlMultiply@_K@ATL@@YAJPEA_K_K1@Z; ATL::AtlMultiply<unsigned __int64>(unsigned __int64 *,unsigned __int64,unsigned __int64)
0x18001d947  test    eax, eax
0x18001d949  js      short loc_18001D955
0x18001d94b  cmp     [rbp+57h+cb], 7FFFFFFFh
0x18001d953  jbe     short loc_18001D9A9
0x18001d955  mov     edx, 95h; void *
0x18001d95a  mov     edi, 8007000Eh
0x18001d95f  mov     r9d, edi; char *
0x18001d962  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\accountscontrol\\api"...
0x18001d969  mov     rcx, [rbp+5Fh]; this
0x18001d96d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d972  nop
0x18001d973  mov     rcx, rbx; pv
0x18001d976  call    cs:__imp_CoTaskMemFree
0x18001d97c  mov     ebx, edi
0x18001d97e  lea     rcx, [rbp+57h+var_A0]
0x18001d982  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001d987  mov     eax, ebx
0x18001d989  mov     rcx, [rbp+57h+var_48]
0x18001d98d  xor     rcx, rsp; StackCookie
0x18001d990  call    __security_check_cookie
0x18001d995  add     rsp, 0B8h
0x18001d99c  pop     r15
0x18001d99e  pop     r14
0x18001d9a0  pop     r13
0x18001d9a2  pop     r12
0x18001d9a4  pop     rdi
0x18001d9a5  pop     rsi
0x18001d9a6  pop     rbx
0x18001d9a7  pop     rbp
0x18001d9a8  retn
0x18001d9a9  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x18001d9ac  call    cs:__imp_CoTaskMemAlloc
0x18001d9b2  mov     rbx, rax
0x18001d9b5  mov     [rbp+57h+var_88], rax
0x18001d9b9  test    rax, rax
0x18001d9bc  jz      short loc_18001D955
0x18001d9be  mov     [rbp+57h+var_A8], r12
0x18001d9c2  lea     rax, [rbp+57h+var_A8]
0x18001d9c6  mov     [rsp+0F0h+var_C8], rax
0x18001d9cb  mov     qword ptr [rsp+0F0h+var_D0], rdi; int
0x18001d9d0  mov     r9, rbx
0x18001d9d3  lea     r8, [rbp+57h+var_60]
0x18001d9d7  lea     rdx, aTargetsize; "TargetSize"
0x18001d9de  mov     rcx, [rbp+57h+var_A0]
0x18001d9e2  call    cs:__imp_ResourceManagerQueueGetString
0x18001d9e8  mov     edi, eax
0x18001d9ea  test    eax, eax
0x18001d9ec  jns     loc_18001DA8A
0x18001d9f2  cmp     eax, 8007007Ah
0x18001d9f7  jz      short loc_18001DA03
0x18001d9f9  mov     edx, 9Bh
0x18001d9fe  jmp     loc_18001D95F
0x18001da03  mov     [rbp+57h+cb], r12
0x18001da07  mov     r9, [rbp+57h+var_A8]
0x18001da0b  mov     rdx, r9
0x18001da0e  lea     rcx, [rbp+57h+cb]
0x18001da12  call    ??$AtlMultiply@_K@ATL@@YAJPEA_K_K1@Z; ATL::AtlMultiply<unsigned __int64>(unsigned __int64 *,unsigned __int64,unsigned __int64)
0x18001da17  test    eax, eax
0x18001da19  js      short loc_18001DA80
0x18001da1b  cmp     [rbp+57h+cb], 7FFFFFFFh
0x18001da23  jbe     short loc_18001DA2A
0x18001da25  mov     rax, r12
0x18001da28  jmp     short loc_18001DA45
0x18001da2a  mov     edx, dword ptr [rbp+57h+cb]; cb
0x18001da2d  mov     rcx, rbx; pv
0x18001da30  call    cs:__imp_CoTaskMemRealloc
0x18001da36  test    rax, rax
0x18001da39  cmovnz  rbx, rax
0x18001da3d  mov     [rbp+57h+var_88], rbx
0x18001da41  mov     r9, [rbp+57h+var_A8]
0x18001da45  test    rax, rax
0x18001da48  jz      short loc_18001DA80
0x18001da4a  lea     rax, [rbp+57h+var_A8]
0x18001da4e  mov     [rsp+0F0h+var_C8], rax
0x18001da53  mov     qword ptr [rsp+0F0h+var_D0], r9
0x18001da58  mov     r9, rbx
0x18001da5b  lea     r8, [rbp+57h+var_60]
0x18001da5f  lea     rdx, aTargetsize; "TargetSize"
0x18001da66  mov     rcx, [rbp+57h+var_A0]
0x18001da6a  call    cs:__imp_ResourceManagerQueueGetString
0x18001da70  mov     edi, eax
0x18001da72  test    eax, eax
0x18001da74  jns     short loc_18001DA8A
0x18001da76  mov     edx, 0A2h
0x18001da7b  jmp     loc_18001D95F
0x18001da80  mov     edx, 0A0h
0x18001da85  jmp     loc_18001D95A
0x18001da8a  mov     [rbp+57h+var_B0], r12
0x18001da8e  lea     rcx, [rbp+57h+var_B0]
0x18001da92  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001da97  mov     [rbp+57h+var_68], r12
0x18001da9b  mov     dword ptr [rbp+57h+cb], r12d
0x18001da9f  inc     rsi
0x18001daa2  cmp     [rbx+rsi*2], r12w
0x18001daa7  jnz     short loc_18001DA9F
0x18001daa9  lea     rdx, [rbp+57h+cb]; unsigned int *
0x18001daad  mov     rcx, rsi; unsigned __int64
0x18001dab0  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18001dab5  test    eax, eax
0x18001dab7  jns     short loc_18001DACC
0x18001dab9  xor     r9d, r9d; lpArguments
0x18001dabc  xor     r8d, r8d; nNumberOfArguments
0x18001dabf  lea     edx, [r9+1]; dwExceptionFlags
0x18001dac3  mov     ecx, eax; dwExceptionCode
0x18001dac5  call    cs:__imp_RaiseException
0x18001dacb  int     3; Trap to Debugger
0x18001dacc  mov     ecx, dword ptr [rbp+57h+cb]; unsigned int
0x18001dacf  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18001dad4  mov     r9d, dword ptr [rbp+57h+cb]; unsigned int
0x18001dad8  mov     r8d, eax; unsigned int
0x18001dadb  mov     rdx, rbx; sourceString
0x18001dade  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001dae2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001dae7  nop
0x18001dae8  lea     r8, [rbp+57h+var_B0]; struct Windows::Storage::Streams::IRandomAccessStream **
0x18001daec  mov     rdx, [rbp+57h+var_68]; HSTRING
0x18001daf0  call    ?GetStreamFromPath@AccountsControlIconCache@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAUHSTRING__@@PEAPEAUIRandomAccessStream@Streams@Storage@5@@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache::GetStreamFromPath(HSTRING__ *,Windows::Storage::Streams::IRandomAccessStream * *)
0x18001daf5  mov     edi, eax
0x18001daf7  test    eax, eax
0x18001daf9  jns     short loc_18001DB22
0x18001dafb  mov     edx, 0A6h; void *
0x18001db00  mov     rcx, [rbp+5Fh]; this
0x18001db04  mov     r9d, edi; char *
0x18001db07  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\accountscontrol\\api"...
0x18001db0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db13  nop
0x18001db14  lea     rcx, [rbp+57h+var_B0]
0x18001db18  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001db1d  jmp     loc_18001D973
0x18001db22  mov     [rbp+57h+var_C0], r12b
0x18001db26  mov     rcx, [r13+40h]
0x18001db2a  mov     rax, [rcx]
0x18001db2d  lea     r9, [rbp+57h+var_C0]
0x18001db31  mov     r8, [rbp+57h+var_B0]
0x18001db35  mov     rdx, r15
0x18001db38  mov     rax, [rax+50h]
0x18001db3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db41  mov     edi, eax
0x18001db43  test    eax, eax
0x18001db45  jns     short loc_18001DB4E
0x18001db47  mov     edx, 0A9h
0x18001db4c  jmp     short loc_18001DB00
0x18001db4e  mov     rcx, [rbp+57h+var_B0]
0x18001db52  mov     rax, [rcx]
0x18001db55  mov     rdx, r14
0x18001db58  mov     rax, [rax+60h]
0x18001db5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db61  mov     edi, eax
0x18001db63  test    eax, eax
0x18001db65  jns     short loc_18001DB6E
0x18001db67  mov     edx, 0ACh
0x18001db6c  jmp     short loc_18001DB00
0x18001db6e  lea     rcx, [rbp+57h+var_B0]
0x18001db72  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001db77  nop
0x18001db78  mov     rcx, rbx; pv
0x18001db7b  call    cs:__imp_CoTaskMemFree
0x18001db81  nop
0x18001db82  lea     rcx, [rbp+57h+var_A0]
0x18001db86  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001db8b  xor     eax, eax
0x18001db8d  jmp     loc_18001D989
```
