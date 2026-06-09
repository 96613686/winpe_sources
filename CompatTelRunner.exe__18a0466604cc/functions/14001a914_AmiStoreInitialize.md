# AmiStoreInitialize

- ea: `0x14001a914`
- end: `0x14001ac28`
- name: `AmiStoreInitialize`
- size: `788`
- prototype: `__int64 __fastcall(void **, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140019258`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x1400093e8`
- `0x1400151b0`
- `0x140019930`
- `0x140019dbc`
- `0x140019fa0`
- `0x14001a914`
- `0x14001ac30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a96b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a96b`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14001aa72`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14001aa72`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14001a952`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14001aa9d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14001a952`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14001aa9d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14001ab7c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14001ab7c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14001ab3e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14001ab3e`

## string_xrefs

- `0x14001aaf7`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x14001ab61`: `AmiOverridePath`
- `0x14001aafe`: `AppCompatFlags`
- `0x14001a97d`: `Error accessing the cache: ERROR_ACCESS_DENIED %ls`
- `0x14001a9a9`: `The cache %ws does not yet exist. Creating a new one.`
- `0x14001aa53`: `AmipVerifyCachePermissionsCorrect could not fix existing cache. Creating a new one: %ls`
- `0x14001a9ce`: `Error accessing the cache: %ls [%d]`
- `0x14001aac1`: `AmipCreateNewCacheFile [%d]`
- `0x14001aa78`: `Commandline is: %ls`
- `0x14001ab86`: `Failed to store Ami cache path [%d]`

## pseudocode

```c
__int64 __fastcall AmiStoreInitialize(void **a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  WCHAR *v6; // rbp
  unsigned int v7; // esi
  DWORD LastError; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 v11; // r8
  __int64 v12; // rcx
  bool v13; // r14
  int PersistedLocation; // eax
  const wchar_t *CommandLineW; // rax
  DWORD FileAttributesW; // eax
  unsigned int NewCacheFile; // eax
  __int64 v18; // rax
  LSTATUS v19; // eax
  unsigned int v20; // eax
  __int64 v21; // rcx
  WCHAR *lpData; // [rsp+20h] [rbp-478h]
  WCHAR FileName[264]; // [rsp+30h] [rbp-468h] BYREF
  WCHAR SubKey[264]; // [rsp+240h] [rbp-258h] BYREF

  *a1 = 0;
  v6 = a2;
  v7 = 3;
  if ( GetFileAttributesW(a2) != -1 )
  {
    if ( AmipVerifyCachePermissionsCorrect(a2) )
      goto LABEL_25;
    PersistedLocation = StringCchPrintfW(FileName, 0x104u, L"%ls.tmp", a2);
    if ( PersistedLocation < 0 )
    {
      v9 = (unsigned __int16)PersistedLocation;
      if ( (PersistedLocation & 0x1FFF0000) != 0x70000 )
        v9 = PersistedLocation;
      v10 = "StringCchPrintfW [%#x]";
      v11 = 432;
      goto LABEL_14;
    }
    v6 = FileName;
    AslLogCallPrintf(
      3,
      "AmiStoreInitialize",
      437,
      "AmipVerifyCachePermissionsCorrect could not fix existing cache. Creating a new one: %ls",
      FileName);
    CommandLineW = GetCommandLineW();
    AslLogCallPrintf(3, "AmiStoreInitialize", 438, "Commandline is: %ls", CommandLineW);
    FileAttributesW = GetFileAttributesW(FileName);
    v13 = FileAttributesW == -1;
    if ( FileAttributesW != -1 )
    {
LABEL_25:
      v20 = AmipStoreInitialize(a1, v6, a3);
      v9 = v20;
      if ( !v20 )
        return 0;
      if ( v20 <= 0x20 && (v21 = 0x100000024LL, _bittest64(&v21, v20)) )
      {
        v11 = 494;
      }
      else
      {
        v7 = 1;
        v11 = 498;
      }
      LODWORD(lpData) = v20;
      v10 = "AmipStoreInitialize failed [%d]";
      goto LABEL_4;
    }
LABEL_16:
    NewCacheFile = AmipCreateNewCacheFile(v6);
    v9 = NewCacheFile;
    if ( NewCacheFile )
    {
      LODWORD(lpData) = NewCacheFile;
      v10 = "AmipCreateNewCacheFile [%d]";
      v11 = 448;
      goto LABEL_4;
    }
    if ( v13 )
    {
      memset_0(SubKey, 0, 0x20Au);
      PersistedLocation = AmiUtilityGetPersistedLocation(
                            (unsigned int)SubKey,
                            261,
                            (unsigned int)L"AppCompatFlags",
                            (unsigned int)L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
                            1);
      if ( PersistedLocation < 0 )
      {
        v10 = "AmiUtilityGetPersistedLocation [%#x]";
        v11 = 460;
LABEL_14:
        LODWORD(lpData) = PersistedLocation;
        v12 = 1;
        goto LABEL_5;
      }
      MoveFileExW(v6, a2, 5u);
      v18 = -1;
      do
        ++v18;
      while ( v6[v18] );
      v19 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, SubKey, L"AmiOverridePath", 1u, v6, 2 * v18 + 2);
      if ( v19 )
        AslLogCallPrintf(1, "AmiStoreInitialize", 479, "Failed to store Ami cache path [%d]", v19);
    }
    goto LABEL_25;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError != 5 )
  {
    if ( LastError != 2 )
    {
      AslLogCallPrintf(1, "AmiStoreInitialize", 418, "Error accessing the cache: %ls [%d]", a2, LastError);
      return v9;
    }
    v13 = 0;
    AslLogCallPrintf(3, "AmiStoreInitialize", 413, "The cache %ws does not yet exist. Creating a new one.", a2);
    goto LABEL_16;
  }
  lpData = v6;
  v10 = "Error accessing the cache: ERROR_ACCESS_DENIED %ls";
  v11 = 408;
