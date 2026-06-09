# CheckMdmPolicy(bool *)

- ea: `0x140002c74`
- end: `0x140002d8b`
- name: `?CheckMdmPolicy@@YAKPEA_N@Z`
- size: `279`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000458c`

## callees

- `0x140002c74`
- `0x1400059dc`
- `0x140013acf`
- `0x140013b10`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140002d30`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140002d30`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140002d0f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140002d0f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140002d63`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140002d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002cd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002d41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002cd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002d41`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x140002cce`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x140002cce`

## string_xrefs

- `0x140002ce0`: `\System32\AppLocker\MDM\*`

## pseudocode

```c
__int64 __fastcall CheckMdmPolicy(bool *a1)
{
  DWORD LastError; // eax
  unsigned int v3; // ebx
  HANDLE FirstFileW; // rax
  HANDLE hFindFile[2]; // [rsp+20h] [rbp-E0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[264]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  hFindFile[0] = (HANDLE)-1LL;
  hFindFile[1] = hFindFile;
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
LABEL_11:
    v3 = LastError;
    goto LABEL_15;
  }
  if ( StringCbCatW(Buffer, 0x20Au, L"\\System32\\AppLocker\\MDM\\*") >= 0 )
  {
    FirstFileW = FindFirstFileW(Buffer, &FindFileData);
    hFindFile[0] = FirstFileW;
    if ( FirstFileW != (HANDLE)-1LL )
    {
      while ( 1 )
      {
        if ( FindFileData.cFileName[0] != 46 )
        {
          *a1 = 1;
          goto LABEL_14;
        }
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
          break;
        FirstFileW = hFindFile[0];
      }
      LastError = GetLastError();
      if ( LastError != 18 )
      {
        if ( LastError )
          goto LABEL_11;
      }
    }
    *a1 = 0;
LABEL_14:
    v3 = 0;
  }
  else
  {
    v3 = 122;
  }
LABEL_15:
  FindClose(hFindFile[0]);
  return v3;
}

```

## disassembly

```asm
0x140002c74  mov     [rsp-8+arg_8], rbx
0x140002c79  push    rbp
0x140002c7a  lea     rbp, [rsp-3A0h]
0x140002c82  sub     rsp, 4A0h
0x140002c89  mov     rax, cs:__security_cookie
0x140002c90  xor     rax, rsp
0x140002c93  mov     [rbp+3A0h+var_10], rax
0x140002c9a  mov     rbx, rcx
0x140002c9d  xor     edx, edx; Val
0x140002c9f  mov     r8d, 250h; Size
0x140002ca5  lea     rcx, [rsp+4A0h+FindFileData]; void *
0x140002caa  call    memset_0
0x140002caf  mov     [rsp+4A0h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x140002cb8  lea     rax, [rsp+4A0h+hFindFile]
0x140002cbd  mov     [rsp+4A0h+var_478], rax
0x140002cc2  mov     edx, 104h; uSize
0x140002cc7  lea     rcx, [rbp+3A0h+Buffer]; lpBuffer
0x140002cce  call    cs:__imp_GetWindowsDirectoryW
0x140002cd4  test    eax, eax
0x140002cd6  jnz     short loc_140002CE0
0x140002cd8  call    cs:__imp_GetLastError
0x140002cde  jmp     short loc_140002D50
0x140002ce0  lea     r8, aSystem32Apploc; "\\System32\\AppLocker\\MDM\\*"
0x140002ce7  mov     edx, 20Ah; unsigned __int64
0x140002cec  lea     rcx, [rbp+3A0h+Buffer]; unsigned __int16 *
0x140002cf3  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140002cf8  test    eax, eax
0x140002cfa  jns     short loc_140002D03
0x140002cfc  mov     ebx, 7Ah ; 'z'
0x140002d01  jmp     short loc_140002D5E
0x140002d03  lea     rdx, [rsp+4A0h+FindFileData]; lpFindFileData
0x140002d08  lea     rcx, [rbp+3A0h+Buffer]; lpFileName
0x140002d0f  call    cs:__imp_FindFirstFileW
0x140002d15  mov     [rsp+4A0h+hFindFile], rax
0x140002d1a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140002d1e  jz      short loc_140002D59
0x140002d20  cmp     [rsp+4A0h+FindFileData.cFileName], 2Eh ; '.'
0x140002d26  jnz     short loc_140002D54
0x140002d28  lea     rdx, [rsp+4A0h+FindFileData]; lpFindFileData
0x140002d2d  mov     rcx, rax; hFindFile
0x140002d30  call    cs:__imp_FindNextFileW
0x140002d36  test    eax, eax
0x140002d38  jz      short loc_140002D41
0x140002d3a  mov     rax, [rsp+4A0h+hFindFile]
0x140002d3f  jmp     short loc_140002D20
0x140002d41  call    cs:__imp_GetLastError
0x140002d47  cmp     eax, 12h
0x140002d4a  jz      short loc_140002D59
0x140002d4c  test    eax, eax
0x140002d4e  jz      short loc_140002D59
0x140002d50  mov     ebx, eax
0x140002d52  jmp     short loc_140002D5E
0x140002d54  mov     byte ptr [rbx], 1
0x140002d57  jmp     short loc_140002D5C
0x140002d59  mov     byte ptr [rbx], 0
0x140002d5c  xor     ebx, ebx
0x140002d5e  mov     rcx, [rsp+4A0h+hFindFile]; hFindFile
0x140002d63  call    cs:__imp_FindClose
0x140002d69  mov     eax, ebx
0x140002d6b  mov     rcx, [rbp+3A0h+var_10]
0x140002d72  xor     rcx, rsp; StackCookie
0x140002d75  call    __security_check_cookie
0x140002d7a  mov     rbx, [rsp+4A0h+arg_8]
0x140002d82  add     rsp, 4A0h
0x140002d89  pop     rbp
0x140002d8a  retn
```
