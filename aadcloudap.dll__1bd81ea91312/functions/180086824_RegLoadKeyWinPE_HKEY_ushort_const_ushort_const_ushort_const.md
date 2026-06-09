# RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x180086824`
- end: `0x1800869ec`
- name: `?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `456`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800898e8`

## callees

- `0x18008659c`
- `0x180086824`
- `0x1800871b4`
- `0x1800871ec`
- `0x18008758c`
- `0x18008aa28`
- `0x18008aa9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180086965`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180086965`

## string_xrefs

- `0x1800869af`: `%s: GetWindowsDirectoryWinPE returns an empty path.`
- `0x180086982`: `%s: Cannot load file "%s" into registry key "%s". RegLoadKeyW error code: 0x%08x.`
- `0x180086869`: `GetwinDirectoryWinPE`
- `0x18008699a`: `%s: File "%s" loaded into registry key "%s".`
- `0x18008693e`: `system32\config\software`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180086824  mov     rax, rsp
0x180086827  mov     [rax+8], rbx
0x18008682b  mov     [rax+20h], r9
0x18008682f  mov     [rax+18h], r8
0x180086833  mov     [rax+10h], rdx
0x180086837  push    rbp
0x180086838  push    rsi
0x180086839  push    rdi
0x18008683a  push    r14
0x18008683c  push    r15
0x18008683e  mov     rbp, rsp
0x180086841  sub     rsp, 30h
0x180086845  xor     r15d, r15d
0x180086848  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x18008684c  mov     [rbp+arg_10], r15
0x180086850  mov     r14d, r15d
0x180086853  mov     [rbp+lpFile], r15
0x180086857  mov     [rbp+arg_8], r15
0x18008685b  call    ?GetWindowsDirectoryWinPE@@YAKPEAPEAG@Z; GetWindowsDirectoryWinPE(ushort * *)
0x180086860  mov     esi, eax
0x180086862  test    eax, eax
0x180086864  jz      short loc_18008688C
0x180086866  mov     r9d, eax
0x180086869  lea     r8, aGetwindirector; "GetwinDirectoryWinPE"
0x180086870  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x180086877  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18008687e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180086883  mov     rdi, [rbp+arg_10]
0x180086887  jmp     loc_180086992
0x18008688c  mov     rdi, [rbp+arg_10]
0x180086890  test    rdi, rdi
0x180086893  jz      loc_1800869A8
0x180086899  cmp     [rdi], r15w
0x18008689d  jz      loc_1800869A8
0x1800868a3  lea     rdx, [rbp+arg_8]; unsigned __int64 *
0x1800868a7  mov     rcx, rdi; unsigned __int16 *
0x1800868aa  call    ?StringLen@@YAJPEBGPEA_K@Z; StringLen(ushort const *,unsigned __int64 *)
0x1800868af  mov     ebx, eax
0x1800868b1  test    eax, eax
0x1800868b3  jns     short loc_1800868D7
0x1800868b5  mov     r9d, eax
0x1800868b8  lea     r8, aStringlen; "StringLen"
0x1800868bf  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x1800868c6  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x1800868cd  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800868d2  jmp     loc_1800869C9
0x1800868d7  mov     rax, [rbp+arg_8]
0x1800868db  test    rax, rax
0x1800868de  jz      short loc_180086937
0x1800868e0  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x1800868e6  jz      short loc_180086937
0x1800868e8  lea     r8, [rbp+lpFile]; unsigned __int16 **
0x1800868ec  mov     rcx, rdi; unsigned __int16 *
0x1800868ef  lea     rdx, asc_1800ABA78; "\\"
0x1800868f6  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x1800868fb  mov     ebx, eax
0x1800868fd  test    eax, eax
0x1800868ff  jns     short loc_180086927
0x180086901  mov     r9d, eax
0x180086904  lea     r8, aStringcat; "StringCat"
0x18008690b  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x180086912  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180086919  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008691e  mov     r14, [rbp+lpFile]
0x180086922  jmp     loc_1800869C9
0x180086927  mov     rcx, rdi; void *
0x18008692a  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008692f  mov     rdi, [rbp+lpFile]
0x180086933  mov     [rbp+lpFile], r15
0x180086937  lea     r8, [rbp+lpFile]; unsigned __int16 **
0x18008693b  mov     rcx, rdi; unsigned __int16 *
0x18008693e  lea     rdx, aSystem32Config; "system32\\config\\software"
0x180086945  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x18008694a  mov     ebx, eax
0x18008694c  test    eax, eax
0x18008694e  js      short loc_180086901
0x180086950  mov     r14, [rbp+lpFile]
0x180086954  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x18008695b  mov     r8, r14; lpFile
0x18008695e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180086965  call    cs:__imp_RegLoadKeyW
0x18008696b  lea     r9, aHkeyLocalMachi_4; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x180086972  mov     r8, r14
0x180086975  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18008697c  mov     esi, eax
0x18008697e  test    eax, eax
0x180086980  jz      short loc_18008699A
0x180086982  lea     rcx, aSCannotLoadFil; "%s: Cannot load file \"%s\" into regist"...
0x180086989  mov     [rsp+30h+var_10], eax
0x18008698d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180086992  test    esi, esi
0x180086994  jg      short loc_1800869C0
0x180086996  mov     ebx, esi
0x180086998  jmp     short loc_1800869C9
0x18008699a  lea     rcx, aSFileSLoadedIn; "%s: File \"%s\" loaded into registry ke"...
0x1800869a1  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800869a6  jmp     short loc_1800869C9
0x1800869a8  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x1800869af  lea     rcx, aSGetwindowsdir; "%s: GetWindowsDirectoryWinPE returns an"...
0x1800869b6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800869bb  mov     esi, 2
0x1800869c0  movzx   ebx, si
0x1800869c3  or      ebx, 80070000h
0x1800869c9  mov     rcx, rdi; void *
0x1800869cc  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800869d1  mov     rcx, r14; void *
0x1800869d4  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800869d9  mov     eax, ebx
0x1800869db  mov     rbx, [rsp+30h+arg_0]
0x1800869e0  add     rsp, 30h
0x1800869e4  pop     r15
0x1800869e6  pop     r14
0x1800869e8  pop     rdi
0x1800869e9  pop     rsi
0x1800869ea  pop     rbp
0x1800869eb  retn
```
