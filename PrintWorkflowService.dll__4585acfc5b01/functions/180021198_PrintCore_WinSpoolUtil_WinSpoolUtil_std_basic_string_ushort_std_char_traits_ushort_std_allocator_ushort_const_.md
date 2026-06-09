# PrintCore::WinSpoolUtil::WinSpoolUtil(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x180021198`
- end: `0x1800212d0`
- name: `??0WinSpoolUtil@PrintCore@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `312`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800228c0`
- `0x180043694`
- `0x180048bcc`
- `0x1800496a4`
- `0x18004d1e8`
- `0x18004d454`
- `0x18004f164`
- `0x18004f490`

## callees

- `0x1800097bc`
- `0x18000a64c`
- `0x180012784`
- `0x1800127a4`
- `0x180016268`
- `0x180021198`
- `0x180023664`
- `0x180023680`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021212`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021212`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800211f4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800211f4`
- `WINSPOOL!OpenPrinterW` at `0x18002129b`
- `WINSPOOL!OpenPrinterW` at `0x18002129b`
- `WINSPOOL!ClosePrinter` at `0x180021273`
- `WINSPOOL!ClosePrinter` at `0x180021273`

## pseudocode

```c
__int64 __fastcall PrintCore::WinSpoolUtil::WinSpoolUtil(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rdx
  void **v4; // r14
  __int64 v5; // rax
  __int64 v6; // rdx
  HMODULE LibraryW; // rsi
  HMODULE v8; // rbp
  void *v9; // rsi
  WCHAR *v10; // rax
  const char *v11; // r9
  int v13; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char v15; // [rsp+68h] [rbp+10h] BYREF

  *(_QWORD *)a1 = 0;
  v2 = a1 + 8;
  std::wstring::wstring(a1 + 8);
  v4 = (void **)(a1 + 40);
  *(_QWORD *)(a1 + 40) = 0;
  if ( v2 != v3 )
  {
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v3);
    std::wstring::assign(v2, v5, *(_QWORD *)(v6 + 16));
  }
  LibraryW = LoadLibraryW(L"winspool.drv");
  v8 = *(HMODULE *)a1;
  if ( *(_QWORD *)a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v15);
    FreeLibrary(v8);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v15);
  }
  *(_QWORD *)a1 = LibraryW;
  if ( !LibraryW )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\winspoolutil.hxx",
      (const char *)0x80070485LL,
      v13);
  v9 = *v4;
  if ( *v4 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v15);
    ClosePrinter(v9);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v15);
  }
  *v4 = 0;
  v10 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v2);
  if ( !OpenPrinterW(v10, (LPHANDLE)(a1 + 40), 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2F,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\winspoolutil.hxx",
      v11);
  return a1;
}

```

## disassembly

```asm
0x180021198  mov     [rsp+arg_10], rbx
0x18002119d  mov     [rsp+arg_18], rbp
0x1800211a2  mov     [rsp+arg_0], rcx
0x1800211a7  push    rsi
0x1800211a8  push    rdi
0x1800211a9  push    r14
0x1800211ab  sub     rsp, 40h
0x1800211af  mov     rbx, rcx
0x1800211b2  mov     qword ptr [rcx], 0
0x1800211b9  lea     rdi, [rcx+8]
0x1800211bd  mov     rcx, rdi
0x1800211c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800211c5  nop
0x1800211c6  lea     r14, [rbx+28h]
0x1800211ca  mov     qword ptr [r14], 0
0x1800211d1  cmp     rdi, rdx
0x1800211d4  jz      short loc_1800211ED
0x1800211d6  mov     rcx, rdx
0x1800211d9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800211de  mov     r8, [rdx+10h]
0x1800211e2  mov     rdx, rax
0x1800211e5  mov     rcx, rdi
0x1800211e8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x1800211ed  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x1800211f4  call    cs:__imp_LoadLibraryW
0x1800211fa  mov     rsi, rax
0x1800211fd  mov     rbp, [rbx]
0x180021200  test    rbp, rbp
0x180021203  jz      short loc_180021222
0x180021205  lea     rcx, [rsp+58h+arg_8]; this
0x18002120a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002120f  mov     rcx, rbp; hLibModule
0x180021212  call    cs:__imp_FreeLibrary
0x180021218  lea     rcx, [rsp+58h+arg_8]; this
0x18002121d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180021222  mov     [rbx], rsi
0x180021225  test    rsi, rsi
0x180021228  setz    al
0x18002122b  mov     rcx, [rsp+58h]; this
0x180021230  test    al, al
0x180021232  jz      short loc_18002124C
0x180021234  mov     r9d, 80070485h; char *
0x18002123a  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\Printscan\\inc\\w"...
0x180021241  mov     edx, 2Ah ; '*'; void *
0x180021246  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002124c  xorps   xmm0, xmm0
0x18002124f  movdqu  [rsp+58h+var_38], xmm0
0x180021255  mov     [rsp+58h+var_28], 0F000Ch
0x18002125e  mov     rsi, [r14]
0x180021261  test    rsi, rsi
0x180021264  jz      short loc_180021283
0x180021266  lea     rcx, [rsp+58h+arg_8]; this
0x18002126b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180021270  mov     rcx, rsi; hPrinter
0x180021273  call    cs:__imp_ClosePrinter
0x180021279  lea     rcx, [rsp+58h+arg_8]; this
0x18002127e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180021283  mov     qword ptr [r14], 0
0x18002128a  mov     rcx, rdi
0x18002128d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021292  xor     r8d, r8d; pDefault
0x180021295  mov     rdx, r14; phPrinter
0x180021298  mov     rcx, rax; pPrinterName
0x18002129b  call    cs:__imp_OpenPrinterW
0x1800212a1  mov     rcx, [rsp+58h]; this
0x1800212a6  test    eax, eax
0x1800212a8  jnz     short loc_1800212BA
0x1800212aa  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\Printscan\\inc\\w"...
0x1800212b1  lea     edx, [rax+2Fh]; void *
0x1800212b4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800212ba  mov     rax, rbx
0x1800212bd  mov     rbx, [rsp+58h+arg_10]
0x1800212c2  mov     rbp, [rsp+58h+arg_18]
0x1800212c7  add     rsp, 40h
0x1800212cb  pop     r14
0x1800212cd  pop     rdi
0x1800212ce  pop     rsi
0x1800212cf  retn
```
