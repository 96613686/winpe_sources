# mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::load_from_file(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140039f5c`
- end: `0x14003a147`
- name: `?load_from_file@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKAEBV12@@Z`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1400335dc`

## callees

- `0x14000350c`
- `0x140003611`
- `0x140006fac`
- `0x140015854`
- `0x140016588`
- `0x1400197b4`
- `0x140039f5c`
- `0x140113220`

## import_xrefs

- `KERNEL32!ReadFile` at `0x14003a09e`
- `KERNEL32!ReadFile` at `0x14003a09e`
- `KERNEL32!FindFirstFileW` at `0x140039fce`
- `KERNEL32!FindFirstFileW` at `0x140039fce`
- `KERNEL32!FindClose` at `0x140039ff6`
- `KERNEL32!FindClose` at `0x140039ff6`
- `KERNEL32!CreateFileW` at `0x14003a050`
- `KERNEL32!CreateFileW` at `0x14003a050`
- `KERNEL32!CloseHandle` at `0x14003a0b3`
- `KERNEL32!CloseHandle` at `0x14003a113`
- `KERNEL32!CloseHandle` at `0x14003a0b3`
- `KERNEL32!CloseHandle` at `0x14003a113`
- `KERNEL32!GetLastError` at `0x140039fda`
- `KERNEL32!GetLastError` at `0x14003a0a8`
- `KERNEL32!GetLastError` at `0x140039fda`
- `KERNEL32!GetLastError` at `0x14003a0a8`
- `KERNEL32!SetLastError` at `0x140039fa0`
- `KERNEL32!SetLastError` at `0x14003a01b`
- `KERNEL32!SetLastError` at `0x140039fa0`
- `KERNEL32!SetLastError` at `0x14003a01b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::load_from_file(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v4; // rbx
  DWORD LastError; // ebx
  HANDLE FirstFileW; // rax
  __int16 dwFileAttributes; // bx
  HANDLE FileW; // rsi
  __int64 v10; // r8
  _QWORD *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-2B8h] BYREF
  __int64 v15; // [rsp+48h] [rbp-2B0h]
  _BYTE pExceptionObject[24]; // [rsp+50h] [rbp-2A8h] BYREF
  _BYTE v17[40]; // [rsp+68h] [rbp-290h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-268h] BYREF

  v15 = a1;
  v4 = *(_QWORD **)a2;
  if ( !**(_QWORD **)a2 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(a1);
    LastError = 87;
LABEL_3:
    SetLastError(LastError);
    return LastError;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW((LPCWSTR)v4[3], &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    goto LABEL_5;
  dwFileAttributes = FindFileData.dwFileAttributes;
  FindClose(FirstFileW);
  if ( (dwFileAttributes & 0x1010) != 0 )
    goto LABEL_5;
  if ( FindFileData.nFileSizeHigh )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(a1);
    SetLastError(0xEu);
    return 14;
  }
  FileW = CreateFileW(*(LPCWSTR *)(*(_QWORD *)a2 + 24LL), 1u, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
LABEL_5:
    LastError = GetLastError();
LABEL_6:
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(a1);
    goto LABEL_3;
  }
  try
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::resize(
      a1,
      (unsigned __int64)FindFileData.nFileSizeLow >> 1);
  }
  catch ( ... )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(v15);
    SetLastError(0xEu);
    return 14;
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(FileW, *(LPVOID *)(*(_QWORD *)a1 + 24LL), FindFileData.nFileSizeLow, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    CloseHandle(FileW);
    goto LABEL_6;
  }
  v11 = *(_QWORD **)a1;
  v12 = *(_QWORD *)(*(_QWORD *)a1 + 24LL);
  if ( v12 )
  {
    if ( *v11 > v11[1] )
    {
      v13 = mlib::_msrse_(v17, "at is larger than buffer size", v10, 1000);
      std::out_of_range::out_of_range(pExceptionObject, v13);
      throw (std::out_of_range *)pExceptionObject;
    }
    *(_WORD *)(v12 + 2LL * *v11) = 0;
  }
  CloseHandle(FileW);
  return 0;
}

