# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800192e0`
- end: `0x180019488`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180019e1c`
- `0x18001a094`

## callees

- `0x180016020`
- `0x180017584`
- `0x1800175c0`
- `0x180017654`
- `0x180018064`
- `0x180018300`
- `0x18001916c`
- `0x1800192e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180019355`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180019355`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001938c`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001938c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180019373`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180019373`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180019446`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180019446`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001932a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001932a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180019411`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180019411`

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
  size_t v15; // rax
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
0x1800192e0  mov     [rsp+arg_0], rbx
0x1800192e5  push    rsi
0x1800192e6  push    rdi
0x1800192e7  push    r14
0x1800192e9  sub     rsp, 480h
0x1800192f0  mov     rax, cs:__security_cookie
0x1800192f7  xor     rax, rsp
0x1800192fa  mov     [rsp+498h+var_28], rax
0x180019302  mov     r14, r9
0x180019305  mov     rdi, r8
0x180019308  mov     rax, rdx
0x18001930b  xor     ebx, ebx
0x18001930d  mov     [rsp+498h+var_450], rbx
0x180019312  mov     [rsp+498h+var_440], rcx
0x180019317  mov     [rsp+498h+var_448], rbx
0x18001931c  mov     [rsp+498h+var_438], rbx
0x180019321  xor     edx, edx; hFile
0x180019323  lea     r8d, [rbx+2]; dwFlags
0x180019327  mov     rcx, rax; lpLibFileName
0x18001932a  call    cs:__imp_LoadLibraryExW
0x180019330  mov     rsi, rax
0x180019333  mov     [rsp+498h+var_460], rax
0x180019338  test    rax, rax
0x18001933b  jnz     short loc_180019349
0x18001933d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180019342  mov     ebx, eax
0x180019344  jmp     loc_18001944D
0x180019349  xor     r9d, r9d; wLanguage
0x18001934c  mov     r8, rdi; lpName
0x18001934f  mov     rdx, r14; lpType
0x180019352  mov     rcx, rsi; hModule
0x180019355  call    cs:__imp_FindResourceExW
0x18001935b  mov     rdi, rax
0x18001935e  test    rax, rax
0x180019361  jnz     short loc_18001936D
0x180019363  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180019368  jmp     loc_180019441
0x18001936d  mov     rdx, rdi; hResInfo
0x180019370  mov     rcx, rsi; hModule
0x180019373  call    cs:__imp_LoadResource
0x180019379  mov     r14, rax
0x18001937c  mov     [rsp+498h+var_458], rax
0x180019381  test    rax, rax
0x180019384  jz      short loc_180019363
0x180019386  mov     rdx, rdi; hResInfo
0x180019389  mov     rcx, rsi; hModule
0x18001938c  call    cs:__imp_SizeofResource
0x180019392  mov     edi, eax
0x180019394  mov     [rsp+498h+var_468], eax
0x180019398  inc     eax
0x18001939a  cmp     eax, edi
0x18001939c  jnb     short loc_1800193A8
0x18001939e  mov     ebx, 8007000Eh
0x1800193a3  jmp     loc_18001944D
0x1800193a8  mov     ecx, eax
0x1800193aa  mov     edx, 2
0x1800193af  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800193b4  cmp     rax, 400h
0x1800193ba  jbe     short loc_1800193D0
0x1800193bc  mov     rdx, rax
0x1800193bf  lea     rcx, [rsp+498h+var_438]
0x1800193c4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800193c9  mov     rax, [rsp+498h+var_438]
0x1800193ce  jmp     short loc_1800193DA
0x1800193d0  lea     rax, [rsp+498h+var_430]
0x1800193d5  mov     [rsp+498h+var_438], rax
0x1800193da  jmp     short loc_1800193F1
0x1800193dc  xor     ebx, ebx
0x1800193de  mov     rsi, [rsp+498h+var_460]
0x1800193e3  mov     r14, [rsp+498h+var_458]
0x1800193e8  mov     edi, [rsp+498h+var_468]
0x1800193ec  mov     rax, [rsp+498h+var_438]
0x1800193f1  test    rax, rax
0x1800193f4  jnz     short loc_1800193FD
0x1800193f6  mov     ebx, 8007000Eh
0x1800193fb  jmp     short loc_180019443
0x1800193fd  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180019401  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180019406  mov     r9d, edi; cbMultiByte
0x180019409  mov     r8, r14; lpMultiByteStr
0x18001940c  xor     edx, edx; dwFlags
0x18001940e  lea     ecx, [rdx+3]; CodePage
0x180019411  call    cs:__imp_MultiByteToWideChar
0x180019417  test    eax, eax
0x180019419  jz      loc_180019363
0x18001941f  mov     ecx, eax
0x180019421  mov     rax, [rsp+498h+var_438]
0x180019426  mov     [rax+rcx*2], bx
0x18001942a  mov     r8d, [rsp+498h+arg_20]; int
0x180019432  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180019437  lea     rcx, [rsp+498h+var_448]; this
0x18001943c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180019441  mov     ebx, eax
0x180019443  mov     rcx, rsi; hLibModule
0x180019446  call    cs:__imp_FreeLibrary
0x18001944c  nop
0x18001944d  lea     rcx, [rsp+498h+var_438]
0x180019452  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180019457  nop
0x180019458  lea     rcx, [rsp+498h+var_450]
0x18001945d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180019462  mov     eax, ebx
0x180019464  mov     rcx, [rsp+498h+var_28]
0x18001946c  xor     rcx, rsp; StackCookie
0x18001946f  call    __security_check_cookie
0x180019474  mov     rbx, [rsp+498h+arg_0]
0x18001947c  add     rsp, 480h
0x180019483  pop     r14
0x180019485  pop     rdi
0x180019486  pop     rsi
0x180019487  retn
```
