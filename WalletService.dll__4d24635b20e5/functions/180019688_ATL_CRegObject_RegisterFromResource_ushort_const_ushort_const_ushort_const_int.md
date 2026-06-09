# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180019688`
- end: `0x180019818`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `400`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001a31c`
- `0x18001a56c`

## callees

- `0x180016f68`
- `0x180017530`
- `0x180017588`
- `0x180017ff0`
- `0x1800180ec`
- `0x180019514`
- `0x180019688`
- `0x180043090`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800196e2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800196e2`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001973a`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001973a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180019726`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180019726`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180019708`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180019708`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800197da`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800197da`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800197a4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800197a4`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v8; // rdi
  unsigned int v9; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rbx
  unsigned int Error; // eax
  const CHAR *v13; // rsi
  DWORD cchWideChar; // ebx
  size_t v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v20[3]; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[1032]; // [rsp+58h] [rbp-A8h] BYREF

  v20[1] = this;
  v19 = 0;
  v20[0] = 0;
  v21 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
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
    v15 = ATL::AtlMultiplyThrow<unsigned __int64>(cchWideChar + 1, 2);
    if ( v15 <= 0x400 )
    {
      lpWideCharStr = (WCHAR *)v22;
      v21 = (LPWSTR)v22;
    }
    else
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v21, v15);
      lpWideCharStr = v21;
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
      v21[v17] = 0;
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v20, v21, a5);
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
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v21);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
  return v9;
}

```

## disassembly

```asm
0x180019688  mov     [rsp-8+arg_0], rbx
0x18001968d  push    rbp
0x18001968e  push    rsi
0x18001968f  push    rdi
0x180019690  lea     rbp, [rsp-370h]
0x180019698  sub     rsp, 470h
0x18001969f  mov     rax, cs:__security_cookie
0x1800196a6  xor     rax, rsp
0x1800196a9  mov     [rbp+380h+var_20], rax
0x1800196b0  mov     rax, rdx
0x1800196b3  mov     [rsp+480h+var_440], rcx
0x1800196b8  xor     edx, edx; hFile
0x1800196ba  mov     [rsp+480h+var_450], 0
0x1800196c3  mov     rbx, r8
0x1800196c6  mov     [rsp+480h+var_448], 0
0x1800196cf  mov     rcx, rax; lpLibFileName
0x1800196d2  mov     [rsp+480h+var_430], 0
0x1800196db  mov     rsi, r9
0x1800196de  lea     r8d, [rdx+2]; dwFlags
0x1800196e2  call    cs:__imp_LoadLibraryExW
0x1800196e8  mov     rdi, rax
0x1800196eb  test    rax, rax
0x1800196ee  jnz     short loc_1800196FC
0x1800196f0  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800196f5  mov     ebx, eax
0x1800196f7  jmp     loc_1800197E0
0x1800196fc  xor     r9d, r9d; wLanguage
0x1800196ff  mov     r8, rbx; lpName
0x180019702  mov     rdx, rsi; lpType
0x180019705  mov     rcx, rdi; hModule
0x180019708  call    cs:__imp_FindResourceExW
0x18001970e  mov     rbx, rax
0x180019711  test    rax, rax
0x180019714  jnz     short loc_180019720
0x180019716  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001971b  jmp     loc_1800197D5
0x180019720  mov     rdx, rbx; hResInfo
0x180019723  mov     rcx, rdi; hModule
0x180019726  call    cs:__imp_LoadResource
0x18001972c  mov     rsi, rax
0x18001972f  test    rax, rax
0x180019732  jz      short loc_180019716
0x180019734  mov     rdx, rbx; hResInfo
0x180019737  mov     rcx, rdi; hModule
0x18001973a  call    cs:__imp_SizeofResource
0x180019740  mov     ebx, eax
0x180019742  inc     eax
0x180019744  cmp     eax, ebx
0x180019746  jnb     short loc_180019752
0x180019748  mov     ebx, 8007000Eh
0x18001974d  jmp     loc_1800197E0
0x180019752  mov     ecx, eax
0x180019754  mov     edx, 2
0x180019759  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18001975e  cmp     rax, 400h
0x180019764  jbe     short loc_18001977A
0x180019766  mov     rdx, rax
0x180019769  lea     rcx, [rsp+480h+var_430]
0x18001976e  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180019773  mov     rax, [rsp+480h+var_430]
0x180019778  jmp     short loc_180019784
0x18001977a  lea     rax, [rsp+480h+var_428]
0x18001977f  mov     [rsp+480h+var_430], rax
0x180019784  test    rax, rax
0x180019787  jnz     short loc_180019790
0x180019789  mov     ebx, 8007000Eh
0x18001978e  jmp     short loc_1800197D7
0x180019790  xor     edx, edx; dwFlags
0x180019792  mov     [rsp+480h+cchWideChar], ebx; cchWideChar
0x180019796  mov     r9d, ebx; cbMultiByte
0x180019799  mov     [rsp+480h+lpWideCharStr], rax; lpWideCharStr
0x18001979e  mov     r8, rsi; lpMultiByteStr
0x1800197a1  lea     ecx, [rdx+3]; CodePage
0x1800197a4  call    cs:__imp_MultiByteToWideChar
0x1800197aa  test    eax, eax
0x1800197ac  jz      loc_180019716
0x1800197b2  mov     r8d, [rbp+380h+arg_20]; int
0x1800197b9  xor     ecx, ecx
0x1800197bb  mov     edx, eax
0x1800197bd  mov     rax, [rsp+480h+var_430]
0x1800197c2  mov     [rax+rdx*2], cx
0x1800197c6  lea     rcx, [rsp+480h+var_448]; this
0x1800197cb  mov     rdx, [rsp+480h+var_430]; unsigned __int16 *
0x1800197d0  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800197d5  mov     ebx, eax
0x1800197d7  mov     rcx, rdi; hLibModule
0x1800197da  call    cs:__imp_FreeLibrary
0x1800197e0  lea     rcx, [rsp+480h+var_430]
0x1800197e5  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800197ea  lea     rcx, [rsp+480h+var_450]
0x1800197ef  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800197f4  mov     eax, ebx
0x1800197f6  mov     rcx, [rbp+380h+var_20]
0x1800197fd  xor     rcx, rsp; StackCookie
0x180019800  call    __security_check_cookie
0x180019805  mov     rbx, [rsp+480h+arg_0]
0x18001980d  add     rsp, 470h
0x180019814  pop     rdi
0x180019815  pop     rsi
0x180019816  pop     rbp
0x180019817  retn
```
