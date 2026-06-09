# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000e660`
- end: `0x18000e808`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800105bc`
- `0x180010834`

## callees

- `0x180001720`
- `0x18000769c`
- `0x1800082ec`
- `0x1800083f0`
- `0x180009c54`
- `0x180009df4`
- `0x18000e458`
- `0x18000e660`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000e6f3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000e6f3`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000e70c`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000e70c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e6aa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e6aa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e7c6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e7c6`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000e6d5`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000e6d5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000e791`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000e791`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v8; // rsi
  unsigned int v9; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rdi
  signed int Error; // eax
  const CHAR *v13; // r14
  DWORD cchWideChar; // edi
  size_t v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  HMODULE v19; // [rsp+38h] [rbp-460h]
  _QWORD *v20; // [rsp+48h] [rbp-450h] BYREF
  _QWORD v21[2]; // [rsp+50h] [rbp-448h] BYREF
  LPWSTR v22; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v23[1032]; // [rsp+68h] [rbp-430h] BYREF

  v20 = 0;
  v21[1] = this;
  v21[0] = 0;
  v22 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  v19 = Library;
  if ( Library )
  {
    Resource = FindResourceExW(Library, a4, a3, 0);
    v11 = Resource;
    if ( !Resource )
      goto LABEL_4;
    v13 = (const CHAR *)LoadResource(v8, Resource);
    if ( !v13 )
      goto LABEL_4;
    cchWideChar = SizeofResource(v8, v11);
    if ( cchWideChar + 1 < cchWideChar )
    {
      v9 = -2147024882;
      goto LABEL_17;
    }
    try
    {
      v15 = ATL::AtlMultiplyThrow<unsigned __int64>();
      if ( v15 <= 0x400 )
      {
        lpWideCharStr = (WCHAR *)v23;
        v22 = (LPWSTR)v23;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v22, v15);
        lpWideCharStr = v22;
      }
    }
    catch ( ... )
    {
      v8 = v19;
      lpWideCharStr = v22;
    }
    if ( !lpWideCharStr )
    {
      v9 = -2147024882;
LABEL_16:
      FreeLibrary(v8);
      goto LABEL_17;
    }
    v17 = MultiByteToWideChar(3u, 0, v13, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v17 )
    {
      v22[v17] = 0;
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v21, v22, a5);
    }
    else
    {
LABEL_4:
      Error = ATL::AtlHresultFromLastError();
    }
    v9 = Error;
    goto LABEL_16;
  }
  v9 = ATL::AtlHresultFromLastError();
LABEL_17:
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v22);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
  return v9;
}

```

## disassembly

