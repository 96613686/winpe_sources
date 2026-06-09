# Windows::Compat::Inventory::SqliteInvCache::OpenDb(ushort const *,sqlite3 * &,int)

- ea: `0x180016ff8`
- end: `0x1800173a2`
- name: `?OpenDb@SqliteInvCache@Inventory@Compat@Windows@@SAJPEBGAEAPEAUsqlite3@@H@Z`
- size: `938`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct sqlite3 **, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800159ec`

## callees

- `0x180005890`
- `0x180006938`
- `0x18000ca3c`
- `0x18000cb74`
- `0x18001036c`
- `0x180014e44`
- `0x180016ff8`
- `0x18001b3b4`
- `0x1800295dc`
- `0x18005ae0c`
- `0x1800a5e60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800170f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800170f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017276`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800170b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800170b9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800171c9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800171c9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017253`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017253`

## string_xrefs

- `0x18001706b`: `Amcache`
- `0x1800170fd`: `GetSystemWindowsDirectory [%d]`
- `0x1800170c8`: `\AppCompat\Programs\`
- `0x18001728e`: `CreateFileW failed for %ls: [%d]`
- `0x180017346`: `sqlite3_open_v2 failed: [%d] %hs`
- `0x180017093`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x18001710a`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x18001729b`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x1800172e3`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x180017353`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::OpenDb(
        const unsigned __int16 *a1,
        struct sqlite3 **a2,
        int a3)
{
  unsigned int v6; // edx
  int PersistedLocation; // eax
  DWORD LastError; // ebx
  const char *v9; // r9
  __int64 v10; // r8
  unsigned int v11; // edi
  DWORD v12; // eax
  char v13; // al
  char *v14; // rdx
  int v15; // edi
  const char *v16; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  _QWORD v19[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  char v21[272]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR FileName[264]; // [rsp+370h] [rbp+270h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(v21, 0, 0x104u);
  PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(Buffer, v6, L"Amcache", &pszFormat, 0);
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v9 = "Failed to get persisted reg key location: 0x%x";
    v10 = 434;
LABEL_3:
    dwCreationDisposition[0] = PersistedLocation;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::OpenDb", v10, v9, *(_QWORD *)dwCreationDisposition);
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
      v19[0] = CreateFileW(FileName, 0x40000000u, 0, 0, 1u, 0x4000080u, 0);
      if ( (unsigned __int64)(v19[0] - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
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
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v19);
        return LastError;
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v19);
      goto LABEL_17;
    }
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::OpenDb",
      509,
      "GetFileAttributesW failed for %ls: [%d]",
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
  PersistedLocation = StringCchPrintfA(v21, 0x104u, "file:/%ls", Buffer);
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v9 = "StringCchPrintfA failed [%#x]";
    v10 = 519;
    goto LABEL_3;
  }
  v13 = v21[0];
  if ( v21[0] )
  {
    v14 = v21;
    do
    {
      if ( v13 == 92 )
        *v14 = 47;
      v13 = *++v14;
    }
    while ( *v14 );
  }
  v15 = openDatabase(v21, a2, v11, 0);
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
    goto LABEL_38;
  }
  return LastError;
}

```

## disassembly

