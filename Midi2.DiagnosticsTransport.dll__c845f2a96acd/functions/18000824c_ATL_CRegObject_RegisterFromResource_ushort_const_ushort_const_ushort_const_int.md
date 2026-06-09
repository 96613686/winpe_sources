# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000824c`
- end: `0x180008426`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `474`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180009cf4`

## callees

- `0x1800033d0`
- `0x180005eac`
- `0x180005fdc`
- `0x180006018`
- `0x18000680c`
- `0x1800080bc`
- `0x18000824c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008293`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008293`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800082f6`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800082f6`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800082bf`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800082bf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800082dd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800082dd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800083d6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800083d6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800083a1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800083a1`

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
0x18000824c  mov     [rsp+arg_0], rbx
0x180008251  push    rsi
0x180008252  push    rdi
0x180008253  push    r14
0x180008255  sub     rsp, 480h
0x18000825c  mov     rax, cs:__security_cookie
0x180008263  xor     rax, rsp
0x180008266  mov     [rsp+498h+var_28], rax
0x18000826e  mov     rsi, r9
0x180008271  mov     rax, rdx
0x180008274  xor     ebx, ebx
0x180008276  mov     [rsp+498h+var_440], rbx
0x18000827b  mov     [rsp+498h+var_448], rcx
0x180008280  mov     [rsp+498h+var_450], rbx
0x180008285  mov     [rsp+498h+var_438], rbx
0x18000828a  xor     edx, edx; hFile
0x18000828c  lea     r8d, [rbx+2]; dwFlags
0x180008290  mov     rcx, rax; lpLibFileName
0x180008293  call    cs:__imp_LoadLibraryExW
0x180008299  mov     rdi, rax
0x18000829c  mov     [rsp+498h+var_460], rax
0x1800082a1  test    rax, rax
0x1800082a4  jnz     short loc_1800082B2
0x1800082a6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800082ab  mov     ebx, eax
0x1800082ad  jmp     loc_1800083DD
0x1800082b2  xor     r9d, r9d; wLanguage
0x1800082b5  lea     r8d, [r9+65h]; lpName
0x1800082b9  mov     rdx, rsi; lpType
0x1800082bc  mov     rcx, rdi; hModule
0x1800082bf  call    cs:__imp_FindResourceExW
0x1800082c5  mov     rsi, rax
0x1800082c8  test    rax, rax
0x1800082cb  jnz     short loc_1800082D7
0x1800082cd  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800082d2  jmp     loc_1800083D1
0x1800082d7  mov     rdx, rsi; hResInfo
0x1800082da  mov     rcx, rdi; hModule
0x1800082dd  call    cs:__imp_LoadResource
0x1800082e3  mov     r14, rax
0x1800082e6  mov     [rsp+498h+var_458], rax
0x1800082eb  test    rax, rax
0x1800082ee  jz      short loc_1800082CD
0x1800082f0  mov     rdx, rsi; hResInfo
0x1800082f3  mov     rcx, rdi; hModule
0x1800082f6  call    cs:__imp_SizeofResource
0x1800082fc  mov     esi, eax
0x1800082fe  mov     [rsp+498h+var_468], eax
0x180008302  inc     eax
0x180008304  cmp     eax, esi
0x180008306  jnb     short loc_180008329
0x180008308  lea     rax, [rsp+498h+var_430]
0x18000830d  cmp     [rsp+498h+var_438], rax
0x180008312  jz      short loc_18000831F
0x180008314  lea     rcx, [rsp+498h+var_438]
0x180008319  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000831e  nop
0x18000831f  mov     eax, 8007000Eh
0x180008324  jmp     loc_1800083F6
0x180008329  test    eax, eax
0x18000832b  jz      short loc_180008360
0x18000832d  mov     ecx, eax
0x18000832f  xor     edx, edx
0x180008331  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008335  div     rcx
0x180008338  cmp     rax, 2
0x18000833c  jb      loc_18000841A
0x180008342  lea     rdx, [rcx+rcx]
0x180008346  cmp     rdx, 400h
0x18000834d  jbe     short loc_180008360
0x18000834f  lea     rcx, [rsp+498h+var_438]
0x180008354  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180008359  mov     rax, [rsp+498h+var_438]
0x18000835e  jmp     short loc_18000836A
0x180008360  lea     rax, [rsp+498h+var_430]
0x180008365  mov     [rsp+498h+var_438], rax
0x18000836a  jmp     short loc_180008381
0x18000836c  xor     ebx, ebx
0x18000836e  mov     rdi, [rsp+498h+var_460]
0x180008373  mov     r14, [rsp+498h+var_458]
0x180008378  mov     esi, [rsp+498h+var_468]
0x18000837c  mov     rax, [rsp+498h+var_438]
0x180008381  test    rax, rax
0x180008384  jnz     short loc_18000838D
0x180008386  mov     ebx, 8007000Eh
0x18000838b  jmp     short loc_1800083D3
0x18000838d  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x180008391  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180008396  mov     r9d, esi; cbMultiByte
0x180008399  mov     r8, r14; lpMultiByteStr
0x18000839c  xor     edx, edx; dwFlags
0x18000839e  lea     ecx, [rdx+3]; CodePage
0x1800083a1  call    cs:__imp_MultiByteToWideChar
0x1800083a7  test    eax, eax
0x1800083a9  jz      loc_1800082CD
0x1800083af  mov     ecx, eax
0x1800083b1  mov     rax, [rsp+498h+var_438]
0x1800083b6  mov     [rax+rcx*2], bx
0x1800083ba  mov     r8d, [rsp+498h+arg_20]; int
0x1800083c2  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x1800083c7  lea     rcx, [rsp+498h+var_450]; this
0x1800083cc  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800083d1  mov     ebx, eax
0x1800083d3  mov     rcx, rdi; hLibModule
0x1800083d6  call    cs:__imp_FreeLibrary
0x1800083dc  nop
0x1800083dd  lea     rax, [rsp+498h+var_430]
0x1800083e2  cmp     [rsp+498h+var_438], rax
0x1800083e7  jz      short loc_1800083F4
0x1800083e9  lea     rcx, [rsp+498h+var_438]
0x1800083ee  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800083f3  nop
0x1800083f4  mov     eax, ebx
0x1800083f6  mov     rcx, [rsp+498h+var_28]
0x1800083fe  xor     rcx, rsp; StackCookie
0x180008401  call    __security_check_cookie
0x180008406  mov     rbx, [rsp+498h+arg_0]
0x18000840e  add     rsp, 480h
0x180008415  pop     r14
0x180008417  pop     rdi
0x180008418  pop     rsi
0x180008419  retn
0x18000841a  mov     ecx, 80070057h; int
0x18000841f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
