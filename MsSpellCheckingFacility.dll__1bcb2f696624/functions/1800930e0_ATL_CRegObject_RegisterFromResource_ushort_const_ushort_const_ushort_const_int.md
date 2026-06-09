# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800930e0`
- end: `0x180093288`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180093d34`

## callees

- `0x180061320`
- `0x18006afd4`
- `0x18006b518`
- `0x18008f830`
- `0x180090c90`
- `0x180091824`
- `0x180092f6c`
- `0x1800930e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180093173`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180093173`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009312a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009312a`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180093155`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180093155`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180093246`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180093246`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18009318c`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18009318c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180093211`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180093211`

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
0x1800930e0  mov     [rsp+arg_0], rbx
0x1800930e5  push    rsi
0x1800930e6  push    rdi
0x1800930e7  push    r14
0x1800930e9  sub     rsp, 480h
0x1800930f0  mov     rax, cs:__security_cookie
0x1800930f7  xor     rax, rsp
0x1800930fa  mov     [rsp+498h+var_28], rax
0x180093102  mov     r14, r9
0x180093105  mov     rdi, r8
0x180093108  mov     rax, rdx
0x18009310b  xor     ebx, ebx
0x18009310d  mov     [rsp+498h+var_450], rbx
0x180093112  mov     [rsp+498h+var_440], rcx
0x180093117  mov     [rsp+498h+var_448], rbx
0x18009311c  mov     [rsp+498h+var_438], rbx
0x180093121  xor     edx, edx; hFile
0x180093123  lea     r8d, [rbx+2]; dwFlags
0x180093127  mov     rcx, rax; lpLibFileName
0x18009312a  call    cs:__imp_LoadLibraryExW
0x180093130  mov     rsi, rax
0x180093133  mov     [rsp+498h+var_460], rax
0x180093138  test    rax, rax
0x18009313b  jnz     short loc_180093149
0x18009313d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180093142  mov     ebx, eax
0x180093144  jmp     loc_18009324D
0x180093149  xor     r9d, r9d; wLanguage
0x18009314c  mov     r8, rdi; lpName
0x18009314f  mov     rdx, r14; lpType
0x180093152  mov     rcx, rsi; hModule
0x180093155  call    cs:__imp_FindResourceExW
0x18009315b  mov     rdi, rax
0x18009315e  test    rax, rax
0x180093161  jnz     short loc_18009316D
0x180093163  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180093168  jmp     loc_180093241
0x18009316d  mov     rdx, rdi; hResInfo
0x180093170  mov     rcx, rsi; hModule
0x180093173  call    cs:__imp_LoadResource
0x180093179  mov     r14, rax
0x18009317c  mov     [rsp+498h+var_458], rax
0x180093181  test    rax, rax
0x180093184  jz      short loc_180093163
0x180093186  mov     rdx, rdi; hResInfo
0x180093189  mov     rcx, rsi; hModule
0x18009318c  call    cs:__imp_SizeofResource
0x180093192  mov     edi, eax
0x180093194  mov     [rsp+498h+var_468], eax
0x180093198  inc     eax
0x18009319a  cmp     eax, edi
0x18009319c  jnb     short loc_1800931A8
0x18009319e  mov     ebx, 8007000Eh
0x1800931a3  jmp     loc_18009324D
0x1800931a8  mov     ecx, eax
0x1800931aa  mov     edx, 2
0x1800931af  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800931b4  cmp     rax, 400h
0x1800931ba  jbe     short loc_1800931D0
0x1800931bc  mov     rdx, rax
0x1800931bf  lea     rcx, [rsp+498h+var_438]
0x1800931c4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800931c9  mov     rax, [rsp+498h+var_438]
0x1800931ce  jmp     short loc_1800931DA
0x1800931d0  lea     rax, [rsp+498h+var_430]
0x1800931d5  mov     [rsp+498h+var_438], rax
0x1800931da  jmp     short loc_1800931F1
0x1800931dc  xor     ebx, ebx
0x1800931de  mov     rsi, [rsp+498h+var_460]
0x1800931e3  mov     r14, [rsp+498h+var_458]
0x1800931e8  mov     edi, [rsp+498h+var_468]
0x1800931ec  mov     rax, [rsp+498h+var_438]
0x1800931f1  test    rax, rax
0x1800931f4  jnz     short loc_1800931FD
0x1800931f6  mov     ebx, 8007000Eh
0x1800931fb  jmp     short loc_180093243
0x1800931fd  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180093201  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180093206  mov     r9d, edi; cbMultiByte
0x180093209  mov     r8, r14; lpMultiByteStr
0x18009320c  xor     edx, edx; dwFlags
0x18009320e  lea     ecx, [rdx+3]; CodePage
0x180093211  call    cs:__imp_MultiByteToWideChar
0x180093217  test    eax, eax
0x180093219  jz      loc_180093163
0x18009321f  mov     ecx, eax
0x180093221  mov     rax, [rsp+498h+var_438]
0x180093226  mov     [rax+rcx*2], bx
0x18009322a  mov     r8d, [rsp+498h+arg_20]; int
0x180093232  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180093237  lea     rcx, [rsp+498h+var_448]; this
0x18009323c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180093241  mov     ebx, eax
0x180093243  mov     rcx, rsi; hLibModule
0x180093246  call    cs:__imp_FreeLibrary
0x18009324c  nop
0x18009324d  lea     rcx, [rsp+498h+var_438]
0x180093252  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180093257  nop
0x180093258  lea     rcx, [rsp+498h+var_450]
0x18009325d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180093262  mov     eax, ebx
0x180093264  mov     rcx, [rsp+498h+var_28]
0x18009326c  xor     rcx, rsp; StackCookie
0x18009326f  call    __security_check_cookie
0x180093274  mov     rbx, [rsp+498h+arg_0]
0x18009327c  add     rsp, 480h
0x180093283  pop     r14
0x180093285  pop     rdi
0x180093286  pop     rsi
0x180093287  retn
```
