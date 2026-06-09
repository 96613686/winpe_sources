# SqliteDatabase::InsertRolloverNotification(IWpnNotification *)

- ea: `0x1800a2968`
- end: `0x1800a2da8`
- name: `?InsertRolloverNotification@SqliteDatabase@@AEAAXPEAUIWpnNotification@@@Z`
- size: `1088`
- prototype: `void __fastcall(SqliteDatabase *__hidden this, struct IWpnNotification *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002ac00`

## callees

- `0x1800082c4`
- `0x18000e090`
- `0x18000e598`
- `0x18000e5f4`
- `0x18001575c`
- `0x18001592c`
- `0x18002b6d4`
- `0x18002b744`
- `0x18002b7a8`
- `0x1800a2968`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2d19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2d34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2d4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2d6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2d19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2d34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2d4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2d6a`
- `winsqlite3!sqlite3_bind_blob` at `0x1800a2c13`
- `winsqlite3!sqlite3_bind_blob` at `0x1800a2c13`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall SqliteDatabase::InsertRolloverNotification(SqliteDatabase *this, struct IWpnNotification *a2)
{
  __int64 v3; // rax
  int v4; // eax
  __int64 (__fastcall *v5)(struct IWpnNotification *, unsigned __int16 **); // rbx
  int v6; // eax
  unsigned __int16 *v7; // rsi
  unsigned __int16 *v8; // r8
  __int64 (__fastcall *v9)(struct IWpnNotification *, unsigned __int16 **); // rbx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  signed int v14; // eax
  __int64 (__fastcall *v15)(struct IWpnNotification *, unsigned __int16 **); // rbx
  int v16; // eax
  __int64 (__fastcall *v17)(struct IWpnNotification *, LPVOID *); // rbx
  int v18; // eax
  int v19; // [rsp+20h] [rbp-99h]
  int v20; // [rsp+30h] [rbp-89h] BYREF
  __int64 v21; // [rsp+38h] [rbp-81h] BYREF
  __int64 v22; // [rsp+40h] [rbp-79h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-71h] BYREF
  __int64 v24; // [rsp+50h] [rbp-69h]
  __int64 v25; // [rsp+58h] [rbp-61h]
  unsigned __int16 *v26; // [rsp+60h] [rbp-59h] BYREF
  __int64 v27; // [rsp+68h] [rbp-51h]
  __int64 v28; // [rsp+70h] [rbp-49h]
  unsigned __int16 *v29; // [rsp+78h] [rbp-41h] BYREF
  __int64 v30; // [rsp+80h] [rbp-39h]
  __int64 v31; // [rsp+88h] [rbp-31h]
  unsigned __int16 *v32; // [rsp+90h] [rbp-29h] BYREF
  __int64 v33; // [rsp+98h] [rbp-21h]
  __int64 v34; // [rsp+A0h] [rbp-19h]
  _BYTE v35[16]; // [rsp+A8h] [rbp-11h] BYREF
  Statement *v36; // [rsp+B8h] [rbp-1h]
  _BYTE v37[16]; // [rsp+C8h] [rbp+Fh] BYREF
  GUID v38; // [rsp+D8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v3 = std::shared_ptr<TileSession>::shared_ptr<TileSession>(v37, (char *)this + 48);
  AutoAddToCache::AutoAddToCache(
    v35,
    v3,
    "INSERT INTO [Notification] ([Id], [HandlerId], [Type], [Tag], [Group], [ExpiryTime], [ArrivalTime], [ActivityId], [P"
    "ayloadType]) SELECT ?, [RecordId], ?, ?, ?, ?, ?, ?, ? FROM [NotificationHandler] WHERE [PrimaryId]=?");
  v20 = 0;
  v4 = (*(__int64 (__fastcall **)(struct IWpnNotification *, int *))(*(_QWORD *)a2 + 24LL))(a2, &v20);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x812,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v4,
      v19);
  Statement::Bind(v36, 1, v20);
  Statement::Bind(v36, 2, L"toastCondensed");
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v5 = *(__int64 (__fastcall **)(struct IWpnNotification *, unsigned __int16 **))(*(_QWORD *)a2 + 56LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v32);
  v33 = -1;
  v34 = -1;
  v6 = v5(a2, &v32);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x818,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v6,
      v19);
  v7 = (unsigned __int16 *)&word_180124798;
  v8 = (unsigned __int16 *)&word_180124798;
  if ( v32 )
    v8 = v32;
  Statement::Bind(v36, 3, v8);
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v9 = *(__int64 (__fastcall **)(struct IWpnNotification *, unsigned __int16 **))(*(_QWORD *)a2 + 64LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v29);
  v30 = -1;
  v31 = -1;
  v10 = v9(a2, &v29);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x81C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v10,
      v19);
  if ( v29 )
    v7 = v29;
  Statement::Bind(v36, 4, v7);
  v22 = 0;
  v11 = (*(__int64 (__fastcall **)(struct IWpnNotification *, __int64 *))(*(_QWORD *)a2 + 72LL))(a2, &v22);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x820,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v11,
      v19);
  Statement::Bind(v36, 5, v22);
  v21 = 0;
  v12 = (*(__int64 (__fastcall **)(struct IWpnNotification *, __int64 *))(*(_QWORD *)a2 + 88LL))(a2, &v21);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x824,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v12,
      v19);
  Statement::Bind(v36, 6, v21);
  v38 = GUID_NULL;
  v13 = (*(__int64 (__fastcall **)(struct IWpnNotification *, GUID *))(*(_QWORD *)a2 + 112LL))(a2, &v38);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x828,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v13,
      v19);
  if ( !*(_QWORD *)v36 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)0x8007139FLL,
      v19);
  v14 = sqlite3_bind_blob(*(_QWORD *)v36, 7, &v38, 16);
  if ( v14 > 0 )
    v14 = (unsigned __int16)v14 | 0x87AF0000;
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)(unsigned int)v14,
      -1);
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v15 = *(__int64 (__fastcall **)(struct IWpnNotification *, unsigned __int16 **))(*(_QWORD *)a2 + 120LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
  v27 = -1;
  v28 = -1;
  v16 = v15(a2, &v26);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x82C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v16,
      -1);
  Statement::Bind(v36, 8, v26);
  pv = 0;
  v24 = 0;
  v25 = 0;
  v17 = *(__int64 (__fastcall **)(struct IWpnNotification *, LPVOID *))(*(_QWORD *)a2 + 32LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
  v24 = -1;
  v25 = -1;
  v18 = v17(a2, &pv);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x830,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v18,
      -1);
  Statement::Bind(v36, 9, (const unsigned __int16 *)pv);
  Statement::FetchNoRow(v36);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v24 = 0;
  v25 = 0;
  if ( v26 )
  {
    CoTaskMemFree(v26);
    v26 = 0;
  }
  v27 = 0;
  v28 = 0;
  if ( v29 )
  {
    CoTaskMemFree(v29);
    v29 = 0;
  }
  v30 = 0;
  v31 = 0;
  if ( v32 )
  {
    CoTaskMemFree(v32);
    v32 = 0;
  }
  v33 = 0;
  v34 = 0;
  AutoAddToCache::~AutoAddToCache((AutoAddToCache *)v35);
}

```

