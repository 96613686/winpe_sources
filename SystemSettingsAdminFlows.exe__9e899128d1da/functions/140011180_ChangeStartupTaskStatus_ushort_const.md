# ChangeStartupTaskStatus(ushort const *)

- ea: `0x140011180`
- end: `0x140011503`
- name: `?ChangeStartupTaskStatus@@YAJPEBG@Z`
- size: `899`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x140005f30`
- `0x14000d850`
- `0x14000dc6c`
- `0x140011180`
- `0x140012880`
- `0x14001a124`
- `0x140026a44`
- `0x140029eb8`
- `0x14002a3e8`
- `0x14002dcdc`
- `0x14002dd1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400112de`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400112de`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x14001129c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x14001129c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001126b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001126b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001146a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001146a`
- `KERNEL32!RegSetValueExW` at `0x140011497`
- `KERNEL32!RegSetValueExW` at `0x140011497`
- `KERNEL32!LocalFree` at `0x140011457`
- `KERNEL32!LocalFree` at `0x1400114b9`
- `KERNEL32!LocalFree` at `0x1400114d0`
- `KERNEL32!LocalFree` at `0x140011457`
- `KERNEL32!LocalFree` at `0x1400114b9`
- `KERNEL32!LocalFree` at `0x1400114d0`
- `KERNEL32!GetLastError` at `0x1400111c9`
- `KERNEL32!GetLastError` at `0x1400111c9`
- `SHELL32!CommandLineToArgvW` at `0x1400111b7`
- `SHELL32!CommandLineToArgvW` at `0x1400111b7`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x1400112b2`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x1400112b2`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1400112c6`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1400112c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ChangeStartupTaskStatus(const unsigned __int16 *a1)
{
  LPWSTR *v1; // rax
  __int64 v2; // r8
  LPWSTR *v3; // rsi
  signed int LastError; // eax
  unsigned int v5; // ebx
  _DWORD *v7; // r14
  const wchar_t *v8; // rbx
  unsigned __int64 v9; // rdi
  const unsigned __int16 *v10; // r15
  int v11; // r12d
  HKEY v12; // rdx
  const unsigned __int16 *v13; // r8
  unsigned __int64 v14; // rdi
  const unsigned __int16 *v15; // r14
  HKEY v16; // rdx
  const unsigned __int16 *v17; // r8
  int v18; // edi
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  int BlockedItemInfo; // eax
  int pNumArgs; // [rsp+30h] [rbp-29h] BYREF
  HKEY hKey[2]; // [rsp+38h] [rbp-21h] BYREF
  wchar_t *EndPtr[2]; // [rsp+48h] [rbp-11h] BYREF
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v26[32]; // [rsp+68h] [rbp+Fh] BYREF

  pNumArgs = 0;
  v1 = CommandLineToArgvW(a1, &pNumArgs);
  v3 = v1;
  EndPtr[1] = (wchar_t *)v1;
  if ( !v1 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids, v5);
    return v5;
  }
  if ( pNumArgs != 3 )
  {
    v5 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v2, (unsigned int)pNumArgs, -2147024809);
    goto LABEL_44;
  }
  std::wstring::wstring((__int64)v26, (__int64)*v1);
  v7 = (_DWORD *)_o__errno();
  v8 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
  EndPtr[0] = 0;
  *v7 = 0;
  v9 = wcstoull(v8, EndPtr, 10);
  if ( v8 == EndPtr[0] )
  {
    std::_Xinvalid_argument("invalid stoull argument");
    __debugbreak();
  }
  if ( *v7 == 34 )
    std::_Xout_of_range("stoull argument out of range");
  std::wstring::_Tidy_deallocate(v26);
  v10 = v3[1];
  v11 = _o__wtoi(v3[2]);
  memset(SystemTimeAsFileTime, 0, 12);
  StartupDB::StartupApproval::StartupApproval((StartupDB::StartupApproval *)hKey);
  v14 = v9 & 0xFC00000000000000uLL;
  switch ( v14 )
  {
    case 0x8000000000000000uLL:
      v15 = L"Run";
      break;
    case 0x4000000000000000uLL:
      v15 = L"Run32";
      break;
    case 0x1000000000000000uLL:
      v15 = L"StartupFolder";
      break;
    default:
      StartupDB::StartupApproval::Uninitialize((StartupDB::StartupApproval *)hKey);
      LocalFree(v3);
      return 2147942487LL;
  }
  v5 = StartupDB::StartupApproval::Initialize(hKey, v12, v13, v15, 0x103u);
  LOWORD(v18) = 5;
  if ( v5 == 5 )
    v5 = StartupDB::StartupApproval::Initialize(hKey, v16, v17, v15, 0x101u);
  if ( (v5 & 0x80000000) != 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v20 = 32;
LABEL_42:
    WPP_SF_d(v19[2], v20, &WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids, v5);
LABEL_43:
    StartupDB::StartupApproval::Uninitialize((StartupDB::StartupApproval *)hKey);
LABEL_44:
    LocalFree(v3);
    return v5;
  }
  BlockedItemInfo = StartupDB::StartupApproval::GetBlockedItemInfo(
                      (StartupDB::StartupApproval *)hKey,
                      v10,
                      (struct StartupDB::BLOCKEDITEMINFO *)SystemTimeAsFileTime);
  v5 = BlockedItemInfo;
  if ( v11 )
  {
    if ( BlockedItemInfo < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_43;
      v20 = 33;
      goto LABEL_42;
    }
    SystemTimeAsFileTime[0].dwLowDateTime &= ~1u;
    *(_QWORD *)&SystemTimeAsFileTime[0].dwHighDateTime = 0;
  }
  else
  {
    if ( BlockedItemInfo != 2 && BlockedItemInfo && BlockedItemInfo != 1630 )
    {
      if ( BlockedItemInfo > 0 )
        v5 = (unsigned __int16)BlockedItemInfo | 0x80070000;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_43;
      v20 = 34;
      goto LABEL_42;
    }
    SystemTimeAsFileTime[0].dwLowDateTime |= 1u;
    GetSystemTimeAsFileTime((LPFILETIME)&SystemTimeAsFileTime[0].dwHighDateTime);
  }
  if ( hKey[0] <= (HKEY)2
    || (v18 = RegSetValueExW(hKey[0], v10, 0, 3u, (const BYTE *)SystemTimeAsFileTime, 0xCu), v18 > 0) )
  {
    v18 = (unsigned __int16)v18 | 0x80070000;
  }
  StartupDB::StartupApproval::Uninitialize((StartupDB::StartupApproval *)hKey);
  LocalFree(v3);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x140011180  mov     [rsp-8+arg_8], rbx
