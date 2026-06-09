# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180007c0c`
- end: `0x180007de6`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `474`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800096b4`

## callees

- `0x180002e70`
- `0x18000586c`
- `0x18000599c`
- `0x1800059d8`
- `0x1800061c8`
- `0x180007a7c`
- `0x180007c0c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180007c9d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180007c9d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007d96`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007d96`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180007c7f`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180007c7f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007c53`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007c53`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180007cb6`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180007cb6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007d61`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007d61`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v7; // rdi
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v10; // rsi
  unsigned int v11; // eax
  const CHAR *v12; // r14
  DWORD cchWideChar; // esi
  DWORD v14; // eax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  HMODULE v18; // [rsp+38h] [rbp-460h]
  _QWORD v19[3]; // [rsp+48h] [rbp-450h] BYREF
  LPWSTR v20; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v21[1032]; // [rsp+68h] [rbp-430h] BYREF

  v19[2] = 0;
  v19[1] = this;
  v19[0] = 0;
  v20 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v7 = Library;
  v18 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_21:
    if ( v20 != (LPWSTR)v21 )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
    return Error;
  }
  Resource = FindResourceExW(Library, a4, (LPCWSTR)0x65, 0);
  v10 = Resource;
  if ( !Resource )
    goto LABEL_4;
  v12 = (const CHAR *)LoadResource(v7, Resource);
  if ( !v12 )
    goto LABEL_4;
  cchWideChar = SizeofResource(v7, v10);
  v14 = cchWideChar + 1;
  if ( cchWideChar + 1 >= cchWideChar )
  {
    try
    {
      if ( cchWideChar == -1 )
        goto LABEL_14;
      if ( 0xFFFFFFFFFFFFFFFFuLL / v14 < 2 )
        ATL::AtlThrowImpl(-2147024809);
      if ( 2 * (unsigned __int64)v14 <= 0x400 )
      {
LABEL_14:
        lpWideCharStr = (WCHAR *)v21;
        v20 = (LPWSTR)v21;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v20, 2LL * v14);
        lpWideCharStr = v20;
      }
    }
    catch ( ... )
    {
      v7 = v18;
      lpWideCharStr = v20;
    }
    if ( !lpWideCharStr )
    {
      Error = -2147024882;
LABEL_20:
      FreeLibrary(v7);
      goto LABEL_21;
    }
    v17 = MultiByteToWideChar(3u, 0, v12, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v17 )
    {
      v20[v17] = 0;
      v11 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v19, v20, a5);
      goto LABEL_19;
    }