```asm
0x18000e660  mov     [rsp+arg_0], rbx
0x18000e665  push    rsi
0x18000e666  push    rdi
0x18000e667  push    r14
0x18000e669  sub     rsp, 480h
0x18000e670  mov     rax, cs:__security_cookie
0x18000e677  xor     rax, rsp
0x18000e67a  mov     [rsp+498h+var_28], rax
0x18000e682  mov     r14, r9
0x18000e685  mov     rdi, r8
0x18000e688  mov     rax, rdx
0x18000e68b  xor     ebx, ebx
0x18000e68d  mov     [rsp+498h+var_450], rbx
0x18000e692  mov     [rsp+498h+var_440], rcx
0x18000e697  mov     [rsp+498h+var_448], rbx
0x18000e69c  mov     [rsp+498h+var_438], rbx
0x18000e6a1  xor     edx, edx; hFile
0x18000e6a3  lea     r8d, [rbx+2]; dwFlags
0x18000e6a7  mov     rcx, rax; lpLibFileName
0x18000e6aa  call    cs:__imp_LoadLibraryExW
0x18000e6b0  mov     rsi, rax
0x18000e6b3  mov     [rsp+498h+var_460], rax
0x18000e6b8  test    rax, rax
0x18000e6bb  jnz     short loc_18000E6C9
0x18000e6bd  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000e6c2  mov     ebx, eax
0x18000e6c4  jmp     loc_18000E7CD
0x18000e6c9  xor     r9d, r9d; wLanguage
0x18000e6cc  mov     r8, rdi; lpName
0x18000e6cf  mov     rdx, r14; lpType
0x18000e6d2  mov     rcx, rsi; hModule
0x18000e6d5  call    cs:__imp_FindResourceExW
0x18000e6db  mov     rdi, rax
0x18000e6de  test    rax, rax
0x18000e6e1  jnz     short loc_18000E6ED
0x18000e6e3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000e6e8  jmp     loc_18000E7C1
0x18000e6ed  mov     rdx, rdi; hResInfo
0x18000e6f0  mov     rcx, rsi; hModule
0x18000e6f3  call    cs:__imp_LoadResource
0x18000e6f9  mov     r14, rax
0x18000e6fc  mov     [rsp+498h+var_458], rax
0x18000e701  test    rax, rax
0x18000e704  jz      short loc_18000E6E3
0x18000e706  mov     rdx, rdi; hResInfo
0x18000e709  mov     rcx, rsi; hModule
0x18000e70c  call    cs:__imp_SizeofResource
0x18000e712  mov     edi, eax
0x18000e714  mov     [rsp+498h+var_468], eax
0x18000e718  inc     eax
0x18000e71a  cmp     eax, edi
0x18000e71c  jnb     short loc_18000E728
0x18000e71e  mov     ebx, 8007000Eh
0x18000e723  jmp     loc_18000E7CD
0x18000e728  mov     ecx, eax
0x18000e72a  mov     edx, 2
0x18000e72f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000e734  cmp     rax, 400h
0x18000e73a  jbe     short loc_18000E750
0x18000e73c  mov     rdx, rax
0x18000e73f  lea     rcx, [rsp+498h+var_438]
0x18000e744  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000e749  mov     rax, [rsp+498h+var_438]
0x18000e74e  jmp     short loc_18000E75A
0x18000e750  lea     rax, [rsp+498h+var_430]
0x18000e755  mov     [rsp+498h+var_438], rax
0x18000e75a  jmp     short loc_18000E771
0x18000e75c  xor     ebx, ebx
0x18000e75e  mov     rsi, [rsp+498h+var_460]
0x18000e763  mov     r14, [rsp+498h+var_458]
0x18000e768  mov     edi, [rsp+498h+var_468]
0x18000e76c  mov     rax, [rsp+498h+var_438]
0x18000e771  test    rax, rax
0x18000e774  jnz     short loc_18000E77D
0x18000e776  mov     ebx, 8007000Eh
0x18000e77b  jmp     short loc_18000E7C3
0x18000e77d  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18000e781  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18000e786  mov     r9d, edi; cbMultiByte
0x18000e789  mov     r8, r14; lpMultiByteStr
0x18000e78c  xor     edx, edx; dwFlags
0x18000e78e  lea     ecx, [rdx+3]; CodePage
0x18000e791  call    cs:__imp_MultiByteToWideChar
0x18000e797  test    eax, eax
0x18000e799  jz      loc_18000E6E3
0x18000e79f  mov     ecx, eax
0x18000e7a1  mov     rax, [rsp+498h+var_438]
0x18000e7a6  mov     [rax+rcx*2], bx
0x18000e7aa  mov     r8d, [rsp+498h+arg_20]; int
0x18000e7b2  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x18000e7b7  lea     rcx, [rsp+498h+var_448]; this
0x18000e7bc  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000e7c1  mov     ebx, eax
0x18000e7c3  mov     rcx, rsi; hLibModule
0x18000e7c6  call    cs:__imp_FreeLibrary
0x18000e7cc  nop
0x18000e7cd  lea     rcx, [rsp+498h+var_438]
0x18000e7d2  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000e7d7  nop
0x18000e7d8  lea     rcx, [rsp+498h+var_450]
0x18000e7dd  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000e7e2  mov     eax, ebx
0x18000e7e4  mov     rcx, [rsp+498h+var_28]
0x18000e7ec  xor     rcx, rsp; StackCookie
0x18000e7ef  call    __security_check_cookie
0x18000e7f4  mov     rbx, [rsp+498h+arg_0]
0x18000e7fc  add     rsp, 480h
0x18000e803  pop     r14
0x18000e805  pop     rdi
0x18000e806  pop     rsi
0x18000e807  retn
```
