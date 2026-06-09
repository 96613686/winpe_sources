# PrintCore::IppPrinterAttributesCache::GetPrinterAttributesCache(std::vector<PrintCore::IppAttribute,std::allocator<PrintCore::IppAttribute>> &)

- ea: `0x18004619c`
- end: `0x1800463c4`
- name: `?GetPrinterAttributesCache@IppPrinterAttributesCache@PrintCore@@QEAAJAEAV?$vector@VIppAttribute@PrintCore@@V?$allocator@VIppAttribute@PrintCore@@@std@@@std@@@Z`
- size: `552`
- prototype: `__int64 __fastcall(__int64, PrintCore::IppAttribute **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180043ae0`
- `0x18004599c`

## callees

- `0x18000b444`
- `0x18000fb68`
- `0x18001973c`
- `0x180020c8c`
- `0x18002dbc8`
- `0x18003aeec`
- `0x18003eee4`
- `0x180040a68`
- `0x18004619c`

## import_xrefs

- `KERNEL32!GetFileSize` at `0x18004629a`
- `KERNEL32!GetFileSize` at `0x18004629a`
- `KERNEL32!ReadFile` at `0x1800462de`
- `KERNEL32!ReadFile` at `0x1800462de`
- `KERNEL32!CreateFileW` at `0x1800461fe`
- `KERNEL32!CreateFileW` at `0x1800461fe`
- `KERNEL32!CloseHandle` at `0x18004623a`
- `KERNEL32!CloseHandle` at `0x180046271`
- `KERNEL32!CloseHandle` at `0x18004630b`
- `KERNEL32!CloseHandle` at `0x18004623a`
- `KERNEL32!CloseHandle` at `0x180046271`
- `KERNEL32!CloseHandle` at `0x18004630b`
- `KERNEL32!GetLastError` at `0x18004621c`
- `KERNEL32!GetLastError` at `0x18004621c`

## string_xrefs

- `0x180046251`: `OneCoreUap\Internal\PrintScan\inc\ippprinterattributescache.hxx`
- `0x18004638e`: `OneCoreUap\Internal\PrintScan\inc\ippprinterattributescache.hxx`
- `0x1800463a0`: `OneCoreUap\Internal\PrintScan\inc\ippprinterattributescache.hxx`
- `0x1800463b2`: `OneCoreUap\Internal\PrintScan\inc\ippprinterattributescache.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PrintCore::IppPrinterAttributesCache::GetPrinterAttributesCache(
        __int64 a1,
        PrintCore::IppAttribute **a2)
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
  __int64 v14; // [rsp+60h] [rbp-20h] BYREF
  const struct PrintCore::IppAttribute *v15[3]; // [rsp+68h] [rbp-18h] BYREF
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
        (__int64)"OneCoreUap\\Internal\\PrintScan\\inc\\ippprinterattributescache.hxx",
        v9);
    std::vector<unsigned char>::resize((__int64 *)lpBuffer, FileSize);
    NumberOfBytesRead = 0;
    if ( !ReadFile(FileW, lpBuffer[0], FileSize, &NumberOfBytesRead, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x43,
        (__int64)"OneCoreUap\\Internal\\PrintScan\\inc\\ippprinterattributescache.hxx",
        v10);
    if ( NumberOfBytesRead != FileSize )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        68,
        (__int64)"OneCoreUap\\Internal\\PrintScan\\inc\\ippprinterattributescache.hxx",
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
      std::vector<char>::~vector<char>((char **)lpBuffer);
      return (unsigned int)LastError;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x3D,
                  (int)"OneCoreUap\\Internal\\PrintScan\\inc\\ippprinterattributescache.hxx",
                  v5);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    if ( LastError < 0 )
      goto LABEL_11;
  }
  v18 = 0;
  PrintCore::IppAttributeGroup::IppAttributeGroup(&v14, (__int64)lpBuffer, (__int64)&v18);
  if ( a2 != v15 )
    std::vector<PrintCore::IppAttribute>::_Assign_counted_range<PrintCore::IppAttribute *>(
      a2,
      v15[0],
      0x6DB6DB6DB6DB6DB7LL * ((v15[1] - v15[0]) >> 3));
  std::vector<PrintCore::IppAttribute>::~vector<PrintCore::IppAttribute>((__int64)v15);
  std::vector<char>::~vector<char>((char **)lpBuffer);
  return 0;
}

```

