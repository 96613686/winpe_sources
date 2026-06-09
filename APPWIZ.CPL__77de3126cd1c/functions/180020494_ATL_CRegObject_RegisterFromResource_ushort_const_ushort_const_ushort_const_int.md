# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180020494`
- end: `0x180020624`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `400`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800219fc`
- `0x180021c34`

## callees

- `0x18001ea8c`
- `0x18001ec8c`
- `0x18001ecbc`
- `0x18001f554`
- `0x18001f6b0`
- `0x1800202fc`
- `0x180020494`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800204ee`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800204ee`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180020546`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180020546`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180020532`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180020532`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180020514`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180020514`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800205e6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800205e6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800205b0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800205b0`

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
  unsigned __int64 v15; // rax
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
      Error = ResultFromLastError();
    }
    v9 = Error;
    goto LABEL_16;
  }
  v9 = ResultFromLastError();
LABEL_17:
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v21);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
  return v9;
}

```

## disassembly

```asm
0x180020494  mov     [rsp-8+arg_0], rbx
0x180020499  push    rbp
0x18002049a  push    rsi
0x18002049b  push    rdi
0x18002049c  lea     rbp, [rsp-370h]
0x1800204a4  sub     rsp, 470h
0x1800204ab  mov     rax, cs:__security_cookie
0x1800204b2  xor     rax, rsp
0x1800204b5  mov     [rbp+380h+var_20], rax
0x1800204bc  mov     rax, rdx
0x1800204bf  mov     [rsp+480h+var_440], rcx
0x1800204c4  xor     edx, edx; hFile
0x1800204c6  mov     [rsp+480h+var_450], 0
0x1800204cf  mov     rbx, r8
0x1800204d2  mov     [rsp+480h+var_448], 0
0x1800204db  mov     rcx, rax; lpLibFileName
0x1800204de  mov     [rsp+480h+var_430], 0
0x1800204e7  mov     rsi, r9
0x1800204ea  lea     r8d, [rdx+2]; dwFlags
0x1800204ee  call    cs:__imp_LoadLibraryExW
0x1800204f4  mov     rdi, rax
0x1800204f7  test    rax, rax
0x1800204fa  jnz     short loc_180020508
0x1800204fc  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180020501  mov     ebx, eax
0x180020503  jmp     loc_1800205EC
0x180020508  xor     r9d, r9d; wLanguage
0x18002050b  mov     r8, rbx; lpName
0x18002050e  mov     rdx, rsi; lpType
0x180020511  mov     rcx, rdi; hModule
0x180020514  call    cs:__imp_FindResourceExW
0x18002051a  mov     rbx, rax
0x18002051d  test    rax, rax
0x180020520  jnz     short loc_18002052C
0x180020522  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180020527  jmp     loc_1800205E1
0x18002052c  mov     rdx, rbx; hResInfo
0x18002052f  mov     rcx, rdi; hModule
0x180020532  call    cs:__imp_LoadResource
0x180020538  mov     rsi, rax
0x18002053b  test    rax, rax
0x18002053e  jz      short loc_180020522
0x180020540  mov     rdx, rbx; hResInfo
0x180020543  mov     rcx, rdi; hModule
0x180020546  call    cs:__imp_SizeofResource
0x18002054c  mov     ebx, eax
0x18002054e  inc     eax
0x180020550  cmp     eax, ebx
0x180020552  jnb     short loc_18002055E
0x180020554  mov     ebx, 8007000Eh
0x180020559  jmp     loc_1800205EC
0x18002055e  mov     ecx, eax
0x180020560  mov     edx, 2
0x180020565  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18002056a  cmp     rax, 400h
0x180020570  jbe     short loc_180020586
0x180020572  mov     rdx, rax
0x180020575  lea     rcx, [rsp+480h+var_430]
0x18002057a  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18002057f  mov     rax, [rsp+480h+var_430]
0x180020584  jmp     short loc_180020590
0x180020586  lea     rax, [rsp+480h+var_428]
0x18002058b  mov     [rsp+480h+var_430], rax
0x180020590  test    rax, rax
0x180020593  jnz     short loc_18002059C
0x180020595  mov     ebx, 8007000Eh
0x18002059a  jmp     short loc_1800205E3
0x18002059c  xor     edx, edx; dwFlags
0x18002059e  mov     [rsp+480h+cchWideChar], ebx; cchWideChar
0x1800205a2  mov     r9d, ebx; cbMultiByte
0x1800205a5  mov     [rsp+480h+lpWideCharStr], rax; lpWideCharStr
0x1800205aa  mov     r8, rsi; lpMultiByteStr
0x1800205ad  lea     ecx, [rdx+3]; CodePage
0x1800205b0  call    cs:__imp_MultiByteToWideChar
0x1800205b6  test    eax, eax
0x1800205b8  jz      loc_180020522
0x1800205be  mov     r8d, [rbp+380h+arg_20]; int
0x1800205c5  xor     ecx, ecx
0x1800205c7  mov     edx, eax
0x1800205c9  mov     rax, [rsp+480h+var_430]
0x1800205ce  mov     [rax+rdx*2], cx
0x1800205d2  lea     rcx, [rsp+480h+var_448]; this
0x1800205d7  mov     rdx, [rsp+480h+var_430]; unsigned __int16 *
0x1800205dc  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800205e1  mov     ebx, eax
0x1800205e3  mov     rcx, rdi; hLibModule
0x1800205e6  call    cs:__imp_FreeLibrary
0x1800205ec  lea     rcx, [rsp+480h+var_430]
0x1800205f1  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800205f6  lea     rcx, [rsp+480h+var_450]
0x1800205fb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180020600  mov     eax, ebx
0x180020602  mov     rcx, [rbp+380h+var_20]
0x180020609  xor     rcx, rsp; StackCookie
0x18002060c  call    __security_check_cookie
0x180020611  mov     rbx, [rsp+480h+arg_0]
0x180020619  add     rsp, 470h
0x180020620  pop     rdi
0x180020621  pop     rsi
0x180020622  pop     rbp
0x180020623  retn
```
