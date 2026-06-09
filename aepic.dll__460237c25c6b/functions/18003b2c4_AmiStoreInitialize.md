# AmiStoreInitialize

- ea: `0x18003b2c4`
- end: `0x18003b5d8`
- name: `AmiStoreInitialize`
- size: `788`
- prototype: `__int64 __fastcall(void **, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003a1e4`

## callees

- `0x180005890`
- `0x180006938`
- `0x18000cb74`
- `0x1800295dc`
- `0x18003a880`
- `0x18003ad18`
- `0x18003aefc`
- `0x18003b2c4`
- `0x18003b5e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b31b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b31b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003b302`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003b44d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003b302`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003b44d`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18003b422`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18003b422`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003b52c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003b52c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003b4ee`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003b4ee`

## string_xrefs

- `0x18003b4a7`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18003b511`: `AmiOverridePath`
- `0x18003b4ae`: `AppCompatFlags`
- `0x18003b32d`: `Error accessing the cache: ERROR_ACCESS_DENIED %ls`
- `0x18003b37e`: `Error accessing the cache: %ls [%d]`
- `0x18003b359`: `The cache %ws does not yet exist. Creating a new one.`
- `0x18003b428`: `Commandline is: %ls`
- `0x18003b403`: `AmipVerifyCachePermissionsCorrect could not fix existing cache. Creating a new one: %ls`
- `0x18003b536`: `Failed to store Ami cache path [%d]`
- `0x18003b471`: `AmipCreateNewCacheFile [%d]`

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
0x18003b2c4  mov     [rsp+arg_18], rbx
0x18003b2c9  push    rbp
0x18003b2ca  push    rsi
0x18003b2cb  push    rdi
0x18003b2cc  push    r12
0x18003b2ce  push    r13
0x18003b2d0  push    r14
0x18003b2d2  push    r15
0x18003b2d4  sub     rsp, 460h
0x18003b2db  mov     rax, cs:__security_cookie
0x18003b2e2  xor     rax, rsp
0x18003b2e5  mov     [rsp+498h+var_48], rax
0x18003b2ed  mov     r15, rcx
0x18003b2f0  xor     r13d, r13d
0x18003b2f3  mov     [rcx], r13
0x18003b2f6  mov     r12, r8
0x18003b2f9  mov     rcx, rdx; lpFileName
0x18003b2fc  mov     rdi, rdx
0x18003b2ff  mov     rbp, rdx
0x18003b302  call    cs:__imp_GetFileAttributesW
0x18003b308  or      ebx, 0FFFFFFFFh
0x18003b30b  lea     esi, [r13+3]
0x18003b30f  lea     r14d, [r13+1]
0x18003b313  cmp     eax, ebx
0x18003b315  jnz     loc_18003B39D
0x18003b31b  call    cs:__imp_GetLastError
0x18003b321  mov     ebx, eax
0x18003b323  cmp     eax, 5
0x18003b326  jnz     short loc_18003B34D
0x18003b328  mov     [rsp+498h+lpData], rbp
0x18003b32d  lea     r9, aErrorAccessing; "Error accessing the cache: ERROR_ACCESS"...
0x18003b334  mov     r8d, 198h
0x18003b33a  mov     ecx, esi
0x18003b33c  lea     rdx, aAmistoreinitia; "AmiStoreInitialize"
0x18003b343  call    AslLogCallPrintf
0x18003b348  jmp     loc_18003B5AB
0x18003b34d  lea     rdx, aAmistoreinitia; "AmiStoreInitialize"
0x18003b354  cmp     eax, 2
0x18003b357  jnz     short loc_18003B37A
0x18003b359  lea     r9, aTheCacheWsDoes; "The cache %ws does not yet exist. Creat"...
0x18003b360  mov     [rsp+498h+lpData], rdi
0x18003b365  mov     r8d, 19Dh
0x18003b36b  mov     ecx, esi
0x18003b36d  mov     r14b, r13b
0x18003b370  call    AslLogCallPrintf
0x18003b375  jmp     loc_18003B45F
0x18003b37a  mov     [rsp+498h+cbData], eax
0x18003b37e  lea     r9, aErrorAccessing_0; "Error accessing the cache: %ls [%d]"
0x18003b385  mov     r8d, 1A2h
0x18003b38b  mov     [rsp+498h+lpData], rdi
0x18003b390  mov     ecx, r14d
0x18003b393  call    AslLogCallPrintf
0x18003b398  jmp     loc_18003B5AB
0x18003b39d  mov     rcx, rdi; lpFile
0x18003b3a0  call    ?AmipVerifyCachePermissionsCorrect@@YA_NPEBG@Z; AmipVerifyCachePermissionsCorrect(ushort const *)
0x18003b3a5  test    al, al
0x18003b3a7  jnz     loc_18003B55E
0x18003b3ad  mov     r9, rdi
0x18003b3b0  lea     r8, aLsTmp; "%ls.tmp"
0x18003b3b7  mov     edx, 104h; unsigned __int64
0x18003b3bc  lea     rcx, [rsp+498h+FileName]; unsigned __int16 *
0x18003b3c1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b3c6  test    eax, eax
0x18003b3c8  jns     short loc_18003B3F8
0x18003b3ca  mov     ecx, eax
0x18003b3cc  movzx   ebx, ax
0x18003b3cf  and     ecx, 1FFF0000h
0x18003b3d5  cmp     ecx, 70000h
0x18003b3db  jz      short loc_18003B3DF
0x18003b3dd  mov     ebx, eax
0x18003b3df  lea     r9, aStringcchprint_2; "StringCchPrintfW [%#x]"
0x18003b3e6  mov     r8d, 1B0h
0x18003b3ec  mov     dword ptr [rsp+498h+lpData], eax
0x18003b3f0  mov     ecx, r14d
0x18003b3f3  jmp     loc_18003B33C
0x18003b3f8  lea     rax, [rsp+498h+FileName]
0x18003b3fd  mov     r8d, 1B5h
0x18003b403  lea     r9, aAmipverifycach_0; "AmipVerifyCachePermissionsCorrect could"...
0x18003b40a  mov     [rsp+498h+lpData], rax
0x18003b40f  lea     rdx, aAmistoreinitia; "AmiStoreInitialize"
0x18003b416  mov     ecx, esi
0x18003b418  lea     rbp, [rsp+498h+FileName]
0x18003b41d  call    AslLogCallPrintf
0x18003b422  call    cs:__imp_GetCommandLineW
0x18003b428  lea     r9, aCommandlineIsL; "Commandline is: %ls"
0x18003b42f  mov     r8d, 1B6h
0x18003b435  lea     rdx, aAmistoreinitia; "AmiStoreInitialize"
0x18003b43c  mov     [rsp+498h+lpData], rax
0x18003b441  mov     ecx, esi
0x18003b443  call    AslLogCallPrintf
0x18003b448  lea     rcx, [rsp+498h+FileName]; lpFileName
0x18003b44d  call    cs:__imp_GetFileAttributesW
0x18003b453  cmp     eax, ebx
0x18003b455  setz    r14b
0x18003b459  jnz     loc_18003B558
0x18003b45f  mov     rcx, rbp; lpFile
0x18003b462  call    ?AmipCreateNewCacheFile@@YAKPEBG@Z; AmipCreateNewCacheFile(ushort const *)
0x18003b467  mov     ebx, eax
0x18003b469  test    eax, eax
0x18003b46b  jz      short loc_18003B483
0x18003b46d  mov     dword ptr [rsp+498h+lpData], eax
0x18003b471  lea     r9, aAmipcreatenewc; "AmipCreateNewCacheFile [%d]"
0x18003b478  mov     r8d, 1C0h
0x18003b47e  jmp     loc_18003B33A
0x18003b483  test    r14b, r14b
0x18003b486  jz      loc_18003B558
0x18003b48c  xor     edx, edx; Val
0x18003b48e  lea     rcx, [rsp+498h+SubKey]; void *
0x18003b496  mov     r8d, 20Ah; Size
0x18003b49c  call    memset_0
0x18003b4a1  mov     r14d, 1
0x18003b4a7  lea     r9, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003b4ae  lea     r8, aAppcompatflags; "AppCompatFlags"
0x18003b4b5  mov     dword ptr [rsp+498h+lpData], r14d
0x18003b4ba  mov     edx, 105h
0x18003b4bf  lea     rcx, [rsp+498h+SubKey]
0x18003b4c7  call    AmiUtilityGetPersistedLocation
0x18003b4cc  test    eax, eax
0x18003b4ce  jns     short loc_18003B4E2
0x18003b4d0  lea     r9, aAmiutilitygetp; "AmiUtilityGetPersistedLocation [%#x]"
0x18003b4d7  mov     r8d, 1CCh
0x18003b4dd  jmp     loc_18003B3EC
0x18003b4e2  mov     r8d, 5; dwFlags
0x18003b4e8  mov     rdx, rdi; lpNewFileName
0x18003b4eb  mov     rcx, rbp; lpExistingFileName
0x18003b4ee  call    cs:__imp_MoveFileExW
0x18003b4f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003b4f8  inc     rax
0x18003b4fb  cmp     [rbp+rax*2+0], r13w
0x18003b501  jnz     short loc_18003B4F8
0x18003b503  lea     eax, ds:2[rax*2]
0x18003b50a  mov     r9d, r14d; dwType
0x18003b50d  mov     [rsp+498h+cbData], eax; cbData
0x18003b511  lea     r8, ValueName; "AmiOverridePath"
0x18003b518  lea     rdx, [rsp+498h+SubKey]; lpSubKey
0x18003b520  mov     [rsp+498h+lpData], rbp; lpData
0x18003b525  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003b52c  call    cs:__imp_RegSetKeyValueW
0x18003b532  test    eax, eax
0x18003b534  jz      short loc_18003B55E
0x18003b536  lea     r9, aFailedToStoreA; "Failed to store Ami cache path [%d]"
0x18003b53d  mov     dword ptr [rsp+498h+lpData], eax
0x18003b541  mov     r8d, 1DFh
0x18003b547  lea     rdx, aAmistoreinitia; "AmiStoreInitialize"
0x18003b54e  mov     ecx, r14d
0x18003b551  call    AslLogCallPrintf
0x18003b556  jmp     short loc_18003B55E
0x18003b558  mov     r14d, 1
0x18003b55e  mov     r8, r12; unsigned __int16 *
0x18003b561  mov     rdx, rbp; unsigned __int16 *
0x18003b564  mov     rcx, r15; void **
0x18003b567  call    ?AmipStoreInitialize@@YAKPEAPEAXPEBG1@Z; AmipStoreInitialize(void * *,ushort const *,ushort const *)
0x18003b56c  mov     ebx, eax
0x18003b56e  test    eax, eax
0x18003b570  jz      short loc_18003B5A8
0x18003b572  cmp     ebx, 20h ; ' '
0x18003b575  ja      short loc_18003B58F
0x18003b577  mov     rcx, 100000024h
0x18003b581  bt      rcx, rbx
0x18003b585  jnb     short loc_18003B58F
0x18003b587  mov     r8d, 1EEh
0x18003b58d  jmp     short loc_18003B598
0x18003b58f  mov     esi, r14d
0x18003b592  mov     r8d, 1F2h
0x18003b598  mov     dword ptr [rsp+498h+lpData], ebx
0x18003b59c  lea     r9, aAmipstoreiniti_0; "AmipStoreInitialize failed [%d]"
0x18003b5a3  jmp     loc_18003B33A
0x18003b5a8  mov     ebx, r13d
0x18003b5ab  mov     eax, ebx
0x18003b5ad  mov     rcx, [rsp+498h+var_48]
0x18003b5b5  xor     rcx, rsp; StackCookie
0x18003b5b8  call    __security_check_cookie
0x18003b5bd  mov     rbx, [rsp+498h+arg_18]
0x18003b5c5  add     rsp, 460h
0x18003b5cc  pop     r15
0x18003b5ce  pop     r14
0x18003b5d0  pop     r13
0x18003b5d2  pop     r12
0x18003b5d4  pop     rdi
0x18003b5d5  pop     rsi
0x18003b5d6  pop     rbp
0x18003b5d7  retn
```
