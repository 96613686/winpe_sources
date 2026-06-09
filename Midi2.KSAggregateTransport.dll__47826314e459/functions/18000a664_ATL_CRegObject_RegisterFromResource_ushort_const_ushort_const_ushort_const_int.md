# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000a664`
- end: `0x18000a83e`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `474`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000c204`

## callees

- `0x180005020`
- `0x180007f4c`
- `0x18000807c`
- `0x1800080b8`
- `0x18000896c`
- `0x18000a4d4`
- `0x18000a664`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000a70e`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000a70e`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000a6d7`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000a6d7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a7ee`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a7ee`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a6ab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a6ab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000a6f5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000a6f5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000a7b9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000a7b9`

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
0x18000a664  mov     [rsp+arg_0], rbx
0x18000a669  push    rsi
0x18000a66a  push    rdi
0x18000a66b  push    r14
0x18000a66d  sub     rsp, 480h
0x18000a674  mov     rax, cs:__security_cookie
0x18000a67b  xor     rax, rsp
0x18000a67e  mov     [rsp+498h+var_28], rax
0x18000a686  mov     rsi, r9
0x18000a689  mov     rax, rdx
0x18000a68c  xor     ebx, ebx
0x18000a68e  mov     [rsp+498h+var_440], rbx
0x18000a693  mov     [rsp+498h+var_448], rcx
0x18000a698  mov     [rsp+498h+var_450], rbx
0x18000a69d  mov     [rsp+498h+var_438], rbx
0x18000a6a2  xor     edx, edx; hFile
0x18000a6a4  lea     r8d, [rbx+2]; dwFlags
0x18000a6a8  mov     rcx, rax; lpLibFileName
0x18000a6ab  call    cs:__imp_LoadLibraryExW
0x18000a6b1  mov     rdi, rax
0x18000a6b4  mov     [rsp+498h+var_460], rax
0x18000a6b9  test    rax, rax
0x18000a6bc  jnz     short loc_18000A6CA
0x18000a6be  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000a6c3  mov     ebx, eax
0x18000a6c5  jmp     loc_18000A7F5
0x18000a6ca  xor     r9d, r9d; wLanguage
0x18000a6cd  lea     r8d, [r9+65h]; lpName
0x18000a6d1  mov     rdx, rsi; lpType
0x18000a6d4  mov     rcx, rdi; hModule
0x18000a6d7  call    cs:__imp_FindResourceExW
0x18000a6dd  mov     rsi, rax
0x18000a6e0  test    rax, rax
0x18000a6e3  jnz     short loc_18000A6EF
0x18000a6e5  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000a6ea  jmp     loc_18000A7E9
0x18000a6ef  mov     rdx, rsi; hResInfo
0x18000a6f2  mov     rcx, rdi; hModule
0x18000a6f5  call    cs:__imp_LoadResource
0x18000a6fb  mov     r14, rax
0x18000a6fe  mov     [rsp+498h+var_458], rax
0x18000a703  test    rax, rax
0x18000a706  jz      short loc_18000A6E5
0x18000a708  mov     rdx, rsi; hResInfo
0x18000a70b  mov     rcx, rdi; hModule
0x18000a70e  call    cs:__imp_SizeofResource
0x18000a714  mov     esi, eax
0x18000a716  mov     [rsp+498h+var_468], eax
0x18000a71a  inc     eax
0x18000a71c  cmp     eax, esi
0x18000a71e  jnb     short loc_18000A741
0x18000a720  lea     rax, [rsp+498h+var_430]
0x18000a725  cmp     [rsp+498h+var_438], rax
0x18000a72a  jz      short loc_18000A737
0x18000a72c  lea     rcx, [rsp+498h+var_438]
0x18000a731  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000a736  nop
0x18000a737  mov     eax, 8007000Eh
0x18000a73c  jmp     loc_18000A80E
0x18000a741  test    eax, eax
0x18000a743  jz      short loc_18000A778
0x18000a745  mov     ecx, eax
0x18000a747  xor     edx, edx
0x18000a749  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a74d  div     rcx
0x18000a750  cmp     rax, 2
0x18000a754  jb      loc_18000A832
0x18000a75a  lea     rdx, [rcx+rcx]
0x18000a75e  cmp     rdx, 400h
0x18000a765  jbe     short loc_18000A778
0x18000a767  lea     rcx, [rsp+498h+var_438]
0x18000a76c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000a771  mov     rax, [rsp+498h+var_438]
0x18000a776  jmp     short loc_18000A782
0x18000a778  lea     rax, [rsp+498h+var_430]
0x18000a77d  mov     [rsp+498h+var_438], rax
0x18000a782  jmp     short loc_18000A799
0x18000a784  xor     ebx, ebx
0x18000a786  mov     rdi, [rsp+498h+var_460]
0x18000a78b  mov     r14, [rsp+498h+var_458]
0x18000a790  mov     esi, [rsp+498h+var_468]
0x18000a794  mov     rax, [rsp+498h+var_438]
0x18000a799  test    rax, rax
0x18000a79c  jnz     short loc_18000A7A5
0x18000a79e  mov     ebx, 8007000Eh
0x18000a7a3  jmp     short loc_18000A7EB
0x18000a7a5  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x18000a7a9  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18000a7ae  mov     r9d, esi; cbMultiByte
0x18000a7b1  mov     r8, r14; lpMultiByteStr
0x18000a7b4  xor     edx, edx; dwFlags
0x18000a7b6  lea     ecx, [rdx+3]; CodePage
0x18000a7b9  call    cs:__imp_MultiByteToWideChar
0x18000a7bf  test    eax, eax
0x18000a7c1  jz      loc_18000A6E5
0x18000a7c7  mov     ecx, eax
0x18000a7c9  mov     rax, [rsp+498h+var_438]
0x18000a7ce  mov     [rax+rcx*2], bx
0x18000a7d2  mov     r8d, [rsp+498h+arg_20]; int
0x18000a7da  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x18000a7df  lea     rcx, [rsp+498h+var_450]; this
0x18000a7e4  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000a7e9  mov     ebx, eax
0x18000a7eb  mov     rcx, rdi; hLibModule
0x18000a7ee  call    cs:__imp_FreeLibrary
0x18000a7f4  nop
0x18000a7f5  lea     rax, [rsp+498h+var_430]
0x18000a7fa  cmp     [rsp+498h+var_438], rax
0x18000a7ff  jz      short loc_18000A80C
0x18000a801  lea     rcx, [rsp+498h+var_438]
0x18000a806  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000a80b  nop
0x18000a80c  mov     eax, ebx
0x18000a80e  mov     rcx, [rsp+498h+var_28]
0x18000a816  xor     rcx, rsp; StackCookie
0x18000a819  call    __security_check_cookie
0x18000a81e  mov     rbx, [rsp+498h+arg_0]
0x18000a826  add     rsp, 480h
0x18000a82d  pop     r14
0x18000a82f  pop     rdi
0x18000a830  pop     rsi
0x18000a831  retn
0x18000a832  mov     ecx, 80070057h; int
0x18000a837  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
