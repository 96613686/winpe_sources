# PrintCore::WinSpoolUtil::WinSpoolUtil(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x18003e458`
- end: `0x18003e589`
- name: `??0WinSpoolUtil@PrintCore@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `305`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003e0e0`
- `0x180040894`

## callees

- `0x18002025c`
- `0x18002c8b4`
- `0x18003e458`
- `0x18003fb04`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18003e4cd`
- `KERNEL32!FreeLibrary` at `0x18003e4cd`
- `KERNEL32!SetLastError` at `0x18003e4d5`
- `KERNEL32!SetLastError` at `0x18003e51e`
- `KERNEL32!SetLastError` at `0x18003e4d5`
- `KERNEL32!SetLastError` at `0x18003e51e`
- `KERNEL32!GetLastError` at `0x18003e4c2`
- `KERNEL32!GetLastError` at `0x18003e50b`
- `KERNEL32!GetLastError` at `0x18003e4c2`
- `KERNEL32!GetLastError` at `0x18003e50b`
- `KERNEL32!LoadLibraryW` at `0x18003e4b1`
- `KERNEL32!LoadLibraryW` at `0x18003e4b1`
- `WINSPOOL!ClosePrinter` at `0x18003e516`
- `WINSPOOL!ClosePrinter` at `0x18003e516`
- `WINSPOOL!OpenPrinterW` at `0x18003e540`
- `WINSPOOL!OpenPrinterW` at `0x18003e540`

## pseudocode

```c
__int64 __fastcall PrintCore::WinSpoolUtil::WinSpoolUtil(__int64 a1, __int64 a2)
{
  WCHAR *v3; // rdi
  HANDLE *v4; // r14
  HMODULE LibraryW; // rbp
  HMODULE v6; // r15
  DWORD LastError; // ebx
  HANDLE v8; // rbp
  DWORD v9; // ebx
  const char *v10; // r9
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+28h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

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
    LastError = GetLastError();
    FreeLibrary(v6);
    SetLastError(LastError);
  }
  *(_QWORD *)a1 = LibraryW;
  if ( !LibraryW )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\WinSpoolUtil.hxx",
      (const char *)0x80070485LL,
      -2);
  *(_OWORD *)&pDefault.pDatatype = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  v8 = *v4;
  if ( *v4 )
  {
    v9 = GetLastError();
    ClosePrinter(v8);
    SetLastError(v9);
  }
  *v4 = 0;
  if ( *((_QWORD *)v3 + 3) > 7u )
    v3 = *(WCHAR **)v3;
  if ( !OpenPrinterW(v3, v4, &pDefault) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2F,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\WinSpoolUtil.hxx",
      v10);
  return a1;
}

```

## disassembly

```asm
0x18003e458  mov     [rsp+arg_0], rcx
0x18003e45d  push    rbx
0x18003e45e  push    rbp
0x18003e45f  push    rsi
0x18003e460  push    rdi
0x18003e461  push    r14
0x18003e463  push    r15
0x18003e465  sub     rsp, 48h
0x18003e469  mov     qword ptr [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh; int
0x18003e472  mov     rsi, rcx
0x18003e475  mov     qword ptr [rcx], 0
0x18003e47c  lea     rdi, [rcx+8]
0x18003e480  xorps   xmm0, xmm0
0x18003e483  movups  xmmword ptr [rdi], xmm0
0x18003e486  mov     qword ptr [rdi+10h], 0
0x18003e48e  mov     qword ptr [rdi+18h], 7
0x18003e496  xor     eax, eax
0x18003e498  mov     [rdi], ax
0x18003e49b  lea     r14, [rcx+28h]
0x18003e49f  mov     [r14], rax
0x18003e4a2  mov     rcx, rdi
0x18003e4a5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003e4aa  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x18003e4b1  call    cs:__imp_LoadLibraryW
0x18003e4b7  mov     rbp, rax
0x18003e4ba  mov     r15, [rsi]
0x18003e4bd  test    r15, r15
0x18003e4c0  jz      short loc_18003E4DB
0x18003e4c2  call    cs:__imp_GetLastError
0x18003e4c8  mov     ebx, eax
0x18003e4ca  mov     rcx, r15; hLibModule
0x18003e4cd  call    cs:__imp_FreeLibrary
0x18003e4d3  mov     ecx, ebx; dwErrCode
0x18003e4d5  call    cs:__imp_SetLastError
0x18003e4db  mov     [rsi], rbp
0x18003e4de  test    rbp, rbp
0x18003e4e1  setz    al
0x18003e4e4  mov     rcx, [rsp+78h]; this
0x18003e4e9  test    al, al
0x18003e4eb  jnz     loc_18003E571
0x18003e4f1  xorps   xmm0, xmm0
0x18003e4f4  movdqu  xmmword ptr [rsp+78h+pDefault.pDatatype], xmm0
0x18003e4fa  mov     qword ptr [rsp+78h+pDefault.DesiredAccess], 0F000Ch
0x18003e503  mov     rbp, [r14]
0x18003e506  test    rbp, rbp
0x18003e509  jz      short loc_18003E524
0x18003e50b  call    cs:__imp_GetLastError
0x18003e511  mov     ebx, eax
0x18003e513  mov     rcx, rbp; hPrinter
0x18003e516  call    cs:__imp_ClosePrinter
0x18003e51c  mov     ecx, ebx; dwErrCode
0x18003e51e  call    cs:__imp_SetLastError
0x18003e524  mov     qword ptr [r14], 0
0x18003e52b  cmp     qword ptr [rdi+18h], 7
0x18003e530  jbe     short loc_18003E535
0x18003e532  mov     rdi, [rdi]
0x18003e535  lea     r8, [rsp+78h+pDefault]; pDefault
0x18003e53a  mov     rdx, r14; phPrinter
0x18003e53d  mov     rcx, rdi; pPrinterName
0x18003e540  call    cs:__imp_OpenPrinterW
0x18003e546  mov     rcx, [rsp+78h]; this
0x18003e54b  test    eax, eax
0x18003e54d  jz      short loc_18003E55F
0x18003e54f  mov     rax, rsi
0x18003e552  add     rsp, 48h
0x18003e556  pop     r15
0x18003e558  pop     r14
0x18003e55a  pop     rdi
0x18003e55b  pop     rsi
0x18003e55c  pop     rbp
0x18003e55d  pop     rbx
0x18003e55e  retn
0x18003e55f  lea     r8, aOnecoreuapInte_6; "OneCoreUap\\Internal\\PrintScan\\inc\\W"...
0x18003e566  mov     edx, 2Fh ; '/'; void *
0x18003e56b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003e571  mov     r9d, 80070485h; char *
0x18003e577  lea     r8, aOnecoreuapInte_6; "OneCoreUap\\Internal\\PrintScan\\inc\\W"...
0x18003e57e  mov     edx, 2Ah ; '*'; void *
0x18003e583  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
