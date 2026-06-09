# PrintCore::WinSpoolUtil::WinSpoolUtil(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x1800269d8`
- end: `0x180026b12`
- name: `??0WinSpoolUtil@PrintCore@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `314`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800280a0`

## callees

- `0x180007a28`
- `0x18000876c`
- `0x18001cfb4`
- `0x1800269d8`
- `0x180027440`
- `0x18002f194`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180026a4c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180026a4c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180026a2e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180026a2e`
- `ext-ms-win-printer-winspool-core-l1-1-0!ClosePrinter` at `0x180026a99`
- `ext-ms-win-printer-winspool-core-l1-1-0!ClosePrinter` at `0x180026a99`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x180026ac3`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x180026ac3`

## pseudocode

```c
__int64 __fastcall PrintCore::WinSpoolUtil::WinSpoolUtil(__int64 a1, __int64 a2)
{
  WCHAR *v3; // rbx
  HANDLE *v4; // rsi
  HMODULE LibraryW; // rbp
  HMODULE v6; // r14
  HANDLE v7; // rbp
  const char *v8; // r9
  int v10; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char v12; // [rsp+78h] [rbp+20h] BYREF

  *(_QWORD *)a1 = 0;
  v3 = (WCHAR *)(a1 + 8);
  *(_OWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 7;
  *(_WORD *)(a1 + 8) = 0;
  v4 = (HANDLE *)(a1 + 40);
  *(_QWORD *)(a1 + 40) = 0;
  std::wstring::operator=(a1 + 8, a2);
  LibraryW = LoadLibraryW(L"winspool.drv");
  v6 = *(HMODULE *)a1;
  if ( *(_QWORD *)a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
    FreeLibrary(v6);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
  }
  *(_QWORD *)a1 = LibraryW;
  if ( !LibraryW )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\WinspoolUtil.hxx",
      (const char *)0x80070485LL,
      v10);
  v7 = *v4;
  if ( *v4 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
    ClosePrinter(v7);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
  }
  *v4 = 0;
  if ( *((_QWORD *)v3 + 3) > 7u )
    v3 = *(WCHAR **)v3;
  if ( !OpenPrinterW(v3, v4, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2F,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\WinspoolUtil.hxx",
      v8);
  return a1;
}

```

## disassembly

```asm
0x1800269d8  mov     [rsp+arg_8], rbx
0x1800269dd  mov     [rsp+arg_10], rbp
0x1800269e2  mov     [rsp+arg_0], rcx
0x1800269e7  push    rsi
0x1800269e8  push    rdi
0x1800269e9  push    r14
0x1800269eb  sub     rsp, 40h
0x1800269ef  mov     rdi, rcx
0x1800269f2  mov     qword ptr [rcx], 0
0x1800269f9  lea     rbx, [rcx+8]
0x1800269fd  xorps   xmm0, xmm0
0x180026a00  movups  xmmword ptr [rbx], xmm0
0x180026a03  mov     qword ptr [rbx+10h], 0
0x180026a0b  mov     qword ptr [rbx+18h], 7
0x180026a13  xor     eax, eax
0x180026a15  mov     [rbx], ax
0x180026a18  lea     rsi, [rcx+28h]
0x180026a1c  mov     [rsi], rax
0x180026a1f  mov     rcx, rbx
0x180026a22  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180026a27  lea     rcx, aWinspoolDrv; "winspool.drv"
0x180026a2e  call    cs:__imp_LoadLibraryW
0x180026a34  mov     rbp, rax
0x180026a37  mov     r14, [rdi]
0x180026a3a  test    r14, r14
0x180026a3d  jz      short loc_180026A5C
0x180026a3f  lea     rcx, [rsp+58h+arg_18]; this
0x180026a44  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180026a49  mov     rcx, r14; hLibModule
0x180026a4c  call    cs:__imp_FreeLibrary
0x180026a52  lea     rcx, [rsp+58h+arg_18]; this
0x180026a57  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180026a5c  mov     [rdi], rbp
0x180026a5f  test    rbp, rbp
0x180026a62  setz    al
0x180026a65  mov     rcx, [rsp+58h]; this
0x180026a6a  test    al, al
0x180026a6c  jnz     loc_180026AFA
0x180026a72  xorps   xmm0, xmm0
0x180026a75  movdqu  [rsp+58h+var_38], xmm0
0x180026a7b  mov     [rsp+58h+var_28], 0F000Ch
0x180026a84  mov     rbp, [rsi]
0x180026a87  test    rbp, rbp
0x180026a8a  jz      short loc_180026AA9
0x180026a8c  lea     rcx, [rsp+58h+arg_18]; this
0x180026a91  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180026a96  mov     rcx, rbp; hPrinter
0x180026a99  call    cs:__imp_ClosePrinter
0x180026a9f  lea     rcx, [rsp+58h+arg_18]; this
0x180026aa4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180026aa9  mov     qword ptr [rsi], 0
0x180026ab0  cmp     qword ptr [rbx+18h], 7
0x180026ab5  jbe     short loc_180026ABA
0x180026ab7  mov     rbx, [rbx]
0x180026aba  xor     r8d, r8d; pDefault
0x180026abd  mov     rdx, rsi; phPrinter
0x180026ac0  mov     rcx, rbx; pPrinterName
0x180026ac3  call    cs:__imp_OpenPrinterW
0x180026ac9  mov     rcx, [rsp+58h]; this
0x180026ace  test    eax, eax
0x180026ad0  jz      short loc_180026AE8
0x180026ad2  mov     rax, rdi
0x180026ad5  mov     rbx, [rsp+58h+arg_8]
0x180026ada  mov     rbp, [rsp+58h+arg_10]
0x180026adf  add     rsp, 40h
0x180026ae3  pop     r14
0x180026ae5  pop     rdi
0x180026ae6  pop     rsi
0x180026ae7  retn
0x180026ae8  lea     r8, aOnecoreuapInte_6; "OneCoreUap\\Internal\\Printscan\\inc\\W"...
0x180026aef  mov     edx, 2Fh ; '/'; void *
0x180026af4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180026afa  mov     r9d, 80070485h; char *
0x180026b00  lea     r8, aOnecoreuapInte_6; "OneCoreUap\\Internal\\Printscan\\inc\\W"...
0x180026b07  mov     edx, 2Ah ; '*'; void *
0x180026b0c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
