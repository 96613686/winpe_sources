# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180015c5c`
- end: `0x180015e38`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `476`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180017500`
- `0x18001779c`

## callees

- `0x180001800`
- `0x180003858`
- `0x180005e44`
- `0x18001301c`
- `0x1800144ac`
- `0x180015acc`
- `0x180015c5c`

## import_xrefs

- `KERNEL32!SizeofResource` at `0x180015d08`
- `KERNEL32!SizeofResource` at `0x180015d08`
- `KERNEL32!LoadResource` at `0x180015cef`
- `KERNEL32!LoadResource` at `0x180015cef`
- `KERNEL32!FindResourceExW` at `0x180015cd1`
- `KERNEL32!FindResourceExW` at `0x180015cd1`
- `KERNEL32!MultiByteToWideChar` at `0x180015db3`
- `KERNEL32!MultiByteToWideChar` at `0x180015db3`
- `KERNEL32!FreeLibrary` at `0x180015de8`
- `KERNEL32!FreeLibrary` at `0x180015de8`
- `KERNEL32!LoadLibraryExW` at `0x180015ca6`
- `KERNEL32!LoadLibraryExW` at `0x180015ca6`

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
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rdi
  signed int v12; // eax
  const CHAR *v13; // r14
  DWORD cchWideChar; // edi
  DWORD v15; // eax
  WCHAR *lpWideCharStr; // rax
  int v18; // eax
  HMODULE v19; // [rsp+38h] [rbp-460h]
  _QWORD v20[3]; // [rsp+48h] [rbp-450h] BYREF
  LPWSTR v21; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v22[1032]; // [rsp+68h] [rbp-430h] BYREF

  v20[2] = 0;
  v20[1] = this;
  v20[0] = 0;
  v21 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  v19 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_21:
    if ( v21 != (LPWSTR)v22 )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v21);
    return Error;
  }
  Resource = FindResourceExW(Library, a4, a3, 0);
  v11 = Resource;
  if ( !Resource )
    goto LABEL_4;
  v13 = (const CHAR *)LoadResource(v8, Resource);
  if ( !v13 )
    goto LABEL_4;
  cchWideChar = SizeofResource(v8, v11);
  v15 = cchWideChar + 1;
  if ( cchWideChar + 1 >= cchWideChar )
  {
    try
    {
      if ( cchWideChar == -1 )
        goto LABEL_14;
      if ( 0xFFFFFFFFFFFFFFFFuLL / v15 < 2 )
        ATL::AtlThrowImpl(-2147024809);
      if ( 2 * (unsigned __int64)v15 <= 0x400 )
      {
LABEL_14:
        lpWideCharStr = (WCHAR *)v22;
        v21 = (LPWSTR)v22;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v21, 2LL * v15);
        lpWideCharStr = v21;
      }
    }
    catch ( ... )
    {
      v8 = v19;
      lpWideCharStr = v21;
    }
    if ( !lpWideCharStr )
    {
      Error = -2147024882;
LABEL_20:
      FreeLibrary(v8);
      goto LABEL_21;
    }
    v18 = MultiByteToWideChar(3u, 0, v13, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v18 )
    {
      v21[v18] = 0;
      v12 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v20, v21, a5);
      goto LABEL_19;
    }
LABEL_4:
    v12 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v12;
    goto LABEL_20;
  }
  if ( v21 != (LPWSTR)v22 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v21);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180015c5c  mov     [rsp+arg_0], rbx
0x180015c61  push    rsi
0x180015c62  push    rdi
0x180015c63  push    r14
0x180015c65  sub     rsp, 480h
0x180015c6c  mov     rax, cs:__security_cookie
0x180015c73  xor     rax, rsp
0x180015c76  mov     [rsp+498h+var_28], rax
0x180015c7e  mov     r14, r9
0x180015c81  mov     rdi, r8
0x180015c84  mov     rax, rdx
0x180015c87  xor     ebx, ebx
0x180015c89  mov     [rsp+498h+var_440], rbx
0x180015c8e  mov     [rsp+498h+var_448], rcx
0x180015c93  mov     [rsp+498h+var_450], rbx
0x180015c98  mov     [rsp+498h+var_438], rbx
0x180015c9d  xor     edx, edx; hFile
0x180015c9f  lea     r8d, [rbx+2]; dwFlags
0x180015ca3  mov     rcx, rax; lpLibFileName
0x180015ca6  call    cs:__imp_LoadLibraryExW
0x180015cac  mov     rsi, rax
0x180015caf  mov     [rsp+498h+var_460], rax
0x180015cb4  test    rax, rax
0x180015cb7  jnz     short loc_180015CC5
0x180015cb9  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180015cbe  mov     ebx, eax
0x180015cc0  jmp     loc_180015DEF
0x180015cc5  xor     r9d, r9d; wLanguage
0x180015cc8  mov     r8, rdi; lpName
0x180015ccb  mov     rdx, r14; lpType
0x180015cce  mov     rcx, rsi; hModule
0x180015cd1  call    cs:__imp_FindResourceExW
0x180015cd7  mov     rdi, rax
0x180015cda  test    rax, rax
0x180015cdd  jnz     short loc_180015CE9
0x180015cdf  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180015ce4  jmp     loc_180015DE3
0x180015ce9  mov     rdx, rdi; hResInfo
0x180015cec  mov     rcx, rsi; hModule
0x180015cef  call    cs:__imp_LoadResource
0x180015cf5  mov     r14, rax
0x180015cf8  mov     [rsp+498h+var_458], rax
0x180015cfd  test    rax, rax
0x180015d00  jz      short loc_180015CDF
0x180015d02  mov     rdx, rdi; hResInfo
0x180015d05  mov     rcx, rsi; hModule
0x180015d08  call    cs:__imp_SizeofResource
0x180015d0e  mov     edi, eax
0x180015d10  mov     [rsp+498h+var_468], eax
0x180015d14  inc     eax
0x180015d16  cmp     eax, edi
0x180015d18  jnb     short loc_180015D3B
0x180015d1a  lea     rax, [rsp+498h+var_430]
0x180015d1f  cmp     [rsp+498h+var_438], rax
0x180015d24  jz      short loc_180015D31
0x180015d26  lea     rcx, [rsp+498h+var_438]
0x180015d2b  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180015d30  nop
0x180015d31  mov     eax, 8007000Eh
0x180015d36  jmp     loc_180015E08
0x180015d3b  test    eax, eax
0x180015d3d  jz      short loc_180015D72
0x180015d3f  mov     ecx, eax
0x180015d41  xor     edx, edx
0x180015d43  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015d47  div     rcx
0x180015d4a  cmp     rax, 2
0x180015d4e  jb      loc_180015E2C
0x180015d54  lea     rdx, [rcx+rcx]
0x180015d58  cmp     rdx, 400h
0x180015d5f  jbe     short loc_180015D72
0x180015d61  lea     rcx, [rsp+498h+var_438]
0x180015d66  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180015d6b  mov     rax, [rsp+498h+var_438]
0x180015d70  jmp     short loc_180015D7C
0x180015d72  lea     rax, [rsp+498h+var_430]
0x180015d77  mov     [rsp+498h+var_438], rax
0x180015d7c  jmp     short loc_180015D93
0x180015d7e  xor     ebx, ebx
0x180015d80  mov     rsi, [rsp+498h+var_460]
0x180015d85  mov     r14, [rsp+498h+var_458]
0x180015d8a  mov     edi, [rsp+498h+var_468]
0x180015d8e  mov     rax, [rsp+498h+var_438]
0x180015d93  test    rax, rax
0x180015d96  jnz     short loc_180015D9F
0x180015d98  mov     ebx, 8007000Eh
0x180015d9d  jmp     short loc_180015DE5
0x180015d9f  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180015da3  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180015da8  mov     r9d, edi; cbMultiByte
0x180015dab  mov     r8, r14; lpMultiByteStr
0x180015dae  xor     edx, edx; dwFlags
0x180015db0  lea     ecx, [rdx+3]; CodePage
0x180015db3  call    cs:__imp_MultiByteToWideChar
0x180015db9  test    eax, eax
0x180015dbb  jz      loc_180015CDF
0x180015dc1  mov     ecx, eax
0x180015dc3  mov     rax, [rsp+498h+var_438]
0x180015dc8  mov     [rax+rcx*2], bx
0x180015dcc  mov     r8d, [rsp+498h+arg_20]; int
0x180015dd4  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180015dd9  lea     rcx, [rsp+498h+var_450]; this
0x180015dde  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180015de3  mov     ebx, eax
0x180015de5  mov     rcx, rsi; hLibModule
0x180015de8  call    cs:__imp_FreeLibrary
0x180015dee  nop
0x180015def  lea     rax, [rsp+498h+var_430]
0x180015df4  cmp     [rsp+498h+var_438], rax
0x180015df9  jz      short loc_180015E06
0x180015dfb  lea     rcx, [rsp+498h+var_438]
0x180015e00  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180015e05  nop
0x180015e06  mov     eax, ebx
0x180015e08  mov     rcx, [rsp+498h+var_28]
0x180015e10  xor     rcx, rsp; StackCookie
0x180015e13  call    __security_check_cookie
0x180015e18  mov     rbx, [rsp+498h+arg_0]
0x180015e20  add     rsp, 480h
0x180015e27  pop     r14
0x180015e29  pop     rdi
0x180015e2a  pop     rsi
0x180015e2b  retn
0x180015e2c  mov     ecx, 80070057h; int
0x180015e31  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
