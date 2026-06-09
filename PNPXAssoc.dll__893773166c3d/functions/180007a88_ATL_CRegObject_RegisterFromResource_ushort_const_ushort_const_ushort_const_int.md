# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180007a88`
- end: `0x180007c43`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `443`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800088fc`
- `0x180008c1c`

## callees

- `0x180006018`
- `0x18000626c`
- `0x180006764`
- `0x180006ebc`
- `0x1800078f8`
- `0x180007a88`
- `0x180012e00`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180007bf8`
- `KERNEL32!FreeLibrary` at `0x180007bf8`
- `KERNEL32!LoadLibraryExW` at `0x180007ad9`
- `KERNEL32!LoadLibraryExW` at `0x180007ad9`
- `KERNEL32!MultiByteToWideChar` at `0x180007bc2`
- `KERNEL32!MultiByteToWideChar` at `0x180007bc2`
- `KERNEL32!LoadResource` at `0x180007b1d`
- `KERNEL32!LoadResource` at `0x180007b1d`
- `KERNEL32!FindResourceExW` at `0x180007aff`
- `KERNEL32!FindResourceExW` at `0x180007aff`
- `KERNEL32!SizeofResource` at `0x180007b31`
- `KERNEL32!SizeofResource` at `0x180007b31`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v8; // rdi
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rbx
  unsigned int v12; // eax
  const CHAR *v13; // rsi
  DWORD cchWideChar; // ebx
  __int64 v15; // rcx
  WCHAR *lpWideCharStr; // rax
  int v18; // eax
  _QWORD v19[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[1032]; // [rsp+48h] [rbp-B8h] BYREF

  v19[1] = this;
  v19[0] = 0;
  v20 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_21:
    if ( v20 != (LPWSTR)v21 )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
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
  if ( (unsigned int)v15 >= cchWideChar )
  {
    if ( cchWideChar == -1 )
      goto LABEL_14;
    if ( 0xFFFFFFFFFFFFFFFFuLL / (unsigned int)v15 < 2 )
      ATL::AtlThrowImpl(-2147024809);
    if ( (unsigned __int64)(2 * v15) <= 0x400 )
    {
LABEL_14:
      lpWideCharStr = (WCHAR *)v21;
      v20 = (LPWSTR)v21;
    }
    else
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v20, 2 * v15);
      lpWideCharStr = v20;
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
      v20[v18] = 0;
      v12 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v19, v20, a5);
      goto LABEL_19;
    }
