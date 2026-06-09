# HashFileContent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uint,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140017174`
- end: `0x1400174ce`
- name: `?HashFileContent@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IAEAV12@@Z`
- size: `858`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x14000e9bc`

## callees

- `0x140002618`
- `0x140006480`
- `0x14000740c`
- `0x14000775c`
- `0x140015ff8`
- `0x140017174`
- `0x1400174d4`
- `0x14001a8aa`
- `0x14001a8d0`

## import_xrefs

- `ADVAPI32!CryptReleaseContext` at `0x14001748c`
- `ADVAPI32!CryptReleaseContext` at `0x14001748c`
- `ADVAPI32!CryptAcquireContextW` at `0x140017267`
- `ADVAPI32!CryptAcquireContextW` at `0x140017267`
- `ADVAPI32!CryptCreateHash` at `0x1400172b3`
- `ADVAPI32!CryptCreateHash` at `0x1400172b3`
- `ADVAPI32!CryptHashData` at `0x14001731b`
- `ADVAPI32!CryptHashData` at `0x14001731b`
- `ADVAPI32!CryptGetHashParam` at `0x14001735e`
- `ADVAPI32!CryptGetHashParam` at `0x1400173ca`
- `ADVAPI32!CryptGetHashParam` at `0x14001735e`
- `ADVAPI32!CryptGetHashParam` at `0x1400173ca`
- `ADVAPI32!CryptDestroyHash` at `0x14001746c`
- `ADVAPI32!CryptDestroyHash` at `0x14001746c`
- `KERNEL32!CreateFileW` at `0x140017201`
- `KERNEL32!CreateFileW` at `0x140017201`
- `KERNEL32!ReadFile` at `0x1400172f7`
- `KERNEL32!ReadFile` at `0x1400172f7`
- `KERNEL32!CloseHandle` at `0x14001745c`
- `KERNEL32!CloseHandle` at `0x14001745c`
- `KERNEL32!GetLastError` at `0x140017271`
- `KERNEL32!GetLastError` at `0x1400172bd`
- `KERNEL32!GetLastError` at `0x140017325`
- `KERNEL32!GetLastError` at `0x140017368`
- `KERNEL32!GetLastError` at `0x1400173d4`
- `KERNEL32!GetLastError` at `0x140017428`
- `KERNEL32!GetLastError` at `0x140017271`
- `KERNEL32!GetLastError` at `0x1400172bd`
- `KERNEL32!GetLastError` at `0x140017325`
- `KERNEL32!GetLastError` at `0x140017368`
- `KERNEL32!GetLastError` at `0x1400173d4`
- `KERNEL32!GetLastError` at `0x140017428`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14001747a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14001747a`

## string_xrefs

- `0x140017222`: `Failed to open file "%1" for reading. Error 0x%2!x!`
- `0x1400172d2`: `Failed to create hash. Error 0x%1!x!`
- `0x14001744d`: `Failed to read source file %1. Error 0x%2!x!`
- `0x14001737d`: `Failed to read hash value size. Error 0x%1!x!`
- `0x1400173e9`: `Failed to read hash value. Error 0x%1!x!`

## pseudocode

