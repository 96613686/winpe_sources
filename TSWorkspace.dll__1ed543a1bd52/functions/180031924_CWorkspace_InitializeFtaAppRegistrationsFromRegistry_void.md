# CWorkspace::InitializeFtaAppRegistrationsFromRegistry(void)

- ea: `0x180031924`
- end: `0x180031e1a`
- name: `?InitializeFtaAppRegistrationsFromRegistry@CWorkspace@@IEAAJXZ`
- size: `1270`
- prototype: `__int64 __fastcall(CWorkspace *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030dc4`

## callees

- `0x180005500`
- `0x1800055d0`
- `0x18000b1d8`
- `0x18000c3a0`
- `0x18000d8d4`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18000fed8`
- `0x18001e41c`
- `0x18001e5d8`
- `0x18001e610`
- `0x180025950`
- `0x180031924`
- `0x1800512e8`
- `0x18005173c`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180031dda`
- `ADVAPI32!RegCloseKey` at `0x180031dda`
- `ADVAPI32!RegEnumKeyExW` at `0x180031b62`
- `ADVAPI32!RegEnumKeyExW` at `0x180031b62`
- `ADVAPI32!RegOpenKeyExW` at `0x180031a29`
- `ADVAPI32!RegOpenKeyExW` at `0x180031a29`

## string_xrefs