LABEL_4:
    v11 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v11;
    goto LABEL_20;
  }
  if ( v20 != (LPWSTR)v21 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180007c0c  mov     [rsp+arg_0], rbx
0x180007c11  push    rsi
0x180007c12  push    rdi
0x180007c13  push    r14
0x180007c15  sub     rsp, 480h
0x180007c1c  mov     rax, cs:__security_cookie
0x180007c23  xor     rax, rsp
0x180007c26  mov     [rsp+498h+var_28], rax
0x180007c2e  mov     rsi, r9
0x180007c31  mov     rax, rdx
0x180007c34  xor     ebx, ebx
0x180007c36  mov     [rsp+498h+var_440], rbx
0x180007c3b  mov     [rsp+498h+var_448], rcx
0x180007c40  mov     [rsp+498h+var_450], rbx
0x180007c45  mov     [rsp+498h+var_438], rbx
0x180007c4a  xor     edx, edx; hFile
0x180007c4c  lea     r8d, [rbx+2]; dwFlags
0x180007c50  mov     rcx, rax; lpLibFileName
0x180007c53  call    cs:__imp_LoadLibraryExW
0x180007c59  mov     rdi, rax
0x180007c5c  mov     [rsp+498h+var_460], rax
0x180007c61  test    rax, rax
0x180007c64  jnz     short loc_180007C72
0x180007c66  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180007c6b  mov     ebx, eax
0x180007c6d  jmp     loc_180007D9D
0x180007c72  xor     r9d, r9d; wLanguage
0x180007c75  lea     r8d, [r9+65h]; lpName
0x180007c79  mov     rdx, rsi; lpType
0x180007c7c  mov     rcx, rdi; hModule
0x180007c7f  call    cs:__imp_FindResourceExW
0x180007c85  mov     rsi, rax
0x180007c88  test    rax, rax
0x180007c8b  jnz     short loc_180007C97
0x180007c8d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180007c92  jmp     loc_180007D91
0x180007c97  mov     rdx, rsi; hResInfo
0x180007c9a  mov     rcx, rdi; hModule
0x180007c9d  call    cs:__imp_LoadResource
0x180007ca3  mov     r14, rax
0x180007ca6  mov     [rsp+498h+var_458], rax
0x180007cab  test    rax, rax
0x180007cae  jz      short loc_180007C8D
0x180007cb0  mov     rdx, rsi; hResInfo
0x180007cb3  mov     rcx, rdi; hModule
0x180007cb6  call    cs:__imp_SizeofResource
0x180007cbc  mov     esi, eax
0x180007cbe  mov     [rsp+498h+var_468], eax
0x180007cc2  inc     eax
0x180007cc4  cmp     eax, esi
0x180007cc6  jnb     short loc_180007CE9
0x180007cc8  lea     rax, [rsp+498h+var_430]
0x180007ccd  cmp     [rsp+498h+var_438], rax
0x180007cd2  jz      short loc_180007CDF
0x180007cd4  lea     rcx, [rsp+498h+var_438]
0x180007cd9  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180007cde  nop
0x180007cdf  mov     eax, 8007000Eh
0x180007ce4  jmp     loc_180007DB6
0x180007ce9  test    eax, eax
0x180007ceb  jz      short loc_180007D20
0x180007ced  mov     ecx, eax
0x180007cef  xor     edx, edx
0x180007cf1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007cf5  div     rcx
0x180007cf8  cmp     rax, 2
0x180007cfc  jb      loc_180007DDA
0x180007d02  lea     rdx, [rcx+rcx]
0x180007d06  cmp     rdx, 400h
0x180007d0d  jbe     short loc_180007D20
0x180007d0f  lea     rcx, [rsp+498h+var_438]
0x180007d14  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180007d19  mov     rax, [rsp+498h+var_438]
0x180007d1e  jmp     short loc_180007D2A
0x180007d20  lea     rax, [rsp+498h+var_430]
0x180007d25  mov     [rsp+498h+var_438], rax
0x180007d2a  jmp     short loc_180007D41
0x180007d2c  xor     ebx, ebx
0x180007d2e  mov     rdi, [rsp+498h+var_460]
0x180007d33  mov     r14, [rsp+498h+var_458]
0x180007d38  mov     esi, [rsp+498h+var_468]
0x180007d3c  mov     rax, [rsp+498h+var_438]
0x180007d41  test    rax, rax
0x180007d44  jnz     short loc_180007D4D
0x180007d46  mov     ebx, 8007000Eh
0x180007d4b  jmp     short loc_180007D93
0x180007d4d  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x180007d51  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180007d56  mov     r9d, esi; cbMultiByte
0x180007d59  mov     r8, r14; lpMultiByteStr
0x180007d5c  xor     edx, edx; dwFlags
0x180007d5e  lea     ecx, [rdx+3]; CodePage
0x180007d61  call    cs:__imp_MultiByteToWideChar
0x180007d67  test    eax, eax
0x180007d69  jz      loc_180007C8D
0x180007d6f  mov     ecx, eax
0x180007d71  mov     rax, [rsp+498h+var_438]
0x180007d76  mov     [rax+rcx*2], bx
0x180007d7a  mov     r8d, [rsp+498h+arg_20]; int
0x180007d82  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180007d87  lea     rcx, [rsp+498h+var_450]; this
0x180007d8c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180007d91  mov     ebx, eax
0x180007d93  mov     rcx, rdi; hLibModule
0x180007d96  call    cs:__imp_FreeLibrary
0x180007d9c  nop
0x180007d9d  lea     rax, [rsp+498h+var_430]
0x180007da2  cmp     [rsp+498h+var_438], rax
0x180007da7  jz      short loc_180007DB4
0x180007da9  lea     rcx, [rsp+498h+var_438]
0x180007dae  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180007db3  nop
0x180007db4  mov     eax, ebx
0x180007db6  mov     rcx, [rsp+498h+var_28]
0x180007dbe  xor     rcx, rsp; StackCookie
0x180007dc1  call    __security_check_cookie
0x180007dc6  mov     rbx, [rsp+498h+arg_0]
0x180007dce  add     rsp, 480h
0x180007dd5  pop     r14
0x180007dd7  pop     rdi
0x180007dd8  pop     rsi
0x180007dd9  retn
0x180007dda  mov     ecx, 80070057h; int
0x180007ddf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
