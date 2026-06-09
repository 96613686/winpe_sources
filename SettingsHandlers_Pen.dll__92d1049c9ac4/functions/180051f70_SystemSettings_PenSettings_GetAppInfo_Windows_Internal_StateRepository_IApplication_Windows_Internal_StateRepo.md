# SystemSettings::PenSettings::GetAppInfo(Windows::Internal::StateRepository::IApplication *,Windows::Internal::StateRepository::IApplicationResourceResolverStatics *,SystemSettings::PenSettings::PenLaunchableAppInfo *)

- ea: `0x180051f70`
- end: `0x18005237b`
- name: `?GetAppInfo@PenSettings@SystemSettings@@YAJPEAUIApplication@StateRepository@Internal@Windows@@PEAUIApplicationResourceResolverStatics@456@PEAUPenLaunchableAppInfo@12@@Z`
- size: `1035`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings *__hidden this, struct Windows::Internal::StateRepository::IApplication *, struct Windows::Internal::StateRepository::IApplicationResourceResolverStatics *, struct SystemSettings::PenSettings::PenLaunchableAppInfo *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180051668`

## callees

- `0x1800030e0`
- `0x180008128`
- `0x18000a2bc`
- `0x18001cff8`
- `0x180020638`
- `0x18003f1a8`
- `0x180051f70`
- `0x180054048`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005220e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180052238`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180052263`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005220e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180052238`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180052263`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800520e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052127`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005218a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800521db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052290`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800522ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800522bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052324`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052341`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800520e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052127`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005218a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800521db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052290`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800522ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800522bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052324`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052341`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052351`

## string_xrefs

