# SqliteDatabase::BackupChannel(IWNSChannelDetails *)

- ea: `0x1800468e0`
- end: `0x180046df4`
- name: `?BackupChannel@SqliteDatabase@@AEAAXPEAUIWNSChannelDetails@@@Z`
- size: `1300`
- prototype: `void __fastcall(SqliteDatabase *__hidden this, struct IWNSChannelDetails *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180047938`
- `0x1800f20c0`

## callees

- `0x18000e5f4`
- `0x180045ab4`
- `0x1800468e0`
- `0x180046dfc`
- `0x1800b99f0`
- `0x1800f2460`
- `0x180118010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x180046b96`
- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x180046c47`
- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x180046cef`
- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x180046b96`
- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x180046c47`
- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x180046cef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046d8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046d9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046dad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046dbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046d8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046d9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046dad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046dbe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180046b1d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180046b1d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046bfb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046cab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046d4b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046bfb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046cab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046d4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046d7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046d7c`

## string_xrefs

- `0x180046b65`: `channelUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall SqliteDatabase::BackupChannel(SqliteDatabase *this, struct IWNSChannelDetails *a2)
{
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  __int64 v8; // rdi
  __int64 v9; // r15
  int v10; // eax
  __int64 v11; // r14
  __int64 v12; // r12
  int v13; // eax
  int v14; // eax
  WCHAR *v15; // rsi
  unsigned int v16; // eax
  SqliteDatabase *v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rax
  unsigned int v20; // eax
  __int64 v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // eax
  const char *v24; // r9
  int dwOptions; // [rsp+20h] [rbp-268h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-268h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-268h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-268h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-268h]
  HKEY hKey; // [rsp+50h] [rbp-238h] BYREF
  __int64 v31; // [rsp+58h] [rbp-230h] BYREF
  __int64 v32; // [rsp+60h] [rbp-228h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-220h] BYREF
  char *v34; // [rsp+70h] [rbp-218h] BYREF
  LPVOID v35; // [rsp+78h] [rbp-210h]
  __int64 v36; // [rsp+80h] [rbp-208h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+88h] [rbp-200h] BYREF
  _WORD Data[72]; // [rsp+A0h] [rbp-1E8h] BYREF
  _WORD v39[72]; // [rsp+130h] [rbp-158h] BYREF
  _WORD v40[72]; // [rsp+1C0h] [rbp-C8h] BYREF
  SqliteDatabase *retaddr; // [rsp+288h] [rbp+0h]

  v35 = 0;
  try
  {
    v4 = (*(__int64 (**)(void))(*(_QWORD *)a2 + 24LL))();
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE74,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v4,
        dwOptions);
    v34 = 0;
    v5 = (*(__int64 (__fastcall **)(struct IWNSChannelDetails *, char **))(*(_QWORD *)a2 + 32LL))(a2, &v34);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE77,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v5,
        dwOptions);
    pv = 0;
    v6 = (*(__int64 (__fastcall **)(struct IWNSChannelDetails *, LPVOID *))(*(_QWORD *)a2 + 40LL))(a2, &pv);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE7A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v6,
        dwOptions);
    v31 = 0;
    v7 = (*(__int64 (__fastcall **)(struct IWNSChannelDetails *, __int64 *))(*(_QWORD *)a2 + 56LL))(a2, &v31);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE7D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v7,
        dwOptions);
    v8 = HIDWORD(v31);
    v9 = (unsigned int)v31;
    v32 = 0;
    v10 = (*(__int64 (__fastcall **)(struct IWNSChannelDetails *, __int64 *))(*(_QWORD *)a2 + 48LL))(a2, &v32);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE81,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v10,
        dwOptions);
    v11 = HIDWORD(v32);
    v12 = (unsigned int)v32;
    v36 = 0;
    v13 = (*(__int64 (__fastcall **)(struct IWNSChannelDetails *, __int64 *))(*(_QWORD *)a2 + 64LL))(a2, &v36);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE85,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v13,
        dwOptions);
    memset(lpSubKey, 0, sizeof(lpSubKey));
    v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
            lpSubKey,
            L"%s\\%s",
            *((_QWORD *)this + 16),
            v35);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE88,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v14,
        dwOptions);
    hKey = 0;
    v15 = (WCHAR *)lpSubKey[0];
    v16 = RegCreateKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( v16 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xE94,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)v16,
        dwOptionsa);
    SqliteDatabase::WriteRegAnsiString(retaddr, hKey, L"channelId", v34);
    SqliteDatabase::WriteRegAnsiString(v17, hKey, L"channelUri", (const char *)pv);
    if ( (unsigned int)_o__i64tow_s(v9 | (v8 << 32), Data, 65) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE9A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)0x80070057LL,
        dwOptionsa);
    v18 = -1;
    v19 = -1;
    do
      ++v19;
    while ( Data[v19] );
    v20 = RegSetValueExW(hKey, L"channelExpiry", 0, 1u, (const BYTE *)Data, 2 * v19);
    if ( v20 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xEE9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)v20,
        dwOptionsb);
    if ( (unsigned int)_o__i64tow_s(v12 | (v11 << 32), v39, 65) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE9E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)0x80070057LL,
        dwOptionsb);
    v21 = -1;
    do
      ++v21;
    while ( v39[v21] );
    v22 = RegSetValueExW(hKey, L"channelCreation", 0, 1u, (const BYTE *)v39, 2 * v21);
    if ( v22 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xEE9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)v22,
        dwOptionsc);
    if ( (unsigned int)_o__i64tow_s(v36, v40, 65) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEA2,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)0x80070057LL,
        dwOptionsc);
    do
      ++v18;
    while ( v40[v18] );
    v23 = RegSetValueExW(hKey, L"deviceVersion", 0, 1u, (const BYTE *)v40, 2 * v18);
    if ( v23 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xEE9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)v23,
        dwOptionsd);
    if ( hKey )
      RegCloseKey(hKey);
    if ( v15 )
      CoTaskMemFree(v15);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v34 )
      CoTaskMemFree(v34);
    if ( v35 )
      CoTaskMemFree(v35);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xEA5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      v24);
  }
}

