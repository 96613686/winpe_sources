# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000699c`
- end: `0x180006b76`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `474`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180008444`

## callees

- `0x180001e60`
- `0x1800045fc`
- `0x18000472c`
- `0x180004768`
- `0x180004f58`
- `0x18000680c`
- `0x18000699c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006b26`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006b26`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180006a2d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180006a2d`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180006a46`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180006a46`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800069e3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800069e3`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180006a0f`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180006a0f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180006af1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180006af1`

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
0x18000699c  mov     [rsp+arg_0], rbx
0x1800069a1  push    rsi
0x1800069a2  push    rdi
0x1800069a3  push    r14
0x1800069a5  sub     rsp, 480h
0x1800069ac  mov     rax, cs:__security_cookie
0x1800069b3  xor     rax, rsp
0x1800069b6  mov     [rsp+498h+var_28], rax
0x1800069be  mov     rsi, r9
0x1800069c1  mov     rax, rdx
0x1800069c4  xor     ebx, ebx
0x1800069c6  mov     [rsp+498h+var_440], rbx
0x1800069cb  mov     [rsp+498h+var_448], rcx
0x1800069d0  mov     [rsp+498h+var_450], rbx
0x1800069d5  mov     [rsp+498h+var_438], rbx
0x1800069da  xor     edx, edx; hFile
0x1800069dc  lea     r8d, [rbx+2]; dwFlags
0x1800069e0  mov     rcx, rax; lpLibFileName
0x1800069e3  call    cs:__imp_LoadLibraryExW
0x1800069e9  mov     rdi, rax
0x1800069ec  mov     [rsp+498h+var_460], rax
0x1800069f1  test    rax, rax
0x1800069f4  jnz     short loc_180006A02
0x1800069f6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800069fb  mov     ebx, eax
0x1800069fd  jmp     loc_180006B2D
0x180006a02  xor     r9d, r9d; wLanguage
0x180006a05  lea     r8d, [r9+65h]; lpName
0x180006a09  mov     rdx, rsi; lpType
0x180006a0c  mov     rcx, rdi; hModule
0x180006a0f  call    cs:__imp_FindResourceExW
0x180006a15  mov     rsi, rax
0x180006a18  test    rax, rax
0x180006a1b  jnz     short loc_180006A27
0x180006a1d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006a22  jmp     loc_180006B21
0x180006a27  mov     rdx, rsi; hResInfo
0x180006a2a  mov     rcx, rdi; hModule
0x180006a2d  call    cs:__imp_LoadResource
0x180006a33  mov     r14, rax
0x180006a36  mov     [rsp+498h+var_458], rax
0x180006a3b  test    rax, rax
0x180006a3e  jz      short loc_180006A1D
0x180006a40  mov     rdx, rsi; hResInfo
0x180006a43  mov     rcx, rdi; hModule
0x180006a46  call    cs:__imp_SizeofResource
0x180006a4c  mov     esi, eax
0x180006a4e  mov     [rsp+498h+var_468], eax
0x180006a52  inc     eax
0x180006a54  cmp     eax, esi
0x180006a56  jnb     short loc_180006A79
0x180006a58  lea     rax, [rsp+498h+var_430]
0x180006a5d  cmp     [rsp+498h+var_438], rax
0x180006a62  jz      short loc_180006A6F
0x180006a64  lea     rcx, [rsp+498h+var_438]
0x180006a69  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180006a6e  nop
0x180006a6f  mov     eax, 8007000Eh
0x180006a74  jmp     loc_180006B46
0x180006a79  test    eax, eax
0x180006a7b  jz      short loc_180006AB0
0x180006a7d  mov     ecx, eax
0x180006a7f  xor     edx, edx
0x180006a81  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006a85  div     rcx
0x180006a88  cmp     rax, 2
0x180006a8c  jb      loc_180006B6A
0x180006a92  lea     rdx, [rcx+rcx]
0x180006a96  cmp     rdx, 400h
0x180006a9d  jbe     short loc_180006AB0
0x180006a9f  lea     rcx, [rsp+498h+var_438]
0x180006aa4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180006aa9  mov     rax, [rsp+498h+var_438]
0x180006aae  jmp     short loc_180006ABA
0x180006ab0  lea     rax, [rsp+498h+var_430]
0x180006ab5  mov     [rsp+498h+var_438], rax
0x180006aba  jmp     short loc_180006AD1
0x180006abc  xor     ebx, ebx
0x180006abe  mov     rdi, [rsp+498h+var_460]
0x180006ac3  mov     r14, [rsp+498h+var_458]
0x180006ac8  mov     esi, [rsp+498h+var_468]
0x180006acc  mov     rax, [rsp+498h+var_438]
0x180006ad1  test    rax, rax
0x180006ad4  jnz     short loc_180006ADD
0x180006ad6  mov     ebx, 8007000Eh
0x180006adb  jmp     short loc_180006B23
0x180006add  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x180006ae1  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180006ae6  mov     r9d, esi; cbMultiByte
0x180006ae9  mov     r8, r14; lpMultiByteStr
0x180006aec  xor     edx, edx; dwFlags
0x180006aee  lea     ecx, [rdx+3]; CodePage
0x180006af1  call    cs:__imp_MultiByteToWideChar
0x180006af7  test    eax, eax
0x180006af9  jz      loc_180006A1D
0x180006aff  mov     ecx, eax
0x180006b01  mov     rax, [rsp+498h+var_438]
0x180006b06  mov     [rax+rcx*2], bx
0x180006b0a  mov     r8d, [rsp+498h+arg_20]; int
0x180006b12  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180006b17  lea     rcx, [rsp+498h+var_450]; this
0x180006b1c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180006b21  mov     ebx, eax
0x180006b23  mov     rcx, rdi; hLibModule
0x180006b26  call    cs:__imp_FreeLibrary
0x180006b2c  nop
0x180006b2d  lea     rax, [rsp+498h+var_430]
0x180006b32  cmp     [rsp+498h+var_438], rax
0x180006b37  jz      short loc_180006B44
0x180006b39  lea     rcx, [rsp+498h+var_438]
0x180006b3e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180006b43  nop
0x180006b44  mov     eax, ebx
0x180006b46  mov     rcx, [rsp+498h+var_28]
0x180006b4e  xor     rcx, rsp; StackCookie
0x180006b51  call    __security_check_cookie
0x180006b56  mov     rbx, [rsp+498h+arg_0]
0x180006b5e  add     rsp, 480h
0x180006b65  pop     r14
0x180006b67  pop     rdi
0x180006b68  pop     rsi
0x180006b69  retn
0x180006b6a  mov     ecx, 80070057h; int
0x180006b6f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
