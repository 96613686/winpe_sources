# WriteLastRunInfo(long,DXDB_UPDATER_TIMESTAMP_EVENT)

- ea: `0x14000d940`
- end: `0x14000dba9`
- name: `?WriteLastRunInfo@@YAJJW4DXDB_UPDATER_TIMESTAMP_EVENT@@@Z`
- size: `617`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140007ad8`
- `0x14000f2a4`

## callees

- `0x140002f40`
- `0x140003f40`
- `0x140005364`
- `0x140005dd8`
- `0x140006484`
- `0x14000a4bc`
- `0x14000a4e0`
- `0x14000d940`
- `0x14000dda4`
- `0x14000df28`
- `0x14000ea40`
- `0x14000efe0`
- `0x14000f080`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000dac7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000db4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000dac7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000db4f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000d999`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000d999`

## string_xrefs

- `0x14000d9ad`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x14000da3f`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x14000dad6`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x14000da80`: `LastUpdaterCallbackTimestamp`
- `0x14000db22`: `LastUpdaterCallbackHresult`
- `0x14000da89`: `LastUpdaterStartTimestamp`
- `0x14000db2b`: `LastUpdaterStartHresult`
- `0x14000db19`: `DxDbUninstallFodReason`
- `0x14000da77`: `DxDbUninstallFodTimestamp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WriteLastRunInfo(int a1, unsigned int a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  time_t *const v5; // rcx
  const wchar_t *v6; // rax
  __int64 v7; // rdx
  char v8; // al
  const WCHAR *v9; // rdx
  int v10; // r8d
  const BYTE *v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // rdx
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  const WCHAR *v16; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  time_t Time; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v22[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v23[16]; // [rsp+60h] [rbp-A0h] BYREF
  char v24[240]; // [rsp+70h] [rbp-90h] BYREF
  BYTE *lpData[2]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  *(_DWORD *)Data = a1;
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\DirectX", 0, 0x2001Fu, &hKey);
  if ( !v3 )
  {
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v23);
    Time = time(v5);
    v22[0] = gmtime(&Time);
    v6 = L"UTC.%F.%T";
    v22[1] = L"UTC.%F.%T";
    do
      ++v6;
    while ( *v6 );
    v22[2] = v6;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v24, v22);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
      v23,
      lpData);
    if ( a2 >= 2 && a2 - 2 >= 2 )
    {
      v7 = 147;
LABEL_8:
      v4 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
        (const char *)0x80070057LL,
        phkResult);
LABEL_9:
      std::wstring::_Tidy_deallocate(lpData);
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v23);
      goto LABEL_27;
    }
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(lpData);
    v11 = (const BYTE *)lpData;
    if ( v8 )
      v11 = lpData[0];
    v12 = RegSetValueExW(hKey, v9, 0, 1u, v11, 2 * v10 + 2);
    if ( v12 )
    {
      v13 = 155;
    }
    else
    {
      if ( a2 )
      {
        v14 = a2 - 1;
        if ( v14 )
        {
          v15 = v14 - 1;
          if ( v15 )
          {
            if ( v15 != 1 )
            {
              v7 = 165;
              goto LABEL_8;
            }
            v16 = L"DxDbOOBESkipHresult";
          }
          else
          {
            v16 = L"DxDbUninstallFodReason";
          }
        }
        else
        {
          v16 = L"LastUpdaterCallbackHresult";
        }
      }
      else
      {
        v16 = L"LastUpdaterStartHresult";
      }
      v12 = RegSetValueExW(hKey, v16, 0, 4u, Data, 4u);
      if ( !v12 )
      {
        std::wstring::_Tidy_deallocate(lpData);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v23);
        v4 = 0;
        goto LABEL_27;
      }
      v13 = 173;
    }
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v13,
           (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
           (const char *)v12,
           phkResult);
    goto LABEL_9;
  }
  v4 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x83,
         (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
         (const char *)v3,
         phkResult);
LABEL_27:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v4;
}

```

## disassembly

