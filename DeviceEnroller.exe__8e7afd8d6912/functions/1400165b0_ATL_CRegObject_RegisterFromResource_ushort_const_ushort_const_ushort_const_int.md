# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1400165b0`
- end: `0x14001678c`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `476`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14001903c`
- `0x140019364`

## callees

- `0x1400042f0`
- `0x14000e3dc`
- `0x14000e50c`
- `0x14000e548`
- `0x14000f50c`
- `0x140016420`
- `0x1400165b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x14001665c`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x14001665c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400165fa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400165fa`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x140016625`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x140016625`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001673c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001673c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x140016643`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x140016643`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140016707`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140016707`

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
0x1400165b0  mov     [rsp+arg_0], rbx
0x1400165b5  push    rsi
0x1400165b6  push    rdi
0x1400165b7  push    r14
0x1400165b9  sub     rsp, 480h
0x1400165c0  mov     rax, cs:__security_cookie
0x1400165c7  xor     rax, rsp
0x1400165ca  mov     [rsp+498h+var_28], rax
0x1400165d2  mov     r14, r9
0x1400165d5  mov     rdi, r8
0x1400165d8  mov     rax, rdx
0x1400165db  xor     ebx, ebx
0x1400165dd  mov     [rsp+498h+var_440], rbx
0x1400165e2  mov     [rsp+498h+var_448], rcx
0x1400165e7  mov     [rsp+498h+var_450], rbx
0x1400165ec  mov     [rsp+498h+var_438], rbx
0x1400165f1  xor     edx, edx; hFile
0x1400165f3  lea     r8d, [rbx+2]; dwFlags
0x1400165f7  mov     rcx, rax; lpLibFileName
0x1400165fa  call    cs:__imp_LoadLibraryExW
0x140016600  mov     rsi, rax
0x140016603  mov     [rsp+498h+var_460], rax
0x140016608  test    rax, rax
0x14001660b  jnz     short loc_140016619
0x14001660d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140016612  mov     ebx, eax
0x140016614  jmp     loc_140016743
0x140016619  xor     r9d, r9d; wLanguage
0x14001661c  mov     r8, rdi; lpName
0x14001661f  mov     rdx, r14; lpType
0x140016622  mov     rcx, rsi; hModule
0x140016625  call    cs:__imp_FindResourceExW
0x14001662b  mov     rdi, rax
0x14001662e  test    rax, rax
0x140016631  jnz     short loc_14001663D
0x140016633  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140016638  jmp     loc_140016737
0x14001663d  mov     rdx, rdi; hResInfo
0x140016640  mov     rcx, rsi; hModule
0x140016643  call    cs:__imp_LoadResource
0x140016649  mov     r14, rax
0x14001664c  mov     [rsp+498h+var_458], rax
0x140016651  test    rax, rax
0x140016654  jz      short loc_140016633
0x140016656  mov     rdx, rdi; hResInfo
0x140016659  mov     rcx, rsi; hModule
0x14001665c  call    cs:__imp_SizeofResource
0x140016662  mov     edi, eax
0x140016664  mov     [rsp+498h+var_468], eax
0x140016668  inc     eax
0x14001666a  cmp     eax, edi
0x14001666c  jnb     short loc_14001668F
0x14001666e  lea     rax, [rsp+498h+var_430]
0x140016673  cmp     [rsp+498h+var_438], rax
0x140016678  jz      short loc_140016685
0x14001667a  lea     rcx, [rsp+498h+var_438]
0x14001667f  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140016684  nop
0x140016685  mov     eax, 8007000Eh
0x14001668a  jmp     loc_14001675C
0x14001668f  test    eax, eax
0x140016691  jz      short loc_1400166C6
0x140016693  mov     ecx, eax
0x140016695  xor     edx, edx
0x140016697  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001669b  div     rcx
0x14001669e  cmp     rax, 2
0x1400166a2  jb      loc_140016780
0x1400166a8  lea     rdx, [rcx+rcx]
0x1400166ac  cmp     rdx, 400h
0x1400166b3  jbe     short loc_1400166C6
0x1400166b5  lea     rcx, [rsp+498h+var_438]
0x1400166ba  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1400166bf  mov     rax, [rsp+498h+var_438]
0x1400166c4  jmp     short loc_1400166D0
0x1400166c6  lea     rax, [rsp+498h+var_430]
0x1400166cb  mov     [rsp+498h+var_438], rax
0x1400166d0  jmp     short loc_1400166E7
0x1400166d2  xor     ebx, ebx
0x1400166d4  mov     rsi, [rsp+498h+var_460]
0x1400166d9  mov     r14, [rsp+498h+var_458]
0x1400166de  mov     edi, [rsp+498h+var_468]
0x1400166e2  mov     rax, [rsp+498h+var_438]
0x1400166e7  test    rax, rax
0x1400166ea  jnz     short loc_1400166F3
0x1400166ec  mov     ebx, 8007000Eh
0x1400166f1  jmp     short loc_140016739
0x1400166f3  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x1400166f7  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x1400166fc  mov     r9d, edi; cbMultiByte
0x1400166ff  mov     r8, r14; lpMultiByteStr
0x140016702  xor     edx, edx; dwFlags
0x140016704  lea     ecx, [rdx+3]; CodePage
0x140016707  call    cs:__imp_MultiByteToWideChar
0x14001670d  test    eax, eax
0x14001670f  jz      loc_140016633
0x140016715  mov     ecx, eax
0x140016717  mov     rax, [rsp+498h+var_438]
0x14001671c  mov     [rax+rcx*2], bx
0x140016720  mov     r8d, [rsp+498h+arg_20]; int
0x140016728  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x14001672d  lea     rcx, [rsp+498h+var_450]; this
0x140016732  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x140016737  mov     ebx, eax
0x140016739  mov     rcx, rsi; hLibModule
0x14001673c  call    cs:__imp_FreeLibrary
0x140016742  nop
0x140016743  lea     rax, [rsp+498h+var_430]
0x140016748  cmp     [rsp+498h+var_438], rax
0x14001674d  jz      short loc_14001675A
0x14001674f  lea     rcx, [rsp+498h+var_438]
0x140016754  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140016759  nop
0x14001675a  mov     eax, ebx
0x14001675c  mov     rcx, [rsp+498h+var_28]
0x140016764  xor     rcx, rsp; StackCookie
0x140016767  call    __security_check_cookie
0x14001676c  mov     rbx, [rsp+498h+arg_0]
0x140016774  add     rsp, 480h
0x14001677b  pop     r14
0x14001677d  pop     rdi
0x14001677e  pop     rsi
0x14001677f  retn
0x140016780  mov     ecx, 80070057h; int
0x140016785  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
