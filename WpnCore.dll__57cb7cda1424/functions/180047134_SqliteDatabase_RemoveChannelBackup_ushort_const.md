# SqliteDatabase::RemoveChannelBackup(ushort const *)

- ea: `0x180047134`
- end: `0x18004731c`
- name: `?RemoveChannelBackup@SqliteDatabase@@AEAAXPEBG@Z`
- size: `488`
- prototype: `void __fastcall(SqliteDatabase *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f0388`
- `0x1800f1240`

## callees

- `0x18000e5f4`
- `0x180045ab4`
- `0x180047134`
- `0x180082b28`
- `0x1800852dc`
- `0x1800f2460`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800472fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800472fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800471e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800471e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800471aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004730d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800471aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004730d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180047214`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180047243`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180047272`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800472a1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800472d0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180047214`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180047243`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180047272`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800472a1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800472d0`

## string_xrefs

- `0x180047237`: `channelUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SqliteDatabase::RemoveChannelBackup(SqliteDatabase *this, const unsigned __int16 *a2)
{
  int v2; // eax
  HKEY v3; // rbx
  WCHAR *v4; // rbx
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  const char *v11; // r9
  int phkResult; // [rsp+20h] [rbp-38h]
  unsigned int phkResulta; // [rsp+20h] [rbp-38h]
  LPCWSTR lpSubKey[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  char v17; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  memset(lpSubKey, 0, 24);
  v2 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"%s\\%s",
         *((_QWORD *)this + 16),
         a2);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xED1,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v2,
        phkResult);
    v3 = hKey;
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v17);
      RegCloseKey(v3);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v17);
    }
    hKey = 0;
    v4 = (WCHAR *)lpSubKey[0];
    v5 = RegOpenKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0x1000Bu, &hKey);
    if ( v5 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xED7,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)v5,
        phkResulta);
    v6 = RegDeleteValueW(hKey, L"channelId");
    if ( v6 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xED9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)v6,
        phkResulta);
    v7 = RegDeleteValueW(hKey, L"channelUri");
    if ( v7 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xEDA,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)v7,
        phkResulta);
    v8 = RegDeleteValueW(hKey, L"channelCreation");
    if ( v8 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xEDB,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)v8,
        phkResulta);
    v9 = RegDeleteValueW(hKey, L"channelExpiry");
    if ( v9 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xEDC,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)v9,
        phkResulta);
    v10 = RegDeleteValueW(hKey, L"deviceVersion");
    if ( v10 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xEDD,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)v10,
        phkResulta);
    if ( v4 )
      CoTaskMemFree(v4);
    if ( hKey )
      RegCloseKey(hKey);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xEDF,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      v11);
  }
}