- `0x180051ffc`: `shellcommon\shell\settingshandlers\pen\lib\pensingletons.cpp`
- `0x180052056`: `shellcommon\shell\settingshandlers\pen\lib\pensingletons.cpp`
- `0x1800520b3`: `shellcommon\shell\settingshandlers\pen\lib\pensingletons.cpp`
- `0x180052110`: `shellcommon\shell\settingshandlers\pen\lib\pensingletons.cpp`
- `0x180052173`: `shellcommon\shell\settingshandlers\pen\lib\pensingletons.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SystemSettings::PenSettings::GetAppInfo(
        SystemSettings::PenSettings *this,
        struct Windows::Internal::StateRepository::IApplication *a2,
        struct Windows::Internal::StateRepository::IApplicationResourceResolverStatics *a3,
        struct SystemSettings::PenSettings::PenLaunchableAppInfo *a4)
{
  int LaunchableAppInfo; // eax
  unsigned int v8; // ebx
  char v9; // al
  __int64 (__fastcall *v10)(SystemSettings::PenSettings *, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  int v20; // eax
  int (__fastcall *v21)(struct Windows::Internal::StateRepository::IApplication *, SystemSettings::PenSettings *, __int64 *); // rbx
  __int64 v22; // rdi
  void (__fastcall *v23)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v25; // r8
  PCWSTR v26; // rax
  __int64 v27; // r8
  PCWSTR v28; // rax
  __int64 v29; // rbx
  const char *v30; // r9
  HSTRING string; // [rsp+20h] [rbp-C8h] BYREF
  __int64 v33; // [rsp+28h] [rbp-C0h] BYREF
  HSTRING v34; // [rsp+30h] [rbp-B8h] BYREF
  HSTRING v35; // [rsp+38h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+48h] [rbp-A0h] BYREF
  unsigned int v38; // [rsp+50h] [rbp-98h]
  __int128 v39; // [rsp+60h] [rbp-88h] BYREF
  __m128i si128; // [rsp+70h] [rbp-78h]
  __m128i v41[2]; // [rsp+80h] [rbp-68h] BYREF
  char v42; // [rsp+A0h] [rbp-48h]
  int v43; // [rsp+A1h] [rbp-47h]
  __int16 v44; // [rsp+A5h] [rbp-43h]
  char v45; // [rsp+A7h] [rbp-41h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v39 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v39) = 0;
  v41[0] = 0;
  v41[1] = si128;
  v41[0].m128i_i16[0] = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  LaunchableAppInfo = SystemSettings::PenSettings::GetLaunchableAppInfo(
                        this,
                        a2,
                        (struct Windows::Internal::StateRepository::IApplicationResourceResolverStatics *)&v39,
                        a4);
  v8 = LaunchableAppInfo;
  if ( LaunchableAppInfo >= 0 )
  {
    v9 = v42;
    if ( v42 )
    {
      v33 = 0;
      v10 = *(__int64 (__fastcall **)(SystemSettings::PenSettings *, __int64 *))(*(_QWORD *)this + 72LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      v11 = v10(this, &v33);
      v8 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x31,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\pensingletons.cpp",
          (const char *)(unsigned int)v11,
          (int)string);
LABEL_6:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        goto LABEL_27;
      }
      v36 = 0;
      v12 = v33;
      v13 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 72LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
      v14 = v13(v12, &v36);
      v8 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x33,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\pensingletons.cpp",
          (const char *)(unsigned int)v14,
          (int)string);
LABEL_9:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        goto LABEL_6;
      }
      string = 0;
      v15 = v36;
      v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36 + 88LL);
      WindowsDeleteString(0);
      string = 0;
      v17 = v16(v15, &string);
      v8 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x35,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\pensingletons.cpp",
          (const char *)(unsigned int)v17,
          (int)string);
LABEL_12:
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_9;
      }
      v34 = 0;
      v18 = v33;
      v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 112LL);
      WindowsDeleteString(0);
      v34 = 0;
      v20 = v19(v18, &v34);
      v8 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\pensingletons.cpp",
          (const char *)(unsigned int)v20,
          (int)string);
        WindowsDeleteString(v34);
        v34 = 0;
        goto LABEL_12;
      }
      v37 = 0;
      v35 = 0;
      v21 = *(int (__fastcall **)(struct Windows::Internal::StateRepository::IApplication *, SystemSettings::PenSettings *, __int64 *))(*(_QWORD *)a2 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      if ( v21(a2, this, &v37) >= 0 )
      {
        v22 = v37;
        v23 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 96LL);
        WindowsDeleteString(v35);
        v35 = 0;
        v23(v22, &v35);
      }
      try
      {
        std::wstring::operator=(a3, v41);
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v29 = -1;
        v25 = -1;
        do
          ++v25;
        while ( StringRawBuffer[v25] );
        std::wstring::_Assign<unsigned short>((char *)a3 + 32, StringRawBuffer);
        v26 = WindowsGetStringRawBuffer(v34, 0);
        v27 = -1;
        do
          ++v27;
        while ( v26[v27] );
        std::wstring::_Assign<unsigned short>((char *)a3 + 96, v26);
        if ( v35 )
          v28 = WindowsGetStringRawBuffer(v35, 0);
        else
          v28 = &word_1800679F0;
        do
          ++v29;
        while ( v28[v29] );
        std::wstring::_Assign<unsigned short>((char *)a3 + 64, v28);
      }
      catch ( ... )
      {
        v38 = wil::details::in1diag3::Return_CaughtException(
                retaddr,
                (void *)0x49,
                (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\pensingletons.cpp",
                v30);
        WindowsDeleteString(v35);
        v35 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
        WindowsDeleteString(v34);
        v34 = 0;
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        v8 = v38;
        goto LABEL_27;
      }
      WindowsDeleteString(v35);
      v35 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      WindowsDeleteString(v34);
      v34 = 0;
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      v9 = v42;
    }
    *((_BYTE *)a3 + 128) = v9;
    v8 = 0;
    goto LABEL_27;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2B,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\pensingletons.cpp",
    (const char *)(unsigned int)LaunchableAppInfo,
    (int)string);
LABEL_27:
  std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(&v39);
  return v8;
}

```

## disassembly

