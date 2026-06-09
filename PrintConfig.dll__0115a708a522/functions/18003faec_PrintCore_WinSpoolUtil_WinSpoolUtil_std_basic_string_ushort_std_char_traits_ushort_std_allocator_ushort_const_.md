# PrintCore::WinSpoolUtil::WinSpoolUtil(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x18003faec`
- end: `0x18003fc4e`
- name: `??0WinSpoolUtil@PrintCore@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `354`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003f724`
- `0x1800421b0`

## callees

- `0x180020c8c`
- `0x18002dbc8`
- `0x18003faec`
- `0x1800412a4`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18003fb6d`
- `KERNEL32!FreeLibrary` at `0x18003fb6d`
- `KERNEL32!SetLastError` at `0x18003fb7b`
- `KERNEL32!SetLastError` at `0x18003fbd6`
- `KERNEL32!SetLastError` at `0x18003fb7b`
- `KERNEL32!SetLastError` at `0x18003fbd6`
- `KERNEL32!GetLastError` at `0x18003fb5c`
- `KERNEL32!GetLastError` at `0x18003fbb7`
- `KERNEL32!GetLastError` at `0x18003fb5c`
- `KERNEL32!GetLastError` at `0x18003fbb7`
- `KERNEL32!LoadLibraryW` at `0x18003fb45`
- `KERNEL32!LoadLibraryW` at `0x18003fb45`
- `WINSPOOL!ClosePrinter` at `0x18003fbc8`
- `WINSPOOL!ClosePrinter` at `0x18003fbc8`
- `WINSPOOL!OpenPrinterW` at `0x18003fbfe`
- `WINSPOOL!OpenPrinterW` at `0x18003fbfe`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PrintCore::WinSpoolUtil::WinSpoolUtil(__int64 a1, _QWORD *a2, __int64 a3)
{
  WCHAR *v4; // rdi
  HANDLE *v5; // r14
  HMODULE LibraryW; // rbp
  HMODULE v7; // r15
  DWORD LastError; // ebx
  HANDLE v9; // rbp
  DWORD v10; // ebx
  const char *v11; // r9
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+28h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_QWORD *)a1 = 0;
  v4 = (WCHAR *)(a1 + 8);
  *(_OWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 7;
  *(_WORD *)(a1 + 8) = 0;
  v5 = (HANDLE *)(a1 + 40);
  *(_QWORD *)(a1 + 40) = 0;
  std::wstring::operator=(a1 + 8, a2, a3);
  LibraryW = LoadLibraryW(L"winspool.drv");
  v7 = *(HMODULE *)a1;
  if ( *(_QWORD *)a1 )
  {
    LastError = GetLastError();
    FreeLibrary(v7);
    SetLastError(LastError);
  }
  *(_QWORD *)a1 = LibraryW;
  if ( !LibraryW )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      42,
      (__int64)"OneCoreUap\\Internal\\PrintScan\\inc\\WinSpoolUtil.hxx",
      (const char *)0x80070485LL,
      -2);
  *(_OWORD *)&pDefault.pDatatype = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  v9 = *v5;
  if ( *v5 )
  {
    v10 = GetLastError();
    ClosePrinter(v9);
    SetLastError(v10);
  }
  *v5 = 0;
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(WCHAR **)v4;
  if ( !OpenPrinterW(v4, v5, &pDefault) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2F,
      (__int64)"OneCoreUap\\Internal\\PrintScan\\inc\\WinSpoolUtil.hxx",
      v11);
  return a1;
}

```

## disassembly

