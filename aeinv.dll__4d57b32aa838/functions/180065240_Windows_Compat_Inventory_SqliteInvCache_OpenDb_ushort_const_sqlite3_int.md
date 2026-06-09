# Windows::Compat::Inventory::SqliteInvCache::OpenDb(ushort const *,sqlite3 * &,int)

- ea: `0x180065240`
- end: `0x1800655ea`
- name: `?OpenDb@SqliteInvCache@Inventory@Compat@Windows@@SAJPEBGAEAPEAUsqlite3@@H@Z`
- size: `938`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct sqlite3 **, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800643a4`

## callees

- `0x180015eec`
- `0x1800197d4`
- `0x18002c9d4`
- `0x18002f4b4`
- `0x18004f970`
- `0x180057460`
- `0x180059920`
- `0x18005a8bc`
- `0x180065240`
- `0x180066a50`
- `0x18009038c`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18006530a`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18006530a`
- `KERNEL32!CreateFileW` at `0x18006549b`
- `KERNEL32!CreateFileW` at `0x18006549b`
- `KERNEL32!GetFileAttributesW` at `0x180065411`
- `KERNEL32!GetFileAttributesW` at `0x180065411`
- `KERNEL32!GetLastError` at `0x18006533f`
- `KERNEL32!GetLastError` at `0x18006541c`
- `KERNEL32!GetLastError` at `0x1800654be`
- `KERNEL32!GetLastError` at `0x18006533f`
- `KERNEL32!GetLastError` at `0x18006541c`
- `KERNEL32!GetLastError` at `0x1800654be`

## string_xrefs

- `0x1800652bc`: `Amcache`
- `0x18006534b`: `GetSystemWindowsDirectory [%d]`
- `0x180065319`: `\AppCompat\Programs\`
- `0x1800654d6`: `CreateFileW failed for %ls: [%d]`
- `0x18006558e`: `sqlite3_open_v2 failed: [%d] %hs`
- `0x1800652e4`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x180065358`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x1800654e3`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x18006552b`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x18006559b`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::OpenDb(
        const unsigned __int16 *a1,
        struct sqlite3 **a2,
        int a3)
{
  __int64 v6; // rdx
  unsigned __int64 v7; // rdx
  int PersistedLocation; // ebx
  const char *v9; // r9
  int v10; // r8d
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rdx
  unsigned int v13; // edi
  char v14; // al
  char *v15; // rdx
  int v16; // edi
  _QWORD v18[2]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+58h] [rbp-B0h] BYREF
  char v20[272]; // [rsp+268h] [rbp+160h] BYREF
  WCHAR FileName[264]; // [rsp+378h] [rbp+270h] BYREF

  v18[1] = -2;
  memset_0(Buffer, 0, 0x208u);
  memset_0(v20, 0, 0x104u);
  PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(
                        Buffer,
                        v6,
                        L"Amcache",
                        &byte_1801389F0,
                        0);
  if ( PersistedLocation < 0 )
  {
    v9 = "Failed to get persisted reg key location: 0x%x";
    v10 = 434;
LABEL_3:
    AslLogCallPrintf(1, (unsigned int)"Windows::Compat::Inventory::SqliteInvCache::OpenDb", v10, (_DWORD)v9);
    return (unsigned int)PersistedLocation;
  }
  if ( !Buffer[0] )
  {
    if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) - 1 > 0x103 )
    {
      PersistedLocation = GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"Windows::Compat::Inventory::SqliteInvCache::OpenDb",
        445,
        (unsigned int)"GetSystemWindowsDirectory [%d]");
      goto LABEL_9;
    }
    PersistedLocation = StringCchCatW(Buffer, v11, L"\\AppCompat\\Programs\\");
    if ( PersistedLocation < 0 )
    {
      v9 = "StringCchCatW failed [%#x]";
      v10 = 453;
      goto LABEL_3;
    }
  }
  PersistedLocation = StringCchCatW(Buffer, v7, a1);
  if ( PersistedLocation < 0 )
  {
    v9 = "StringCchCatW failed [%#x]";
    v10 = 461;
    goto LABEL_3;
  }
  PersistedLocation = StringCchCatW(Buffer, v12, L".db");
  if ( PersistedLocation < 0 )
  {
    v9 = "StringCchCatW failed [%#x]";
    v10 = 468;
    goto LABEL_3;
  }
  if ( a3 )
  {
    v13 = 16908486;
    goto LABEL_17;
  }
  v13 = 16777286;
  if ( GetFileAttributesW(Buffer) == -1 )
  {
    PersistedLocation = GetLastError();
    if ( PersistedLocation == 2 )
    {
      memset_0(FileName, 0, 0x208u);
      PersistedLocation = StringCchPrintfW(FileName, 0x104u, L"%ls.tmp", Buffer);
      if ( PersistedLocation < 0 )
      {
        v9 = "StringCchPrintfW failed [%#x]";
        v10 = 494;
        goto LABEL_3;
      }
      v18[0] = CreateFileW(FileName, 0x40000000u, 0, 0, 1u, 0x4000080u, 0);
      if ( (unsigned __int64)(v18[0] - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        PersistedLocation = GetLastError();
        AslLogCallPrintf(
          1,
          (unsigned int)"Windows::Compat::Inventory::SqliteInvCache::OpenDb",
          502,
          (unsigned int)"CreateFileW failed for %ls: [%d]");
        if ( PersistedLocation > 0 )
          PersistedLocation = (unsigned __int16)PersistedLocation | 0x80070000;
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v18);
        return (unsigned int)PersistedLocation;
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v18);
      goto LABEL_17;
    }
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Inventory::SqliteInvCache::OpenDb",
      509,
      (unsigned int)"GetFileAttributesW failed for %ls: [%d]");
LABEL_9:
    if ( PersistedLocation <= 0 )
      return (unsigned int)PersistedLocation;
    PersistedLocation = (unsigned __int16)PersistedLocation;
LABEL_38:
    PersistedLocation |= 0x80070000;
    return (unsigned int)PersistedLocation;
  }
LABEL_17:
  PersistedLocation = StringCchPrintfA(v20, 0x104u, "file:/%ls", Buffer);
  if ( PersistedLocation < 0 )
  {
    v9 = "StringCchPrintfA failed [%#x]";
    v10 = 519;
    goto LABEL_3;
  }
  v14 = v20[0];
  if ( v20[0] )
  {
    v15 = v20;
    do
    {
      if ( v14 == 92 )
        *v15 = 47;
      v14 = *++v15;
    }
    while ( *v15 );
  }
  v16 = openDatabase(v20, a2, v13, 0);
  if ( v16 )
  {
    sqlite3_errmsg(*a2);
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Inventory::SqliteInvCache::OpenDb",
      535,
      (unsigned int)"sqlite3_open_v2 failed: [%d] %hs");
    if ( v16 <= 0 )
      return (unsigned int)v16;
    PersistedLocation = (unsigned __int16)v16;
    goto LABEL_38;
  }
  return (unsigned int)PersistedLocation;
}

```

