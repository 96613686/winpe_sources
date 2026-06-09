# ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)

- ea: `0x140022c44`
- end: `0x140022df7`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z`
- size: `435`
- prototype: `int(ATL::CRegObject *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400249cc`
- `0x140024c4c`

## callees

- `0x1400030a0`
- `0x140019e6c`
- `0x14001b6ec`
- `0x14001b888`
- `0x14001d318`
- `0x14001d4e8`
- `0x140022ad0`
- `0x140022c44`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x140022ce2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x140022ce2`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x140022cfb`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x140022cfb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140022db5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140022db5`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x140022cc4`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x140022cc4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140022c99`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140022c99`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140022d80`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140022d80`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
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
  size_t v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  HMODULE v19; // [rsp+38h] [rbp-470h]
  __int64 v20; // [rsp+48h] [rbp-460h] BYREF
  _QWORD v21[4]; // [rsp+50h] [rbp-458h] BYREF
  LPWSTR v22; // [rsp+70h] [rbp-438h] BYREF
  _BYTE v23[1032]; // [rsp+78h] [rbp-430h] BYREF

  v21[2] = -2;
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
        ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&v22, v15);
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
      Error = ResultFromLastError();
    }
    v9 = Error;
    goto LABEL_16;
  }
  v9 = ResultFromLastError();
LABEL_17:
  ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&v22);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
  return v9;
}

```

## disassembly

```asm
0x140022c44  mov     rax, rsp
0x140022c47  push    rsi
0x140022c48  push    rdi
0x140022c49  push    r14
0x140022c4b  sub     rsp, 490h
0x140022c52  mov     [rsp+4A8h+var_448], 0FFFFFFFFFFFFFFFEh
0x140022c5b  mov     [rax+8], rbx
0x140022c5f  mov     rax, cs:__security_cookie
0x140022c66  xor     rax, rsp
0x140022c69  mov     [rsp+4A8h+var_28], rax
0x140022c71  mov     r14, r9
0x140022c74  mov     rdi, r8
0x140022c77  mov     rax, rdx
0x140022c7a  xor     ebx, ebx
0x140022c7c  mov     [rsp+4A8h+var_460], rbx
0x140022c81  mov     [rsp+4A8h+var_450], rcx
0x140022c86  mov     [rsp+4A8h+var_458], rbx
0x140022c8b  mov     [rsp+4A8h+var_438], rbx
0x140022c90  xor     edx, edx; hFile
0x140022c92  lea     r8d, [rbx+2]; dwFlags
0x140022c96  mov     rcx, rax; lpLibFileName
0x140022c99  call    cs:__imp_LoadLibraryExW
0x140022c9f  mov     rsi, rax
0x140022ca2  mov     [rsp+4A8h+var_470], rax
0x140022ca7  test    rax, rax
0x140022caa  jnz     short loc_140022CB8
0x140022cac  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140022cb1  mov     ebx, eax
0x140022cb3  jmp     loc_140022DBC
0x140022cb8  xor     r9d, r9d; wLanguage
0x140022cbb  mov     r8, rdi; lpName
0x140022cbe  mov     rdx, r14; lpType
0x140022cc1  mov     rcx, rsi; hModule
0x140022cc4  call    cs:__imp_FindResourceExW
0x140022cca  mov     rdi, rax
0x140022ccd  test    rax, rax
0x140022cd0  jnz     short loc_140022CDC
0x140022cd2  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140022cd7  jmp     loc_140022DB0
0x140022cdc  mov     rdx, rdi; hResInfo
0x140022cdf  mov     rcx, rsi; hModule
0x140022ce2  call    cs:__imp_LoadResource
0x140022ce8  mov     r14, rax
0x140022ceb  mov     [rsp+4A8h+var_468], rax
0x140022cf0  test    rax, rax
0x140022cf3  jz      short loc_140022CD2
0x140022cf5  mov     rdx, rdi; hResInfo
0x140022cf8  mov     rcx, rsi; hModule
0x140022cfb  call    cs:__imp_SizeofResource
0x140022d01  mov     edi, eax
0x140022d03  mov     [rsp+4A8h+var_478], eax
0x140022d07  inc     eax
0x140022d09  cmp     eax, edi
0x140022d0b  jnb     short loc_140022D17
0x140022d0d  mov     ebx, 8007000Eh
0x140022d12  jmp     loc_140022DBC
0x140022d17  mov     ecx, eax
0x140022d19  mov     edx, 2
0x140022d1e  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x140022d23  cmp     rax, 400h
0x140022d29  jbe     short loc_140022D3F
0x140022d2b  mov     rdx, rax
0x140022d2e  lea     rcx, [rsp+4A8h+var_438]
0x140022d33  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140022d38  mov     rax, [rsp+4A8h+var_438]
0x140022d3d  jmp     short loc_140022D49
0x140022d3f  lea     rax, [rsp+4A8h+var_430]
0x140022d44  mov     [rsp+4A8h+var_438], rax
0x140022d49  jmp     short loc_140022D60
0x140022d4b  xor     ebx, ebx
0x140022d4d  mov     rsi, [rsp+4A8h+var_470]
0x140022d52  mov     r14, [rsp+4A8h+var_468]
0x140022d57  mov     edi, [rsp+4A8h+var_478]
0x140022d5b  mov     rax, [rsp+4A8h+var_438]
0x140022d60  test    rax, rax
0x140022d63  jnz     short loc_140022D6C
0x140022d65  mov     ebx, 8007000Eh
0x140022d6a  jmp     short loc_140022DB2
0x140022d6c  mov     [rsp+4A8h+cchWideChar], edi; cchWideChar
0x140022d70  mov     [rsp+4A8h+lpWideCharStr], rax; lpWideCharStr
0x140022d75  mov     r9d, edi; cbMultiByte
0x140022d78  mov     r8, r14; lpMultiByteStr
0x140022d7b  xor     edx, edx; dwFlags
0x140022d7d  lea     ecx, [rdx+3]; CodePage
0x140022d80  call    cs:__imp_MultiByteToWideChar
0x140022d86  test    eax, eax
0x140022d88  jz      loc_140022CD2
0x140022d8e  mov     ecx, eax
0x140022d90  mov     rax, [rsp+4A8h+var_438]
0x140022d95  mov     [rax+rcx*2], bx
0x140022d99  mov     r8d, [rsp+4A8h+arg_20]; int
0x140022da1  mov     rdx, [rsp+4A8h+var_438]; wchar_t *
0x140022da6  lea     rcx, [rsp+4A8h+var_458]; this
0x140022dab  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z; ATL::CRegParser::RegisterBuffer(wchar_t *,int)
0x140022db0  mov     ebx, eax
0x140022db2  mov     rcx, rsi; hLibModule
0x140022db5  call    cs:__imp_FreeLibrary
0x140022dbb  nop
0x140022dbc  lea     rcx, [rsp+4A8h+var_438]
0x140022dc1  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x140022dc6  nop
0x140022dc7  lea     rcx, [rsp+4A8h+var_460]
0x140022dcc  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140022dd1  mov     eax, ebx
0x140022dd3  mov     rcx, [rsp+4A8h+var_28]
0x140022ddb  xor     rcx, rsp; StackCookie
0x140022dde  call    __security_check_cookie
0x140022de3  mov     rbx, [rsp+4A8h+arg_0]
0x140022deb  add     rsp, 490h
0x140022df2  pop     r14
0x140022df4  pop     rdi
0x140022df5  pop     rsi
0x140022df6  retn
```
