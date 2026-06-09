# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18002d1b0`
- end: `0x18002d364`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `436`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18002dd6c`
- `0x18002dff4`

## callees

- `0x1800277b0`
- `0x1800284c4`
- `0x18002a0a8`
- `0x18002a140`
- `0x18002a304`
- `0x18002ae2c`
- `0x18002b1ac`
- `0x18002d03c`
- `0x18002d1b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18002d236`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18002d236`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18002d254`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18002d254`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d20b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d20b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d327`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d327`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18002d26d`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18002d26d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002d2f2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002d2f2`

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
  HMODULE v9; // rsi
  unsigned int v10; // ebx
  HRSRC Resource; // rax
  HRSRC v12; // rbx
  unsigned int Error; // eax
  const CHAR *v14; // r14
  DWORD cchWideChar; // ebx
  unsigned __int64 v16; // rax
  WCHAR *lpWideCharStr; // rax
  int v18; // eax
  HMODULE v20; // [rsp+38h] [rbp-470h]
  __int64 v21; // [rsp+48h] [rbp-460h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-458h] BYREF
  LPWSTR v23; // [rsp+60h] [rbp-448h] BYREF
  _BYTE v24[1032]; // [rsp+68h] [rbp-440h] BYREF

  v21 = 0;
  v22[1] = this;
  v22[0] = 0;
  memset_0(&v23, 0, 0x408u);
  v23 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v9 = Library;
  v20 = Library;
  if ( Library )
  {
    Resource = FindResourceExW(Library, a4, a3, 0);
    v12 = Resource;
    if ( !Resource )
      goto LABEL_4;
    v14 = (const CHAR *)LoadResource(v9, Resource);
    if ( !v14 )
      goto LABEL_4;
    cchWideChar = SizeofResource(v9, v12);
    if ( cchWideChar + 1 < cchWideChar )
    {
      v10 = -2147024882;
      goto LABEL_17;
    }
    try
    {
      v16 = ATL::AtlMultiplyThrow<unsigned __int64>();
      if ( v16 <= 0x400 )
      {
        lpWideCharStr = (WCHAR *)v24;
        v23 = (LPWSTR)v24;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v23, v16);
        lpWideCharStr = v23;
      }
    }
    catch ( ... )
    {
      v9 = v20;
      lpWideCharStr = v23;
    }
    if ( !lpWideCharStr )
    {
      v10 = -2147024882;
LABEL_16:
      FreeLibrary(v9);
      goto LABEL_17;
    }
    v18 = MultiByteToWideChar(3u, 0, v14, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v18 )
    {
      v23[v18] = 0;
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v22, v23, a5);
    }
    else
    {
LABEL_4:
      Error = ATL::AtlHresultFromLastError();
    }
    v10 = Error;
    goto LABEL_16;
  }
  v10 = ATL::AtlHresultFromLastError();
LABEL_17:
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v23);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
  return v10;
}

