# PCLmWriter::CharHelper::ToString(double,uint)

- ea: `0x18001a61c`
- end: `0x18001a74c`
- name: `?ToString@CharHelper@PCLmWriter@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@NI@Z`
- size: `304`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180017d98`
- `0x18001806c`
- `0x180019930`

## callees

- `0x1800015f0`
- `0x180002148`
- `0x18000bffc`
- `0x18000f3e0`
- `0x180010050`
- `0x18001a61c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a6ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a6ec`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001a6e2`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001a6e2`

## pseudocode

```c
__int64 __fastcall PCLmWriter::CharHelper::ToString(__int64 a1, float a2, unsigned int a3)
{
  unsigned int v5; // eax
  signed int LastError; // eax
  unsigned int lpMultiByteStr; // [rsp+20h] [rbp-4A8h]
  CHAR MultiByteStr[368]; // [rsp+50h] [rbp-478h] BYREF
  WCHAR WideCharStr[360]; // [rsp+1C0h] [rbp-308h] BYREF

  memset_0(MultiByteStr, 0, 0x168u);
  memset_0(WideCharStr, 0, sizeof(WideCharStr));
  v5 = StringCchPrintfW(WideCharStr, 0x168u, L"%.*lf", a3);
  PrintCore::ThrowIfError(
    (PrintCore *)v5,
    (int)"Unspecified.",
    "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pclm\\lib\\utils.cpp",
    (const char *)0x5B,
    LODWORD(a2));
  if ( !WideCharToMultiByte(0xFDE9u, 0, WideCharStr, 360, MultiByteStr, 360, 0, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PrintCore::ThrowIfError(
      (PrintCore *)(unsigned int)LastError,
      (int)"Unspecified.",
      "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pclm\\lib\\utils.cpp",
      (const char *)0x5E,
      lpMultiByteStr);
  }
  std::string::string(a1, MultiByteStr);
  return a1;
}

```

## disassembly

```asm
0x18001a61c  mov     rax, rsp
0x18001a61f  push    rbx
0x18001a620  push    rsi
0x18001a621  push    rdi
0x18001a622  sub     rsp, 4B0h
0x18001a629  movaps  xmmword ptr [rax-28h], xmm6
0x18001a62d  mov     rax, cs:__security_cookie
0x18001a634  xor     rax, rsp
0x18001a637  mov     [rsp+4C8h+var_38], rax
0x18001a63f  mov     ebx, r8d
0x18001a642  mov     [rsp+4C8h+var_480], rcx
0x18001a647  mov     rdi, rcx
0x18001a64a  mov     esi, 168h
0x18001a64f  mov     r8d, esi; Size
0x18001a652  lea     rcx, [rsp+4C8h+MultiByteStr]; void *
0x18001a657  xor     edx, edx; Val
0x18001a659  movaps  xmm6, xmm1
0x18001a65c  call    memset_0
0x18001a661  xor     edx, edx; Val
0x18001a663  lea     rcx, [rsp+4C8h+WideCharStr]; void *
0x18001a66b  mov     r8d, 2D0h; Size
0x18001a671  call    memset_0
0x18001a676  mov     r9d, ebx
0x18001a679  movsd   [rsp+4C8h+lpMultiByteStr], xmm6; unsigned int
0x18001a67f  lea     r8, aLf; "%.*lf"
0x18001a686  mov     edx, esi; unsigned __int64
0x18001a688  lea     rcx, [rsp+4C8h+WideCharStr]; unsigned __int16 *
0x18001a690  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a695  mov     r9d, 5Bh ; '['; char *
0x18001a69b  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\drivers\\"...
0x18001a6a2  lea     rdx, aUnspecified; "Unspecified."
0x18001a6a9  mov     ecx, eax; this
0x18001a6ab  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18001a6b0  mov     [rsp+4C8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001a6b9  lea     rax, [rsp+4C8h+MultiByteStr]
0x18001a6be  mov     [rsp+4C8h+lpDefaultChar], 0; lpDefaultChar
0x18001a6c7  lea     r8, [rsp+4C8h+WideCharStr]; lpWideCharStr
0x18001a6cf  mov     [rsp+4C8h+cbMultiByte], esi; cbMultiByte
0x18001a6d3  mov     r9d, esi; cchWideChar
0x18001a6d6  xor     edx, edx; dwFlags
0x18001a6d8  mov     [rsp+4C8h+lpMultiByteStr], rax; unsigned int
0x18001a6dd  mov     ecx, 0FDE9h; CodePage
0x18001a6e2  call    cs:__imp_WideCharToMultiByte
0x18001a6e8  test    eax, eax
0x18001a6ea  jnz     short loc_18001A719
0x18001a6ec  call    cs:__imp_GetLastError
0x18001a6f2  test    eax, eax
0x18001a6f4  jle     short loc_18001A6FE
0x18001a6f6  movzx   eax, ax
0x18001a6f9  or      eax, 80070000h
0x18001a6fe  mov     r9d, 5Eh ; '^'; char *
0x18001a704  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\drivers\\"...
0x18001a70b  lea     rdx, aUnspecified; "Unspecified."
0x18001a712  mov     ecx, eax; this
0x18001a714  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18001a719  lea     rdx, [rsp+4C8h+MultiByteStr]
0x18001a71e  mov     rcx, rdi
0x18001a721  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001a726  mov     rax, rdi
0x18001a729  mov     rcx, [rsp+4C8h+var_38]
0x18001a731  xor     rcx, rsp; StackCookie
0x18001a734  call    __security_check_cookie
0x18001a739  movaps  xmm6, [rsp+4C8h+var_28]
0x18001a741  add     rsp, 4B0h
0x18001a748  pop     rdi
0x18001a749  pop     rsi
0x18001a74a  pop     rbx
0x18001a74b  retn
```
