# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180006b3c`
- end: `0x180006d16`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `474`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800085f4`

## callees

- `0x180002000`
- `0x18000479c`
- `0x1800048cc`
- `0x180004908`
- `0x1800050f8`
- `0x1800069ac`
- `0x180006b3c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180006be6`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180006be6`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180006baf`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180006baf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180006bcd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180006bcd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006cc6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006cc6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006b83`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006b83`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180006c91`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180006c91`

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
0x180006b3c  mov     [rsp+arg_0], rbx
0x180006b41  push    rsi
0x180006b42  push    rdi
0x180006b43  push    r14
0x180006b45  sub     rsp, 480h
0x180006b4c  mov     rax, cs:__security_cookie
0x180006b53  xor     rax, rsp
0x180006b56  mov     [rsp+498h+var_28], rax
0x180006b5e  mov     rsi, r9
0x180006b61  mov     rax, rdx
0x180006b64  xor     ebx, ebx
0x180006b66  mov     [rsp+498h+var_440], rbx
0x180006b6b  mov     [rsp+498h+var_448], rcx
0x180006b70  mov     [rsp+498h+var_450], rbx
0x180006b75  mov     [rsp+498h+var_438], rbx
0x180006b7a  xor     edx, edx; hFile
0x180006b7c  lea     r8d, [rbx+2]; dwFlags
0x180006b80  mov     rcx, rax; lpLibFileName
0x180006b83  call    cs:__imp_LoadLibraryExW
0x180006b89  mov     rdi, rax
0x180006b8c  mov     [rsp+498h+var_460], rax
0x180006b91  test    rax, rax
0x180006b94  jnz     short loc_180006BA2
0x180006b96  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006b9b  mov     ebx, eax
0x180006b9d  jmp     loc_180006CCD
0x180006ba2  xor     r9d, r9d; wLanguage
0x180006ba5  lea     r8d, [r9+65h]; lpName
0x180006ba9  mov     rdx, rsi; lpType
0x180006bac  mov     rcx, rdi; hModule
0x180006baf  call    cs:__imp_FindResourceExW
0x180006bb5  mov     rsi, rax
0x180006bb8  test    rax, rax
0x180006bbb  jnz     short loc_180006BC7
0x180006bbd  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006bc2  jmp     loc_180006CC1
0x180006bc7  mov     rdx, rsi; hResInfo
0x180006bca  mov     rcx, rdi; hModule
0x180006bcd  call    cs:__imp_LoadResource
0x180006bd3  mov     r14, rax
0x180006bd6  mov     [rsp+498h+var_458], rax
0x180006bdb  test    rax, rax
0x180006bde  jz      short loc_180006BBD
0x180006be0  mov     rdx, rsi; hResInfo
0x180006be3  mov     rcx, rdi; hModule
0x180006be6  call    cs:__imp_SizeofResource
0x180006bec  mov     esi, eax
0x180006bee  mov     [rsp+498h+var_468], eax
0x180006bf2  inc     eax
0x180006bf4  cmp     eax, esi
0x180006bf6  jnb     short loc_180006C19
0x180006bf8  lea     rax, [rsp+498h+var_430]
0x180006bfd  cmp     [rsp+498h+var_438], rax
0x180006c02  jz      short loc_180006C0F
0x180006c04  lea     rcx, [rsp+498h+var_438]
0x180006c09  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180006c0e  nop
0x180006c0f  mov     eax, 8007000Eh
0x180006c14  jmp     loc_180006CE6
0x180006c19  test    eax, eax
0x180006c1b  jz      short loc_180006C50
0x180006c1d  mov     ecx, eax
0x180006c1f  xor     edx, edx
0x180006c21  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006c25  div     rcx
0x180006c28  cmp     rax, 2
0x180006c2c  jb      loc_180006D0A
0x180006c32  lea     rdx, [rcx+rcx]
0x180006c36  cmp     rdx, 400h
0x180006c3d  jbe     short loc_180006C50
0x180006c3f  lea     rcx, [rsp+498h+var_438]
0x180006c44  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180006c49  mov     rax, [rsp+498h+var_438]
0x180006c4e  jmp     short loc_180006C5A
0x180006c50  lea     rax, [rsp+498h+var_430]
0x180006c55  mov     [rsp+498h+var_438], rax
0x180006c5a  jmp     short loc_180006C71
0x180006c5c  xor     ebx, ebx
0x180006c5e  mov     rdi, [rsp+498h+var_460]
0x180006c63  mov     r14, [rsp+498h+var_458]
0x180006c68  mov     esi, [rsp+498h+var_468]
0x180006c6c  mov     rax, [rsp+498h+var_438]
0x180006c71  test    rax, rax
0x180006c74  jnz     short loc_180006C7D
0x180006c76  mov     ebx, 8007000Eh
0x180006c7b  jmp     short loc_180006CC3
0x180006c7d  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x180006c81  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180006c86  mov     r9d, esi; cbMultiByte
0x180006c89  mov     r8, r14; lpMultiByteStr
0x180006c8c  xor     edx, edx; dwFlags
0x180006c8e  lea     ecx, [rdx+3]; CodePage
0x180006c91  call    cs:__imp_MultiByteToWideChar
0x180006c97  test    eax, eax
0x180006c99  jz      loc_180006BBD
0x180006c9f  mov     ecx, eax
0x180006ca1  mov     rax, [rsp+498h+var_438]
0x180006ca6  mov     [rax+rcx*2], bx
0x180006caa  mov     r8d, [rsp+498h+arg_20]; int
0x180006cb2  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180006cb7  lea     rcx, [rsp+498h+var_450]; this
0x180006cbc  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180006cc1  mov     ebx, eax
0x180006cc3  mov     rcx, rdi; hLibModule
0x180006cc6  call    cs:__imp_FreeLibrary
0x180006ccc  nop
0x180006ccd  lea     rax, [rsp+498h+var_430]
0x180006cd2  cmp     [rsp+498h+var_438], rax
0x180006cd7  jz      short loc_180006CE4
0x180006cd9  lea     rcx, [rsp+498h+var_438]
0x180006cde  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180006ce3  nop
0x180006ce4  mov     eax, ebx
0x180006ce6  mov     rcx, [rsp+498h+var_28]
0x180006cee  xor     rcx, rsp; StackCookie
0x180006cf1  call    __security_check_cookie
0x180006cf6  mov     rbx, [rsp+498h+arg_0]
0x180006cfe  add     rsp, 480h
0x180006d05  pop     r14
0x180006d07  pop     rdi
0x180006d08  pop     rsi
0x180006d09  retn
0x180006d0a  mov     ecx, 80070057h; int
0x180006d0f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
