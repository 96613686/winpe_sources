# Windows::Compat::Inventory::SqliteInvCache::OpenDb(ushort const *,sqlite3 * &,int)

- ea: `0x1800a276c`
- end: `0x1800a2b18`
- name: `?OpenDb@SqliteInvCache@Inventory@Compat@Windows@@SAJPEBGAEAPEAUsqlite3@@H@Z`
- size: `940`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct sqlite3 **, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800a1368`

## callees

- `0x180003924`
- `0x18000dc08`
- `0x180012920`
- `0x180013334`
- `0x180040eec`
- `0x18004aa5c`
- `0x18007a9cf`
- `0x1800a276c`
- `0x1800f1f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a29ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a29ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800a282d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800a282d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a29c7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a29c7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a293d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a293d`
- `winsqlite3!sqlite3_errmsg` at `0x1800a2aad`
- `winsqlite3!sqlite3_errmsg` at `0x1800a2aad`
- `winsqlite3!sqlite3_open_v2` at `0x1800a2a9e`
- `winsqlite3!sqlite3_open_v2` at `0x1800a2a9e`

## string_xrefs

- `0x1800a27df`: `Amcache`
- `0x1800a2a02`: `CreateFileW failed for %ls: [%d]`
- `0x1800a2807`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x1800a287e`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x1800a2a0f`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x1800a2a57`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x1800a2ac9`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x1800a2871`: `GetSystemWindowsDirectory [%d]`
- `0x1800a283c`: `\AppCompat\Programs\`
- `0x1800a2abc`: `sqlite3_open_v2 failed: [%d] %hs`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::OpenDb(
        const unsigned __int16 *a1,
        struct sqlite3 **a2,
        int a3)
{
  unsigned int v6; // edx
  int PersistedLocation; // eax
  DWORD LastError; // ebx
  const char *v9; // r9
  int v10; // r8d
  unsigned int v11; // edi
  DWORD v12; // eax
  char v13; // al
  char *v14; // rdx
  int v15; // edi
  __int64 v16; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D8h]
  _QWORD v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  char v22[272]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR FileName[264]; // [rsp+370h] [rbp+270h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(v22, 0, 0x104u);
  PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(Buffer, v6, L"Amcache", &sourceString, 0);
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v9 = "Failed to get persisted reg key location: 0x%x";
    v10 = 434;
LABEL_3:
    dwCreationDisposition[0] = PersistedLocation;
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Inventory::SqliteInvCache::OpenDb",
      v10,
      (_DWORD)v9,
      *(_QWORD *)dwCreationDisposition);
    return LastError;
  }
  if ( !Buffer[0] )
  {
    if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) - 1 > 0x103 )
    {
      LastError = GetLastError();
      dwCreationDisposition[0] = LastError;
      AslLogCallPrintf(
        1,
        (unsigned int)"Windows::Compat::Inventory::SqliteInvCache::OpenDb",
        445,
        (unsigned int)"GetSystemWindowsDirectory [%d]",
        *(_QWORD *)dwCreationDisposition);
      goto LABEL_9;
    }
    PersistedLocation = StringCchCatW(Buffer, 0x104u, L"\\AppCompat\\Programs\\");
    LastError = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v9 = "StringCchCatW failed [%#x]";
      v10 = 453;
      goto LABEL_3;
    }
  }
  PersistedLocation = StringCchCatW(Buffer, 0x104u, a1);
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v9 = "StringCchCatW failed [%#x]";
    v10 = 461;
    goto LABEL_3;
  }
  PersistedLocation = StringCchCatW(Buffer, 0x104u, L".db");
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v9 = "StringCchCatW failed [%#x]";
    v10 = 468;
    goto LABEL_3;
  }
  if ( a3 )
  {
    v11 = 16908486;
    goto LABEL_17;
  }
  v11 = 16777286;
  if ( GetFileAttributesW(Buffer) == -1 )
  {
    v12 = GetLastError();
    LastError = v12;
    if ( v12 == 2 )
    {
      memset_0(FileName, 0, 0x208u);
      PersistedLocation = StringCchPrintfW(FileName, 0x104u, L"%ls.tmp", Buffer);
      LastError = PersistedLocation;
      if ( PersistedLocation < 0 )
      {
        v9 = "StringCchPrintfW failed [%#x]";
        v10 = 494;
        goto LABEL_3;
      }
      v20[0] = CreateFileW(FileName, 0x40000000u, 0, 0, 1u, 0x4000080u, 0);
      if ( (unsigned __int64)(v20[0] - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        dwFlagsAndAttributes[0] = LastError;
        AslLogCallPrintf(
          1,
          (unsigned int)"Windows::Compat::Inventory::SqliteInvCache::OpenDb",
          502,
          (unsigned int)"CreateFileW failed for %ls: [%d]",
          FileName,
          *(_QWORD *)dwFlagsAndAttributes);
        if ( (int)LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v20);
        return LastError;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v20);
      goto LABEL_17;
    }
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Inventory::SqliteInvCache::OpenDb",
      509,
      (unsigned int)"GetFileAttributesW failed for %ls: [%d]",
      Buffer,
      v12);
LABEL_9:
    if ( (int)LastError <= 0 )
      return LastError;
    LastError = (unsigned __int16)LastError;
LABEL_38:
    LastError |= 0x80070000;
    return LastError;
  }
LABEL_17:
  PersistedLocation = StringCchPrintfA(v22, 0x104u, "file:/%ls", Buffer);
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v9 = "StringCchPrintfA failed [%#x]";
    v10 = 519;
    goto LABEL_3;
  }
  v13 = v22[0];
  if ( v22[0] )
  {
    v14 = v22;
    do
    {
      if ( v13 == 92 )
        *v14 = 47;
      v13 = *++v14;
    }
    while ( *v14 );
  }
  v15 = sqlite3_open_v2(v22, a2, v11, 0);
  if ( v15 )
  {
    v16 = sqlite3_errmsg(*a2);
    dwCreationDisposition[0] = v15;
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Inventory::SqliteInvCache::OpenDb",
      535,
      (unsigned int)"sqlite3_open_v2 failed: [%d] %hs",
      *(_QWORD *)dwCreationDisposition,
      v16);
    if ( v15 <= 0 )
      return (DWORD)v15;
    LastError = (unsigned __int16)v15;
    goto LABEL_38;
  }
  return LastError;
}

```

