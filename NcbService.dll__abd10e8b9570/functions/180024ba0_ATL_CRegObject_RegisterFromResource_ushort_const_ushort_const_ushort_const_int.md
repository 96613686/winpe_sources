# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180024ba0`
- end: `0x180024d48`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800254dc`
- `0x18002575c`

## callees

- `0x18001d8e0`
- `0x180023484`
- `0x1800234bc`
- `0x180023510`
- `0x180023ef4`
- `0x1800240b4`
- `0x180024a2c`
- `0x180024ba0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180024c33`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180024c33`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180024c15`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180024c15`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180024c4c`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180024c4c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024d06`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024d06`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024bea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024bea`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180024cd1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180024cd1`

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
      v15 = ATL::AtlMultiplyThrow<unsigned __int64>(cchWideChar + 1, 2);
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
0x180024ba0  mov     [rsp+arg_0], rbx
0x180024ba5  push    rsi
0x180024ba6  push    rdi
0x180024ba7  push    r14
0x180024ba9  sub     rsp, 480h
0x180024bb0  mov     rax, cs:__security_cookie
0x180024bb7  xor     rax, rsp
0x180024bba  mov     [rsp+498h+var_28], rax
0x180024bc2  mov     r14, r9
0x180024bc5  mov     rdi, r8
0x180024bc8  mov     rax, rdx
0x180024bcb  xor     ebx, ebx
0x180024bcd  mov     [rsp+498h+var_450], rbx
0x180024bd2  mov     [rsp+498h+var_440], rcx
0x180024bd7  mov     [rsp+498h+var_448], rbx
0x180024bdc  mov     [rsp+498h+var_438], rbx
0x180024be1  xor     edx, edx; hFile
0x180024be3  lea     r8d, [rbx+2]; dwFlags
0x180024be7  mov     rcx, rax; lpLibFileName
0x180024bea  call    cs:__imp_LoadLibraryExW
0x180024bf0  mov     rsi, rax
0x180024bf3  mov     [rsp+498h+var_460], rax
0x180024bf8  test    rax, rax
0x180024bfb  jnz     short loc_180024C09
0x180024bfd  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180024c02  mov     ebx, eax
0x180024c04  jmp     loc_180024D0D
0x180024c09  xor     r9d, r9d; wLanguage
0x180024c0c  mov     r8, rdi; lpName
0x180024c0f  mov     rdx, r14; lpType
0x180024c12  mov     rcx, rsi; hModule
0x180024c15  call    cs:__imp_FindResourceExW
0x180024c1b  mov     rdi, rax
0x180024c1e  test    rax, rax
0x180024c21  jnz     short loc_180024C2D
0x180024c23  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180024c28  jmp     loc_180024D01
0x180024c2d  mov     rdx, rdi; hResInfo
0x180024c30  mov     rcx, rsi; hModule
0x180024c33  call    cs:__imp_LoadResource
0x180024c39  mov     r14, rax
0x180024c3c  mov     [rsp+498h+var_458], rax
0x180024c41  test    rax, rax
0x180024c44  jz      short loc_180024C23
0x180024c46  mov     rdx, rdi; hResInfo
0x180024c49  mov     rcx, rsi; hModule
0x180024c4c  call    cs:__imp_SizeofResource
0x180024c52  mov     edi, eax
0x180024c54  mov     [rsp+498h+var_468], eax
0x180024c58  inc     eax
0x180024c5a  cmp     eax, edi
0x180024c5c  jnb     short loc_180024C68
0x180024c5e  mov     ebx, 8007000Eh
0x180024c63  jmp     loc_180024D0D
0x180024c68  mov     ecx, eax
0x180024c6a  mov     edx, 2
0x180024c6f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180024c74  cmp     rax, 400h
0x180024c7a  jbe     short loc_180024C90
0x180024c7c  mov     rdx, rax
0x180024c7f  lea     rcx, [rsp+498h+var_438]
0x180024c84  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180024c89  mov     rax, [rsp+498h+var_438]
0x180024c8e  jmp     short loc_180024C9A
0x180024c90  lea     rax, [rsp+498h+var_430]
0x180024c95  mov     [rsp+498h+var_438], rax
0x180024c9a  jmp     short loc_180024CB1
0x180024c9c  xor     ebx, ebx
0x180024c9e  mov     rsi, [rsp+498h+var_460]
0x180024ca3  mov     r14, [rsp+498h+var_458]
0x180024ca8  mov     edi, [rsp+498h+var_468]
0x180024cac  mov     rax, [rsp+498h+var_438]
0x180024cb1  test    rax, rax
0x180024cb4  jnz     short loc_180024CBD
0x180024cb6  mov     ebx, 8007000Eh
0x180024cbb  jmp     short loc_180024D03
0x180024cbd  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180024cc1  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180024cc6  mov     r9d, edi; cbMultiByte
0x180024cc9  mov     r8, r14; lpMultiByteStr
0x180024ccc  xor     edx, edx; dwFlags
0x180024cce  lea     ecx, [rdx+3]; CodePage
0x180024cd1  call    cs:__imp_MultiByteToWideChar
0x180024cd7  test    eax, eax
0x180024cd9  jz      loc_180024C23
0x180024cdf  mov     ecx, eax
0x180024ce1  mov     rax, [rsp+498h+var_438]
0x180024ce6  mov     [rax+rcx*2], bx
0x180024cea  mov     r8d, [rsp+498h+arg_20]; int
0x180024cf2  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180024cf7  lea     rcx, [rsp+498h+var_448]; this
0x180024cfc  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180024d01  mov     ebx, eax
0x180024d03  mov     rcx, rsi; hLibModule
0x180024d06  call    cs:__imp_FreeLibrary
0x180024d0c  nop
0x180024d0d  lea     rcx, [rsp+498h+var_438]
0x180024d12  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180024d17  nop
0x180024d18  lea     rcx, [rsp+498h+var_450]
0x180024d1d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180024d22  mov     eax, ebx
0x180024d24  mov     rcx, [rsp+498h+var_28]
0x180024d2c  xor     rcx, rsp; StackCookie
0x180024d2f  call    __security_check_cookie
0x180024d34  mov     rbx, [rsp+498h+arg_0]
0x180024d3c  add     rsp, 480h
0x180024d43  pop     r14
0x180024d45  pop     rdi
0x180024d46  pop     rsi
0x180024d47  retn
```
