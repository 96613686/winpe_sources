# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180004710`
- end: `0x1800048cf`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `447`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800091d4`

## callees

- `0x180004710`
- `0x1800059a4`
- `0x1800059dc`
- `0x1800065fc`
- `0x180006720`
- `0x180006740`
- `0x180006750`
- `0x180008e9c`
- `0x18000b630`

## import_xrefs

- `KERNEL32!SizeofResource` at `0x1800047bc`
- `KERNEL32!SizeofResource` at `0x1800047bc`
- `KERNEL32!MultiByteToWideChar` at `0x180004856`
- `KERNEL32!MultiByteToWideChar` at `0x180004856`
- `KERNEL32!FindResourceExW` at `0x180004785`
- `KERNEL32!FindResourceExW` at `0x180004785`
- `KERNEL32!LoadResource` at `0x1800047a3`
- `KERNEL32!LoadResource` at `0x1800047a3`
- `KERNEL32!FreeLibrary` at `0x18000488b`
- `KERNEL32!FreeLibrary` at `0x18000488b`
- `KERNEL32!LoadLibraryExW` at `0x18000475a`
- `KERNEL32!LoadLibraryExW` at `0x18000475a`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        const WCHAR *this,
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
  size_t v16; // rax
  WCHAR *lpWideCharStr; // rax
  int v18; // eax
  _QWORD *v19; // [rsp+38h] [rbp-460h] BYREF
  HMODULE v20; // [rsp+40h] [rbp-458h]
  const CHAR *v21; // [rsp+48h] [rbp-450h]
  LPCWSTR v22[2]; // [rsp+50h] [rbp-448h] BYREF
  LPWSTR v23; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v24[1032]; // [rsp+68h] [rbp-430h] BYREF

  v19 = 0;
  v22[1] = this;
  v22[0] = 0;
  v23 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  v20 = Library;
  if ( Library )
  {
    Resource = FindResourceExW(Library, a4, a3, 0);
    v11 = Resource;
    if ( !Resource )
      goto LABEL_4;
    v13 = (const CHAR *)LoadResource(v8, Resource);
    v21 = v13;
    if ( !v13 )
      goto LABEL_4;
    cchWideChar = SizeofResource(v8, v11);
    if ( cchWideChar + 1 < cchWideChar )
    {
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v23);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      return 2147942414LL;
    }
    try
    {
      v16 = ATL::AtlMultiplyThrow<unsigned __int64>();
      if ( v16 <= 0x400 )
      {
        lpWideCharStr = (WCHAR *)v24;
        v23 = (LPWSTR)v24;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v23, v16);
        lpWideCharStr = v23;
      }
    }
    catch ( ... )
    {
      v8 = v20;
      v13 = v21;
      lpWideCharStr = v23;
    }
    if ( !lpWideCharStr )
    {
      v9 = -2147024882;
LABEL_16:
      FreeLibrary(v8);
      goto LABEL_17;
    }
    v18 = MultiByteToWideChar(3u, 0, v13, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v18 )
    {
      v23[v18] = 0;
      Error = ATL::CRegParser::RegisterBuffer(v22, v23, a5);
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
  if ( v23 != (LPWSTR)v24 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v23);
  return v9;
}

```

## disassembly

