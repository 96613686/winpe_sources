# ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)

- ea: `0x18000ce70`
- end: `0x18000d018`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000db7c`
- `0x18000ddf4`

## callees

- `0x180002300`
- `0x18000aa18`
- `0x18000ac10`
- `0x18000ad38`
- `0x18000b780`
- `0x18000b9f0`
- `0x18000ccfc`
- `0x18000ce70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000cfd6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000cfd6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ceba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ceba`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000cf1c`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000cf1c`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000cee5`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000cee5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000cf03`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000cf03`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000cfa1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000cfa1`

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
0x18000ce70  mov     [rsp+arg_0], rbx
0x18000ce75  push    rsi
0x18000ce76  push    rdi
0x18000ce77  push    r14
0x18000ce79  sub     rsp, 480h
0x18000ce80  mov     rax, cs:__security_cookie
0x18000ce87  xor     rax, rsp
0x18000ce8a  mov     [rsp+498h+var_28], rax
0x18000ce92  mov     r14, r9
0x18000ce95  mov     rdi, r8
0x18000ce98  mov     rax, rdx
0x18000ce9b  xor     ebx, ebx
0x18000ce9d  mov     [rsp+498h+var_450], rbx
0x18000cea2  mov     [rsp+498h+var_440], rcx
0x18000cea7  mov     [rsp+498h+var_448], rbx
0x18000ceac  mov     [rsp+498h+var_438], rbx
0x18000ceb1  xor     edx, edx; hFile
0x18000ceb3  lea     r8d, [rbx+2]; dwFlags
0x18000ceb7  mov     rcx, rax; lpLibFileName
0x18000ceba  call    cs:__imp_LoadLibraryExW
0x18000cec0  mov     rsi, rax
0x18000cec3  mov     [rsp+498h+var_460], rax
0x18000cec8  test    rax, rax
0x18000cecb  jnz     short loc_18000CED9
0x18000cecd  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18000ced2  mov     ebx, eax
0x18000ced4  jmp     loc_18000CFDD
0x18000ced9  xor     r9d, r9d; wLanguage
0x18000cedc  mov     r8, rdi; lpName
0x18000cedf  mov     rdx, r14; lpType
0x18000cee2  mov     rcx, rsi; hModule
0x18000cee5  call    cs:__imp_FindResourceExW
0x18000ceeb  mov     rdi, rax
0x18000ceee  test    rax, rax
0x18000cef1  jnz     short loc_18000CEFD
0x18000cef3  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18000cef8  jmp     loc_18000CFD1
0x18000cefd  mov     rdx, rdi; hResInfo
0x18000cf00  mov     rcx, rsi; hModule
0x18000cf03  call    cs:__imp_LoadResource
0x18000cf09  mov     r14, rax
0x18000cf0c  mov     [rsp+498h+var_458], rax
0x18000cf11  test    rax, rax
0x18000cf14  jz      short loc_18000CEF3
0x18000cf16  mov     rdx, rdi; hResInfo
0x18000cf19  mov     rcx, rsi; hModule
0x18000cf1c  call    cs:__imp_SizeofResource
0x18000cf22  mov     edi, eax
0x18000cf24  mov     [rsp+498h+var_468], eax
0x18000cf28  inc     eax
0x18000cf2a  cmp     eax, edi
0x18000cf2c  jnb     short loc_18000CF38
0x18000cf2e  mov     ebx, 8007000Eh
0x18000cf33  jmp     loc_18000CFDD
0x18000cf38  mov     ecx, eax
0x18000cf3a  mov     edx, 2
0x18000cf3f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000cf44  cmp     rax, 400h
0x18000cf4a  jbe     short loc_18000CF60
0x18000cf4c  mov     rdx, rax
0x18000cf4f  lea     rcx, [rsp+498h+var_438]
0x18000cf54  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000cf59  mov     rax, [rsp+498h+var_438]
0x18000cf5e  jmp     short loc_18000CF6A
0x18000cf60  lea     rax, [rsp+498h+var_430]
0x18000cf65  mov     [rsp+498h+var_438], rax
0x18000cf6a  jmp     short loc_18000CF81
0x18000cf6c  xor     ebx, ebx
0x18000cf6e  mov     rsi, [rsp+498h+var_460]
0x18000cf73  mov     r14, [rsp+498h+var_458]
0x18000cf78  mov     edi, [rsp+498h+var_468]
0x18000cf7c  mov     rax, [rsp+498h+var_438]
0x18000cf81  test    rax, rax
0x18000cf84  jnz     short loc_18000CF8D
0x18000cf86  mov     ebx, 8007000Eh
0x18000cf8b  jmp     short loc_18000CFD3
0x18000cf8d  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18000cf91  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18000cf96  mov     r9d, edi; cbMultiByte
0x18000cf99  mov     r8, r14; lpMultiByteStr
0x18000cf9c  xor     edx, edx; dwFlags
0x18000cf9e  lea     ecx, [rdx+3]; CodePage
0x18000cfa1  call    cs:__imp_MultiByteToWideChar
0x18000cfa7  test    eax, eax
0x18000cfa9  jz      loc_18000CEF3
0x18000cfaf  mov     ecx, eax
0x18000cfb1  mov     rax, [rsp+498h+var_438]
0x18000cfb6  mov     [rax+rcx*2], bx
0x18000cfba  mov     r8d, [rsp+498h+arg_20]; int
0x18000cfc2  mov     rdx, [rsp+498h+var_438]; wchar_t *
0x18000cfc7  lea     rcx, [rsp+498h+var_448]; this
0x18000cfcc  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z; ATL::CRegParser::RegisterBuffer(wchar_t *,int)
0x18000cfd1  mov     ebx, eax
0x18000cfd3  mov     rcx, rsi; hLibModule
0x18000cfd6  call    cs:__imp_FreeLibrary
0x18000cfdc  nop
0x18000cfdd  lea     rcx, [rsp+498h+var_438]
0x18000cfe2  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18000cfe7  nop
0x18000cfe8  lea     rcx, [rsp+498h+var_450]
0x18000cfed  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000cff2  mov     eax, ebx
0x18000cff4  mov     rcx, [rsp+498h+var_28]
0x18000cffc  xor     rcx, rsp; StackCookie
0x18000cfff  call    __security_check_cookie
0x18000d004  mov     rbx, [rsp+498h+arg_0]
0x18000d00c  add     rsp, 480h
0x18000d013  pop     r14
0x18000d015  pop     rdi
0x18000d016  pop     rsi
0x18000d017  retn
```
