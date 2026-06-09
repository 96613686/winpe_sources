# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180021228`
- end: `0x180021404`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `476`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180021f9c`
- `0x1800222c4`

## callees

- `0x1800018f0`
- `0x18001fa78`
- `0x18001fc74`
- `0x180020178`
- `0x180020754`
- `0x180021098`
- `0x180021228`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180021272`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180021272`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18002129d`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18002129d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800212bb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800212bb`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800212d4`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800212d4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800213b4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800213b4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002137f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002137f`

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
  HMODULE v8; // rsi
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rdi
  unsigned int v12; // eax
  const CHAR *v13; // r14
  DWORD cchWideChar; // edi
  DWORD v15; // eax
  WCHAR *lpWideCharStr; // rax
  int v18; // eax
  HMODULE v19; // [rsp+38h] [rbp-460h]
  _QWORD v20[3]; // [rsp+48h] [rbp-450h] BYREF
  LPWSTR v21; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v22[1032]; // [rsp+68h] [rbp-430h] BYREF

  v20[2] = 0;
  v20[1] = this;
  v20[0] = 0;
  v21 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  v19 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_21:
    if ( v21 != (LPWSTR)v22 )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v21);
    return Error;
  }
  Resource = FindResourceExW(Library, a4, a3, 0);
  v11 = Resource;
  if ( !Resource )
    goto LABEL_4;
  v13 = (const CHAR *)LoadResource(v8, Resource);
  if ( !v13 )
    goto LABEL_4;
  cchWideChar = SizeofResource(v8, v11);
  v15 = cchWideChar + 1;
  if ( cchWideChar + 1 >= cchWideChar )
  {
    try
    {
      if ( cchWideChar == -1 )
        goto LABEL_14;
      if ( 0xFFFFFFFFFFFFFFFFuLL / v15 < 2 )
        ATL::AtlThrowImpl(-2147024809);
      if ( 2 * (unsigned __int64)v15 <= 0x400 )
      {
LABEL_14:
        lpWideCharStr = (WCHAR *)v22;
        v21 = (LPWSTR)v22;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v21, 2LL * v15);
        lpWideCharStr = v21;
      }
    }
    catch ( ... )
    {
      v8 = v19;
      lpWideCharStr = v21;
    }
    if ( !lpWideCharStr )
    {
      Error = -2147024882;
LABEL_20:
      FreeLibrary(v8);
      goto LABEL_21;
    }
    v18 = MultiByteToWideChar(3u, 0, v13, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v18 )
    {
      v21[v18] = 0;
      v12 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v20, v21, a5);
      goto LABEL_19;
    }
LABEL_4:
    v12 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v12;
    goto LABEL_20;
  }
  if ( v21 != (LPWSTR)v22 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v21);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180021228  mov     [rsp+arg_0], rbx
0x18002122d  push    rsi
0x18002122e  push    rdi
0x18002122f  push    r14
0x180021231  sub     rsp, 480h
0x180021238  mov     rax, cs:__security_cookie
0x18002123f  xor     rax, rsp
0x180021242  mov     [rsp+498h+var_28], rax
0x18002124a  mov     r14, r9
0x18002124d  mov     rdi, r8
0x180021250  mov     rax, rdx
0x180021253  xor     ebx, ebx
0x180021255  mov     [rsp+498h+var_440], rbx
0x18002125a  mov     [rsp+498h+var_448], rcx
0x18002125f  mov     [rsp+498h+var_450], rbx
0x180021264  mov     [rsp+498h+var_438], rbx
0x180021269  xor     edx, edx; hFile
0x18002126b  lea     r8d, [rbx+2]; dwFlags
0x18002126f  mov     rcx, rax; lpLibFileName
0x180021272  call    cs:__imp_LoadLibraryExW
0x180021278  mov     rsi, rax
0x18002127b  mov     [rsp+498h+var_460], rax
0x180021280  test    rax, rax
0x180021283  jnz     short loc_180021291
0x180021285  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002128a  mov     ebx, eax
0x18002128c  jmp     loc_1800213BB
0x180021291  xor     r9d, r9d; wLanguage
0x180021294  mov     r8, rdi; lpName
0x180021297  mov     rdx, r14; lpType
0x18002129a  mov     rcx, rsi; hModule
0x18002129d  call    cs:__imp_FindResourceExW
0x1800212a3  mov     rdi, rax
0x1800212a6  test    rax, rax
0x1800212a9  jnz     short loc_1800212B5
0x1800212ab  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800212b0  jmp     loc_1800213AF
0x1800212b5  mov     rdx, rdi; hResInfo
0x1800212b8  mov     rcx, rsi; hModule
0x1800212bb  call    cs:__imp_LoadResource
0x1800212c1  mov     r14, rax
0x1800212c4  mov     [rsp+498h+var_458], rax
0x1800212c9  test    rax, rax
0x1800212cc  jz      short loc_1800212AB
0x1800212ce  mov     rdx, rdi; hResInfo
0x1800212d1  mov     rcx, rsi; hModule
0x1800212d4  call    cs:__imp_SizeofResource
0x1800212da  mov     edi, eax
0x1800212dc  mov     [rsp+498h+var_468], eax
0x1800212e0  inc     eax
0x1800212e2  cmp     eax, edi
0x1800212e4  jnb     short loc_180021307
0x1800212e6  lea     rax, [rsp+498h+var_430]
0x1800212eb  cmp     [rsp+498h+var_438], rax
0x1800212f0  jz      short loc_1800212FD
0x1800212f2  lea     rcx, [rsp+498h+var_438]
0x1800212f7  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800212fc  nop
0x1800212fd  mov     eax, 8007000Eh
0x180021302  jmp     loc_1800213D4
0x180021307  test    eax, eax
0x180021309  jz      short loc_18002133E
0x18002130b  mov     ecx, eax
0x18002130d  xor     edx, edx
0x18002130f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021313  div     rcx
0x180021316  cmp     rax, 2
0x18002131a  jb      loc_1800213F8
0x180021320  lea     rdx, [rcx+rcx]
0x180021324  cmp     rdx, 400h
0x18002132b  jbe     short loc_18002133E
0x18002132d  lea     rcx, [rsp+498h+var_438]
0x180021332  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180021337  mov     rax, [rsp+498h+var_438]
0x18002133c  jmp     short loc_180021348
0x18002133e  lea     rax, [rsp+498h+var_430]
0x180021343  mov     [rsp+498h+var_438], rax
0x180021348  jmp     short loc_18002135F
0x18002134a  xor     ebx, ebx
0x18002134c  mov     rsi, [rsp+498h+var_460]
0x180021351  mov     r14, [rsp+498h+var_458]
0x180021356  mov     edi, [rsp+498h+var_468]
0x18002135a  mov     rax, [rsp+498h+var_438]
0x18002135f  test    rax, rax
0x180021362  jnz     short loc_18002136B
0x180021364  mov     ebx, 8007000Eh
0x180021369  jmp     short loc_1800213B1
0x18002136b  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18002136f  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180021374  mov     r9d, edi; cbMultiByte
0x180021377  mov     r8, r14; lpMultiByteStr
0x18002137a  xor     edx, edx; dwFlags
0x18002137c  lea     ecx, [rdx+3]; CodePage
0x18002137f  call    cs:__imp_MultiByteToWideChar
0x180021385  test    eax, eax
0x180021387  jz      loc_1800212AB
0x18002138d  mov     ecx, eax
0x18002138f  mov     rax, [rsp+498h+var_438]
0x180021394  mov     [rax+rcx*2], bx
0x180021398  mov     r8d, [rsp+498h+arg_20]; int
0x1800213a0  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x1800213a5  lea     rcx, [rsp+498h+var_450]; this
0x1800213aa  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800213af  mov     ebx, eax
0x1800213b1  mov     rcx, rsi; hLibModule
0x1800213b4  call    cs:__imp_FreeLibrary
0x1800213ba  nop
0x1800213bb  lea     rax, [rsp+498h+var_430]
0x1800213c0  cmp     [rsp+498h+var_438], rax
0x1800213c5  jz      short loc_1800213D2
0x1800213c7  lea     rcx, [rsp+498h+var_438]
0x1800213cc  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800213d1  nop
0x1800213d2  mov     eax, ebx
0x1800213d4  mov     rcx, [rsp+498h+var_28]
0x1800213dc  xor     rcx, rsp; StackCookie
0x1800213df  call    __security_check_cookie
0x1800213e4  mov     rbx, [rsp+498h+arg_0]
0x1800213ec  add     rsp, 480h
0x1800213f3  pop     r14
0x1800213f5  pop     rdi
0x1800213f6  pop     rsi
0x1800213f7  retn
0x1800213f8  mov     ecx, 80070057h; int
0x1800213fd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
