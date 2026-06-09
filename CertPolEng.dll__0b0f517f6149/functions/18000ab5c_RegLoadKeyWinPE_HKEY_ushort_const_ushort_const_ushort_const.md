# RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000ab5c`
- end: `0x18000ad24`
- name: `?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `456`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180008950`

## callees

- `0x1800088f0`
- `0x18000ab5c`
- `0x18000b32c`
- `0x18000b3c4`
- `0x180018f50`
- `0x1800191fc`
- `0x1800193b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18000ac9d`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18000ac9d`

## string_xrefs

- `0x18000ace7`: `%s: GetWindowsDirectoryWinPE returns an empty path.`
- `0x18000aba1`: `GetwinDirectoryWinPE`
- `0x18000acba`: `%s: Cannot load file "%s" into registry key "%s". RegLoadKeyW error code: 0x%08x.`
- `0x18000acd2`: `%s: File "%s" loaded into registry key "%s".`
- `0x18000ac76`: `system32\config\software`

## pseudocode

```c
__int64 __fastcall RegLoadKeyWinPE(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  WCHAR *v4; // r14
  unsigned int WindowsDirectoryWinPE; // eax
  int v6; // esi
  unsigned __int16 *v7; // rdi
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  LSTATUS KeyW; // eax
  unsigned __int64 v13; // [rsp+68h] [rbp+38h] BYREF
  unsigned __int16 *v14; // [rsp+70h] [rbp+40h] BYREF
  LPCWSTR lpFile; // [rsp+78h] [rbp+48h] BYREF

  v14 = 0;
  v4 = 0;
  lpFile = 0;
  v13 = 0;
  WindowsDirectoryWinPE = GetWindowsDirectoryWinPE(&v14);
  v6 = WindowsDirectoryWinPE;
  if ( WindowsDirectoryWinPE )
  {
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"RegLoadKeyWinPE",
      L"GetwinDirectoryWinPE",
      WindowsDirectoryWinPE);
    v7 = v14;
    goto LABEL_15;
  }
  v7 = v14;
  if ( !v14 || !*v14 )
  {
    Logger::TraceError(L"%s: GetWindowsDirectoryWinPE returns an empty path.", L"RegLoadKeyWinPE");
    LOWORD(v6) = 2;
    goto LABEL_19;
  }
  v8 = StringLen(v14, &v13);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( v13 && v7[v13 - 1] != 92 )
    {
      v10 = StringCat(v7, L"\\", (unsigned __int16 **)&lpFile);
      v9 = v10;
      if ( v10 < 0 )
      {
LABEL_10:
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"RegLoadKeyWinPE",
          L"StringCat",
          (unsigned int)v10);
        v4 = (WCHAR *)lpFile;
        goto LABEL_20;
      }
      SafeFree(v7);
      v7 = (unsigned __int16 *)lpFile;
      lpFile = 0;
    }
    v10 = StringCat(v7, L"system32\\config\\software", (unsigned __int16 **)&lpFile);
    v9 = v10;
    if ( v10 >= 0 )
    {
      v4 = (WCHAR *)lpFile;
      KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware", lpFile);
      v6 = KeyW;
      if ( !KeyW )
      {
        Logger::TraceVerbose(
          L"%s: File \"%s\" loaded into registry key \"%s\".",
          L"RegLoadKeyWinPE",
          v4,
          L"HKEY_LOCAL_MACHINE\\TargetSoftware");
        goto LABEL_20;
      }
      Logger::TraceError(
        L"%s: Cannot load file \"%s\" into registry key \"%s\". RegLoadKeyW error code: 0x%08x.",
        L"RegLoadKeyWinPE",
        v4,
        L"HKEY_LOCAL_MACHINE\\TargetSoftware",
        KeyW);
LABEL_15:
      if ( v6 <= 0 )
      {
        v9 = v6;
        goto LABEL_20;
      }
LABEL_19:
      v9 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_20;
    }
    goto LABEL_10;
  }
  Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"RegLoadKeyWinPE", L"StringLen", (unsigned int)v8);
LABEL_20:
  SafeFree(v7);
  SafeFree(v4);
  return v9;
}

