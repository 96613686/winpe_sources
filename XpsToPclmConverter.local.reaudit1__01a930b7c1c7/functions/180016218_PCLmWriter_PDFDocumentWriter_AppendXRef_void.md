# PCLmWriter::PDFDocumentWriter::_AppendXRef(void)

- ea: `0x180016218`
- end: `0x1800163a9`
- name: `?_AppendXRef@PDFDocumentWriter@PCLmWriter@@AEAAXXZ`
- size: `401`
- prototype: `void __fastcall(PCLmWriter::PDFDocumentWriter *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180015de4`

## callees

- `0x1800015f0`
- `0x18000bffc`
- `0x180010050`
- `0x180016218`
- `0x180016a54`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001632e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001632e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180016324`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180016324`

## string_xrefs

- `0x1800162e1`: `onecoreuap\printscan\print\drivers\renderlibrary\pclm\lib\pdfdocumentwriter.cpp`
- `0x180016346`: `onecoreuap\printscan\print\drivers\renderlibrary\pclm\lib\pdfdocumentwriter.cpp`

## pseudocode

```c
void __fastcall PCLmWriter::PDFDocumentWriter::_AppendXRef(PCLmWriter::PDFDocumentWriter *this)
{
  unsigned int *v1; // rbx
  bool v3; // zf
  unsigned int v4; // eax
  __int64 v5; // r9
  signed int LastError; // eax
  __int64 v7; // rsi
  void (__fastcall *v8)(__int64, CHAR *, size_t); // rdi
  size_t v9; // rax
  unsigned int lpMultiByteStr; // [rsp+20h] [rbp-89h]
  unsigned int lpMultiByteStra; // [rsp+20h] [rbp-89h]
  CHAR MultiByteStr[32]; // [rsp+40h] [rbp-69h] BYREF
  WCHAR WideCharStr[8]; // [rsp+60h] [rbp-49h] BYREF
  __int128 v14; // [rsp+70h] [rbp-39h]
  __int128 v15; // [rsp+80h] [rbp-29h]
  __int16 v16; // [rsp+90h] [rbp-19h]
  unsigned __int16 v17[8]; // [rsp+98h] [rbp-11h] BYREF
  unsigned __int16 v18[8]; // [rsp+A8h] [rbp-1h] BYREF
  __int128 v19; // [rsp+B8h] [rbp+Fh]

  v1 = (unsigned int *)*((_QWORD *)this + 15);
  *(_OWORD *)v17 = *(_OWORD *)L"%u %u\r\n";
  *(_OWORD *)v18 = *(_OWORD *)L"%010u %05u %c\r\n";
  v19 = *(_OWORD *)L"5u %c\r\n";
  while ( v1 != *((unsigned int **)this + 16) )
  {
    v3 = *((_BYTE *)v1 + 12) == 100;
    memset(MultiByteStr, 0, 25);
    v16 = 0;
    *(_OWORD *)WideCharStr = 0;
    v14 = 0;
    v15 = 0;
    if ( v3 )
    {
      lpMultiByteStr = v1[1];
      v4 = StringCchPrintfW(WideCharStr, 0x19u, v17, *v1);
      v5 = 353;
    }
    else
    {
      lpMultiByteStr = v1[2];
      v4 = StringCchPrintfW(WideCharStr, 0x19u, v18, v1[1]);
      v5 = 357;
    }
    PrintCore::ThrowIfError(
      (PrintCore *)v4,
      (int)"Unspecified.",
      "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pclm\\lib\\pdfdocumentwriter.cpp",
      (const char *)v5,
      lpMultiByteStr);
    if ( !WideCharToMultiByte(0xFDE9u, 0, WideCharStr, 25, MultiByteStr, 25, 0, 0) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PrintCore::ThrowIfError(
        (PrintCore *)(unsigned int)LastError,
        (int)"Unspecified.",
        "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pclm\\lib\\pdfdocumentwriter.cpp",
        (const char *)0x16A,
        lpMultiByteStra);
    }
    v7 = *((_QWORD *)this + 2);
    v8 = *(void (__fastcall **)(__int64, CHAR *, size_t))(*(_QWORD *)v7 + 24LL);
    v9 = strnlen_s(MultiByteStr, 0x19u);
    v8(v7, MultiByteStr, v9);
    v1 += 4;
  }
}

```

## disassembly