```c
__int64 __fastcall HashFileContent(_QWORD *a1)
{
  _QWORD *v1; // rdi
  unsigned __int8 *v2; // rsi
  HANDLE FileW; // r14
  unsigned int v4; // ebx
  const WCHAR *v5; // r8
  signed int v6; // eax
  signed int v7; // eax
  signed int v8; // eax
  signed int v9; // eax
  unsigned __int8 *v10; // rax
  signed int LastError; // eax
  int v12; // eax
  signed int v13; // eax
  __int64 v14; // rdx
  BYTE pbData[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwProvType; // [rsp+44h] [rbp-BCh] BYREF
  HCRYPTHASH phHash; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pdwDataLen; // [rsp+50h] [rbp-B0h] BYREF
  HCRYPTPROV phProv; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR szProvider[3]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v22; // [rsp+78h] [rbp-88h]
  BYTE Buffer[3280]; // [rsp+80h] [rbp-80h] BYREF

  v1 = a1;
  phProv = 0;
  phHash = 0;
  pdwDataLen = 0;
  *(_DWORD *)pbData = 0;
  dwProvType = 0;
  v22 = 7;
  szProvider[2] = 0;
  LOWORD(szProvider[0]) = 0;
  v2 = 0;
  if ( a1[3] >= 8u )
    a1 = (_QWORD *)*a1;
  FileW = CreateFileW((LPCWSTR)a1, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW )
  {
    GetDefaultProviderInfo(szProvider, &dwProvType);
    v5 = (const WCHAR *)szProvider;
    if ( v22 >= 8 )
      v5 = szProvider[0];
    if ( CryptAcquireContextW(&phProv, 0, v5, dwProvType, 0xF0000000) )
    {
      if ( CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
      {
        while ( 1 )
        {
          dwProvType = 0;
          if ( !ReadFile(FileW, Buffer, 0xCCCu, &dwProvType, 0) )
            break;
          if ( !dwProvType )
          {
            pdwDataLen = 4;
            if ( CryptGetHashParam(phHash, 4u, pbData, &pdwDataLen, 0) )
            {
              if ( *(_DWORD *)pbData )
              {
                v10 = (unsigned __int8 *)operator new[](*(unsigned int *)pbData);
                v2 = v10;
                if ( v10 )
                {
                  memset_0(v10, 0, *(unsigned int *)pbData);
                  if ( CryptGetHashParam(phHash, 2u, v2, (DWORD *)pbData, 0) )
                  {
                    v12 = HexBinaryEncode(v2, *(unsigned int *)pbData);
                    v4 = v12;
                    if ( v12 < 0 )
                      LogWarn(L"Failed to hex hash string. Error 0x%1!x!", (unsigned int)v12);
                  }
                  else
                  {
                    LastError = GetLastError();
                    v4 = LastError;
                    if ( LastError > 0 )
                      v4 = (unsigned __int16)LastError | 0x80070000;
                    LogError(L"Failed to read hash value. Error 0x%1!x!", v4);
                  }
                }
                else
                {
                  v4 = -2147024882;
                }
              }
              else
              {
                v4 = -2147467259;
              }
            }
            else
            {
              v9 = GetLastError();
              v4 = v9;
              if ( v9 > 0 )
                v4 = (unsigned __int16)v9 | 0x80070000;
              LogError(L"Failed to read hash value size. Error 0x%1!x!", v4);
            }
            goto LABEL_43;
          }
          if ( !CryptHashData(phHash, Buffer, dwProvType, 0) )
          {
            v8 = GetLastError();
            v4 = v8;
            if ( v8 > 0 )
              v4 = (unsigned __int16)v8 | 0x80070000;
            LogError(L"Failed hash file data. Error 0x%1!x!", v4);
            goto LABEL_43;
          }
        }
        v13 = GetLastError();
        v4 = v13;
        if ( v13 > 0 )
          v4 = (unsigned __int16)v13 | 0x80070000;
        if ( v1[3] >= 8u )
          v1 = (_QWORD *)*v1;
        LogError(L"Failed to read source file %1. Error 0x%2!x!", v1, v4);
      }
      else
      {
        v7 = GetLastError();
        v4 = v7;
        if ( v7 > 0 )
          v4 = (unsigned __int16)v7 | 0x80070000;
        LogError(L"Failed to create hash. Error 0x%1!x!", v4);
      }
    }
    else
    {
      v6 = GetLastError();
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      LogError(L"Failed to acquire crypt context. Error 0x%1!x!", v4);
    }
LABEL_43:
    CloseHandle(FileW);
  }
  else
  {
    v4 = 0;
    if ( v1[3] >= 8u )
      v1 = (_QWORD *)*v1;
    LogError(L"Failed to open file \"%1\" for reading. Error 0x%2!x!", v1, 0);
  }
  if ( phHash )
  {
    CryptDestroyHash(phHash);
    phHash = 0;
  }
  operator delete[](v2);
  if ( phProv )
  {
    CryptReleaseContext(phProv, 0);
    phProv = 0;
  }
  LOBYTE(v14) = 1;
  std::wstring::_Tidy(szProvider, v14, 0);
  return v4;
}

```

## disassembly

