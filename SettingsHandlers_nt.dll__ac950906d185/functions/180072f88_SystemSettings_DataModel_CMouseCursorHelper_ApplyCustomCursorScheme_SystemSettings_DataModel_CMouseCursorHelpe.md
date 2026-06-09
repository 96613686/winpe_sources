# SystemSettings::DataModel::CMouseCursorHelper::_ApplyCustomCursorScheme(SystemSettings::DataModel::CMouseCursorHelper::SMouseCursorScheme const *)

- ea: `0x180072f88`
- end: `0x1800731b7`
- name: `?_ApplyCustomCursorScheme@CMouseCursorHelper@DataModel@SystemSettings@@AEAAJPEBUSMouseCursorScheme@123@@Z`
- size: `559`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CMouseCursorHelper *__hidden this, const struct SystemSettings::DataModel::CMouseCursorHelper::SMouseCursorScheme *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180072f08`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x180019a20`
- `0x180066f74`
- `0x180072f88`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180073128`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180073128`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180073064`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180073094`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800730bf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180073064`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180073094`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800730bf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007302d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007302d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180072feb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180072feb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007303d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007303d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007310b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007310b`

## string_xrefs

- `0x180073104`: `Windows.Internal.Accessibility.Experience.CustomCursor`
- `0x18007314e`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\mouseaid.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CMouseCursorHelper::_ApplyCustomCursorScheme(
        SystemSettings::DataModel::CMouseCursorHelper *this,
        const struct SystemSettings::DataModel::CMouseCursorHelper::SMouseCursorScheme *a2)
{
  const BYTE *v3; // rcx
  __int64 v4; // rax
  unsigned int v5; // ebx
  int v6; // eax
  unsigned int v7; // edi
  DWORD dwOptions; // [rsp+28h] [rbp-29h]
  unsigned int v10; // [rsp+58h] [rbp+7h]
  HKEY hKey; // [rsp+60h] [rbp+Fh] BYREF
  __int64 v12; // [rsp+68h] [rbp+17h] BYREF
  HSTRING string; // [rsp+70h] [rbp+1Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+5Fh]

  hKey = 0;
  RegCreateKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Cursors", 0, 0, 0, 0x20006u, 0, &hKey, 0);
  v3 = (const BYTE *)*((_QWORD *)a2 + 2);
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)&v3[2 * v4] );
  RegSetValueExW(hKey, 0, 0, 1u, v3, 2 * v4 + 2);
  RegCloseKey(hKey);
  v10 = -1;
  if ( CompareStringOrdinal(*((LPCWCH *)a2 + 1), -1, L"Black", -1, 1) == 2 )
  {
    *(_WORD *)((char *)&v10 + 1) = 0;
    HIBYTE(v10) = 0;
  }
  else if ( CompareStringOrdinal(*((LPCWCH *)a2 + 1), -1, L"Inverted", -1, 1) == 2 )
  {
    LOBYTE(v10) = 0;
  }
  else if ( CompareStringOrdinal(*((LPCWCH *)a2 + 1), -1, L"Custom", -1, 1) == 2 )
  {
    *(_WORD *)((char *)&v10 + 1) = *((_WORD *)&qword_18039D538 + 2);
    HIBYTE(v10) = *((_BYTE *)&qword_18039D538 + 6);
  }
  v5 = qword_18039D538 - 1;
  v12 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.Accessibility.Experience.CustomCursor",
         0x36u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Accessibility::Experience::ICustomCursor>>(
         string,
         &v12);
  v7 = v6;
  if ( v6 >= 0 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v12 + 48LL))(v12, ((32 * v5) >> 1) + 32, v10);
    qword_18039D528 = a2;
    v7 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F1,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\mouseaid.cpp",
      (const char *)(unsigned int)v6,
      dwOptions);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  return v7;
}

```

## disassembly

