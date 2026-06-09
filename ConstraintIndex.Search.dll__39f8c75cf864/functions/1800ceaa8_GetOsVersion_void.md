# GetOsVersion(void)

- ea: `0x1800ceaa8`
- end: `0x1800ced69`
- name: `?GetOsVersion@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ce76c`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x180009fa0`
- `0x18003e1c4`
- `0x18003e940`
- `0x1800999d0`
- `0x1800ceaa8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800ceafb`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800ceafb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ceb70`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800cebc1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800cec3d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800cecbe`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ceb70`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800cebc1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800cec3d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800cecbe`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800cec4e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800cec4e`

## string_xrefs

- `0x1800ceb0c`: `shellcommon\shell\cortana\Common\Utilities\Inc\OsVersionHelpers.h`
- `0x1800cec62`: `shellcommon\shell\cortana\Common\Utilities\Inc\OsVersionHelpers.h`
- `0x1800ced1a`: `shellcommon\shell\cortana\Common\Utilities\Inc\OsVersionHelpers.h`

## pseudocode

```c
__int64 __fastcall GetOsVersion(__int64 a1)
{
  const char *v2; // r9
  DWORD dwBuildNumber; // r14d
  int v4; // ebx
  int v5; // eax
  int pdwType; // [rsp+20h] [rbp-E0h]
  LPDWORD pdwTypea; // [rsp+20h] [rbp-E0h]
  int pdwTypeb; // [rsp+20h] [rbp-E0h]
  PVOID pvData; // [rsp+28h] [rbp-D8h]
  LPDWORD pcbData; // [rsp+30h] [rbp-D0h]
  DWORD dwMajorVersion; // [rsp+54h] [rbp-ACh] BYREF
  int dwMinorVersion; // [rsp+58h] [rbp-A8h] BYREF
  int v14; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD v15; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v16; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD v17; // [rsp+68h] [rbp-98h] BYREF
  DWORD v18[4]; // [rsp+70h] [rbp-90h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v20; // [rsp+194h] [rbp+94h]
  unsigned __int16 v21; // [rsp+196h] [rbp+96h]
  wchar_t v22[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  wchar_t v23[104]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *(_QWORD *)v18 = a1;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&VersionInformation) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x10,
      (unsigned int)"shellcommon\\shell\\cortana\\Common\\Utilities\\Inc\\OsVersionHelpers.h",
      v2);
  dwBuildNumber = VersionInformation.dwBuildNumber;
  dwMajorVersion = VersionInformation.dwMajorVersion;
  dwMinorVersion = VersionInformation.dwMinorVersion;
  v15 = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
         L"CurrentMajorVersionNumber",
         0x10u,
         0,
         &dwMajorVersion,
         &v15)
    || dwMajorVersion < VersionInformation.dwMajorVersion )
  {
    dwMajorVersion = VersionInformation.dwMajorVersion;
  }
  else
  {
    v16 = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
           L"CurrentMinorVersionNumber",
           0x10u,
           0,
           &dwMinorVersion,
           &v16)
      || dwMajorVersion <= VersionInformation.dwMajorVersion && dwMinorVersion <= VersionInformation.dwMinorVersion )
    {
      dwMinorVersion = VersionInformation.dwMinorVersion;
    }
    else
    {
      v17 = 32;
      memset(v22, 0, sizeof(v22));
      if ( !RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
              L"CurrentBuild",
              2u,
              0,
              v22,
              &v17) )
      {
        dwBuildNumber = _o__wtoi(v22);
        if ( !dwBuildNumber )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x28,
            (unsigned int)"shellcommon\\shell\\cortana\\Common\\Utilities\\Inc\\OsVersionHelpers.h",
            (const char *)0x8000FFFFLL,
            pdwType);
      }
    }
  }
  v4 = 0;
  v18[0] = 4;
  v14 = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
          L"UBR",
          0x10u,
          0,
          &v14,
          v18) )
    v4 = v14;
  LODWORD(pcbData) = v21;
  LODWORD(pvData) = v20;
  LODWORD(pdwTypea) = dwMinorVersion;
  v5 = StringCchPrintfW(v23, 0x64u, L"%d.%d.%d.%d.%d.%d", dwMajorVersion, pdwTypea, pvData, pcbData, dwBuildNumber, v4);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"shellcommon\\shell\\cortana\\Common\\Utilities\\Inc\\OsVersionHelpers.h",
      (const char *)(unsigned int)v5,
      pdwTypeb);
  std::wstring::wstring(a1, v23);
  return a1;
}

```

## disassembly