```

## disassembly

```asm
0x18000ab5c  mov     rax, rsp
0x18000ab5f  mov     [rax+8], rbx
0x18000ab63  mov     [rax+20h], r9
0x18000ab67  mov     [rax+18h], r8
0x18000ab6b  mov     [rax+10h], rdx
0x18000ab6f  push    rbp
0x18000ab70  push    rsi
0x18000ab71  push    rdi
0x18000ab72  push    r14
0x18000ab74  push    r15
0x18000ab76  mov     rbp, rsp
0x18000ab79  sub     rsp, 30h
0x18000ab7d  xor     r15d, r15d
0x18000ab80  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x18000ab84  mov     [rbp+arg_10], r15
0x18000ab88  mov     r14d, r15d
0x18000ab8b  mov     [rbp+lpFile], r15
0x18000ab8f  mov     [rbp+arg_8], r15
0x18000ab93  call    ?GetWindowsDirectoryWinPE@@YAKPEAPEAG@Z; GetWindowsDirectoryWinPE(ushort * *)
0x18000ab98  mov     esi, eax
0x18000ab9a  test    eax, eax
0x18000ab9c  jz      short loc_18000ABC4
0x18000ab9e  mov     r9d, eax
0x18000aba1  lea     r8, aGetwindirector; "GetwinDirectoryWinPE"
0x18000aba8  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18000abaf  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000abb6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000abbb  mov     rdi, [rbp+arg_10]
0x18000abbf  jmp     loc_18000ACCA
0x18000abc4  mov     rdi, [rbp+arg_10]
0x18000abc8  test    rdi, rdi
0x18000abcb  jz      loc_18000ACE0
0x18000abd1  cmp     [rdi], r15w
0x18000abd5  jz      loc_18000ACE0
0x18000abdb  lea     rdx, [rbp+arg_8]; unsigned __int64 *
0x18000abdf  mov     rcx, rdi; unsigned __int16 *
0x18000abe2  call    ?StringLen@@YAJPEBGPEA_K@Z; StringLen(ushort const *,unsigned __int64 *)
0x18000abe7  mov     ebx, eax
0x18000abe9  test    eax, eax
0x18000abeb  jns     short loc_18000AC0F
0x18000abed  mov     r9d, eax
0x18000abf0  lea     r8, aStringlen; "StringLen"
0x18000abf7  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18000abfe  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18000ac05  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000ac0a  jmp     loc_18000AD01
0x18000ac0f  mov     rax, [rbp+arg_8]
0x18000ac13  test    rax, rax
0x18000ac16  jz      short loc_18000AC6F
0x18000ac18  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x18000ac1e  jz      short loc_18000AC6F
0x18000ac20  lea     r8, [rbp+lpFile]; unsigned __int16 **
0x18000ac24  mov     rcx, rdi; unsigned __int16 *
0x18000ac27  lea     rdx, asc_18001F910; "\\"
0x18000ac2e  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x18000ac33  mov     ebx, eax
0x18000ac35  test    eax, eax
0x18000ac37  jns     short loc_18000AC5F
0x18000ac39  mov     r9d, eax
0x18000ac3c  lea     r8, aStringcat; "StringCat"
0x18000ac43  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18000ac4a  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18000ac51  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000ac56  mov     r14, [rbp+lpFile]
0x18000ac5a  jmp     loc_18000AD01
0x18000ac5f  mov     rcx, rdi; void *
0x18000ac62  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000ac67  mov     rdi, [rbp+lpFile]
0x18000ac6b  mov     [rbp+lpFile], r15
0x18000ac6f  lea     r8, [rbp+lpFile]; unsigned __int16 **
0x18000ac73  mov     rcx, rdi; unsigned __int16 *
0x18000ac76  lea     rdx, aSystem32Config; "system32\\config\\software"
0x18000ac7d  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x18000ac82  mov     ebx, eax
0x18000ac84  test    eax, eax
0x18000ac86  js      short loc_18000AC39
0x18000ac88  mov     r14, [rbp+lpFile]
0x18000ac8c  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x18000ac93  mov     r8, r14; lpFile
0x18000ac96  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ac9d  call    cs:__imp_RegLoadKeyW
0x18000aca3  lea     r9, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x18000acaa  mov     r8, r14
0x18000acad  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18000acb4  mov     esi, eax
0x18000acb6  test    eax, eax
0x18000acb8  jz      short loc_18000ACD2
0x18000acba  lea     rcx, aSCannotLoadFil; "%s: Cannot load file \"%s\" into regist"...
0x18000acc1  mov     [rsp+30h+var_10], eax
0x18000acc5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000acca  test    esi, esi
0x18000accc  jg      short loc_18000ACF8
0x18000acce  mov     ebx, esi
0x18000acd0  jmp     short loc_18000AD01
0x18000acd2  lea     rcx, aSFileSLoadedIn; "%s: File \"%s\" loaded into registry ke"...
0x18000acd9  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000acde  jmp     short loc_18000AD01
0x18000ace0  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18000ace7  lea     rcx, aSGetwindowsdir; "%s: GetWindowsDirectoryWinPE returns an"...
0x18000acee  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000acf3  mov     esi, 2
0x18000acf8  movzx   ebx, si
0x18000acfb  or      ebx, 80070000h
0x18000ad01  mov     rcx, rdi; void *
0x18000ad04  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000ad09  mov     rcx, r14; void *
0x18000ad0c  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000ad11  mov     eax, ebx
0x18000ad13  mov     rbx, [rsp+30h+arg_0]
0x18000ad18  add     rsp, 30h
0x18000ad1c  pop     r15
0x18000ad1e  pop     r14
0x18000ad20  pop     rdi
0x18000ad21  pop     rsi
0x18000ad22  pop     rbp
0x18000ad23  retn
```
