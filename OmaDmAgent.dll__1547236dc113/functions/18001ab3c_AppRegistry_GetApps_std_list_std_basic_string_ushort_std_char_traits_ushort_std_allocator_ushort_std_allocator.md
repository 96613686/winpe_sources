# AppRegistry::GetApps(std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,PackageApplicationType)

- ea: `0x18001ab3c`
- end: `0x18001af3a`
- name: `?GetApps@AppRegistry@@QEAAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@W4PackageApplicationType@@@Z`
- size: `1022`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000dcb4`

## callees

- `0x18000212c`
- `0x180002a50`
- `0x1800062ac`
- `0x180009134`
- `0x180009f0c`
- `0x18000a080`
- `0x18000a290`
- `0x18000a2c0`
- `0x18000a6a4`
- `0x18001ab3c`
- `0x18001af40`
- `0x18001f3da`
- `0x18001f420`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18001ae4d`
- `msvcrt!wcscpy_s` at `0x18001ae4d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001af08`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001af08`
- `ADVAPI32!RegCloseKey` at `0x18001aef4`
- `ADVAPI32!RegCloseKey` at `0x18001aef4`
- `ADVAPI32!RegEnumValueW` at `0x18001ad8c`
- `ADVAPI32!RegEnumValueW` at `0x18001ad8c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001acf9`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001acf9`
- `ADVAPI32!RegOpenKeyExW` at `0x18001ac18`
- `ADVAPI32!RegOpenKeyExW` at `0x18001ac18`
- `KERNEL32!GetLastError` at `0x18001ac87`
- `KERNEL32!GetLastError` at `0x18001ad36`
- `KERNEL32!GetLastError` at `0x18001ae05`
- `KERNEL32!GetLastError` at `0x18001aea6`
- `KERNEL32!GetLastError` at `0x18001ac87`
- `KERNEL32!GetLastError` at `0x18001ad36`
- `KERNEL32!GetLastError` at `0x18001ae05`
- `KERNEL32!GetLastError` at `0x18001aea6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppRegistry::GetApps(__int64 a1, __int64 a2)
{
  unsigned __int64 v3; // rax
  WCHAR *v4; // rsi
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  char v7; // di
  char LastError; // al
  int v9; // edx
  LSTATUS v10; // eax
  DWORD i; // edi
  LSTATUS v12; // eax
  char v13; // r14
  int RegSZValue; // eax
  char v15; // r14
  __int64 v16; // rcx
  char v17; // al
  __int64 v18; // rdx
  char v19; // al
  unsigned int *lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  DWORD cchValueName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cValues; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v25[32]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Destination[256]; // [rsp+90h] [rbp-70h] BYREF

  hKey = 0;
  cValues = 0;
  cchValueName = 0x3FFF;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_4f09d0fd1f8630d51627157231414720_Traceguids, 3);
  std::list<std::wstring>::clear(a2);
  v3 = 2LL * cchValueName;
  if ( !is_mul_ok(cchValueName, 2u) )
    v3 = -1;
  v4 = (WCHAR *)operator new[](v3, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v5 = -2147024882;
    goto LABEL_44;
  }
  v6 = RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\AppDB", 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 == 2 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4f09d0fd1f8630d51627157231414720_Traceguids);
      v5 = 0;
      goto LABEL_44;
    }
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    else
      v5 = v6;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_44;
    LastError = GetLastError();
    v9 = 13;
LABEL_20:
    WPP_SF_SdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)WPP_4f09d0fd1f8630d51627157231414720_Traceguids,
      (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\AppDB",
      v7,
      LastError);
    goto LABEL_44;
  }
  v10 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
  v7 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    else
      v5 = v10;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_44;
    LastError = GetLastError();
    v9 = 14;
    goto LABEL_20;
  }
  v5 = 0;
  for ( i = 0; i < cValues; ++i )
  {
    cchValueName = 0x3FFF;
    *v4 = 0;
    v12 = RegEnumValueW(hKey, i, v4, &cchValueName, 0, 0, 0, 0);
    v13 = v12;
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        v19 = GetLastError();
        WPP_SF_SdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_4f09d0fd1f8630d51627157231414720_Traceguids,
          (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\AppDB",
          v13,
          v19);
      }
    }
    else
    {
      memset_0(Destination, 0, 0x1FEu);
      RegSZValue = ReadRegSZValue(
                     (LPBYTE)Destination,
                     0xFFu,
                     HKEY_CURRENT_USER,
                     L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\AppDB",
                     v4,
                     lpcbMaxSubKeyLen);
      v15 = RegSZValue;
      if ( RegSZValue < 0 )
        goto LABEL_35;
      v16 = -1;
      do
        ++v16;
      while ( Destination[v16] );
      if ( !v16 )
      {
LABEL_35:
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          v17 = GetLastError();
          WPP_SF_SdD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)WPP_4f09d0fd1f8630d51627157231414720_Traceguids,
            (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\AppDB",
            v15,
            v17);
        }
        wcscpy_s(Destination, 0xCu, L"Application");
      }
      if ( (unsigned int)GetPackageApplicationTypeFromString(Destination) == 3 )
      {
        std::wstring::wstring(v25, v4);
        std::list<std::wstring>::push_back(a2, v25);
        LOBYTE(v18) = 1;
        std::wstring::_Tidy(v25, v18, 0);
      }
    }
  }
LABEL_44:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 )
    operator delete[](v4);
  return v5;
}

```

