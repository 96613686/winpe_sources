# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800070fc`
- end: `0x1800072d6`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `474`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180008bf4`

## callees

- `0x180002470`
- `0x180004d4c`
- `0x180004e7c`
- `0x180004eb8`
- `0x1800056a8`
- `0x180006f6c`
- `0x1800070fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007143`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007143`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000718d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000718d`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000716f`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000716f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007286`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007286`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800071a6`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800071a6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007251`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007251`

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
0x1800070fc  mov     [rsp+arg_0], rbx
0x180007101  push    rsi
0x180007102  push    rdi
0x180007103  push    r14
0x180007105  sub     rsp, 480h
0x18000710c  mov     rax, cs:__security_cookie
0x180007113  xor     rax, rsp
0x180007116  mov     [rsp+498h+var_28], rax
0x18000711e  mov     rsi, r9
0x180007121  mov     rax, rdx
0x180007124  xor     ebx, ebx
0x180007126  mov     [rsp+498h+var_440], rbx
0x18000712b  mov     [rsp+498h+var_448], rcx
0x180007130  mov     [rsp+498h+var_450], rbx
0x180007135  mov     [rsp+498h+var_438], rbx
0x18000713a  xor     edx, edx; hFile
0x18000713c  lea     r8d, [rbx+2]; dwFlags
0x180007140  mov     rcx, rax; lpLibFileName
0x180007143  call    cs:__imp_LoadLibraryExW
0x180007149  mov     rdi, rax
0x18000714c  mov     [rsp+498h+var_460], rax
0x180007151  test    rax, rax
0x180007154  jnz     short loc_180007162
0x180007156  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000715b  mov     ebx, eax
0x18000715d  jmp     loc_18000728D
0x180007162  xor     r9d, r9d; wLanguage
0x180007165  lea     r8d, [r9+65h]; lpName
0x180007169  mov     rdx, rsi; lpType
0x18000716c  mov     rcx, rdi; hModule
0x18000716f  call    cs:__imp_FindResourceExW
0x180007175  mov     rsi, rax
0x180007178  test    rax, rax
0x18000717b  jnz     short loc_180007187
0x18000717d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180007182  jmp     loc_180007281
0x180007187  mov     rdx, rsi; hResInfo
0x18000718a  mov     rcx, rdi; hModule
0x18000718d  call    cs:__imp_LoadResource
0x180007193  mov     r14, rax
0x180007196  mov     [rsp+498h+var_458], rax
0x18000719b  test    rax, rax
0x18000719e  jz      short loc_18000717D
0x1800071a0  mov     rdx, rsi; hResInfo
0x1800071a3  mov     rcx, rdi; hModule
0x1800071a6  call    cs:__imp_SizeofResource
0x1800071ac  mov     esi, eax
0x1800071ae  mov     [rsp+498h+var_468], eax
0x1800071b2  inc     eax
0x1800071b4  cmp     eax, esi
0x1800071b6  jnb     short loc_1800071D9
0x1800071b8  lea     rax, [rsp+498h+var_430]
0x1800071bd  cmp     [rsp+498h+var_438], rax
0x1800071c2  jz      short loc_1800071CF
0x1800071c4  lea     rcx, [rsp+498h+var_438]
0x1800071c9  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800071ce  nop
0x1800071cf  mov     eax, 8007000Eh
0x1800071d4  jmp     loc_1800072A6
0x1800071d9  test    eax, eax
0x1800071db  jz      short loc_180007210
0x1800071dd  mov     ecx, eax
0x1800071df  xor     edx, edx
0x1800071e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800071e5  div     rcx
0x1800071e8  cmp     rax, 2
0x1800071ec  jb      loc_1800072CA
0x1800071f2  lea     rdx, [rcx+rcx]
0x1800071f6  cmp     rdx, 400h
0x1800071fd  jbe     short loc_180007210
0x1800071ff  lea     rcx, [rsp+498h+var_438]
0x180007204  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180007209  mov     rax, [rsp+498h+var_438]
0x18000720e  jmp     short loc_18000721A
0x180007210  lea     rax, [rsp+498h+var_430]
0x180007215  mov     [rsp+498h+var_438], rax
0x18000721a  jmp     short loc_180007231
0x18000721c  xor     ebx, ebx
0x18000721e  mov     rdi, [rsp+498h+var_460]
0x180007223  mov     r14, [rsp+498h+var_458]
0x180007228  mov     esi, [rsp+498h+var_468]
0x18000722c  mov     rax, [rsp+498h+var_438]
0x180007231  test    rax, rax
0x180007234  jnz     short loc_18000723D
0x180007236  mov     ebx, 8007000Eh
0x18000723b  jmp     short loc_180007283
0x18000723d  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x180007241  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180007246  mov     r9d, esi; cbMultiByte
0x180007249  mov     r8, r14; lpMultiByteStr
0x18000724c  xor     edx, edx; dwFlags
0x18000724e  lea     ecx, [rdx+3]; CodePage
0x180007251  call    cs:__imp_MultiByteToWideChar
0x180007257  test    eax, eax
0x180007259  jz      loc_18000717D
0x18000725f  mov     ecx, eax
0x180007261  mov     rax, [rsp+498h+var_438]
0x180007266  mov     [rax+rcx*2], bx
0x18000726a  mov     r8d, [rsp+498h+arg_20]; int
0x180007272  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180007277  lea     rcx, [rsp+498h+var_450]; this
0x18000727c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180007281  mov     ebx, eax
0x180007283  mov     rcx, rdi; hLibModule
0x180007286  call    cs:__imp_FreeLibrary
0x18000728c  nop
0x18000728d  lea     rax, [rsp+498h+var_430]
0x180007292  cmp     [rsp+498h+var_438], rax
0x180007297  jz      short loc_1800072A4
0x180007299  lea     rcx, [rsp+498h+var_438]
0x18000729e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800072a3  nop
0x1800072a4  mov     eax, ebx
0x1800072a6  mov     rcx, [rsp+498h+var_28]
0x1800072ae  xor     rcx, rsp; StackCookie
0x1800072b1  call    __security_check_cookie
0x1800072b6  mov     rbx, [rsp+498h+arg_0]
0x1800072be  add     rsp, 480h
0x1800072c5  pop     r14
0x1800072c7  pop     rdi
0x1800072c8  pop     rsi
0x1800072c9  retn
0x1800072ca  mov     ecx, 80070057h; int
0x1800072cf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