## disassembly

```asm
0x18004619c  mov     rax, rsp
0x18004619f  push    rbp
0x1800461a0  push    rsi
0x1800461a1  push    rdi
0x1800461a2  mov     rbp, rsp
0x1800461a5  sub     rsp, 80h
0x1800461ac  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x1800461b4  mov     [rax+10h], rbx
0x1800461b8  mov     rsi, rdx
0x1800461bb  xorps   xmm0, xmm0
0x1800461be  movdqu  xmmword ptr [rbp+lpBuffer], xmm0
0x1800461c3  mov     [rbp+var_28], 0
0x1800461cb  add     rcx, 8
0x1800461cf  cmp     qword ptr [rcx+18h], 7
0x1800461d4  jbe     short loc_1800461D9
0x1800461d6  mov     rcx, [rcx]; lpFileName
0x1800461d9  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x1800461e2  mov     [rsp+80h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x1800461ea  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x1800461f2  xor     r9d, r9d; lpSecurityAttributes
0x1800461f5  mov     edx, 80000000h; dwDesiredAccess
0x1800461fa  lea     r8d, [r9+1]; dwShareMode
0x1800461fe  call    cs:__imp_CreateFileW
0x180046205  nop     dword ptr [rax+rax+00h]
0x18004620a  mov     rbx, rax
0x18004620d  mov     [rbp+arg_18], rax
0x180046211  inc     rax
0x180046214  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004621a  jnz     short loc_180046295
0x18004621c  call    cs:__imp_GetLastError
0x180046223  nop     dword ptr [rax+rax+00h]
0x180046228  cmp     eax, 2
0x18004622b  jnz     short loc_18004624D
0x18004622d  lea     rax, [rbx-1]
0x180046231  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180046235  ja      short loc_180046246
0x180046237  mov     rcx, rbx; hObject
0x18004623a  call    cs:__imp_CloseHandle
0x180046241  nop     dword ptr [rax+rax+00h]
0x180046246  mov     edi, 80070002h
0x18004624b  jmp     short loc_180046285
0x18004624d  mov     rcx, [rbp+18h]; this
0x180046251  lea     r8, aOnecoreuapInte_2; "OneCoreUap\\Internal\\PrintScan\\inc\\i"...
0x180046258  mov     edx, 3Dh ; '='; void *
0x18004625d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180046262  mov     edi, eax
0x180046264  lea     rax, [rbx-1]
0x180046268  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004626c  ja      short loc_18004627D
0x18004626e  mov     rcx, rbx; hObject
0x180046271  call    cs:__imp_CloseHandle
0x180046278  nop     dword ptr [rax+rax+00h]
0x18004627d  test    edi, edi
0x18004627f  jns     loc_180046317
0x180046285  lea     rcx, [rbp+lpBuffer]
0x180046289  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18004628e  mov     eax, edi
0x180046290  jmp     loc_180046374
0x180046295  xor     edx, edx; lpFileSizeHigh
0x180046297  mov     rcx, rbx; hFile
0x18004629a  call    cs:__imp_GetFileSize
0x1800462a1  nop     dword ptr [rax+rax+00h]
0x1800462a6  mov     edi, eax
0x1800462a8  mov     rcx, [rbp+18h]; this
0x1800462ac  cmp     eax, 0FFFFFFFFh
0x1800462af  jz      loc_1800463A0
0x1800462b5  mov     edx, edi
0x1800462b7  lea     rcx, [rbp+lpBuffer]
0x1800462bb  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800462c0  mov     [rbp+NumberOfBytesRead], 0
0x1800462c7  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; int
0x1800462d0  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800462d4  mov     r8d, edi; nNumberOfBytesToRead
0x1800462d7  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x1800462db  mov     rcx, rbx; hFile
0x1800462de  call    cs:__imp_ReadFile
0x1800462e5  nop     dword ptr [rax+rax+00h]
0x1800462ea  mov     rcx, [rbp+18h]; this
0x1800462ee  test    eax, eax
0x1800462f0  jz      loc_1800463B2
0x1800462f6  cmp     [rbp+NumberOfBytesRead], edi
0x1800462f9  setnz   al
0x1800462fc  mov     rcx, [rbp+18h]; this
0x180046300  test    al, al
0x180046302  jnz     loc_180046388
0x180046308  mov     rcx, rbx; hObject
0x18004630b  call    cs:__imp_CloseHandle
0x180046312  nop     dword ptr [rax+rax+00h]
0x180046317  mov     [rbp+arg_10], 0
0x18004631e  lea     r8, [rbp+arg_10]
0x180046322  lea     rdx, [rbp+lpBuffer]
0x180046326  lea     rcx, [rbp+var_20]
0x18004632a  call    ??0IppAttributeGroup@PrintCore@@QEAA@AEAV?$vector@EV?$allocator@E@std@@@std@@AEAK@Z; PrintCore::IppAttributeGroup::IppAttributeGroup(std::vector<uchar> &,ulong &)
0x18004632f  nop
0x180046330  lea     rax, [rbp+var_18]
0x180046334  cmp     rsi, rax
0x180046337  jz      short loc_18004635F
0x180046339  mov     rdx, [rbp+var_18]
0x18004633d  mov     r8, [rbp+var_10]
0x180046341  sub     r8, rdx
0x180046344  sar     r8, 3
0x180046348  mov     rax, 6DB6DB6DB6DB6DB7h
0x180046352  imul    r8, rax
0x180046356  mov     rcx, rsi
0x180046359  call    ??$_Assign_counted_range@PEAVIppAttribute@PrintCore@@@?$vector@VIppAttribute@PrintCore@@V?$allocator@VIppAttribute@PrintCore@@@std@@@std@@AEAAXPEAVIppAttribute@PrintCore@@_K@Z; std::vector<PrintCore::IppAttribute>::_Assign_counted_range<PrintCore::IppAttribute *>(PrintCore::IppAttribute *,unsigned __int64)
0x18004635e  nop
0x18004635f  lea     rcx, [rbp+var_18]
0x180046363  call    ??1?$vector@VIppAttribute@PrintCore@@V?$allocator@VIppAttribute@PrintCore@@@std@@@std@@QEAA@XZ; std::vector<PrintCore::IppAttribute>::~vector<PrintCore::IppAttribute>(void)
0x180046368  nop
0x180046369  lea     rcx, [rbp+lpBuffer]
0x18004636d  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180046372  xor     eax, eax
0x180046374  mov     rbx, [rsp+80h+arg_8]
0x18004637c  add     rsp, 80h
0x180046383  pop     rdi
0x180046384  pop     rsi
0x180046385  pop     rbp
0x180046386  retn
0x180046388  mov     r9d, 8000FFFFh; char *
0x18004638e  lea     r8, aOnecoreuapInte_2; "OneCoreUap\\Internal\\PrintScan\\inc\\i"...
0x180046395  mov     edx, 44h ; 'D'; void *
0x18004639a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800463a0  lea     r8, aOnecoreuapInte_2; "OneCoreUap\\Internal\\PrintScan\\inc\\i"...
0x1800463a7  mov     edx, 40h ; '@'; void *
0x1800463ac  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800463b2  lea     r8, aOnecoreuapInte_2; "OneCoreUap\\Internal\\PrintScan\\inc\\i"...
0x1800463b9  mov     edx, 43h ; 'C'; void *
0x1800463be  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
