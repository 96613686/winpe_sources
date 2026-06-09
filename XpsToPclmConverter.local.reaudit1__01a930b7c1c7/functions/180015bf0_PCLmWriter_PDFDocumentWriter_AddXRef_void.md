# PCLmWriter::PDFDocumentWriter::_AddXRef(void)

- ea: `0x180015bf0`
- end: `0x180015ddd`
- name: `?_AddXRef@PDFDocumentWriter@PCLmWriter@@AEAAXXZ`
- size: `493`
- prototype: `void __fastcall(PCLmWriter::PDFDocumentWriter *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800152f4`

## callees

- `0x1800015f0`
- `0x180002148`
- `0x18000bffc`
- `0x180010050`
- `0x1800101cc`
- `0x180013780`
- `0x180014538`
- `0x180015bf0`
- `0x180015de4`
- `0x180016a54`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d55`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180015d4b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180015d4b`

## string_xrefs

- `0x180015d08`: `onecoreuap\printscan\print\drivers\renderlibrary\pclm\lib\pdfdocumentwriter.cpp`
- `0x180015d6d`: `onecoreuap\printscan\print\drivers\renderlibrary\pclm\lib\pdfdocumentwriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PCLmWriter::PDFDocumentWriter::_AddXRef(PCLmWriter::PDFDocumentWriter *this)
{
  unsigned int v2; // ebx
  __int64 *v3; // rax
  __int64 v4; // rcx
  std::_Ref_count_base *v5; // rsi
  _QWORD *v6; // rax
  unsigned int v7; // eax
  signed int LastError; // eax
  __int64 v9; // rdi
  void (__fastcall *v10)(__int64, CHAR *, size_t); // rbx
  size_t v11; // rax
  unsigned int lpMultiByteStr; // [rsp+20h] [rbp-89h]
  unsigned int lpMultiByteStra; // [rsp+20h] [rbp-89h]
  int v14; // [rsp+40h] [rbp-69h] BYREF
  __int128 v15; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v16[8]; // [rsp+58h] [rbp-51h] BYREF
  std::_Ref_count_base *v17; // [rsp+60h] [rbp-49h]
  CHAR MultiByteStr[16]; // [rsp+68h] [rbp-41h] BYREF
  _BYTE v19[19]; // [rsp+78h] [rbp-31h] BYREF
  WCHAR WideCharStr[40]; // [rsp+90h] [rbp-19h] BYREF

  memset_0(WideCharStr, 0, 0x46u);
  *(_OWORD *)MultiByteStr = 0;
  memset(v19, 0, sizeof(v19));
  (*(void (__fastcall **)(_QWORD, char *, __int64))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2), "\n", 1);
  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
  v15 = 0;
  PCLmWriter::PDFDocumentWriter::_AddXRefSection(this);
  v3 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, _QWORD))(**(_QWORD **)this + 96LL))(
                    *(_QWORD *)this,
                    v16,
                    0,
                    v2);
  v4 = *v3;
  v5 = (std::_Ref_count_base *)v3[1];
  *v3 = 0;
  v3[1] = 0;
  *(_QWORD *)&v15 = v4;
  *((_QWORD *)&v15 + 1) = v5;
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  v14 = 0;
  v6 = (_QWORD *)std::map<unsigned int,std::shared_ptr<PCLmWriter::IXrefEntry>>::_Try_emplace<unsigned int,>(
                   *((_QWORD *)this + 7),
                   v16,
                   &v14);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(*v6 + 40LL, &v15);
  v7 = StringCchPrintfW(WideCharStr, 0x23u, L"\nstartxref\n%u\n%%%%EOF\n", v2);
  PrintCore::ThrowIfError(
    (PrintCore *)v7,
    (int)"Unspecified.",
    "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pclm\\lib\\pdfdocumentwriter.cpp",
    (const char *)0xFA,
    lpMultiByteStr);
  if ( !WideCharToMultiByte(0xFDE9u, 0, WideCharStr, 35, MultiByteStr, 35, 0, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PrintCore::ThrowIfError(
      (PrintCore *)(unsigned int)LastError,
      (int)"Unspecified.",
      "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pclm\\lib\\pdfdocumentwriter.cpp",
      (const char *)0xFD,
      lpMultiByteStra);
  }
  v9 = *((_QWORD *)this + 2);
  v10 = *(void (__fastcall **)(__int64, CHAR *, size_t))(*(_QWORD *)v9 + 24LL);
  v11 = strnlen_s(MultiByteStr, 0x23u);
  v10(v9, MultiByteStr, v11);
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
}

```

## disassembly