```

## disassembly

```asm
0x180047134  mov     rax, rsp
0x180047137  push    rbx
0x180047138  sub     rsp, 50h
0x18004713c  mov     qword ptr [rax+8], 0
0x180047144  mov     qword ptr [rax-28h], 0
0x18004714c  mov     qword ptr [rax-20h], 0
0x180047154  mov     qword ptr [rax-18h], 0
0x18004715c  mov     r9, rdx
0x18004715f  mov     r8, [rcx+80h]
0x180047166  lea     rdx, aSS_0; "%s\\%s"
0x18004716d  lea     rcx, [rax-28h]
0x180047171  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180047176  mov     rcx, [rsp+58h]; this
0x18004717b  test    eax, eax
0x18004717d  jns     short loc_180047193
0x18004717f  mov     r9d, eax; char *
0x180047182  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180047189  mov     edx, 0ED1h; void *
0x18004718e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180047193  mov     rbx, [rsp+58h+hKey]
0x180047198  test    rbx, rbx
0x18004719b  jz      short loc_1800471BA
0x18004719d  lea     rcx, [rsp+58h+arg_10]; this
0x1800471a2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800471a7  mov     rcx, rbx; hKey
0x1800471aa  call    cs:__imp_RegCloseKey
0x1800471b0  lea     rcx, [rsp+58h+arg_10]; this
0x1800471b5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800471ba  mov     [rsp+58h+hKey], 0
0x1800471c3  lea     rax, [rsp+58h+hKey]
0x1800471c8  mov     qword ptr [rsp+58h+phkResult], rax; unsigned int
0x1800471cd  mov     r9d, 1000Bh; samDesired
0x1800471d3  xor     r8d, r8d; ulOptions
0x1800471d6  mov     rbx, [rsp+58h+lpSubKey]
0x1800471db  mov     rdx, rbx; lpSubKey
0x1800471de  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800471e5  call    cs:__imp_RegOpenKeyExW
0x1800471eb  mov     rcx, [rsp+58h]; this
0x1800471f0  test    eax, eax
0x1800471f2  jz      short loc_180047208
0x1800471f4  mov     r9d, eax; char *
0x1800471f7  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800471fe  mov     edx, 0ED7h; void *
0x180047203  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180047208  lea     rdx, aChannelid; "channelId"
0x18004720f  mov     rcx, [rsp+58h+hKey]; hKey
0x180047214  call    cs:__imp_RegDeleteValueW
0x18004721a  mov     rcx, [rsp+58h]; this
0x18004721f  test    eax, eax
0x180047221  jz      short loc_180047237
0x180047223  mov     r9d, eax; char *
0x180047226  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004722d  mov     edx, 0ED9h; void *
0x180047232  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180047237  lea     rdx, aChanneluri; "channelUri"
0x18004723e  mov     rcx, [rsp+58h+hKey]; hKey
0x180047243  call    cs:__imp_RegDeleteValueW
0x180047249  mov     rcx, [rsp+58h]; this
0x18004724e  test    eax, eax
0x180047250  jz      short loc_180047266
0x180047252  mov     r9d, eax; char *
0x180047255  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004725c  mov     edx, 0EDAh; void *
0x180047261  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180047266  lea     rdx, aChannelcreatio; "channelCreation"
0x18004726d  mov     rcx, [rsp+58h+hKey]; hKey
0x180047272  call    cs:__imp_RegDeleteValueW
0x180047278  mov     rcx, [rsp+58h]; this
0x18004727d  test    eax, eax
0x18004727f  jz      short loc_180047295
0x180047281  mov     r9d, eax; char *
0x180047284  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004728b  mov     edx, 0EDBh; void *
0x180047290  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180047295  lea     rdx, aChannelexpiry; "channelExpiry"
0x18004729c  mov     rcx, [rsp+58h+hKey]; hKey
0x1800472a1  call    cs:__imp_RegDeleteValueW
0x1800472a7  mov     rcx, [rsp+58h]; this
0x1800472ac  test    eax, eax
0x1800472ae  jz      short loc_1800472C4
0x1800472b0  mov     r9d, eax; char *
0x1800472b3  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800472ba  mov     edx, 0EDCh; void *
0x1800472bf  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800472c4  lea     rdx, aDeviceversion_0; "deviceVersion"
0x1800472cb  mov     rcx, [rsp+58h+hKey]; hKey
0x1800472d0  call    cs:__imp_RegDeleteValueW
0x1800472d6  mov     rcx, [rsp+58h]; this
0x1800472db  test    eax, eax
0x1800472dd  jz      short loc_1800472F4
0x1800472df  mov     r9d, eax; char *
0x1800472e2  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800472e9  mov     edx, 0EDDh; void *
0x1800472ee  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800472f4  test    rbx, rbx
0x1800472f7  jz      short loc_180047303
0x1800472f9  mov     rcx, rbx; pv
0x1800472fc  call    cs:__imp_CoTaskMemFree
0x180047302  nop
0x180047303  mov     rcx, [rsp+58h+hKey]; hKey
0x180047308  test    rcx, rcx
0x18004730b  jz      short loc_180047314
0x18004730d  call    cs:__imp_RegCloseKey
0x180047313  nop
0x180047314  jmp     short $+2
0x180047316  add     rsp, 50h
0x18004731a  pop     rbx
0x18004731b  retn
```
