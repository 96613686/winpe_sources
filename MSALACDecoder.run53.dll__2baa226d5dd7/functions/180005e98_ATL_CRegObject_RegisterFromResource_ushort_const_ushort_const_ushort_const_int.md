# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180005e98`
- end: `0x180006074`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `476`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180006bcc`
- `0x180006ef4`

## callees

- `0x180001550`
- `0x180004c08`
- `0x180004e04`
- `0x180004e40`
- `0x180005404`
- `0x180005d08`
- `0x180005e98`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180005f44`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180005f44`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005ee2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005ee2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180005f2b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180005f2b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006024`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006024`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180005f0d`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180005f0d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180005fef`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180005fef`

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
  unsigned int v12; // eax
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
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v21);
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
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v21);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180005e98  mov     [rsp+arg_0], rbx
0x180005e9d  push    rsi
0x180005e9e  push    rdi
0x180005e9f  push    r14
0x180005ea1  sub     rsp, 480h
0x180005ea8  mov     rax, cs:__security_cookie
0x180005eaf  xor     rax, rsp
0x180005eb2  mov     [rsp+498h+var_28], rax
0x180005eba  mov     r14, r9
0x180005ebd  mov     rdi, r8
0x180005ec0  mov     rax, rdx
0x180005ec3  xor     ebx, ebx
0x180005ec5  mov     [rsp+498h+var_440], rbx
0x180005eca  mov     [rsp+498h+var_448], rcx
0x180005ecf  mov     [rsp+498h+var_450], rbx
0x180005ed4  mov     [rsp+498h+var_438], rbx
0x180005ed9  xor     edx, edx; hFile
0x180005edb  lea     r8d, [rbx+2]; dwFlags
0x180005edf  mov     rcx, rax; lpLibFileName
0x180005ee2  call    cs:__imp_LoadLibraryExW
0x180005ee8  mov     rsi, rax
0x180005eeb  mov     [rsp+498h+var_460], rax
0x180005ef0  test    rax, rax
0x180005ef3  jnz     short loc_180005F01
0x180005ef5  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005efa  mov     ebx, eax
0x180005efc  jmp     loc_18000602B
0x180005f01  xor     r9d, r9d; wLanguage
0x180005f04  mov     r8, rdi; lpName
0x180005f07  mov     rdx, r14; lpType
0x180005f0a  mov     rcx, rsi; hModule
0x180005f0d  call    cs:__imp_FindResourceExW
0x180005f13  mov     rdi, rax
0x180005f16  test    rax, rax
0x180005f19  jnz     short loc_180005F25
0x180005f1b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005f20  jmp     loc_18000601F
0x180005f25  mov     rdx, rdi; hResInfo
0x180005f28  mov     rcx, rsi; hModule
0x180005f2b  call    cs:__imp_LoadResource
0x180005f31  mov     r14, rax
0x180005f34  mov     [rsp+498h+var_458], rax
0x180005f39  test    rax, rax
0x180005f3c  jz      short loc_180005F1B
0x180005f3e  mov     rdx, rdi; hResInfo
0x180005f41  mov     rcx, rsi; hModule
0x180005f44  call    cs:__imp_SizeofResource
0x180005f4a  mov     edi, eax
0x180005f4c  mov     [rsp+498h+var_468], eax
0x180005f50  inc     eax
0x180005f52  cmp     eax, edi
0x180005f54  jnb     short loc_180005F77
0x180005f56  lea     rax, [rsp+498h+var_430]
0x180005f5b  cmp     [rsp+498h+var_438], rax
0x180005f60  jz      short loc_180005F6D
0x180005f62  lea     rcx, [rsp+498h+var_438]
0x180005f67  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180005f6c  nop
0x180005f6d  mov     eax, 8007000Eh
0x180005f72  jmp     loc_180006044
0x180005f77  test    eax, eax
0x180005f79  jz      short loc_180005FAE
0x180005f7b  mov     ecx, eax
0x180005f7d  xor     edx, edx
0x180005f7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005f83  div     rcx
0x180005f86  cmp     rax, 2
0x180005f8a  jb      loc_180006068
0x180005f90  lea     rdx, [rcx+rcx]
0x180005f94  cmp     rdx, 400h
0x180005f9b  jbe     short loc_180005FAE
0x180005f9d  lea     rcx, [rsp+498h+var_438]
0x180005fa2  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180005fa7  mov     rax, [rsp+498h+var_438]
0x180005fac  jmp     short loc_180005FB8
0x180005fae  lea     rax, [rsp+498h+var_430]
0x180005fb3  mov     [rsp+498h+var_438], rax
0x180005fb8  jmp     short loc_180005FCF
0x180005fba  xor     ebx, ebx
0x180005fbc  mov     rsi, [rsp+498h+var_460]
0x180005fc1  mov     r14, [rsp+498h+var_458]
0x180005fc6  mov     edi, [rsp+498h+var_468]
0x180005fca  mov     rax, [rsp+498h+var_438]
0x180005fcf  test    rax, rax
0x180005fd2  jnz     short loc_180005FDB
0x180005fd4  mov     ebx, 8007000Eh
0x180005fd9  jmp     short loc_180006021
0x180005fdb  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180005fdf  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180005fe4  mov     r9d, edi; cbMultiByte
0x180005fe7  mov     r8, r14; lpMultiByteStr
0x180005fea  xor     edx, edx; dwFlags
0x180005fec  lea     ecx, [rdx+3]; CodePage
0x180005fef  call    cs:__imp_MultiByteToWideChar
0x180005ff5  test    eax, eax
0x180005ff7  jz      loc_180005F1B
0x180005ffd  mov     ecx, eax
0x180005fff  mov     rax, [rsp+498h+var_438]
0x180006004  mov     [rax+rcx*2], bx
0x180006008  mov     r8d, [rsp+498h+arg_20]; int
0x180006010  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180006015  lea     rcx, [rsp+498h+var_450]; this
0x18000601a  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000601f  mov     ebx, eax
0x180006021  mov     rcx, rsi; hLibModule
0x180006024  call    cs:__imp_FreeLibrary
0x18000602a  nop
0x18000602b  lea     rax, [rsp+498h+var_430]
0x180006030  cmp     [rsp+498h+var_438], rax
0x180006035  jz      short loc_180006042
0x180006037  lea     rcx, [rsp+498h+var_438]
0x18000603c  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180006041  nop
0x180006042  mov     eax, ebx
0x180006044  mov     rcx, [rsp+498h+var_28]
0x18000604c  xor     rcx, rsp; StackCookie
0x18000604f  call    __security_check_cookie
0x180006054  mov     rbx, [rsp+498h+arg_0]
0x18000605c  add     rsp, 480h
0x180006063  pop     r14
0x180006065  pop     rdi
0x180006066  pop     rsi
0x180006067  retn
0x180006068  mov     ecx, 80070057h; int
0x18000606d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