```

## disassembly

```asm
0x140039f5c  mov     [rsp+arg_10], rbx
0x140039f61  mov     [rsp+arg_18], rsi
0x140039f66  push    rdi
0x140039f67  sub     rsp, 2F0h
0x140039f6e  mov     rax, cs:__security_cookie
0x140039f75  xor     rax, rsp
0x140039f78  mov     [rsp+2F8h+var_18], rax
0x140039f80  mov     rsi, rdx
0x140039f83  mov     rdi, rcx
0x140039f86  mov     [rsp+2F8h+var_2B0], rcx
0x140039f8b  mov     rbx, [rdx]
0x140039f8e  cmp     qword ptr [rbx], 0
0x140039f92  jnz     short loc_140039FAD
0x140039f94  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x140039f99  mov     ebx, 57h ; 'W'
0x140039f9e  mov     ecx, ebx; dwErrCode
0x140039fa0  call    cs:__imp_SetLastError
0x140039fa6  mov     eax, ebx
0x140039fa8  jmp     loc_14003A122
0x140039fad  xor     edx, edx; Val
0x140039faf  mov     r8d, 250h; Size
0x140039fb5  lea     rcx, [rsp+2F8h+FindFileData]; void *
0x140039fbd  call    memset_0
0x140039fc2  lea     rdx, [rsp+2F8h+FindFileData]; lpFindFileData
0x140039fca  mov     rcx, [rbx+18h]; lpFileName
0x140039fce  call    cs:__imp_FindFirstFileW
0x140039fd4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140039fd8  jnz     short loc_140039FEC
0x140039fda  call    cs:__imp_GetLastError
0x140039fe0  mov     ebx, eax
0x140039fe2  mov     rcx, rdi
0x140039fe5  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x140039fea  jmp     short loc_140039F9E
0x140039fec  mov     ebx, [rsp+2F8h+FindFileData.dwFileAttributes]
0x140039ff3  mov     rcx, rax; hFindFile
0x140039ff6  call    cs:__imp_FindClose
0x140039ffc  test    ebx, 1010h
0x14003a002  jnz     short loc_140039FDA
0x14003a004  cmp     [rsp+2F8h+FindFileData.nFileSizeHigh], 0
0x14003a00c  jz      short loc_14003A026
0x14003a00e  mov     rcx, rdi
0x14003a011  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x14003a016  mov     ecx, 0Eh; dwErrCode
0x14003a01b  call    cs:__imp_SetLastError
0x14003a021  jmp     loc_14003A11D
0x14003a026  mov     rcx, [rsi]
0x14003a029  mov     [rsp+2F8h+hTemplateFile], 0; hTemplateFile
0x14003a032  mov     [rsp+2F8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14003a03a  mov     [rsp+2F8h+dwCreationDisposition], 3; dwCreationDisposition
0x14003a042  xor     r9d, r9d; lpSecurityAttributes
0x14003a045  lea     edx, [r9+1]; dwDesiredAccess
0x14003a049  mov     r8d, edx; dwShareMode
0x14003a04c  mov     rcx, [rcx+18h]; lpFileName
0x14003a050  call    cs:__imp_CreateFileW
0x14003a056  mov     rsi, rax
0x14003a059  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14003a05d  jz      loc_140039FDA
0x14003a063  mov     edx, [rsp+2F8h+FindFileData.nFileSizeLow]
0x14003a06a  shr     rdx, 1
0x14003a06d  mov     rcx, rdi
0x14003a070  call    ?resize@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAX_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::resize(unsigned __int64)
0x14003a075  nop
0x14003a076  mov     [rsp+2F8h+NumberOfBytesRead], 0
0x14003a07e  mov     rdx, [rdi]
0x14003a081  mov     qword ptr [rsp+2F8h+dwCreationDisposition], 0; lpOverlapped
0x14003a08a  lea     r9, [rsp+2F8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14003a08f  mov     r8d, [rsp+2F8h+FindFileData.nFileSizeLow]; nNumberOfBytesToRead
0x14003a097  mov     rdx, [rdx+18h]; lpBuffer
0x14003a09b  mov     rcx, rsi; hFile
0x14003a09e  call    cs:__imp_ReadFile
0x14003a0a4  test    eax, eax
0x14003a0a6  jnz     short loc_14003A0BE
0x14003a0a8  call    cs:__imp_GetLastError
0x14003a0ae  mov     ebx, eax
0x14003a0b0  mov     rcx, rsi; hObject
0x14003a0b3  call    cs:__imp_CloseHandle
0x14003a0b9  jmp     loc_140039FE2
0x14003a0be  mov     rax, [rdi]
0x14003a0c1  mov     rdx, [rax+18h]
0x14003a0c5  test    rdx, rdx
0x14003a0c8  jz      short loc_14003A110
0x14003a0ca  mov     rcx, [rax]
0x14003a0cd  cmp     rcx, [rax+8]
0x14003a0d1  jbe     short loc_14003A10A
0x14003a0d3  mov     r9d, 3E8h
0x14003a0d9  lea     rdx, aAtIsLargerThan; "at is larger than buffer size"
0x14003a0e0  lea     rcx, [rsp+2F8h+var_290]
0x14003a0e5  call    ?_msrse_@mlib@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD0H@Z; mlib::_msrse_(char const *,char const *,int)
0x14003a0ea  nop
0x14003a0eb  mov     rdx, rax
0x14003a0ee  lea     rcx, [rsp+2F8h+pExceptionObject]
0x14003a0f3  call    ??0out_of_range@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::out_of_range::out_of_range(std::string const &)
0x14003a0f8  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x14003a0ff  lea     rcx, [rsp+2F8h+pExceptionObject]; pExceptionObject
0x14003a104  call    _CxxThrowException_0
0x14003a10a  xor     eax, eax
0x14003a10c  mov     [rdx+rcx*2], ax
0x14003a110  mov     rcx, rsi; hObject
0x14003a113  call    cs:__imp_CloseHandle
0x14003a119  xor     eax, eax
0x14003a11b  jmp     short loc_14003A122
0x14003a11d  mov     eax, 0Eh
0x14003a122  mov     rcx, [rsp+2F8h+var_18]
0x14003a12a  xor     rcx, rsp; StackCookie
0x14003a12d  call    __security_check_cookie
0x14003a132  lea     r11, [rsp+2F8h+var_8]
0x14003a13a  mov     rbx, [r11+20h]
0x14003a13e  mov     rsi, [r11+28h]
0x14003a142  mov     rsp, r11
0x14003a145  pop     rdi
0x14003a146  retn
```
