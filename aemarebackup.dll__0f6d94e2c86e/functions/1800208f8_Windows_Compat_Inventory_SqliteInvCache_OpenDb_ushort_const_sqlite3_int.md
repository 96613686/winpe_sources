# Windows::Compat::Inventory::SqliteInvCache::OpenDb(ushort const *,sqlite3 * &,int)

- ea: `0x1800208f8`
- end: `0x180020ca8`
- name: `?OpenDb@SqliteInvCache@Inventory@Compat@Windows@@SAJPEBGAEAPEAUsqlite3@@H@Z`
- size: `944`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct sqlite3 **, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001ec10`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x18000d508`
- `0x18000d62c`
- `0x18001dbec`
- `0x1800208f8`
- `0x180024fb8`
- `0x18004c020`
- `0x18007645c`
- `0x1800c4b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800209ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020acb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800209ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020acb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020b64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020bc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020b64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020bc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800209b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800209b9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180020b4a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180020b4a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180020ac0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180020ac0`

## string_xrefs

- `0x18002096b`: `Amcache`
- `0x1800209fa`: `GetSystemWindowsDirectory [%d]`
- `0x1800209c8`: `\AppCompat\Programs\`
- `0x180020b87`: `CreateFileW failed for %ls: [%d]`
- `0x180020c4c`: `sqlite3_open_v2 failed: [%d] %hs`
- `0x180020993`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x180020a07`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x180020b94`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x180020be9`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x180020c59`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::OpenDb(
        const unsigned __int16 *a1,
        struct sqlite3 **a2,
        int a3)
{
  unsigned int v6; // edx
  int PersistedLocation; // eax
  unsigned __int64 v8; // rdx
  DWORD LastError; // edi
  const char *v10; // r9
  __int64 v11; // r8
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  unsigned int v14; // esi
  DWORD v15; // eax
  char *FileW; // rbx
  char v17; // al
  char *v18; // rdx
  int v19; // ebx
  const char *v20; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  char v24[272]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR FileName[264]; // [rsp+370h] [rbp+270h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(v24, 0, 0x104u);
  PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(
                        Buffer,
                        v6,
                        L"Amcache",
                        &dword_1800F6C3C,
                        0);
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v10 = "Failed to get persisted reg key location: 0x%x";
    v11 = 434;
LABEL_3:
    dwCreationDisposition[0] = PersistedLocation;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::OpenDb",
      v11,
      v10,
      *(_QWORD *)dwCreationDisposition);
    return LastError;
  }
  if ( !Buffer[0] )
  {
    if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) - 1 > 0x103 )
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::OpenDb",
        445,
        "GetSystemWindowsDirectory [%d]",
        LastError);
      goto LABEL_9;
    }
    PersistedLocation = StringCchCatW(Buffer, v12, L"\\AppCompat\\Programs\\");
    LastError = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v10 = "StringCchCatW failed [%#x]";
      v11 = 453;
      goto LABEL_3;
    }
  }
  PersistedLocation = StringCchCatW(Buffer, v8, a1);
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v10 = "StringCchCatW failed [%#x]";
    v11 = 461;
    goto LABEL_3;
  }
  PersistedLocation = StringCchCatW(Buffer, v13, L".db");
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v10 = "StringCchCatW failed [%#x]";
    v11 = 468;
    goto LABEL_3;
  }
  if ( a3 )
  {
    v14 = 16908486;
    goto LABEL_17;
  }
  v14 = 16777286;
  if ( GetFileAttributesW(Buffer) == -1 )
  {
    v15 = GetLastError();
    LastError = v15;
    if ( v15 == 2 )
    {
      memset_0(FileName, 0, 0x208u);
      PersistedLocation = StringCchPrintfW(FileName, 0x104u, L"%ls.tmp", Buffer);
      LastError = PersistedLocation;
      if ( PersistedLocation < 0 )
      {
        v10 = "StringCchPrintfW failed [%#x]";
        v11 = 494;
        goto LABEL_3;
      }
      FileW = (char *)CreateFileW(FileName, 0x40000000u, 0, 0, 1u, 0x4000080u, 0);
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::SqliteInvCache::OpenDb",
          502,
          "CreateFileW failed for %ls: [%d]",
          FileName,
          LastError);
        if ( (int)LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(FileW);
        return LastError;
      }
      CloseHandle(FileW);
      goto LABEL_17;
    }
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::OpenDb",
      509,
      "GetFileAttributesW failed for %ls: [%d]",
      Buffer,
      v15);
LABEL_9:
    if ( (int)LastError <= 0 )
      return LastError;
    LastError = (unsigned __int16)LastError;
LABEL_39:
    LastError |= 0x80070000;
    return LastError;
  }
LABEL_17:
  PersistedLocation = StringCchPrintfA(v24, 0x104u, "file:/%ls", Buffer);
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v10 = "StringCchPrintfA failed [%#x]";
    v11 = 519;
    goto LABEL_3;
  }
  v17 = v24[0];
  if ( v24[0] )
  {
    v18 = v24;
    do
    {
      if ( v17 == 92 )
        *v18 = 47;
      v17 = *++v18;
    }
    while ( *v18 );
  }
  v19 = openDatabase(v24, a2, v14, 0);
  if ( v19 )
  {
    v20 = (const char *)sqlite3_errmsg(*a2);
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::OpenDb",
      535,
      "sqlite3_open_v2 failed: [%d] %hs",
      v19,
      v20);
    if ( v19 <= 0 )
      return (DWORD)v19;
    LastError = (unsigned __int16)v19;
    goto LABEL_39;
  }
  return LastError;
}

```

