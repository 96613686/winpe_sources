# SystemSettings::PenSettings::DeviceSpecificAppLink::Invoke(HWND__ *)

- ea: `0x180016400`
- end: `0x1800167f2`
- name: `?Invoke@DeviceSpecificAppLink@PenSettings@SystemSettings@@MEAAJPEAUHWND__@@@Z`
- size: `1010`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::DeviceSpecificAppLink *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800030e0`
- `0x180008128`
- `0x18000a2bc`
- `0x18000f058`
- `0x180011e10`
- `0x1800127cc`
- `0x180016400`
- `0x18001950c`
- `0x1800198b8`
- `0x1800199b4`
- `0x180019a40`
- `0x180019c14`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001665d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800167ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001665d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800167ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016644`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016644`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016456`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016456`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016486`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016486`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180016561`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001667e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180016561`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001667e`

## string_xrefs

- `0x180016536`: `Windows.Foundation.Uri`
- `0x180016574`: `shellcommon\shell\settingshandlers\pen\lib\mischandlers.cpp`
- `0x18001660c`: `shellcommon\shell\settingshandlers\pen\lib\mischandlers.cpp`
- `0x180016691`: `shellcommon\shell\settingshandlers\pen\lib\mischandlers.cpp`
- `0x1800166eb`: `shellcommon\shell\settingshandlers\pen\lib\mischandlers.cpp`
- `0x180016740`: `shellcommon\shell\settingshandlers\pen\lib\mischandlers.cpp`
- `0x1800167ba`: `shellcommon\shell\settingshandlers\pen\lib\mischandlers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SystemSettings::PenSettings::DeviceSpecificAppLink::Invoke(
        SystemSettings::PenSettings::DeviceSpecificAppLink *this,
        HWND a2)
{
  LSTATUS v2; // eax
  __int64 v3; // r8
  HSTRING v4; // rbx
  const WCHAR *v5; // rdi
  __int64 v6; // rax
  unsigned __int64 v7; // rsi
  int v8; // eax
  __int64 v9; // rbx
  int ActivationFactory; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r14
  unsigned int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 (__fastcall *v17)(HSTRING, GUID *, __int64 *); // rdi
  int v18; // eax
  __int64 v19; // rdi
  int v20; // eax
  int phkResult; // [rsp+20h] [rbp-59h]
  _QWORD *v23; // [rsp+30h] [rbp-49h] BYREF
  __int64 v24; // [rsp+38h] [rbp-41h] BYREF
  __int64 (__fastcall ***v25)(HSTRING, GUID *, __int64 *); // [rsp+40h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-31h] BYREF
  __int64 v27; // [rsp+50h] [rbp-29h] BYREF
  __int64 v28; // [rsp+58h] [rbp-21h] BYREF
  PCWSTR sourceString; // [rsp+60h] [rbp-19h] BYREF
  __int64 v30; // [rsp+68h] [rbp-11h]
  __int64 v31; // [rsp+70h] [rbp-9h]
  HSTRING string; // [rsp+78h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  sourceString = 0;
  v30 = 0;
  v31 = 0;
  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\ClickNote\\OemCustomizationSettingsApp",
         0,
         0x20019u,
         &hKey);
  LODWORD(v4) = v2;
  if ( v2 > 0 )
    LODWORD(v4) = (unsigned __int16)v2 | 0x80070000;
  if ( (int)v4 < 0
    || (LODWORD(v4) = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
                        (BYTE **)&sourceString,
                        hKey,
                        v3),
        RegCloseKey(hKey),
        (int)v4 < 0) )
  {
LABEL_36:
    v11 = (unsigned int)v4;
    v12 = 446;
    goto LABEL_37;
  }
  v5 = sourceString;
  v6 = v30;
  v7 = -1;
  if ( v30 == -1 )
  {
    if ( sourceString )
    {
      v6 = -1;
      do
        ++v6;
      while ( sourceString[v6] );
    }
    else
    {
      v6 = 0;
    }
  }
  if ( &v5[v6] == (const WCHAR *)std::_Find_vectorized<unsigned short const,unsigned short>(
                                   sourceString,
                                   &sourceString[v6],
                                   58) )
  {
    LODWORD(hKey) = 58;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
    v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
           &sourceString,
           v30 + 1);
    LODWORD(v4) = v8;
    if ( v8 < 0 )
    {
      v11 = (unsigned int)v8;
      v12 = 451;
LABEL_37:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\mischandlers.cpp",
        (const char *)v11,
        phkResult);
      goto LABEL_38;
    }
    v5 = sourceString;
    v9 = v30;
    StringCchCopyNW((unsigned __int16 *)&sourceString[v30], 2u, (const unsigned __int16 *)&hKey, 1u);
    v30 = v9 + 1;
  }
  v23 = 0;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    (HSTRING_HEADER *)&string,
    L"Windows.Foundation.Uri",
    0x17u,
    0x16u);
  v4 = *(HSTRING *)&hstringHeader.Reserved.Reserved2[16];
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v23);
  LODWORD(v4) = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v24 = 0;
    v4 = (HSTRING)v23;
    v13 = *v23;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
    do
      ++v7;
    while ( v5[v7] );
    if ( v7 <= 0xFFFFFFFF )
    {
      v14 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v7);
      Microsoft::WRL::Wrappers::HStringReference::CreateReference((HSTRING_HEADER *)&string, v5, v14, v7);
      v15 = (*(__int64 (__fastcall **)(HSTRING, _QWORD, __int64 *))(v13 + 48))(
              v4,
              *(_QWORD *)&hstringHeader.Reserved.Reserved2[16],
              &v24);
      LODWORD(v4) = v15;
      if ( v15 >= 0 )
      {
        v25 = 0;
        if ( WindowsCreateStringReference(L"Windows.System.Launcher", 0x17u, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v4 = string;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
        v16 = RoGetActivationFactory(v4, &GUID_00000035_0000_0000_c000_000000000046, &v25);
        LODWORD(v4) = v16;
        if ( v16 >= 0 )
        {
          v27 = 0;
          v4 = (HSTRING)v25;
          v17 = **v25;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
          v18 = v17(v4, &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451, &v27);
          LODWORD(v4) = v18;
          if ( v18 >= 0 )
          {
            v28 = 0;
            v19 = v27;
            v4 = *(HSTRING *)(*(_QWORD *)v27 + 64LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
            v20 = ((__int64 (__fastcall *)(__int64, __int64, __int64 *))v4)(v19, v24, &v28);
            LODWORD(v4) = v20;
            if ( v20 >= 0 )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
              return 0;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1D3,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\mischandlers.cpp",
              (const char *)(unsigned int)v20,
              phkResult);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1D0,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\mischandlers.cpp",
              (const char *)(unsigned int)v18,
              phkResult);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1CD,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\mischandlers.cpp",
            (const char *)(unsigned int)v16,
            phkResult);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1CA,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\mischandlers.cpp",
          (const char *)(unsigned int)v15,
          phkResult);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
      goto LABEL_16;
    }
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_36;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1C7,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\mischandlers.cpp",
    (const char *)(unsigned int)ActivationFactory,
    phkResult);
LABEL_16:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
LABEL_38:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180016400  push    rbp
0x180016402  push    rbx
0x180016403  push    rsi
0x180016404  push    rdi
0x180016405  push    r14
0x180016407  push    r15
0x180016409  lea     rbp, [rsp-2Fh]
0x18001640e  sub     rsp, 0A8h
0x180016415  mov     rax, cs:__security_cookie
0x18001641c  xor     rax, rsp
0x18001641f  mov     [rbp+57h+var_38], rax
0x180016423  xor     r15d, r15d
0x180016426  mov     [rbp+57h+sourceString], r15
0x18001642a  mov     [rbp+57h+var_68], r15
0x18001642e  mov     [rbp+57h+var_60], r15
0x180016432  mov     [rbp+57h+hKey], r15
0x180016436  lea     rax, [rbp+57h+hKey]
0x18001643a  mov     qword ptr [rsp+0D0h+phkResult], rax; int
0x18001643f  mov     r9d, 20019h; samDesired
0x180016445  xor     r8d, r8d; ulOptions
0x180016448  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001644f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016456  call    cs:__imp_RegOpenKeyExW
0x18001645c  mov     ebx, eax
0x18001645e  test    eax, eax
0x180016460  jle     short loc_18001646B
0x180016462  movzx   ebx, ax
0x180016465  or      ebx, 80070000h
0x18001646b  test    ebx, ebx
0x18001646d  js      loc_1800167B2
0x180016473  mov     rdx, [rbp+57h+hKey]
0x180016477  lea     rcx, [rbp+57h+sourceString]
0x18001647b  call    ?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x180016480  mov     ebx, eax
0x180016482  mov     rcx, [rbp+57h+hKey]; hKey
0x180016486  call    cs:__imp_RegCloseKey
0x18001648c  test    ebx, ebx
0x18001648e  js      loc_1800167B2
0x180016494  mov     rdi, [rbp+57h+sourceString]
0x180016498  mov     rax, [rbp+57h+var_68]
0x18001649c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800164a0  cmp     rax, rsi
0x1800164a3  jnz     short loc_1800164BC
0x1800164a5  test    rdi, rdi
0x1800164a8  jz      short loc_1800164B9
0x1800164aa  mov     rax, rsi
0x1800164ad  inc     rax
0x1800164b0  cmp     [rdi+rax*2], r15w
0x1800164b5  jnz     short loc_1800164AD
0x1800164b7  jmp     short loc_1800164BC
0x1800164b9  mov     rax, r15
0x1800164bc  lea     rbx, [rdi+rax*2]
0x1800164c0  mov     r14d, 3Ah ; ':'
0x1800164c6  mov     r8d, r14d
0x1800164c9  mov     rdx, rbx
0x1800164cc  mov     rcx, rdi
0x1800164cf  call    ??$_Find_vectorized@$$CBGG@std@@YAPEBGQEBG0G@Z; std::_Find_vectorized<ushort const,ushort>(ushort const * const,ushort const * const,ushort)
0x1800164d4  cmp     rbx, rax
0x1800164d7  jnz     short loc_180016524
0x1800164d9  mov     dword ptr [rbp+57h+hKey], r14d
0x1800164dd  lea     rcx, [rbp+57h+sourceString]
0x1800164e1  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800164e6  mov     rdx, [rbp+57h+var_68]
0x1800164ea  inc     rdx
0x1800164ed  lea     rcx, [rbp+57h+sourceString]
0x1800164f1  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1800164f6  mov     ebx, eax
0x1800164f8  test    eax, eax
0x1800164fa  js      loc_180016594
0x180016500  mov     rdi, [rbp+57h+sourceString]
0x180016504  mov     rbx, [rbp+57h+var_68]
0x180016508  lea     rcx, [rdi+rbx*2]; unsigned __int16 *
0x18001650c  lea     r9d, [r14-39h]; unsigned __int64
0x180016510  lea     r8, [rbp+57h+hKey]; unsigned __int16 *
0x180016514  lea     edx, [r14-38h]; unsigned __int64
0x180016518  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001651d  inc     rbx
0x180016520  mov     [rbp+57h+var_68], rbx
0x180016524  mov     [rbp+57h+var_A0], r15
0x180016528  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], r15
0x18001652c  mov     r9d, 16h; unsigned int
0x180016532  lea     r8d, [r9+1]; unsigned int
0x180016536  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18001653d  lea     rcx, [rbp+57h+string]; hstringHeader
0x180016541  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180016546  mov     rbx, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x18001654a  lea     rcx, [rbp+57h+var_A0]
0x18001654e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016553  lea     r8, [rbp+57h+var_A0]
0x180016557  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x18001655e  mov     rcx, rbx
0x180016561  call    cs:__imp_RoGetActivationFactory
0x180016567  mov     ebx, eax
0x180016569  test    eax, eax
0x18001656b  jns     short loc_1800165A1
0x18001656d  mov     rcx, [rbp+5Fh]; this
0x180016571  mov     r9d, eax; char *
0x180016574  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\settingshandlers\\p"...
0x18001657b  mov     edx, 1C7h; void *
0x180016580  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016585  nop
0x180016586  lea     rcx, [rbp+57h+var_A0]
0x18001658a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001658f  jmp     loc_1800167CB
0x180016594  mov     r9d, eax
0x180016597  mov     edx, 1C3h
0x18001659c  jmp     loc_1800167BA
0x1800165a1  mov     [rbp+57h+var_98], r15
0x1800165a5  mov     rbx, [rbp+57h+var_A0]
0x1800165a9  mov     r14, [rbx]
0x1800165ac  lea     rcx, [rbp+57h+var_98]
0x1800165b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800165b5  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], r15
0x1800165b9  inc     rsi
0x1800165bc  cmp     [rdi+rsi*2], r15w
0x1800165c1  jnz     short loc_1800165B9
0x1800165c3  mov     eax, 0FFFFFFFFh
0x1800165c8  cmp     rsi, rax
0x1800165cb  ja      loc_18001679C
0x1800165d1  mov     ecx, esi; unsigned int
0x1800165d3  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800165d8  mov     r9d, esi; unsigned int
0x1800165db  mov     r8d, eax; unsigned int
0x1800165de  mov     rdx, rdi; sourceString
0x1800165e1  lea     rcx, [rbp+57h+string]; hstringHeader
0x1800165e5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800165ea  nop
0x1800165eb  lea     r8, [rbp+57h+var_98]
0x1800165ef  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x1800165f3  mov     rcx, rbx
0x1800165f6  mov     rax, [r14+30h]
0x1800165fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165ff  mov     ebx, eax
0x180016601  test    eax, eax
0x180016603  jns     short loc_18001662C
0x180016605  mov     rcx, [rbp+5Fh]; this
0x180016609  mov     r9d, eax; char *
0x18001660c  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\settingshandlers\\p"...
0x180016613  mov     edx, 1CAh; void *
0x180016618  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001661d  nop
0x18001661e  lea     rcx, [rbp+57h+var_98]
0x180016622  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016627  jmp     loc_180016586
0x18001662c  mov     [rbp+57h+var_90], r15
0x180016630  lea     r9, [rbp+57h+string]; string
0x180016634  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180016638  mov     edx, 17h; length
0x18001663d  lea     rcx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x180016644  call    cs:__imp_WindowsCreateStringReference
0x18001664a  test    eax, eax
0x18001664c  jns     short loc_180016663
0x18001664e  xor     r9d, r9d; lpArguments
0x180016651  xor     r8d, r8d; nNumberOfArguments
0x180016654  lea     edx, [r9+1]; dwExceptionFlags
0x180016658  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001665d  call    cs:__imp_RaiseException
0x180016663  mov     rbx, [rbp+57h+string]
0x180016667  lea     rcx, [rbp+57h+var_90]
0x18001666b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016670  lea     r8, [rbp+57h+var_90]
0x180016674  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18001667b  mov     rcx, rbx
0x18001667e  call    cs:__imp_RoGetActivationFactory
0x180016684  mov     ebx, eax
0x180016686  test    eax, eax
0x180016688  jns     short loc_1800166B1
0x18001668a  mov     rcx, [rbp+5Fh]; this
0x18001668e  mov     r9d, eax; char *
0x180016691  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\settingshandlers\\p"...
0x180016698  mov     edx, 1CDh; void *
0x18001669d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800166a2  nop
0x1800166a3  lea     rcx, [rbp+57h+var_90]
0x1800166a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800166ac  jmp     loc_18001661E
0x1800166b1  mov     [rbp+57h+var_80], r15
0x1800166b5  mov     rbx, [rbp+57h+var_90]
0x1800166b9  mov     rax, [rbx]
0x1800166bc  mov     rdi, [rax]
0x1800166bf  lea     rcx, [rbp+57h+var_80]
0x1800166c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800166c8  lea     r8, [rbp+57h+var_80]
0x1800166cc  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x1800166d3  mov     rcx, rbx
0x1800166d6  mov     rax, rdi
0x1800166d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166de  mov     ebx, eax
0x1800166e0  test    eax, eax
0x1800166e2  jns     short loc_180016708
0x1800166e4  mov     rcx, [rbp+5Fh]; this
0x1800166e8  mov     r9d, eax; char *
0x1800166eb  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\settingshandlers\\p"...
0x1800166f2  mov     edx, 1D0h; void *
0x1800166f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800166fc  nop
0x1800166fd  lea     rcx, [rbp+57h+var_80]
0x180016701  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016706  jmp     short loc_1800166A3
0x180016708  mov     [rbp+57h+var_78], r15
0x18001670c  mov     rdi, [rbp+57h+var_80]
0x180016710  mov     rax, [rdi]
0x180016713  mov     rbx, [rax+40h]
0x180016717  lea     rcx, [rbp+57h+var_78]
0x18001671b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016720  lea     r8, [rbp+57h+var_78]
0x180016724  mov     rdx, [rbp+57h+var_98]
0x180016728  mov     rcx, rdi
0x18001672b  mov     rax, rbx
0x18001672e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016733  mov     ebx, eax
0x180016735  test    eax, eax
0x180016737  jns     short loc_18001675D
0x180016739  mov     rcx, [rbp+5Fh]; this
0x18001673d  mov     r9d, eax; char *
0x180016740  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\settingshandlers\\p"...
0x180016747  mov     edx, 1D3h; void *
0x18001674c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016751  nop
0x180016752  lea     rcx, [rbp+57h+var_78]
0x180016756  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001675b  jmp     short loc_1800166FD
0x18001675d  lea     rcx, [rbp+57h+var_78]
0x180016761  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016766  nop
0x180016767  lea     rcx, [rbp+57h+var_80]
0x18001676b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016770  nop
0x180016771  lea     rcx, [rbp+57h+var_90]
0x180016775  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001677a  nop
0x18001677b  lea     rcx, [rbp+57h+var_98]
0x18001677f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016784  nop
0x180016785  lea     rcx, [rbp+57h+var_A0]
0x180016789  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001678e  nop
0x18001678f  lea     rcx, [rbp+57h+sourceString]
0x180016793  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180016798  xor     eax, eax
0x18001679a  jmp     short loc_1800167D6
0x18001679c  xor     r9d, r9d; lpArguments
0x18001679f  xor     r8d, r8d; nNumberOfArguments
0x1800167a2  lea     edx, [r9+1]; dwExceptionFlags
0x1800167a6  mov     ecx, 80070216h; dwExceptionCode
0x1800167ab  call    cs:__imp_RaiseException
0x1800167b1  nop
0x1800167b2  mov     r9d, ebx; char *
0x1800167b5  mov     edx, 1BEh; void *
0x1800167ba  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\settingshandlers\\p"...
0x1800167c1  mov     rcx, [rbp+5Fh]; this
0x1800167c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800167ca  nop
0x1800167cb  lea     rcx, [rbp+57h+sourceString]
0x1800167cf  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800167d4  mov     eax, ebx
0x1800167d6  mov     rcx, [rbp+57h+var_38]
0x1800167da  xor     rcx, rsp; StackCookie
0x1800167dd  call    __security_check_cookie
0x1800167e2  add     rsp, 0A8h
0x1800167e9  pop     r15
0x1800167eb  pop     r14
0x1800167ed  pop     rdi
0x1800167ee  pop     rsi
0x1800167ef  pop     rbx
0x1800167f0  pop     rbp
0x1800167f1  retn
```