```asm
0x180004710  mov     [rsp+arg_0], rbx
0x180004715  push    rsi
0x180004716  push    rdi
0x180004717  push    r14
0x180004719  sub     rsp, 480h
0x180004720  mov     rax, cs:__security_cookie
0x180004727  xor     rax, rsp
0x18000472a  mov     [rsp+498h+var_28], rax
0x180004732  mov     r14, r9
0x180004735  mov     rdi, r8
0x180004738  mov     rax, rdx
0x18000473b  xor     ebx, ebx
0x18000473d  mov     [rsp+498h+var_460], rbx
0x180004742  mov     [rsp+498h+var_440], rcx
0x180004747  mov     [rsp+498h+var_448], rbx
0x18000474c  mov     [rsp+498h+var_438], rbx
0x180004751  xor     edx, edx; hFile
0x180004753  lea     r8d, [rbx+2]; dwFlags
0x180004757  mov     rcx, rax; lpLibFileName
0x18000475a  call    cs:__imp_LoadLibraryExW
0x180004760  mov     rsi, rax
0x180004763  mov     [rsp+498h+var_458], rax
0x180004768  test    rax, rax
0x18000476b  jnz     short loc_180004779
0x18000476d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004772  mov     ebx, eax
0x180004774  jmp     loc_180004892
0x180004779  xor     r9d, r9d; wLanguage
0x18000477c  mov     r8, rdi; lpName
0x18000477f  mov     rdx, r14; lpType
0x180004782  mov     rcx, rsi; hModule
0x180004785  call    cs:__imp_FindResourceExW
0x18000478b  mov     rdi, rax
0x18000478e  test    rax, rax
0x180004791  jnz     short loc_18000479D
0x180004793  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004798  jmp     loc_180004886
0x18000479d  mov     rdx, rdi; hResInfo
0x1800047a0  mov     rcx, rsi; hModule
0x1800047a3  call    cs:__imp_LoadResource
0x1800047a9  mov     r14, rax
0x1800047ac  mov     [rsp+498h+var_450], rax
0x1800047b1  test    rax, rax
0x1800047b4  jz      short loc_180004793
0x1800047b6  mov     rdx, rdi; hResInfo
0x1800047b9  mov     rcx, rsi; hModule
0x1800047bc  call    cs:__imp_SizeofResource
0x1800047c2  mov     edi, eax
0x1800047c4  mov     [rsp+498h+var_468], eax
0x1800047c8  inc     eax
0x1800047ca  cmp     eax, edi
0x1800047cc  jnb     short loc_1800047ED
0x1800047ce  lea     rcx, [rsp+498h+var_438]
0x1800047d3  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800047d8  nop
0x1800047d9  lea     rcx, [rsp+498h+var_460]
0x1800047de  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800047e3  mov     eax, 8007000Eh
0x1800047e8  jmp     loc_1800048AB
0x1800047ed  mov     ecx, eax
0x1800047ef  mov     edx, 2
0x1800047f4  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800047f9  cmp     rax, 400h
0x1800047ff  jbe     short loc_180004815
0x180004801  mov     rdx, rax
0x180004804  lea     rcx, [rsp+498h+var_438]
0x180004809  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000480e  mov     rax, [rsp+498h+var_438]
0x180004813  jmp     short loc_18000481F
0x180004815  lea     rax, [rsp+498h+var_430]
0x18000481a  mov     [rsp+498h+var_438], rax
0x18000481f  jmp     short loc_180004836
0x180004821  xor     ebx, ebx
0x180004823  mov     rsi, [rsp+498h+var_458]
0x180004828  mov     r14, [rsp+498h+var_450]
0x18000482d  mov     edi, [rsp+498h+var_468]
0x180004831  mov     rax, [rsp+498h+var_438]
0x180004836  test    rax, rax
0x180004839  jnz     short loc_180004842
0x18000483b  mov     ebx, 8007000Eh
0x180004840  jmp     short loc_180004888
0x180004842  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180004846  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18000484b  mov     r9d, edi; cbMultiByte
0x18000484e  mov     r8, r14; lpMultiByteStr
0x180004851  xor     edx, edx; dwFlags
0x180004853  lea     ecx, [rdx+3]; CodePage
0x180004856  call    cs:__imp_MultiByteToWideChar
0x18000485c  test    eax, eax
0x18000485e  jz      loc_180004793
0x180004864  mov     ecx, eax
0x180004866  mov     rax, [rsp+498h+var_438]
0x18000486b  mov     [rax+rcx*2], bx
0x18000486f  mov     r8d, [rsp+498h+arg_20]; int
0x180004877  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x18000487c  lea     rcx, [rsp+498h+var_448]; this
0x180004881  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180004886  mov     ebx, eax
0x180004888  mov     rcx, rsi; hLibModule
0x18000488b  call    cs:__imp_FreeLibrary
0x180004891  nop
0x180004892  lea     rax, [rsp+498h+var_430]
0x180004897  cmp     [rsp+498h+var_438], rax
0x18000489c  jz      short loc_1800048A9
0x18000489e  lea     rcx, [rsp+498h+var_438]
0x1800048a3  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800048a8  nop
0x1800048a9  mov     eax, ebx
0x1800048ab  mov     rcx, [rsp+498h+var_28]
0x1800048b3  xor     rcx, rsp; StackCookie
0x1800048b6  call    __security_check_cookie
0x1800048bb  mov     rbx, [rsp+498h+arg_0]
0x1800048c3  add     rsp, 480h
0x1800048ca  pop     r14
0x1800048cc  pop     rdi
0x1800048cd  pop     rsi
0x1800048ce  retn
```
