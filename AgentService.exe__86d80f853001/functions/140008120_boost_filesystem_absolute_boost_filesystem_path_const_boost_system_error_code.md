# boost::filesystem::absolute(boost::filesystem::path const &,boost::system::error_code &)

- ea: `0x140008120`
- end: `0x1400082a4`
- name: `?absolute@filesystem@boost@@YA?AVpath@12@AEBV312@AEAVerror_code@system@2@@Z`
- size: `388`
- prototype: `struct boost::filesystem::path __high(const struct boost::filesystem::path *, struct boost::system::error_code *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140007a70`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x140003fcc`
- `0x140007450`
- `0x140007a70`
- `0x140008120`
- `0x14000ac03`
- `0x14000c2b8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000819a`
- `KERNEL32!GetLastError` at `0x14000819a`
- `KERNEL32!GetCurrentDirectoryW` at `0x140008154`
- `KERNEL32!GetCurrentDirectoryW` at `0x140008190`
- `KERNEL32!GetCurrentDirectoryW` at `0x140008154`
- `KERNEL32!GetCurrentDirectoryW` at `0x140008190`

## string_xrefs

- `0x1400081a4`: `boost::filesystem::current_path`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall boost::filesystem::absolute(__int64 a1, boost::filesystem::path *a2, __int64 a3)
{
  DWORD CurrentDirectoryW; // ebx
  WCHAR *v7; // rbp
  DWORD LastError; // eax
  const char *v9; // r9
  size_t v10; // rax
  __int64 v11; // rax
  void *v12; // rcx
  void *Block[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v15; // [rsp+40h] [rbp-48h]
  unsigned __int64 v16; // [rsp+48h] [rbp-40h]

  CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
  if ( !CurrentDirectoryW )
    CurrentDirectoryW = 1;
  v7 = (WCHAR *)operator new[](saturated_mul(CurrentDirectoryW, 2u));
  if ( GetCurrentDirectoryW(CurrentDirectoryW, v7) || (LastError = GetLastError()) == 0 )
  {
    if ( a3 )
    {
      *(_OWORD *)a3 = 0;
      *(_QWORD *)(a3 + 16) = 0;
    }
  }
  else
  {
    boost::filesystem::emit_error(
      (boost::filesystem *)LastError,
      a3,
      (struct boost::system::error_code *)"boost::filesystem::current_path",
      v9);
  }
  *(_OWORD *)Block = 0;
  v15 = 0;
  v16 = 0;
  v10 = wcslen_0(v7);
  std::wstring::_Construct<1,wchar_t *>(Block, v7, v10);
  operator delete(v7);
  v11 = *(_QWORD *)(a3 + 16);
  if ( (v11 & 1) != 0 && (v11 != 1 || *(_DWORD *)a3) )
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 7;
    *(_WORD *)a1 = 0;
  }
  else
  {
    boost::filesystem::detail::absolute(a1, a2, (boost::filesystem::path *)Block, a3);
  }
  if ( v16 > 7 )
  {
    if ( 2 * v16 + 2 < 0x1000 )
    {
      v12 = Block[0];
    }
    else
    {
      v12 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v12 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v12);
  }
  return a1;
}

```

## disassembly

