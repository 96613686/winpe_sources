# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180009ae4`
- end: `0x180009cbe`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `474`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000b684`

## callees

- `0x180004410`
- `0x1800073cc`
- `0x1800074fc`
- `0x180007538`
- `0x180007dec`
- `0x180009954`
- `0x180009ae4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180009b8e`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180009b8e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180009c6e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180009c6e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009b2b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009b2b`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180009b57`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180009b57`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180009b75`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180009b75`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180009c39`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180009c39`

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
  _QWORD v19[3]; // [rsp+48h] [rbp-450h] BYREF
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
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
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
      v11 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v19, v20, a5);
      goto LABEL_19;
    }
LABEL_4:
    v11 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v11;
    goto LABEL_20;
  }
  if ( v20 != (LPWSTR)v21 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180009ae4  mov     [rsp+arg_0], rbx
0x180009ae9  push    rsi
0x180009aea  push    rdi
0x180009aeb  push    r14
0x180009aed  sub     rsp, 480h
0x180009af4  mov     rax, cs:__security_cookie
0x180009afb  xor     rax, rsp
0x180009afe  mov     [rsp+498h+var_28], rax
0x180009b06  mov     rsi, r9
0x180009b09  mov     rax, rdx
0x180009b0c  xor     ebx, ebx
0x180009b0e  mov     [rsp+498h+var_440], rbx
0x180009b13  mov     [rsp+498h+var_448], rcx
0x180009b18  mov     [rsp+498h+var_450], rbx
0x180009b1d  mov     [rsp+498h+var_438], rbx
0x180009b22  xor     edx, edx; hFile
0x180009b24  lea     r8d, [rbx+2]; dwFlags
0x180009b28  mov     rcx, rax; lpLibFileName
0x180009b2b  call    cs:__imp_LoadLibraryExW
0x180009b31  mov     rdi, rax
0x180009b34  mov     [rsp+498h+var_460], rax
0x180009b39  test    rax, rax
0x180009b3c  jnz     short loc_180009B4A
0x180009b3e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180009b43  mov     ebx, eax
0x180009b45  jmp     loc_180009C75
0x180009b4a  xor     r9d, r9d; wLanguage
0x180009b4d  lea     r8d, [r9+65h]; lpName
0x180009b51  mov     rdx, rsi; lpType
0x180009b54  mov     rcx, rdi; hModule
0x180009b57  call    cs:__imp_FindResourceExW
0x180009b5d  mov     rsi, rax
0x180009b60  test    rax, rax
0x180009b63  jnz     short loc_180009B6F
0x180009b65  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180009b6a  jmp     loc_180009C69
0x180009b6f  mov     rdx, rsi; hResInfo
0x180009b72  mov     rcx, rdi; hModule
0x180009b75  call    cs:__imp_LoadResource
0x180009b7b  mov     r14, rax
0x180009b7e  mov     [rsp+498h+var_458], rax
0x180009b83  test    rax, rax
0x180009b86  jz      short loc_180009B65
0x180009b88  mov     rdx, rsi; hResInfo
0x180009b8b  mov     rcx, rdi; hModule
0x180009b8e  call    cs:__imp_SizeofResource
0x180009b94  mov     esi, eax
0x180009b96  mov     [rsp+498h+var_468], eax
0x180009b9a  inc     eax
0x180009b9c  cmp     eax, esi
0x180009b9e  jnb     short loc_180009BC1
0x180009ba0  lea     rax, [rsp+498h+var_430]
0x180009ba5  cmp     [rsp+498h+var_438], rax
0x180009baa  jz      short loc_180009BB7
0x180009bac  lea     rcx, [rsp+498h+var_438]
0x180009bb1  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180009bb6  nop
0x180009bb7  mov     eax, 8007000Eh
0x180009bbc  jmp     loc_180009C8E
0x180009bc1  test    eax, eax
0x180009bc3  jz      short loc_180009BF8
0x180009bc5  mov     ecx, eax
0x180009bc7  xor     edx, edx
0x180009bc9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009bcd  div     rcx
0x180009bd0  cmp     rax, 2
0x180009bd4  jb      loc_180009CB2
0x180009bda  lea     rdx, [rcx+rcx]
0x180009bde  cmp     rdx, 400h
0x180009be5  jbe     short loc_180009BF8
0x180009be7  lea     rcx, [rsp+498h+var_438]
0x180009bec  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180009bf1  mov     rax, [rsp+498h+var_438]
0x180009bf6  jmp     short loc_180009C02
0x180009bf8  lea     rax, [rsp+498h+var_430]
0x180009bfd  mov     [rsp+498h+var_438], rax
0x180009c02  jmp     short loc_180009C19
0x180009c04  xor     ebx, ebx
0x180009c06  mov     rdi, [rsp+498h+var_460]
0x180009c0b  mov     r14, [rsp+498h+var_458]
0x180009c10  mov     esi, [rsp+498h+var_468]
0x180009c14  mov     rax, [rsp+498h+var_438]
0x180009c19  test    rax, rax
0x180009c1c  jnz     short loc_180009C25
0x180009c1e  mov     ebx, 8007000Eh
0x180009c23  jmp     short loc_180009C6B
0x180009c25  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x180009c29  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180009c2e  mov     r9d, esi; cbMultiByte
0x180009c31  mov     r8, r14; lpMultiByteStr
0x180009c34  xor     edx, edx; dwFlags
0x180009c36  lea     ecx, [rdx+3]; CodePage
0x180009c39  call    cs:__imp_MultiByteToWideChar
0x180009c3f  test    eax, eax
0x180009c41  jz      loc_180009B65
0x180009c47  mov     ecx, eax
0x180009c49  mov     rax, [rsp+498h+var_438]
0x180009c4e  mov     [rax+rcx*2], bx
0x180009c52  mov     r8d, [rsp+498h+arg_20]; int
0x180009c5a  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180009c5f  lea     rcx, [rsp+498h+var_450]; this
0x180009c64  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180009c69  mov     ebx, eax
0x180009c6b  mov     rcx, rdi; hLibModule
0x180009c6e  call    cs:__imp_FreeLibrary
0x180009c74  nop
0x180009c75  lea     rax, [rsp+498h+var_430]
0x180009c7a  cmp     [rsp+498h+var_438], rax
0x180009c7f  jz      short loc_180009C8C
0x180009c81  lea     rcx, [rsp+498h+var_438]
0x180009c86  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180009c8b  nop
0x180009c8c  mov     eax, ebx
0x180009c8e  mov     rcx, [rsp+498h+var_28]
0x180009c96  xor     rcx, rsp; StackCookie
0x180009c99  call    __security_check_cookie
0x180009c9e  mov     rbx, [rsp+498h+arg_0]
0x180009ca6  add     rsp, 480h
0x180009cad  pop     r14
0x180009caf  pop     rdi
0x180009cb0  pop     rsi
0x180009cb1  retn
0x180009cb2  mov     ecx, 80070057h; int
0x180009cb7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
