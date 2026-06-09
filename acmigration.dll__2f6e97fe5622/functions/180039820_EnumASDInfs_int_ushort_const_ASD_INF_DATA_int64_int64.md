# EnumASDInfs(int (&)(ushort const *,_ASD_INF_DATA *,__int64),__int64)

- ea: `0x180039820`
- end: `0x180039a13`
- name: `?EnumASDInfs@@YAJA6AHPEBGPEAU_ASD_INF_DATA@@_J@Z2@Z`
- size: `499`
- prototype: `__int64 __fastcall(int (*)(const unsigned __int16 *, struct _ASD_INF_DATA *, __int64), __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180039740`
- `0x1800397f0`

## callees

- `0x180001cf0`
- `0x180002110`
- `0x180002874`
- `0x18000a51c`
- `0x18000a654`
- `0x180039820`
- `0x180039a1c`
- `0x18006a010`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryW` at `0x180039882`
- `KERNEL32!GetWindowsDirectoryW` at `0x180039882`
- `KERNEL32!FindClose` at `0x1800399cd`
- `KERNEL32!FindClose` at `0x1800399cd`
- `KERNEL32!FindNextFileW` at `0x1800399b9`
- `KERNEL32!FindNextFileW` at `0x1800399b9`
- `KERNEL32!FindFirstFileW` at `0x180039935`
- `KERNEL32!FindFirstFileW` at `0x180039935`
- `KERNEL32!GetLastError` at `0x18003988c`
- `KERNEL32!GetLastError` at `0x18003988c`

## pseudocode

```c
__int64 __fastcall EnumASDInfs(unsigned int (__fastcall *a1)(wchar_t *, struct _ASD_INF_DATA *, __int64), __int64 a2)
{
  __int64 v4; // rdx
  signed int LastError; // ebx
  __int64 v6; // rax
  unsigned __int64 v7; // rcx
  HANDLE FirstFileW; // rdi
  struct _ASD_INF_DATA *v10; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t v13[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  wchar_t pszDest[264]; // [rsp+6B0h] [rbp+5B0h] BYREF

  v10 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    goto LABEL_24;
  }
  v6 = -1;
  do
    ++v6;
  while ( Buffer[v6] );
  if ( !(_DWORD)v6 )
  {
    LOWORD(LastError) = 1627;
    return (unsigned __int16)LastError | 0x80070000;
  }
  v7 = (unsigned int)(v6 - 1);
  if ( Buffer[v7] == 92 )
  {
    if ( v7 >= 260 )
      _report_rangecheckfailure(v7 * 2, v4);
    Buffer[(unsigned int)(v6 - 1)] = 0;
  }
  if ( StringCchCatW(Buffer, 0x104u, L"\\inf") < 0 || StringCchPrintfW(pszDest, 0x104u, L"%ws\\oem*.inf", Buffer) < 0 )
  {
    LOWORD(LastError) = 122;
    return (unsigned __int16)LastError | 0x80070000;
  }
  FirstFileW = FindFirstFileW(pszDest, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LOWORD(LastError) = 2;
    return (unsigned __int16)LastError | 0x80070000;
  }
  LastError = 0;
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      goto LABEL_20;
    if ( StringCchPrintfW(v13, 0x104u, L"%ws\\%ws", Buffer, FindFileData.cFileName) < 0 )
      break;
    if ( (unsigned int)IsASDInf(v13, &v10) && !a1(v13, v10, a2) )
      goto LABEL_23;
LABEL_20:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_23;
  }
  LastError = 122;
LABEL_23:
  FindClose(FirstFileW);
