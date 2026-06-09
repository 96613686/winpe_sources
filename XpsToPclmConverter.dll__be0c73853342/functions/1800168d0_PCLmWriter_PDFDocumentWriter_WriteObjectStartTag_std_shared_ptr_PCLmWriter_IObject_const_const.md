# PCLmWriter::PDFDocumentWriter::_WriteObjectStartTag(std::shared_ptr<PCLmWriter::IObject const> const &)

- ea: `0x1800168d0`
- end: `0x180016a4d`
- name: `?_WriteObjectStartTag@PDFDocumentWriter@PCLmWriter@@AEAAXAEBV?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@Z`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800159d0`

## callees

- `0x1800015f0`
- `0x180002148`
- `0x18000bffc`
- `0x180010050`
- `0x1800168d0`
- `0x180016a54`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169d1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800169c7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800169c7`

## string_xrefs

- `0x180016983`: `onecoreuap\printscan\print\drivers\renderlibrary\pclm\lib\pdfdocumentwriter.cpp`
- `0x1800169e9`: `onecoreuap\printscan\print\drivers\renderlibrary\pclm\lib\pdfdocumentwriter.cpp`

## pseudocode

```c
__int64 __fastcall PCLmWriter::PDFDocumentWriter::_WriteObjectStartTag(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // eax
  signed int LastError; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, CHAR *, size_t); // rbx
  size_t v11; // rax
  unsigned int lpMultiByteStr; // [rsp+20h] [rbp-E0h]
  CHAR MultiByteStr[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v15; // [rsp+50h] [rbp-B0h]
  __int128 v16; // [rsp+60h] [rbp-A0h]
  __int16 v17; // [rsp+70h] [rbp-90h]
  unsigned __int16 v18[8]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v19; // [rsp+88h] [rbp-78h]
  WCHAR WideCharStr[56]; // [rsp+90h] [rbp-70h] BYREF

  v17 = 0;
  *(_OWORD *)MultiByteStr = 0;
  v15 = 0;
  v16 = 0;
  memset_0(WideCharStr, 0, 0x64u);
  v4 = *a2;
  *(_OWORD *)v18 = *(_OWORD *)L"\n%d %d obj\n";
  v19 = *(_QWORD *)L"bj\n";
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4);
  v6 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
  v7 = StringCchPrintfW(WideCharStr, 0x32u, v18, v6);
  PrintCore::ThrowIfError(
    (PrintCore *)v7,
    (int)"Unspecified.",
    "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pclm\\lib\\pdfdocumentwriter.cpp",
    (const char *)0x10B,
    v5);
  if ( !WideCharToMultiByte(0xFDE9u, 0, WideCharStr, 50, MultiByteStr, 50, 0, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PrintCore::ThrowIfError(
      (PrintCore *)(unsigned int)LastError,
      (int)"Unspecified.",
      "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pclm\\lib\\pdfdocumentwriter.cpp",
      (const char *)0x10E,
      lpMultiByteStr);
  }
  v9 = *(_QWORD *)(a1 + 16);
  v10 = *(__int64 (__fastcall **)(__int64, CHAR *, size_t))(*(_QWORD *)v9 + 24LL);
  v11 = strnlen_s(MultiByteStr, 0x32u);
  return v10(v9, MultiByteStr, v11);
}

```

## disassembly

