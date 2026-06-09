# PrintCore::IppPrinterAttributesCache::GetPrinterAttributesCache(std::vector<PrintCore::IppAttribute,std::allocator<PrintCore::IppAttribute>> &)

- ea: `0x180044700`
- end: `0x1800448f5`
- name: `?GetPrinterAttributesCache@IppPrinterAttributesCache@PrintCore@@QEAAJAEAV?$vector@VIppAttribute@PrintCore@@V?$allocator@VIppAttribute@PrintCore@@@std@@@std@@@Z`
- size: `501`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800421f4`
- `0x180043f48`

## callees

- `0x18000b274`
- `0x18000f6a0`
- `0x180018b44`
- `0x18002025c`
- `0x18002c8b4`
- `0x180039928`
- `0x18003d8b4`
- `0x18003f318`
- `0x180044700`

## import_xrefs

- `KERNEL32!GetFileSize` at `0x1800447e2`
- `KERNEL32!GetFileSize` at `0x1800447e2`
- `KERNEL32!ReadFile` at `0x180044820`
- `KERNEL32!ReadFile` at `0x180044820`
- `KERNEL32!CreateFileW` at `0x180044762`
- `KERNEL32!CreateFileW` at `0x180044762`
- `KERNEL32!CloseHandle` at `0x180044792`
- `KERNEL32!CloseHandle` at `0x1800447c3`
- `KERNEL32!CloseHandle` at `0x180044843`
- `KERNEL32!CloseHandle` at `0x180044792`
- `KERNEL32!CloseHandle` at `0x1800447c3`
- `KERNEL32!CloseHandle` at `0x180044843`
- `KERNEL32!GetLastError` at `0x18004477a`
- `KERNEL32!GetLastError` at `0x18004477a`

## string_xrefs

- `0x1800447a3`: `OneCoreUap\Internal\PrintScan\inc\ippprinterattributescache.hxx`
- `0x1800448bf`: `OneCoreUap\Internal\PrintScan\inc\ippprinterattributescache.hxx`
- `0x1800448d1`: `OneCoreUap\Internal\PrintScan\inc\ippprinterattributescache.hxx`
- `0x1800448e3`: `OneCoreUap\Internal\PrintScan\inc\ippprinterattributescache.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PrintCore::IppPrinterAttributesCache::GetPrinterAttributesCache(__int64 a1, _QWORD *a2)
{
  const WCHAR *v3; // rcx
  char *FileW; // rbx
  const char *v5; // r9
  int LastError; // edi
  DWORD FileSize; // edi
  const char *v9; // r9
  const char *v10; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-60h]
  LPVOID lpBuffer[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v13; // [rsp+58h] [rbp-28h]
  _BYTE v14[8]; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v15[3]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  DWORD NumberOfBytesRead; // [rsp+A0h] [rbp+20h] BYREF
  int v18; // [rsp+B0h] [rbp+30h] BYREF
  char *v19; // [rsp+B8h] [rbp+38h]

  *(_OWORD *)lpBuffer = 0;
  v13 = 0;
  v3 = (const WCHAR *)(a1 + 8);
  if ( *((_QWORD *)v3 + 3) > 7u )
    v3 = *(const WCHAR **)v3;
  FileW = (char *)CreateFileW(v3, 0x80000000, 1u, 0, 3u, 0x100000u, 0);
  v19 = FileW;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    FileSize = GetFileSize(FileW, 0);
    if ( FileSize == -1 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x40,
        (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\ippprinterattributescache.hxx",
        v9);
    std::vector<unsigned char>::resize(lpBuffer, FileSize);
    NumberOfBytesRead = 0;
    if ( !ReadFile(FileW, lpBuffer[0], FileSize, &NumberOfBytesRead, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x43,
        (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\ippprinterattributescache.hxx",
        v10);
    if ( NumberOfBytesRead != FileSize )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\ippprinterattributescache.hxx",
        (const char *)0x8000FFFFLL,
        dwCreationDisposition);
    CloseHandle(FileW);
  }
  else
  {
    if ( GetLastError() == 2 )
    {
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(FileW);
      LastError = -2147024894;
LABEL_11:
      std::vector<char>::~vector<char>(lpBuffer);
      return (unsigned int)LastError;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x3D,
                  (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\ippprinterattributescache.hxx",
                  v5);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    if ( LastError < 0 )
      goto LABEL_11;
  }
  v18 = 0;
  PrintCore::IppAttributeGroup::IppAttributeGroup(v14, lpBuffer, &v18);
  if ( a2 != v15 )
    std::vector<PrintCore::IppAttribute>::_Assign_counted_range<PrintCore::IppAttribute *>(
      a2,
      v15[0],
      0x6DB6DB6DB6DB6DB7LL * ((__int64)(v15[1] - v15[0]) >> 3));
  std::vector<PrintCore::IppAttribute>::~vector<PrintCore::IppAttribute>(v15);
  std::vector<char>::~vector<char>(lpBuffer);
  return 0;
}

```

## disassembly

```asm
0x180044700  mov     rax, rsp
0x180044703  push    rbp
0x180044704  push    rsi
0x180044705  push    rdi
0x180044706  mov     rbp, rsp
0x180044709  sub     rsp, 80h
0x180044710  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x180044718  mov     [rax+10h], rbx
0x18004471c  mov     rsi, rdx
0x18004471f  xorps   xmm0, xmm0
0x180044722  movdqu  xmmword ptr [rbp+lpBuffer], xmm0
0x180044727  mov     [rbp+var_28], 0
0x18004472f  add     rcx, 8
0x180044733  cmp     qword ptr [rcx+18h], 7
0x180044738  jbe     short loc_18004473D
0x18004473a  mov     rcx, [rcx]; lpFileName
0x18004473d  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x180044746  mov     [rsp+80h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x18004474e  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x180044756  xor     r9d, r9d; lpSecurityAttributes
0x180044759  mov     edx, 80000000h; dwDesiredAccess
0x18004475e  lea     r8d, [r9+1]; dwShareMode
0x180044762  call    cs:__imp_CreateFileW
0x180044768  mov     rbx, rax
0x18004476b  mov     [rbp+arg_18], rax
0x18004476f  inc     rax
0x180044772  test    rax, 0FFFFFFFFFFFFFFFEh
0x180044778  jnz     short loc_1800447DD
0x18004477a  call    cs:__imp_GetLastError
0x180044780  cmp     eax, 2
0x180044783  jnz     short loc_18004479F
0x180044785  lea     rax, [rbx-1]
0x180044789  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004478d  ja      short loc_180044798
0x18004478f  mov     rcx, rbx; hObject
0x180044792  call    cs:__imp_CloseHandle
0x180044798  mov     edi, 80070002h
0x18004479d  jmp     short loc_1800447CD
0x18004479f  mov     rcx, [rbp+18h]; this
0x1800447a3  lea     r8, aOnecoreuapInte_2; "OneCoreUap\\Internal\\PrintScan\\inc\\i"...
0x1800447aa  mov     edx, 3Dh ; '='; void *
0x1800447af  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800447b4  mov     edi, eax
0x1800447b6  lea     rax, [rbx-1]
0x1800447ba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800447be  ja      short loc_1800447C9
0x1800447c0  mov     rcx, rbx; hObject
0x1800447c3  call    cs:__imp_CloseHandle
0x1800447c9  test    edi, edi
0x1800447cb  jns     short loc_180044849
0x1800447cd  lea     rcx, [rbp+lpBuffer]
0x1800447d1  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800447d6  mov     eax, edi
0x1800447d8  jmp     loc_1800448A6
0x1800447dd  xor     edx, edx; lpFileSizeHigh
0x1800447df  mov     rcx, rbx; hFile
0x1800447e2  call    cs:__imp_GetFileSize
0x1800447e8  mov     edi, eax
0x1800447ea  mov     rcx, [rbp+18h]; this
0x1800447ee  cmp     eax, 0FFFFFFFFh
0x1800447f1  jz      loc_1800448D1
0x1800447f7  mov     edx, edi
0x1800447f9  lea     rcx, [rbp+lpBuffer]
0x1800447fd  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180044802  mov     [rbp+NumberOfBytesRead], 0
0x180044809  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; int
0x180044812  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180044816  mov     r8d, edi; nNumberOfBytesToRead
0x180044819  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x18004481d  mov     rcx, rbx; hFile
0x180044820  call    cs:__imp_ReadFile
0x180044826  mov     rcx, [rbp+18h]; this
0x18004482a  test    eax, eax
0x18004482c  jz      loc_1800448E3
0x180044832  cmp     [rbp+NumberOfBytesRead], edi
0x180044835  setnz   al
0x180044838  mov     rcx, [rbp+18h]; this
0x18004483c  test    al, al
0x18004483e  jnz     short loc_1800448B9
0x180044840  mov     rcx, rbx; hObject
0x180044843  call    cs:__imp_CloseHandle
0x180044849  mov     [rbp+arg_10], 0
0x180044850  lea     r8, [rbp+arg_10]
0x180044854  lea     rdx, [rbp+lpBuffer]
0x180044858  lea     rcx, [rbp+var_20]
0x18004485c  call    ??0IppAttributeGroup@PrintCore@@QEAA@AEAV?$vector@EV?$allocator@E@std@@@std@@AEAK@Z; PrintCore::IppAttributeGroup::IppAttributeGroup(std::vector<uchar> &,ulong &)
0x180044861  nop
0x180044862  lea     rax, [rbp+var_18]
0x180044866  cmp     rsi, rax
0x180044869  jz      short loc_180044891
0x18004486b  mov     rdx, [rbp+var_18]
0x18004486f  mov     r8, [rbp+var_10]
0x180044873  sub     r8, rdx
0x180044876  sar     r8, 3
0x18004487a  mov     rax, 6DB6DB6DB6DB6DB7h
0x180044884  imul    r8, rax
0x180044888  mov     rcx, rsi
0x18004488b  call    ??$_Assign_counted_range@PEAVIppAttribute@PrintCore@@@?$vector@VIppAttribute@PrintCore@@V?$allocator@VIppAttribute@PrintCore@@@std@@@std@@AEAAXPEAVIppAttribute@PrintCore@@_K@Z; std::vector<PrintCore::IppAttribute>::_Assign_counted_range<PrintCore::IppAttribute *>(PrintCore::IppAttribute *,unsigned __int64)
0x180044890  nop
0x180044891  lea     rcx, [rbp+var_18]
0x180044895  call    ??1?$vector@VIppAttribute@PrintCore@@V?$allocator@VIppAttribute@PrintCore@@@std@@@std@@QEAA@XZ; std::vector<PrintCore::IppAttribute>::~vector<PrintCore::IppAttribute>(void)
0x18004489a  nop
0x18004489b  lea     rcx, [rbp+lpBuffer]
0x18004489f  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800448a4  xor     eax, eax
0x1800448a6  mov     rbx, [rsp+80h+arg_8]
0x1800448ae  add     rsp, 80h
0x1800448b5  pop     rdi
0x1800448b6  pop     rsi
0x1800448b7  pop     rbp
0x1800448b8  retn
0x1800448b9  mov     r9d, 8000FFFFh; char *
0x1800448bf  lea     r8, aOnecoreuapInte_2; "OneCoreUap\\Internal\\PrintScan\\inc\\i"...
0x1800448c6  mov     edx, 44h ; 'D'; void *
0x1800448cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800448d1  lea     r8, aOnecoreuapInte_2; "OneCoreUap\\Internal\\PrintScan\\inc\\i"...
0x1800448d8  mov     edx, 40h ; '@'; void *
0x1800448dd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800448e3  lea     r8, aOnecoreuapInte_2; "OneCoreUap\\Internal\\PrintScan\\inc\\i"...
0x1800448ea  mov     edx, 43h ; 'C'; void *
0x1800448ef  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