- `0x180031c46`: `CWorkspaceFtaAppRegistration::CreateInstance failed`
- `0x180031d67`: `CWorkspaceFtaAppRegistration::InitializeFromRegistry failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall CWorkspace::InitializeFtaAppRegistrationsFromRegistry(CWorkspace *this)
{
  CWorkspace *v1; // rdi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v3; // rax
  __int64 v4; // rax
  const WCHAR *v5; // rax
  LSTATUS v6; // r12d
  unsigned int v7; // eax
  signed int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v10; // eax
  DWORD v11; // r13d
  LSTATUS v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // eax
  int v16; // r14d
  void *v17; // rsi
  void *v18; // rdi
  int v19; // ebx
  int v20; // eax
  unsigned int v21; // eax
  LPWSTR lpClass; // [rsp+28h] [rbp-340h]
  LPWSTR lpClassa; // [rsp+28h] [rbp-340h]
  struct CWorkspaceFtaAppRegistration *v25; // [rsp+48h] [rbp-320h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-318h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-310h] BYREF
  DWORD i; // [rsp+60h] [rbp-308h]
  CWorkspace *v29; // [rsp+68h] [rbp-300h]
  __int64 v30; // [rsp+70h] [rbp-2F8h]
  _BYTE *v31; // [rsp+78h] [rbp-2F0h]
  _BYTE *v32; // [rsp+80h] [rbp-2E8h]
  _BYTE *v33; // [rsp+88h] [rbp-2E0h]
  _BYTE *v34; // [rsp+90h] [rbp-2D8h]
  _BYTE v35[32]; // [rsp+98h] [rbp-2D0h] BYREF
  _BYTE v36[32]; // [rsp+B8h] [rbp-2B0h] BYREF
  _BYTE v37[32]; // [rsp+D8h] [rbp-290h] BYREF
  _BYTE v38[40]; // [rsp+F8h] [rbp-270h] BYREF
  WCHAR Name[268]; // [rsp+120h] [rbp-248h] BYREF

  v30 = -2;
  v1 = this;
  v29 = this;
  hKey = 0;
  v25 = 0;
  cchName = 260;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      101,
      WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  (*(void (__fastcall **)(__int64))(*((_QWORD *)v1 + 104) + 24LL))((__int64)v1 + 832);
  v3 = std::operator+<unsigned short>(v38, (char *)v1 + 488, L"\\");
  v4 = std::operator+<unsigned short>(v37, v3, L"Resources");
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
  v6 = RegOpenKeyExW(HKEY_CURRENT_USER, v5, 0, 0x20019u, &hKey);
  std::wstring::~wstring(v37);
  std::wstring::~wstring(v38);
  if ( v6 == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v7);
    }
    v8 = 1;
    goto LABEL_51;
  }
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v6 > 0 )
        v9 = (unsigned __int16)v6 | 0x80070000;
      else
        v9 = v6;
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v10, v9);
    }
    if ( v6 > 0 )
      v8 = (unsigned __int16)v6 | 0x80070000;
    else
      v8 = v6;
    goto LABEL_51;
  }
  v11 = 0;
  for ( i = 0; ; i = v11 )
  {
    if ( v6 == 259 )
    {
      v8 = 0;
      goto LABEL_51;
    }
    Name[0] = 0;
    cchName = 260;
    v12 = RegEnumKeyExW(hKey, v11, Name, &cchName, 0, 0, 0, 0);
    v6 = v12;
    if ( !v12 )
      break;
    if ( v12 != 259 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( v12 > 0 )
          v13 = (unsigned __int16)v12 | 0x80070000;
        else
          v13 = v12;
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v14, v13);
      }
      if ( v6 > 0 )
        v8 = (unsigned __int16)v6 | 0x80070000;
      else
        v8 = v6;
      goto LABEL_51;
    }
LABEL_49:
    ++v11;
  }
  if ( v25 )
  {
    TCntPtr<CConfigManager>::SafeRelease(&v25);
    v25 = 0;
    TCntPtr<CConfigManager>::SafeAddRef(&v25);
  }
  v8 = CWorkspaceFtaAppRegistration::CreateInstance(&v25);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(lpClass) = v8;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        105,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v15,
        (__int64)"CWorkspaceFtaAppRegistration::CreateInstance failed",
        lpClass);
    }
    goto LABEL_51;
  }
  v16 = (int)v25;
  v31 = v38;
  v17 = (void *)std::wstring::wstring(v38, Name);
  v32 = v37;
  v18 = (void *)std::wstring::wstring(v37, (char *)v1 + 296);
  v33 = v35;
  v19 = std::wstring::wstring(v35, (char *)v29 + 104);
  v34 = v36;
  v20 = std::wstring::wstring(v36, (char *)v29 + 64);
  v8 = CWorkspaceFtaAppRegistration::InitializeFromRegistry(v16, (int)hKey, v20, v19, v18, v17);
  if ( v8 >= 0 )
  {
    v1 = v29;
    (*(void (__fastcall **)(__int64, struct CWorkspaceFtaAppRegistration *))(*((_QWORD *)v29 + 104) + 8LL))(
      (__int64)v29 + 832,
      v25);
    goto LABEL_49;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v21 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(lpClassa) = v8;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      106,
      (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      v21,
      (__int64)"CWorkspaceFtaAppRegistration::InitializeFromRegistry failed",
      lpClassa);
  }
LABEL_51:
  if ( hKey )
    RegCloseKey(hKey);
  ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(&v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180031924  mov     rax, rsp
0x180031927  push    rdi
0x180031928  push    r12
0x18003192a  push    r13
0x18003192c  push    r14
0x18003192e  push    r15
0x180031930  sub     rsp, 340h
0x180031937  mov     [rsp+368h+var_2F8], 0FFFFFFFFFFFFFFFEh
0x180031940  mov     [rax+10h], rbx
0x180031944  mov     [rax+18h], rsi
0x180031948  mov     rax, cs:__security_cookie
0x18003194f  xor     rax, rsp
0x180031952  mov     [rsp+368h+var_30], rax
0x18003195a  mov     rdi, rcx
0x18003195d  mov     [rsp+368h+var_300], rcx
0x180031962  xor     r15d, r15d
0x180031965  mov     [rsp+368h+hKey], r15
0x18003196a  mov     [rsp+368h+var_320], r15
0x18003196f  mov     [rsp+368h+cchName], 104h
0x180031977  lea     rsi, WPP_GLOBAL_Control
0x18003197e  mov     rax, cs:WPP_GLOBAL_Control
0x180031985  cmp     rax, rsi
0x180031988  jz      short loc_1800319BA
0x18003198a  test    byte ptr [rax+1Ch], 1
0x18003198e  jz      short loc_1800319BA
0x180031990  cmp     byte ptr [rax+19h], 4
0x180031994  jb      short loc_1800319BA
0x180031996  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003199b  lea     edx, [r15+65h]
0x18003199f  mov     r9d, eax
0x1800319a2  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800319a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800319b0  mov     rcx, [rcx+10h]
0x1800319b4  call    WPP_SF_D
0x1800319b9  nop
0x1800319ba  lea     rbx, [rdi+340h]
0x1800319c1  mov     rax, [rbx]
0x1800319c4  mov     rcx, rbx
0x1800319c7  mov     rax, [rax+18h]
0x1800319cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800319d0  lea     rdx, [rdi+1E8h]
0x1800319d7  lea     r8, SubStr; "\\"
0x1800319de  lea     rcx, [rsp+368h+var_270]
0x1800319e6  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x1800319eb  nop
0x1800319ec  lea     r8, aResources; "Resources"
0x1800319f3  mov     rdx, rax
0x1800319f6  lea     rcx, [rsp+368h+var_290]
0x1800319fe  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180031a03  nop
0x180031a04  mov     rcx, rax
0x180031a07  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180031a0c  lea     rcx, [rsp+368h+hKey]
0x180031a11  mov     [rsp+368h+phkResult], rcx; phkResult
0x180031a16  mov     r9d, 20019h; samDesired
0x180031a1c  xor     r8d, r8d; ulOptions
0x180031a1f  mov     rdx, rax; lpSubKey
0x180031a22  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180031a29  call    cs:__imp_RegOpenKeyExW
0x180031a2f  mov     r12d, eax
0x180031a32  lea     rcx, [rsp+368h+var_290]; void *
0x180031a3a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180031a3f  nop
0x180031a40  lea     rcx, [rsp+368h+var_270]; void *
0x180031a48  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180031a4d  cmp     r12d, 2
0x180031a51  jnz     short loc_180031A9D
0x180031a53  mov     rax, cs:WPP_GLOBAL_Control
0x180031a5a  cmp     rax, rsi
0x180031a5d  jz      short loc_180031A8F
0x180031a5f  test    byte ptr [rax+1Ch], 1
0x180031a63  jz      short loc_180031A8F
0x180031a65  cmp     [rax+19h], r12b
0x180031a69  jb      short loc_180031A8F
0x180031a6b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031a70  lea     edx, [r12+64h]
0x180031a75  mov     r9d, eax
0x180031a78  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180031a7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180031a86  mov     rcx, [rcx+10h]
0x180031a8a  call    WPP_SF_D
0x180031a8f  mov     ebx, 1
0x180031a94  mov     [rsp+368h+var_328], ebx
0x180031a98  jmp     loc_180031DD0
0x180031a9d  test    r12d, r12d
0x180031aa0  jz      short loc_180031B13
0x180031aa2  mov     rax, cs:WPP_GLOBAL_Control
0x180031aa9  cmp     rax, rsi
0x180031aac  jz      short loc_180031AF6
0x180031aae  test    byte ptr [rax+1Ch], 8
0x180031ab2  jz      short loc_180031AF6
0x180031ab4  cmp     byte ptr [rax+19h], 2
0x180031ab8  jb      short loc_180031AF6
0x180031aba  test    r12d, r12d
0x180031abd  jg      short loc_180031AC4
0x180031abf  mov     ebx, r12d
0x180031ac2  jmp     short loc_180031ACE
0x180031ac4  movzx   ebx, r12w
0x180031ac8  or      ebx, 80070000h
0x180031ace  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031ad3  mov     edx, 67h ; 'g'
0x180031ad8  mov     dword ptr [rsp+368h+phkResult], ebx
0x180031adc  mov     r9d, eax
0x180031adf  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180031ae6  mov     rcx, cs:WPP_GLOBAL_Control
0x180031aed  mov     rcx, [rcx+10h]
0x180031af1  call    WPP_SF_Dd
0x180031af6  test    r12d, r12d
0x180031af9  jg      short loc_180031B00
0x180031afb  mov     ebx, r12d
0x180031afe  jmp     short loc_180031B0A
0x180031b00  movzx   ebx, r12w
0x180031b04  or      ebx, 80070000h
0x180031b0a  mov     [rsp+368h+var_328], ebx
0x180031b0e  jmp     loc_180031DD0
0x180031b13  mov     r13d, r15d
0x180031b16  mov     [rsp+368h+var_308], r15d
0x180031b1b  cmp     r12d, 103h
0x180031b22  jz      loc_180031DC1
0x180031b28  mov     [rsp+368h+Name], r15w
0x180031b31  mov     [rsp+368h+cchName], 104h
0x180031b39  mov     [rsp+368h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180031b3e  mov     [rsp+368h+lpcchClass], r15; lpcchClass
0x180031b43  mov     [rsp+368h+lpClass], r15; lpClass
0x180031b48  mov     [rsp+368h+phkResult], r15; lpReserved
0x180031b4d  lea     r9, [rsp+368h+cchName]; lpcchName
0x180031b52  lea     r8, [rsp+368h+Name]; lpName
0x180031b5a  mov     edx, r13d; dwIndex
0x180031b5d  mov     rcx, [rsp+368h+hKey]; hKey
0x180031b62  call    cs:__imp_RegEnumKeyExW
0x180031b68  mov     r12d, eax
0x180031b6b  test    eax, eax
0x180031b6d  jz      short loc_180031BEC
0x180031b6f  cmp     eax, 103h
0x180031b74  jz      short loc_180031BE7
0x180031b76  mov     rax, cs:WPP_GLOBAL_Control
0x180031b7d  cmp     rax, rsi
0x180031b80  jz      short loc_180031BCA
0x180031b82  test    byte ptr [rax+1Ch], 8
0x180031b86  jz      short loc_180031BCA
0x180031b88  cmp     byte ptr [rax+19h], 2
0x180031b8c  jb      short loc_180031BCA
0x180031b8e  test    r12d, r12d
0x180031b91  jg      short loc_180031B98
0x180031b93  mov     ebx, r12d
0x180031b96  jmp     short loc_180031BA2
0x180031b98  movzx   ebx, r12w
0x180031b9c  or      ebx, 80070000h
0x180031ba2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031ba7  mov     edx, 68h ; 'h'
0x180031bac  mov     dword ptr [rsp+368h+phkResult], ebx
0x180031bb0  mov     r9d, eax
0x180031bb3  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180031bba  mov     rcx, cs:WPP_GLOBAL_Control
0x180031bc1  mov     rcx, [rcx+10h]
0x180031bc5  call    WPP_SF_Dd
0x180031bca  test    r12d, r12d
0x180031bcd  jg      short loc_180031BD4
0x180031bcf  mov     ebx, r12d
0x180031bd2  jmp     short loc_180031BDE
0x180031bd4  movzx   ebx, r12w
0x180031bd8  or      ebx, 80070000h
0x180031bde  mov     [rsp+368h+var_328], ebx
0x180031be2  jmp     loc_180031DD0
0x180031be7  jmp     loc_180031DB4
0x180031bec  cmp     [rsp+368h+var_320], r15
0x180031bf1  jz      short loc_180031C0C
0x180031bf3  lea     rcx, [rsp+368h+var_320]
0x180031bf8  call    ?SafeRelease@?$TCntPtr@VCConfigManager@@@@AEAAXXZ; TCntPtr<CConfigManager>::SafeRelease(void)
0x180031bfd  mov     [rsp+368h+var_320], r15
0x180031c02  lea     rcx, [rsp+368h+var_320]
0x180031c07  call    ?SafeAddRef@?$TCntPtr@VCConfigManager@@@@AEAAXXZ; TCntPtr<CConfigManager>::SafeAddRef(void)
0x180031c0c  lea     rcx, [rsp+368h+var_320]; struct CWorkspaceFtaAppRegistration **
0x180031c11  call    ?CreateInstance@CWorkspaceFtaAppRegistration@@SAJPEAPEAV1@@Z; CWorkspaceFtaAppRegistration::CreateInstance(CWorkspaceFtaAppRegistration * *)
0x180031c16  mov     ebx, eax
0x180031c18  mov     [rsp+368h+var_328], eax
0x180031c1c  test    eax, eax
0x180031c1e  jns     short loc_180031C72
0x180031c20  mov     rax, cs:WPP_GLOBAL_Control
0x180031c27  cmp     rax, rsi
0x180031c2a  jz      short loc_180031C6D
0x180031c2c  test    byte ptr [rax+1Ch], 8
0x180031c30  jz      short loc_180031C6D
0x180031c32  cmp     byte ptr [rax+19h], 2
0x180031c36  jb      short loc_180031C6D
0x180031c38  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031c3d  mov     edx, 69h ; 'i'
0x180031c42  mov     dword ptr [rsp+368h+lpClass], ebx
0x180031c46  lea     rcx, aCworkspaceftaa_1; "CWorkspaceFtaAppRegistration::CreateIns"...
0x180031c4d  mov     [rsp+368h+phkResult], rcx
0x180031c52  mov     r9d, eax
0x180031c55  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180031c5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c63  mov     rcx, [rcx+10h]
0x180031c67  call    WPP_SF_DsD
0x180031c6c  nop
0x180031c6d  jmp     loc_180031DD0
0x180031c72  mov     r14, [rsp+368h+var_320]
0x180031c77  lea     rax, [rsp+368h+var_270]
0x180031c7f  mov     [rsp+368h+var_2F0], rax
0x180031c84  lea     rdx, [rsp+368h+Name]
0x180031c8c  lea     rcx, [rsp+368h+var_270]
0x180031c94  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180031c99  mov     rsi, rax
0x180031c9c  lea     rax, [rsp+368h+var_290]
0x180031ca4  mov     [rsp+368h+var_2E8], rax
0x180031cac  lea     rdx, [rdi+128h]
0x180031cb3  lea     rcx, [rsp+368h+var_290]
0x180031cbb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180031cc0  mov     rdi, rax
0x180031cc3  lea     rax, [rsp+368h+var_2D0]
0x180031ccb  mov     [rsp+368h+var_2E0], rax
0x180031cd3  mov     rdx, [rsp+368h+var_300]
0x180031cd8  add     rdx, 68h ; 'h'
0x180031cdc  lea     rcx, [rsp+368h+var_2D0]
0x180031ce4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180031ce9  mov     rbx, rax
0x180031cec  lea     rax, [rsp+368h+var_2B0]
0x180031cf4  mov     [rsp+368h+var_2D8], rax
0x180031cfc  mov     rdx, [rsp+368h+var_300]
0x180031d01  add     rdx, 40h ; '@'
0x180031d05  lea     rcx, [rsp+368h+var_2B0]
0x180031d0d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180031d12  nop
0x180031d13  mov     rdx, [rsp+368h+hKey]; int
0x180031d18  mov     [rsp+368h+lpClass], rsi; void *
0x180031d1d  mov     [rsp+368h+phkResult], rdi; void *
0x180031d22  mov     r9, rbx; int
0x180031d25  mov     r8, rax; int
0x180031d28  mov     rcx, r14; int
0x180031d2b  call    ?InitializeFromRegistry@CWorkspaceFtaAppRegistration@@QEAAJPEAUHKEY__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; CWorkspaceFtaAppRegistration::InitializeFromRegistry(HKEY__ *,std::wstring,std::wstring,std::wstring,std::wstring)
0x180031d30  mov     ebx, eax
0x180031d32  mov     [rsp+368h+var_328], eax
0x180031d36  test    eax, eax
0x180031d38  jns     short loc_180031D90
0x180031d3a  mov     rax, cs:WPP_GLOBAL_Control
0x180031d41  lea     rcx, WPP_GLOBAL_Control
0x180031d48  cmp     rax, rcx
0x180031d4b  jz      short loc_180031D8E
0x180031d4d  test    byte ptr [rax+1Ch], 8
0x180031d51  jz      short loc_180031D8E
0x180031d53  cmp     byte ptr [rax+19h], 2
0x180031d57  jb      short loc_180031D8E
0x180031d59  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031d5e  mov     edx, 6Ah ; 'j'
0x180031d63  mov     dword ptr [rsp+368h+lpClass], ebx
0x180031d67  lea     rcx, aCworkspaceftaa_4; "CWorkspaceFtaAppRegistration::Initializ"...
0x180031d6e  mov     [rsp+368h+phkResult], rcx
0x180031d73  mov     r9d, eax
0x180031d76  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180031d7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031d84  mov     rcx, [rcx+10h]
0x180031d88  call    WPP_SF_DsD
0x180031d8d  nop
0x180031d8e  jmp     short loc_180031DD0
0x180031d90  mov     rdi, [rsp+368h+var_300]
0x180031d95  lea     rcx, [rdi+340h]
0x180031d9c  mov     rax, [rcx]
0x180031d9f  mov     rdx, [rsp+368h+var_320]
0x180031da4  mov     rax, [rax+8]
0x180031da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031dad  lea     rsi, WPP_GLOBAL_Control
0x180031db4  inc     r13d
0x180031db7  mov     [rsp+368h+var_308], r13d
0x180031dbc  jmp     loc_180031B1B
0x180031dc1  mov     ebx, r15d
0x180031dc4  mov     [rsp+368h+var_328], ebx
0x180031dc8  jmp     short loc_180031DD0
0x180031dca  jmp     short $+2
0x180031dcc  mov     ebx, [rsp+368h+var_328]
0x180031dd0  mov     rcx, [rsp+368h+hKey]; hKey
0x180031dd5  test    rcx, rcx
0x180031dd8  jz      short loc_180031DE1
0x180031dda  call    cs:__imp_RegCloseKey
0x180031de0  nop
0x180031de1  lea     rcx, [rsp+368h+var_320]
0x180031de6  call    ??1?$ComPlainSmartPtr@VCRadcXmlIcon@@@@QEAA@XZ; ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(void)
0x180031deb  mov     eax, ebx
0x180031ded  mov     rcx, [rsp+368h+var_30]
0x180031df5  xor     rcx, rsp; StackCookie
0x180031df8  call    __security_check_cookie
0x180031dfd  lea     r11, [rsp+368h+var_28]
0x180031e05  mov     rbx, [r11+38h]
0x180031e09  mov     rsi, [r11+40h]
0x180031e0d  mov     rsp, r11
0x180031e10  pop     r15
0x180031e12  pop     r14
0x180031e14  pop     r13
0x180031e16  pop     r12
0x180031e18  pop     rdi
0x180031e19  retn
```