```asm
0x180016ff8  mov     [rsp-8+arg_10], rbx
0x180016ffd  mov     [rsp-8+arg_18], rsi
0x180017002  push    rbp
0x180017003  push    rdi
0x180017004  push    r12
0x180017006  push    r14
0x180017008  push    r15
0x18001700a  lea     rbp, [rsp-490h]
0x180017012  sub     rsp, 590h
0x180017019  mov     rax, cs:__security_cookie
0x180017020  xor     rax, rsp
0x180017023  mov     [rbp+4B0h+var_30], rax
0x18001702a  mov     edi, r8d
0x18001702d  mov     r14, rdx
0x180017030  mov     rsi, rcx
0x180017033  xor     edx, edx; Val
0x180017035  mov     r8d, 208h; Size
0x18001703b  lea     rcx, [rsp+5B0h+Buffer]; void *
0x180017040  call    memset_0
0x180017045  mov     r12d, 104h
0x18001704b  mov     r8d, r12d; Size
0x18001704e  xor     edx, edx; Val
0x180017050  lea     rcx, [rbp+4B0h+var_350]; void *
0x180017057  call    memset_0
0x18001705c  xor     r15d, r15d
0x18001705f  mov     [rsp+5B0h+dwCreationDisposition], r15d; int
0x180017064  lea     r9, pszFormat; unsigned __int16 *
0x18001706b  lea     r8, aAmcache; "Amcache"
0x180017072  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180017077  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x18001707c  mov     ebx, eax
0x18001707e  test    eax, eax
0x180017080  jns     short loc_1800170A9
0x180017082  lea     r9, aFailedToGetPer; "Failed to get persisted reg key locatio"...
0x180017089  mov     r8d, 1B2h
0x18001708f  mov     [rsp+5B0h+dwCreationDisposition], eax
0x180017093  lea     rdx, aWindowsCompatI_25; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001709a  mov     ecx, 1
0x18001709f  call    AslLogCallPrintf
0x1800170a4  jmp     loc_180017375
0x1800170a9  cmp     [rsp+5B0h+Buffer], r15w
0x1800170af  jnz     short loc_18001712B
0x1800170b1  mov     edx, r12d; uSize
0x1800170b4  lea     rcx, [rsp+5B0h+Buffer]; lpBuffer
0x1800170b9  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800170bf  dec     eax
0x1800170c1  cmp     eax, 103h
0x1800170c6  ja      short loc_1800170F1
0x1800170c8  lea     r8, aAppcompatProgr_0; "\\AppCompat\\Programs\\"
0x1800170cf  mov     rdx, r12; unsigned __int64
0x1800170d2  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x1800170d7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800170dc  mov     ebx, eax
0x1800170de  test    eax, eax
0x1800170e0  jns     short loc_18001712B
0x1800170e2  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x1800170e9  mov     r8d, 1C5h
0x1800170ef  jmp     short loc_18001708F
0x1800170f1  call    cs:__imp_GetLastError
0x1800170f7  mov     ebx, eax
0x1800170f9  mov     [rsp+5B0h+dwCreationDisposition], eax
0x1800170fd  lea     r9, aGetsystemwindo; "GetSystemWindowsDirectory [%d]"
0x180017104  mov     r8d, 1BDh
0x18001710a  lea     rdx, aWindowsCompatI_25; "Windows::Compat::Inventory::SqliteInvCa"...
0x180017111  mov     ecx, 1
0x180017116  call    AslLogCallPrintf
0x18001711b  test    ebx, ebx
0x18001711d  jle     loc_180017375
0x180017123  movzx   ebx, bx
0x180017126  jmp     loc_18001736F
0x18001712b  mov     r8, rsi; unsigned __int16 *
0x18001712e  mov     rdx, r12; unsigned __int64
0x180017131  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180017136  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001713b  mov     ebx, eax
0x18001713d  test    eax, eax
0x18001713f  jns     short loc_180017153
0x180017141  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x180017148  mov     r8d, 1CDh
0x18001714e  jmp     loc_18001708F
0x180017153  lea     r8, aDb; ".db"
0x18001715a  mov     rdx, r12; unsigned __int64
0x18001715d  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180017162  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017167  mov     ebx, eax
0x180017169  test    eax, eax
0x18001716b  jns     short loc_18001717F
0x18001716d  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x180017174  mov     r8d, 1D4h
0x18001717a  jmp     loc_18001708F
0x18001717f  test    edi, edi
0x180017181  jz      short loc_1800171BF
0x180017183  mov     edi, 10200C6h
0x180017188  lea     r9, [rsp+5B0h+Buffer]
0x18001718d  lea     r8, aFileLs; "file:/%ls"
0x180017194  mov     rdx, r12; unsigned __int64
0x180017197  lea     rcx, [rbp+4B0h+var_350]; char *
0x18001719e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800171a3  mov     ebx, eax
0x1800171a5  test    eax, eax
0x1800171a7  jns     loc_1800172F9
0x1800171ad  lea     r9, aStringcchprint; "StringCchPrintfA failed [%#x]"
0x1800171b4  mov     r8d, 207h
0x1800171ba  jmp     loc_18001708F
0x1800171bf  mov     edi, 1000046h
0x1800171c4  lea     rcx, [rsp+5B0h+Buffer]; lpFileName
0x1800171c9  call    cs:__imp_GetFileAttributesW
0x1800171cf  cmp     eax, 0FFFFFFFFh
0x1800171d2  jnz     short loc_180017188
0x1800171d4  call    cs:__imp_GetLastError
0x1800171da  mov     ebx, eax
0x1800171dc  cmp     eax, 2
0x1800171df  jnz     loc_1800172C8
0x1800171e5  xor     edx, edx; Val
0x1800171e7  mov     r8d, 208h; Size
0x1800171ed  lea     rcx, [rbp+4B0h+FileName]; void *
0x1800171f4  call    memset_0
0x1800171f9  lea     r9, [rsp+5B0h+Buffer]
0x1800171fe  lea     r8, aLsTmp; "%ls.tmp"
0x180017205  mov     rdx, r12; unsigned __int64
0x180017208  lea     rcx, [rbp+4B0h+FileName]; unsigned __int16 *
0x18001720f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017214  mov     ebx, eax
0x180017216  test    eax, eax
0x180017218  jns     short loc_18001722C
0x18001721a  lea     r9, aStringcchprint_5; "StringCchPrintfW failed [%#x]"
0x180017221  mov     r8d, 1EEh
0x180017227  jmp     loc_18001708F
0x18001722c  mov     [rsp+5B0h+hTemplateFile], r15; hTemplateFile
0x180017231  mov     [rsp+5B0h+dwFlagsAndAttributes], 4000080h; dwFlagsAndAttributes
0x180017239  mov     [rsp+5B0h+dwCreationDisposition], 1; dwCreationDisposition
0x180017241  xor     r9d, r9d; lpSecurityAttributes
0x180017244  xor     r8d, r8d; dwShareMode
0x180017247  mov     edx, 40000000h; dwDesiredAccess
0x18001724c  lea     rcx, [rbp+4B0h+FileName]; lpFileName
0x180017253  call    cs:__imp_CreateFileW
0x180017259  mov     [rsp+5B0h+var_570], rax
0x18001725e  dec     rax
0x180017261  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017265  ja      short loc_180017276
0x180017267  lea     rcx, [rsp+5B0h+var_570]
0x18001726c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017271  jmp     loc_180017188
0x180017276  call    cs:__imp_GetLastError
0x18001727c  mov     ebx, eax
0x18001727e  mov     [rsp+5B0h+dwFlagsAndAttributes], eax
0x180017282  lea     rax, [rbp+4B0h+FileName]
0x180017289  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rax
0x18001728e  lea     r9, aCreatefilewFai; "CreateFileW failed for %ls: [%d]"
0x180017295  mov     r8d, 1F6h
0x18001729b  lea     rdx, aWindowsCompatI_25; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800172a2  mov     ecx, 1
0x1800172a7  call    AslLogCallPrintf
0x1800172ac  test    ebx, ebx
0x1800172ae  jle     short loc_1800172B9
0x1800172b0  movzx   ebx, bx
0x1800172b3  or      ebx, 80070000h
0x1800172b9  lea     rcx, [rsp+5B0h+var_570]
0x1800172be  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800172c3  jmp     loc_180017375
0x1800172c8  mov     [rsp+5B0h+dwFlagsAndAttributes], ebx
0x1800172cc  lea     rax, [rsp+5B0h+Buffer]
0x1800172d1  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rax
0x1800172d6  lea     r9, aGetfileattribu_0; "GetFileAttributesW failed for %ls: [%d]"
0x1800172dd  mov     r8d, 1FDh
0x1800172e3  lea     rdx, aWindowsCompatI_25; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800172ea  mov     ecx, 1
0x1800172ef  call    AslLogCallPrintf
0x1800172f4  jmp     loc_18001711B
0x1800172f9  mov     al, [rbp+4B0h+var_350]
0x1800172ff  test    al, al
0x180017301  jz      short loc_18001731A
0x180017303  lea     rdx, [rbp+4B0h+var_350]
0x18001730a  cmp     al, 5Ch ; '\'
0x18001730c  jnz     short loc_180017311
0x18001730e  mov     byte ptr [rdx], 2Fh ; '/'
0x180017311  inc     rdx
0x180017314  mov     al, [rdx]
0x180017316  test    al, al
0x180017318  jnz     short loc_18001730A
0x18001731a  xor     r9d, r9d
0x18001731d  mov     r8d, edi
0x180017320  mov     rdx, r14
0x180017323  lea     rcx, [rbp+4B0h+var_350]
0x18001732a  call    openDatabase
0x18001732f  mov     edi, eax
0x180017331  test    eax, eax
0x180017333  jz      short loc_180017375
0x180017335  mov     rcx, [r14]
0x180017338  call    sqlite3_errmsg
0x18001733d  mov     qword ptr [rsp+5B0h+dwFlagsAndAttributes], rax
0x180017342  mov     [rsp+5B0h+dwCreationDisposition], edi
0x180017346  lea     r9, aSqlite3OpenV2F; "sqlite3_open_v2 failed: [%d] %hs"
0x18001734d  mov     r8d, 217h
0x180017353  lea     rdx, aWindowsCompatI_25; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001735a  mov     ecx, 1
0x18001735f  call    AslLogCallPrintf
0x180017364  test    edi, edi
0x180017366  jg      short loc_18001736C
0x180017368  mov     ebx, edi
0x18001736a  jmp     short loc_180017375
0x18001736c  movzx   ebx, di
0x18001736f  or      ebx, 80070000h
0x180017375  mov     eax, ebx
0x180017377  mov     rcx, [rbp+4B0h+var_30]
0x18001737e  xor     rcx, rsp; StackCookie
0x180017381  call    __security_check_cookie
0x180017386  lea     r11, [rsp+5B0h+var_20]
0x18001738e  mov     rbx, [r11+40h]
0x180017392  mov     rsi, [r11+48h]
0x180017396  mov     rsp, r11
0x180017399  pop     r15
0x18001739b  pop     r14
0x18001739d  pop     r12
0x18001739f  pop     rdi
0x1800173a0  pop     rbp
0x1800173a1  retn
```
