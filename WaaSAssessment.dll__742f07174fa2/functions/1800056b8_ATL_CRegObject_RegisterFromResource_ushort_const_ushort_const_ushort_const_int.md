# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800056b8`
- end: `0x180005894`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `476`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000637c`
- `0x18000669c`

## callees

- `0x180003c78`
- `0x180003eb4`
- `0x180004740`
- `0x180004ca4`
- `0x180005528`
- `0x1800056b8`
- `0x180019760`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000572d`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000572d`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180005764`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180005764`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005844`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005844`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005702`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005702`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000574b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000574b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000580f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000580f`

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
0x1800056b8  mov     [rsp+arg_0], rbx
0x1800056bd  push    rsi
0x1800056be  push    rdi
0x1800056bf  push    r14
0x1800056c1  sub     rsp, 480h
0x1800056c8  mov     rax, cs:__security_cookie
0x1800056cf  xor     rax, rsp
0x1800056d2  mov     [rsp+498h+var_28], rax
0x1800056da  mov     r14, r9
0x1800056dd  mov     rdi, r8
0x1800056e0  mov     rax, rdx
0x1800056e3  xor     ebx, ebx
0x1800056e5  mov     [rsp+498h+var_440], rbx
0x1800056ea  mov     [rsp+498h+var_448], rcx
0x1800056ef  mov     [rsp+498h+var_450], rbx
0x1800056f4  mov     [rsp+498h+var_438], rbx
0x1800056f9  xor     edx, edx; hFile
0x1800056fb  lea     r8d, [rbx+2]; dwFlags
0x1800056ff  mov     rcx, rax; lpLibFileName
0x180005702  call    cs:__imp_LoadLibraryExW
0x180005708  mov     rsi, rax
0x18000570b  mov     [rsp+498h+var_460], rax
0x180005710  test    rax, rax
0x180005713  jnz     short loc_180005721
0x180005715  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000571a  mov     ebx, eax
0x18000571c  jmp     loc_18000584B
0x180005721  xor     r9d, r9d; wLanguage
0x180005724  mov     r8, rdi; lpName
0x180005727  mov     rdx, r14; lpType
0x18000572a  mov     rcx, rsi; hModule
0x18000572d  call    cs:__imp_FindResourceExW
0x180005733  mov     rdi, rax
0x180005736  test    rax, rax
0x180005739  jnz     short loc_180005745
0x18000573b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005740  jmp     loc_18000583F
0x180005745  mov     rdx, rdi; hResInfo
0x180005748  mov     rcx, rsi; hModule
0x18000574b  call    cs:__imp_LoadResource
0x180005751  mov     r14, rax
0x180005754  mov     [rsp+498h+var_458], rax
0x180005759  test    rax, rax
0x18000575c  jz      short loc_18000573B
0x18000575e  mov     rdx, rdi; hResInfo
0x180005761  mov     rcx, rsi; hModule
0x180005764  call    cs:__imp_SizeofResource
0x18000576a  mov     edi, eax
0x18000576c  mov     [rsp+498h+var_468], eax
0x180005770  inc     eax
0x180005772  cmp     eax, edi
0x180005774  jnb     short loc_180005797
0x180005776  lea     rax, [rsp+498h+var_430]
0x18000577b  cmp     [rsp+498h+var_438], rax
0x180005780  jz      short loc_18000578D
0x180005782  lea     rcx, [rsp+498h+var_438]
0x180005787  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000578c  nop
0x18000578d  mov     eax, 8007000Eh
0x180005792  jmp     loc_180005864
0x180005797  test    eax, eax
0x180005799  jz      short loc_1800057CE
0x18000579b  mov     ecx, eax
0x18000579d  xor     edx, edx
0x18000579f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800057a3  div     rcx
0x1800057a6  cmp     rax, 2
0x1800057aa  jb      loc_180005888
0x1800057b0  lea     rdx, [rcx+rcx]
0x1800057b4  cmp     rdx, 400h
0x1800057bb  jbe     short loc_1800057CE
0x1800057bd  lea     rcx, [rsp+498h+var_438]
0x1800057c2  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800057c7  mov     rax, [rsp+498h+var_438]
0x1800057cc  jmp     short loc_1800057D8
0x1800057ce  lea     rax, [rsp+498h+var_430]
0x1800057d3  mov     [rsp+498h+var_438], rax
0x1800057d8  jmp     short loc_1800057EF
0x1800057da  xor     ebx, ebx
0x1800057dc  mov     rsi, [rsp+498h+var_460]
0x1800057e1  mov     r14, [rsp+498h+var_458]
0x1800057e6  mov     edi, [rsp+498h+var_468]
0x1800057ea  mov     rax, [rsp+498h+var_438]
0x1800057ef  test    rax, rax
0x1800057f2  jnz     short loc_1800057FB
0x1800057f4  mov     ebx, 8007000Eh
0x1800057f9  jmp     short loc_180005841
0x1800057fb  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x1800057ff  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180005804  mov     r9d, edi; cbMultiByte
0x180005807  mov     r8, r14; lpMultiByteStr
0x18000580a  xor     edx, edx; dwFlags
0x18000580c  lea     ecx, [rdx+3]; CodePage
0x18000580f  call    cs:__imp_MultiByteToWideChar
0x180005815  test    eax, eax
0x180005817  jz      loc_18000573B
0x18000581d  mov     ecx, eax
0x18000581f  mov     rax, [rsp+498h+var_438]
0x180005824  mov     [rax+rcx*2], bx
0x180005828  mov     r8d, [rsp+498h+arg_20]; int
0x180005830  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180005835  lea     rcx, [rsp+498h+var_450]; this
0x18000583a  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000583f  mov     ebx, eax
0x180005841  mov     rcx, rsi; hLibModule
0x180005844  call    cs:__imp_FreeLibrary
0x18000584a  nop
0x18000584b  lea     rax, [rsp+498h+var_430]
0x180005850  cmp     [rsp+498h+var_438], rax
0x180005855  jz      short loc_180005862
0x180005857  lea     rcx, [rsp+498h+var_438]
0x18000585c  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180005861  nop
0x180005862  mov     eax, ebx
0x180005864  mov     rcx, [rsp+498h+var_28]
0x18000586c  xor     rcx, rsp; StackCookie
0x18000586f  call    __security_check_cookie
0x180005874  mov     rbx, [rsp+498h+arg_0]
0x18000587c  add     rsp, 480h
0x180005883  pop     r14
0x180005885  pop     rdi
0x180005886  pop     rsi
0x180005887  retn
0x180005888  mov     ecx, 80070057h; int
0x18000588d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