```asm
0x180016218  push    rbp
0x18001621a  push    rbx
0x18001621b  push    rsi
0x18001621c  push    rdi
0x18001621d  push    r14
0x18001621f  push    r15
0x180016221  lea     rbp, [rsp-2Fh]
0x180016226  sub     rsp, 0D8h
0x18001622d  mov     rax, cs:__security_cookie
0x180016234  xor     rax, rsp
0x180016237  mov     [rbp+57h+var_38], rax
0x18001623b  movups  xmm0, xmmword ptr cs:aUU; "%u %u\r\n"
0x180016242  mov     rbx, [rcx+78h]
0x180016246  mov     r14, rcx
0x180016249  movups  xmm1, xmmword ptr cs:a010u05uC; "%010u %05u %c\r\n"
0x180016250  mov     r15d, 19h
0x180016256  movdqu  xmmword ptr [rbp+57h+var_68], xmm0
0x18001625b  movups  xmm0, xmmword ptr cs:a010u05uC+10h; "5u %c\r\n"
0x180016262  movups  xmmword ptr [rbp+57h+var_58], xmm1
0x180016266  movups  [rbp+57h+var_48], xmm0
0x18001626a  cmp     rbx, [r14+80h]
0x180016271  jz      loc_18001638D
0x180016277  xorps   xmm1, xmm1
0x18001627a  lea     rcx, [rbp+57h+WideCharStr]; unsigned __int16 *
0x18001627e  xorps   xmm0, xmm0
0x180016281  xor     eax, eax
0x180016283  cmp     byte ptr [rbx+0Ch], 64h ; 'd'
0x180016287  mov     rdx, r15; unsigned __int64
0x18001628a  movups  xmmword ptr [rbp+57h+MultiByteStr], xmm0
0x18001628e  mov     [rbp+57h+var_70], ax
0x180016292  movups  xmmword ptr [rbp+57h+MultiByteStr+9], xmm0
0x180016296  movups  xmmword ptr [rbp+57h+WideCharStr], xmm1
0x18001629a  movups  [rbp+57h+var_90], xmm1
0x18001629e  movups  [rbp+57h+var_80], xmm1
0x1800162a2  jnz     short loc_1800162BF
0x1800162a4  mov     eax, [rbx+4]
0x1800162a7  lea     r8, [rbp+57h+var_68]; unsigned __int16 *
0x1800162ab  mov     r9d, [rbx]
0x1800162ae  mov     dword ptr [rsp+100h+lpMultiByteStr], eax
0x1800162b2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800162b7  mov     r9d, 161h
0x1800162bd  jmp     short loc_1800162E1
0x1800162bf  movsx   eax, byte ptr [rbx+0Ch]
0x1800162c3  lea     r8, [rbp+57h+var_58]; unsigned __int16 *
0x1800162c7  mov     r9d, [rbx+4]
0x1800162cb  mov     [rsp+100h+cbMultiByte], eax
0x1800162cf  mov     eax, [rbx+8]
0x1800162d2  mov     dword ptr [rsp+100h+lpMultiByteStr], eax; unsigned int
0x1800162d6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800162db  mov     r9d, 165h; char *
0x1800162e1  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\drivers\\"...
0x1800162e8  mov     ecx, eax; this
0x1800162ea  lea     rdx, aUnspecified; "Unspecified."
0x1800162f1  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x1800162f6  mov     [rsp+100h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800162ff  lea     rax, [rbp+57h+MultiByteStr]
0x180016303  mov     [rsp+100h+lpDefaultChar], 0; lpDefaultChar
0x18001630c  lea     r8, [rbp+57h+WideCharStr]; lpWideCharStr
0x180016310  mov     [rsp+100h+cbMultiByte], r15d; cbMultiByte
0x180016315  mov     r9d, r15d; cchWideChar
0x180016318  xor     edx, edx; dwFlags
0x18001631a  mov     [rsp+100h+lpMultiByteStr], rax; unsigned int
0x18001631f  mov     ecx, 0FDE9h; CodePage
0x180016324  call    cs:__imp_WideCharToMultiByte
0x18001632a  test    eax, eax
0x18001632c  jnz     short loc_18001635B
0x18001632e  call    cs:__imp_GetLastError
0x180016334  test    eax, eax
0x180016336  jle     short loc_180016340
0x180016338  movzx   eax, ax
0x18001633b  or      eax, 80070000h
0x180016340  mov     r9d, 16Ah; char *
0x180016346  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\drivers\\"...
0x18001634d  lea     rdx, aUnspecified; "Unspecified."
0x180016354  mov     ecx, eax; this
0x180016356  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18001635b  mov     rsi, [r14+10h]
0x18001635f  lea     rcx, [rbp+57h+MultiByteStr]; String
0x180016363  mov     rdx, r15; MaxCount
0x180016366  mov     rax, [rsi]
0x180016369  mov     rdi, [rax+18h]
0x18001636d  call    strnlen_s
0x180016372  mov     r8, rax
0x180016375  lea     rdx, [rbp+57h+MultiByteStr]
0x180016379  mov     rax, rdi
0x18001637c  mov     rcx, rsi
0x18001637f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016384  add     rbx, 10h
0x180016388  jmp     loc_18001626A
0x18001638d  mov     rcx, [rbp+57h+var_38]
0x180016391  xor     rcx, rsp; StackCookie
0x180016394  call    __security_check_cookie
0x180016399  add     rsp, 0D8h
0x1800163a0  pop     r15
0x1800163a2  pop     r14
0x1800163a4  pop     rdi
0x1800163a5  pop     rsi
0x1800163a6  pop     rbx
0x1800163a7  pop     rbp
0x1800163a8  retn
```