0x140011185  mov     [rsp-8+arg_10], rsi
0x14001118a  push    rbp
0x14001118b  push    rdi
0x14001118c  push    r12
0x14001118e  push    r14
0x140011190  push    r15
0x140011192  lea     rbp, [rsp-37h]
0x140011197  sub     rsp, 90h
0x14001119e  mov     rax, cs:__security_cookie
0x1400111a5  xor     rax, rsp
0x1400111a8  mov     [rbp+57h+var_28], rax
0x1400111ac  mov     [rbp+57h+pNumArgs], 0
0x1400111b3  lea     rdx, [rbp+57h+pNumArgs]; pNumArgs
0x1400111b7  call    cs:__imp_CommandLineToArgvW
0x1400111bd  mov     rsi, rax
0x1400111c0  mov     [rbp+57h+var_60], rax
0x1400111c4  test    rax, rax
0x1400111c7  jnz     short loc_140011217
0x1400111c9  call    cs:__imp_GetLastError
0x1400111cf  mov     ebx, eax
0x1400111d1  test    eax, eax
0x1400111d3  jle     short loc_1400111DE
0x1400111d5  movzx   ebx, ax
0x1400111d8  or      ebx, 80070000h
0x1400111de  lea     rax, WPP_GLOBAL_Control
0x1400111e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400111ec  cmp     rcx, rax
0x1400111ef  jz      short loc_140011210
0x1400111f1  test    byte ptr [rcx+1Ch], 2
0x1400111f5  jz      short loc_140011210
0x1400111f7  mov     edx, 1Eh
0x1400111fc  mov     r9d, ebx
0x1400111ff  lea     r8, WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids
0x140011206  mov     rcx, [rcx+10h]
0x14001120a  call    WPP_SF_d
0x14001120f  nop
0x140011210  mov     eax, ebx
0x140011212  jmp     loc_1400114DB
0x140011217  mov     r9d, [rbp+57h+pNumArgs]
0x14001121b  cmp     r9d, 3
0x14001121f  jz      short loc_14001125E
0x140011221  lea     rax, WPP_GLOBAL_Control
0x140011228  mov     ebx, 80070057h
0x14001122d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011234  cmp     rcx, rax
0x140011237  jz      loc_140011454
0x14001123d  test    byte ptr [rcx+1Ch], 2
0x140011241  jz      loc_140011454
0x140011247  mov     edx, 1Fh
0x14001124c  mov     dword ptr [rsp+0B0h+lpData], ebx
0x140011250  mov     rcx, [rcx+10h]
0x140011254  call    WPP_SF_dd
0x140011259  jmp     loc_140011454
0x14001125e  mov     rdx, [rax]
0x140011261  lea     rcx, [rbp+57h+var_48]
0x140011265  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14001126a  nop
0x14001126b  call    cs:__imp__o__errno
0x140011271  mov     r14, rax
0x140011274  lea     rcx, [rbp+57h+var_48]
0x140011278  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14001127d  mov     rbx, rax
0x140011280  mov     [rbp+57h+EndPtr], 0
0x140011288  mov     dword ptr [r14], 0
0x14001128f  mov     r8d, 0Ah; Radix
0x140011295  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x140011299  mov     rcx, rax; String
0x14001129c  call    cs:__imp_wcstoull
0x1400112a2  mov     rdi, rax
0x1400112a5  cmp     rbx, [rbp+57h+EndPtr]
0x1400112a9  jnz     short loc_1400112B9
0x1400112ab  lea     rcx, aInvalidStoullA; "invalid stoull argument"
0x1400112b2  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x1400112b8  int     3; Trap to Debugger
0x1400112b9  cmp     dword ptr [r14], 22h ; '"'
0x1400112bd  jnz     short loc_1400112CD
0x1400112bf  lea     rcx, aStoullArgument; "stoull argument out of range"
0x1400112c6  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1400112cc  nop
0x1400112cd  lea     rcx, [rbp+57h+var_48]
0x1400112d1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400112d6  mov     r15, [rsi+8]
0x1400112da  mov     rcx, [rsi+10h]
0x1400112de  call    cs:__imp__o__wtoi
0x1400112e4  mov     r12d, eax
0x1400112e7  xor     eax, eax
0x1400112e9  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400112ed  mov     [rbp+57h+var_50], eax
0x1400112f0  lea     rcx, [rbp+57h+hKey]; this
0x1400112f4  call    ??0StartupApproval@StartupDB@@QEAA@XZ; StartupDB::StartupApproval::StartupApproval(void)
0x1400112f9  mov     rax, 0FC00000000000000h
0x140011303  and     rdi, rax
0x140011306  mov     rax, 8000000000000000h
0x140011310  cmp     rdi, rax
0x140011313  jnz     short loc_14001131E
0x140011315  lea     r14, aRun; "Run"
0x14001131c  jmp     short loc_140011350
0x14001131e  mov     rax, 4000000000000000h
0x140011328  cmp     rdi, rax
0x14001132b  jnz     short loc_140011336
0x14001132d  lea     r14, aRun32; "Run32"
0x140011334  jmp     short loc_140011350
0x140011336  mov     rax, 1000000000000000h
0x140011340  cmp     rdi, rax
0x140011343  jnz     loc_1400114C3
0x140011349  lea     r14, aStartupfolder; "StartupFolder"
0x140011350  mov     dword ptr [rsp+0B0h+lpData], 103h; unsigned int
0x140011358  mov     r9, r14; unsigned __int16 *
0x14001135b  lea     rcx, [rbp+57h+hKey]; this
0x14001135f  call    ?Initialize@StartupApproval@StartupDB@@QEAAJPEAUHKEY__@@PEBG1K@Z; StartupDB::StartupApproval::Initialize(HKEY__ *,ushort const *,ushort const *,ulong)
0x140011364  mov     ebx, eax
0x140011366  mov     edi, 5
0x14001136b  cmp     eax, edi
0x14001136d  jnz     short loc_140011385
0x14001136f  mov     dword ptr [rsp+0B0h+lpData], 101h; unsigned int
0x140011377  mov     r9, r14; unsigned __int16 *
0x14001137a  lea     rcx, [rbp+57h+hKey]; this
0x14001137e  call    ?Initialize@StartupApproval@StartupDB@@QEAAJPEAUHKEY__@@PEBG1K@Z; StartupDB::StartupApproval::Initialize(HKEY__ *,ushort const *,ushort const *,ulong)
0x140011383  mov     ebx, eax
0x140011385  test    ebx, ebx
0x140011387  jns     short loc_1400113B4
0x140011389  lea     rax, WPP_GLOBAL_Control
0x140011390  mov     rcx, cs:WPP_GLOBAL_Control
0x140011397  cmp     rcx, rax
0x14001139a  jz      loc_14001144A
0x1400113a0  test    byte ptr [rcx+1Ch], 2
0x1400113a4  jz      loc_14001144A
0x1400113aa  mov     edx, 20h ; ' '
0x1400113af  jmp     loc_140011437
0x1400113b4  lea     r8, [rbp+57h+SystemTimeAsFileTime]; struct StartupDB::BLOCKEDITEMINFO *
0x1400113b8  mov     rdx, r15; unsigned __int16 *
0x1400113bb  lea     rcx, [rbp+57h+hKey]; this
0x1400113bf  call    ?GetBlockedItemInfo@StartupApproval@StartupDB@@QEAAJPEBGPEAUBLOCKEDITEMINFO@2@@Z; StartupDB::StartupApproval::GetBlockedItemInfo(ushort const *,StartupDB::BLOCKEDITEMINFO *)
0x1400113c4  mov     ebx, eax
0x1400113c6  test    r12d, r12d
0x1400113c9  jz      short loc_1400113FB
0x1400113cb  test    eax, eax
0x1400113cd  jns     short loc_1400113EF
0x1400113cf  lea     rax, WPP_GLOBAL_Control
0x1400113d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400113dd  cmp     rcx, rax
0x1400113e0  jz      short loc_14001144A
0x1400113e2  test    byte ptr [rcx+1Ch], 2
0x1400113e6  jz      short loc_14001144A
0x1400113e8  mov     edx, 21h ; '!'
0x1400113ed  jmp     short loc_140011437
0x1400113ef  and     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0FFFFFFFEh
0x1400113f3  xor     eax, eax
0x1400113f5  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwHighDateTime], rax
0x1400113f9  jmp     short loc_140011470
0x1400113fb  cmp     ebx, 2
0x1400113fe  jz      short loc_140011462
0x140011400  test    ebx, ebx
0x140011402  jz      short loc_140011462
0x140011404  cmp     ebx, 65Eh
0x14001140a  jz      short loc_140011462
0x14001140c  test    ebx, ebx
0x14001140e  jle     short loc_140011419
0x140011410  movzx   ebx, bx
0x140011413  or      ebx, 80070000h
0x140011419  lea     rax, WPP_GLOBAL_Control
0x140011420  mov     rcx, cs:WPP_GLOBAL_Control
0x140011427  cmp     rcx, rax
0x14001142a  jz      short loc_14001144A
0x14001142c  test    byte ptr [rcx+1Ch], 2
0x140011430  jz      short loc_14001144A
0x140011432  mov     edx, 22h ; '"'
0x140011437  mov     r9d, ebx
0x14001143a  lea     r8, WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids
0x140011441  mov     rcx, [rcx+10h]
0x140011445  call    WPP_SF_d
0x14001144a  lea     rcx, [rbp+57h+hKey]; this
0x14001144e  call    ?Uninitialize@StartupApproval@StartupDB@@QEAAXXZ; StartupDB::StartupApproval::Uninitialize(void)
0x140011453  nop
0x140011454  mov     rcx, rsi; hMem
0x140011457  call    cs:__imp_LocalFree
0x14001145d  jmp     loc_140011210
0x140011462  or      [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 1
0x140011466  lea     rcx, [rbp+57h+SystemTimeAsFileTime.dwHighDateTime]; lpSystemTimeAsFileTime
0x14001146a  call    cs:__imp_GetSystemTimeAsFileTime
0x140011470  mov     rcx, [rbp+57h+hKey]; hKey
0x140011474  cmp     rcx, 2
0x140011478  jbe     short loc_1400114A3
0x14001147a  mov     [rsp+0B0h+cbData], 0Ch; cbData
0x140011482  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x140011486  mov     [rsp+0B0h+lpData], rax; lpData
0x14001148b  mov     r9d, 3; dwType
0x140011491  xor     r8d, r8d; Reserved
0x140011494  mov     rdx, r15; lpValueName
0x140011497  call    cs:__imp_RegSetValueExW
0x14001149d  mov     edi, eax
0x14001149f  test    eax, eax
0x1400114a1  jle     short loc_1400114AC
0x1400114a3  movzx   edi, di
0x1400114a6  or      edi, 80070000h
0x1400114ac  lea     rcx, [rbp+57h+hKey]; this
0x1400114b0  call    ?Uninitialize@StartupApproval@StartupDB@@QEAAXXZ; StartupDB::StartupApproval::Uninitialize(void)
0x1400114b5  nop
0x1400114b6  mov     rcx, rsi; hMem
0x1400114b9  call    cs:__imp_LocalFree
0x1400114bf  mov     eax, edi
0x1400114c1  jmp     short loc_1400114DB
0x1400114c3  lea     rcx, [rbp+57h+hKey]; this
0x1400114c7  call    ?Uninitialize@StartupApproval@StartupDB@@QEAAXXZ; StartupDB::StartupApproval::Uninitialize(void)
0x1400114cc  nop
0x1400114cd  mov     rcx, rsi; hMem
0x1400114d0  call    cs:__imp_LocalFree
0x1400114d6  mov     eax, 80070057h
0x1400114db  mov     rcx, [rbp+57h+var_28]
0x1400114df  xor     rcx, rsp; StackCookie
0x1400114e2  call    __security_check_cookie
0x1400114e7  lea     r11, [rsp+0B0h+var_20]
0x1400114ef  mov     rbx, [r11+38h]
0x1400114f3  mov     rsi, [r11+40h]
0x1400114f7  mov     rsp, r11
0x1400114fa  pop     r15
0x1400114fc  pop     r14
0x1400114fe  pop     r12
0x140011500  pop     rdi
0x140011501  pop     rbp
0x140011502  retn
```
