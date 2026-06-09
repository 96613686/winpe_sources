# Windows::Compat::Inventory::SqliteInvCache::OpenDb(ushort const *,sqlite3 * &,int)

- ea: `0x1801081b4`
- end: `0x180108577`
- name: `?OpenDb@SqliteInvCache@Inventory@Compat@Windows@@SAJPEBGAEAPEAUsqlite3@@H@Z`
- size: `963`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct sqlite3 **, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180106f1c`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x180011c5c`
- `0x180011d94`
- `0x18001a2f4`
- `0x18008b0f0`
- `0x1800fca34`
- `0x1801081b4`
- `0x18013f92c`
- `0x18018dfd0`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18010827b`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18010827b`
- `KERNEL32!GetFileAttributesW` at `0x18010838f`
- `KERNEL32!GetFileAttributesW` at `0x18010838f`
- `KERNEL32!CreateFileW` at `0x180108419`
- `KERNEL32!CreateFileW` at `0x180108419`
- `KERNEL32!CloseHandle` at `0x180108433`
- `KERNEL32!CloseHandle` at `0x180108492`
- `KERNEL32!CloseHandle` at `0x180108433`
- `KERNEL32!CloseHandle` at `0x180108492`
- `KERNEL32!GetLastError` at `0x1801082b3`
- `KERNEL32!GetLastError` at `0x18010839a`
- `KERNEL32!GetLastError` at `0x18010843e`
- `KERNEL32!GetLastError` at `0x1801082b3`
- `KERNEL32!GetLastError` at `0x18010839a`
- `KERNEL32!GetLastError` at `0x18010843e`

## string_xrefs

- `0x18010822d`: `Amcache`
- `0x18010828a`: `\AppCompat\Programs\`
- `0x1801082bf`: `GetSystemWindowsDirectory [%d]`
- `0x180108456`: `CreateFileW failed for %ls: [%d]`
- `0x180108255`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x1801082cc`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x180108463`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x1801084b8`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x180108528`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x18010851b`: `sqlite3_open_v2 failed: [%d] %hs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::OpenDb(
        const unsigned __int16 *a1,
        struct sqlite3 **a2,
        int a3)
{
  unsigned int v5; // edx
  int PersistedLocation; // eax
  DWORD LastError; // edi
  const char *v8; // r9
  __int64 v9; // r8
  unsigned int v10; // esi
  DWORD v11; // eax
  char *FileW; // rbx
  char v13; // al
  char *v14; // rdx
  int v15; // ebx
  const char *v16; // rax
  DWORD dwCreationDisposition[2]; // [rsp+28h] [rbp-E0h]
  WCHAR Buffer[264]; // [rsp+58h] [rbp-B0h] BYREF
  char v20[272]; // [rsp+268h] [rbp+160h] BYREF
  WCHAR FileName[264]; // [rsp+378h] [rbp+270h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(v20, 0, 0x104u);
  PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(
                        Buffer,
                        v5,
                        L"Amcache",
                        (const unsigned __int16 *const)&szValueBuf,
                        0);
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v8 = "Failed to get persisted reg key location: 0x%x";
    v9 = 434;
LABEL_3:
    dwCreationDisposition[0] = PersistedLocation;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::OpenDb", v9, v8, *(_QWORD *)dwCreationDisposition);
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
    PersistedLocation = StringCchCatW(Buffer, 0x104u, L"\\AppCompat\\Programs\\");
    LastError = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v8 = "StringCchCatW failed [%#x]";
      v9 = 453;
      goto LABEL_3;
    }
  }
  PersistedLocation = StringCchCatW(Buffer, 0x104u, L"Mare");
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v8 = "StringCchCatW failed [%#x]";
    v9 = 461;
    goto LABEL_3;
  }
  PersistedLocation = StringCchCatW(Buffer, 0x104u, L".db");
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v8 = "StringCchCatW failed [%#x]";
    v9 = 468;
    goto LABEL_3;
  }
  if ( a3 )
  {
    v10 = 16908486;
    goto LABEL_17;
  }
  v10 = 16777286;
  if ( GetFileAttributesW(Buffer) == -1 )
  {
    v11 = GetLastError();
    LastError = v11;
    if ( v11 == 2 )
    {
      memset_0(FileName, 0, 0x208u);
      PersistedLocation = StringCchPrintfW(FileName, 0x104u, L"%ls.tmp", Buffer);
      LastError = PersistedLocation;
      if ( PersistedLocation < 0 )
      {
        v8 = "StringCchPrintfW failed [%#x]";
        v9 = 494;
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
      v11);
LABEL_9:
    if ( (int)LastError <= 0 )
      return LastError;
    LastError = (unsigned __int16)LastError;
LABEL_39:
    LastError |= 0x80070000;
    return LastError;
  }
LABEL_17:
  PersistedLocation = StringCchPrintfA(v20, 0x104u, "file:/%ls", Buffer);
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v8 = "StringCchPrintfA failed [%#x]";
    v9 = 519;
    goto LABEL_3;
  }
  v13 = v20[0];
  if ( v20[0] )
  {
    v14 = v20;
    do
    {
      if ( v13 == 92 )
        *v14 = 47;
      v13 = *++v14;
    }
    while ( *v14 );
  }
  v15 = openDatabase(v20, a2, v10, 0);
  if ( v15 )
  {
    v16 = (const char *)sqlite3_errmsg(*a2);
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::OpenDb",
      535,
      "sqlite3_open_v2 failed: [%d] %hs",
      v15,
      v16);
    if ( v15 <= 0 )
      return (DWORD)v15;
    LastError = (unsigned __int16)v15;
    goto LABEL_39;
  }
  return LastError;
}

```