```asm
0x18003faec  mov     [rsp+arg_0], rcx
0x18003faf1  push    rbx
0x18003faf2  push    rbp
0x18003faf3  push    rsi
0x18003faf4  push    rdi
0x18003faf5  push    r14
0x18003faf7  push    r15
0x18003faf9  sub     rsp, 48h
0x18003fafd  mov     qword ptr [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh; int
0x18003fb06  mov     rsi, rcx
0x18003fb09  mov     qword ptr [rcx], 0
0x18003fb10  lea     rdi, [rcx+8]
0x18003fb14  xorps   xmm0, xmm0
0x18003fb17  movups  xmmword ptr [rdi], xmm0
0x18003fb1a  mov     qword ptr [rdi+10h], 0
0x18003fb22  mov     qword ptr [rdi+18h], 7
0x18003fb2a  xor     eax, eax
0x18003fb2c  mov     [rdi], ax
0x18003fb2f  lea     r14, [rcx+28h]
0x18003fb33  mov     [r14], rax
0x18003fb36  mov     rcx, rdi
0x18003fb39  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003fb3e  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x18003fb45  call    cs:__imp_LoadLibraryW
0x18003fb4c  nop     dword ptr [rax+rax+00h]
0x18003fb51  mov     rbp, rax
0x18003fb54  mov     r15, [rsi]
0x18003fb57  test    r15, r15
0x18003fb5a  jz      short loc_18003FB87
0x18003fb5c  call    cs:__imp_GetLastError
0x18003fb63  nop     dword ptr [rax+rax+00h]
0x18003fb68  mov     ebx, eax
0x18003fb6a  mov     rcx, r15; hLibModule
0x18003fb6d  call    cs:__imp_FreeLibrary
0x18003fb74  nop     dword ptr [rax+rax+00h]
0x18003fb79  mov     ecx, ebx; dwErrCode
0x18003fb7b  call    cs:__imp_SetLastError
0x18003fb82  nop     dword ptr [rax+rax+00h]
0x18003fb87  mov     [rsi], rbp
0x18003fb8a  test    rbp, rbp
0x18003fb8d  setz    al
0x18003fb90  mov     rcx, [rsp+78h]; this
0x18003fb95  test    al, al
0x18003fb97  jnz     loc_18003FC36
0x18003fb9d  xorps   xmm0, xmm0
0x18003fba0  movdqu  xmmword ptr [rsp+78h+pDefault.pDatatype], xmm0
0x18003fba6  mov     qword ptr [rsp+78h+pDefault.DesiredAccess], 0F000Ch
0x18003fbaf  mov     rbp, [r14]
0x18003fbb2  test    rbp, rbp
0x18003fbb5  jz      short loc_18003FBE2
0x18003fbb7  call    cs:__imp_GetLastError
0x18003fbbe  nop     dword ptr [rax+rax+00h]
0x18003fbc3  mov     ebx, eax
0x18003fbc5  mov     rcx, rbp; hPrinter
0x18003fbc8  call    cs:__imp_ClosePrinter
0x18003fbcf  nop     dword ptr [rax+rax+00h]
0x18003fbd4  mov     ecx, ebx; dwErrCode
0x18003fbd6  call    cs:__imp_SetLastError
0x18003fbdd  nop     dword ptr [rax+rax+00h]
0x18003fbe2  mov     qword ptr [r14], 0
0x18003fbe9  cmp     qword ptr [rdi+18h], 7
0x18003fbee  jbe     short loc_18003FBF3
0x18003fbf0  mov     rdi, [rdi]
0x18003fbf3  lea     r8, [rsp+78h+pDefault]; pDefault
0x18003fbf8  mov     rdx, r14; phPrinter
0x18003fbfb  mov     rcx, rdi; pPrinterName
0x18003fbfe  call    cs:__imp_OpenPrinterW
0x18003fc05  nop     dword ptr [rax+rax+00h]
0x18003fc0a  mov     rcx, [rsp+78h]; this
0x18003fc0f  test    eax, eax
0x18003fc11  jz      short loc_18003FC24
0x18003fc13  mov     rax, rsi
0x18003fc16  add     rsp, 48h
0x18003fc1a  pop     r15
0x18003fc1c  pop     r14
0x18003fc1e  pop     rdi
0x18003fc1f  pop     rsi
0x18003fc20  pop     rbp
0x18003fc21  pop     rbx
0x18003fc22  retn
0x18003fc24  lea     r8, aOnecoreuapInte_6; "OneCoreUap\\Internal\\PrintScan\\inc\\W"...
0x18003fc2b  mov     edx, 2Fh ; '/'; void *
0x18003fc30  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003fc36  mov     r9d, 80070485h; char *
0x18003fc3c  lea     r8, aOnecoreuapInte_6; "OneCoreUap\\Internal\\PrintScan\\inc\\W"...
0x18003fc43  mov     edx, 2Ah ; '*'; void *
0x18003fc48  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
