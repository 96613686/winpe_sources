# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18002f08c`
- end: `0x18002f265`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `473`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18002fcb0`
- `0x18002ff44`

## callees

- `0x1800294b0`
- `0x18002a1f4`
- `0x18002bde4`
- `0x18002be80`
- `0x18002c054`
- `0x18002cafc`
- `0x18002ce7c`
- `0x18002ef0c`
- `0x18002f08c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18002f118`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18002f118`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18002f13c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18002f13c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002f0e7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002f0e7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002f221`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002f221`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18002f15b`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18002f15b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002f1e6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002f1e6`

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
0x18002f08c  push    rbx
0x18002f08e  push    rsi
0x18002f08f  push    rdi
0x18002f090  push    r14
0x18002f092  push    r15
0x18002f094  sub     rsp, 480h
0x18002f09b  mov     rax, cs:__security_cookie
0x18002f0a2  xor     rax, rsp
0x18002f0a5  mov     [rsp+4A8h+var_38], rax
0x18002f0ad  mov     r15, r9
0x18002f0b0  mov     r14, r8
0x18002f0b3  mov     rbx, rdx
0x18002f0b6  xor     edi, edi
0x18002f0b8  mov     [rsp+4A8h+var_460], rdi
0x18002f0bd  mov     [rsp+4A8h+var_450], rcx
0x18002f0c2  mov     [rsp+4A8h+var_458], rdi
0x18002f0c7  xor     edx, edx; Val
0x18002f0c9  mov     r8d, 408h; Size
0x18002f0cf  lea     rcx, [rsp+4A8h+var_448]; void *
0x18002f0d4  call    memset_0
0x18002f0d9  mov     [rsp+4A8h+var_448], rdi
0x18002f0de  xor     edx, edx; hFile
0x18002f0e0  lea     r8d, [rdi+2]; dwFlags
0x18002f0e4  mov     rcx, rbx; lpLibFileName
0x18002f0e7  call    cs:__imp_LoadLibraryExW
0x18002f0ee  nop     dword ptr [rax+rax+00h]
0x18002f0f3  mov     rsi, rax
0x18002f0f6  mov     [rsp+4A8h+var_470], rax
0x18002f0fb  test    rax, rax
0x18002f0fe  jnz     short loc_18002F10C
0x18002f100  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002f105  mov     ebx, eax
0x18002f107  jmp     loc_18002F22E
0x18002f10c  xor     r9d, r9d; wLanguage
0x18002f10f  mov     r8, r14; lpName
0x18002f112  mov     rdx, r15; lpType
0x18002f115  mov     rcx, rsi; hModule
0x18002f118  call    cs:__imp_FindResourceExW
0x18002f11f  nop     dword ptr [rax+rax+00h]
0x18002f124  mov     rbx, rax
0x18002f127  test    rax, rax
0x18002f12a  jnz     short loc_18002F136
0x18002f12c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002f131  jmp     loc_18002F21C
0x18002f136  mov     rdx, rbx; hResInfo
0x18002f139  mov     rcx, rsi; hModule
0x18002f13c  call    cs:__imp_LoadResource
0x18002f143  nop     dword ptr [rax+rax+00h]
0x18002f148  mov     r14, rax
0x18002f14b  mov     [rsp+4A8h+var_468], rax
0x18002f150  test    rax, rax
0x18002f153  jz      short loc_18002F12C
0x18002f155  mov     rdx, rbx; hResInfo
0x18002f158  mov     rcx, rsi; hModule
0x18002f15b  call    cs:__imp_SizeofResource
0x18002f162  nop     dword ptr [rax+rax+00h]
0x18002f167  mov     ebx, eax
0x18002f169  mov     [rsp+4A8h+var_478], eax
0x18002f16d  inc     eax
0x18002f16f  cmp     eax, ebx
0x18002f171  jnb     short loc_18002F17D
0x18002f173  mov     ebx, 8007000Eh
0x18002f178  jmp     loc_18002F22E
0x18002f17d  mov     ecx, eax
0x18002f17f  mov     edx, 2
0x18002f184  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18002f189  cmp     rax, 400h
0x18002f18f  jbe     short loc_18002F1A5
0x18002f191  mov     rdx, rax
0x18002f194  lea     rcx, [rsp+4A8h+var_448]
0x18002f199  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18002f19e  mov     rax, [rsp+4A8h+var_448]
0x18002f1a3  jmp     short loc_18002F1AF
0x18002f1a5  lea     rax, [rsp+4A8h+var_440]
0x18002f1aa  mov     [rsp+4A8h+var_448], rax
0x18002f1af  jmp     short loc_18002F1C6
0x18002f1b1  xor     edi, edi
0x18002f1b3  mov     rsi, [rsp+4A8h+var_470]
0x18002f1b8  mov     r14, [rsp+4A8h+var_468]
0x18002f1bd  mov     ebx, [rsp+4A8h+var_478]
0x18002f1c1  mov     rax, [rsp+4A8h+var_448]
0x18002f1c6  test    rax, rax
0x18002f1c9  jnz     short loc_18002F1D2
0x18002f1cb  mov     ebx, 8007000Eh
0x18002f1d0  jmp     short loc_18002F21E
0x18002f1d2  mov     [rsp+4A8h+cchWideChar], ebx; cchWideChar
0x18002f1d6  mov     [rsp+4A8h+lpWideCharStr], rax; lpWideCharStr
0x18002f1db  mov     r9d, ebx; cbMultiByte
0x18002f1de  mov     r8, r14; lpMultiByteStr
0x18002f1e1  xor     edx, edx; dwFlags
0x18002f1e3  lea     ecx, [rdx+3]; CodePage
0x18002f1e6  call    cs:__imp_MultiByteToWideChar
0x18002f1ed  nop     dword ptr [rax+rax+00h]
0x18002f1f2  test    eax, eax
0x18002f1f4  jz      loc_18002F12C
0x18002f1fa  mov     ecx, eax
0x18002f1fc  mov     rax, [rsp+4A8h+var_448]
0x18002f201  mov     [rax+rcx*2], di
0x18002f205  mov     r8d, [rsp+4A8h+arg_20]; int
0x18002f20d  mov     rdx, [rsp+4A8h+var_448]; unsigned __int16 *
0x18002f212  lea     rcx, [rsp+4A8h+var_458]; this
0x18002f217  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18002f21c  mov     ebx, eax
0x18002f21e  mov     rcx, rsi; hLibModule
0x18002f221  call    cs:__imp_FreeLibrary
0x18002f228  nop     dword ptr [rax+rax+00h]
0x18002f22d  nop
0x18002f22e  lea     rcx, [rsp+4A8h+var_448]
0x18002f233  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18002f238  nop
0x18002f239  lea     rcx, [rsp+4A8h+var_460]
0x18002f23e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002f243  mov     eax, ebx
0x18002f245  mov     rcx, [rsp+4A8h+var_38]
0x18002f24d  xor     rcx, rsp; StackCookie
0x18002f250  call    __security_check_cookie
0x18002f255  add     rsp, 480h
0x18002f25c  pop     r15
0x18002f25e  pop     r14
0x18002f260  pop     rdi
0x18002f261  pop     rsi
0x18002f262  pop     rbx
0x18002f263  retn
```