```asm
0x180051f70  mov     r11, rsp
0x180051f73  mov     [r11+20h], rbx
0x180051f77  push    rsi
0x180051f78  push    rdi
0x180051f79  push    r12
0x180051f7b  push    r14
0x180051f7d  push    r15
0x180051f7f  sub     rsp, 0C0h
0x180051f86  mov     rax, cs:__security_cookie
0x180051f8d  xor     rax, rsp
0x180051f90  mov     [rsp+0E8h+var_38], rax
0x180051f98  mov     r14, r8
0x180051f9b  mov     r12, rdx
0x180051f9e  mov     r15, rcx
0x180051fa1  xorps   xmm0, xmm0
0x180051fa4  movups  [rsp+0E8h+var_88], xmm0
0x180051fa9  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180051fb1  movdqa  [rsp+0E8h+var_78], xmm1
0x180051fb7  xor     esi, esi
0x180051fb9  mov     word ptr [rsp+0E8h+var_88], si
0x180051fbe  movups  xmmword ptr [r11-68h], xmm0
0x180051fc3  movdqa  xmmword ptr [r11-58h], xmm1
0x180051fc9  mov     [r11-68h], si
0x180051fce  mov     [r11-48h], sil
0x180051fd2  xor     eax, eax
0x180051fd4  mov     [r11-47h], eax
0x180051fd8  mov     [r11-43h], ax
0x180051fdd  mov     [r11-41h], al
0x180051fe1  lea     r8, [rsp+0E8h+var_88]; struct Windows::Internal::StateRepository::IApplicationResourceResolverStatics *
0x180051fe6  call    ?GetLaunchableAppInfo@PenSettings@SystemSettings@@YAJPEAUIApplication@StateRepository@Internal@Windows@@PEAUIApplicationResourceResolverStatics@456@PEAUAppInfo@12@@Z; SystemSettings::PenSettings::GetLaunchableAppInfo(Windows::Internal::StateRepository::IApplication *,Windows::Internal::StateRepository::IApplicationResourceResolverStatics *,SystemSettings::PenSettings::AppInfo *)
0x180051feb  mov     ebx, eax
0x180051fed  test    eax, eax
0x180051fef  jns     short loc_180052010
0x180051ff1  mov     rcx, [rsp+0E8h]; this
0x180051ff9  mov     r9d, eax; char *
0x180051ffc  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\p"...
0x180052003  lea     edx, [rsi+2Bh]; void *
0x180052006  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005200b  jmp     loc_1800522EB
0x180052010  mov     al, [rsp+0E8h+var_48]
0x180052017  test    al, al
0x180052019  jz      loc_1800522E2
0x18005201f  mov     [rsp+0E8h+var_C0], rsi
0x180052024  mov     rax, [r15]
0x180052027  mov     rbx, [rax+48h]
0x18005202b  lea     rcx, [rsp+0E8h+var_C0]
0x180052030  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052035  lea     rdx, [rsp+0E8h+var_C0]
0x18005203a  mov     rcx, r15
0x18005203d  mov     rax, rbx
0x180052040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052045  mov     ebx, eax
0x180052047  test    eax, eax
0x180052049  jns     short loc_180052077
0x18005204b  mov     rcx, [rsp+0E8h]; this
0x180052053  mov     r9d, eax; char *
0x180052056  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\p"...
0x18005205d  mov     edx, 31h ; '1'; void *
0x180052062  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052067  nop
0x180052068  lea     rcx, [rsp+0E8h+var_C0]
0x18005206d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052072  jmp     loc_1800522EB
0x180052077  mov     [rsp+0E8h+var_A8], rsi
0x18005207c  mov     rdi, [rsp+0E8h+var_C0]
0x180052081  mov     rax, [rdi]
0x180052084  mov     rbx, [rax+48h]
0x180052088  lea     rcx, [rsp+0E8h+var_A8]
0x18005208d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052092  lea     rdx, [rsp+0E8h+var_A8]
0x180052097  mov     rcx, rdi
0x18005209a  mov     rax, rbx
0x18005209d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800520a2  mov     ebx, eax
0x1800520a4  test    eax, eax
0x1800520a6  jns     short loc_1800520D1
0x1800520a8  mov     rcx, [rsp+0E8h]; this
0x1800520b0  mov     r9d, eax; char *
0x1800520b3  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\p"...
0x1800520ba  mov     edx, 33h ; '3'; void *
0x1800520bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800520c4  nop
0x1800520c5  lea     rcx, [rsp+0E8h+var_A8]
0x1800520ca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800520cf  jmp     short loc_180052068
0x1800520d1  mov     [rsp+0E8h+string], rsi
0x1800520d6  mov     rdi, [rsp+0E8h+var_A8]
0x1800520db  mov     rax, [rdi]
0x1800520de  mov     rbx, [rax+58h]
0x1800520e2  xor     ecx, ecx; string
0x1800520e4  call    cs:__imp_WindowsDeleteString
0x1800520ea  mov     [rsp+0E8h+string], rsi; int
0x1800520ef  lea     rdx, [rsp+0E8h+string]
0x1800520f4  mov     rcx, rdi
0x1800520f7  mov     rax, rbx
0x1800520fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800520ff  mov     ebx, eax
0x180052101  test    eax, eax
0x180052103  jns     short loc_180052134
0x180052105  mov     rcx, [rsp+0E8h]; this
0x18005210d  mov     r9d, eax; char *
0x180052110  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\p"...
0x180052117  mov     edx, 35h ; '5'; void *
0x18005211c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052121  nop
0x180052122  mov     rcx, [rsp+0E8h+string]; string
0x180052127  call    cs:__imp_WindowsDeleteString
0x18005212d  mov     [rsp+0E8h+string], rsi
0x180052132  jmp     short loc_1800520C5
0x180052134  mov     [rsp+0E8h+var_B8], rsi
0x180052139  mov     rdi, [rsp+0E8h+var_C0]
0x18005213e  mov     rax, [rdi]
0x180052141  mov     rbx, [rax+70h]
0x180052145  xor     ecx, ecx; string
0x180052147  call    cs:__imp_WindowsDeleteString
0x18005214d  mov     [rsp+0E8h+var_B8], rsi
0x180052152  lea     rdx, [rsp+0E8h+var_B8]
0x180052157  mov     rcx, rdi
0x18005215a  mov     rax, rbx
0x18005215d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052162  mov     ebx, eax
0x180052164  test    eax, eax
0x180052166  jns     short loc_180052197
0x180052168  mov     rcx, [rsp+0E8h]; this
0x180052170  mov     r9d, eax; char *
0x180052173  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\p"...
0x18005217a  mov     edx, 37h ; '7'; void *
0x18005217f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052184  nop
0x180052185  mov     rcx, [rsp+0E8h+var_B8]; string
0x18005218a  call    cs:__imp_WindowsDeleteString
0x180052190  mov     [rsp+0E8h+var_B8], rsi
0x180052195  jmp     short loc_180052122
0x180052197  mov     [rsp+0E8h+var_A0], rsi
0x18005219c  mov     [rsp+0E8h+var_B0], rsi
0x1800521a1  mov     rax, [r12]
0x1800521a5  mov     rbx, [rax+30h]
0x1800521a9  lea     rcx, [rsp+0E8h+var_A0]
0x1800521ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800521b3  lea     r8, [rsp+0E8h+var_A0]
0x1800521b8  mov     rdx, r15
0x1800521bb  mov     rcx, r12
0x1800521be  mov     rax, rbx
0x1800521c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800521c6  test    eax, eax
0x1800521c8  js      short loc_1800521F7
0x1800521ca  mov     rdi, [rsp+0E8h+var_A0]
0x1800521cf  mov     rax, [rdi]
0x1800521d2  mov     rbx, [rax+60h]
0x1800521d6  mov     rcx, [rsp+0E8h+var_B0]; string
0x1800521db  call    cs:__imp_WindowsDeleteString
0x1800521e1  mov     [rsp+0E8h+var_B0], rsi
0x1800521e6  lea     rdx, [rsp+0E8h+var_B0]
0x1800521eb  mov     rcx, rdi
0x1800521ee  mov     rax, rbx
0x1800521f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800521f6  nop
0x1800521f7  lea     rdx, [rsp+0E8h+var_68]
0x1800521ff  mov     rcx, r14
0x180052202  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180052207  xor     edx, edx; length
0x180052209  mov     rcx, [rsp+0E8h+string]; string
0x18005220e  call    cs:__imp_WindowsGetStringRawBuffer
0x180052214  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180052218  mov     r8, rbx
0x18005221b  inc     r8
0x18005221e  cmp     [rax+r8*2], si
0x180052223  jnz     short loc_18005221B
0x180052225  lea     rcx, [r14+20h]
0x180052229  mov     rdx, rax
0x18005222c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180052231  xor     edx, edx; length
0x180052233  mov     rcx, [rsp+0E8h+var_B8]; string
0x180052238  call    cs:__imp_WindowsGetStringRawBuffer
0x18005223e  mov     r8, rbx
0x180052241  inc     r8
0x180052244  cmp     [rax+r8*2], si
0x180052249  jnz     short loc_180052241
0x18005224b  lea     rcx, [r14+60h]
0x18005224f  mov     rdx, rax
0x180052252  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180052257  mov     rcx, [rsp+0E8h+var_B0]; string
0x18005225c  test    rcx, rcx
0x18005225f  jz      short loc_18005226B
0x180052261  xor     edx, edx; length
0x180052263  call    cs:__imp_WindowsGetStringRawBuffer
0x180052269  jmp     short loc_180052272
0x18005226b  lea     rax, word_1800679F0
0x180052272  inc     rbx
0x180052275  cmp     [rax+rbx*2], si
0x180052279  jnz     short loc_180052272
0x18005227b  lea     rcx, [r14+40h]
0x18005227f  mov     r8, rbx
0x180052282  mov     rdx, rax
0x180052285  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005228a  nop
0x18005228b  mov     rcx, [rsp+0E8h+var_B0]; string
0x180052290  call    cs:__imp_WindowsDeleteString
0x180052296  mov     [rsp+0E8h+var_B0], rsi
0x18005229b  lea     rcx, [rsp+0E8h+var_A0]
0x1800522a0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800522a5  nop
0x1800522a6  mov     rcx, [rsp+0E8h+var_B8]; string
0x1800522ab  call    cs:__imp_WindowsDeleteString
0x1800522b1  mov     [rsp+0E8h+var_B8], rsi
0x1800522b6  mov     rcx, [rsp+0E8h+string]; string
0x1800522bb  call    cs:__imp_WindowsDeleteString
0x1800522c1  mov     [rsp+0E8h+string], rsi
0x1800522c6  lea     rcx, [rsp+0E8h+var_A8]
0x1800522cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800522d0  nop
0x1800522d1  lea     rcx, [rsp+0E8h+var_C0]
0x1800522d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800522db  mov     al, [rsp+0E8h+var_48]
0x1800522e2  mov     [r14+80h], al
0x1800522e9  mov     ebx, esi
0x1800522eb  lea     rcx, [rsp+0E8h+var_88]
0x1800522f0  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x1800522f5  mov     eax, ebx
0x1800522f7  mov     rcx, [rsp+0E8h+var_38]
0x1800522ff  xor     rcx, rsp; StackCookie
0x180052302  call    __security_check_cookie
0x180052307  mov     rbx, [rsp+0E8h+arg_18]
0x18005230f  add     rsp, 0C0h
0x180052316  pop     r15
0x180052318  pop     r14
0x18005231a  pop     r12
0x18005231c  pop     rdi
0x18005231d  pop     rsi
0x18005231e  retn
0x18005231f  mov     rcx, [rsp+0E8h+var_B0]; string
0x180052324  call    cs:__imp_WindowsDeleteString
0x18005232a  xor     esi, esi
0x18005232c  mov     [rsp+0E8h+var_B0], rsi
0x180052331  lea     rcx, [rsp+0E8h+var_A0]
0x180052336  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005233b  nop
0x18005233c  mov     rcx, [rsp+0E8h+var_B8]; string
0x180052341  call    cs:__imp_WindowsDeleteString
0x180052347  mov     [rsp+0E8h+var_B8], rsi
0x18005234c  mov     rcx, [rsp+0E8h+string]; string
0x180052351  call    cs:__imp_WindowsDeleteString
0x180052357  mov     [rsp+0E8h+string], rsi
0x18005235c  lea     rcx, [rsp+0E8h+var_A8]
0x180052361  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052366  nop
0x180052367  lea     rcx, [rsp+0E8h+var_C0]
0x18005236c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052371  mov     ebx, [rsp+0E8h+var_98]
0x180052375  jmp     loc_1800522EB
```
