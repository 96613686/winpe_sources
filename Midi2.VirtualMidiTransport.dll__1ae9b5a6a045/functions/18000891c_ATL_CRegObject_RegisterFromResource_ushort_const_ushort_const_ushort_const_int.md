# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000891c`
- end: `0x180008af6`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `474`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000a514`

## callees

- `0x1800038f0`
- `0x18000653c`
- `0x18000666c`
- `0x1800066a8`
- `0x180006e9c`
- `0x18000878c`
- `0x18000891c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800089c6`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800089c6`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000898f`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000898f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800089ad`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800089ad`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008963`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008963`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008aa6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008aa6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180008a71`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180008a71`

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
0x18000891c  mov     [rsp+arg_0], rbx
0x180008921  push    rsi
0x180008922  push    rdi
0x180008923  push    r14
0x180008925  sub     rsp, 480h
0x18000892c  mov     rax, cs:__security_cookie
0x180008933  xor     rax, rsp
0x180008936  mov     [rsp+498h+var_28], rax
0x18000893e  mov     rsi, r9
0x180008941  mov     rax, rdx
0x180008944  xor     ebx, ebx
0x180008946  mov     [rsp+498h+var_440], rbx
0x18000894b  mov     [rsp+498h+var_448], rcx
0x180008950  mov     [rsp+498h+var_450], rbx
0x180008955  mov     [rsp+498h+var_438], rbx
0x18000895a  xor     edx, edx; hFile
0x18000895c  lea     r8d, [rbx+2]; dwFlags
0x180008960  mov     rcx, rax; lpLibFileName
0x180008963  call    cs:__imp_LoadLibraryExW
0x180008969  mov     rdi, rax
0x18000896c  mov     [rsp+498h+var_460], rax
0x180008971  test    rax, rax
0x180008974  jnz     short loc_180008982
0x180008976  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000897b  mov     ebx, eax
0x18000897d  jmp     loc_180008AAD
0x180008982  xor     r9d, r9d; wLanguage
0x180008985  lea     r8d, [r9+65h]; lpName
0x180008989  mov     rdx, rsi; lpType
0x18000898c  mov     rcx, rdi; hModule
0x18000898f  call    cs:__imp_FindResourceExW
0x180008995  mov     rsi, rax
0x180008998  test    rax, rax
0x18000899b  jnz     short loc_1800089A7
0x18000899d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800089a2  jmp     loc_180008AA1
0x1800089a7  mov     rdx, rsi; hResInfo
0x1800089aa  mov     rcx, rdi; hModule
0x1800089ad  call    cs:__imp_LoadResource
0x1800089b3  mov     r14, rax
0x1800089b6  mov     [rsp+498h+var_458], rax
0x1800089bb  test    rax, rax
0x1800089be  jz      short loc_18000899D
0x1800089c0  mov     rdx, rsi; hResInfo
0x1800089c3  mov     rcx, rdi; hModule
0x1800089c6  call    cs:__imp_SizeofResource
0x1800089cc  mov     esi, eax
0x1800089ce  mov     [rsp+498h+var_468], eax
0x1800089d2  inc     eax
0x1800089d4  cmp     eax, esi
0x1800089d6  jnb     short loc_1800089F9
0x1800089d8  lea     rax, [rsp+498h+var_430]
0x1800089dd  cmp     [rsp+498h+var_438], rax
0x1800089e2  jz      short loc_1800089EF
0x1800089e4  lea     rcx, [rsp+498h+var_438]
0x1800089e9  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800089ee  nop
0x1800089ef  mov     eax, 8007000Eh
0x1800089f4  jmp     loc_180008AC6
0x1800089f9  test    eax, eax
0x1800089fb  jz      short loc_180008A30
0x1800089fd  mov     ecx, eax
0x1800089ff  xor     edx, edx
0x180008a01  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008a05  div     rcx
0x180008a08  cmp     rax, 2
0x180008a0c  jb      loc_180008AEA
0x180008a12  lea     rdx, [rcx+rcx]
0x180008a16  cmp     rdx, 400h
0x180008a1d  jbe     short loc_180008A30
0x180008a1f  lea     rcx, [rsp+498h+var_438]
0x180008a24  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180008a29  mov     rax, [rsp+498h+var_438]
0x180008a2e  jmp     short loc_180008A3A
0x180008a30  lea     rax, [rsp+498h+var_430]
0x180008a35  mov     [rsp+498h+var_438], rax
0x180008a3a  jmp     short loc_180008A51
0x180008a3c  xor     ebx, ebx
0x180008a3e  mov     rdi, [rsp+498h+var_460]
0x180008a43  mov     r14, [rsp+498h+var_458]
0x180008a48  mov     esi, [rsp+498h+var_468]
0x180008a4c  mov     rax, [rsp+498h+var_438]
0x180008a51  test    rax, rax
0x180008a54  jnz     short loc_180008A5D
0x180008a56  mov     ebx, 8007000Eh
0x180008a5b  jmp     short loc_180008AA3
0x180008a5d  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x180008a61  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180008a66  mov     r9d, esi; cbMultiByte
0x180008a69  mov     r8, r14; lpMultiByteStr
0x180008a6c  xor     edx, edx; dwFlags
0x180008a6e  lea     ecx, [rdx+3]; CodePage
0x180008a71  call    cs:__imp_MultiByteToWideChar
0x180008a77  test    eax, eax
0x180008a79  jz      loc_18000899D
0x180008a7f  mov     ecx, eax
0x180008a81  mov     rax, [rsp+498h+var_438]
0x180008a86  mov     [rax+rcx*2], bx
0x180008a8a  mov     r8d, [rsp+498h+arg_20]; int
0x180008a92  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180008a97  lea     rcx, [rsp+498h+var_450]; this
0x180008a9c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180008aa1  mov     ebx, eax
0x180008aa3  mov     rcx, rdi; hLibModule
0x180008aa6  call    cs:__imp_FreeLibrary
0x180008aac  nop
0x180008aad  lea     rax, [rsp+498h+var_430]
0x180008ab2  cmp     [rsp+498h+var_438], rax
0x180008ab7  jz      short loc_180008AC4
0x180008ab9  lea     rcx, [rsp+498h+var_438]
0x180008abe  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180008ac3  nop
0x180008ac4  mov     eax, ebx
0x180008ac6  mov     rcx, [rsp+498h+var_28]
0x180008ace  xor     rcx, rsp; StackCookie
0x180008ad1  call    __security_check_cookie
0x180008ad6  mov     rbx, [rsp+498h+arg_0]
0x180008ade  add     rsp, 480h
0x180008ae5  pop     r14
0x180008ae7  pop     rdi
0x180008ae8  pop     rsi
0x180008ae9  retn
0x180008aea  mov     ecx, 80070057h; int
0x180008aef  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