## disassembly

```asm
0x18001ab3c  push    rbp
0x18001ab3e  push    rbx
0x18001ab3f  push    rsi
0x18001ab40  push    rdi
0x18001ab41  push    r12
0x18001ab43  push    r13
0x18001ab45  push    r14
0x18001ab47  push    r15
0x18001ab49  lea     rbp, [rsp-1A8h]
0x18001ab51  sub     rsp, 2A8h
0x18001ab58  mov     rax, cs:__security_cookie
0x18001ab5f  xor     rax, rsp
0x18001ab62  mov     [rbp+1E0h+var_50], rax
0x18001ab69  mov     r15, rdx
0x18001ab6c  xor     r12d, r12d
0x18001ab6f  mov     [rsp+2E0h+hKey], r12
0x18001ab74  mov     [rsp+2E0h+cValues], r12d
0x18001ab79  mov     [rsp+2E0h+cchValueName], 3FFFh
0x18001ab81  lea     r13, WPP_GLOBAL_Control
0x18001ab88  lea     r14, WPP_4f09d0fd1f8630d51627157231414720_Traceguids
0x18001ab8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab96  cmp     rcx, r13
0x18001ab99  jz      short loc_18001ABB7
0x18001ab9b  test    byte ptr [rcx+1Ch], 1
0x18001ab9f  jz      short loc_18001ABB7
0x18001aba1  lea     edx, [r12+0Bh]
0x18001aba6  lea     r9d, [r12+3]
0x18001abab  mov     r8, r14
0x18001abae  mov     rcx, [rcx+10h]
0x18001abb2  call    WPP_SF_d
0x18001abb7  mov     rcx, r15
0x18001abba  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::list<std::wstring>::clear(void)
0x18001abbf  mov     ecx, [rsp+2E0h+cchValueName]
0x18001abc3  mov     eax, 2
0x18001abc8  mul     rcx
0x18001abcb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001abd2  cmovb   rax, rcx
0x18001abd6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001abdd  mov     rcx, rax; unsigned __int64
0x18001abe0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001abe5  mov     rsi, rax
0x18001abe8  test    rax, rax
0x18001abeb  jnz     short loc_18001ABF7
0x18001abed  mov     ebx, 8007000Eh
0x18001abf2  jmp     loc_18001AEEA
0x18001abf7  lea     rax, [rsp+2E0h+hKey]
0x18001abfc  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18001ac01  mov     r9d, 20019h; samDesired
0x18001ac07  xor     r8d, r8d; ulOptions
0x18001ac0a  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001ac11  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001ac18  call    cs:__imp_RegOpenKeyExW
0x18001ac1f  nop     dword ptr [rax+rax+00h]
0x18001ac24  mov     edi, eax
0x18001ac26  test    eax, eax
0x18001ac28  jz      loc_18001ACBF
0x18001ac2e  cmp     eax, 2
0x18001ac31  jnz     short loc_18001AC5C
0x18001ac33  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac3a  cmp     rcx, r13
0x18001ac3d  jz      short loc_18001AC54
0x18001ac3f  test    byte ptr [rcx+1Ch], 1
0x18001ac43  jz      short loc_18001AC54
0x18001ac45  lea     edx, [rax+0Ah]
0x18001ac48  mov     r8, r14
0x18001ac4b  mov     rcx, [rcx+10h]
0x18001ac4f  call    WPP_SF_
0x18001ac54  mov     ebx, r12d
0x18001ac57  jmp     loc_18001AEEA
0x18001ac5c  test    edi, edi
0x18001ac5e  jg      short loc_18001AC64
0x18001ac60  mov     ebx, edi
0x18001ac62  jmp     short loc_18001AC6D
0x18001ac64  movzx   ebx, di
0x18001ac67  or      ebx, 80070000h
0x18001ac6d  mov     rax, cs:WPP_GLOBAL_Control
0x18001ac74  cmp     rax, r13
0x18001ac77  jz      loc_18001AEEA
0x18001ac7d  test    byte ptr [rax+1Ch], 4
0x18001ac81  jz      loc_18001AEEA
0x18001ac87  call    cs:__imp_GetLastError
0x18001ac8e  nop     dword ptr [rax+rax+00h]
0x18001ac93  mov     edx, 0Dh
0x18001ac98  mov     dword ptr [rsp+2E0h+lpcbMaxSubKeyLen], eax
0x18001ac9c  mov     dword ptr [rsp+2E0h+phkResult], edi
0x18001aca0  lea     r9, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001aca7  mov     r8, r14
0x18001acaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001acb1  mov     rcx, [rcx+10h]
0x18001acb5  call    WPP_SF_SdD
0x18001acba  jmp     loc_18001AEEA
0x18001acbf  mov     [rsp+2E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18001acc4  mov     [rsp+2E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18001acc9  mov     [rsp+2E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18001acce  mov     [rsp+2E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18001acd3  lea     rax, [rsp+2E0h+cValues]
0x18001acd8  mov     [rsp+2E0h+lpcValues], rax; lpcValues
0x18001acdd  mov     [rsp+2E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18001ace2  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18001ace7  mov     [rsp+2E0h+phkResult], r12; lpcSubKeys
0x18001acec  xor     r9d, r9d; lpReserved
0x18001acef  xor     r8d, r8d; lpcchClass
0x18001acf2  xor     edx, edx; lpClass
0x18001acf4  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001acf9  call    cs:__imp_RegQueryInfoKeyW
0x18001ad00  nop     dword ptr [rax+rax+00h]
0x18001ad05  mov     edi, eax
0x18001ad07  test    eax, eax
0x18001ad09  jz      short loc_18001AD4C
0x18001ad0b  test    eax, eax
0x18001ad0d  jg      short loc_18001AD13
0x18001ad0f  mov     ebx, eax
0x18001ad11  jmp     short loc_18001AD1C
0x18001ad13  movzx   ebx, di
0x18001ad16  or      ebx, 80070000h
0x18001ad1c  mov     rax, cs:WPP_GLOBAL_Control
0x18001ad23  cmp     rax, r13
0x18001ad26  jz      loc_18001AEEA
0x18001ad2c  test    byte ptr [rax+1Ch], 4
0x18001ad30  jz      loc_18001AEEA
0x18001ad36  call    cs:__imp_GetLastError
0x18001ad3d  nop     dword ptr [rax+rax+00h]
0x18001ad42  mov     edx, 0Eh
0x18001ad47  jmp     loc_18001AC98
0x18001ad4c  mov     ebx, r12d
0x18001ad4f  mov     edi, r12d
0x18001ad52  cmp     [rsp+2E0h+cValues], r12d
0x18001ad57  jbe     loc_18001AEEA
0x18001ad5d  mov     [rsp+2E0h+cchValueName], 3FFFh
0x18001ad65  mov     [rsi], r12w
0x18001ad69  mov     [rsp+2E0h+lpcValues], r12; lpcbData
0x18001ad6e  mov     [rsp+2E0h+lpcbMaxClassLen], r12; lpData
0x18001ad73  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r12; unsigned int *
0x18001ad78  mov     [rsp+2E0h+phkResult], r12; lpReserved
0x18001ad7d  lea     r9, [rsp+2E0h+cchValueName]; lpcchValueName
0x18001ad82  mov     r8, rsi; lpValueName
0x18001ad85  mov     edx, edi; dwIndex
0x18001ad87  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001ad8c  call    cs:__imp_RegEnumValueW
0x18001ad93  nop     dword ptr [rax+rax+00h]
0x18001ad98  mov     r14d, eax
0x18001ad9b  test    eax, eax
0x18001ad9d  jnz     loc_18001AE94
0x18001ada3  xor     edx, edx; Val
0x18001ada5  mov     r8d, 1FEh; Size
0x18001adab  lea     rcx, [rbp+1E0h+Destination]; void *
0x18001adaf  call    memset_0
0x18001adb4  mov     [rsp+2E0h+phkResult], rsi; unsigned __int16 *
0x18001adb9  lea     r9, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001adc0  mov     edx, 0FFh; unsigned __int64
0x18001adc5  mov     r8, 0FFFFFFFF80000001h; HKEY
0x18001adcc  lea     rcx, [rbp+1E0h+Destination]; lpData
0x18001add0  call    ?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z; ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001add5  mov     r14d, eax
0x18001add8  test    eax, eax
0x18001adda  js      short loc_18001ADF3
0x18001addc  lea     rax, [rbp+1E0h+Destination]
0x18001ade0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001ade4  inc     rcx
0x18001ade7  cmp     [rax+rcx*2], r12w
0x18001adec  jnz     short loc_18001ADE4
0x18001adee  test    rcx, rcx
0x18001adf1  jnz     short loc_18001AE59
0x18001adf3  mov     rax, cs:WPP_GLOBAL_Control
0x18001adfa  cmp     rax, r13
0x18001adfd  jz      short loc_18001AE3D
0x18001adff  test    byte ptr [rax+1Ch], 4
0x18001ae03  jz      short loc_18001AE3D
0x18001ae05  call    cs:__imp_GetLastError
0x18001ae0c  nop     dword ptr [rax+rax+00h]
0x18001ae11  mov     edx, 0Fh
0x18001ae16  mov     dword ptr [rsp+2E0h+lpcbMaxSubKeyLen], eax
0x18001ae1a  mov     dword ptr [rsp+2E0h+phkResult], r14d
0x18001ae1f  lea     r9, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001ae26  lea     r8, WPP_4f09d0fd1f8630d51627157231414720_Traceguids
0x18001ae2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae34  mov     rcx, [rcx+10h]
0x18001ae38  call    WPP_SF_SdD
0x18001ae3d  lea     r8, aApplication; "Application"
0x18001ae44  mov     edx, 0Ch; SizeInWords
0x18001ae49  lea     rcx, [rbp+1E0h+Destination]; Destination
0x18001ae4d  call    cs:__imp_wcscpy_s
0x18001ae54  nop     dword ptr [rax+rax+00h]
0x18001ae59  lea     rcx, [rbp+1E0h+Destination]
0x18001ae5d  call    ?GetPackageApplicationTypeFromString@@YA?AW4PackageApplicationType@@PEAG@Z; GetPackageApplicationTypeFromString(ushort *)
0x18001ae62  cmp     eax, 3
0x18001ae65  jnz     short loc_18001AEDE
0x18001ae67  mov     rdx, rsi
0x18001ae6a  lea     rcx, [rsp+2E0h+var_270]
0x18001ae6f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001ae74  nop
0x18001ae75  lea     rdx, [rsp+2E0h+var_270]
0x18001ae7a  mov     rcx, r15
0x18001ae7d  call    ?push_back@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::list<std::wstring>::push_back(std::wstring &&)
0x18001ae82  nop
0x18001ae83  xor     r8d, r8d
0x18001ae86  mov     dl, 1
0x18001ae88  lea     rcx, [rsp+2E0h+var_270]
0x18001ae8d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ae92  jmp     short loc_18001AEDE
0x18001ae94  mov     rax, cs:WPP_GLOBAL_Control
0x18001ae9b  cmp     rax, r13
0x18001ae9e  jz      short loc_18001AEDE
0x18001aea0  test    byte ptr [rax+1Ch], 4
0x18001aea4  jz      short loc_18001AEDE
0x18001aea6  call    cs:__imp_GetLastError
0x18001aead  nop     dword ptr [rax+rax+00h]
0x18001aeb2  mov     edx, 10h
0x18001aeb7  mov     dword ptr [rsp+2E0h+lpcbMaxSubKeyLen], eax
0x18001aebb  mov     dword ptr [rsp+2E0h+phkResult], r14d
0x18001aec0  lea     r9, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001aec7  lea     r8, WPP_4f09d0fd1f8630d51627157231414720_Traceguids
0x18001aece  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aed5  mov     rcx, [rcx+10h]
0x18001aed9  call    WPP_SF_SdD
0x18001aede  inc     edi
0x18001aee0  cmp     edi, [rsp+2E0h+cValues]
0x18001aee4  jb      loc_18001AD5D
0x18001aeea  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001aeef  test    rcx, rcx
0x18001aef2  jz      short loc_18001AF00
0x18001aef4  call    cs:__imp_RegCloseKey
0x18001aefb  nop     dword ptr [rax+rax+00h]
0x18001af00  test    rsi, rsi
0x18001af03  jz      short loc_18001AF14
0x18001af05  mov     rcx, rsi
0x18001af08  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001af0f  nop     dword ptr [rax+rax+00h]
0x18001af14  mov     eax, ebx
0x18001af16  mov     rcx, [rbp+1E0h+var_50]
0x18001af1d  xor     rcx, rsp; StackCookie
0x18001af20  call    __security_check_cookie
0x18001af25  add     rsp, 2A8h
0x18001af2c  pop     r15
0x18001af2e  pop     r14
0x18001af30  pop     r13
0x18001af32  pop     r12
0x18001af34  pop     rdi
0x18001af35  pop     rsi
0x18001af36  pop     rbx
0x18001af37  pop     rbp
0x18001af38  retn
```
