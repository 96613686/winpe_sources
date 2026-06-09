# RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x180079670`
- end: `0x180079838`
- name: `?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `456`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18007c080`

## callees

- `0x180079504`
- `0x180079670`
- `0x180079de0`
- `0x180079e18`
- `0x18007a168`
- `0x18007d1b8`
- `0x18007d22c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800797b1`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800797b1`

## string_xrefs

- `0x1800797fb`: `%s: GetWindowsDirectoryWinPE returns an empty path.`
- `0x1800796b5`: `GetwinDirectoryWinPE`
- `0x1800797ce`: `%s: Cannot load file "%s" into registry key "%s". RegLoadKeyW error code: 0x%08x.`
- `0x1800797e6`: `%s: File "%s" loaded into registry key "%s".`
- `0x18007978a`: `system32\config\software`

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
0x180079670  mov     rax, rsp
0x180079673  mov     [rax+8], rbx
0x180079677  mov     [rax+20h], r9
0x18007967b  mov     [rax+18h], r8
0x18007967f  mov     [rax+10h], rdx
0x180079683  push    rbp
0x180079684  push    rsi
0x180079685  push    rdi
0x180079686  push    r14
0x180079688  push    r15
0x18007968a  mov     rbp, rsp
0x18007968d  sub     rsp, 30h
0x180079691  xor     r15d, r15d
0x180079694  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x180079698  mov     [rbp+arg_10], r15
0x18007969c  mov     r14d, r15d
0x18007969f  mov     [rbp+lpFile], r15
0x1800796a3  mov     [rbp+arg_8], r15
0x1800796a7  call    ?GetWindowsDirectoryWinPE@@YAKPEAPEAG@Z; GetWindowsDirectoryWinPE(ushort * *)
0x1800796ac  mov     esi, eax
0x1800796ae  test    eax, eax
0x1800796b0  jz      short loc_1800796D8
0x1800796b2  mov     r9d, eax
0x1800796b5  lea     r8, aGetwindirector; "GetwinDirectoryWinPE"
0x1800796bc  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x1800796c3  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x1800796ca  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800796cf  mov     rdi, [rbp+arg_10]
0x1800796d3  jmp     loc_1800797DE
0x1800796d8  mov     rdi, [rbp+arg_10]
0x1800796dc  test    rdi, rdi
0x1800796df  jz      loc_1800797F4
0x1800796e5  cmp     [rdi], r15w
0x1800796e9  jz      loc_1800797F4
0x1800796ef  lea     rdx, [rbp+arg_8]; unsigned __int64 *
0x1800796f3  mov     rcx, rdi; unsigned __int16 *
0x1800796f6  call    ?StringLen@@YAJPEBGPEA_K@Z; StringLen(ushort const *,unsigned __int64 *)
0x1800796fb  mov     ebx, eax
0x1800796fd  test    eax, eax
0x1800796ff  jns     short loc_180079723
0x180079701  mov     r9d, eax
0x180079704  lea     r8, aStringlen; "StringLen"
0x18007970b  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x180079712  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180079719  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007971e  jmp     loc_180079815
0x180079723  mov     rax, [rbp+arg_8]
0x180079727  test    rax, rax
0x18007972a  jz      short loc_180079783
0x18007972c  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x180079732  jz      short loc_180079783
0x180079734  lea     r8, [rbp+lpFile]; unsigned __int16 **
0x180079738  mov     rcx, rdi; unsigned __int16 *
0x18007973b  lea     rdx, asc_180093A68; "\\"
0x180079742  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x180079747  mov     ebx, eax
0x180079749  test    eax, eax
0x18007974b  jns     short loc_180079773
0x18007974d  mov     r9d, eax
0x180079750  lea     r8, aStringcat; "StringCat"
0x180079757  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18007975e  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180079765  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007976a  mov     r14, [rbp+lpFile]
0x18007976e  jmp     loc_180079815
0x180079773  mov     rcx, rdi; void *
0x180079776  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007977b  mov     rdi, [rbp+lpFile]
0x18007977f  mov     [rbp+lpFile], r15
0x180079783  lea     r8, [rbp+lpFile]; unsigned __int16 **
0x180079787  mov     rcx, rdi; unsigned __int16 *
0x18007978a  lea     rdx, aSystem32Config; "system32\\config\\software"
0x180079791  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x180079796  mov     ebx, eax
0x180079798  test    eax, eax
0x18007979a  js      short loc_18007974D
0x18007979c  mov     r14, [rbp+lpFile]
0x1800797a0  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x1800797a7  mov     r8, r14; lpFile
0x1800797aa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800797b1  call    cs:__imp_RegLoadKeyW
0x1800797b7  lea     r9, aHkeyLocalMachi_3; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x1800797be  mov     r8, r14
0x1800797c1  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x1800797c8  mov     esi, eax
0x1800797ca  test    eax, eax
0x1800797cc  jz      short loc_1800797E6
0x1800797ce  lea     rcx, aSCannotLoadFil; "%s: Cannot load file \"%s\" into regist"...
0x1800797d5  mov     [rsp+30h+var_10], eax
0x1800797d9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800797de  test    esi, esi
0x1800797e0  jg      short loc_18007980C
0x1800797e2  mov     ebx, esi
0x1800797e4  jmp     short loc_180079815
0x1800797e6  lea     rcx, aSFileSLoadedIn; "%s: File \"%s\" loaded into registry ke"...
0x1800797ed  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800797f2  jmp     short loc_180079815
0x1800797f4  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x1800797fb  lea     rcx, aSGetwindowsdir; "%s: GetWindowsDirectoryWinPE returns an"...
0x180079802  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180079807  mov     esi, 2
0x18007980c  movzx   ebx, si
0x18007980f  or      ebx, 80070000h
0x180079815  mov     rcx, rdi; void *
0x180079818  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007981d  mov     rcx, r14; void *
0x180079820  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180079825  mov     eax, ebx
0x180079827  mov     rbx, [rsp+30h+arg_0]
0x18007982c  add     rsp, 30h
0x180079830  pop     r15
0x180079832  pop     r14
0x180079834  pop     rdi
0x180079835  pop     rsi
0x180079836  pop     rbp
0x180079837  retn
```
