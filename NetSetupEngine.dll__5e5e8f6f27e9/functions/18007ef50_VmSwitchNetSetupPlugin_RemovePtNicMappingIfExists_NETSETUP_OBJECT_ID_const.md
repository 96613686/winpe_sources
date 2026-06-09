# VmSwitchNetSetupPlugin::RemovePtNicMappingIfExists(_NETSETUP_OBJECT_ID const &)

- ea: `0x18007ef50`
- end: `0x18007f24e`
- name: `?RemovePtNicMappingIfExists@VmSwitchNetSetupPlugin@@AEAAXAEBU_NETSETUP_OBJECT_ID@@@Z`
- size: `766`
- prototype: `void __fastcall(VmSwitchNetSetupPlugin *__hidden this, const struct _NETSETUP_OBJECT_ID *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18002ef78`

## callees

- `0x180005410`
- `0x180028a90`
- `0x180029d20`
- `0x18004f104`
- `0x180052620`
- `0x180052698`
- `0x18005b034`
- `0x18005c848`
- `0x180065035`
- `0x18007ef50`
- `0x18007f5a0`
- `0x1800810d0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18007f03b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18007f03b`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18007efc8`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18007efc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007efd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007efd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f051`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18007f1d5`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18007f1d5`

## string_xrefs

- `0x18007efc1`: `ntdll.dll`
- `0x18007f05e`: `System\CurrentControlSet\Services\VmsMp\Parameters`
- `0x18007f110`: `System\CurrentControlSet\Services\VmsMp\Parameters`
- `0x18007f13d`: `System\CurrentControlSet\Services\VmsMp\Parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VmSwitchNetSetupPlugin::RemovePtNicMappingIfExists(
        VmSwitchNetSetupPlugin *this,
        const struct _NETSETUP_OBJECT_ID *a2)
{
  HMODULE Library; // rbx
  DWORD LastError; // eax
  signed int v5; // esi
  FARPROC ProcAddress; // rax
  DWORD v7; // eax
  signed int v8; // esi
  unsigned int v9; // esi
  const WCHAR *v10; // rdx
  LSTATUS v11; // eax
  __int64 v12; // rdx
  LPCWSTR *v13; // r9
  _BYTE pExceptionObject[208]; // [rsp+50h] [rbp-B8h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+120h] [rbp+18h] BYREF
  unsigned __int64 v16; // [rsp+138h] [rbp+30h]
  int v17; // [rsp+140h] [rbp+38h] BYREF
  _BYTE v18[80]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v19[528]; // [rsp+198h] [rbp+90h] BYREF

  v17 = 0;
  StringFromGuid<40>((char *)a2 + 4, v18);
  v16 = 7;
  lpSubKey[2] = 0;
  LOWORD(lpSubKey[0]) = 0;
  VerifyOnline(*(_QWORD *)this);
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  if ( !Library )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids, LastError);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v5);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation");
  if ( ProcAddress )
  {
    v9 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, const wchar_t *, _QWORD, _BYTE *, int, int *))ProcAddress)(
           L"VmSwitchParameters",
           0,
           L"System\\CurrentControlSet\\Services\\VmsMp\\Parameters",
           0,
           v19,
           520,
           &v17);
    if ( v9 )
    {
      std::wstring::assign(lpSubKey, L"System\\CurrentControlSet\\Services\\VmsMp\\Parameters");
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids, v9);
    }
    else
    {
      std::wstring::assign(lpSubKey, v19);
    }
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 == 127 )
    {
      std::wstring::assign(lpSubKey, L"System\\CurrentControlSet\\Services\\VmsMp\\Parameters");
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)(v8 - 100),
          WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids);
    }
    else if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids, v7);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v8);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  std::wstring::append(lpSubKey, L"\\");
  std::wstring::append(lpSubKey, L"NicList");
  std::wstring::append(lpSubKey, L"\\");
  std::wstring::append(lpSubKey, L"/Device/");
  std::wstring::append(lpSubKey, v18);
  v10 = (const WCHAR *)lpSubKey;
  if ( v16 >= 8 )
    v10 = lpSubKey[0];
  v11 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, v10);
  if ( (v11 & 0xFFFFFFFD) != 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v13 = lpSubKey;
    if ( v16 >= 8 )
      LODWORD(v13) = lpSubKey[0];
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      (unsigned int)WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids,
      (_DWORD)v13,
      v11);
  }
  LOBYTE(v12) = 1;
  std::wstring::_Tidy(lpSubKey, v12, 0);
}

```

## disassembly