LABEL_24:
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180039820  mov     [rsp-8+arg_10], rbx
0x180039825  mov     [rsp-8+arg_18], rsi
0x18003982a  push    rbp
0x18003982b  push    rdi
0x18003982c  push    r12
0x18003982e  push    r14
0x180039830  push    r15
0x180039832  lea     rbp, [rsp-7D0h]
0x18003983a  sub     rsp, 8D0h
0x180039841  mov     rax, cs:__security_cookie
0x180039848  xor     rax, rsp
0x18003984b  mov     [rbp+7F0h+var_30], rax
0x180039852  mov     r14, rdx
0x180039855  mov     rsi, rcx
0x180039858  xor     r15d, r15d
0x18003985b  lea     rcx, [rsp+8F0h+FindFileData]; void *
0x180039860  xor     edx, edx; Val
0x180039862  mov     [rsp+8F0h+var_8C0], r15
0x180039867  mov     r8d, 250h; Size
0x18003986d  call    memset_0
0x180039872  mov     r12d, 104h
0x180039878  lea     rcx, [rbp+7F0h+Buffer]; lpBuffer
0x18003987f  mov     edx, r12d; uSize
0x180039882  call    cs:__imp_GetWindowsDirectoryW
0x180039888  test    eax, eax
0x18003988a  jnz     short loc_180039899
0x18003988c  call    cs:__imp_GetLastError
0x180039892  mov     ebx, eax
0x180039894  jmp     loc_1800399D3
0x180039899  lea     rcx, [rbp+7F0h+Buffer]
0x1800398a0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800398a4  inc     rax
0x1800398a7  cmp     [rcx+rax*2], r15w
0x1800398ac  jnz     short loc_1800398A4
0x1800398ae  cmp     eax, 1
0x1800398b1  jnb     short loc_1800398BD
0x1800398b3  mov     ebx, 65Bh
0x1800398b8  jmp     loc_1800399D7
0x1800398bd  lea     ecx, [rax-1]
0x1800398c0  add     rcx, rcx
0x1800398c3  cmp     [rbp+rcx+7F0h+Buffer], 5Ch ; '\'
0x1800398cc  jnz     short loc_1800398E4
0x1800398ce  cmp     rcx, 208h
0x1800398d5  jnb     loc_180039A0D
0x1800398db  mov     [rbp+rcx+7F0h+Buffer], r15w
0x1800398e4  lea     r8, aInf; "\\inf"
0x1800398eb  mov     rdx, r12; cchDest
0x1800398ee  lea     rcx, [rbp+7F0h+Buffer]; pszDest
0x1800398f5  call    StringCchCatW
0x1800398fa  test    eax, eax
0x1800398fc  jns     short loc_180039908
0x1800398fe  mov     ebx, 7Ah ; 'z'
0x180039903  jmp     loc_1800399D7
0x180039908  lea     r9, [rbp+7F0h+Buffer]
0x18003990f  mov     rdx, r12; cchDest
0x180039912  lea     r8, aWsOemInf; "%ws\\oem*.inf"
0x180039919  lea     rcx, [rbp+7F0h+pszDest]; pszDest
0x180039920  call    StringCchPrintfW
0x180039925  test    eax, eax
0x180039927  js      short loc_1800398FE
0x180039929  lea     rdx, [rsp+8F0h+FindFileData]; lpFindFileData
0x18003992e  lea     rcx, [rbp+7F0h+pszDest]; lpFileName
0x180039935  call    cs:__imp_FindFirstFileW
0x18003993b  mov     rdi, rax
0x18003993e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039942  jnz     short loc_18003994C
0x180039944  lea     ebx, [rax+3]
0x180039947  jmp     loc_1800399D7
0x18003994c  mov     ebx, r15d
0x18003994f  test    byte ptr [rsp+8F0h+FindFileData.dwFileAttributes], 10h
0x180039954  jnz     short loc_1800399B1
0x180039956  lea     rax, [rsp+8F0h+FindFileData.cFileName]
0x18003995b  mov     rdx, r12; cchDest
0x18003995e  lea     r9, [rbp+7F0h+Buffer]
0x180039965  mov     [rsp+8F0h+var_8D0], rax
0x18003996a  lea     r8, aWsWs; "%ws\\%ws"
0x180039971  lea     rcx, [rbp+7F0h+var_450]; pszDest
0x180039978  call    StringCchPrintfW
0x18003997d  test    eax, eax
0x18003997f  js      short loc_1800399C5
0x180039981  lea     rdx, [rsp+8F0h+var_8C0]; struct _ASD_INF_DATA **
0x180039986  lea     rcx, [rbp+7F0h+var_450]; unsigned __int16 *
0x18003998d  call    ?IsASDInf@@YAHPEBGPEAPEAU_ASD_INF_DATA@@@Z; IsASDInf(ushort const *,_ASD_INF_DATA * *)
0x180039992  test    eax, eax
0x180039994  jz      short loc_1800399B1
0x180039996  mov     rdx, [rsp+8F0h+var_8C0]
0x18003999b  lea     rcx, [rbp+7F0h+var_450]
0x1800399a2  mov     r8, r14
0x1800399a5  mov     rax, rsi
0x1800399a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399ad  test    eax, eax
0x1800399af  jz      short loc_1800399CA
0x1800399b1  lea     rdx, [rsp+8F0h+FindFileData]; lpFindFileData
0x1800399b6  mov     rcx, rdi; hFindFile
0x1800399b9  call    cs:__imp_FindNextFileW
0x1800399bf  test    eax, eax
0x1800399c1  jnz     short loc_18003994F
0x1800399c3  jmp     short loc_1800399CA
0x1800399c5  mov     ebx, 7Ah ; 'z'
0x1800399ca  mov     rcx, rdi; hFindFile
0x1800399cd  call    cs:__imp_FindClose
0x1800399d3  test    ebx, ebx
0x1800399d5  jle     short loc_1800399E0
0x1800399d7  movzx   ebx, bx
0x1800399da  or      ebx, 80070000h
0x1800399e0  mov     eax, ebx
0x1800399e2  mov     rcx, [rbp+7F0h+var_30]
0x1800399e9  xor     rcx, rsp; StackCookie
0x1800399ec  call    __security_check_cookie
0x1800399f1  lea     r11, [rsp+8F0h+var_20]
0x1800399f9  mov     rbx, [r11+40h]
0x1800399fd  mov     rsi, [r11+48h]
0x180039a01  mov     rsp, r11
0x180039a04  pop     r15
0x180039a06  pop     r14
0x180039a08  pop     r12
0x180039a0a  pop     rdi
0x180039a0b  pop     rbp
0x180039a0c  retn
0x180039a0d  call    __report_rangecheckfailure
```