## disassembly

```asm
0x1800208f8  mov     [rsp-8+arg_10], rbx
0x1800208fd  mov     [rsp-8+arg_18], rsi
0x180020902  push    rbp
0x180020903  push    rdi
0x180020904  push    r12
0x180020906  push    r14
0x180020908  push    r15
0x18002090a  lea     rbp, [rsp-490h]
0x180020912  sub     rsp, 590h
0x180020919  mov     rax, cs:__security_cookie
0x180020920  xor     rax, rsp
0x180020923  mov     [rbp+4B0h+var_30], rax
0x18002092a  mov     ebx, r8d
0x18002092d  mov     r14, rdx
0x180020930  mov     rsi, rcx
0x180020933  xor     edx, edx; Val
0x180020935  mov     r8d, 208h; Size
0x18002093b  lea     rcx, [rsp+5B0h+Buffer]; void *
0x180020940  call    memset_0
0x180020945  mov     r12d, 104h
0x18002094b  mov     r8d, r12d; Size
0x18002094e  xor     edx, edx; Val
0x180020950  lea     rcx, [rbp+4B0h+var_350]; void *
0x180020957  call    memset_0
0x18002095c  xor     r15d, r15d
0x18002095f  mov     [rsp+5B0h+dwCreationDisposition], r15d; int
0x180020964  lea     r9, dword_1800F6C3C; unsigned __int16 *
0x18002096b  lea     r8, aAmcache; "Amcache"
0x180020972  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180020977  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x18002097c  mov     edi, eax
0x18002097e  test    eax, eax
0x180020980  jns     short loc_1800209A9
0x180020982  lea     r9, aFailedToGetPer; "Failed to get persisted reg key locatio"...
0x180020989  mov     r8d, 1B2h
0x18002098f  mov     [rsp+5B0h+dwCreationDisposition], eax
0x180020993  lea     rdx, aWindowsCompatI_39; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002099a  mov     ecx, 1
0x18002099f  call    AslLogCallPrintf
0x1800209a4  jmp     loc_180020C7B
0x1800209a9  cmp     [rsp+5B0h+Buffer], r15w
0x1800209af  jnz     short loc_180020A28
0x1800209b1  mov     edx, r12d; uSize
0x1800209b4  lea     rcx, [rsp+5B0h+Buffer]; lpBuffer
0x1800209b9  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800209bf  dec     eax
0x1800209c1  cmp     eax, 103h
0x1800209c6  ja      short loc_1800209EE
0x1800209c8  lea     r8, aAppcompatProgr_0; "\\AppCompat\\Programs\\"
0x1800209cf  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x1800209d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800209d9  mov     edi, eax
0x1800209db  test    eax, eax
0x1800209dd  jns     short loc_180020A28
0x1800209df  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x1800209e6  mov     r8d, 1C5h
0x1800209ec  jmp     short loc_18002098F
0x1800209ee  call    cs:__imp_GetLastError
0x1800209f4  mov     edi, eax
0x1800209f6  mov     [rsp+5B0h+dwCreationDisposition], eax
0x1800209fa  lea     r9, aGetsystemwindo; "GetSystemWindowsDirectory [%d]"
0x180020a01  mov     r8d, 1BDh
0x180020a07  lea     rdx, aWindowsCompatI_39; "Windows::Compat::Inventory::SqliteInvCa"...
0x180020a0e  mov     ecx, 1
0x180020a13  call    AslLogCallPrintf
0x180020a18  test    edi, edi
0x180020a1a  jle     loc_180020C7B
0x180020a20  movzx   edi, di
0x180020a23  jmp     loc_180020C75
0x180020a28  mov     r8, rsi; unsigned __int16 *
0x180020a2b  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180020a30  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180020a35  mov     edi, eax
0x180020a37  test    eax, eax
0x180020a39  jns     short loc_180020A4D
0x180020a3b  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x180020a42  mov     r8d, 1CDh
0x180020a48  jmp     loc_18002098F
0x180020a4d  lea     r8, aDb; ".db"
0x180020a54  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180020a59  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180020a5e  mov     edi, eax
0x180020a60  test    eax, eax
0x180020a62  jns     short loc_180020A76
0x180020a64  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x180020a6b  mov     r8d, 1D4h
0x180020a71  jmp     loc_18002098F
0x180020a76  test    ebx, ebx
0x180020a78  jz      short loc_180020AB6
0x180020a7a  mov     esi, 10200C6h
0x180020a7f  lea     r9, [rsp+5B0h+Buffer]
0x180020a84  lea     r8, aFileLs; "file:/%ls"
0x180020a8b  mov     rdx, r12; unsigned __int64
0x180020a8e  lea     rcx, [rbp+4B0h+var_350]; char *
0x180020a95  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180020a9a  mov     edi, eax
0x180020a9c  test    eax, eax
0x180020a9e  jns     loc_180020BFF
0x180020aa4  lea     r9, aStringcchprint; "StringCchPrintfA failed [%#x]"
0x180020aab  mov     r8d, 207h
0x180020ab1  jmp     loc_18002098F
0x180020ab6  mov     esi, 1000046h
0x180020abb  lea     rcx, [rsp+5B0h+Buffer]; lpFileName
0x180020ac0  call    cs:__imp_GetFileAttributesW
0x180020ac6  cmp     eax, 0FFFFFFFFh
0x180020ac9  jnz     short loc_180020A7F
0x180020acb  call    cs:__imp_GetLastError
0x180020ad1  mov     edi, eax
0x180020ad3  cmp     eax, 2
0x180020ad6  jnz     loc_180020BCE
0x180020adc  xor     edx, edx; Val
0x180020ade  mov     r8d, 208h; Size
0x180020ae4  lea     rcx, [rbp+4B0h+FileName]; void *
0x180020aeb  call    memset_0
0x180020af0  lea     r9, [rsp+5B0h+Buffer]
0x180020af5  lea     r8, aLsTmp; "%ls.tmp"
0x180020afc  mov     rdx, r12; unsigned __int64
0x180020aff  lea     rcx, [rbp+4B0h+FileName]; unsigned __int16 *
0x180020b06  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020b0b  mov     edi, eax
0x180020b0d  test    eax, eax
0x180020b0f  jns     short loc_180020B23
0x180020b11  lea     r9, aStringcchprint_3; "StringCchPrintfW failed [%#x]"
0x180020b18  mov     r8d, 1EEh
0x180020b1e  jmp     loc_18002098F
0x180020b23  mov     [rsp+5B0h+hTemplateFile], r15; hTemplateFile
0x180020b28  mov     [rsp+5B0h+dwFlagsAndAttributes], 4000080h; dwFlagsAndAttributes
0x180020b30  mov     [rsp+5B0h+dwCreationDisposition], 1; dwCreationDisposition
0x180020b38  xor     r9d, r9d; lpSecurityAttributes
0x180020b3b  xor     r8d, r8d; dwShareMode
0x180020b3e  mov     edx, 40000000h; dwDesiredAccess
0x180020b43  lea     rcx, [rbp+4B0h+FileName]; lpFileName
0x180020b4a  call    cs:__imp_CreateFileW
0x180020b50  mov     rbx, rax
0x180020b53  mov     [rsp+5B0h+var_570], rax
0x180020b58  dec     rax
0x180020b5b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020b5f  ja      short loc_180020B6F
0x180020b61  mov     rcx, rbx; hObject
0x180020b64  call    cs:__imp_CloseHandle
0x180020b6a  jmp     loc_180020A7F
0x180020b6f  call    cs:__imp_GetLastError
0x180020b75  mov     edi, eax
0x180020b77  mov     [rsp+5B0h+dwFlagsAndAttributes], eax
0x180020b7b  lea     rax, [rbp+4B0h+FileName]
0x180020b82  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rax
0x180020b87  lea     r9, aCreatefilewFai_0; "CreateFileW failed for %ls: [%d]"
0x180020b8e  mov     r8d, 1F6h
0x180020b94  lea     rdx, aWindowsCompatI_39; "Windows::Compat::Inventory::SqliteInvCa"...
0x180020b9b  mov     ecx, 1
0x180020ba0  call    AslLogCallPrintf
0x180020ba5  test    edi, edi
0x180020ba7  jle     short loc_180020BB2
0x180020ba9  movzx   edi, di
0x180020bac  or      edi, 80070000h
0x180020bb2  lea     rax, [rbx-1]
0x180020bb6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020bba  ja      loc_180020C7B
0x180020bc0  mov     rcx, rbx; hObject
0x180020bc3  call    cs:__imp_CloseHandle
0x180020bc9  jmp     loc_180020C7B
0x180020bce  mov     [rsp+5B0h+dwFlagsAndAttributes], edi
0x180020bd2  lea     rax, [rsp+5B0h+Buffer]
0x180020bd7  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rax
0x180020bdc  lea     r9, aGetfileattribu_1; "GetFileAttributesW failed for %ls: [%d]"
0x180020be3  mov     r8d, 1FDh
0x180020be9  lea     rdx, aWindowsCompatI_39; "Windows::Compat::Inventory::SqliteInvCa"...
0x180020bf0  mov     ecx, 1
0x180020bf5  call    AslLogCallPrintf
0x180020bfa  jmp     loc_180020A18
0x180020bff  mov     al, [rbp+4B0h+var_350]
0x180020c05  test    al, al
0x180020c07  jz      short loc_180020C20
0x180020c09  lea     rdx, [rbp+4B0h+var_350]
0x180020c10  cmp     al, 5Ch ; '\'
0x180020c12  jnz     short loc_180020C17
0x180020c14  mov     byte ptr [rdx], 2Fh ; '/'
0x180020c17  inc     rdx
0x180020c1a  mov     al, [rdx]
0x180020c1c  test    al, al
0x180020c1e  jnz     short loc_180020C10
0x180020c20  xor     r9d, r9d
0x180020c23  mov     r8d, esi
0x180020c26  mov     rdx, r14
0x180020c29  lea     rcx, [rbp+4B0h+var_350]
0x180020c30  call    openDatabase
0x180020c35  mov     ebx, eax
0x180020c37  test    eax, eax
0x180020c39  jz      short loc_180020C7B
0x180020c3b  mov     rcx, [r14]
0x180020c3e  call    sqlite3_errmsg
0x180020c43  mov     qword ptr [rsp+5B0h+dwFlagsAndAttributes], rax
0x180020c48  mov     [rsp+5B0h+dwCreationDisposition], ebx
0x180020c4c  lea     r9, aSqlite3OpenV2F; "sqlite3_open_v2 failed: [%d] %hs"
0x180020c53  mov     r8d, 217h
0x180020c59  lea     rdx, aWindowsCompatI_39; "Windows::Compat::Inventory::SqliteInvCa"...
0x180020c60  mov     ecx, 1
0x180020c65  call    AslLogCallPrintf
0x180020c6a  test    ebx, ebx
0x180020c6c  jg      short loc_180020C72
0x180020c6e  mov     edi, ebx
0x180020c70  jmp     short loc_180020C7B
0x180020c72  movzx   edi, bx
0x180020c75  or      edi, 80070000h
0x180020c7b  mov     eax, edi
0x180020c7d  mov     rcx, [rbp+4B0h+var_30]
0x180020c84  xor     rcx, rsp; StackCookie
0x180020c87  call    __security_check_cookie
0x180020c8c  lea     r11, [rsp+5B0h+var_20]
0x180020c94  mov     rbx, [r11+40h]
0x180020c98  mov     rsi, [r11+48h]
0x180020c9c  mov     rsp, r11
0x180020c9f  pop     r15
0x180020ca1  pop     r14
0x180020ca3  pop     r12
0x180020ca5  pop     rdi
0x180020ca6  pop     rbp
0x180020ca7  retn
```
