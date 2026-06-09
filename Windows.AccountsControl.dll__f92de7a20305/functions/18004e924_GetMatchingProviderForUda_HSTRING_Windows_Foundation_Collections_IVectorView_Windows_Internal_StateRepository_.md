# GetMatchingProviderForUda(HSTRING__ *,Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::ApplicationExtension *> *,HSTRING__ * *)

- ea: `0x18004e924`
- end: `0x18004eb70`
- name: `?GetMatchingProviderForUda@@YAJPEAUHSTRING__@@PEAU?$IVectorView@PEAVApplicationExtension@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@PEAPEAU1@@Z`
- size: `588`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004f028`

## callees

- `0x180006e8c`
- `0x180006eac`
- `0x180011ffc`
- `0x18004e254`
- `0x18004e924`
- `0x18004eb78`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e9de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ea4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004eae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004eb2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e9de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ea4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004eae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004eb2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004e990`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ea05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004e990`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ea05`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ea34`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ea34`

## string_xrefs

- `0x18004e969`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\appextensionhelpers.cpp`
- `0x18004ea97`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\appextensionhelpers.cpp`
- `0x18004eafa`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\appextensionhelpers.cpp`
- `0x18004eb16`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\appextensionhelpers.cpp`
- `0x18004eb3f`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\appextensionhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetMatchingProviderForUda(HSTRING string, __int64 a2, _QWORD *a3)
{
  int v6; // eax
  unsigned int LastError; // ebx
  const WCHAR *StringRawBuffer; // r14
  unsigned int i; // edi
  __int64 (__fastcall *v11)(__int64, _QWORD, struct Windows::Internal::StateRepository::IApplicationExtension **); // rbx
  int v12; // eax
  int PackageFamilyNameForAppExtension; // eax
  const WCHAR *v14; // rbx
  int v15; // eax
  const char *v16; // r9
  struct Windows::Internal::StateRepository::IApplicationExtension *v17; // rdi
  __int64 (__fastcall *v18)(struct Windows::Internal::StateRepository::IApplicationExtension *, const WCHAR **); // rbx
  int v19; // eax
  __int64 v20; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-20h]
  struct Windows::Internal::StateRepository::IApplicationExtension *v22; // [rsp+30h] [rbp-10h] BYREF
  const WCHAR *v23; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  unsigned int v25; // [rsp+88h] [rbp+48h] BYREF
  HSTRING stringa; // [rsp+90h] [rbp+50h] BYREF
  const WCHAR *v27; // [rsp+98h] [rbp+58h] BYREF

  *a3 = 0;
  v25 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v25);
  LastError = v6;
  if ( v6 >= 0 )
  {
    if ( v25 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v23 = StringRawBuffer;
      for ( i = 0; ; ++i )
      {
        if ( i >= v25 )
          return 0;
        v22 = 0;
        v11 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Internal::StateRepository::IApplicationExtension **))(*(_QWORD *)a2 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
        v12 = v11(a2, i, &v22);
        LastError = v12;
        if ( v12 < 0 )
          break;
        stringa = 0;
        WindowsDeleteString(0);
        stringa = 0;
        PackageFamilyNameForAppExtension = GetPackageFamilyNameForAppExtension(v22, &stringa);
        LastError = PackageFamilyNameForAppExtension;
        if ( PackageFamilyNameForAppExtension < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9F,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\appextensionhelpers.cpp",
            (const char *)(unsigned int)PackageFamilyNameForAppExtension,
            bIgnoreCase);
          goto LABEL_20;
        }
        v14 = WindowsGetStringRawBuffer(stringa, 0);
        v27 = v14;
        SyncPartnershipApiTelemetry::MatchingUdaProviderWithContractProvider<unsigned short const * &,unsigned short const * &>(
          &v23,
          &v27);
        v15 = CompareStringOrdinal(StringRawBuffer, -1, v14, -1, 1);
        if ( !v15 )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xA9,
                        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\appexte"
                                      "nsionhelpers.cpp",
                        v16);
          goto LABEL_20;
        }
        if ( v15 == 2 )
        {
          v27 = 0;
          v17 = v22;
          v18 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IApplicationExtension *, const WCHAR **))(*(_QWORD *)v22 + 72LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
          v19 = v18(v17, &v27);
          LastError = v19;
          if ( v19 < 0 )
          {
            v20 = 173;
            goto LABEL_14;
          }
          v19 = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD *))(*(_QWORD *)v27 + 232LL))(v27, a3);
          LastError = v19;
          if ( v19 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
            WindowsDeleteString(stringa);
            stringa = 0;
            LastError = 0;
          }
          else
          {
            v20 = 174;
LABEL_14:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v20,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\appextensionhelpers.cpp",
              (const char *)(unsigned int)v19,
              bIgnoreCase);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