## disassembly

```asm
0x1800a276c  mov     [rsp-8+arg_10], rbx
0x1800a2771  mov     [rsp-8+arg_18], rsi
0x1800a2776  push    rbp
0x1800a2777  push    rdi
0x1800a2778  push    r12
0x1800a277a  push    r14
0x1800a277c  push    r15
0x1800a277e  lea     rbp, [rsp-490h]
0x1800a2786  sub     rsp, 590h
0x1800a278d  mov     rax, cs:__security_cookie
0x1800a2794  xor     rax, rsp
0x1800a2797  mov     [rbp+4B0h+var_30], rax
0x1800a279e  mov     edi, r8d
0x1800a27a1  mov     r14, rdx
0x1800a27a4  mov     rsi, rcx
0x1800a27a7  xor     edx, edx; Val
0x1800a27a9  mov     r8d, 208h; Size
0x1800a27af  lea     rcx, [rsp+5B0h+Buffer]; void *
0x1800a27b4  call    memset_0
0x1800a27b9  mov     r12d, 104h
0x1800a27bf  mov     r8d, r12d; Size
0x1800a27c2  xor     edx, edx; Val
0x1800a27c4  lea     rcx, [rbp+4B0h+var_350]; void *
0x1800a27cb  call    memset_0
0x1800a27d0  xor     r15d, r15d
0x1800a27d3  mov     [rsp+5B0h+dwCreationDisposition], r15d; int
0x1800a27d8  lea     r9, sourceString; unsigned __int16 *
0x1800a27df  lea     r8, aAmcache; "Amcache"
0x1800a27e6  lea     rcx, [rsp+5B0h+Buffer]; Destination
0x1800a27eb  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x1800a27f0  mov     ebx, eax
0x1800a27f2  test    eax, eax
0x1800a27f4  jns     short loc_1800A281D
0x1800a27f6  lea     r9, aFailedToGetPer_3; "Failed to get persisted reg key locatio"...
0x1800a27fd  mov     r8d, 1B2h
0x1800a2803  mov     [rsp+5B0h+dwCreationDisposition], eax
0x1800a2807  lea     rdx, aWindowsCompatI_73; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800a280e  mov     ecx, 1
0x1800a2813  call    AslLogCallPrintf
0x1800a2818  jmp     loc_1800A2AEB
0x1800a281d  cmp     [rsp+5B0h+Buffer], r15w
0x1800a2823  jnz     short loc_1800A289F
0x1800a2825  mov     edx, r12d; uSize
0x1800a2828  lea     rcx, [rsp+5B0h+Buffer]; lpBuffer
0x1800a282d  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800a2833  dec     eax
0x1800a2835  cmp     eax, 103h
0x1800a283a  ja      short loc_1800A2865
0x1800a283c  lea     r8, aAppcompatProgr_0; "\\AppCompat\\Programs\\"
0x1800a2843  mov     rdx, r12; unsigned __int64
0x1800a2846  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x1800a284b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a2850  mov     ebx, eax
0x1800a2852  test    eax, eax
0x1800a2854  jns     short loc_1800A289F
0x1800a2856  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x1800a285d  mov     r8d, 1C5h
0x1800a2863  jmp     short loc_1800A2803
0x1800a2865  call    cs:__imp_GetLastError
0x1800a286b  mov     ebx, eax
0x1800a286d  mov     [rsp+5B0h+dwCreationDisposition], eax
0x1800a2871  lea     r9, aGetsystemwindo; "GetSystemWindowsDirectory [%d]"
0x1800a2878  mov     r8d, 1BDh
0x1800a287e  lea     rdx, aWindowsCompatI_73; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800a2885  mov     ecx, 1
0x1800a288a  call    AslLogCallPrintf
0x1800a288f  test    ebx, ebx
0x1800a2891  jle     loc_1800A2AEB
0x1800a2897  movzx   ebx, bx
0x1800a289a  jmp     loc_1800A2AE5
0x1800a289f  mov     r8, rsi; unsigned __int16 *
0x1800a28a2  mov     rdx, r12; unsigned __int64
0x1800a28a5  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x1800a28aa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a28af  mov     ebx, eax
0x1800a28b1  test    eax, eax
0x1800a28b3  jns     short loc_1800A28C7
0x1800a28b5  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x1800a28bc  mov     r8d, 1CDh
0x1800a28c2  jmp     loc_1800A2803
0x1800a28c7  lea     r8, aDb; ".db"
0x1800a28ce  mov     rdx, r12; unsigned __int64
0x1800a28d1  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x1800a28d6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a28db  mov     ebx, eax
0x1800a28dd  test    eax, eax
0x1800a28df  jns     short loc_1800A28F3
0x1800a28e1  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x1800a28e8  mov     r8d, 1D4h
0x1800a28ee  jmp     loc_1800A2803
0x1800a28f3  test    edi, edi
0x1800a28f5  jz      short loc_1800A2933
0x1800a28f7  mov     edi, 10200C6h
0x1800a28fc  lea     r9, [rsp+5B0h+Buffer]
0x1800a2901  lea     r8, aFileLs; "file:/%ls"
0x1800a2908  mov     rdx, r12; unsigned __int64
0x1800a290b  lea     rcx, [rbp+4B0h+var_350]; char *
0x1800a2912  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800a2917  mov     ebx, eax
0x1800a2919  test    eax, eax
0x1800a291b  jns     loc_1800A2A6D
0x1800a2921  lea     r9, aStringcchprint; "StringCchPrintfA failed [%#x]"
0x1800a2928  mov     r8d, 207h
0x1800a292e  jmp     loc_1800A2803
0x1800a2933  mov     edi, 1000046h
0x1800a2938  lea     rcx, [rsp+5B0h+Buffer]; lpFileName
0x1800a293d  call    cs:__imp_GetFileAttributesW
0x1800a2943  cmp     eax, 0FFFFFFFFh
0x1800a2946  jnz     short loc_1800A28FC
0x1800a2948  call    cs:__imp_GetLastError
0x1800a294e  mov     ebx, eax
0x1800a2950  cmp     eax, 2
0x1800a2953  jnz     loc_1800A2A3C
0x1800a2959  xor     edx, edx; Val
0x1800a295b  mov     r8d, 208h; Size
0x1800a2961  lea     rcx, [rbp+4B0h+FileName]; void *
0x1800a2968  call    memset_0
0x1800a296d  lea     r9, [rsp+5B0h+Buffer]
0x1800a2972  lea     r8, aLsTmp; "%ls.tmp"
0x1800a2979  mov     rdx, r12; unsigned __int64
0x1800a297c  lea     rcx, [rbp+4B0h+FileName]; unsigned __int16 *
0x1800a2983  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a2988  mov     ebx, eax
0x1800a298a  test    eax, eax
0x1800a298c  jns     short loc_1800A29A0
0x1800a298e  lea     r9, aStringcchprint_6; "StringCchPrintfW failed [%#x]"
0x1800a2995  mov     r8d, 1EEh
0x1800a299b  jmp     loc_1800A2803
0x1800a29a0  mov     [rsp+5B0h+hTemplateFile], r15; hTemplateFile
0x1800a29a5  mov     [rsp+5B0h+dwFlagsAndAttributes], 4000080h; dwFlagsAndAttributes
0x1800a29ad  mov     [rsp+5B0h+dwCreationDisposition], 1; dwCreationDisposition
0x1800a29b5  xor     r9d, r9d; lpSecurityAttributes
0x1800a29b8  xor     r8d, r8d; dwShareMode
0x1800a29bb  mov     edx, 40000000h; dwDesiredAccess
0x1800a29c0  lea     rcx, [rbp+4B0h+FileName]; lpFileName
0x1800a29c7  call    cs:__imp_CreateFileW
0x1800a29cd  mov     [rsp+5B0h+var_570], rax
0x1800a29d2  dec     rax
0x1800a29d5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a29d9  ja      short loc_1800A29EA
0x1800a29db  lea     rcx, [rsp+5B0h+var_570]
0x1800a29e0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a29e5  jmp     loc_1800A28FC
0x1800a29ea  call    cs:__imp_GetLastError
0x1800a29f0  mov     ebx, eax
0x1800a29f2  mov     [rsp+5B0h+dwFlagsAndAttributes], eax
0x1800a29f6  lea     rax, [rbp+4B0h+FileName]
0x1800a29fd  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rax
0x1800a2a02  lea     r9, aCreatefilewFai_0; "CreateFileW failed for %ls: [%d]"
0x1800a2a09  mov     r8d, 1F6h
0x1800a2a0f  lea     rdx, aWindowsCompatI_73; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800a2a16  mov     ecx, 1
0x1800a2a1b  call    AslLogCallPrintf
0x1800a2a20  test    ebx, ebx
0x1800a2a22  jle     short loc_1800A2A2D
0x1800a2a24  movzx   ebx, bx
0x1800a2a27  or      ebx, 80070000h
0x1800a2a2d  lea     rcx, [rsp+5B0h+var_570]
0x1800a2a32  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a2a37  jmp     loc_1800A2AEB
0x1800a2a3c  mov     [rsp+5B0h+dwFlagsAndAttributes], ebx
0x1800a2a40  lea     rax, [rsp+5B0h+Buffer]
0x1800a2a45  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rax
0x1800a2a4a  lea     r9, aGetfileattribu; "GetFileAttributesW failed for %ls: [%d]"
0x1800a2a51  mov     r8d, 1FDh
0x1800a2a57  lea     rdx, aWindowsCompatI_73; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800a2a5e  mov     ecx, 1
0x1800a2a63  call    AslLogCallPrintf
0x1800a2a68  jmp     loc_1800A288F
0x1800a2a6d  mov     al, [rbp+4B0h+var_350]
0x1800a2a73  test    al, al
0x1800a2a75  jz      short loc_1800A2A8E
0x1800a2a77  lea     rdx, [rbp+4B0h+var_350]
0x1800a2a7e  cmp     al, 5Ch ; '\'
0x1800a2a80  jnz     short loc_1800A2A85
0x1800a2a82  mov     byte ptr [rdx], 2Fh ; '/'
0x1800a2a85  inc     rdx
0x1800a2a88  mov     al, [rdx]
0x1800a2a8a  test    al, al
0x1800a2a8c  jnz     short loc_1800A2A7E
0x1800a2a8e  xor     r9d, r9d
0x1800a2a91  mov     r8d, edi
0x1800a2a94  mov     rdx, r14
0x1800a2a97  lea     rcx, [rbp+4B0h+var_350]
0x1800a2a9e  call    cs:__imp_sqlite3_open_v2
0x1800a2aa4  mov     edi, eax
0x1800a2aa6  test    eax, eax
0x1800a2aa8  jz      short loc_1800A2AEB
0x1800a2aaa  mov     rcx, [r14]
0x1800a2aad  call    cs:__imp_sqlite3_errmsg
0x1800a2ab3  mov     qword ptr [rsp+5B0h+dwFlagsAndAttributes], rax
0x1800a2ab8  mov     [rsp+5B0h+dwCreationDisposition], edi
0x1800a2abc  lea     r9, aSqlite3OpenV2F; "sqlite3_open_v2 failed: [%d] %hs"
0x1800a2ac3  mov     r8d, 217h
0x1800a2ac9  lea     rdx, aWindowsCompatI_73; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800a2ad0  mov     ecx, 1
0x1800a2ad5  call    AslLogCallPrintf
0x1800a2ada  test    edi, edi
0x1800a2adc  jg      short loc_1800A2AE2
0x1800a2ade  mov     ebx, edi
0x1800a2ae0  jmp     short loc_1800A2AEB
0x1800a2ae2  movzx   ebx, di
0x1800a2ae5  or      ebx, 80070000h
0x1800a2aeb  mov     eax, ebx
0x1800a2aed  mov     rcx, [rbp+4B0h+var_30]
0x1800a2af4  xor     rcx, rsp; StackCookie
0x1800a2af7  call    __security_check_cookie
0x1800a2afc  lea     r11, [rsp+5B0h+var_20]
0x1800a2b04  mov     rbx, [r11+40h]
0x1800a2b08  mov     rsi, [r11+48h]
0x1800a2b0c  mov     rsp, r11
0x1800a2b0f  pop     r15
0x1800a2b11  pop     r14
0x1800a2b13  pop     r12
0x1800a2b15  pop     rdi
0x1800a2b16  pop     rbp
0x1800a2b17  retn
```
