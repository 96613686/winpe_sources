# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180019e6c`
- end: `0x18001a039`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `461`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001aa20`
- `0x18001aca4`

## callees

- `0x180016a40`
- `0x18001803c`
- `0x180018078`
- `0x180018118`
- `0x180018a98`
- `0x180018d38`
- `0x180019cec`
- `0x180019e6c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180019ee7`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180019ee7`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180019f2a`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180019f2a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180019f0b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180019f0b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180019ff0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180019ff0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180019eb6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180019eb6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180019fb5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180019fb5`

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
  unsigned int v9; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rdi
  unsigned int Error; // eax
  const CHAR *v13; // r14
  DWORD cchWideChar; // edi
  unsigned __int64 v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  HMODULE v19; // [rsp+38h] [rbp-460h]
  __int64 v20; // [rsp+48h] [rbp-450h] BYREF
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
0x180019e6c  mov     [rsp+arg_0], rbx
0x180019e71  push    rsi
0x180019e72  push    rdi
0x180019e73  push    r14
0x180019e75  sub     rsp, 480h
0x180019e7c  mov     rax, cs:__security_cookie
0x180019e83  xor     rax, rsp
0x180019e86  mov     [rsp+498h+var_28], rax
0x180019e8e  mov     r14, r9
0x180019e91  mov     rdi, r8
0x180019e94  mov     rax, rdx
0x180019e97  xor     ebx, ebx
0x180019e99  mov     [rsp+498h+var_450], rbx
0x180019e9e  mov     [rsp+498h+var_440], rcx
0x180019ea3  mov     [rsp+498h+var_448], rbx
0x180019ea8  mov     [rsp+498h+var_438], rbx
0x180019ead  xor     edx, edx; hFile
0x180019eaf  lea     r8d, [rbx+2]; dwFlags
0x180019eb3  mov     rcx, rax; lpLibFileName
0x180019eb6  call    cs:__imp_LoadLibraryExW
0x180019ebd  nop     dword ptr [rax+rax+00h]
0x180019ec2  mov     rsi, rax
0x180019ec5  mov     [rsp+498h+var_460], rax
0x180019eca  test    rax, rax
0x180019ecd  jnz     short loc_180019EDB
0x180019ecf  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180019ed4  mov     ebx, eax
0x180019ed6  jmp     loc_180019FFD
0x180019edb  xor     r9d, r9d; wLanguage
0x180019ede  mov     r8, rdi; lpName
0x180019ee1  mov     rdx, r14; lpType
0x180019ee4  mov     rcx, rsi; hModule
0x180019ee7  call    cs:__imp_FindResourceExW
0x180019eee  nop     dword ptr [rax+rax+00h]
0x180019ef3  mov     rdi, rax
0x180019ef6  test    rax, rax
0x180019ef9  jnz     short loc_180019F05
0x180019efb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180019f00  jmp     loc_180019FEB
0x180019f05  mov     rdx, rdi; hResInfo
0x180019f08  mov     rcx, rsi; hModule
0x180019f0b  call    cs:__imp_LoadResource
0x180019f12  nop     dword ptr [rax+rax+00h]
0x180019f17  mov     r14, rax
0x180019f1a  mov     [rsp+498h+var_458], rax
0x180019f1f  test    rax, rax
0x180019f22  jz      short loc_180019EFB
0x180019f24  mov     rdx, rdi; hResInfo
0x180019f27  mov     rcx, rsi; hModule
0x180019f2a  call    cs:__imp_SizeofResource
0x180019f31  nop     dword ptr [rax+rax+00h]
0x180019f36  mov     edi, eax
0x180019f38  mov     [rsp+498h+var_468], eax
0x180019f3c  inc     eax
0x180019f3e  cmp     eax, edi
0x180019f40  jnb     short loc_180019F4C
0x180019f42  mov     ebx, 8007000Eh
0x180019f47  jmp     loc_180019FFD
0x180019f4c  mov     ecx, eax
0x180019f4e  mov     edx, 2
0x180019f53  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180019f58  cmp     rax, 400h
0x180019f5e  jbe     short loc_180019F74
0x180019f60  mov     rdx, rax
0x180019f63  lea     rcx, [rsp+498h+var_438]
0x180019f68  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180019f6d  mov     rax, [rsp+498h+var_438]
0x180019f72  jmp     short loc_180019F7E
0x180019f74  lea     rax, [rsp+498h+var_430]
0x180019f79  mov     [rsp+498h+var_438], rax
0x180019f7e  jmp     short loc_180019F95
0x180019f80  xor     ebx, ebx
0x180019f82  mov     rsi, [rsp+498h+var_460]
0x180019f87  mov     r14, [rsp+498h+var_458]
0x180019f8c  mov     edi, [rsp+498h+var_468]
0x180019f90  mov     rax, [rsp+498h+var_438]
0x180019f95  test    rax, rax
0x180019f98  jnz     short loc_180019FA1
0x180019f9a  mov     ebx, 8007000Eh
0x180019f9f  jmp     short loc_180019FED
0x180019fa1  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180019fa5  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180019faa  mov     r9d, edi; cbMultiByte
0x180019fad  mov     r8, r14; lpMultiByteStr
0x180019fb0  xor     edx, edx; dwFlags
0x180019fb2  lea     ecx, [rdx+3]; CodePage
0x180019fb5  call    cs:__imp_MultiByteToWideChar
0x180019fbc  nop     dword ptr [rax+rax+00h]
0x180019fc1  test    eax, eax
0x180019fc3  jz      loc_180019EFB
0x180019fc9  mov     ecx, eax
0x180019fcb  mov     rax, [rsp+498h+var_438]
0x180019fd0  mov     [rax+rcx*2], bx
0x180019fd4  mov     r8d, [rsp+498h+arg_20]; int
0x180019fdc  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180019fe1  lea     rcx, [rsp+498h+var_448]; this
0x180019fe6  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180019feb  mov     ebx, eax
0x180019fed  mov     rcx, rsi; hLibModule
0x180019ff0  call    cs:__imp_FreeLibrary
0x180019ff7  nop     dword ptr [rax+rax+00h]
0x180019ffc  nop
0x180019ffd  lea     rcx, [rsp+498h+var_438]
0x18001a002  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18001a007  nop
0x18001a008  lea     rcx, [rsp+498h+var_450]
0x18001a00d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a012  mov     eax, ebx
0x18001a014  mov     rcx, [rsp+498h+var_28]
0x18001a01c  xor     rcx, rsp; StackCookie
0x18001a01f  call    __security_check_cookie
0x18001a024  mov     rbx, [rsp+498h+arg_0]
0x18001a02c  add     rsp, 480h
0x18001a033  pop     r14
0x18001a035  pop     rdi
0x18001a036  pop     rsi
0x18001a037  retn
```
