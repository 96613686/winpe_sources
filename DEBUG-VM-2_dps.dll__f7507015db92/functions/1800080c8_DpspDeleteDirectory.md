# DpspDeleteDirectory

- ea: `0x1800080c8`
- end: `0x1800082a0`
- name: `DpspDeleteDirectory`
- size: `472`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800080c8`
- `0x1800082a8`

## callees

- `0x1800080c8`
- `0x180009090`
- `0x180009fb0`
- `0x180009ff0`
- `0x18000a856`
- `0x18000c93c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180008286`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180008286`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000827d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000827d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800081dd`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800081dd`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000828f`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000828f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180008270`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180008270`

## string_xrefs

- `0x180008128`: `DpspDeleteDirectory`

## pseudocode

```c
errno_t __fastcall DpspDeleteDirectory(_WORD *a1)
{
  errno_t result; // eax
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rcx
  HANDLE FirstFileW; // rax
  void *v6; // rsi
  unsigned __int64 v7; // rbx
  __int64 v8; // r9
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Destination[264]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 )
    return WdipTraceError(
             (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
             (int)L"DpspDeleteDirectory",
             484,
             (int)L"Error = %d",
             87);
  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  if ( v3 >= 0x101 )
    return WdipTraceError(
             (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
             (int)L"DpspDeleteDirectory",
             489,
             (int)L"Error = %d",
             22);
  result = memcpy_s(Destination, 0x104u, a1, 2 * v3);
  if ( !result )
  {
    v4 = 2 * v3 + 4;
    *(_DWORD *)&Destination[v3] = 2752604;
    if ( v4 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)Destination + v4) = 0;
    FirstFileW = FindFirstFileW(Destination, &FindFileData);
    v6 = FirstFileW;
    if ( FirstFileW )
    {
      v7 = v3 + 1;
      if ( FirstFileW != (HANDLE)-1LL )
      {
        do
        {
          if ( FindFileData.cFileName[0] != 46
            || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
          {
            v8 = -1;
            do
              ++v8;
            while ( FindFileData.cFileName[v8] );
            memcpy_s(&Destination[v7], 260 - v7, FindFileData.cFileName, 2 * v8 + 2);
            DpspDeleteDirectory(Destination);
          }
        }
        while ( FindNextFileW(v6, &FindFileData) );
        FindClose(v6);
      }
    }
    DeleteFileW(a1);
    return RemoveDirectoryW(a1);
  }
  return result;
}

```

## disassembly

```asm
0x1800080c8  mov     [rsp-8+arg_8], rbx
0x1800080cd  mov     [rsp-8+arg_10], rsi
0x1800080d2  push    rbp
0x1800080d3  push    rdi
0x1800080d4  push    r14
0x1800080d6  lea     rbp, [rsp-3A0h]
0x1800080de  sub     rsp, 4A0h
0x1800080e5  mov     rax, cs:__security_cookie
0x1800080ec  xor     rax, rsp
0x1800080ef  mov     [rbp+3B0h+var_20], rax
0x1800080f6  mov     rdi, rcx
0x1800080f9  xor     edx, edx; Val
0x1800080fb  lea     rcx, [rsp+4B0h+FindFileData]; void *
0x180008100  mov     r8d, 250h; Size
0x180008106  call    memset_0
0x18000810b  xor     r14d, r14d
0x18000810e  test    rdi, rdi
0x180008111  jnz     short loc_180008162
0x180008113  mov     dword ptr [rsp+4B0h+Args], 57h ; 'W'; Args
0x18000811b  mov     r8d, 1E4h; int
0x180008121  lea     r9, aErrorD; "Error = %d"
0x180008128  lea     rdx, aDpspdeletedire; "DpspDeleteDirectory"
0x18000812f  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180008136  call    WdipTraceError
0x18000813b  mov     rcx, [rbp+3B0h+var_20]
0x180008142  xor     rcx, rsp; StackCookie
0x180008145  call    __security_check_cookie
0x18000814a  lea     r11, [rsp+4B0h+var_10]
0x180008152  mov     rbx, [r11+28h]
0x180008156  mov     rsi, [r11+30h]
0x18000815a  mov     rsp, r11
0x18000815d  pop     r14
0x18000815f  pop     rdi
0x180008160  pop     rbp
0x180008161  retn
0x180008162  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008166  inc     rbx
0x180008169  cmp     [rdi+rbx*2], r14w
0x18000816e  jnz     short loc_180008166
0x180008170  cmp     rbx, 101h
0x180008177  jb      short loc_180008189
0x180008179  mov     dword ptr [rsp+4B0h+Args], 216h
0x180008181  mov     r8d, 1E9h
0x180008187  jmp     short loc_180008121
0x180008189  lea     rsi, [rbx+rbx]
0x18000818d  mov     r8, rdi; Source
0x180008190  mov     r9, rsi; SourceSize
0x180008193  lea     rcx, [rbp+3B0h+Destination]; Destination
0x18000819a  mov     edx, 104h; DestinationSize
0x18000819f  call    memcpy_s
0x1800081a4  test    eax, eax
0x1800081a6  jnz     short loc_18000813B
0x1800081a8  lea     rcx, ds:4[rbx*2]
0x1800081b0  mov     dword ptr [rbp+rsi+3B0h+Destination], 2A005Ch
0x1800081bb  cmp     rcx, 208h
0x1800081c2  jnb     loc_18000829A
0x1800081c8  mov     [rbp+rcx+3B0h+Destination], r14w
0x1800081d1  lea     rdx, [rsp+4B0h+FindFileData]; lpFindFileData
0x1800081d6  lea     rcx, [rbp+3B0h+Destination]; lpFileName
0x1800081dd  call    cs:__imp_FindFirstFileW
0x1800081e3  mov     rsi, rax
0x1800081e6  test    rax, rax
0x1800081e9  jz      loc_180008283
0x1800081ef  inc     rbx
0x1800081f2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800081f6  jz      loc_180008283
0x1800081fc  cmp     [rsp+4B0h+FindFileData.cFileName], 2Eh ; '.'
0x180008202  movzx   eax, [rsp+4B0h+FindFileData.cFileName+2]
0x180008207  jnz     short loc_180008224
0x180008209  test    ax, ax
0x18000820c  jz      short loc_180008268
0x18000820e  cmp     [rsp+4B0h+FindFileData.cFileName], 2Eh ; '.'
0x180008214  jnz     short loc_180008224
0x180008216  cmp     ax, 2Eh ; '.'
0x18000821a  jnz     short loc_180008224
0x18000821c  cmp     [rsp+4B0h+FindFileData.cFileName+4], r14w
0x180008222  jz      short loc_180008268
0x180008224  lea     rax, [rsp+4B0h+FindFileData.cFileName]
0x180008229  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000822d  inc     r9
0x180008230  cmp     [rax+r9*2], r14w
0x180008235  jnz     short loc_18000822D
0x180008237  mov     edx, 104h
0x18000823c  lea     rcx, [rbp+3B0h+Destination]
0x180008243  sub     rdx, rbx; DestinationSize
0x180008246  lea     rcx, [rcx+rbx*2]; Destination
0x18000824a  lea     r9, ds:2[r9*2]; SourceSize
0x180008252  lea     r8, [rsp+4B0h+FindFileData.cFileName]; Source
0x180008257  call    memcpy_s
0x18000825c  lea     rcx, [rbp+3B0h+Destination]
0x180008263  call    DpspDeleteDirectory
0x180008268  lea     rdx, [rsp+4B0h+FindFileData]; lpFindFileData
0x18000826d  mov     rcx, rsi; hFindFile
0x180008270  call    cs:__imp_FindNextFileW
0x180008276  test    eax, eax
0x180008278  jnz     short loc_1800081FC
0x18000827a  mov     rcx, rsi; hFindFile
0x18000827d  call    cs:__imp_FindClose
0x180008283  mov     rcx, rdi; lpFileName
0x180008286  call    cs:__imp_DeleteFileW
0x18000828c  mov     rcx, rdi; lpPathName
0x18000828f  call    cs:__imp_RemoveDirectoryW
0x180008295  jmp     loc_18000813B
0x18000829a  call    __report_rangecheckfailure
```