```asm
0x14000d940  mov     [rsp-8+arg_8], rbx
0x14000d945  mov     [rsp-8+arg_10], rdi
0x14000d94a  push    rbp
0x14000d94b  lea     rbp, [rsp-90h]
0x14000d953  sub     rsp, 190h
0x14000d95a  mov     rax, cs:__security_cookie
0x14000d961  xor     rax, rsp
0x14000d964  mov     [rbp+90h+var_10], rax
0x14000d96b  mov     ebx, edx
0x14000d96d  mov     dword ptr [rsp+190h+Data], ecx
0x14000d971  xor     edi, edi
0x14000d973  mov     [rsp+190h+hKey], rdi
0x14000d978  lea     rax, [rsp+190h+hKey]
0x14000d97d  mov     [rsp+190h+phkResult], rax; int
0x14000d982  mov     r9d, 2001Fh; samDesired
0x14000d988  xor     r8d, r8d; ulOptions
0x14000d98b  lea     rdx, SubKey; "Software\\Microsoft\\DirectX"
0x14000d992  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000d999  call    cs:__imp_RegOpenKeyExW
0x14000d99f  test    eax, eax
0x14000d9a1  jz      short loc_14000D9C5
0x14000d9a3  mov     rcx, [rbp+98h]; this
0x14000d9aa  mov     r9d, eax; char *
0x14000d9ad  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x14000d9b4  mov     edx, 83h; void *
0x14000d9b9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000d9be  mov     ebx, eax
0x14000d9c0  jmp     loc_14000DB79
0x14000d9c5  lea     rcx, [rsp+190h+var_130]
0x14000d9ca  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x14000d9cf  nop
0x14000d9d0  call    time
0x14000d9d5  mov     [rsp+190h+Time], rax
0x14000d9da  lea     rcx, [rsp+190h+Time]; Time
0x14000d9df  call    gmtime
0x14000d9e4  mov     [rsp+190h+var_148], rax
0x14000d9e9  lea     rax, aUtcFT; "UTC.%F.%T"
0x14000d9f0  mov     [rsp+190h+var_140], rax
0x14000d9f5  add     rax, 2
0x14000d9f9  cmp     [rax], di
0x14000d9fc  jnz     short loc_14000D9F5
0x14000d9fe  mov     [rsp+190h+var_138], rax
0x14000da03  lea     rdx, [rsp+190h+var_148]
0x14000da08  lea     rcx, [rsp+190h+var_120]
0x14000da0d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBU?$_Timeobj@GPEBUtm@@@0@@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,std::_Timeobj<ushort,tm const *> const &)
0x14000da12  lea     rdx, [rbp+90h+lpData]
0x14000da16  lea     rcx, [rsp+190h+var_130]
0x14000da1b  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x14000da20  mov     ecx, ebx
0x14000da22  test    ebx, ebx
0x14000da24  jz      short loc_14000DA89
0x14000da26  sub     ecx, 1
0x14000da29  jz      short loc_14000DA80
0x14000da2b  sub     ecx, 1
0x14000da2e  jz      short loc_14000DA77
0x14000da30  cmp     ecx, 1
0x14000da33  jz      short loc_14000DA6E
0x14000da35  mov     edx, 93h; void *
0x14000da3a  mov     ebx, 80070057h
0x14000da3f  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x14000da46  mov     r9d, ebx; char *
0x14000da49  mov     rcx, [rbp+98h]; this
0x14000da50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000da55  lea     rcx, [rbp+90h+lpData]
0x14000da59  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000da5e  nop
0x14000da5f  lea     rcx, [rsp+190h+var_130]
0x14000da64  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x14000da69  jmp     loc_14000DB79
0x14000da6e  lea     rdx, aLastoobeskipti; "LastOOBESkipTimestamp"
0x14000da75  jmp     short loc_14000DA90
0x14000da77  lea     rdx, aDxdbuninstallf; "DxDbUninstallFodTimestamp"
0x14000da7e  jmp     short loc_14000DA90
0x14000da80  lea     rdx, aLastupdatercal; "LastUpdaterCallbackTimestamp"
0x14000da87  jmp     short loc_14000DA90
0x14000da89  lea     rdx, aLastupdatersta; "LastUpdaterStartTimestamp"
0x14000da90  mov     r8d, [rbp+90h+var_20]
0x14000da94  lea     rcx, [rbp+90h+lpData]
0x14000da98  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x14000da9d  lea     rcx, [rbp+90h+lpData]
0x14000daa1  test    al, al
0x14000daa3  cmovnz  rcx, [rbp+90h+lpData]
0x14000daa8  lea     eax, ds:2[r8*2]
0x14000dab0  mov     [rsp+190h+cbData], eax; cbData
0x14000dab4  mov     [rsp+190h+phkResult], rcx; unsigned int
0x14000dab9  mov     r9d, 1; dwType
0x14000dabf  xor     r8d, r8d; Reserved
0x14000dac2  mov     rcx, [rsp+190h+hKey]; hKey
0x14000dac7  call    cs:__imp_RegSetValueExW
0x14000dacd  test    eax, eax
0x14000dacf  jz      short loc_14000DAF3
0x14000dad1  mov     edx, 9Bh; void *
0x14000dad6  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x14000dadd  mov     r9d, eax; char *
0x14000dae0  mov     rcx, [rbp+98h]; this
0x14000dae7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000daec  mov     ebx, eax
0x14000daee  jmp     loc_14000DA55
0x14000daf3  test    ebx, ebx
0x14000daf5  jz      short loc_14000DB2B
0x14000daf7  sub     ebx, 1
0x14000dafa  jz      short loc_14000DB22
0x14000dafc  sub     ebx, 1
0x14000daff  jz      short loc_14000DB19
0x14000db01  cmp     ebx, 1
0x14000db04  jz      short loc_14000DB10
0x14000db06  mov     edx, 0A5h
0x14000db0b  jmp     loc_14000DA3A
0x14000db10  lea     rdx, aDxdboobeskiphr; "DxDbOOBESkipHresult"
0x14000db17  jmp     short loc_14000DB32
0x14000db19  lea     rdx, aDxdbuninstallf_0; "DxDbUninstallFodReason"
0x14000db20  jmp     short loc_14000DB32
0x14000db22  lea     rdx, aLastupdatercal_0; "LastUpdaterCallbackHresult"
0x14000db29  jmp     short loc_14000DB32
0x14000db2b  lea     rdx, ValueName; "LastUpdaterStartHresult"
0x14000db32  mov     r9d, 4; dwType
0x14000db38  mov     [rsp+190h+cbData], r9d; cbData
0x14000db3d  lea     rax, [rsp+190h+Data]
0x14000db42  mov     [rsp+190h+phkResult], rax; lpData
0x14000db47  xor     r8d, r8d; Reserved
0x14000db4a  mov     rcx, [rsp+190h+hKey]; hKey
0x14000db4f  call    cs:__imp_RegSetValueExW
0x14000db55  test    eax, eax
0x14000db57  jz      short loc_14000DB63
0x14000db59  mov     edx, 0ADh
0x14000db5e  jmp     loc_14000DAD6
0x14000db63  lea     rcx, [rbp+90h+lpData]
0x14000db67  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000db6c  nop
0x14000db6d  lea     rcx, [rsp+190h+var_130]
0x14000db72  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x14000db77  mov     ebx, edi
0x14000db79  lea     rcx, [rsp+190h+hKey]
0x14000db7e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000db83  mov     eax, ebx
0x14000db85  mov     rcx, [rbp+90h+var_10]
0x14000db8c  xor     rcx, rsp; StackCookie
0x14000db8f  call    __security_check_cookie
0x14000db94  lea     r11, [rsp+190h+var_s0]
0x14000db9c  mov     rbx, [r11+18h]
0x14000dba0  mov     rdi, [r11+20h]
0x14000dba4  mov     rsp, r11
0x14000dba7  pop     rbp
0x14000dba8  retn
```
