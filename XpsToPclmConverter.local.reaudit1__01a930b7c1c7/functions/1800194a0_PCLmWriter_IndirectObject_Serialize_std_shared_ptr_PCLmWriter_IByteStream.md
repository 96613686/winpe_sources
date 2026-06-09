# PCLmWriter::IndirectObject::Serialize(std::shared_ptr<PCLmWriter::IByteStream>)

- ea: `0x1800194a0`
- end: `0x180019604`
- name: `?Serialize@IndirectObject@PCLmWriter@@UEBAXV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@Z`
- size: `356`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800015f0`
- `0x18000bffc`
- `0x180010050`
- `0x1800101cc`
- `0x180016a54`
- `0x1800194a0`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001957b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001957b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180019571`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180019571`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PCLmWriter::IndirectObject::Serialize(__int64 a1, _QWORD *a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // eax
  signed int LastError; // eax
  __int64 v8; // rdi
  void (__fastcall *v9)(__int64, CHAR *, size_t); // rbx
  size_t v10; // rax
  std::_Ref_count_base *v11; // rcx
  unsigned int lpMultiByteStr; // [rsp+20h] [rbp-98h]
  CHAR MultiByteStr[16]; // [rsp+48h] [rbp-70h] BYREF
  __int64 v14; // [rsp+58h] [rbp-60h]
  WCHAR WideCharStr[8]; // [rsp+60h] [rbp-58h] BYREF
  __int128 v16; // [rsp+70h] [rbp-48h]
  __int128 v17; // [rsp+80h] [rbp-38h]

  *(_OWORD *)MultiByteStr = 0;
  v14 = 0;
  *(_OWORD *)WideCharStr = 0;
  v16 = 0;
  v17 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  v6 = StringCchPrintfW(WideCharStr, 0x18u, L"%d %d R", v5);
  PrintCore::ThrowIfError(
    (PrintCore *)v6,
    (int)"Unspecified.",
    "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pclm\\lib\\pdfobjects.cpp",
    (const char *)0x8E,
    v4);
  if ( !WideCharToMultiByte(0xFDE9u, 0, WideCharStr, 24, MultiByteStr, 24, 0, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PrintCore::ThrowIfError(
      (PrintCore *)(unsigned int)LastError,
      (int)"Unspecified.",
      "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pclm\\lib\\pdfobjects.cpp",
      (const char *)0x91,
      lpMultiByteStr);
  }
  v8 = *a2;
  v9 = *(void (__fastcall **)(__int64, CHAR *, size_t))(*(_QWORD *)*a2 + 24LL);
  v10 = strnlen_s(MultiByteStr, 0x18u);
  v9(v8, MultiByteStr, v10);
  v11 = (std::_Ref_count_base *)a2[1];
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
}

```

## disassembly

```asm
0x1800194a0  mov     r11, rsp
0x1800194a3  mov     [r11+18h], rbx
0x1800194a7  push    rbp
0x1800194a8  push    rsi
0x1800194a9  push    rdi
0x1800194aa  sub     rsp, 0A0h
0x1800194b1  mov     rax, cs:__security_cookie
0x1800194b8  xor     rax, rsp
0x1800194bb  mov     [rsp+0B8h+var_28], rax
0x1800194c3  mov     rsi, rdx
0x1800194c6  mov     rdi, rcx
0x1800194c9  mov     [r11-78h], rdx
0x1800194cd  xorps   xmm0, xmm0
0x1800194d0  xor     eax, eax
0x1800194d2  movups  xmmword ptr [rsp+0B8h+MultiByteStr], xmm0
0x1800194d7  mov     [r11-60h], rax
0x1800194db  xorps   xmm1, xmm1
0x1800194de  movups  xmmword ptr [rsp+0B8h+WideCharStr], xmm1
0x1800194e3  movups  [rsp+0B8h+var_48], xmm1
0x1800194e8  movups  xmmword ptr [r11-38h], xmm1
0x1800194ed  mov     rax, [rcx]
0x1800194f0  mov     rax, [rax+18h]
0x1800194f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194f9  mov     ebx, eax
0x1800194fb  mov     rdx, [rdi]
0x1800194fe  mov     rcx, rdi
0x180019501  mov     rax, [rdx+10h]
0x180019505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001950a  mov     dword ptr [rsp+0B8h+lpMultiByteStr], ebx; unsigned int
0x18001950e  mov     r9d, eax
0x180019511  lea     r8, aDDR; "%d %d R"
0x180019518  mov     ebp, 18h
0x18001951d  mov     edx, ebp; unsigned __int64
0x18001951f  lea     rcx, [rsp+0B8h+WideCharStr]; unsigned __int16 *
0x180019524  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019529  lea     r9d, [rbp+76h]; char *
0x18001952d  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x180019534  lea     rdx, aUnspecified; "Unspecified."
0x18001953b  mov     ecx, eax; this
0x18001953d  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180019542  mov     [rsp+0B8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001954b  mov     [rsp+0B8h+lpDefaultChar], 0; lpDefaultChar
0x180019554  mov     [rsp+0B8h+cbMultiByte], ebp; cbMultiByte
0x180019558  lea     rax, [rsp+0B8h+MultiByteStr]
0x18001955d  mov     [rsp+0B8h+lpMultiByteStr], rax; unsigned int
0x180019562  mov     r9d, ebp; cchWideChar
0x180019565  lea     r8, [rsp+0B8h+WideCharStr]; lpWideCharStr
0x18001956a  xor     edx, edx; dwFlags
0x18001956c  mov     ecx, 0FDE9h; CodePage
0x180019571  call    cs:__imp_WideCharToMultiByte
0x180019577  test    eax, eax
0x180019579  jnz     short loc_1800195A8
0x18001957b  call    cs:__imp_GetLastError
0x180019581  test    eax, eax
0x180019583  jle     short loc_18001958D
0x180019585  movzx   eax, ax
0x180019588  or      eax, 80070000h
0x18001958d  mov     r9d, 91h; char *
0x180019593  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18001959a  lea     rdx, aUnspecified; "Unspecified."
0x1800195a1  mov     ecx, eax; this
0x1800195a3  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x1800195a8  mov     rdi, [rsi]
0x1800195ab  mov     rax, [rdi]
0x1800195ae  mov     rbx, [rax+18h]
0x1800195b2  mov     rdx, rbp; MaxCount
0x1800195b5  lea     rcx, [rsp+0B8h+MultiByteStr]; String
0x1800195ba  call    strnlen_s
0x1800195bf  mov     r8, rax
0x1800195c2  lea     rdx, [rsp+0B8h+MultiByteStr]
0x1800195c7  mov     rcx, rdi
0x1800195ca  mov     rax, rbx
0x1800195cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195d2  nop
0x1800195d3  mov     rcx, [rsi+8]; this
0x1800195d7  test    rcx, rcx
0x1800195da  jz      short loc_1800195E1
0x1800195dc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800195e1  mov     rcx, [rsp+0B8h+var_28]
0x1800195e9  xor     rcx, rsp; StackCookie
0x1800195ec  call    __security_check_cookie
0x1800195f1  mov     rbx, [rsp+0B8h+arg_10]
0x1800195f9  add     rsp, 0A0h
0x180019600  pop     rdi
0x180019601  pop     rsi
0x180019602  pop     rbp
0x180019603  retn
```