```asm
0x180072f88  mov     r11, rsp
0x180072f8b  mov     [r11+8], rbx
0x180072f8f  mov     [r11+18h], rsi
0x180072f93  push    rbp
0x180072f94  push    rdi
0x180072f95  push    r14
0x180072f97  lea     rbp, [r11-5Fh]
0x180072f9b  sub     rsp, 90h
0x180072fa2  mov     rax, cs:__security_cookie
0x180072fa9  xor     rax, rsp
0x180072fac  mov     [rbp+57h+var_18], rax
0x180072fb0  mov     rsi, rdx
0x180072fb3  xor     r14d, r14d
0x180072fb6  mov     [rbp+57h+hKey], r14
0x180072fba  mov     [r11-68h], r14
0x180072fbe  lea     rax, [rbp+57h+hKey]
0x180072fc2  mov     [r11-70h], rax
0x180072fc6  mov     [r11-78h], r14
0x180072fca  mov     [rsp+0A0h+samDesired], 20006h; samDesired
0x180072fd2  mov     [rsp+0A0h+dwOptions], r14d; dwOptions
0x180072fd7  xor     r9d, r9d; lpClass
0x180072fda  xor     r8d, r8d; Reserved
0x180072fdd  lea     rdx, aControlPanelCu; "Control Panel\\Cursors"
0x180072fe4  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180072feb  call    cs:__imp_RegCreateKeyExW
0x180072ff2  nop     dword ptr [rax+rax+00h]
0x180072ff7  mov     rcx, [rsi+10h]
0x180072ffb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180072fff  mov     rax, rbx
0x180073002  inc     rax
0x180073005  cmp     [rcx+rax*2], r14w
0x18007300a  jnz     short loc_180073002
0x18007300c  lea     eax, ds:2[rax*2]
0x180073013  mov     [rsp+0A0h+samDesired], eax; cbData
0x180073017  mov     qword ptr [rsp+0A0h+dwOptions], rcx; lpData
0x18007301c  mov     edi, 1
0x180073021  mov     r9d, edi; dwType
0x180073024  xor     r8d, r8d; Reserved
0x180073027  xor     edx, edx; lpValueName
0x180073029  mov     rcx, [rbp+57h+hKey]; hKey
0x18007302d  call    cs:__imp_RegSetValueExW
0x180073034  nop     dword ptr [rax+rax+00h]
0x180073039  mov     rcx, [rbp+57h+hKey]; hKey
0x18007303d  call    cs:__imp_RegCloseKey
0x180073044  nop     dword ptr [rax+rax+00h]
0x180073049  mov     [rbp+57h+var_50], 0FFFFFFFFh
0x180073050  mov     [rsp+0A0h+dwOptions], edi; bIgnoreCase
0x180073054  mov     r9d, ebx; cchCount2
0x180073057  lea     r8, aBlack; "Black"
0x18007305e  mov     edx, ebx; cchCount1
0x180073060  mov     rcx, [rsi+8]; lpString1
0x180073064  call    cs:__imp_CompareStringOrdinal
0x18007306b  nop     dword ptr [rax+rax+00h]
0x180073070  cmp     eax, 2
0x180073073  jnz     short loc_180073080
0x180073075  mov     word ptr [rbp+57h+var_50+1], r14w
0x18007307a  mov     byte ptr [rbp+57h+var_50+3], r14b
0x18007307e  jmp     short loc_1800730EB
0x180073080  mov     [rsp+0A0h+dwOptions], edi; bIgnoreCase
0x180073084  mov     r9d, ebx; cchCount2
0x180073087  lea     r8, aInverted; "Inverted"
0x18007308e  mov     edx, ebx; cchCount1
0x180073090  mov     rcx, [rsi+8]; lpString1
0x180073094  call    cs:__imp_CompareStringOrdinal
0x18007309b  nop     dword ptr [rax+rax+00h]
0x1800730a0  cmp     eax, 2
0x1800730a3  jnz     short loc_1800730AB
0x1800730a5  mov     byte ptr [rbp+57h+var_50], r14b
0x1800730a9  jmp     short loc_1800730EB
0x1800730ab  mov     [rsp+0A0h+dwOptions], edi; int
0x1800730af  mov     r9d, ebx; cchCount2
0x1800730b2  lea     r8, String1; "Custom"
0x1800730b9  mov     edx, ebx; cchCount1
0x1800730bb  mov     rcx, [rsi+8]; lpString1
0x1800730bf  call    cs:__imp_CompareStringOrdinal
0x1800730c6  nop     dword ptr [rax+rax+00h]
0x1800730cb  cmp     eax, 2
0x1800730ce  jnz     short loc_1800730EB
0x1800730d0  mov     al, byte ptr cs:qword_18039D538+4
0x1800730d6  mov     byte ptr [rbp+57h+var_50+1], al
0x1800730d9  mov     al, byte ptr cs:qword_18039D538+5
0x1800730df  mov     byte ptr [rbp+57h+var_50+2], al
0x1800730e2  mov     al, byte ptr cs:qword_18039D538+6
0x1800730e8  mov     byte ptr [rbp+57h+var_50+3], al
0x1800730eb  mov     ebx, dword ptr cs:qword_18039D538
0x1800730f1  dec     ebx
0x1800730f3  mov     [rbp+57h+var_40], r14
0x1800730f7  lea     r9, [rbp+57h+string]; string
0x1800730fb  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800730ff  mov     edx, 36h ; '6'; length
0x180073104  lea     rcx, ?RuntimeClass_Windows_Internal_Accessibility_Experience_CustomCursor@@3QBGB; "Windows.Internal.Accessibility.Experien"...
0x18007310b  call    cs:__imp_WindowsCreateStringReference
0x180073112  nop     dword ptr [rax+rax+00h]
0x180073117  test    eax, eax
0x180073119  jns     short loc_180073134
0x18007311b  xor     r9d, r9d; lpArguments
0x18007311e  xor     r8d, r8d; nNumberOfArguments
0x180073121  mov     edx, edi; dwExceptionFlags
0x180073123  mov     ecx, 0C000000Dh; dwExceptionCode
0x180073128  call    cs:__imp_RaiseException
0x18007312f  nop     dword ptr [rax+rax+00h]
0x180073134  lea     rdx, [rbp+57h+var_40]
0x180073138  mov     rcx, [rbp+57h+string]
0x18007313c  call    ??$ActivateInstance@V?$ComPtr@UICustomCursor@Experience@Accessibility@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICustomCursor@Experience@Accessibility@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Accessibility::Experience::ICustomCursor>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Accessibility::Experience::ICustomCursor>>)
0x180073141  mov     edi, eax
0x180073143  test    eax, eax
0x180073145  jns     short loc_180073161
0x180073147  mov     rcx, [rbp+5Fh]; this
0x18007314b  mov     r9d, eax; char *
0x18007314e  lea     r8, aShellSystemset_53; "shell\\systemsettingsthreshold\\handler"...
0x180073155  mov     edx, 2F1h; void *
0x18007315a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007315f  jmp     short loc_180073187
0x180073161  mov     rcx, [rbp+57h+var_40]
0x180073165  mov     rax, [rcx]
0x180073168  shl     ebx, 5
0x18007316b  shr     ebx, 1
0x18007316d  lea     edx, [rbx+20h]
0x180073170  mov     r8d, [rbp+57h+var_50]
0x180073174  mov     rax, [rax+30h]
0x180073178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007317d  mov     cs:qword_18039D528, rsi
0x180073184  mov     edi, r14d
0x180073187  lea     rcx, [rbp+57h+var_40]
0x18007318b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180073190  mov     eax, edi
0x180073192  mov     rcx, [rbp+57h+var_18]
0x180073196  xor     rcx, rsp; StackCookie
0x180073199  call    __security_check_cookie
0x18007319e  lea     r11, [rsp+0A0h+var_10]
0x1800731a6  mov     rbx, [r11+20h]
0x1800731aa  mov     rsi, [r11+30h]
0x1800731ae  mov     rsp, r11
0x1800731b1  pop     r14
0x1800731b3  pop     rdi
0x1800731b4  pop     rbp
0x1800731b5  retn
```
