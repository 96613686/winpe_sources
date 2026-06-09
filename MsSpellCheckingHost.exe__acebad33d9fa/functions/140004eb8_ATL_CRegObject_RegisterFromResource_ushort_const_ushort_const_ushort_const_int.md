# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x140004eb8`
- end: `0x140005092`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `474`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140005f04`

## callees

- `0x1400031c8`
- `0x1400032f8`
- `0x140003b88`
- `0x140003d60`
- `0x140004d28`
- `0x140004eb8`
- `0x140011e10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x140004f49`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x140004f49`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140005042`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140005042`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140004eff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140004eff`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x140004f62`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x140004f62`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x140004f2b`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x140004f2b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14000500d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14000500d`

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
  HMODULE v7; // rdi
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v10; // rsi
  unsigned int v11; // eax
  const CHAR *v12; // r14
  DWORD cchWideChar; // esi
  DWORD v14; // eax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  HMODULE v18; // [rsp+38h] [rbp-460h]
  LPCWSTR v19[3]; // [rsp+48h] [rbp-450h] BYREF
  LPWSTR v20; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v21[1032]; // [rsp+68h] [rbp-430h] BYREF

  v19[2] = 0;
  v19[1] = this;
  v19[0] = 0;
  v20 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v7 = Library;
  v18 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_21:
    if ( v20 != (LPWSTR)v21 )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v20);
    return Error;
  }
  Resource = FindResourceExW(Library, a4, (LPCWSTR)0x65, 0);
  v10 = Resource;
  if ( !Resource )
    goto LABEL_4;
  v12 = (const CHAR *)LoadResource(v7, Resource);
  if ( !v12 )
    goto LABEL_4;
  cchWideChar = SizeofResource(v7, v10);
  v14 = cchWideChar + 1;
  if ( cchWideChar + 1 >= cchWideChar )
  {
    try
    {
      if ( cchWideChar == -1 )
        goto LABEL_14;
      if ( 0xFFFFFFFFFFFFFFFFuLL / v14 < 2 )
        ATL::AtlThrowImpl(-2147024809);
      if ( 2 * (unsigned __int64)v14 <= 0x400 )
      {
LABEL_14:
        lpWideCharStr = (WCHAR *)v21;
        v20 = (LPWSTR)v21;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v20, 2LL * v14);
        lpWideCharStr = v20;
      }
    }
    catch ( ... )
    {
      v7 = v18;
      lpWideCharStr = v20;
    }
    if ( !lpWideCharStr )
    {
      Error = -2147024882;
LABEL_20:
      FreeLibrary(v7);
      goto LABEL_21;
    }
    v17 = MultiByteToWideChar(3u, 0, v12, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v17 )
    {
      v20[v17] = 0;
      v11 = ATL::CRegParser::RegisterBuffer(v19, v20, a5);
      goto LABEL_19;
    }
LABEL_4:
    v11 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v11;
    goto LABEL_20;
  }
  if ( v20 != (LPWSTR)v21 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x140004eb8  mov     [rsp+arg_0], rbx
0x140004ebd  push    rsi
0x140004ebe  push    rdi
0x140004ebf  push    r14
0x140004ec1  sub     rsp, 480h
0x140004ec8  mov     rax, cs:__security_cookie
0x140004ecf  xor     rax, rsp
0x140004ed2  mov     [rsp+498h+var_28], rax
0x140004eda  mov     rsi, r9
0x140004edd  mov     rax, rdx
0x140004ee0  xor     ebx, ebx
0x140004ee2  mov     [rsp+498h+var_440], rbx
0x140004ee7  mov     [rsp+498h+var_448], rcx
0x140004eec  mov     [rsp+498h+var_450], rbx
0x140004ef1  mov     [rsp+498h+var_438], rbx
0x140004ef6  xor     edx, edx; hFile
0x140004ef8  lea     r8d, [rbx+2]; dwFlags
0x140004efc  mov     rcx, rax; lpLibFileName
0x140004eff  call    cs:__imp_LoadLibraryExW
0x140004f05  mov     rdi, rax
0x140004f08  mov     [rsp+498h+var_460], rax
0x140004f0d  test    rax, rax
0x140004f10  jnz     short loc_140004F1E
0x140004f12  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140004f17  mov     ebx, eax
0x140004f19  jmp     loc_140005049
0x140004f1e  xor     r9d, r9d; wLanguage
0x140004f21  lea     r8d, [r9+65h]; lpName
0x140004f25  mov     rdx, rsi; lpType
0x140004f28  mov     rcx, rdi; hModule
0x140004f2b  call    cs:__imp_FindResourceExW
0x140004f31  mov     rsi, rax
0x140004f34  test    rax, rax
0x140004f37  jnz     short loc_140004F43
0x140004f39  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140004f3e  jmp     loc_14000503D
0x140004f43  mov     rdx, rsi; hResInfo
0x140004f46  mov     rcx, rdi; hModule
0x140004f49  call    cs:__imp_LoadResource
0x140004f4f  mov     r14, rax
0x140004f52  mov     [rsp+498h+var_458], rax
0x140004f57  test    rax, rax
0x140004f5a  jz      short loc_140004F39
0x140004f5c  mov     rdx, rsi; hResInfo
0x140004f5f  mov     rcx, rdi; hModule
0x140004f62  call    cs:__imp_SizeofResource
0x140004f68  mov     esi, eax
0x140004f6a  mov     [rsp+498h+var_468], eax
0x140004f6e  inc     eax
0x140004f70  cmp     eax, esi
0x140004f72  jnb     short loc_140004F95
0x140004f74  lea     rax, [rsp+498h+var_430]
0x140004f79  cmp     [rsp+498h+var_438], rax
0x140004f7e  jz      short loc_140004F8B
0x140004f80  lea     rcx, [rsp+498h+var_438]
0x140004f85  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140004f8a  nop
0x140004f8b  mov     eax, 8007000Eh
0x140004f90  jmp     loc_140005062
0x140004f95  test    eax, eax
0x140004f97  jz      short loc_140004FCC
0x140004f99  mov     ecx, eax
0x140004f9b  xor     edx, edx
0x140004f9d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004fa1  div     rcx
0x140004fa4  cmp     rax, 2
0x140004fa8  jb      loc_140005086
0x140004fae  lea     rdx, [rcx+rcx]
0x140004fb2  cmp     rdx, 400h
0x140004fb9  jbe     short loc_140004FCC
0x140004fbb  lea     rcx, [rsp+498h+var_438]
0x140004fc0  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140004fc5  mov     rax, [rsp+498h+var_438]
0x140004fca  jmp     short loc_140004FD6
0x140004fcc  lea     rax, [rsp+498h+var_430]
0x140004fd1  mov     [rsp+498h+var_438], rax
0x140004fd6  jmp     short loc_140004FED
0x140004fd8  xor     ebx, ebx
0x140004fda  mov     rdi, [rsp+498h+var_460]
0x140004fdf  mov     r14, [rsp+498h+var_458]
0x140004fe4  mov     esi, [rsp+498h+var_468]
0x140004fe8  mov     rax, [rsp+498h+var_438]
0x140004fed  test    rax, rax
0x140004ff0  jnz     short loc_140004FF9
0x140004ff2  mov     ebx, 8007000Eh
0x140004ff7  jmp     short loc_14000503F
0x140004ff9  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x140004ffd  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x140005002  mov     r9d, esi; cbMultiByte
0x140005005  mov     r8, r14; lpMultiByteStr
0x140005008  xor     edx, edx; dwFlags
0x14000500a  lea     ecx, [rdx+3]; CodePage
0x14000500d  call    cs:__imp_MultiByteToWideChar
0x140005013  test    eax, eax
0x140005015  jz      loc_140004F39
0x14000501b  mov     ecx, eax
0x14000501d  mov     rax, [rsp+498h+var_438]
0x140005022  mov     [rax+rcx*2], bx
0x140005026  mov     r8d, [rsp+498h+arg_20]; int
0x14000502e  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x140005033  lea     rcx, [rsp+498h+var_450]; this
0x140005038  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x14000503d  mov     ebx, eax
0x14000503f  mov     rcx, rdi; hLibModule
0x140005042  call    cs:__imp_FreeLibrary
0x140005048  nop
0x140005049  lea     rax, [rsp+498h+var_430]
0x14000504e  cmp     [rsp+498h+var_438], rax
0x140005053  jz      short loc_140005060
0x140005055  lea     rcx, [rsp+498h+var_438]
0x14000505a  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x14000505f  nop
0x140005060  mov     eax, ebx
0x140005062  mov     rcx, [rsp+498h+var_28]
0x14000506a  xor     rcx, rsp; StackCookie
0x14000506d  call    __security_check_cookie
0x140005072  mov     rbx, [rsp+498h+arg_0]
0x14000507a  add     rsp, 480h
0x140005081  pop     r14
0x140005083  pop     rdi
0x140005084  pop     rsi
0x140005085  retn
0x140005086  mov     ecx, 80070057h; int
0x14000508b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