```asm
0x180015bf0  mov     [rsp-8+arg_8], rbx
0x180015bf5  mov     [rsp-8+arg_10], rsi
0x180015bfa  push    rbp
0x180015bfb  push    rdi
0x180015bfc  push    r15
0x180015bfe  lea     rbp, [rsp-47h]
0x180015c03  sub     rsp, 0F0h
0x180015c0a  mov     rax, cs:__security_cookie
0x180015c11  xor     rax, rsp
0x180015c14  mov     [rbp+57h+var_20], rax
0x180015c18  mov     rdi, rcx
0x180015c1b  xor     edx, edx; Val
0x180015c1d  lea     r8d, [rdx+46h]; Size
0x180015c21  lea     rcx, [rbp+57h+WideCharStr]; void *
0x180015c25  call    memset_0
0x180015c2a  xorps   xmm0, xmm0
0x180015c2d  xor     eax, eax
0x180015c2f  movups  xmmword ptr [rbp+57h+MultiByteStr], xmm0
0x180015c33  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x180015c37  mov     dword ptr [rbp+57h+var_88+0Fh], eax
0x180015c3a  mov     rcx, [rdi+10h]
0x180015c3e  mov     rax, [rcx]
0x180015c41  mov     r8d, 1
0x180015c47  lea     rdx, asc_180025754+1; "\n"
0x180015c4e  mov     rax, [rax+18h]
0x180015c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c57  mov     rcx, [rdi+10h]
0x180015c5b  mov     rax, [rcx]
0x180015c5e  mov     rax, [rax+10h]
0x180015c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c67  mov     ebx, eax
0x180015c69  xorps   xmm0, xmm0
0x180015c6c  movdqu  [rbp+57h+var_B8], xmm0
0x180015c71  mov     rcx, rdi; this
0x180015c74  call    ?_AddXRefSection@PDFDocumentWriter@PCLmWriter@@AEAAXXZ; PCLmWriter::PDFDocumentWriter::_AddXRefSection(void)
0x180015c79  mov     rcx, [rdi]
0x180015c7c  mov     rdx, [rcx]
0x180015c7f  mov     r9d, ebx
0x180015c82  mov     rax, [rdx+60h]
0x180015c86  xor     r8d, r8d
0x180015c89  lea     rdx, [rbp+57h+var_A8]
0x180015c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c92  mov     rcx, [rax]
0x180015c95  mov     rsi, [rax+8]
0x180015c99  mov     qword ptr [rax], 0
0x180015ca0  mov     qword ptr [rax+8], 0
0x180015ca8  mov     qword ptr [rbp+57h+var_B8], rcx
0x180015cac  mov     qword ptr [rbp+57h+var_B8+8], rsi
0x180015cb0  mov     rcx, [rbp+57h+var_A0]; this
0x180015cb4  test    rcx, rcx
0x180015cb7  jz      short loc_180015CBE
0x180015cb9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015cbe  mov     [rbp+57h+var_C0], 0
0x180015cc5  lea     r8, [rbp+57h+var_C0]
0x180015cc9  lea     rdx, [rbp+57h+var_A8]
0x180015ccd  mov     rcx, [rdi+38h]
0x180015cd1  call    ??$_Try_emplace@I$$V@?$map@IV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@std@@_N@1@$$QEAI@Z; std::map<uint,std::shared_ptr<PCLmWriter::IXrefEntry>>::_Try_emplace<uint,>(uint &&)
0x180015cd6  mov     rcx, [rax]
0x180015cd9  add     rcx, 28h ; '('
0x180015cdd  lea     rdx, [rbp+57h+var_B8]
0x180015ce1  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x180015ce6  mov     r9d, ebx
0x180015ce9  lea     r8, aStartxrefUEof; "\nstartxref\n%u\n%%%%EOF\n"
0x180015cf0  mov     r15d, 23h ; '#'
0x180015cf6  mov     edx, r15d; unsigned __int64
0x180015cf9  lea     rcx, [rbp+57h+WideCharStr]; unsigned __int16 *
0x180015cfd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015d02  mov     r9d, 0FAh; char *
0x180015d08  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\drivers\\"...
0x180015d0f  lea     rdx, aUnspecified; "Unspecified."
0x180015d16  mov     ecx, eax; this
0x180015d18  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180015d1d  mov     [rsp+100h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180015d26  mov     [rsp+100h+lpDefaultChar], 0; lpDefaultChar
0x180015d2f  mov     [rsp+100h+cbMultiByte], r15d; cbMultiByte
0x180015d34  lea     rax, [rbp+57h+MultiByteStr]
0x180015d38  mov     [rsp+100h+lpMultiByteStr], rax; unsigned int
0x180015d3d  mov     r9d, r15d; cchWideChar
0x180015d40  lea     r8, [rbp+57h+WideCharStr]; lpWideCharStr
0x180015d44  xor     edx, edx; dwFlags
0x180015d46  mov     ecx, 0FDE9h; CodePage
0x180015d4b  call    cs:__imp_WideCharToMultiByte
0x180015d51  test    eax, eax
0x180015d53  jnz     short loc_180015D82
0x180015d55  call    cs:__imp_GetLastError
0x180015d5b  test    eax, eax
0x180015d5d  jle     short loc_180015D67
0x180015d5f  movzx   eax, ax
0x180015d62  or      eax, 80070000h
0x180015d67  mov     r9d, 0FDh; char *
0x180015d6d  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\drivers\\"...
0x180015d74  lea     rdx, aUnspecified; "Unspecified."
0x180015d7b  mov     ecx, eax; this
0x180015d7d  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180015d82  mov     rdi, [rdi+10h]
0x180015d86  mov     rax, [rdi]
0x180015d89  mov     rbx, [rax+18h]
0x180015d8d  mov     rdx, r15; MaxCount
0x180015d90  lea     rcx, [rbp+57h+MultiByteStr]; String
0x180015d94  call    strnlen_s
0x180015d99  mov     r8, rax
0x180015d9c  lea     rdx, [rbp+57h+MultiByteStr]
0x180015da0  mov     rcx, rdi
0x180015da3  mov     rax, rbx
0x180015da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dab  nop
0x180015dac  test    rsi, rsi
0x180015daf  jz      short loc_180015DB9
0x180015db1  mov     rcx, rsi; this
0x180015db4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015db9  mov     rcx, [rbp+57h+var_20]
0x180015dbd  xor     rcx, rsp; StackCookie
0x180015dc0  call    __security_check_cookie
0x180015dc5  lea     r11, [rsp+100h+var_10]
0x180015dcd  mov     rbx, [r11+28h]
0x180015dd1  mov     rsi, [r11+30h]
0x180015dd5  mov     rsp, r11
0x180015dd8  pop     r15
0x180015dda  pop     rdi
0x180015ddb  pop     rbp
0x180015ddc  retn
```