LABEL_4:
  v12 = v7;
LABEL_5:
  AslLogCallPrintf(v12, "AmiStoreInitialize", v11, v10, lpData);
  return v9;
}

```

## disassembly

```asm
0x14001a914  mov     [rsp+arg_18], rbx
0x14001a919  push    rbp
0x14001a91a  push    rsi
0x14001a91b  push    rdi
0x14001a91c  push    r12
0x14001a91e  push    r13
0x14001a920  push    r14
0x14001a922  push    r15
0x14001a924  sub     rsp, 460h
0x14001a92b  mov     rax, cs:__security_cookie
0x14001a932  xor     rax, rsp
0x14001a935  mov     [rsp+498h+var_48], rax
0x14001a93d  mov     r15, rcx
0x14001a940  xor     r13d, r13d
0x14001a943  mov     [rcx], r13
0x14001a946  mov     r12, r8
0x14001a949  mov     rcx, rdx; lpFileName
0x14001a94c  mov     rdi, rdx
0x14001a94f  mov     rbp, rdx
0x14001a952  call    cs:__imp_GetFileAttributesW
0x14001a958  or      ebx, 0FFFFFFFFh
0x14001a95b  lea     esi, [r13+3]
0x14001a95f  lea     r14d, [r13+1]
0x14001a963  cmp     eax, ebx
0x14001a965  jnz     loc_14001A9ED
0x14001a96b  call    cs:__imp_GetLastError
0x14001a971  mov     ebx, eax
0x14001a973  cmp     eax, 5
0x14001a976  jnz     short loc_14001A99D
0x14001a978  mov     [rsp+498h+lpData], rbp
0x14001a97d  lea     r9, aErrorAccessing; "Error accessing the cache: ERROR_ACCESS"...
0x14001a984  mov     r8d, 198h
0x14001a98a  mov     ecx, esi
0x14001a98c  lea     rdx, aAmistoreinitia; "AmiStoreInitialize"
0x14001a993  call    AslLogCallPrintf
0x14001a998  jmp     loc_14001ABFB
0x14001a99d  lea     rdx, aAmistoreinitia; "AmiStoreInitialize"
0x14001a9a4  cmp     eax, 2
0x14001a9a7  jnz     short loc_14001A9CA
0x14001a9a9  lea     r9, aTheCacheWsDoes; "The cache %ws does not yet exist. Creat"...
0x14001a9b0  mov     [rsp+498h+lpData], rdi
0x14001a9b5  mov     r8d, 19Dh
0x14001a9bb  mov     ecx, esi
0x14001a9bd  mov     r14b, r13b
0x14001a9c0  call    AslLogCallPrintf
0x14001a9c5  jmp     loc_14001AAAF
0x14001a9ca  mov     [rsp+498h+cbData], eax
0x14001a9ce  lea     r9, aErrorAccessing_0; "Error accessing the cache: %ls [%d]"
0x14001a9d5  mov     r8d, 1A2h
0x14001a9db  mov     [rsp+498h+lpData], rdi
0x14001a9e0  mov     ecx, r14d
0x14001a9e3  call    AslLogCallPrintf
0x14001a9e8  jmp     loc_14001ABFB
0x14001a9ed  mov     rcx, rdi; lpFile
0x14001a9f0  call    ?AmipVerifyCachePermissionsCorrect@@YA_NPEBG@Z; AmipVerifyCachePermissionsCorrect(ushort const *)
0x14001a9f5  test    al, al
0x14001a9f7  jnz     loc_14001ABAE
0x14001a9fd  mov     r9, rdi
0x14001aa00  lea     r8, aLsTmp; "%ls.tmp"
0x14001aa07  mov     edx, 104h; unsigned __int64
0x14001aa0c  lea     rcx, [rsp+498h+FileName]; unsigned __int16 *
0x14001aa11  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001aa16  test    eax, eax
0x14001aa18  jns     short loc_14001AA48
0x14001aa1a  mov     ecx, eax
0x14001aa1c  movzx   ebx, ax
0x14001aa1f  and     ecx, 1FFF0000h
0x14001aa25  cmp     ecx, 70000h
0x14001aa2b  jz      short loc_14001AA2F
0x14001aa2d  mov     ebx, eax
0x14001aa2f  lea     r9, aStringcchprint_0; "StringCchPrintfW [%#x]"
0x14001aa36  mov     r8d, 1B0h
0x14001aa3c  mov     dword ptr [rsp+498h+lpData], eax
0x14001aa40  mov     ecx, r14d
0x14001aa43  jmp     loc_14001A98C
0x14001aa48  lea     rax, [rsp+498h+FileName]
0x14001aa4d  mov     r8d, 1B5h
0x14001aa53  lea     r9, aAmipverifycach_0; "AmipVerifyCachePermissionsCorrect could"...
0x14001aa5a  mov     [rsp+498h+lpData], rax
0x14001aa5f  lea     rdx, aAmistoreinitia; "AmiStoreInitialize"
0x14001aa66  mov     ecx, esi
0x14001aa68  lea     rbp, [rsp+498h+FileName]
0x14001aa6d  call    AslLogCallPrintf
0x14001aa72  call    cs:__imp_GetCommandLineW
0x14001aa78  lea     r9, aCommandlineIsL; "Commandline is: %ls"
0x14001aa7f  mov     r8d, 1B6h
0x14001aa85  lea     rdx, aAmistoreinitia; "AmiStoreInitialize"
0x14001aa8c  mov     [rsp+498h+lpData], rax
0x14001aa91  mov     ecx, esi
0x14001aa93  call    AslLogCallPrintf
0x14001aa98  lea     rcx, [rsp+498h+FileName]; lpFileName
0x14001aa9d  call    cs:__imp_GetFileAttributesW
0x14001aaa3  cmp     eax, ebx
0x14001aaa5  setz    r14b
0x14001aaa9  jnz     loc_14001ABA8
0x14001aaaf  mov     rcx, rbp; lpFile
0x14001aab2  call    ?AmipCreateNewCacheFile@@YAKPEBG@Z; AmipCreateNewCacheFile(ushort const *)
0x14001aab7  mov     ebx, eax
0x14001aab9  test    eax, eax
0x14001aabb  jz      short loc_14001AAD3
0x14001aabd  mov     dword ptr [rsp+498h+lpData], eax
0x14001aac1  lea     r9, aAmipcreatenewc; "AmipCreateNewCacheFile [%d]"
0x14001aac8  mov     r8d, 1C0h
0x14001aace  jmp     loc_14001A98A
0x14001aad3  test    r14b, r14b
0x14001aad6  jz      loc_14001ABA8
0x14001aadc  xor     edx, edx; Val
0x14001aade  lea     rcx, [rsp+498h+SubKey]; void *
0x14001aae6  mov     r8d, 20Ah; Size
0x14001aaec  call    memset_0
0x14001aaf1  mov     r14d, 1
0x14001aaf7  lea     r9, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001aafe  lea     r8, aAppcompatflags; "AppCompatFlags"
0x14001ab05  mov     dword ptr [rsp+498h+lpData], r14d
0x14001ab0a  mov     edx, 105h
0x14001ab0f  lea     rcx, [rsp+498h+SubKey]
0x14001ab17  call    AmiUtilityGetPersistedLocation
0x14001ab1c  test    eax, eax
0x14001ab1e  jns     short loc_14001AB32
0x14001ab20  lea     r9, aAmiutilitygetp; "AmiUtilityGetPersistedLocation [%#x]"
0x14001ab27  mov     r8d, 1CCh
0x14001ab2d  jmp     loc_14001AA3C
0x14001ab32  mov     r8d, 5; dwFlags
0x14001ab38  mov     rdx, rdi; lpNewFileName
0x14001ab3b  mov     rcx, rbp; lpExistingFileName
0x14001ab3e  call    cs:__imp_MoveFileExW
0x14001ab44  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001ab48  inc     rax
0x14001ab4b  cmp     [rbp+rax*2+0], r13w
0x14001ab51  jnz     short loc_14001AB48
0x14001ab53  lea     eax, ds:2[rax*2]
0x14001ab5a  mov     r9d, r14d; dwType
0x14001ab5d  mov     [rsp+498h+cbData], eax; cbData
0x14001ab61  lea     r8, ValueName; "AmiOverridePath"
0x14001ab68  lea     rdx, [rsp+498h+SubKey]; lpSubKey
0x14001ab70  mov     [rsp+498h+lpData], rbp; lpData
0x14001ab75  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001ab7c  call    cs:__imp_RegSetKeyValueW
0x14001ab82  test    eax, eax
0x14001ab84  jz      short loc_14001ABAE
0x14001ab86  lea     r9, aFailedToStoreA; "Failed to store Ami cache path [%d]"
0x14001ab8d  mov     dword ptr [rsp+498h+lpData], eax
0x14001ab91  mov     r8d, 1DFh
0x14001ab97  lea     rdx, aAmistoreinitia; "AmiStoreInitialize"
0x14001ab9e  mov     ecx, r14d
0x14001aba1  call    AslLogCallPrintf
0x14001aba6  jmp     short loc_14001ABAE
0x14001aba8  mov     r14d, 1
0x14001abae  mov     r8, r12; unsigned __int16 *
0x14001abb1  mov     rdx, rbp; unsigned __int16 *
0x14001abb4  mov     rcx, r15; void **
0x14001abb7  call    ?AmipStoreInitialize@@YAKPEAPEAXPEBG1@Z; AmipStoreInitialize(void * *,ushort const *,ushort const *)
0x14001abbc  mov     ebx, eax
0x14001abbe  test    eax, eax
0x14001abc0  jz      short loc_14001ABF8
0x14001abc2  cmp     ebx, 20h ; ' '
0x14001abc5  ja      short loc_14001ABDF
0x14001abc7  mov     rcx, 100000024h
0x14001abd1  bt      rcx, rbx
0x14001abd5  jnb     short loc_14001ABDF
0x14001abd7  mov     r8d, 1EEh
0x14001abdd  jmp     short loc_14001ABE8
0x14001abdf  mov     esi, r14d
0x14001abe2  mov     r8d, 1F2h
0x14001abe8  mov     dword ptr [rsp+498h+lpData], ebx
0x14001abec  lea     r9, aAmipstoreiniti_0; "AmipStoreInitialize failed [%d]"
0x14001abf3  jmp     loc_14001A98A
0x14001abf8  mov     ebx, r13d
0x14001abfb  mov     eax, ebx
0x14001abfd  mov     rcx, [rsp+498h+var_48]
0x14001ac05  xor     rcx, rsp; StackCookie
0x14001ac08  call    __security_check_cookie
0x14001ac0d  mov     rbx, [rsp+498h+arg_18]
0x14001ac15  add     rsp, 460h
0x14001ac1c  pop     r15
0x14001ac1e  pop     r14
0x14001ac20  pop     r13
0x14001ac22  pop     r12
0x14001ac24  pop     rdi
0x14001ac25  pop     rsi
0x14001ac26  pop     rbp
0x14001ac27  retn
```