```asm
0x140008120  mov     [rsp+arg_18], rbx
0x140008125  push    rbp
0x140008126  push    rsi
0x140008127  push    rdi
0x140008128  push    r14
0x14000812a  push    r15
0x14000812c  sub     rsp, 60h
0x140008130  mov     rax, cs:__security_cookie
0x140008137  xor     rax, rsp
0x14000813a  mov     [rsp+88h+var_38], rax
0x14000813f  mov     rdi, r8
0x140008142  mov     r14, rdx
0x140008145  mov     rsi, rcx
0x140008148  mov     [rsp+88h+var_60], rcx
0x14000814d  xor     r15d, r15d
0x140008150  xor     edx, edx; lpBuffer
0x140008152  xor     ecx, ecx; nBufferLength
0x140008154  call    cs:__imp_GetCurrentDirectoryW
0x14000815a  mov     ebx, eax
0x14000815c  mov     eax, 1
0x140008161  test    ebx, ebx
0x140008163  cmovz   ebx, eax
0x140008166  mov     edx, ebx
0x140008168  mov     eax, 2
0x14000816d  mul     rdx
0x140008170  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140008177  cmovb   rax, rcx
0x14000817b  mov     rcx, rax; unsigned __int64
0x14000817e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140008183  mov     rbp, rax
0x140008186  mov     [rsp+88h+var_60], rax
0x14000818b  mov     rdx, rax; lpBuffer
0x14000818e  mov     ecx, ebx; nBufferLength
0x140008190  call    cs:__imp_GetCurrentDirectoryW
0x140008196  test    eax, eax
0x140008198  jnz     short loc_1400081B7
0x14000819a  call    cs:__imp_GetLastError
0x1400081a0  test    eax, eax
0x1400081a2  jz      short loc_1400081B7
0x1400081a4  lea     r8, aBoostFilesyste; "boost::filesystem::current_path"
0x1400081ab  mov     rdx, rdi; unsigned int
0x1400081ae  mov     ecx, eax; this
0x1400081b0  call    ?emit_error@filesystem@boost@@YAXKPEAVerror_code@system@2@PEBD@Z; boost::filesystem::emit_error(ulong,boost::system::error_code *,char const *)
0x1400081b5  jmp     short loc_1400081C6
0x1400081b7  test    rdi, rdi
0x1400081ba  jz      short loc_1400081C6
0x1400081bc  xorps   xmm0, xmm0
0x1400081bf  movups  xmmword ptr [rdi], xmm0
0x1400081c2  mov     [rdi+10h], r15
0x1400081c6  xorps   xmm0, xmm0
0x1400081c9  movups  xmmword ptr [rsp+88h+Block], xmm0
0x1400081ce  mov     [rsp+88h+var_48], r15
0x1400081d3  mov     [rsp+88h+var_40], r15
0x1400081d8  mov     rcx, rbp; String
0x1400081db  call    wcslen_0
0x1400081e0  mov     r8, rax
0x1400081e3  mov     rdx, rbp
0x1400081e6  lea     rcx, [rsp+88h+Block]
0x1400081eb  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1400081f0  nop
0x1400081f1  mov     rcx, rbp; Block
0x1400081f4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400081f9  nop
0x1400081fa  mov     rax, [rdi+10h]
0x1400081fe  test    al, 1
0x140008200  jz      short loc_140008225
0x140008202  cmp     rax, 1
0x140008206  jnz     short loc_14000820D
0x140008208  cmp     dword ptr [rdi], 0
0x14000820b  jz      short loc_140008225
0x14000820d  xorps   xmm0, xmm0
0x140008210  movups  xmmword ptr [rsi], xmm0
0x140008213  mov     [rsi+10h], r15
0x140008217  mov     qword ptr [rsi+18h], 7
0x14000821f  mov     [rsi], r15w
0x140008223  jmp     short loc_140008239
0x140008225  mov     r9, rdi
0x140008228  lea     r8, [rsp+88h+Block]
0x14000822d  mov     rdx, r14
0x140008230  mov     rcx, rsi
0x140008233  call    ?absolute@detail@filesystem@boost@@YA?AVpath@23@AEBV423@0PEAVerror_code@system@3@@Z; boost::filesystem::detail::absolute(boost::filesystem::path const &,boost::filesystem::path const &,boost::system::error_code *)
0x140008238  nop
0x140008239  mov     rdx, [rsp+88h+var_40]
0x14000823e  cmp     rdx, 7
0x140008242  jbe     short loc_140008280
0x140008244  mov     rax, [rsp+88h+Block]
0x140008249  lea     rdx, ds:2[rdx*2]
0x140008251  cmp     rdx, 1000h
0x140008258  jb      short loc_140008278
0x14000825a  mov     rcx, [rax-8]
0x14000825e  sub     rax, rcx
0x140008261  sub     rax, 8
0x140008265  cmp     rax, 1Fh
0x140008269  ja      short loc_140008271
0x14000826b  add     rdx, 27h ; '''
0x14000826f  jmp     short loc_14000827B
0x140008271  mov     ecx, 5
0x140008276  int     29h; Win8: RtlFailFast(ecx)
0x140008278  mov     rcx, rax; Block
0x14000827b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140008280  mov     rax, rsi
0x140008283  mov     rcx, [rsp+88h+var_38]
0x140008288  xor     rcx, rsp; StackCookie
0x14000828b  call    __security_check_cookie
0x140008290  mov     rbx, [rsp+88h+arg_18]
0x140008298  add     rsp, 60h
0x14000829c  pop     r15
0x14000829e  pop     r14
0x1400082a0  pop     rdi
0x1400082a1  pop     rsi
0x1400082a2  pop     rbp
0x1400082a3  retn
```