```asm
0x1800ceaa8  mov     [rsp-8+arg_8], rbx
0x1800ceaad  mov     [rsp-8+arg_10], rdi
0x1800ceab2  push    rbp
0x1800ceab3  push    r13
0x1800ceab5  push    r14
0x1800ceab7  lea     rbp, [rsp-1A0h]
0x1800ceabf  sub     rsp, 2A0h
0x1800ceac6  mov     rax, cs:__security_cookie
0x1800ceacd  xor     rax, rsp
0x1800cead0  mov     [rbp+1B0h+var_20], rax
0x1800cead7  mov     rdi, rcx
0x1800ceada  mov     qword ptr [rsp+2B0h+var_240], rcx
0x1800ceadf  lea     rcx, [rbp+1B0h+VersionInformation.dwMajorVersion]; void *
0x1800ceae3  xor     edx, edx; Val
0x1800ceae5  mov     r8d, 118h; Size
0x1800ceaeb  call    memset_0
0x1800ceaf0  lea     rcx, [rbp+1B0h+VersionInformation]; lpVersionInformation
0x1800ceaf4  mov     [rbp+1B0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800ceafb  call    cs:__imp_GetVersionExW
0x1800ceb01  test    eax, eax
0x1800ceb03  jnz     short loc_1800CEB1C
0x1800ceb05  mov     rcx, [rbp+1B8h]; this
0x1800ceb0c  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\cortana\\Common\\Ut"...
0x1800ceb13  lea     edx, [rax+10h]; void *
0x1800ceb16  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800ceb1c  mov     eax, [rbp+1B0h+VersionInformation.dwMajorVersion]
0x1800ceb1f  lea     r8, aCurrentmajorve; "CurrentMajorVersionNumber"
0x1800ceb26  mov     r14d, [rbp+1B0h+VersionInformation.dwBuildNumber]
0x1800ceb2a  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800ceb31  mov     [rsp+2B0h+var_25C], eax
0x1800ceb35  mov     ebx, 4
0x1800ceb3a  mov     eax, [rbp+1B0h+VersionInformation.dwMinorVersion]
0x1800ceb3d  mov     r13, 0FFFFFFFF80000002h
0x1800ceb44  mov     [rsp+2B0h+var_258], eax
0x1800ceb48  mov     rcx, r13; hkey
0x1800ceb4b  lea     rax, [rsp+2B0h+var_250]
0x1800ceb50  mov     [rsp+2B0h+var_250], ebx
0x1800ceb54  mov     [rsp+2B0h+pcbData], rax; pcbData
0x1800ceb59  lea     r9d, [rbx+0Ch]; dwFlags
0x1800ceb5d  lea     rax, [rsp+2B0h+var_25C]
0x1800ceb62  mov     [rsp+2B0h+pvData], rax; pvData
0x1800ceb67  mov     [rsp+2B0h+pdwType], 0; pdwType
0x1800ceb70  call    cs:__imp_RegGetValueW
0x1800ceb76  mov     ecx, [rbp+1B0h+VersionInformation.dwMajorVersion]
0x1800ceb79  test    eax, eax
0x1800ceb7b  jnz     loc_1800CEC7E
0x1800ceb81  cmp     [rsp+2B0h+var_25C], ecx
0x1800ceb85  jb      loc_1800CEC7E
0x1800ceb8b  lea     rax, [rsp+2B0h+var_24C]
0x1800ceb90  mov     [rsp+2B0h+var_24C], ebx
0x1800ceb94  mov     [rsp+2B0h+pcbData], rax; pcbData
0x1800ceb99  lea     r9d, [rbx+0Ch]; dwFlags
0x1800ceb9d  lea     rax, [rsp+2B0h+var_258]
0x1800ceba2  mov     rcx, r13; hkey
0x1800ceba5  mov     [rsp+2B0h+pvData], rax; pvData
0x1800cebaa  lea     r8, aCurrentminorve; "CurrentMinorVersionNumber"
0x1800cebb1  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800cebb8  mov     [rsp+2B0h+pdwType], 0; pdwType
0x1800cebc1  call    cs:__imp_RegGetValueW
0x1800cebc7  mov     ecx, [rbp+1B0h+VersionInformation.dwMinorVersion]
0x1800cebca  test    eax, eax
0x1800cebcc  jnz     loc_1800CEC78
0x1800cebd2  mov     eax, [rbp+1B0h+VersionInformation.dwMajorVersion]
0x1800cebd5  cmp     [rsp+2B0h+var_25C], eax
0x1800cebd9  ja      short loc_1800CEBE5
0x1800cebdb  cmp     [rsp+2B0h+var_258], ecx
0x1800cebdf  jbe     loc_1800CEC78
0x1800cebe5  xor     eax, eax
0x1800cebe7  mov     [rsp+2B0h+var_248], 20h ; ' '
0x1800cebef  mov     [rbp+1B0h+var_110], ax
0x1800cebf6  lea     r8, aCurrentbuild; "CurrentBuild"
0x1800cebfd  xorps   xmm0, xmm0
0x1800cec00  lea     rax, [rsp+2B0h+var_248]
0x1800cec05  mov     [rsp+2B0h+pcbData], rax; pcbData
0x1800cec0a  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800cec11  lea     rax, [rbp+1B0h+var_110]
0x1800cec18  mov     r9d, 2; dwFlags
0x1800cec1e  mov     [rsp+2B0h+pvData], rax; pvData
0x1800cec23  mov     rcx, r13; hkey
0x1800cec26  movups  xmmword ptr [rbp+1B0h+var_10E], xmm0
0x1800cec2d  mov     [rsp+2B0h+pdwType], 0; int
0x1800cec36  movups  xmmword ptr [rbp+1B0h+var_10E+0Eh], xmm0
0x1800cec3d  call    cs:__imp_RegGetValueW
0x1800cec43  test    eax, eax
0x1800cec45  jnz     short loc_1800CEC82
0x1800cec47  lea     rcx, [rbp+1B0h+var_110]
0x1800cec4e  call    cs:__imp__o__wtoi
0x1800cec54  mov     r14d, eax
0x1800cec57  test    eax, eax
0x1800cec59  jnz     short loc_1800CEC82
0x1800cec5b  mov     rcx, [rbp+1B8h]; this
0x1800cec62  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\cortana\\Common\\Ut"...
0x1800cec69  mov     r9d, 8000FFFFh; char *
0x1800cec6f  lea     edx, [rax+28h]; void *
0x1800cec72  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800cec78  mov     [rsp+2B0h+var_258], ecx
0x1800cec7c  jmp     short loc_1800CEC82
0x1800cec7e  mov     [rsp+2B0h+var_25C], ecx
0x1800cec82  xor     ebx, ebx
0x1800cec84  mov     [rsp+2B0h+var_240], 4
0x1800cec8c  lea     rax, [rsp+2B0h+var_240]
0x1800cec91  mov     [rsp+2B0h+var_254], ebx
0x1800cec95  mov     [rsp+2B0h+pcbData], rax; pcbData
0x1800cec9a  lea     r8, aUbr; "UBR"
0x1800ceca1  lea     rax, [rsp+2B0h+var_254]
0x1800ceca6  mov     rcx, r13; hkey
0x1800ceca9  mov     [rsp+2B0h+pvData], rax; pvData
0x1800cecae  lea     r9d, [rbx+10h]; dwFlags
0x1800cecb2  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800cecb9  mov     [rsp+2B0h+pdwType], rbx; pdwType
0x1800cecbe  call    cs:__imp_RegGetValueW
0x1800cecc4  movzx   ecx, [rbp+1B0h+var_11C]
0x1800ceccb  lea     r8, aDDDDDD; "%d.%d.%d.%d.%d.%d"
0x1800cecd2  mov     r9d, [rsp+2B0h+var_25C]
0x1800cecd7  test    eax, eax
0x1800cecd9  movzx   eax, [rbp+1B0h+var_11A]
0x1800cece0  mov     edx, 64h ; 'd'; unsigned __int64
0x1800cece5  cmovz   ebx, [rsp+2B0h+var_254]
0x1800cecea  mov     [rsp+2B0h+var_270], ebx
0x1800cecee  mov     [rsp+2B0h+var_278], r14d
0x1800cecf3  mov     dword ptr [rsp+2B0h+pcbData], eax
0x1800cecf7  mov     eax, [rsp+2B0h+var_258]
0x1800cecfb  mov     dword ptr [rsp+2B0h+pvData], ecx
0x1800cecff  lea     rcx, [rbp+1B0h+var_F0]; wchar_t *
0x1800ced06  mov     dword ptr [rsp+2B0h+pdwType], eax; int
0x1800ced0a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ced0f  test    eax, eax
0x1800ced11  jns     short loc_1800CED2F
0x1800ced13  mov     rcx, [rbp+1B8h]; this
0x1800ced1a  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\cortana\\Common\\Ut"...
0x1800ced21  mov     r9d, eax; char *
0x1800ced24  mov     edx, 3Fh ; '?'; void *
0x1800ced29  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800ced2f  lea     rdx, [rbp+1B0h+var_F0]
0x1800ced36  mov     rcx, rdi
0x1800ced39  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800ced3e  mov     rax, rdi
0x1800ced41  mov     rcx, [rbp+1B0h+var_20]
0x1800ced48  xor     rcx, rsp; StackCookie
0x1800ced4b  call    __security_check_cookie
0x1800ced50  lea     r11, [rsp+2B0h+var_10]
0x1800ced58  mov     rbx, [r11+28h]
0x1800ced5c  mov     rdi, [r11+30h]
0x1800ced60  mov     rsp, r11
0x1800ced63  pop     r14
0x1800ced65  pop     r13
0x1800ced67  pop     rbp
0x1800ced68  retn
```