```asm
0x1800168d0  mov     [rsp-8+arg_10], rbx
0x1800168d5  mov     [rsp-8+arg_18], rsi
0x1800168da  push    rbp
0x1800168db  push    rdi
0x1800168dc  push    r14
0x1800168de  lea     rbp, [rsp-10h]
0x1800168e3  sub     rsp, 110h
0x1800168ea  mov     rax, cs:__security_cookie
0x1800168f1  xor     rax, rsp
0x1800168f4  mov     [rbp+20h+var_20], rax
0x1800168f8  xorps   xmm0, xmm0
0x1800168fb  xor     eax, eax
0x1800168fd  mov     rdi, rdx
0x180016900  mov     [rsp+120h+var_B0], ax
0x180016905  mov     rsi, rcx
0x180016908  xor     edx, edx; Val
0x18001690a  lea     rcx, [rbp+20h+WideCharStr]; void *
0x18001690e  lea     r8d, [rax+64h]; Size
0x180016912  movups  xmmword ptr [rsp+120h+MultiByteStr], xmm0
0x180016917  movups  [rsp+120h+var_D0], xmm0
0x18001691c  movups  [rsp+120h+var_C0], xmm0
0x180016921  call    memset_0
0x180016926  movups  xmm0, xmmword ptr cs:aDDObj; "\n%d %d obj\n"
0x18001692d  mov     rcx, [rdi]
0x180016930  movsd   xmm1, qword ptr cs:aDDObj+10h; "bj\n"
0x180016938  movups  xmmword ptr [rsp+120h+var_A8], xmm0
0x18001693d  movsd   [rbp+20h+var_98], xmm1
0x180016942  mov     rax, [rcx]
0x180016945  mov     rax, [rax+18h]
0x180016949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001694e  mov     rcx, [rdi]
0x180016951  mov     ebx, eax
0x180016953  mov     rdx, [rcx]
0x180016956  mov     rax, [rdx+10h]
0x18001695a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001695f  mov     r14d, 32h ; '2'
0x180016965  mov     dword ptr [rsp+120h+lpMultiByteStr], ebx; unsigned int
0x180016969  mov     edx, r14d; unsigned __int64
0x18001696c  lea     r8, [rsp+120h+var_A8]; unsigned __int16 *
0x180016971  mov     r9d, eax
0x180016974  lea     rcx, [rbp+20h+WideCharStr]; unsigned __int16 *
0x180016978  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001697d  mov     r9d, 10Bh; char *
0x180016983  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\drivers\\"...
0x18001698a  lea     rdx, aUnspecified; "Unspecified."
0x180016991  mov     ecx, eax; this
0x180016993  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180016998  mov     [rsp+120h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800169a1  lea     rax, [rsp+120h+MultiByteStr]
0x1800169a6  mov     [rsp+120h+lpDefaultChar], 0; lpDefaultChar
0x1800169af  lea     r8, [rbp+20h+WideCharStr]; lpWideCharStr
0x1800169b3  mov     [rsp+120h+cbMultiByte], r14d; cbMultiByte
0x1800169b8  mov     r9d, r14d; cchWideChar
0x1800169bb  xor     edx, edx; dwFlags
0x1800169bd  mov     [rsp+120h+lpMultiByteStr], rax; unsigned int
0x1800169c2  mov     ecx, 0FDE9h; CodePage
0x1800169c7  call    cs:__imp_WideCharToMultiByte
0x1800169cd  test    eax, eax
0x1800169cf  jnz     short loc_1800169FE
0x1800169d1  call    cs:__imp_GetLastError
0x1800169d7  test    eax, eax
0x1800169d9  jle     short loc_1800169E3
0x1800169db  movzx   eax, ax
0x1800169de  or      eax, 80070000h
0x1800169e3  mov     r9d, 10Eh; char *
0x1800169e9  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\drivers\\"...
0x1800169f0  lea     rdx, aUnspecified; "Unspecified."
0x1800169f7  mov     ecx, eax; this
0x1800169f9  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x1800169fe  mov     rdi, [rsi+10h]
0x180016a02  lea     rcx, [rsp+120h+MultiByteStr]; String
0x180016a07  mov     rdx, r14; MaxCount
0x180016a0a  mov     rax, [rdi]
0x180016a0d  mov     rbx, [rax+18h]
0x180016a11  call    strnlen_s
0x180016a16  mov     r8, rax
0x180016a19  lea     rdx, [rsp+120h+MultiByteStr]
0x180016a1e  mov     rax, rbx
0x180016a21  mov     rcx, rdi
0x180016a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a29  mov     rcx, [rbp+20h+var_20]
0x180016a2d  xor     rcx, rsp; StackCookie
0x180016a30  call    __security_check_cookie
0x180016a35  lea     r11, [rsp+120h+var_10]
0x180016a3d  mov     rbx, [r11+30h]
0x180016a41  mov     rsi, [r11+38h]
0x180016a45  mov     rsp, r11
0x180016a48  pop     r14
0x180016a4a  pop     rdi
0x180016a4b  pop     rbp
0x180016a4c  retn
```
