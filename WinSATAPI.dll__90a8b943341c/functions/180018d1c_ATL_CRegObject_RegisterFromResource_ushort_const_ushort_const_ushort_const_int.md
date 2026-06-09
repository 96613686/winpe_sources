# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180018d1c`
- end: `0x180018ef4`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `472`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180019e50`
- `0x18001a0dc`

## callees

- `0x180013e9c`
- `0x180013f48`
- `0x1800144ac`
- `0x180015454`
- `0x180015774`
- `0x180018b90`
- `0x180018d1c`
- `0x18002fb50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180018dc6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180018dc6`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180018de5`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180018de5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018d71`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018d71`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180018da2`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180018da2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018eab`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018eab`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180018e70`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180018e70`

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
0x180018d1c  mov     rax, rsp
0x180018d1f  push    rsi
0x180018d20  push    rdi
0x180018d21  push    r14
0x180018d23  sub     rsp, 490h
0x180018d2a  mov     [rsp+4A8h+var_448], 0FFFFFFFFFFFFFFFEh
0x180018d33  mov     [rax+8], rbx
0x180018d37  mov     rax, cs:__security_cookie
0x180018d3e  xor     rax, rsp
0x180018d41  mov     [rsp+4A8h+var_28], rax
0x180018d49  mov     r14, r9
0x180018d4c  mov     rdi, r8
0x180018d4f  mov     rax, rdx
0x180018d52  xor     ebx, ebx
0x180018d54  mov     [rsp+4A8h+var_460], rbx
0x180018d59  mov     [rsp+4A8h+var_450], rcx
0x180018d5e  mov     [rsp+4A8h+var_458], rbx
0x180018d63  mov     [rsp+4A8h+var_438], rbx
0x180018d68  xor     edx, edx; hFile
0x180018d6a  lea     r8d, [rbx+2]; dwFlags
0x180018d6e  mov     rcx, rax; lpLibFileName
0x180018d71  call    cs:__imp_LoadLibraryExW
0x180018d78  nop     dword ptr [rax+rax+00h]
0x180018d7d  mov     rsi, rax
0x180018d80  mov     [rsp+4A8h+var_470], rax
0x180018d85  test    rax, rax
0x180018d88  jnz     short loc_180018D96
0x180018d8a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180018d8f  mov     ebx, eax
0x180018d91  jmp     loc_180018EB8
0x180018d96  xor     r9d, r9d; wLanguage
0x180018d99  mov     r8, rdi; lpName
0x180018d9c  mov     rdx, r14; lpType
0x180018d9f  mov     rcx, rsi; hModule
0x180018da2  call    cs:__imp_FindResourceExW
0x180018da9  nop     dword ptr [rax+rax+00h]
0x180018dae  mov     rdi, rax
0x180018db1  test    rax, rax
0x180018db4  jnz     short loc_180018DC0
0x180018db6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180018dbb  jmp     loc_180018EA6
0x180018dc0  mov     rdx, rdi; hResInfo
0x180018dc3  mov     rcx, rsi; hModule
0x180018dc6  call    cs:__imp_LoadResource
0x180018dcd  nop     dword ptr [rax+rax+00h]
0x180018dd2  mov     r14, rax
0x180018dd5  mov     [rsp+4A8h+var_468], rax
0x180018dda  test    rax, rax
0x180018ddd  jz      short loc_180018DB6
0x180018ddf  mov     rdx, rdi; hResInfo
0x180018de2  mov     rcx, rsi; hModule
0x180018de5  call    cs:__imp_SizeofResource
0x180018dec  nop     dword ptr [rax+rax+00h]
0x180018df1  mov     edi, eax
0x180018df3  mov     [rsp+4A8h+var_478], eax
0x180018df7  inc     eax
0x180018df9  cmp     eax, edi
0x180018dfb  jnb     short loc_180018E07
0x180018dfd  mov     ebx, 8007000Eh
0x180018e02  jmp     loc_180018EB8
0x180018e07  mov     ecx, eax
0x180018e09  mov     edx, 2
0x180018e0e  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180018e13  cmp     rax, 400h
0x180018e19  jbe     short loc_180018E2F
0x180018e1b  mov     rdx, rax
0x180018e1e  lea     rcx, [rsp+4A8h+var_438]
0x180018e23  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180018e28  mov     rax, [rsp+4A8h+var_438]
0x180018e2d  jmp     short loc_180018E39
0x180018e2f  lea     rax, [rsp+4A8h+var_430]
0x180018e34  mov     [rsp+4A8h+var_438], rax
0x180018e39  jmp     short loc_180018E50
0x180018e3b  xor     ebx, ebx
0x180018e3d  mov     rsi, [rsp+4A8h+var_470]
0x180018e42  mov     r14, [rsp+4A8h+var_468]
0x180018e47  mov     edi, [rsp+4A8h+var_478]
0x180018e4b  mov     rax, [rsp+4A8h+var_438]
0x180018e50  test    rax, rax
0x180018e53  jnz     short loc_180018E5C
0x180018e55  mov     ebx, 8007000Eh
0x180018e5a  jmp     short loc_180018EA8
0x180018e5c  mov     [rsp+4A8h+cchWideChar], edi; cchWideChar
0x180018e60  mov     [rsp+4A8h+lpWideCharStr], rax; lpWideCharStr
0x180018e65  mov     r9d, edi; cbMultiByte
0x180018e68  mov     r8, r14; lpMultiByteStr
0x180018e6b  xor     edx, edx; dwFlags
0x180018e6d  lea     ecx, [rdx+3]; CodePage
0x180018e70  call    cs:__imp_MultiByteToWideChar
0x180018e77  nop     dword ptr [rax+rax+00h]
0x180018e7c  test    eax, eax
0x180018e7e  jz      loc_180018DB6
0x180018e84  mov     ecx, eax
0x180018e86  mov     rax, [rsp+4A8h+var_438]
0x180018e8b  mov     [rax+rcx*2], bx
0x180018e8f  mov     r8d, [rsp+4A8h+arg_20]; int
0x180018e97  mov     rdx, [rsp+4A8h+var_438]; unsigned __int16 *
0x180018e9c  lea     rcx, [rsp+4A8h+var_458]; this
0x180018ea1  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180018ea6  mov     ebx, eax
0x180018ea8  mov     rcx, rsi; hLibModule
0x180018eab  call    cs:__imp_FreeLibrary
0x180018eb2  nop     dword ptr [rax+rax+00h]
0x180018eb7  nop
0x180018eb8  lea     rcx, [rsp+4A8h+var_438]
0x180018ebd  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180018ec2  nop
0x180018ec3  lea     rcx, [rsp+4A8h+var_460]
0x180018ec8  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180018ecd  mov     eax, ebx
0x180018ecf  mov     rcx, [rsp+4A8h+var_28]
0x180018ed7  xor     rcx, rsp; StackCookie
0x180018eda  call    __security_check_cookie
0x180018edf  mov     rbx, [rsp+4A8h+arg_0]
0x180018ee7  add     rsp, 490h
0x180018eee  pop     r14
0x180018ef0  pop     rdi
0x180018ef1  pop     rsi
0x180018ef2  retn
```