```

## disassembly

```asm
0x1800468e0  mov     [rsp+arg_10], rbx
0x1800468e5  mov     [rsp+arg_18], rsi
0x1800468ea  push    rdi
0x1800468eb  push    r12
0x1800468ed  push    r13
0x1800468ef  push    r14
0x1800468f1  push    r15
0x1800468f3  sub     rsp, 260h
0x1800468fa  mov     rax, cs:__security_cookie
0x180046901  xor     rax, rsp
0x180046904  mov     [rsp+288h+var_38], rax
0x18004690c  mov     rbx, rdx
0x18004690f  mov     rsi, rcx
0x180046912  xor     r13d, r13d
0x180046915  mov     [rsp+288h+var_210], r13
0x18004691a  mov     rax, [rdx]
0x18004691d  lea     rdx, [rsp+288h+var_210]
0x180046922  mov     rcx, rbx
0x180046925  mov     rax, [rax+18h]
0x180046929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004692e  mov     rcx, [rsp+288h]; this
0x180046936  test    eax, eax
0x180046938  jns     short loc_18004694F
0x18004693a  mov     r9d, eax; char *
0x18004693d  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180046944  mov     edx, 0E74h; void *
0x180046949  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004694f  mov     [rsp+288h+var_218], r13
0x180046954  mov     rax, [rbx]
0x180046957  lea     rdx, [rsp+288h+var_218]
0x18004695c  mov     rcx, rbx
0x18004695f  mov     rax, [rax+20h]
0x180046963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046968  mov     rcx, [rsp+288h]; this
0x180046970  test    eax, eax
0x180046972  jns     short loc_180046989
0x180046974  mov     r9d, eax; char *
0x180046977  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004697e  mov     edx, 0E77h; void *
0x180046983  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046989  mov     [rsp+288h+pv], r13
0x18004698e  mov     rax, [rbx]
0x180046991  lea     rdx, [rsp+288h+pv]
0x180046996  mov     rcx, rbx
0x180046999  mov     rax, [rax+28h]
0x18004699d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469a2  mov     rcx, [rsp+288h]; this
0x1800469aa  test    eax, eax
0x1800469ac  jns     short loc_1800469C2
0x1800469ae  mov     r9d, eax; char *
0x1800469b1  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800469b8  mov     edx, 0E7Ah; void *
0x1800469bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800469c2  mov     [rsp+288h+var_230], r13
0x1800469c7  mov     rax, [rbx]
0x1800469ca  lea     rdx, [rsp+288h+var_230]
0x1800469cf  mov     rcx, rbx
0x1800469d2  mov     rax, [rax+38h]
0x1800469d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469db  mov     rcx, [rsp+288h]; this
0x1800469e3  test    eax, eax
0x1800469e5  jns     short loc_1800469FB
0x1800469e7  mov     r9d, eax; char *
0x1800469ea  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800469f1  mov     edx, 0E7Dh; void *
0x1800469f6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800469fb  mov     edi, dword ptr [rsp+288h+var_230+4]
0x1800469ff  mov     r15d, dword ptr [rsp+288h+var_230]
0x180046a04  mov     [rsp+288h+var_228], r13
0x180046a09  mov     rax, [rbx]
0x180046a0c  lea     rdx, [rsp+288h+var_228]
0x180046a11  mov     rcx, rbx
0x180046a14  mov     rax, [rax+30h]
0x180046a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a1d  mov     rcx, [rsp+288h]; this
0x180046a25  test    eax, eax
0x180046a27  jns     short loc_180046A3D
0x180046a29  mov     r9d, eax; char *
0x180046a2c  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180046a33  mov     edx, 0E81h; void *
0x180046a38  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046a3d  mov     r14d, dword ptr [rsp+288h+var_228+4]
0x180046a42  mov     r12d, dword ptr [rsp+288h+var_228]
0x180046a47  mov     [rsp+288h+var_208], r13
0x180046a4f  mov     rax, [rbx]
0x180046a52  lea     rdx, [rsp+288h+var_208]
0x180046a5a  mov     rcx, rbx
0x180046a5d  mov     rax, [rax+40h]
0x180046a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a66  mov     rcx, [rsp+288h]; this
0x180046a6e  test    eax, eax
0x180046a70  jns     short loc_180046A86
0x180046a72  mov     r9d, eax; char *
0x180046a75  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180046a7c  mov     edx, 0E85h; void *
0x180046a81  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046a86  mov     [rsp+288h+lpSubKey], r13
0x180046a8e  mov     [rsp+288h+var_1F8], r13
0x180046a96  mov     [rsp+288h+var_1F0], r13
0x180046a9e  mov     r9, [rsp+288h+var_210]
0x180046aa3  mov     r8, [rsi+80h]
0x180046aaa  lea     rdx, aSS_0; "%s\\%s"
0x180046ab1  lea     rcx, [rsp+288h+lpSubKey]
0x180046ab9  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180046abe  mov     rcx, [rsp+288h]; this
0x180046ac6  test    eax, eax
0x180046ac8  jns     short loc_180046ADF
0x180046aca  mov     r9d, eax; char *
0x180046acd  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180046ad4  mov     edx, 0E88h; void *
0x180046ad9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046adf  mov     [rsp+288h+hKey], r13
0x180046ae4  mov     [rsp+288h+lpdwDisposition], r13; lpdwDisposition
0x180046ae9  lea     rax, [rsp+288h+hKey]
0x180046aee  mov     [rsp+288h+phkResult], rax; phkResult
0x180046af3  mov     [rsp+288h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180046af8  mov     [rsp+288h+samDesired], 20006h; samDesired
0x180046b00  mov     [rsp+288h+dwOptions], r13d; int
0x180046b05  xor     r9d, r9d; lpClass
0x180046b08  xor     r8d, r8d; Reserved
0x180046b0b  mov     rsi, [rsp+288h+lpSubKey]
0x180046b13  mov     rdx, rsi; lpSubKey
0x180046b16  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180046b1d  call    cs:__imp_RegCreateKeyExW
0x180046b23  mov     rcx, [rsp+288h]; this
0x180046b2b  test    eax, eax
0x180046b2d  jz      short loc_180046B43
0x180046b2f  mov     r9d, eax; char *
0x180046b32  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180046b39  mov     edx, 0E94h; void *
0x180046b3e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180046b43  shl     rdi, 20h
0x180046b47  or      rdi, r15
0x180046b4a  mov     r9, [rsp+288h+var_218]; char *
0x180046b4f  lea     r8, aChannelid; "channelId"
0x180046b56  mov     rdx, [rsp+288h+hKey]; HKEY
0x180046b5b  call    ?WriteRegAnsiString@SqliteDatabase@@AEAAXPEAUHKEY__@@PEBGPEBD@Z; SqliteDatabase::WriteRegAnsiString(HKEY__ *,ushort const *,char const *)
0x180046b60  mov     r9, [rsp+288h+pv]; char *
0x180046b65  lea     r8, aChanneluri; "channelUri"
0x180046b6c  mov     rdx, [rsp+288h+hKey]; HKEY
0x180046b71  call    ?WriteRegAnsiString@SqliteDatabase@@AEAAXPEAUHKEY__@@PEBGPEBD@Z; SqliteDatabase::WriteRegAnsiString(HKEY__ *,ushort const *,char const *)
0x180046b76  mov     rbx, [rsp+288h]
0x180046b7e  mov     r15d, 0Ah
0x180046b84  mov     r9d, r15d
0x180046b87  lea     r8d, [r15+37h]
0x180046b8b  lea     rdx, [rsp+288h+Data]
0x180046b93  mov     rcx, rdi
0x180046b96  call    cs:__imp__o__i64tow_s
0x180046b9c  test    eax, eax
0x180046b9e  jz      short loc_180046BBA
0x180046ba0  mov     r9d, 80070057h; char *
0x180046ba6  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180046bad  mov     edx, 0E9Ah; void *
0x180046bb2  mov     rcx, rbx; this
0x180046bb5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046bba  lea     rcx, [rsp+288h+Data]
0x180046bc2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180046bc6  mov     rax, rbx
0x180046bc9  inc     rax
0x180046bcc  cmp     [rcx+rax*2], r13w
0x180046bd1  jnz     short loc_180046BC9
0x180046bd3  add     eax, eax
0x180046bd5  mov     [rsp+288h+samDesired], eax; cbData
0x180046bd9  lea     rax, [rsp+288h+Data]
0x180046be1  mov     qword ptr [rsp+288h+dwOptions], rax; int
0x180046be6  mov     r9d, 1; dwType
0x180046bec  xor     r8d, r8d; Reserved
0x180046bef  lea     rdx, aChannelexpiry; "channelExpiry"
0x180046bf6  mov     rcx, [rsp+288h+hKey]; hKey
0x180046bfb  call    cs:__imp_RegSetValueExW
0x180046c01  mov     rcx, [rsp+288h]; this
0x180046c09  test    eax, eax
0x180046c0b  jz      short loc_180046C21
0x180046c0d  mov     r9d, eax; char *
0x180046c10  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180046c17  mov     edx, 0EE9h; void *
0x180046c1c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180046c21  mov     rdi, [rsp+288h]
0x180046c29  shl     r14, 20h
0x180046c2d  or      r14, r12
0x180046c30  mov     r9d, r15d
0x180046c33  mov     r12d, 41h ; 'A'
0x180046c39  mov     r8d, r12d
0x180046c3c  lea     rdx, [rsp+288h+var_158]
0x180046c44  mov     rcx, r14
0x180046c47  call    cs:__imp__o__i64tow_s
0x180046c4d  test    eax, eax
0x180046c4f  jz      short loc_180046C6B
0x180046c51  mov     r9d, 80070057h; char *
0x180046c57  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180046c5e  mov     edx, 0E9Eh; void *
0x180046c63  mov     rcx, rdi; this
0x180046c66  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046c6b  lea     rcx, [rsp+288h+var_158]
0x180046c73  mov     rax, rbx
0x180046c76  inc     rax
0x180046c79  cmp     [rcx+rax*2], r13w
0x180046c7e  jnz     short loc_180046C76
0x180046c80  add     eax, eax
0x180046c82  mov     [rsp+288h+samDesired], eax; cbData
0x180046c86  lea     rax, [rsp+288h+var_158]
0x180046c8e  mov     qword ptr [rsp+288h+dwOptions], rax; int
0x180046c93  mov     r14d, 1
0x180046c99  mov     r9d, r14d; dwType
0x180046c9c  xor     r8d, r8d; Reserved
0x180046c9f  lea     rdx, aChannelcreatio; "channelCreation"
0x180046ca6  mov     rcx, [rsp+288h+hKey]; hKey
0x180046cab  call    cs:__imp_RegSetValueExW
0x180046cb1  mov     rcx, [rsp+288h]; this
0x180046cb9  test    eax, eax
0x180046cbb  jz      short loc_180046CD1
0x180046cbd  mov     r9d, eax; char *
0x180046cc0  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180046cc7  mov     edx, 0EE9h; void *
0x180046ccc  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180046cd1  mov     rdi, [rsp+288h]
0x180046cd9  mov     r9d, r15d
0x180046cdc  mov     r8, r12
0x180046cdf  lea     rdx, [rsp+288h+var_C8]
0x180046ce7  mov     rcx, [rsp+288h+var_208]
0x180046cef  call    cs:__imp__o__i64tow_s
0x180046cf5  test    eax, eax
0x180046cf7  jz      short loc_180046D13
0x180046cf9  mov     r9d, 80070057h; char *
0x180046cff  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180046d06  mov     edx, 0EA2h; void *
0x180046d0b  mov     rcx, rdi; this
0x180046d0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046d13  lea     rax, [rsp+288h+var_C8]
0x180046d1b  inc     rbx
0x180046d1e  cmp     [rax+rbx*2], r13w
0x180046d23  jnz     short loc_180046D1B
0x180046d25  lea     eax, [rbx+rbx]
0x180046d28  mov     [rsp+288h+samDesired], eax; cbData
0x180046d2c  lea     rax, [rsp+288h+var_C8]
0x180046d34  mov     qword ptr [rsp+288h+dwOptions], rax; unsigned int
0x180046d39  mov     r9d, r14d; dwType
0x180046d3c  xor     r8d, r8d; Reserved
0x180046d3f  lea     rdx, aDeviceversion_0; "deviceVersion"
0x180046d46  mov     rcx, [rsp+288h+hKey]; hKey
0x180046d4b  call    cs:__imp_RegSetValueExW
0x180046d51  mov     rcx, [rsp+288h]; this
0x180046d59  test    eax, eax
0x180046d5b  jz      short loc_180046D72
0x180046d5d  mov     r9d, eax; char *
0x180046d60  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180046d67  mov     edx, 0EE9h; void *
0x180046d6c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180046d72  mov     rcx, [rsp+288h+hKey]; hKey
0x180046d77  test    rcx, rcx
0x180046d7a  jz      short loc_180046D83
0x180046d7c  call    cs:__imp_RegCloseKey
0x180046d82  nop
0x180046d83  test    rsi, rsi
0x180046d86  jz      short loc_180046D92
0x180046d88  mov     rcx, rsi; pv
0x180046d8b  call    cs:__imp_CoTaskMemFree
0x180046d91  nop
0x180046d92  mov     rcx, [rsp+288h+pv]; pv
0x180046d97  test    rcx, rcx
0x180046d9a  jz      short loc_180046DA3
0x180046d9c  call    cs:__imp_CoTaskMemFree
0x180046da2  nop
0x180046da3  mov     rcx, [rsp+288h+var_218]; pv
0x180046da8  test    rcx, rcx
0x180046dab  jz      short loc_180046DB4
0x180046dad  call    cs:__imp_CoTaskMemFree
0x180046db3  nop
0x180046db4  mov     rcx, [rsp+288h+var_210]; pv
0x180046db9  test    rcx, rcx
0x180046dbc  jz      short loc_180046DC5
0x180046dbe  call    cs:__imp_CoTaskMemFree
0x180046dc4  nop
0x180046dc5  jmp     short $+2
0x180046dc7  mov     rcx, [rsp+288h+var_38]
0x180046dcf  xor     rcx, rsp; StackCookie
0x180046dd2  call    __security_check_cookie
0x180046dd7  lea     r11, [rsp+288h+var_28]
0x180046ddf  mov     rbx, [r11+40h]
0x180046de3  mov     rsi, [r11+48h]
0x180046de7  mov     rsp, r11
0x180046dea  pop     r15
0x180046dec  pop     r14
0x180046dee  pop     r13
0x180046df0  pop     r12
0x180046df2  pop     rdi
0x180046df3  retn
```