## disassembly

```asm
0x180065240  mov     rax, rsp
0x180065243  push    rbp
0x180065244  push    rdi
0x180065245  push    r12
0x180065247  push    r14
0x180065249  push    r15
0x18006524b  lea     rbp, [rax-4B8h]
0x180065252  sub     rsp, 590h
0x180065259  mov     qword ptr [rsp+5B0h+var_568], 0FFFFFFFFFFFFFFFEh
0x180065262  mov     [rax+18h], rbx
0x180065266  mov     [rax+20h], rsi
0x18006526a  mov     rax, cs:__security_cookie
0x180065271  xor     rax, rsp
0x180065274  mov     [rbp+4B0h+var_30], rax
0x18006527b  mov     edi, r8d
0x18006527e  mov     r14, rdx
0x180065281  mov     rsi, rcx
0x180065284  xor     edx, edx; Val
0x180065286  mov     r8d, 208h; Size
0x18006528c  lea     rcx, [rsp+5B0h+Buffer]; void *
0x180065291  call    memset_0
0x180065296  mov     r12d, 104h
0x18006529c  mov     r8d, r12d; Size
0x18006529f  xor     edx, edx; Val
0x1800652a1  lea     rcx, [rbp+4B0h+var_350]; void *
0x1800652a8  call    memset_0
0x1800652ad  xor     r15d, r15d
0x1800652b0  mov     [rsp+5B0h+dwCreationDisposition], r15d; int
0x1800652b5  lea     r9, byte_1801389F0; unsigned __int16 *
0x1800652bc  lea     r8, aAmcache; "Amcache"
0x1800652c3  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x1800652c8  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x1800652cd  mov     ebx, eax
0x1800652cf  test    eax, eax
0x1800652d1  jns     short loc_1800652FA
0x1800652d3  lea     r9, aFailedToGetPer; "Failed to get persisted reg key locatio"...
0x1800652da  mov     r8d, 1B2h
0x1800652e0  mov     [rsp+5B0h+dwCreationDisposition], eax
0x1800652e4  lea     rdx, aWindowsCompatI_24; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800652eb  mov     ecx, 1
0x1800652f0  call    AslLogCallPrintf
0x1800652f5  jmp     loc_1800655BD
0x1800652fa  cmp     [rsp+5B0h+Buffer], r15w
0x180065300  jnz     short loc_180065379
0x180065302  mov     edx, r12d; uSize
0x180065305  lea     rcx, [rsp+5B0h+Buffer]; lpBuffer
0x18006530a  call    cs:__imp_GetSystemWindowsDirectoryW
0x180065310  dec     eax
0x180065312  cmp     eax, 103h
0x180065317  ja      short loc_18006533F
0x180065319  lea     r8, aAppcompatProgr_0; "\\AppCompat\\Programs\\"
0x180065320  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180065325  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006532a  mov     ebx, eax
0x18006532c  test    eax, eax
0x18006532e  jns     short loc_180065379
0x180065330  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x180065337  mov     r8d, 1C5h
0x18006533d  jmp     short loc_1800652E0
0x18006533f  call    cs:__imp_GetLastError
0x180065345  mov     ebx, eax
0x180065347  mov     [rsp+5B0h+dwCreationDisposition], eax
0x18006534b  lea     r9, aGetsystemwindo; "GetSystemWindowsDirectory [%d]"
0x180065352  mov     r8d, 1BDh
0x180065358  lea     rdx, aWindowsCompatI_24; "Windows::Compat::Inventory::SqliteInvCa"...
0x18006535f  mov     ecx, 1
0x180065364  call    AslLogCallPrintf
0x180065369  test    ebx, ebx
0x18006536b  jle     loc_1800655BD
0x180065371  movzx   ebx, bx
0x180065374  jmp     loc_1800655B7
0x180065379  mov     r8, rsi; unsigned __int16 *
0x18006537c  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180065381  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180065386  mov     ebx, eax
0x180065388  test    eax, eax
0x18006538a  jns     short loc_18006539E
0x18006538c  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x180065393  mov     r8d, 1CDh
0x180065399  jmp     loc_1800652E0
0x18006539e  lea     r8, aDb; ".db"
0x1800653a5  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x1800653aa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800653af  mov     ebx, eax
0x1800653b1  test    eax, eax
0x1800653b3  jns     short loc_1800653C7
0x1800653b5  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x1800653bc  mov     r8d, 1D4h
0x1800653c2  jmp     loc_1800652E0
0x1800653c7  test    edi, edi
0x1800653c9  jz      short loc_180065407
0x1800653cb  mov     edi, 10200C6h
0x1800653d0  lea     r9, [rsp+5B0h+Buffer]
0x1800653d5  lea     r8, aFileLs; "file:/%ls"
0x1800653dc  mov     rdx, r12; unsigned __int64
0x1800653df  lea     rcx, [rbp+4B0h+var_350]; char *
0x1800653e6  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800653eb  mov     ebx, eax
0x1800653ed  test    eax, eax
0x1800653ef  jns     loc_180065541
0x1800653f5  lea     r9, aStringcchprint; "StringCchPrintfA failed [%#x]"
0x1800653fc  mov     r8d, 207h
0x180065402  jmp     loc_1800652E0
0x180065407  mov     edi, 1000046h
0x18006540c  lea     rcx, [rsp+5B0h+Buffer]; lpFileName
0x180065411  call    cs:__imp_GetFileAttributesW
0x180065417  cmp     eax, 0FFFFFFFFh
0x18006541a  jnz     short loc_1800653D0
0x18006541c  call    cs:__imp_GetLastError
0x180065422  mov     ebx, eax
0x180065424  cmp     eax, 2
0x180065427  jnz     loc_180065510
0x18006542d  xor     edx, edx; Val
0x18006542f  mov     r8d, 208h; Size
0x180065435  lea     rcx, [rbp+4B0h+FileName]; void *
0x18006543c  call    memset_0
0x180065441  lea     r9, [rsp+5B0h+Buffer]
0x180065446  lea     r8, aLsTmp; "%ls.tmp"
0x18006544d  mov     rdx, r12; unsigned __int64
0x180065450  lea     rcx, [rbp+4B0h+FileName]; unsigned __int16 *
0x180065457  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006545c  mov     ebx, eax
0x18006545e  test    eax, eax
0x180065460  jns     short loc_180065474
0x180065462  lea     r9, aStringcchprint_4; "StringCchPrintfW failed [%#x]"
0x180065469  mov     r8d, 1EEh
0x18006546f  jmp     loc_1800652E0
0x180065474  mov     [rsp+5B0h+hTemplateFile], r15; hTemplateFile
0x180065479  mov     [rsp+5B0h+dwFlagsAndAttributes], 4000080h; dwFlagsAndAttributes
0x180065481  mov     [rsp+5B0h+dwCreationDisposition], 1; dwCreationDisposition
0x180065489  xor     r9d, r9d; lpSecurityAttributes
0x18006548c  xor     r8d, r8d; dwShareMode
0x18006548f  mov     edx, 40000000h; dwDesiredAccess
0x180065494  lea     rcx, [rbp+4B0h+FileName]; lpFileName
0x18006549b  call    cs:__imp_CreateFileW
0x1800654a1  mov     [rsp+5B0h+var_570], rax
0x1800654a6  dec     rax
0x1800654a9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800654ad  ja      short loc_1800654BE
0x1800654af  lea     rcx, [rsp+5B0h+var_570]
0x1800654b4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800654b9  jmp     loc_1800653D0
0x1800654be  call    cs:__imp_GetLastError
0x1800654c4  mov     ebx, eax
0x1800654c6  mov     [rsp+5B0h+dwFlagsAndAttributes], eax
0x1800654ca  lea     rax, [rbp+4B0h+FileName]
0x1800654d1  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rax
0x1800654d6  lea     r9, aCreatefilewFai; "CreateFileW failed for %ls: [%d]"
0x1800654dd  mov     r8d, 1F6h
0x1800654e3  lea     rdx, aWindowsCompatI_24; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800654ea  mov     ecx, 1
0x1800654ef  call    AslLogCallPrintf
0x1800654f4  test    ebx, ebx
0x1800654f6  jle     short loc_180065501
0x1800654f8  movzx   ebx, bx
0x1800654fb  or      ebx, 80070000h
0x180065501  lea     rcx, [rsp+5B0h+var_570]
0x180065506  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006550b  jmp     loc_1800655BD
0x180065510  mov     [rsp+5B0h+dwFlagsAndAttributes], ebx
0x180065514  lea     rax, [rsp+5B0h+Buffer]
0x180065519  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rax
0x18006551e  lea     r9, aGetfileattribu_0; "GetFileAttributesW failed for %ls: [%d]"
0x180065525  mov     r8d, 1FDh
0x18006552b  lea     rdx, aWindowsCompatI_24; "Windows::Compat::Inventory::SqliteInvCa"...
0x180065532  mov     ecx, 1
0x180065537  call    AslLogCallPrintf
0x18006553c  jmp     loc_180065369
0x180065541  mov     al, [rbp+4B0h+var_350]
0x180065547  test    al, al
0x180065549  jz      short loc_180065562
0x18006554b  lea     rdx, [rbp+4B0h+var_350]
0x180065552  cmp     al, 5Ch ; '\'
0x180065554  jnz     short loc_180065559
0x180065556  mov     byte ptr [rdx], 2Fh ; '/'
0x180065559  inc     rdx
0x18006555c  mov     al, [rdx]
0x18006555e  test    al, al
0x180065560  jnz     short loc_180065552
0x180065562  xor     r9d, r9d
0x180065565  mov     r8d, edi
0x180065568  mov     rdx, r14
0x18006556b  lea     rcx, [rbp+4B0h+var_350]
0x180065572  call    openDatabase
0x180065577  mov     edi, eax
0x180065579  test    eax, eax
0x18006557b  jz      short loc_1800655BD
0x18006557d  mov     rcx, [r14]
0x180065580  call    sqlite3_errmsg
0x180065585  mov     qword ptr [rsp+5B0h+dwFlagsAndAttributes], rax
0x18006558a  mov     [rsp+5B0h+dwCreationDisposition], edi
0x18006558e  lea     r9, aSqlite3OpenV2F; "sqlite3_open_v2 failed: [%d] %hs"
0x180065595  mov     r8d, 217h
0x18006559b  lea     rdx, aWindowsCompatI_24; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800655a2  mov     ecx, 1
0x1800655a7  call    AslLogCallPrintf
0x1800655ac  test    edi, edi
0x1800655ae  jg      short loc_1800655B4
0x1800655b0  mov     ebx, edi
0x1800655b2  jmp     short loc_1800655BD
0x1800655b4  movzx   ebx, di
0x1800655b7  or      ebx, 80070000h
0x1800655bd  mov     eax, ebx
0x1800655bf  mov     rcx, [rbp+4B0h+var_30]
0x1800655c6  xor     rcx, rsp; StackCookie
0x1800655c9  call    __security_check_cookie
0x1800655ce  lea     r11, [rsp+5B0h+var_20]
0x1800655d6  mov     rbx, [r11+40h]
0x1800655da  mov     rsi, [r11+48h]
0x1800655de  mov     rsp, r11
0x1800655e1  pop     r15
0x1800655e3  pop     r14
0x1800655e5  pop     r12
0x1800655e7  pop     rdi
0x1800655e8  pop     rbp
0x1800655e9  retn
```