LABEL_20:
            WindowsDeleteString(stringa);
            stringa = 0;
          }
LABEL_22:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
          return LastError;
        }
        WindowsDeleteString(stringa);
        stringa = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\appextensionhelpers.cpp",
        (const char *)(unsigned int)v12,
        bIgnoreCase);
      goto LABEL_22;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\appextensionhelpers.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
    return LastError;
  }
}

```

## disassembly

```asm
0x18004e924  push    rbp
0x18004e926  push    rbx
0x18004e927  push    rsi
0x18004e928  push    rdi
0x18004e929  push    r12
0x18004e92b  push    r14
0x18004e92d  push    r15
0x18004e92f  mov     rbp, rsp
0x18004e932  sub     rsp, 40h
0x18004e936  mov     r15, r8
0x18004e939  mov     rsi, rdx
0x18004e93c  mov     rdi, rcx
0x18004e93f  xor     r12d, r12d
0x18004e942  mov     [r8], r12
0x18004e945  mov     [rbp+arg_8], r12d
0x18004e949  mov     rax, [rdx]
0x18004e94c  lea     rdx, [rbp+arg_8]
0x18004e950  mov     rcx, rsi
0x18004e953  mov     rax, [rax+38h]
0x18004e957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e95c  mov     ebx, eax
0x18004e95e  test    eax, eax
0x18004e960  jns     short loc_18004E981
0x18004e962  mov     rcx, [rbp+38h]; this
0x18004e966  mov     r9d, eax; char *
0x18004e969  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004e970  mov     edx, 92h; void *
0x18004e975  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e97a  mov     eax, ebx
0x18004e97c  jmp     loc_18004EB61
0x18004e981  cmp     [rbp+arg_8], r12d
0x18004e985  jz      loc_18004EB5F
0x18004e98b  xor     edx, edx; length
0x18004e98d  mov     rcx, rdi; string
0x18004e990  call    cs:__imp_WindowsGetStringRawBuffer
0x18004e996  mov     r14, rax
0x18004e999  mov     [rbp+var_8], rax
0x18004e99d  mov     edi, r12d
0x18004e9a0  cmp     edi, [rbp+arg_8]
0x18004e9a3  jnb     loc_18004EB5F
0x18004e9a9  mov     [rbp+var_10], r12
0x18004e9ad  mov     rcx, [rsi]
0x18004e9b0  mov     rbx, [rcx+30h]
0x18004e9b4  lea     rcx, [rbp+var_10]
0x18004e9b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e9bd  lea     r8, [rbp+var_10]
0x18004e9c1  mov     edx, edi
0x18004e9c3  mov     rcx, rsi
0x18004e9c6  mov     rax, rbx
0x18004e9c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9ce  mov     ebx, eax
0x18004e9d0  test    eax, eax
0x18004e9d2  js      loc_18004EB38
0x18004e9d8  mov     [rbp+string], r12
0x18004e9dc  xor     ecx, ecx; string
0x18004e9de  call    cs:__imp_WindowsDeleteString
0x18004e9e4  mov     [rbp+string], r12
0x18004e9e8  lea     rdx, [rbp+string]; HSTRING *
0x18004e9ec  mov     rcx, [rbp+var_10]; struct Windows::Internal::StateRepository::IApplicationExtension *
0x18004e9f0  call    ?GetPackageFamilyNameForAppExtension@@YAJPEAUIApplicationExtension@StateRepository@Internal@Windows@@PEAPEAUHSTRING__@@@Z; GetPackageFamilyNameForAppExtension(Windows::Internal::StateRepository::IApplicationExtension *,HSTRING__ * *)
0x18004e9f5  mov     ebx, eax
0x18004e9f7  test    eax, eax
0x18004e9f9  js      loc_18004EB0F
0x18004e9ff  xor     edx, edx; length
0x18004ea01  mov     rcx, [rbp+string]; string
0x18004ea05  call    cs:__imp_WindowsGetStringRawBuffer
0x18004ea0b  mov     rbx, rax
0x18004ea0e  mov     [rbp+arg_18], rax
0x18004ea12  lea     rdx, [rbp+arg_18]
0x18004ea16  lea     rcx, [rbp+var_8]
0x18004ea1a  call    ??$MatchingUdaProviderWithContractProvider@AEAPEBGAEAPEBG@SyncPartnershipApiTelemetry@@SAXAEAPEBG0@Z; SyncPartnershipApiTelemetry::MatchingUdaProviderWithContractProvider<ushort const * &,ushort const * &>(ushort const * &,ushort const * &)
0x18004ea1f  mov     [rsp+40h+bIgnoreCase], 1; int
0x18004ea27  or      r9d, 0FFFFFFFFh; cchCount2
0x18004ea2b  mov     r8, rbx; lpString2
0x18004ea2e  or      edx, r9d; cchCount1
0x18004ea31  mov     rcx, r14; lpString1
0x18004ea34  call    cs:__imp_CompareStringOrdinal
0x18004ea3a  test    eax, eax
0x18004ea3c  jz      loc_18004EAF6
0x18004ea42  cmp     eax, 2
0x18004ea45  jz      short loc_18004EA65
0x18004ea47  mov     rcx, [rbp+string]; string
0x18004ea4b  call    cs:__imp_WindowsDeleteString
0x18004ea51  mov     [rbp+string], r12
0x18004ea55  lea     rcx, [rbp+var_10]
0x18004ea59  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ea5e  inc     edi
0x18004ea60  jmp     loc_18004E9A0
0x18004ea65  mov     [rbp+arg_18], r12
0x18004ea69  mov     rdi, [rbp+var_10]
0x18004ea6d  mov     rax, [rdi]
0x18004ea70  mov     rbx, [rax+48h]
0x18004ea74  lea     rcx, [rbp+arg_18]
0x18004ea78  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ea7d  lea     rdx, [rbp+arg_18]
0x18004ea81  mov     rcx, rdi
0x18004ea84  mov     rax, rbx
0x18004ea87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea8c  mov     ebx, eax
0x18004ea8e  test    eax, eax
0x18004ea90  jns     short loc_18004EAB6
0x18004ea92  mov     edx, 0ADh; void *
0x18004ea97  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004ea9e  mov     r9d, eax; char *
0x18004eaa1  mov     rcx, [rbp+38h]; this
0x18004eaa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eaaa  nop
0x18004eaab  lea     rcx, [rbp+arg_18]
0x18004eaaf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004eab4  jmp     short loc_18004EB28
0x18004eab6  mov     rcx, [rbp+arg_18]
0x18004eaba  mov     rax, [rcx]
0x18004eabd  mov     rdx, r15
0x18004eac0  mov     rax, [rax+0E8h]
0x18004eac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eacc  mov     ebx, eax
0x18004eace  test    eax, eax
0x18004ead0  jns     short loc_18004EAD9
0x18004ead2  mov     edx, 0AEh
0x18004ead7  jmp     short loc_18004EA97
0x18004ead9  lea     rcx, [rbp+arg_18]
0x18004eadd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004eae2  nop
0x18004eae3  mov     rcx, [rbp+string]; string
0x18004eae7  call    cs:__imp_WindowsDeleteString
0x18004eaed  mov     [rbp+string], r12
0x18004eaf1  mov     ebx, r12d
0x18004eaf4  jmp     short loc_18004EB51
0x18004eaf6  mov     rcx, [rbp+38h]; this
0x18004eafa  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004eb01  mov     edx, 0A9h; void *
0x18004eb06  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004eb0b  mov     ebx, eax
0x18004eb0d  jmp     short loc_18004EB28
0x18004eb0f  mov     rcx, [rbp+38h]; this
0x18004eb13  mov     r9d, eax; char *
0x18004eb16  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004eb1d  mov     edx, 9Fh; void *
0x18004eb22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eb27  nop
0x18004eb28  mov     rcx, [rbp+string]; string
0x18004eb2c  call    cs:__imp_WindowsDeleteString
0x18004eb32  mov     [rbp+string], r12
0x18004eb36  jmp     short loc_18004EB51
0x18004eb38  mov     rcx, [rbp+38h]; this
0x18004eb3c  mov     r9d, eax; char *
0x18004eb3f  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004eb46  mov     edx, 9Ch; void *
0x18004eb4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eb50  nop
0x18004eb51  lea     rcx, [rbp+var_10]
0x18004eb55  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004eb5a  jmp     loc_18004E97A
0x18004eb5f  xor     eax, eax
0x18004eb61  add     rsp, 40h
0x18004eb65  pop     r15
0x18004eb67  pop     r14
0x18004eb69  pop     r12
0x18004eb6b  pop     rdi
0x18004eb6c  pop     rsi
0x18004eb6d  pop     rbx
0x18004eb6e  pop     rbp
0x18004eb6f  retn
```
