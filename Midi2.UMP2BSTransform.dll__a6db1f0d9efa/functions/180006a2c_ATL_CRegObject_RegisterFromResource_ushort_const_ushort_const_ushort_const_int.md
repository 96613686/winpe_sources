# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180006a2c`
- end: `0x180006c06`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `474`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800084d4`

## callees

- `0x180001ef0`
- `0x18000468c`
- `0x1800047bc`
- `0x1800047f8`
- `0x180004fe8`
- `0x18000689c`
- `0x180006a2c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180006a9f`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180006a9f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006a73`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006a73`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180006ad6`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180006ad6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006bb6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006bb6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180006abd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180006abd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180006b81`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180006b81`

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
0x180006a2c  mov     [rsp+arg_0], rbx
0x180006a31  push    rsi
0x180006a32  push    rdi
0x180006a33  push    r14
0x180006a35  sub     rsp, 480h
0x180006a3c  mov     rax, cs:__security_cookie
0x180006a43  xor     rax, rsp
0x180006a46  mov     [rsp+498h+var_28], rax
0x180006a4e  mov     rsi, r9
0x180006a51  mov     rax, rdx
0x180006a54  xor     ebx, ebx
0x180006a56  mov     [rsp+498h+var_440], rbx
0x180006a5b  mov     [rsp+498h+var_448], rcx
0x180006a60  mov     [rsp+498h+var_450], rbx
0x180006a65  mov     [rsp+498h+var_438], rbx
0x180006a6a  xor     edx, edx; hFile
0x180006a6c  lea     r8d, [rbx+2]; dwFlags
0x180006a70  mov     rcx, rax; lpLibFileName
0x180006a73  call    cs:__imp_LoadLibraryExW
0x180006a79  mov     rdi, rax
0x180006a7c  mov     [rsp+498h+var_460], rax
0x180006a81  test    rax, rax
0x180006a84  jnz     short loc_180006A92
0x180006a86  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006a8b  mov     ebx, eax
0x180006a8d  jmp     loc_180006BBD
0x180006a92  xor     r9d, r9d; wLanguage
0x180006a95  lea     r8d, [r9+65h]; lpName
0x180006a99  mov     rdx, rsi; lpType
0x180006a9c  mov     rcx, rdi; hModule
0x180006a9f  call    cs:__imp_FindResourceExW
0x180006aa5  mov     rsi, rax
0x180006aa8  test    rax, rax
0x180006aab  jnz     short loc_180006AB7
0x180006aad  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006ab2  jmp     loc_180006BB1
0x180006ab7  mov     rdx, rsi; hResInfo
0x180006aba  mov     rcx, rdi; hModule
0x180006abd  call    cs:__imp_LoadResource
0x180006ac3  mov     r14, rax
0x180006ac6  mov     [rsp+498h+var_458], rax
0x180006acb  test    rax, rax
0x180006ace  jz      short loc_180006AAD
0x180006ad0  mov     rdx, rsi; hResInfo
0x180006ad3  mov     rcx, rdi; hModule
0x180006ad6  call    cs:__imp_SizeofResource
0x180006adc  mov     esi, eax
0x180006ade  mov     [rsp+498h+var_468], eax
0x180006ae2  inc     eax
0x180006ae4  cmp     eax, esi
0x180006ae6  jnb     short loc_180006B09
0x180006ae8  lea     rax, [rsp+498h+var_430]
0x180006aed  cmp     [rsp+498h+var_438], rax
0x180006af2  jz      short loc_180006AFF
0x180006af4  lea     rcx, [rsp+498h+var_438]
0x180006af9  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180006afe  nop
0x180006aff  mov     eax, 8007000Eh
0x180006b04  jmp     loc_180006BD6
0x180006b09  test    eax, eax
0x180006b0b  jz      short loc_180006B40
0x180006b0d  mov     ecx, eax
0x180006b0f  xor     edx, edx
0x180006b11  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006b15  div     rcx
0x180006b18  cmp     rax, 2
0x180006b1c  jb      loc_180006BFA
0x180006b22  lea     rdx, [rcx+rcx]
0x180006b26  cmp     rdx, 400h
0x180006b2d  jbe     short loc_180006B40
0x180006b2f  lea     rcx, [rsp+498h+var_438]
0x180006b34  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180006b39  mov     rax, [rsp+498h+var_438]
0x180006b3e  jmp     short loc_180006B4A
0x180006b40  lea     rax, [rsp+498h+var_430]
0x180006b45  mov     [rsp+498h+var_438], rax
0x180006b4a  jmp     short loc_180006B61
0x180006b4c  xor     ebx, ebx
0x180006b4e  mov     rdi, [rsp+498h+var_460]
0x180006b53  mov     r14, [rsp+498h+var_458]
0x180006b58  mov     esi, [rsp+498h+var_468]
0x180006b5c  mov     rax, [rsp+498h+var_438]
0x180006b61  test    rax, rax
0x180006b64  jnz     short loc_180006B6D
0x180006b66  mov     ebx, 8007000Eh
0x180006b6b  jmp     short loc_180006BB3
0x180006b6d  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x180006b71  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180006b76  mov     r9d, esi; cbMultiByte
0x180006b79  mov     r8, r14; lpMultiByteStr
0x180006b7c  xor     edx, edx; dwFlags
0x180006b7e  lea     ecx, [rdx+3]; CodePage
0x180006b81  call    cs:__imp_MultiByteToWideChar
0x180006b87  test    eax, eax
0x180006b89  jz      loc_180006AAD
0x180006b8f  mov     ecx, eax
0x180006b91  mov     rax, [rsp+498h+var_438]
0x180006b96  mov     [rax+rcx*2], bx
0x180006b9a  mov     r8d, [rsp+498h+arg_20]; int
0x180006ba2  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180006ba7  lea     rcx, [rsp+498h+var_450]; this
0x180006bac  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180006bb1  mov     ebx, eax
0x180006bb3  mov     rcx, rdi; hLibModule
0x180006bb6  call    cs:__imp_FreeLibrary
0x180006bbc  nop
0x180006bbd  lea     rax, [rsp+498h+var_430]
0x180006bc2  cmp     [rsp+498h+var_438], rax
0x180006bc7  jz      short loc_180006BD4
0x180006bc9  lea     rcx, [rsp+498h+var_438]
0x180006bce  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180006bd3  nop
0x180006bd4  mov     eax, ebx
0x180006bd6  mov     rcx, [rsp+498h+var_28]
0x180006bde  xor     rcx, rsp; StackCookie
0x180006be1  call    __security_check_cookie
0x180006be6  mov     rbx, [rsp+498h+arg_0]
0x180006bee  add     rsp, 480h
0x180006bf5  pop     r14
0x180006bf7  pop     rdi
0x180006bf8  pop     rsi
0x180006bf9  retn
0x180006bfa  mov     ecx, 80070057h; int
0x180006bff  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