## disassembly

```asm
0x1801081b4  mov     rax, rsp
0x1801081b7  push    rbp
0x1801081b8  push    rdi
0x1801081b9  push    r12
0x1801081bb  push    r14
0x1801081bd  push    r15
0x1801081bf  lea     rbp, [rax-4B8h]
0x1801081c6  sub     rsp, 590h
0x1801081cd  mov     [rsp+5B0h+var_570], 0FFFFFFFFFFFFFFFEh
0x1801081d6  mov     [rax+8], rbx
0x1801081da  mov     [rax+18h], rsi
0x1801081de  mov     rax, cs:__security_cookie
0x1801081e5  xor     rax, rsp
0x1801081e8  mov     [rbp+4B0h+var_30], rax
0x1801081ef  mov     ebx, r8d
0x1801081f2  mov     r14, rdx
0x1801081f5  xor     edx, edx; Val
0x1801081f7  mov     r8d, 208h; Size
0x1801081fd  lea     rcx, [rsp+5B0h+Buffer]; void *
0x180108202  call    memset_0
0x180108207  mov     r12d, 104h
0x18010820d  mov     r8d, r12d; Size
0x180108210  xor     edx, edx; Val
0x180108212  lea     rcx, [rbp+4B0h+var_350]; void *
0x180108219  call    memset_0
0x18010821e  xor     r15d, r15d
0x180108221  mov     [rsp+5B0h+dwCreationDisposition], r15d; int
0x180108226  lea     r9, szValueBuf; unsigned __int16 *
0x18010822d  lea     r8, aAmcache; "Amcache"
0x180108234  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180108239  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x18010823e  mov     edi, eax
0x180108240  test    eax, eax
0x180108242  jns     short loc_18010826B
0x180108244  lea     r9, aFailedToGetPer_0; "Failed to get persisted reg key locatio"...
0x18010824b  mov     r8d, 1B2h
0x180108251  mov     [rsp+5B0h+dwCreationDisposition], eax
0x180108255  lea     rdx, aWindowsCompatI_24; "Windows::Compat::Inventory::SqliteInvCa"...
0x18010825c  mov     ecx, 1
0x180108261  call    AslLogCallPrintf
0x180108266  jmp     loc_18010854A
0x18010826b  cmp     [rsp+5B0h+Buffer], r15w
0x180108271  jnz     short loc_1801082ED
0x180108273  mov     edx, r12d; uSize
0x180108276  lea     rcx, [rsp+5B0h+Buffer]; lpBuffer
0x18010827b  call    cs:__imp_GetSystemWindowsDirectoryW
0x180108281  dec     eax
0x180108283  cmp     eax, 103h
0x180108288  ja      short loc_1801082B3
0x18010828a  lea     r8, aAppcompatProgr_0; "\\AppCompat\\Programs\\"
0x180108291  mov     rdx, r12; unsigned __int64
0x180108294  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180108299  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18010829e  mov     edi, eax
0x1801082a0  test    eax, eax
0x1801082a2  jns     short loc_1801082ED
0x1801082a4  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x1801082ab  mov     r8d, 1C5h
0x1801082b1  jmp     short loc_180108251
0x1801082b3  call    cs:__imp_GetLastError
0x1801082b9  mov     edi, eax
0x1801082bb  mov     [rsp+5B0h+dwCreationDisposition], eax
0x1801082bf  lea     r9, aGetsystemwindo; "GetSystemWindowsDirectory [%d]"
0x1801082c6  mov     r8d, 1BDh
0x1801082cc  lea     rdx, aWindowsCompatI_24; "Windows::Compat::Inventory::SqliteInvCa"...
0x1801082d3  mov     ecx, 1
0x1801082d8  call    AslLogCallPrintf
0x1801082dd  test    edi, edi
0x1801082df  jle     loc_18010854A
0x1801082e5  movzx   edi, di
0x1801082e8  jmp     loc_180108544
0x1801082ed  lea     r8, aMare; "Mare"
0x1801082f4  mov     rdx, r12; unsigned __int64
0x1801082f7  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x1801082fc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180108301  mov     edi, eax
0x180108303  test    eax, eax
0x180108305  jns     short loc_180108319
0x180108307  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x18010830e  mov     r8d, 1CDh
0x180108314  jmp     loc_180108251
0x180108319  lea     r8, aDb; ".db"
0x180108320  mov     rdx, r12; unsigned __int64
0x180108323  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180108328  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18010832d  mov     edi, eax
0x18010832f  test    eax, eax
0x180108331  jns     short loc_180108345
0x180108333  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x18010833a  mov     r8d, 1D4h
0x180108340  jmp     loc_180108251
0x180108345  test    ebx, ebx
0x180108347  jz      short loc_180108385
0x180108349  mov     esi, 10200C6h
0x18010834e  lea     r9, [rsp+5B0h+Buffer]
0x180108353  lea     r8, aFileLs; "file:/%ls"
0x18010835a  mov     rdx, r12; unsigned __int64
0x18010835d  lea     rcx, [rbp+4B0h+var_350]; char *
0x180108364  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180108369  mov     edi, eax
0x18010836b  test    eax, eax
0x18010836d  jns     loc_1801084CE
0x180108373  lea     r9, aStringcchprint; "StringCchPrintfA failed [%#x]"
0x18010837a  mov     r8d, 207h
0x180108380  jmp     loc_180108251
0x180108385  mov     esi, 1000046h
0x18010838a  lea     rcx, [rsp+5B0h+Buffer]; lpFileName
0x18010838f  call    cs:__imp_GetFileAttributesW
0x180108395  cmp     eax, 0FFFFFFFFh
0x180108398  jnz     short loc_18010834E
0x18010839a  call    cs:__imp_GetLastError
0x1801083a0  mov     edi, eax
0x1801083a2  cmp     eax, 2
0x1801083a5  jnz     loc_18010849D
0x1801083ab  xor     edx, edx; Val
0x1801083ad  mov     r8d, 208h; Size
0x1801083b3  lea     rcx, [rbp+4B0h+FileName]; void *
0x1801083ba  call    memset_0
0x1801083bf  lea     r9, [rsp+5B0h+Buffer]
0x1801083c4  lea     r8, aLsTmp; "%ls.tmp"
0x1801083cb  mov     rdx, r12; unsigned __int64
0x1801083ce  lea     rcx, [rbp+4B0h+FileName]; unsigned __int16 *
0x1801083d5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801083da  mov     edi, eax
0x1801083dc  test    eax, eax
0x1801083de  jns     short loc_1801083F2
0x1801083e0  lea     r9, aStringcchprint_4; "StringCchPrintfW failed [%#x]"
0x1801083e7  mov     r8d, 1EEh
0x1801083ed  jmp     loc_180108251
0x1801083f2  mov     [rsp+5B0h+hTemplateFile], r15; hTemplateFile
0x1801083f7  mov     [rsp+5B0h+dwFlagsAndAttributes], 4000080h; dwFlagsAndAttributes
0x1801083ff  mov     [rsp+5B0h+dwCreationDisposition], 1; dwCreationDisposition
0x180108407  xor     r9d, r9d; lpSecurityAttributes
0x18010840a  xor     r8d, r8d; dwShareMode
0x18010840d  mov     edx, 40000000h; dwDesiredAccess
0x180108412  lea     rcx, [rbp+4B0h+FileName]; lpFileName
0x180108419  call    cs:__imp_CreateFileW
0x18010841f  mov     rbx, rax
0x180108422  mov     qword ptr [rsp+5B0h+var_568], rax
0x180108427  dec     rax
0x18010842a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010842e  ja      short loc_18010843E
0x180108430  mov     rcx, rbx; hObject
0x180108433  call    cs:__imp_CloseHandle
0x180108439  jmp     loc_18010834E
0x18010843e  call    cs:__imp_GetLastError
0x180108444  mov     edi, eax
0x180108446  mov     [rsp+5B0h+dwFlagsAndAttributes], eax
0x18010844a  lea     rax, [rbp+4B0h+FileName]
0x180108451  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rax
0x180108456  lea     r9, aCreatefilewFai; "CreateFileW failed for %ls: [%d]"
0x18010845d  mov     r8d, 1F6h
0x180108463  lea     rdx, aWindowsCompatI_24; "Windows::Compat::Inventory::SqliteInvCa"...
0x18010846a  mov     ecx, 1
0x18010846f  call    AslLogCallPrintf
0x180108474  test    edi, edi
0x180108476  jle     short loc_180108481
0x180108478  movzx   edi, di
0x18010847b  or      edi, 80070000h
0x180108481  lea     rax, [rbx-1]
0x180108485  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180108489  ja      loc_18010854A
0x18010848f  mov     rcx, rbx; hObject
0x180108492  call    cs:__imp_CloseHandle
0x180108498  jmp     loc_18010854A
0x18010849d  mov     [rsp+5B0h+dwFlagsAndAttributes], edi
0x1801084a1  lea     rax, [rsp+5B0h+Buffer]
0x1801084a6  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rax
0x1801084ab  lea     r9, aGetfileattribu_0; "GetFileAttributesW failed for %ls: [%d]"
0x1801084b2  mov     r8d, 1FDh
0x1801084b8  lea     rdx, aWindowsCompatI_24; "Windows::Compat::Inventory::SqliteInvCa"...
0x1801084bf  mov     ecx, 1
0x1801084c4  call    AslLogCallPrintf
0x1801084c9  jmp     loc_1801082DD
0x1801084ce  mov     al, [rbp+4B0h+var_350]
0x1801084d4  test    al, al
0x1801084d6  jz      short loc_1801084EF
0x1801084d8  lea     rdx, [rbp+4B0h+var_350]
0x1801084df  cmp     al, 5Ch ; '\'
0x1801084e1  jnz     short loc_1801084E6
0x1801084e3  mov     byte ptr [rdx], 2Fh ; '/'
0x1801084e6  inc     rdx
0x1801084e9  mov     al, [rdx]
0x1801084eb  test    al, al
0x1801084ed  jnz     short loc_1801084DF
0x1801084ef  xor     r9d, r9d
0x1801084f2  mov     r8d, esi
0x1801084f5  mov     rdx, r14
0x1801084f8  lea     rcx, [rbp+4B0h+var_350]
0x1801084ff  call    openDatabase
0x180108504  mov     ebx, eax
0x180108506  test    eax, eax
0x180108508  jz      short loc_18010854A
0x18010850a  mov     rcx, [r14]
0x18010850d  call    sqlite3_errmsg
0x180108512  mov     qword ptr [rsp+5B0h+dwFlagsAndAttributes], rax
0x180108517  mov     [rsp+5B0h+dwCreationDisposition], ebx
0x18010851b  lea     r9, aSqlite3OpenV2F; "sqlite3_open_v2 failed: [%d] %hs"
0x180108522  mov     r8d, 217h
0x180108528  lea     rdx, aWindowsCompatI_24; "Windows::Compat::Inventory::SqliteInvCa"...
0x18010852f  mov     ecx, 1
0x180108534  call    AslLogCallPrintf
0x180108539  test    ebx, ebx
0x18010853b  jg      short loc_180108541
0x18010853d  mov     edi, ebx
0x18010853f  jmp     short loc_18010854A
0x180108541  movzx   edi, bx
0x180108544  or      edi, 80070000h
0x18010854a  mov     eax, edi
0x18010854c  mov     rcx, [rbp+4B0h+var_30]
0x180108553  xor     rcx, rsp; StackCookie
0x180108556  call    __security_check_cookie
0x18010855b  lea     r11, [rsp+5B0h+var_20]
0x180108563  mov     rbx, [r11+30h]
0x180108567  mov     rsi, [r11+40h]
0x18010856b  mov     rsp, r11
0x18010856e  pop     r15
0x180108570  pop     r14
0x180108572  pop     r12
0x180108574  pop     rdi
0x180108575  pop     rbp
0x180108576  retn
```
