# wprt::proc::impl::WindowsPrinterProcessor::CreateTmpFile(SmartHstring &)

- ea: `0x1800046b0`
- end: `0x180004935`
- name: `?CreateTmpFile@WindowsPrinterProcessor@impl@proc@wprt@@AEAAPEAXAEAVSmartHstring@@@Z`
- size: `645`
- prototype: `__int64 __fastcall(wprt::proc::impl::WindowsPrinterProcessor *this, HSTRING *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180004b20`

## callees

- `0x180003180`
- `0x180003580`
- `0x180003d30`
- `0x180003d3c`
- `0x180004110`
- `0x1800046b0`
- `0x1800a02eb`
- `0x1800a94f4`
- `0x1800abad8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800048c4`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800048c4`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180004744`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180004744`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004777`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004777`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800046f6`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800046f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wprt::proc::impl::WindowsPrinterProcessor::CreateTmpFile(
        wprt::proc::impl::WindowsPrinterProcessor *this,
        HSTRING *a2)
{
  unsigned __int64 v3; // rbx
  __int64 FileW; // r15
  int TempPath2W; // edi
  __int64 v6; // rsi
  size_t v7; // rbx
  __int64 v8; // rcx
  unsigned __int64 v9; // rbx
  const WCHAR *v10; // rcx
  HSTRING v11; // rcx
  HRESULT v12; // eax
  HSTRING v13; // rcx
  WCHAR *v14; // rcx
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  PCNZWCH sourceString[2]; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 length[2]; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v19; // [rsp+68h] [rbp-98h]
  WCHAR TempFileName[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR PathName[264]; // [rsp+280h] [rbp+180h] BYREF

  v3 = -1;
  FileW = -1;
  TempPath2W = GetTempPath2W(260, PathName);
  if ( *a2 )
  {
    WindowsDeleteString_0(*a2);
    *a2 = 0;
  }
  WindowsDeleteString_0(0);
  if ( (unsigned int)(TempPath2W - 1) <= 0xF4 && GetTempFileNameW(PathName, L"tmp", 0, TempFileName) )
  {
    FileW = (__int64)CreateFileW(TempFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    *(_OWORD *)sourceString = 0;
    do
      ++v3;
    while ( TempFileName[v3] );
    v6 = 0x7FFFFFFFFFFFFFFELL;
    if ( v3 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    if ( v3 >= 8 )
    {
      if ( (v3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
      {
        v6 = v3 | 7;
        if ( (v3 | 7) < 0xA )
          v6 = 10;
        v8 = v6 + 1;
        if ( (unsigned __int64)(v6 + 1) > 0x7FFFFFFFFFFFFFFFLL )
          std::_Throw_bad_array_new_length();
      }
      else
      {
        v8 = 0x7FFFFFFFFFFFFFFFLL;
      }
      _mm_lfence();
      *(_QWORD *)length = v3;
      v9 = v3;
      sourceString[0] = (PCNZWCH)std::_Allocate<16,std::_Default_allocate_traits,0>(2 * v8);
      v19 = v6;
      memcpy_0((void *)sourceString[0], TempFileName, v9 * 2);
      sourceString[0][v9] = 0;
    }
    else
    {
      *(_QWORD *)length = v3;
      v7 = 2 * v3;
      v19 = 7;
      memcpy_0(sourceString, TempFileName, v7);
      *(_WORD *)((char *)sourceString + v7) = 0;
    }
    v10 = (const WCHAR *)sourceString;
    if ( v19 >= 8 )
      v10 = sourceString[0];
    string = 0;
    WindowsCreateString_0(v10, length[0], &string);
    v11 = string;
    if ( string != *a2 )
    {
      WindowsDeleteString_0(*a2);
      v11 = 0;
      *a2 = string;
      string = 0;
    }
    v12 = WindowsDeleteString_0(v11);
    v13 = string;
    if ( !v12 )
      v13 = 0;
    string = v13;
    if ( v19 >= 8 )
    {
      v14 = (WCHAR *)sourceString[0];
      if ( 2 * v19 + 2 >= 0x1000 )
      {
        v14 = (WCHAR *)*((_QWORD *)sourceString[0] - 1);
        if ( (unsigned __int64)((char *)sourceString[0] - (char *)v14 - 8) > 0x1F )
        {
          _o__invalid_parameter_noinfo_noreturn(v14, 2 * v19 + 41);
          __debugbreak();
        }
      }
      operator delete(v14);
    }
  }
  return FileW;
}

```

## disassembly

```asm
0x1800046b0  mov     [rsp-8+arg_10], rbx
0x1800046b5  push    rbp
0x1800046b6  push    rdi
0x1800046b7  push    r12
0x1800046b9  push    r14
0x1800046bb  push    r15
0x1800046bd  lea     rbp, [rsp-3A0h]
0x1800046c5  sub     rsp, 4A0h
0x1800046cc  mov     rax, cs:__security_cookie
0x1800046d3  xor     rax, rsp
0x1800046d6  mov     [rbp+3C0h+var_30], rax
0x1800046dd  mov     r14, rdx
0x1800046e0  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800046e7  lea     rdx, [rbp+3C0h+PathName]
0x1800046ee  mov     ecx, 104h
0x1800046f3  mov     r15, rbx
0x1800046f6  call    cs:__imp_GetTempPath2W
0x1800046fc  mov     rcx, [r14]; string
0x1800046ff  xor     r12d, r12d
0x180004702  mov     edi, eax
0x180004704  test    rcx, rcx
0x180004707  jz      short loc_180004711
0x180004709  call    WindowsDeleteString_0
0x18000470e  mov     [r14], r12
0x180004711  xor     ecx, ecx; string
0x180004713  mov     [rsp+4C0h+arg_0], rsi
0x18000471b  call    WindowsDeleteString_0
0x180004720  lea     eax, [rdi-1]
0x180004723  cmp     eax, 0F4h
0x180004728  ja      loc_1800048F7
0x18000472e  lea     r9, [rsp+4C0h+TempFileName]; lpTempFileName
0x180004733  xor     r8d, r8d; uUnique
0x180004736  lea     rdx, PrefixString; "tmp"
0x18000473d  lea     rcx, [rbp+3C0h+PathName]; lpPathName
0x180004744  call    cs:__imp_GetTempFileNameW
0x18000474a  test    eax, eax
0x18000474c  jz      loc_1800048F7
0x180004752  mov     [rsp+4C0h+hTemplateFile], r12; hTemplateFile
0x180004757  lea     rcx, [rsp+4C0h+TempFileName]; lpFileName
0x18000475c  mov     [rsp+4C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180004764  xor     r9d, r9d; lpSecurityAttributes
0x180004767  xor     r8d, r8d; dwShareMode
0x18000476a  mov     [rsp+4C0h+dwCreationDisposition], 2; dwCreationDisposition
0x180004772  mov     edx, 40000000h; dwDesiredAccess
0x180004777  call    cs:__imp_CreateFileW
0x18000477d  xorps   xmm0, xmm0
0x180004780  mov     r15, rax
0x180004783  movups  xmmword ptr [rsp+4C0h+sourceString], xmm0
0x180004788  lea     rax, [rsp+4C0h+TempFileName]
0x18000478d  nop     dword ptr [rax]
0x180004790  inc     rbx
0x180004793  cmp     [rax+rbx*2], r12w
0x180004798  jnz     short loc_180004790
0x18000479a  mov     rsi, 7FFFFFFFFFFFFFFEh
0x1800047a4  cmp     rbx, rsi
0x1800047a7  ja      loc_180004929
0x1800047ad  cmp     rbx, 8
0x1800047b1  jnb     short loc_1800047DE
0x1800047b3  mov     qword ptr [rsp+4C0h+length], rbx
0x1800047b8  lea     rdx, [rsp+4C0h+TempFileName]; Src
0x1800047bd  add     rbx, rbx
0x1800047c0  mov     [rsp+4C0h+var_458], 7
0x1800047c9  mov     r8, rbx; Size
0x1800047cc  lea     rcx, [rsp+4C0h+sourceString]; void *
0x1800047d1  call    memcpy_0
0x1800047d6  mov     word ptr [rsp+rbx+4C0h+sourceString], r12w
0x1800047dc  jmp     short loc_18000482D
0x1800047de  mov     rax, rbx
0x1800047e1  or      rax, 7
0x1800047e5  cmp     rax, rsi
0x1800047e8  jbe     loc_1800048CB
0x1800047ee  mov     rcx, 7FFFFFFFFFFFFFFFh
0x1800047f8  lfence
0x1800047fb  add     rcx, rcx
0x1800047fe  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@$0A@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits,0>(unsigned __int64)
0x180004803  mov     qword ptr [rsp+4C0h+length], rbx
0x180004808  lea     rdx, [rsp+4C0h+TempFileName]; Src
0x18000480d  add     rbx, rbx
0x180004810  mov     [rsp+4C0h+sourceString], rax
0x180004815  mov     r8, rbx; Size
0x180004818  mov     [rsp+4C0h+var_458], rsi
0x18000481d  mov     rcx, rax; void *
0x180004820  mov     rdi, rax
0x180004823  call    memcpy_0
0x180004828  mov     [rbx+rdi], r12w
0x18000482d  cmp     [rsp+4C0h+var_458], 8
0x180004833  lea     rcx, [rsp+4C0h+sourceString]
0x180004838  mov     edx, [rsp+4C0h+length]; length
0x18000483c  lea     r8, [rsp+4C0h+string]; string
0x180004841  cmovnb  rcx, [rsp+4C0h+sourceString]; sourceString
0x180004847  mov     [rsp+4C0h+string], r12
0x18000484c  call    WindowsCreateString_0
0x180004851  mov     rax, [r14]
0x180004854  mov     rcx, [rsp+4C0h+string]
0x180004859  cmp     rcx, rax
0x18000485c  jz      short loc_180004876
0x18000485e  mov     rcx, rax; string
0x180004861  call    WindowsDeleteString_0
0x180004866  mov     rax, [rsp+4C0h+string]
0x18000486b  mov     rcx, r12; string
0x18000486e  mov     [r14], rax
0x180004871  mov     [rsp+4C0h+string], rcx
0x180004876  call    WindowsDeleteString_0
0x18000487b  mov     rcx, [rsp+4C0h+string]
0x180004880  test    eax, eax
0x180004882  mov     rdx, [rsp+4C0h+var_458]
0x180004887  cmovz   rcx, r12
0x18000488b  mov     [rsp+4C0h+string], rcx
0x180004890  cmp     rdx, 8
0x180004894  jb      short loc_1800048F7
0x180004896  mov     rcx, [rsp+4C0h+sourceString]; Block
0x18000489b  lea     rdx, ds:2[rdx*2]
0x1800048a3  mov     rax, rcx
0x1800048a6  cmp     rdx, 1000h
0x1800048ad  jb      short loc_1800048F2
0x1800048af  mov     rcx, [rcx-8]
0x1800048b3  add     rdx, 27h ; '''
0x1800048b7  sub     rax, rcx
0x1800048ba  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800048be  cmp     rax, 1Fh
0x1800048c2  jbe     short loc_1800048F2
0x1800048c4  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x1800048ca  int     3; Trap to Debugger
0x1800048cb  mov     ecx, 0Ah
0x1800048d0  mov     rsi, rax
0x1800048d3  cmp     rax, rcx
0x1800048d6  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800048e0  cmovb   rsi, rcx
0x1800048e4  lea     rcx, [rsi+1]
0x1800048e8  cmp     rcx, rax
0x1800048eb  ja      short loc_18000492F
0x1800048ed  jmp     loc_1800047F8
0x1800048f2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800048f7  mov     rsi, [rsp+4C0h+arg_0]
0x1800048ff  mov     rax, r15
0x180004902  mov     rcx, [rbp+3C0h+var_30]
0x180004909  xor     rcx, rsp; StackCookie
0x18000490c  call    __security_check_cookie
0x180004911  mov     rbx, [rsp+4C0h+arg_10]
0x180004919  add     rsp, 4A0h
0x180004920  pop     r15
0x180004922  pop     r14
0x180004924  pop     r12
0x180004926  pop     rdi
0x180004927  pop     rbp
0x180004928  retn
0x180004929  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18000492f  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