```

## disassembly

```asm
0x18002d1b0  push    rbx
0x18002d1b2  push    rsi
0x18002d1b3  push    rdi
0x18002d1b4  push    r14
0x18002d1b6  push    r15
0x18002d1b8  sub     rsp, 480h
0x18002d1bf  mov     rax, cs:__security_cookie
0x18002d1c6  xor     rax, rsp
0x18002d1c9  mov     [rsp+4A8h+var_38], rax
0x18002d1d1  mov     r15, r9
0x18002d1d4  mov     r14, r8
0x18002d1d7  mov     rbx, rdx
0x18002d1da  xor     edi, edi
0x18002d1dc  mov     [rsp+4A8h+var_460], rdi
0x18002d1e1  mov     [rsp+4A8h+var_450], rcx
0x18002d1e6  mov     [rsp+4A8h+var_458], rdi
0x18002d1eb  xor     edx, edx; Val
0x18002d1ed  mov     r8d, 408h; Size
0x18002d1f3  lea     rcx, [rsp+4A8h+var_448]; void *
0x18002d1f8  call    memset_0
0x18002d1fd  mov     [rsp+4A8h+var_448], rdi
0x18002d202  xor     edx, edx; hFile
0x18002d204  lea     r8d, [rdi+2]; dwFlags
0x18002d208  mov     rcx, rbx; lpLibFileName
0x18002d20b  call    cs:__imp_LoadLibraryExW
0x18002d211  mov     rsi, rax
0x18002d214  mov     [rsp+4A8h+var_470], rax
0x18002d219  test    rax, rax
0x18002d21c  jnz     short loc_18002D22A
0x18002d21e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002d223  mov     ebx, eax
0x18002d225  jmp     loc_18002D32E
0x18002d22a  xor     r9d, r9d; wLanguage
0x18002d22d  mov     r8, r14; lpName
0x18002d230  mov     rdx, r15; lpType
0x18002d233  mov     rcx, rsi; hModule
0x18002d236  call    cs:__imp_FindResourceExW
0x18002d23c  mov     rbx, rax
0x18002d23f  test    rax, rax
0x18002d242  jnz     short loc_18002D24E
0x18002d244  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002d249  jmp     loc_18002D322
0x18002d24e  mov     rdx, rbx; hResInfo
0x18002d251  mov     rcx, rsi; hModule
0x18002d254  call    cs:__imp_LoadResource
0x18002d25a  mov     r14, rax
0x18002d25d  mov     [rsp+4A8h+var_468], rax
0x18002d262  test    rax, rax
0x18002d265  jz      short loc_18002D244
0x18002d267  mov     rdx, rbx; hResInfo
0x18002d26a  mov     rcx, rsi; hModule
0x18002d26d  call    cs:__imp_SizeofResource
0x18002d273  mov     ebx, eax
0x18002d275  mov     [rsp+4A8h+var_478], eax
0x18002d279  inc     eax
0x18002d27b  cmp     eax, ebx
0x18002d27d  jnb     short loc_18002D289
0x18002d27f  mov     ebx, 8007000Eh
0x18002d284  jmp     loc_18002D32E
0x18002d289  mov     ecx, eax
0x18002d28b  mov     edx, 2
0x18002d290  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18002d295  cmp     rax, 400h
0x18002d29b  jbe     short loc_18002D2B1
0x18002d29d  mov     rdx, rax
0x18002d2a0  lea     rcx, [rsp+4A8h+var_448]
0x18002d2a5  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18002d2aa  mov     rax, [rsp+4A8h+var_448]
0x18002d2af  jmp     short loc_18002D2BB
0x18002d2b1  lea     rax, [rsp+4A8h+var_440]
0x18002d2b6  mov     [rsp+4A8h+var_448], rax
0x18002d2bb  jmp     short loc_18002D2D2
0x18002d2bd  xor     edi, edi
0x18002d2bf  mov     rsi, [rsp+4A8h+var_470]
0x18002d2c4  mov     r14, [rsp+4A8h+var_468]
0x18002d2c9  mov     ebx, [rsp+4A8h+var_478]
0x18002d2cd  mov     rax, [rsp+4A8h+var_448]
0x18002d2d2  test    rax, rax
0x18002d2d5  jnz     short loc_18002D2DE
0x18002d2d7  mov     ebx, 8007000Eh
0x18002d2dc  jmp     short loc_18002D324
0x18002d2de  mov     [rsp+4A8h+cchWideChar], ebx; cchWideChar
0x18002d2e2  mov     [rsp+4A8h+lpWideCharStr], rax; lpWideCharStr
0x18002d2e7  mov     r9d, ebx; cbMultiByte
0x18002d2ea  mov     r8, r14; lpMultiByteStr
0x18002d2ed  xor     edx, edx; dwFlags
0x18002d2ef  lea     ecx, [rdx+3]; CodePage
0x18002d2f2  call    cs:__imp_MultiByteToWideChar
0x18002d2f8  test    eax, eax
0x18002d2fa  jz      loc_18002D244
0x18002d300  mov     ecx, eax
0x18002d302  mov     rax, [rsp+4A8h+var_448]
0x18002d307  mov     [rax+rcx*2], di
0x18002d30b  mov     r8d, [rsp+4A8h+arg_20]; int
0x18002d313  mov     rdx, [rsp+4A8h+var_448]; unsigned __int16 *
0x18002d318  lea     rcx, [rsp+4A8h+var_458]; this
0x18002d31d  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18002d322  mov     ebx, eax
0x18002d324  mov     rcx, rsi; hLibModule
0x18002d327  call    cs:__imp_FreeLibrary
0x18002d32d  nop
0x18002d32e  lea     rcx, [rsp+4A8h+var_448]
0x18002d333  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18002d338  nop
0x18002d339  lea     rcx, [rsp+4A8h+var_460]
0x18002d33e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002d343  mov     eax, ebx
0x18002d345  mov     rcx, [rsp+4A8h+var_38]
0x18002d34d  xor     rcx, rsp; StackCookie
0x18002d350  call    __security_check_cookie
0x18002d355  add     rsp, 480h
0x18002d35c  pop     r15
0x18002d35e  pop     r14
0x18002d360  pop     rdi
0x18002d361  pop     rsi
0x18002d362  pop     rbx
0x18002d363  retn
```
