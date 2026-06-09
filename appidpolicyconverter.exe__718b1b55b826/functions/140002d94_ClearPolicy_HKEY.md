# ClearPolicy(HKEY__ *)

- ea: `0x140002d94`
- end: `0x140002ffd`
- name: `?ClearPolicy@@YAKPEAUHKEY__@@@Z`
- size: `617`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x14000458c`

## callees

- `0x140002d94`
- `0x1400059dc`
- `0x140005a50`
- `0x1400073a8`
- `0x140013acf`
- `0x140013b10`

## import_xrefs

- `msvcrt!wcsstr` at `0x140002ea3`
- `msvcrt!wcsstr` at `0x140002ea3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140002eda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140002eda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002eef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002eef`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140002f87`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140002f87`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140002efd`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140002efd`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140002e6f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140002e6f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140002f1a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140002f1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002dfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002dfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002f95`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x140002df0`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x140002df0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140002fa7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140002fa7`

## string_xrefs

- `0x140002e23`: `\System32\AppLocker\`
- `0x140002e47`: `\System32\AppLocker\*.Applocker`

## pseudocode

```c
__int64 __fastcall ClearPolicy(HKEY hKey)
{
  DWORD LastError; // ebx
  HANDLE FirstFileW; // rsi
  wchar_t *v4; // rax
  wchar_t *v5; // rdi
  LSTATUS v6; // eax
  unsigned int i; // edi
  int v9; // r8d
  HKEY hKeya; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR Buffer[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  hKeya = 0;
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    return GetLastError();
  StringCbCopyW(FileName, 0x208u, Buffer);
  if ( StringCbCatW(FileName, 0x208u, L"\\System32\\AppLocker\\") < 0
    || StringCbCatW(Buffer, 0x20Au, L"\\System32\\AppLocker\\*.Applocker") < 0 )
  {
    return 122;
  }
  LastError = 0;
  FirstFileW = FindFirstFileW(Buffer, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    return LastError;
  do
  {
    if ( FindFileData.cFileName[0] != 46 && (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      v4 = wcsstr(FindFileData.cFileName, L".");
      v5 = v4;
      if ( v4 )
      {
        *v4 = 0;
        if ( hKey )
        {
          v6 = RegOpenKeyExW(hKey, FindFileData.cFileName, 0, 0x20019u, &hKeya);
          *v5 = 46;
          LastError = v6;
          if ( !v6 )
          {
            RegCloseKey(hKeya);
            continue;
          }
          if ( v6 != 2 )
            goto LABEL_16;
        }
        else
        {
          hKeya = 0;
          *v4 = 46;
        }
        if ( StringCbCatW(FileName, 0x208u, FindFileData.cFileName) < 0 )
        {
          LastError = 122;
          goto LABEL_16;
        }
        for ( i = 0; i < 0xA && !DeleteFileW(FileName); ++i )
        {
          LastError = GetLastError();
          if ( LastError != 32 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
            {
              WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, v9, (unsigned int)FileName, LastError);
            }
            goto LABEL_16;
          }
          Sleep(0x3E8u);
        }
      }
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  LastError = GetLastError();
  if ( LastError == 18 )
    LastError = 0;
LABEL_16:
  FindClose(FirstFileW);
  return LastError;
}

```

## disassembly

```asm
0x140002d94  mov     [rsp-8+arg_8], rbx
0x140002d99  mov     [rsp-8+arg_10], rsi
0x140002d9e  push    rbp
0x140002d9f  push    rdi
0x140002da0  push    r12
0x140002da2  push    r14
0x140002da4  push    r15
0x140002da6  lea     rbp, [rsp-5C0h]
0x140002dae  sub     rsp, 6C0h
0x140002db5  mov     rax, cs:__security_cookie
0x140002dbc  xor     rax, rsp
0x140002dbf  mov     [rbp+5E0h+var_30], rax
0x140002dc6  mov     r14, rcx
0x140002dc9  xor     edx, edx; Val
0x140002dcb  lea     rcx, [rsp+6E0h+FindFileData]; void *
0x140002dd0  mov     r8d, 250h; Size
0x140002dd6  call    memset_0
0x140002ddb  mov     edx, 104h; uSize
0x140002de0  mov     [rsp+6E0h+hKey], 0
0x140002de9  lea     rcx, [rbp+5E0h+Buffer]; lpBuffer
0x140002df0  call    cs:__imp_GetWindowsDirectoryW
0x140002df6  test    eax, eax
0x140002df8  jnz     short loc_140002E07
0x140002dfa  call    cs:__imp_GetLastError
0x140002e00  mov     ebx, eax
0x140002e02  jmp     loc_140002F20
0x140002e07  mov     r12d, 208h
0x140002e0d  lea     r8, [rbp+5E0h+Buffer]; unsigned __int16 *
0x140002e14  mov     edx, r12d; unsigned __int64
0x140002e17  lea     rcx, [rbp+5E0h+FileName]; unsigned __int16 *
0x140002e1e  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140002e23  lea     r8, aSystem32Apploc_1; "\\System32\\AppLocker\\"
0x140002e2a  mov     edx, r12d; unsigned __int64
0x140002e2d  lea     rcx, [rbp+5E0h+FileName]; unsigned __int16 *
0x140002e34  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140002e39  test    eax, eax
0x140002e3b  jns     short loc_140002E47
0x140002e3d  mov     ebx, 7Ah ; 'z'
0x140002e42  jmp     loc_140002F20
0x140002e47  lea     r8, aSystem32Apploc_0; "\\System32\\AppLocker\\*.Applocker"
0x140002e4e  mov     edx, 20Ah; unsigned __int64
0x140002e53  lea     rcx, [rbp+5E0h+Buffer]; unsigned __int16 *
0x140002e5a  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140002e5f  test    eax, eax
0x140002e61  js      short loc_140002E3D
0x140002e63  lea     rdx, [rsp+6E0h+FindFileData]; lpFindFileData
0x140002e68  lea     rcx, [rbp+5E0h+Buffer]; lpFileName
0x140002e6f  call    cs:__imp_FindFirstFileW
0x140002e75  xor     ebx, ebx
0x140002e77  mov     rsi, rax
0x140002e7a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140002e7e  jz      loc_140002F20
0x140002e84  lea     r15d, [rbx+2Eh]
0x140002e88  cmp     [rsp+6E0h+FindFileData.cFileName], r15w
0x140002e8e  jz      short loc_140002EF5
0x140002e90  test    byte ptr [rsp+6E0h+FindFileData.dwFileAttributes], 10h
0x140002e95  jnz     short loc_140002EF5
0x140002e97  lea     rdx, SubStr; "."
0x140002e9e  lea     rcx, [rsp+6E0h+FindFileData.cFileName]; Str
0x140002ea3  call    cs:__imp_wcsstr
0x140002ea9  mov     rdi, rax
0x140002eac  test    rax, rax
0x140002eaf  jz      short loc_140002EF5
0x140002eb1  xor     ecx, ecx
0x140002eb3  mov     [rax], cx
0x140002eb6  test    r14, r14
0x140002eb9  jz      loc_140002F54
0x140002ebf  lea     rax, [rsp+6E0h+hKey]
0x140002ec4  mov     r9d, 20019h; samDesired
0x140002eca  xor     r8d, r8d; ulOptions
0x140002ecd  mov     [rsp+6E0h+phkResult], rax; phkResult
0x140002ed2  lea     rdx, [rsp+6E0h+FindFileData.cFileName]; lpSubKey
0x140002ed7  mov     rcx, r14; hKey
0x140002eda  call    cs:__imp_RegOpenKeyExW
0x140002ee0  mov     [rdi], r15w
0x140002ee4  mov     ebx, eax
0x140002ee6  test    eax, eax
0x140002ee8  jnz     short loc_140002F4D
0x140002eea  mov     rcx, [rsp+6E0h+hKey]; hKey
0x140002eef  call    cs:__imp_RegCloseKey
0x140002ef5  lea     rdx, [rsp+6E0h+FindFileData]; lpFindFileData
0x140002efa  mov     rcx, rsi; hFindFile
0x140002efd  call    cs:__imp_FindNextFileW
0x140002f03  test    eax, eax
0x140002f05  jnz     short loc_140002E88
0x140002f07  call    cs:__imp_GetLastError
0x140002f0d  mov     ebx, eax
0x140002f0f  xor     eax, eax
0x140002f11  cmp     ebx, 12h
0x140002f14  cmovz   ebx, eax
0x140002f17  mov     rcx, rsi; hFindFile
0x140002f1a  call    cs:__imp_FindClose
0x140002f20  mov     eax, ebx
0x140002f22  mov     rcx, [rbp+5E0h+var_30]
0x140002f29  xor     rcx, rsp; StackCookie
0x140002f2c  call    __security_check_cookie
0x140002f31  lea     r11, [rsp+6E0h+var_20]
0x140002f39  mov     rbx, [r11+38h]
0x140002f3d  mov     rsi, [r11+40h]
0x140002f41  mov     rsp, r11
0x140002f44  pop     r15
0x140002f46  pop     r14
0x140002f48  pop     r12
0x140002f4a  pop     rdi
0x140002f4b  pop     rbp
0x140002f4c  retn
0x140002f4d  cmp     eax, 2
0x140002f50  jnz     short loc_140002F17
0x140002f52  jmp     short loc_140002F5D
0x140002f54  mov     [rsp+6E0h+hKey], rcx
0x140002f59  mov     [rax], r15w
0x140002f5d  lea     r8, [rsp+6E0h+FindFileData.cFileName]; unsigned __int16 *
0x140002f62  mov     rdx, r12; unsigned __int64
0x140002f65  lea     rcx, [rbp+5E0h+FileName]; unsigned __int16 *
0x140002f6c  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140002f71  test    eax, eax
0x140002f73  js      short loc_140002FF3
0x140002f75  xor     edi, edi
0x140002f77  cmp     edi, 0Ah
0x140002f7a  jnb     loc_140002EF5
0x140002f80  lea     rcx, [rbp+5E0h+FileName]; lpFileName
0x140002f87  call    cs:__imp_DeleteFileW
0x140002f8d  test    eax, eax
0x140002f8f  jnz     loc_140002EF5
0x140002f95  call    cs:__imp_GetLastError
0x140002f9b  mov     ebx, eax
0x140002f9d  cmp     eax, 20h ; ' '
0x140002fa0  jnz     short loc_140002FB1
0x140002fa2  mov     ecx, 3E8h; dwMilliseconds
0x140002fa7  call    cs:__imp_Sleep
0x140002fad  inc     edi
0x140002faf  jmp     short loc_140002F77
0x140002fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140002fb8  lea     rax, WPP_GLOBAL_Control
0x140002fbf  cmp     rcx, rax
0x140002fc2  jz      loc_140002F17
0x140002fc8  test    dword ptr [rcx+1Ch], 800h
0x140002fcf  jz      loc_140002F17
0x140002fd5  mov     rcx, [rcx+10h]
0x140002fd9  lea     r9, [rbp+5E0h+FileName]
0x140002fe0  mov     edx, 3Ah ; ':'
0x140002fe5  mov     dword ptr [rsp+6E0h+phkResult], ebx
0x140002fe9  call    WPP_SF_Sd
0x140002fee  jmp     loc_140002F17
0x140002ff3  mov     ebx, 7Ah ; 'z'
0x140002ff8  jmp     loc_140002F17
```