```asm
0x18007ef50  mov     rax, rsp
0x18007ef53  push    rbp
0x18007ef54  lea     rbp, [rax-2B8h]
0x18007ef5b  sub     rsp, 3B0h
0x18007ef62  mov     qword ptr [rsp+3B0h+var_370], 0FFFFFFFFFFFFFFFEh
0x18007ef6b  mov     [rax+18h], rbx
0x18007ef6f  mov     [rax+20h], rsi
0x18007ef73  mov     rax, cs:__security_cookie
0x18007ef7a  xor     rax, rsp
0x18007ef7d  mov     [rbp+2B0h+var_10], rax
0x18007ef84  mov     rbx, rcx
0x18007ef87  mov     [rbp+2B0h+var_278], 0
0x18007ef8e  lea     rcx, [rdx+4]
0x18007ef92  lea     rdx, [rbp+2B0h+var_270]
0x18007ef96  call    ??$StringFromGuid@$0CI@@@YAXAEBU_GUID@@AEAY0CI@_WW4GuidConvertOptions@@@Z; StringFromGuid<40>(_GUID const &,wchar_t (&)[40],GuidConvertOptions)
0x18007ef9b  mov     [rbp+2B0h+var_280], 7
0x18007efa3  mov     [rbp+2B0h+var_288], 0
0x18007efab  xor     eax, eax
0x18007efad  mov     word ptr [rbp+2B0h+lpSubKey], ax
0x18007efb1  mov     rcx, [rbx]
0x18007efb4  call    VerifyOnline
0x18007efb9  xor     edx, edx; hFile
0x18007efbb  mov     r8d, 800h; dwFlags
0x18007efc1  lea     rcx, ModuleName; "ntdll.dll"
0x18007efc8  call    cs:__imp_LoadLibraryExW
0x18007efce  mov     rbx, rax
0x18007efd1  test    rax, rax
0x18007efd4  jnz     short loc_18007F031
0x18007efd6  call    cs:__imp_GetLastError
0x18007efdc  mov     esi, eax
0x18007efde  test    eax, eax
0x18007efe0  jz      short loc_18007F031
0x18007efe2  lea     rbx, WPP_GLOBAL_Control
0x18007efe9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eff0  cmp     rcx, rbx
0x18007eff3  jz      short loc_18007F013
0x18007eff5  cmp     byte ptr [rcx+19h], 2
0x18007eff9  jb      short loc_18007F013
0x18007effb  mov     edx, 1Ah
0x18007f000  mov     r9d, eax
0x18007f003  lea     r8, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids
0x18007f00a  mov     rcx, [rcx+10h]
0x18007f00e  call    WPP_SF_d
0x18007f013  mov     edx, esi; int
0x18007f015  lea     rcx, [rsp+3B0h+pExceptionObject]; this
0x18007f01a  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18007f01f  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18007f026  lea     rcx, [rsp+3B0h+pExceptionObject]; pExceptionObject
0x18007f02b  call    _CxxThrowException_0
0x18007f031  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x18007f038  mov     rcx, rbx; hModule
0x18007f03b  call    cs:__imp_GetProcAddress
0x18007f041  lea     rbx, WPP_GLOBAL_Control
0x18007f048  test    rax, rax
0x18007f04b  jnz     loc_18007F0F0
0x18007f051  call    cs:__imp_GetLastError
0x18007f057  mov     esi, eax
0x18007f059  cmp     eax, 7Fh
0x18007f05c  jnz     short loc_18007F0A0
0x18007f05e  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Vm"...
0x18007f065  lea     rcx, [rbp+2B0h+lpSubKey]
0x18007f069  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::assign(wchar_t const *)
0x18007f06e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f075  cmp     rcx, rbx
0x18007f078  jz      loc_18007F173
0x18007f07e  cmp     byte ptr [rcx+19h], 3
0x18007f082  jb      loc_18007F173
0x18007f088  lea     edx, [rsi-64h]
0x18007f08b  lea     r8, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids
0x18007f092  mov     rcx, [rcx+10h]
0x18007f096  call    WPP_SF_
0x18007f09b  jmp     loc_18007F173
0x18007f0a0  test    esi, esi
0x18007f0a2  jz      loc_18007F173
0x18007f0a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f0af  cmp     rcx, rbx
0x18007f0b2  jz      short loc_18007F0D2
0x18007f0b4  cmp     byte ptr [rcx+19h], 2
0x18007f0b8  jb      short loc_18007F0D2
0x18007f0ba  mov     edx, 1Ch
0x18007f0bf  mov     r9d, esi
0x18007f0c2  lea     r8, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids
0x18007f0c9  mov     rcx, [rcx+10h]
0x18007f0cd  call    WPP_SF_d
0x18007f0d2  mov     edx, esi; int
0x18007f0d4  lea     rcx, [rsp+3B0h+pExceptionObject]; this
0x18007f0d9  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18007f0de  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18007f0e5  lea     rcx, [rsp+3B0h+pExceptionObject]; pExceptionObject
0x18007f0ea  call    _CxxThrowException_0
0x18007f0f0  lea     rcx, [rbp+2B0h+var_278]
0x18007f0f4  mov     [rsp+3B0h+var_380], rcx
0x18007f0f9  mov     dword ptr [rsp+3B0h+var_388], 208h
0x18007f101  lea     rcx, [rbp+2B0h+var_220]
0x18007f108  mov     qword ptr [rsp+3B0h+var_390], rcx
0x18007f10d  xor     r9d, r9d
0x18007f110  lea     r8, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Vm"...
0x18007f117  xor     edx, edx
0x18007f119  lea     rcx, aVmswitchparame; "VmSwitchParameters"
0x18007f120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f125  mov     esi, eax
0x18007f127  lea     rcx, [rbp+2B0h+lpSubKey]
0x18007f12b  test    eax, eax
0x18007f12d  jnz     short loc_18007F13D
0x18007f12f  lea     rdx, [rbp+2B0h+var_220]
0x18007f136  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::assign(wchar_t const *)
0x18007f13b  jmp     short loc_18007F173
0x18007f13d  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Vm"...
0x18007f144  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::assign(wchar_t const *)
0x18007f149  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f150  cmp     rcx, rbx
0x18007f153  jz      short loc_18007F173
0x18007f155  cmp     byte ptr [rcx+19h], 2
0x18007f159  jb      short loc_18007F173
0x18007f15b  mov     edx, 1Dh
0x18007f160  mov     r9d, esi
0x18007f163  lea     r8, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids
0x18007f16a  mov     rcx, [rcx+10h]
0x18007f16e  call    WPP_SF_d
0x18007f173  lea     rdx, asc_1800A2384; "\\"
0x18007f17a  lea     rcx, [rbp+2B0h+lpSubKey]
0x18007f17e  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::append(wchar_t const *)
0x18007f183  lea     rdx, aNiclist; "NicList"
0x18007f18a  lea     rcx, [rbp+2B0h+lpSubKey]
0x18007f18e  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::append(wchar_t const *)
0x18007f193  lea     rdx, asc_1800A2384; "\\"
0x18007f19a  lea     rcx, [rbp+2B0h+lpSubKey]
0x18007f19e  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::append(wchar_t const *)
0x18007f1a3  lea     rdx, aDevice_2; "/Device/"
0x18007f1aa  lea     rcx, [rbp+2B0h+lpSubKey]
0x18007f1ae  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::append(wchar_t const *)
0x18007f1b3  lea     rdx, [rbp+2B0h+var_270]
0x18007f1b7  lea     rcx, [rbp+2B0h+lpSubKey]
0x18007f1bb  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::append(wchar_t const *)
0x18007f1c0  lea     rdx, [rbp+2B0h+lpSubKey]
0x18007f1c4  cmp     [rbp+2B0h+var_280], 8
0x18007f1c9  cmovnb  rdx, [rbp+2B0h+lpSubKey]; lpSubKey
0x18007f1ce  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007f1d5  call    cs:__imp_RegDeleteKeyW
0x18007f1db  test    eax, 0FFFFFFFDh
0x18007f1e0  jz      short loc_18007F21C
0x18007f1e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f1e9  cmp     rcx, rbx
0x18007f1ec  jz      short loc_18007F21C
0x18007f1ee  cmp     byte ptr [rcx+19h], 3
0x18007f1f2  jb      short loc_18007F21C
0x18007f1f4  lea     r9, [rbp+2B0h+lpSubKey]
0x18007f1f8  cmp     [rbp+2B0h+var_280], 8
0x18007f1fd  cmovnb  r9, [rbp+2B0h+lpSubKey]
0x18007f202  mov     edx, 1Eh
0x18007f207  mov     [rsp+3B0h+var_390], eax
0x18007f20b  lea     r8, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids
0x18007f212  mov     rcx, [rcx+10h]
0x18007f216  call    WPP_SF_Sd
0x18007f21b  nop
0x18007f21c  xor     r8d, r8d
0x18007f21f  mov     dl, 1
0x18007f221  lea     rcx, [rbp+2B0h+lpSubKey]
0x18007f225  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18007f22a  mov     rcx, [rbp+2B0h+var_10]
0x18007f231  xor     rcx, rsp; StackCookie
0x18007f234  call    __security_check_cookie
0x18007f239  lea     r11, [rsp+3B0h+var_s0]
0x18007f241  mov     rbx, [r11+20h]
0x18007f245  mov     rsi, [r11+28h]
0x18007f249  mov     rsp, r11
0x18007f24c  pop     rbp
0x18007f24d  retn
```
