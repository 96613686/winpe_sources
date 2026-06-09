# ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)

- ea: `0x140024888`
- end: `0x140024a3b`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z`
- size: `435`
- prototype: `int(ATL::CRegObject *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140031cdc`
- `0x140031f64`

## callees

- `0x140005240`
- `0x140007d44`
- `0x14000e534`
- `0x14000e6ec`
- `0x1400121e8`
- `0x1400124cc`
- `0x140024714`
- `0x140024888`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400249f9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400249f9`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x14002493f`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x14002493f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400248dd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400248dd`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x140024908`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x140024908`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x140024926`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x140024926`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400249c4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400249c4`

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
0x140024888  mov     rax, rsp
0x14002488b  push    rsi
0x14002488c  push    rdi
0x14002488d  push    r14
0x14002488f  sub     rsp, 490h
0x140024896  mov     [rsp+4A8h+var_448], 0FFFFFFFFFFFFFFFEh
0x14002489f  mov     [rax+8], rbx
0x1400248a3  mov     rax, cs:__security_cookie
0x1400248aa  xor     rax, rsp
0x1400248ad  mov     [rsp+4A8h+var_28], rax
0x1400248b5  mov     r14, r9
0x1400248b8  mov     rdi, r8
0x1400248bb  mov     rax, rdx
0x1400248be  xor     ebx, ebx
0x1400248c0  mov     [rsp+4A8h+var_460], rbx
0x1400248c5  mov     [rsp+4A8h+var_450], rcx
0x1400248ca  mov     [rsp+4A8h+var_458], rbx
0x1400248cf  mov     [rsp+4A8h+var_438], rbx
0x1400248d4  xor     edx, edx; hFile
0x1400248d6  lea     r8d, [rbx+2]; dwFlags
0x1400248da  mov     rcx, rax; lpLibFileName
0x1400248dd  call    cs:__imp_LoadLibraryExW
0x1400248e3  mov     rsi, rax
0x1400248e6  mov     [rsp+4A8h+var_470], rax
0x1400248eb  test    rax, rax
0x1400248ee  jnz     short loc_1400248FC
0x1400248f0  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1400248f5  mov     ebx, eax
0x1400248f7  jmp     loc_140024A00
0x1400248fc  xor     r9d, r9d; wLanguage
0x1400248ff  mov     r8, rdi; lpName
0x140024902  mov     rdx, r14; lpType
0x140024905  mov     rcx, rsi; hModule
0x140024908  call    cs:__imp_FindResourceExW
0x14002490e  mov     rdi, rax
0x140024911  test    rax, rax
0x140024914  jnz     short loc_140024920
0x140024916  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x14002491b  jmp     loc_1400249F4
0x140024920  mov     rdx, rdi; hResInfo
0x140024923  mov     rcx, rsi; hModule
0x140024926  call    cs:__imp_LoadResource
0x14002492c  mov     r14, rax
0x14002492f  mov     [rsp+4A8h+var_468], rax
0x140024934  test    rax, rax
0x140024937  jz      short loc_140024916
0x140024939  mov     rdx, rdi; hResInfo
0x14002493c  mov     rcx, rsi; hModule
0x14002493f  call    cs:__imp_SizeofResource
0x140024945  mov     edi, eax
0x140024947  mov     [rsp+4A8h+var_478], eax
0x14002494b  inc     eax
0x14002494d  cmp     eax, edi
0x14002494f  jnb     short loc_14002495B
0x140024951  mov     ebx, 8007000Eh
0x140024956  jmp     loc_140024A00
0x14002495b  mov     ecx, eax
0x14002495d  mov     edx, 2
0x140024962  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x140024967  cmp     rax, 400h
0x14002496d  jbe     short loc_140024983
0x14002496f  mov     rdx, rax
0x140024972  lea     rcx, [rsp+4A8h+var_438]
0x140024977  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14002497c  mov     rax, [rsp+4A8h+var_438]
0x140024981  jmp     short loc_14002498D
0x140024983  lea     rax, [rsp+4A8h+var_430]
0x140024988  mov     [rsp+4A8h+var_438], rax
0x14002498d  jmp     short loc_1400249A4
0x14002498f  xor     ebx, ebx
0x140024991  mov     rsi, [rsp+4A8h+var_470]
0x140024996  mov     r14, [rsp+4A8h+var_468]
0x14002499b  mov     edi, [rsp+4A8h+var_478]
0x14002499f  mov     rax, [rsp+4A8h+var_438]
0x1400249a4  test    rax, rax
0x1400249a7  jnz     short loc_1400249B0
0x1400249a9  mov     ebx, 8007000Eh
0x1400249ae  jmp     short loc_1400249F6
0x1400249b0  mov     [rsp+4A8h+cchWideChar], edi; cchWideChar
0x1400249b4  mov     [rsp+4A8h+lpWideCharStr], rax; lpWideCharStr
0x1400249b9  mov     r9d, edi; cbMultiByte
0x1400249bc  mov     r8, r14; lpMultiByteStr
0x1400249bf  xor     edx, edx; dwFlags
0x1400249c1  lea     ecx, [rdx+3]; CodePage
0x1400249c4  call    cs:__imp_MultiByteToWideChar
0x1400249ca  test    eax, eax
0x1400249cc  jz      loc_140024916
0x1400249d2  mov     ecx, eax
0x1400249d4  mov     rax, [rsp+4A8h+var_438]
0x1400249d9  mov     [rax+rcx*2], bx
0x1400249dd  mov     r8d, [rsp+4A8h+arg_20]; int
0x1400249e5  mov     rdx, [rsp+4A8h+var_438]; wchar_t *
0x1400249ea  lea     rcx, [rsp+4A8h+var_458]; this
0x1400249ef  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z; ATL::CRegParser::RegisterBuffer(wchar_t *,int)
0x1400249f4  mov     ebx, eax
0x1400249f6  mov     rcx, rsi; hLibModule
0x1400249f9  call    cs:__imp_FreeLibrary
0x1400249ff  nop
0x140024a00  lea     rcx, [rsp+4A8h+var_438]
0x140024a05  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x140024a0a  nop
0x140024a0b  lea     rcx, [rsp+4A8h+var_460]
0x140024a10  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140024a15  mov     eax, ebx
0x140024a17  mov     rcx, [rsp+4A8h+var_28]
0x140024a1f  xor     rcx, rsp; StackCookie
0x140024a22  call    __security_check_cookie
0x140024a27  mov     rbx, [rsp+4A8h+arg_0]
0x140024a2f  add     rsp, 490h
0x140024a36  pop     r14
0x140024a38  pop     rdi
0x140024a39  pop     rsi
0x140024a3a  retn
```