## disassembly

```asm
0x1800a2968  mov     [rsp-8+arg_10], rbx
0x1800a296d  push    rbp
0x1800a296e  push    rsi
0x1800a296f  push    rdi
0x1800a2970  push    r14
0x1800a2972  push    r15
0x1800a2974  lea     rbp, [rsp-37h]
0x1800a2979  sub     rsp, 0F0h
0x1800a2980  mov     rax, cs:__security_cookie
0x1800a2987  xor     rax, rsp
0x1800a298a  mov     [rbp+57h+var_28], rax
0x1800a298e  mov     rdi, rdx
0x1800a2991  lea     rdx, [rcx+30h]
0x1800a2995  lea     rcx, [rbp+57h+var_48]
0x1800a2999  call    ??0?$shared_ptr@VTileSession@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<TileSession>::shared_ptr<TileSession>(std::shared_ptr<TileSession> const &)
0x1800a299e  lea     r8, aInsertIntoNoti_1; "INSERT INTO [Notification] ([Id], [Hand"...
0x1800a29a5  mov     rdx, rax
0x1800a29a8  lea     rcx, [rbp+57h+var_68]
0x1800a29ac  call    ??0AutoAddToCache@@QEAA@V?$shared_ptr@VDatabase@@@std@@PEBD@Z; AutoAddToCache::AutoAddToCache(std::shared_ptr<Database>,char const *)
0x1800a29b1  nop
0x1800a29b2  xor     r14d, r14d
0x1800a29b5  mov     [rsp+110h+var_E0], r14d
0x1800a29ba  mov     rax, [rdi]
0x1800a29bd  lea     rdx, [rsp+110h+var_E0]
0x1800a29c2  mov     rcx, rdi
0x1800a29c5  mov     rax, [rax+18h]
0x1800a29c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a29ce  mov     rcx, [rbp+5Fh]; this
0x1800a29d2  test    eax, eax
0x1800a29d4  jns     short loc_1800A29EB
0x1800a29d6  mov     r9d, eax; char *
0x1800a29d9  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a29e0  mov     edx, 812h; void *
0x1800a29e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a29eb  mov     r8d, [rsp+110h+var_E0]; int
0x1800a29f0  mov     edx, 1; int
0x1800a29f5  mov     rcx, [rbp+57h+var_58]; this
0x1800a29f9  call    ?Bind@Statement@@QEAAXHH@Z; Statement::Bind(int,int)
0x1800a29fe  lea     r8, String1; "toastCondensed"
0x1800a2a05  mov     edx, 2; int
0x1800a2a0a  mov     rcx, [rbp+57h+var_58]; this
0x1800a2a0e  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x1800a2a13  mov     [rbp+57h+var_80], r14
0x1800a2a17  mov     [rbp+57h+var_78], r14
0x1800a2a1b  mov     [rbp+57h+var_70], r14
0x1800a2a1f  mov     rax, [rdi]
0x1800a2a22  mov     rbx, [rax+38h]
0x1800a2a26  lea     rcx, [rbp+57h+var_80]
0x1800a2a2a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a2a2f  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800a2a33  mov     [rbp+57h+var_78], r15
0x1800a2a37  mov     [rbp+57h+var_70], r15
0x1800a2a3b  lea     rdx, [rbp+57h+var_80]
0x1800a2a3f  mov     rcx, rdi
0x1800a2a42  mov     rax, rbx
0x1800a2a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2a4a  mov     rcx, [rbp+5Fh]; this
0x1800a2a4e  test    eax, eax
0x1800a2a50  jns     short loc_1800A2A67
0x1800a2a52  mov     r9d, eax; char *
0x1800a2a55  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a2a5c  mov     edx, 818h; void *
0x1800a2a61  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a2a67  mov     rax, [rbp+57h+var_80]
0x1800a2a6b  lea     rsi, word_180124798
0x1800a2a72  mov     r8, rsi
0x1800a2a75  test    rax, rax
0x1800a2a78  cmovnz  r8, rax; unsigned __int16 *
0x1800a2a7c  mov     edx, 3; int
0x1800a2a81  mov     rcx, [rbp+57h+var_58]; this
0x1800a2a85  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x1800a2a8a  mov     [rbp+57h+var_98], r14
0x1800a2a8e  mov     [rbp+57h+var_90], r14
0x1800a2a92  mov     [rbp+57h+var_88], r14
0x1800a2a96  mov     rax, [rdi]
0x1800a2a99  mov     rbx, [rax+40h]
0x1800a2a9d  lea     rcx, [rbp+57h+var_98]
0x1800a2aa1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a2aa6  mov     [rbp+57h+var_90], r15
0x1800a2aaa  mov     [rbp+57h+var_88], r15
0x1800a2aae  lea     rdx, [rbp+57h+var_98]
0x1800a2ab2  mov     rcx, rdi
0x1800a2ab5  mov     rax, rbx
0x1800a2ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2abd  mov     rcx, [rbp+5Fh]; this
0x1800a2ac1  test    eax, eax
0x1800a2ac3  jns     short loc_1800A2ADA
0x1800a2ac5  mov     r9d, eax; char *
0x1800a2ac8  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a2acf  mov     edx, 81Ch; void *
0x1800a2ad4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a2ada  mov     rax, [rbp+57h+var_98]
0x1800a2ade  test    rax, rax
0x1800a2ae1  cmovnz  rsi, rax
0x1800a2ae5  mov     r8, rsi; unsigned __int16 *
0x1800a2ae8  mov     edx, 4; int
0x1800a2aed  mov     rcx, [rbp+57h+var_58]; this
0x1800a2af1  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x1800a2af6  mov     [rbp+57h+var_D0], r14
0x1800a2afa  mov     rax, [rdi]
0x1800a2afd  lea     rdx, [rbp+57h+var_D0]
0x1800a2b01  mov     rcx, rdi
0x1800a2b04  mov     rax, [rax+48h]
0x1800a2b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2b0d  mov     rcx, [rbp+5Fh]; this
0x1800a2b11  test    eax, eax
0x1800a2b13  jns     short loc_1800A2B2A
0x1800a2b15  mov     r9d, eax; char *
0x1800a2b18  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a2b1f  mov     edx, 820h; void *
0x1800a2b24  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a2b2a  mov     r8d, dword ptr [rbp+57h+var_D0+4]
0x1800a2b2e  shl     r8, 20h
0x1800a2b32  mov     eax, dword ptr [rbp+57h+var_D0]
0x1800a2b35  or      r8, rax; __int64
0x1800a2b38  mov     edx, 5; int
0x1800a2b3d  mov     rcx, [rbp+57h+var_58]; this
0x1800a2b41  call    ?Bind@Statement@@QEAAXH_J@Z; Statement::Bind(int,__int64)
0x1800a2b46  mov     [rsp+110h+var_D8], r14
0x1800a2b4b  mov     rax, [rdi]
0x1800a2b4e  lea     rdx, [rsp+110h+var_D8]
0x1800a2b53  mov     rcx, rdi
0x1800a2b56  mov     rax, [rax+58h]
0x1800a2b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2b5f  mov     rcx, [rbp+5Fh]; this
0x1800a2b63  test    eax, eax
0x1800a2b65  jns     short loc_1800A2B7C
0x1800a2b67  mov     r9d, eax; char *
0x1800a2b6a  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a2b71  mov     edx, 824h; void *
0x1800a2b76  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a2b7c  mov     r8d, dword ptr [rbp+57h+var_D8+4]
0x1800a2b80  shl     r8, 20h
0x1800a2b84  mov     eax, dword ptr [rsp+110h+var_D8]
0x1800a2b88  or      r8, rax; __int64
0x1800a2b8b  mov     edx, 6; int
0x1800a2b90  mov     rcx, [rbp+57h+var_58]; this
0x1800a2b94  call    ?Bind@Statement@@QEAAXH_J@Z; Statement::Bind(int,__int64)
0x1800a2b99  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800a2ba0  movdqu  [rbp+57h+var_38], xmm0
0x1800a2ba5  mov     rax, [rdi]
0x1800a2ba8  lea     rdx, [rbp+57h+var_38]
0x1800a2bac  mov     rcx, rdi
0x1800a2baf  mov     rax, [rax+70h]
0x1800a2bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2bb8  mov     rcx, [rbp+5Fh]; this
0x1800a2bbc  test    eax, eax
0x1800a2bbe  jns     short loc_1800A2BD5
0x1800a2bc0  mov     r9d, eax; char *
0x1800a2bc3  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a2bca  mov     edx, 828h; void *
0x1800a2bcf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a2bd5  mov     rax, [rbp+57h+var_58]
0x1800a2bd9  mov     rcx, [rax]
0x1800a2bdc  mov     rax, [rbp+5Fh]
0x1800a2be0  test    rcx, rcx
0x1800a2be3  jnz     short loc_1800A2C00
0x1800a2be5  mov     r9d, 8007139Fh; char *
0x1800a2beb  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a2bf2  mov     edx, 10Bh; void *
0x1800a2bf7  mov     rcx, rax; this
0x1800a2bfa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a2c00  mov     qword ptr [rsp+110h+var_F0], r15; int
0x1800a2c05  mov     r9d, 10h
0x1800a2c0b  lea     r8, [rbp+57h+var_38]
0x1800a2c0f  lea     edx, [r9-9]
0x1800a2c13  call    cs:__imp_sqlite3_bind_blob
0x1800a2c19  test    eax, eax
0x1800a2c1b  jle     short loc_1800A2C25
0x1800a2c1d  movzx   eax, ax
0x1800a2c20  or      eax, 87AF0000h
0x1800a2c25  mov     rcx, [rbp+5Fh]; this
0x1800a2c29  test    eax, eax
0x1800a2c2b  jns     short loc_1800A2C42
0x1800a2c2d  mov     r9d, eax; char *
0x1800a2c30  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a2c37  mov     edx, 10Ch; void *
0x1800a2c3c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a2c42  mov     [rbp+57h+var_B0], r14
0x1800a2c46  mov     [rbp+57h+var_A8], r14
0x1800a2c4a  mov     [rbp+57h+var_A0], r14
0x1800a2c4e  mov     rax, [rdi]
0x1800a2c51  mov     rbx, [rax+78h]
0x1800a2c55  lea     rcx, [rbp+57h+var_B0]
0x1800a2c59  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a2c5e  mov     [rbp+57h+var_A8], r15
0x1800a2c62  mov     [rbp+57h+var_A0], r15
0x1800a2c66  lea     rdx, [rbp+57h+var_B0]
0x1800a2c6a  mov     rcx, rdi
0x1800a2c6d  mov     rax, rbx
0x1800a2c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2c75  mov     rcx, [rbp+5Fh]; this
0x1800a2c79  test    eax, eax
0x1800a2c7b  jns     short loc_1800A2C92
0x1800a2c7d  mov     r9d, eax; char *
0x1800a2c80  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a2c87  mov     edx, 82Ch; void *
0x1800a2c8c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a2c92  mov     r8, [rbp+57h+var_B0]; unsigned __int16 *
0x1800a2c96  mov     edx, 8; int
0x1800a2c9b  mov     rcx, [rbp+57h+var_58]; this
0x1800a2c9f  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x1800a2ca4  mov     [rbp+57h+pv], r14
0x1800a2ca8  mov     [rbp+57h+var_C0], r14
0x1800a2cac  mov     [rbp+57h+var_B8], r14
0x1800a2cb0  mov     rax, [rdi]
0x1800a2cb3  mov     rbx, [rax+20h]
0x1800a2cb7  lea     rcx, [rbp+57h+pv]
0x1800a2cbb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a2cc0  mov     [rbp+57h+var_C0], r15
0x1800a2cc4  mov     [rbp+57h+var_B8], r15
0x1800a2cc8  lea     rdx, [rbp+57h+pv]
0x1800a2ccc  mov     rcx, rdi
0x1800a2ccf  mov     rax, rbx
0x1800a2cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2cd7  mov     rcx, [rbp+5Fh]; this
0x1800a2cdb  test    eax, eax
0x1800a2cdd  jns     short loc_1800A2CF4
0x1800a2cdf  mov     r9d, eax; char *
0x1800a2ce2  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a2ce9  mov     edx, 830h; void *
0x1800a2cee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a2cf4  mov     r8, [rbp+57h+pv]; unsigned __int16 *
0x1800a2cf8  mov     edx, 9; int
0x1800a2cfd  mov     rcx, [rbp+57h+var_58]; this
0x1800a2d01  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x1800a2d06  mov     rcx, [rbp+57h+var_58]; this
0x1800a2d0a  call    ?FetchNoRow@Statement@@QEAAXXZ; Statement::FetchNoRow(void)
0x1800a2d0f  nop
0x1800a2d10  mov     rcx, [rbp+57h+pv]; pv
0x1800a2d14  test    rcx, rcx
0x1800a2d17  jz      short loc_1800A2D23
0x1800a2d19  call    cs:__imp_CoTaskMemFree
0x1800a2d1f  mov     [rbp+57h+pv], r14
0x1800a2d23  mov     [rbp+57h+var_C0], r14
0x1800a2d27  mov     [rbp+57h+var_B8], r14
0x1800a2d2b  mov     rcx, [rbp+57h+var_B0]; pv
0x1800a2d2f  test    rcx, rcx
0x1800a2d32  jz      short loc_1800A2D3E
0x1800a2d34  call    cs:__imp_CoTaskMemFree
0x1800a2d3a  mov     [rbp+57h+var_B0], r14
0x1800a2d3e  mov     [rbp+57h+var_A8], r14
0x1800a2d42  mov     [rbp+57h+var_A0], r14
0x1800a2d46  mov     rcx, [rbp+57h+var_98]; pv
0x1800a2d4a  test    rcx, rcx
0x1800a2d4d  jz      short loc_1800A2D59
0x1800a2d4f  call    cs:__imp_CoTaskMemFree
0x1800a2d55  mov     [rbp+57h+var_98], r14
0x1800a2d59  mov     [rbp+57h+var_90], r14
0x1800a2d5d  mov     [rbp+57h+var_88], r14
0x1800a2d61  mov     rcx, [rbp+57h+var_80]; pv
0x1800a2d65  test    rcx, rcx
0x1800a2d68  jz      short loc_1800A2D74
0x1800a2d6a  call    cs:__imp_CoTaskMemFree
0x1800a2d70  mov     [rbp+57h+var_80], r14
0x1800a2d74  mov     [rbp+57h+var_78], r14
0x1800a2d78  mov     [rbp+57h+var_70], r14
0x1800a2d7c  lea     rcx, [rbp+57h+var_68]; this
0x1800a2d80  call    ??1AutoAddToCache@@QEAA@XZ; AutoAddToCache::~AutoAddToCache(void)
0x1800a2d85  mov     rcx, [rbp+57h+var_28]
0x1800a2d89  xor     rcx, rsp; StackCookie
0x1800a2d8c  call    __security_check_cookie
0x1800a2d91  mov     rbx, [rsp+110h+arg_10]
0x1800a2d99  add     rsp, 0F0h
0x1800a2da0  pop     r15
0x1800a2da2  pop     r14
0x1800a2da4  pop     rdi
0x1800a2da5  pop     rsi
0x1800a2da6  pop     rbp
0x1800a2da7  retn
```
