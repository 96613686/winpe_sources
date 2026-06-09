# CONFIG_HISTORY_ENTITY::ScanHistoryDirectory(void)

- ea: `0x1800048fc`
- end: `0x180004b05`
- name: `?ScanHistoryDirectory@CONFIG_HISTORY_ENTITY@@QEAAJXZ`
- size: `521`
- prototype: `__int64 __fastcall(const unsigned __int16 **this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1800032f0`
- `0x180004014`
- `0x180005110`

## callees

- `0x1800048fc`
- `0x180008c1f`
- `0x180008c50`

## import_xrefs

- `msvcrt!wcstoul` at `0x180004a7e`
- `msvcrt!wcstoul` at `0x180004a7e`
- `msvcrt!_wcsnicmp` at `0x180004a5a`
- `msvcrt!_wcsnicmp` at `0x180004a5a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180004ace`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180004ace`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180004a03`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180004a03`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800049e6`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800049e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a26`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004ada`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004ada`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004964`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004964`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000499d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000499d`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180004981`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800049c7`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180004981`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800049c7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004945`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004945`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CONFIG_HISTORY_ENTITY::ScanHistoryDirectory(const unsigned __int16 **this)
{
  signed int v2; // ebx
  __int64 FirstFileW; // rsi
  unsigned int v4; // r14d
  unsigned int v5; // r15d
  int v6; // r13d
  int v7; // r12d
  signed int LastError; // eax
  unsigned int v9; // eax
  _BYTE v11[32]; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  STRU::STRU((STRU *)v11);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v2 = STRU::Copy((STRU *)v11, this[5]);
  if ( v2 < 0 )
    goto LABEL_24;
  v2 = STRU::Append((STRU *)v11, 0x5Cu);
  if ( v2 < 0 )
    goto LABEL_24;
  v2 = STRU::Append((STRU *)v11, L"CFGHISTORY_");
  if ( v2 < 0 )
    goto LABEL_24;
  FirstFileW = -1;
  v4 = -1;
  v5 = 0;
  v6 = 0;
  v7 = 1;
  v2 = STRU::Append((STRU *)v11, 0x2Au);
  if ( v2 < 0 )
    goto LABEL_24;
  while ( v7 )
  {
    FirstFileW = (__int64)FindFirstFileW(lpFileName, &FindFileData);
    if ( FirstFileW == -1 )
    {
      this[36] = 0;
      *((_DWORD *)this + 74) = 0;
      goto LABEL_24;
    }
    v7 = 0;
LABEL_14:
    if ( (FindFileData.dwFileAttributes & 0x10) != 0
      && !_wcsnicmp(FindFileData.cFileName, L"CFGHISTORY_", 0xBu)
      && !FindFileData.cFileName[21] )
    {
      v9 = wcstoul(&FindFileData.cFileName[11], 0, 10);
      ++v6;
      if ( v9 < v4 )
        v4 = v9;
      if ( v9 > v5 )
        v5 = v9;
    }
  }
  if ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
    goto LABEL_14;
  if ( GetLastError() != 18 )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v2 = -2147467259;
    }
    goto LABEL_14;
  }
  *((_DWORD *)this + 72) = v6;
  *((_DWORD *)this + 73) = v4;
  *((_DWORD *)this + 74) = v5;
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
LABEL_24:
  STRU::~STRU((STRU *)v11);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800048fc  push    rbp
0x1800048fe  push    rbx
0x1800048ff  push    rsi
0x180004900  push    rdi
0x180004901  push    r12
0x180004903  push    r13
0x180004905  push    r14
0x180004907  push    r15
0x180004909  lea     rbp, [rsp-1C8h]
0x180004911  sub     rsp, 2C8h
0x180004918  mov     rax, cs:__security_cookie
0x18000491f  xor     rax, rsp
0x180004922  mov     [rbp+200h+var_50], rax
0x180004929  mov     rdi, rcx
0x18000492c  mov     ebx, 250h
0x180004931  mov     r8d, ebx; Size
0x180004934  xor     edx, edx; Val
0x180004936  lea     rcx, [rsp+300h+FindFileData]; void *
0x18000493b  call    memset_0
0x180004940  lea     rcx, [rsp+300h+var_2E0]
0x180004945  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000494b  nop
0x18000494c  mov     r8d, ebx; Size
0x18000494f  xor     edx, edx; Val
0x180004951  lea     rcx, [rsp+300h+FindFileData]; void *
0x180004956  call    memset_0
0x18000495b  mov     rdx, [rdi+28h]
0x18000495f  lea     rcx, [rsp+300h+var_2E0]
0x180004964  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000496a  mov     ebx, eax
0x18000496c  xor     r12d, r12d
0x18000496f  test    eax, eax
0x180004971  js      loc_180004AD5
0x180004977  lea     edx, [r12+5Ch]
0x18000497c  lea     rcx, [rsp+300h+var_2E0]
0x180004981  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180004987  mov     ebx, eax
0x180004989  test    eax, eax
0x18000498b  js      loc_180004AD5
0x180004991  lea     rdx, aCfghistory; "CFGHISTORY_"
0x180004998  lea     rcx, [rsp+300h+var_2E0]
0x18000499d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800049a3  mov     ebx, eax
0x1800049a5  test    eax, eax
0x1800049a7  js      loc_180004AD5
0x1800049ad  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800049b1  or      r14d, 0FFFFFFFFh
0x1800049b5  mov     r15d, r12d
0x1800049b8  mov     r13d, r12d
0x1800049bb  lea     edx, [rsi+2Bh]
0x1800049be  lea     r12d, [rsi+2]
0x1800049c2  lea     rcx, [rsp+300h+var_2E0]
0x1800049c7  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x1800049cd  mov     ebx, eax
0x1800049cf  test    eax, eax
0x1800049d1  js      loc_180004AD5
0x1800049d7  lea     rdx, [rsp+300h+FindFileData]; lpFindFileData
0x1800049dc  test    r12d, r12d
0x1800049df  jz      short loc_180004A00
0x1800049e1  mov     rcx, [rsp+300h+lpFileName]; lpFileName
0x1800049e6  call    cs:__imp_FindFirstFileW
0x1800049ec  mov     rsi, rax
0x1800049ef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800049f3  jz      loc_180004A9F
0x1800049f9  xor     ecx, ecx
0x1800049fb  mov     r12d, ecx
0x1800049fe  jmp     short loc_180004A42
0x180004a00  mov     rcx, rsi; hFindFile
0x180004a03  call    cs:__imp_FindNextFileW
0x180004a09  test    eax, eax
0x180004a0b  jnz     short loc_180004A42
0x180004a0d  call    cs:__imp_GetLastError
0x180004a13  cmp     eax, 12h
0x180004a16  jz      loc_180004AB0
0x180004a1c  call    cs:__imp_GetLastError
0x180004a22  test    eax, eax
0x180004a24  jz      short loc_180004A3D
0x180004a26  call    cs:__imp_GetLastError
0x180004a2c  mov     ebx, eax
0x180004a2e  test    eax, eax
0x180004a30  jle     short loc_180004A42
0x180004a32  movzx   ebx, ax
0x180004a35  or      ebx, 80070000h
0x180004a3b  jmp     short loc_180004A42
0x180004a3d  mov     ebx, 80004005h
0x180004a42  test    byte ptr [rsp+300h+FindFileData.dwFileAttributes], 10h
0x180004a47  jz      short loc_1800049D7
0x180004a49  mov     r8d, 0Bh; MaxCount
0x180004a4f  lea     rdx, aCfghistory; "CFGHISTORY_"
0x180004a56  lea     rcx, [rbp+200h+FindFileData.cFileName]; String1
0x180004a5a  call    cs:__imp__wcsnicmp
0x180004a60  xor     ecx, ecx
0x180004a62  test    eax, eax
0x180004a64  jnz     loc_1800049D7
0x180004a6a  cmp     [rbp+200h+FindFileData.cFileName+2Ah], cx
0x180004a6e  jnz     loc_1800049D7
0x180004a74  xor     edx, edx; EndPtr
0x180004a76  lea     r8d, [rcx+0Ah]; Radix
0x180004a7a  lea     rcx, [rbp+200h+FindFileData.cFileName+16h]; String
0x180004a7e  call    cs:__imp_wcstoul
0x180004a84  inc     r13d
0x180004a87  cmp     eax, r14d
0x180004a8a  cmovb   r14d, eax
0x180004a8e  cmp     eax, r15d
0x180004a91  jbe     loc_1800049D7
0x180004a97  mov     r15d, eax
0x180004a9a  jmp     loc_1800049D7
0x180004a9f  xor     eax, eax
0x180004aa1  mov     [rdi+120h], rax
0x180004aa8  mov     [rdi+128h], eax
0x180004aae  jmp     short loc_180004AD5
0x180004ab0  mov     [rdi+120h], r13d
0x180004ab7  mov     [rdi+124h], r14d
0x180004abe  mov     [rdi+128h], r15d
0x180004ac5  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180004ac9  jz      short loc_180004AD5
0x180004acb  mov     rcx, rsi; hFindFile
0x180004ace  call    cs:__imp_FindClose
0x180004ad4  nop
0x180004ad5  lea     rcx, [rsp+300h+var_2E0]
0x180004ada  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004ae0  mov     eax, ebx
0x180004ae2  mov     rcx, [rbp+200h+var_50]
0x180004ae9  xor     rcx, rsp; StackCookie
0x180004aec  call    __security_check_cookie
0x180004af1  add     rsp, 2C8h
0x180004af8  pop     r15
0x180004afa  pop     r14
0x180004afc  pop     r13
0x180004afe  pop     r12
0x180004b00  pop     rdi
0x180004b01  pop     rsi
0x180004b02  pop     rbx
0x180004b03  pop     rbp
0x180004b04  retn
```
