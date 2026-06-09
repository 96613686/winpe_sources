# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800798ec`
- end: `0x180079aa1`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `437`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18007aa40`
- `0x18007acac`

## callees

- `0x180074160`
- `0x180076924`
- `0x180076b00`
- `0x180076c60`
- `0x180077664`
- `0x1800778ec`
- `0x18007976c`
- `0x1800798ec`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180079a5c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180079a5c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180079946`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180079946`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800799b0`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800799b0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180079996`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180079996`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180079972`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180079972`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180079a20`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180079a20`

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
0x1800798ec  mov     [rsp-8+arg_0], rbx
0x1800798f1  push    rbp
0x1800798f2  push    rsi
0x1800798f3  push    rdi
0x1800798f4  lea     rbp, [rsp-370h]
0x1800798fc  sub     rsp, 470h
0x180079903  mov     rax, cs:__security_cookie
0x18007990a  xor     rax, rsp
0x18007990d  mov     [rbp+380h+var_20], rax
0x180079914  mov     rax, rdx
0x180079917  mov     [rsp+480h+var_440], rcx
0x18007991c  xor     edx, edx; hFile
0x18007991e  mov     [rsp+480h+var_450], 0
0x180079927  mov     rbx, r8
0x18007992a  mov     [rsp+480h+var_448], 0
0x180079933  mov     rcx, rax; lpLibFileName
0x180079936  mov     [rsp+480h+var_430], 0
0x18007993f  mov     rsi, r9
0x180079942  lea     r8d, [rdx+2]; dwFlags
0x180079946  call    cs:__imp_LoadLibraryExW
0x18007994d  nop     dword ptr [rax+rax+00h]
0x180079952  mov     rdi, rax
0x180079955  test    rax, rax
0x180079958  jnz     short loc_180079966
0x18007995a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007995f  mov     ebx, eax
0x180079961  jmp     loc_180079A68
0x180079966  xor     r9d, r9d; wLanguage
0x180079969  mov     r8, rbx; lpName
0x18007996c  mov     rdx, rsi; lpType
0x18007996f  mov     rcx, rdi; hModule
0x180079972  call    cs:__imp_FindResourceExW
0x180079979  nop     dword ptr [rax+rax+00h]
0x18007997e  mov     rbx, rax
0x180079981  test    rax, rax
0x180079984  jnz     short loc_180079990
0x180079986  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007998b  jmp     loc_180079A57
0x180079990  mov     rdx, rbx; hResInfo
0x180079993  mov     rcx, rdi; hModule
0x180079996  call    cs:__imp_LoadResource
0x18007999d  nop     dword ptr [rax+rax+00h]
0x1800799a2  mov     rsi, rax
0x1800799a5  test    rax, rax
0x1800799a8  jz      short loc_180079986
0x1800799aa  mov     rdx, rbx; hResInfo
0x1800799ad  mov     rcx, rdi; hModule
0x1800799b0  call    cs:__imp_SizeofResource
0x1800799b7  nop     dword ptr [rax+rax+00h]
0x1800799bc  mov     ebx, eax
0x1800799be  inc     eax
0x1800799c0  cmp     eax, ebx
0x1800799c2  jnb     short loc_1800799CE
0x1800799c4  mov     ebx, 8007000Eh
0x1800799c9  jmp     loc_180079A68
0x1800799ce  mov     ecx, eax
0x1800799d0  mov     edx, 2
0x1800799d5  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800799da  cmp     rax, 400h
0x1800799e0  jbe     short loc_1800799F6
0x1800799e2  mov     rdx, rax
0x1800799e5  lea     rcx, [rsp+480h+var_430]
0x1800799ea  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800799ef  mov     rax, [rsp+480h+var_430]
0x1800799f4  jmp     short loc_180079A00
0x1800799f6  lea     rax, [rsp+480h+var_428]
0x1800799fb  mov     [rsp+480h+var_430], rax
0x180079a00  test    rax, rax
0x180079a03  jnz     short loc_180079A0C
0x180079a05  mov     ebx, 8007000Eh
0x180079a0a  jmp     short loc_180079A59
0x180079a0c  xor     edx, edx; dwFlags
0x180079a0e  mov     [rsp+480h+cchWideChar], ebx; cchWideChar
0x180079a12  mov     r9d, ebx; cbMultiByte
0x180079a15  mov     [rsp+480h+lpWideCharStr], rax; lpWideCharStr
0x180079a1a  mov     r8, rsi; lpMultiByteStr
0x180079a1d  lea     ecx, [rdx+3]; CodePage
0x180079a20  call    cs:__imp_MultiByteToWideChar
0x180079a27  nop     dword ptr [rax+rax+00h]
0x180079a2c  test    eax, eax
0x180079a2e  jz      loc_180079986
0x180079a34  mov     r8d, [rbp+380h+arg_20]; int
0x180079a3b  xor     ecx, ecx
0x180079a3d  mov     edx, eax
0x180079a3f  mov     rax, [rsp+480h+var_430]
0x180079a44  mov     [rax+rdx*2], cx
0x180079a48  lea     rcx, [rsp+480h+var_448]; this
0x180079a4d  mov     rdx, [rsp+480h+var_430]; unsigned __int16 *
0x180079a52  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180079a57  mov     ebx, eax
0x180079a59  mov     rcx, rdi; hLibModule
0x180079a5c  call    cs:__imp_FreeLibrary
0x180079a63  nop     dword ptr [rax+rax+00h]
0x180079a68  lea     rcx, [rsp+480h+var_430]
0x180079a6d  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180079a72  lea     rcx, [rsp+480h+var_450]
0x180079a77  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180079a7c  mov     eax, ebx
0x180079a7e  mov     rcx, [rbp+380h+var_20]
0x180079a85  xor     rcx, rsp; StackCookie
0x180079a88  call    __security_check_cookie
0x180079a8d  mov     rbx, [rsp+480h+arg_0]
0x180079a95  add     rsp, 470h
0x180079a9c  pop     rdi
0x180079a9d  pop     rsi
0x180079a9e  pop     rbp
0x180079a9f  retn
```