LABEL_4:
    v12 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v12;
    goto LABEL_20;
  }
  if ( v20 != (LPWSTR)v21 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180007a88  mov     [rsp-8+arg_0], rbx
0x180007a8d  push    rbp
0x180007a8e  push    rsi
0x180007a8f  push    rdi
0x180007a90  lea     rbp, [rsp-360h]
0x180007a98  sub     rsp, 460h
0x180007a9f  mov     rax, cs:__security_cookie
0x180007aa6  xor     rax, rsp
0x180007aa9  mov     [rbp+370h+var_20], rax
0x180007ab0  mov     rax, rdx
0x180007ab3  mov     [rsp+470h+var_438], rcx
0x180007ab8  xor     edx, edx; hFile
0x180007aba  mov     [rsp+470h+var_440], 0
0x180007ac3  mov     rbx, r8
0x180007ac6  mov     [rsp+470h+var_430], 0
0x180007acf  mov     rcx, rax; lpLibFileName
0x180007ad2  mov     rsi, r9
0x180007ad5  lea     r8d, [rdx+2]; dwFlags
0x180007ad9  call    cs:__imp_LoadLibraryExW
0x180007adf  mov     rdi, rax
0x180007ae2  test    rax, rax
0x180007ae5  jnz     short loc_180007AF3
0x180007ae7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180007aec  mov     ebx, eax
0x180007aee  jmp     loc_180007BFE
0x180007af3  xor     r9d, r9d; wLanguage
0x180007af6  mov     r8, rbx; lpName
0x180007af9  mov     rdx, rsi; lpType
0x180007afc  mov     rcx, rdi; hModule
0x180007aff  call    cs:__imp_FindResourceExW
0x180007b05  mov     rbx, rax
0x180007b08  test    rax, rax
0x180007b0b  jnz     short loc_180007B17
0x180007b0d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180007b12  jmp     loc_180007BF3
0x180007b17  mov     rdx, rbx; hResInfo
0x180007b1a  mov     rcx, rdi; hModule
0x180007b1d  call    cs:__imp_LoadResource
0x180007b23  mov     rsi, rax
0x180007b26  test    rax, rax
0x180007b29  jz      short loc_180007B0D
0x180007b2b  mov     rdx, rbx; hResInfo
0x180007b2e  mov     rcx, rdi; hModule
0x180007b31  call    cs:__imp_SizeofResource
0x180007b37  mov     ebx, eax
0x180007b39  lea     ecx, [rax+1]
0x180007b3c  cmp     ecx, eax
0x180007b3e  jnb     short loc_180007B60
0x180007b40  lea     rax, [rsp+470h+var_428]
0x180007b45  cmp     [rsp+470h+var_430], rax
0x180007b4a  jz      short loc_180007B56
0x180007b4c  lea     rcx, [rsp+470h+var_430]
0x180007b51  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180007b56  mov     eax, 8007000Eh
0x180007b5b  jmp     loc_180007C16
0x180007b60  test    ecx, ecx
0x180007b62  jz      short loc_180007B98
0x180007b64  xor     edx, edx
0x180007b66  mov     r8d, ecx
0x180007b69  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007b6d  div     r8
0x180007b70  cmp     rax, 2
0x180007b74  jb      loc_180007C38
0x180007b7a  lea     rdx, [rcx+rcx]
0x180007b7e  cmp     rdx, 400h
0x180007b85  jbe     short loc_180007B98
0x180007b87  lea     rcx, [rsp+470h+var_430]
0x180007b8c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180007b91  mov     rax, [rsp+470h+var_430]
0x180007b96  jmp     short loc_180007BA2
0x180007b98  lea     rax, [rsp+470h+var_428]
0x180007b9d  mov     [rsp+470h+var_430], rax
0x180007ba2  test    rax, rax
0x180007ba5  jnz     short loc_180007BAE
0x180007ba7  mov     ebx, 8007000Eh
0x180007bac  jmp     short loc_180007BF5
0x180007bae  xor     edx, edx; dwFlags
0x180007bb0  mov     [rsp+470h+cchWideChar], ebx; cchWideChar
0x180007bb4  mov     r9d, ebx; cbMultiByte
0x180007bb7  mov     [rsp+470h+lpWideCharStr], rax; lpWideCharStr
0x180007bbc  mov     r8, rsi; lpMultiByteStr
0x180007bbf  lea     ecx, [rdx+3]; CodePage
0x180007bc2  call    cs:__imp_MultiByteToWideChar
0x180007bc8  test    eax, eax
0x180007bca  jz      loc_180007B0D
0x180007bd0  mov     r8d, [rbp+370h+arg_20]; int
0x180007bd7  xor     ecx, ecx
0x180007bd9  mov     edx, eax
0x180007bdb  mov     rax, [rsp+470h+var_430]
0x180007be0  mov     [rax+rdx*2], cx
0x180007be4  lea     rcx, [rsp+470h+var_440]; this
0x180007be9  mov     rdx, [rsp+470h+var_430]; unsigned __int16 *
0x180007bee  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180007bf3  mov     ebx, eax
0x180007bf5  mov     rcx, rdi; hLibModule
0x180007bf8  call    cs:__imp_FreeLibrary
0x180007bfe  lea     rax, [rsp+470h+var_428]
0x180007c03  cmp     [rsp+470h+var_430], rax
0x180007c08  jz      short loc_180007C14
0x180007c0a  lea     rcx, [rsp+470h+var_430]
0x180007c0f  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180007c14  mov     eax, ebx
0x180007c16  mov     rcx, [rbp+370h+var_20]
0x180007c1d  xor     rcx, rsp; StackCookie
0x180007c20  call    __security_check_cookie
0x180007c25  mov     rbx, [rsp+470h+arg_0]
0x180007c2d  add     rsp, 460h
0x180007c34  pop     rdi
0x180007c35  pop     rsi
0x180007c36  pop     rbp
0x180007c37  retn
0x180007c38  mov     ecx, 80070057h; int
0x180007c3d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