```asm
0x140017174  mov     [rsp-8+arg_8], rbx
0x140017179  push    rbp
0x14001717a  push    rsi
0x14001717b  push    rdi
0x14001717c  push    r14
0x14001717e  push    r15
0x140017180  lea     rbp, [rsp-0C60h]
0x140017188  sub     rsp, 0D60h
0x14001718f  mov     rax, cs:__security_cookie
0x140017196  xor     rax, rsp
0x140017199  mov     [rbp+0C80h+var_30], rax
0x1400171a0  mov     rbx, r8
0x1400171a3  mov     rdi, rcx
0x1400171a6  xor     r15d, r15d
0x1400171a9  mov     [rsp+0D80h+phProv], r15
0x1400171ae  mov     [rsp+0D80h+phHash], r15
0x1400171b3  mov     [rsp+0D80h+pdwDataLen], r15d
0x1400171b8  mov     dword ptr [rsp+0D80h+pbData], r15d
0x1400171bd  mov     [rsp+0D80h+dwProvType], r15d
0x1400171c2  mov     [rsp+0D80h+var_D08], 7
0x1400171cb  mov     [rsp+0D80h+var_D10], r15
0x1400171d0  mov     word ptr [rsp+0D80h+szProvider], r15w
0x1400171d6  mov     esi, r15d
0x1400171d9  cmp     qword ptr [rcx+18h], 8
0x1400171de  jb      short loc_1400171E3
0x1400171e0  mov     rcx, [rcx]; lpFileName
0x1400171e3  mov     [rsp+0D80h+hTemplateFile], r15; hTemplateFile
0x1400171e8  mov     [rsp+0D80h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1400171ed  mov     [rsp+0D80h+dwCreationDisposition], 3; dwCreationDisposition
0x1400171f5  xor     r9d, r9d; lpSecurityAttributes
0x1400171f8  mov     edx, 80000000h; dwDesiredAccess
0x1400171fd  lea     r8d, [r9+1]; dwShareMode
0x140017201  call    cs:__imp_CreateFileW
0x140017207  mov     r14, rax
0x14001720a  test    rax, rax
0x14001720d  jnz     short loc_140017233
0x14001720f  mov     ebx, r15d
0x140017212  cmp     qword ptr [rdi+18h], 8
0x140017217  jb      short loc_14001721C
0x140017219  mov     rdi, [rdi]
0x14001721c  xor     r8d, r8d
0x14001721f  mov     rdx, rdi
0x140017222  lea     rcx, aFailedToOpenFi; "Failed to open file \"%1\" for reading."...
0x140017229  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14001722e  jmp     loc_140017462
0x140017233  lea     rdx, [rsp+0D80h+dwProvType]
0x140017238  lea     rcx, [rsp+0D80h+szProvider]
0x14001723d  call    ?GetDefaultProviderInfo@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK@Z; GetDefaultProviderInfo(std::wstring &,ulong &)
0x140017242  lea     r8, [rsp+0D80h+szProvider]
0x140017247  cmp     [rsp+0D80h+var_D08], 8
0x14001724d  cmovnb  r8, [rsp+0D80h+szProvider]; szProvider
0x140017253  mov     [rsp+0D80h+dwCreationDisposition], 0F0000000h; dwFlags
0x14001725b  mov     r9d, [rsp+0D80h+dwProvType]; dwProvType
0x140017260  xor     edx, edx; szContainer
0x140017262  lea     rcx, [rsp+0D80h+phProv]; phProv
0x140017267  call    cs:__imp_CryptAcquireContextW
0x14001726d  test    eax, eax
0x14001726f  jnz     short loc_140017299
0x140017271  call    cs:__imp_GetLastError
0x140017277  mov     ebx, eax
0x140017279  test    eax, eax
0x14001727b  jle     short loc_140017286
0x14001727d  movzx   ebx, ax
0x140017280  or      ebx, 80070000h
0x140017286  lea     rcx, aFailedToAcquir; "Failed to acquire crypt context. Error "...
0x14001728d  mov     edx, ebx
0x14001728f  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140017294  jmp     loc_140017459
0x140017299  lea     rax, [rsp+0D80h+phHash]
0x14001729e  mov     qword ptr [rsp+0D80h+dwCreationDisposition], rax; phHash
0x1400172a3  xor     r9d, r9d; dwFlags
0x1400172a6  xor     r8d, r8d; hKey
0x1400172a9  mov     edx, 800Ch; Algid
0x1400172ae  mov     rcx, [rsp+0D80h+phProv]; hProv
0x1400172b3  call    cs:__imp_CryptCreateHash
0x1400172b9  test    eax, eax
0x1400172bb  jnz     short loc_1400172DB
0x1400172bd  call    cs:__imp_GetLastError
0x1400172c3  mov     ebx, eax
0x1400172c5  test    eax, eax
0x1400172c7  jle     short loc_1400172D2
0x1400172c9  movzx   ebx, ax
0x1400172cc  or      ebx, 80070000h
0x1400172d2  lea     rcx, aFailedToCreate_4; "Failed to create hash. Error 0x%1!x!"
0x1400172d9  jmp     short loc_14001728D
0x1400172db  mov     [rsp+0D80h+dwProvType], r15d
0x1400172e0  mov     qword ptr [rsp+0D80h+dwCreationDisposition], r15; lpOverlapped
0x1400172e5  lea     r9, [rsp+0D80h+dwProvType]; lpNumberOfBytesRead
0x1400172ea  mov     r8d, 0CCCh; nNumberOfBytesToRead
0x1400172f0  lea     rdx, [rbp+0C80h+Buffer]; lpBuffer
0x1400172f4  mov     rcx, r14; hFile
0x1400172f7  call    cs:__imp_ReadFile
0x1400172fd  test    eax, eax
0x1400172ff  jz      loc_140017428
0x140017305  mov     r8d, [rsp+0D80h+dwProvType]; dwDataLen
0x14001730a  mov     rcx, [rsp+0D80h+phHash]; hHash
0x14001730f  test    r8d, r8d
0x140017312  jz      short loc_140017346
0x140017314  xor     r9d, r9d; dwFlags
0x140017317  lea     rdx, [rbp+0C80h+Buffer]; pbData
0x14001731b  call    cs:__imp_CryptHashData
0x140017321  test    eax, eax
0x140017323  jnz     short loc_1400172DB
0x140017325  call    cs:__imp_GetLastError
0x14001732b  mov     ebx, eax
0x14001732d  test    eax, eax
0x14001732f  jle     short loc_14001733A
0x140017331  movzx   ebx, ax
0x140017334  or      ebx, 80070000h
0x14001733a  lea     rcx, aFailedHashFile; "Failed hash file data. Error 0x%1!x!"
0x140017341  jmp     loc_14001728D
0x140017346  mov     edx, 4; dwParam
0x14001734b  mov     [rsp+0D80h+pdwDataLen], edx
0x14001734f  mov     [rsp+0D80h+dwCreationDisposition], r15d; dwFlags
0x140017354  lea     r9, [rsp+0D80h+pdwDataLen]; pdwDataLen
0x140017359  lea     r8, [rsp+0D80h+pbData]; pbData
0x14001735e  call    cs:__imp_CryptGetHashParam
0x140017364  test    eax, eax
0x140017366  jnz     short loc_140017389
0x140017368  call    cs:__imp_GetLastError
0x14001736e  mov     ebx, eax
0x140017370  test    eax, eax
0x140017372  jle     short loc_14001737D
0x140017374  movzx   ebx, ax
0x140017377  or      ebx, 80070000h
0x14001737d  lea     rcx, aFailedToReadHa; "Failed to read hash value size. Error 0"...
0x140017384  jmp     loc_14001728D
0x140017389  mov     eax, dword ptr [rsp+0D80h+pbData]
0x14001738d  test    eax, eax
0x14001738f  jz      loc_140017421
0x140017395  mov     ecx, eax; unsigned __int64
0x140017397  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14001739c  mov     rsi, rax
0x14001739f  test    rax, rax
0x1400173a2  jz      short loc_14001741A
0x1400173a4  mov     r8d, dword ptr [rsp+0D80h+pbData]; Size
0x1400173a9  xor     edx, edx; Val
0x1400173ab  mov     rcx, rax; void *
0x1400173ae  call    memset_0
0x1400173b3  mov     [rsp+0D80h+dwCreationDisposition], r15d; dwFlags
0x1400173b8  lea     r9, [rsp+0D80h+pbData]; pdwDataLen
0x1400173bd  mov     r8, rsi; pbData
0x1400173c0  mov     edx, 2; dwParam
0x1400173c5  mov     rcx, [rsp+0D80h+phHash]; hHash
0x1400173ca  call    cs:__imp_CryptGetHashParam
0x1400173d0  test    eax, eax
0x1400173d2  jnz     short loc_1400173F5
0x1400173d4  call    cs:__imp_GetLastError
0x1400173da  mov     ebx, eax
0x1400173dc  test    eax, eax
0x1400173de  jle     short loc_1400173E9
0x1400173e0  movzx   ebx, ax
0x1400173e3  or      ebx, 80070000h
0x1400173e9  lea     rcx, aFailedToReadHa_0; "Failed to read hash value. Error 0x%1!x"...
0x1400173f0  jmp     loc_14001728D
0x1400173f5  mov     r8, rbx
0x1400173f8  mov     edx, dword ptr [rsp+0D80h+pbData]; unsigned int
0x1400173fc  mov     rcx, rsi; unsigned __int8 *
0x1400173ff  call    ?HexBinaryEncode@@YAJPEBEKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HexBinaryEncode(uchar const *,ulong,std::wstring &)
0x140017404  mov     ebx, eax
0x140017406  test    eax, eax
0x140017408  jns     short loc_140017459
0x14001740a  mov     edx, eax
0x14001740c  lea     rcx, aFailedToHexHas; "Failed to hex hash string. Error 0x%1!x"...
0x140017413  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x140017418  jmp     short loc_140017459
0x14001741a  mov     ebx, 8007000Eh
0x14001741f  jmp     short loc_140017459
0x140017421  mov     ebx, 80004005h
0x140017426  jmp     short loc_140017459
0x140017428  call    cs:__imp_GetLastError
0x14001742e  mov     ebx, eax
0x140017430  test    eax, eax
0x140017432  jle     short loc_14001743D
0x140017434  movzx   ebx, ax
0x140017437  or      ebx, 80070000h
0x14001743d  cmp     qword ptr [rdi+18h], 8
0x140017442  jb      short loc_140017447
0x140017444  mov     rdi, [rdi]
0x140017447  mov     r8d, ebx
0x14001744a  mov     rdx, rdi
0x14001744d  lea     rcx, aFailedToReadSo; "Failed to read source file %1. Error 0x"...
0x140017454  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140017459  mov     rcx, r14; hObject
0x14001745c  call    cs:__imp_CloseHandle
0x140017462  mov     rcx, [rsp+0D80h+phHash]; hHash
0x140017467  test    rcx, rcx
0x14001746a  jz      short loc_140017477
0x14001746c  call    cs:__imp_CryptDestroyHash
0x140017472  mov     [rsp+0D80h+phHash], r15
0x140017477  mov     rcx, rsi
0x14001747a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140017480  mov     rcx, [rsp+0D80h+phProv]; hProv
0x140017485  test    rcx, rcx
0x140017488  jz      short loc_140017497
0x14001748a  xor     edx, edx; dwFlags
0x14001748c  call    cs:__imp_CryptReleaseContext
0x140017492  mov     [rsp+0D80h+phProv], r15
0x140017497  xor     r8d, r8d
0x14001749a  mov     dl, 1
0x14001749c  lea     rcx, [rsp+0D80h+szProvider]
0x1400174a1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1400174a6  mov     eax, ebx
0x1400174a8  mov     rcx, [rbp+0C80h+var_30]
0x1400174af  xor     rcx, rsp; StackCookie
0x1400174b2  call    __security_check_cookie
0x1400174b7  mov     rbx, [rsp+0D80h+arg_8]
0x1400174bf  add     rsp, 0D60h
0x1400174c6  pop     r15
0x1400174c8  pop     r14
0x1400174ca  pop     rdi
0x1400174cb  pop     rsi
0x1400174cc  pop     rbp
0x1400174cd  retn
```
