# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000930c`
- end: `0x1800094e6`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `474`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000adb4`

## callees

- `0x180004180`
- `0x180006f4c`
- `0x18000707c`
- `0x1800070b8`
- `0x1800078cc`
- `0x18000917c`
- `0x18000930c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009353`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009353`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800093b6`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800093b6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180009496`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180009496`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000937f`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000937f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000939d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000939d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180009461`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180009461`

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
0x18000930c  mov     [rsp+arg_0], rbx
0x180009311  push    rsi
0x180009312  push    rdi
0x180009313  push    r14
0x180009315  sub     rsp, 480h
0x18000931c  mov     rax, cs:__security_cookie
0x180009323  xor     rax, rsp
0x180009326  mov     [rsp+498h+var_28], rax
0x18000932e  mov     rsi, r9
0x180009331  mov     rax, rdx
0x180009334  xor     ebx, ebx
0x180009336  mov     [rsp+498h+var_440], rbx
0x18000933b  mov     [rsp+498h+var_448], rcx
0x180009340  mov     [rsp+498h+var_450], rbx
0x180009345  mov     [rsp+498h+var_438], rbx
0x18000934a  xor     edx, edx; hFile
0x18000934c  lea     r8d, [rbx+2]; dwFlags
0x180009350  mov     rcx, rax; lpLibFileName
0x180009353  call    cs:__imp_LoadLibraryExW
0x180009359  mov     rdi, rax
0x18000935c  mov     [rsp+498h+var_460], rax
0x180009361  test    rax, rax
0x180009364  jnz     short loc_180009372
0x180009366  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000936b  mov     ebx, eax
0x18000936d  jmp     loc_18000949D
0x180009372  xor     r9d, r9d; wLanguage
0x180009375  lea     r8d, [r9+65h]; lpName
0x180009379  mov     rdx, rsi; lpType
0x18000937c  mov     rcx, rdi; hModule
0x18000937f  call    cs:__imp_FindResourceExW
0x180009385  mov     rsi, rax
0x180009388  test    rax, rax
0x18000938b  jnz     short loc_180009397
0x18000938d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180009392  jmp     loc_180009491
0x180009397  mov     rdx, rsi; hResInfo
0x18000939a  mov     rcx, rdi; hModule
0x18000939d  call    cs:__imp_LoadResource
0x1800093a3  mov     r14, rax
0x1800093a6  mov     [rsp+498h+var_458], rax
0x1800093ab  test    rax, rax
0x1800093ae  jz      short loc_18000938D
0x1800093b0  mov     rdx, rsi; hResInfo
0x1800093b3  mov     rcx, rdi; hModule
0x1800093b6  call    cs:__imp_SizeofResource
0x1800093bc  mov     esi, eax
0x1800093be  mov     [rsp+498h+var_468], eax
0x1800093c2  inc     eax
0x1800093c4  cmp     eax, esi
0x1800093c6  jnb     short loc_1800093E9
0x1800093c8  lea     rax, [rsp+498h+var_430]
0x1800093cd  cmp     [rsp+498h+var_438], rax
0x1800093d2  jz      short loc_1800093DF
0x1800093d4  lea     rcx, [rsp+498h+var_438]
0x1800093d9  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800093de  nop
0x1800093df  mov     eax, 8007000Eh
0x1800093e4  jmp     loc_1800094B6
0x1800093e9  test    eax, eax
0x1800093eb  jz      short loc_180009420
0x1800093ed  mov     ecx, eax
0x1800093ef  xor     edx, edx
0x1800093f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800093f5  div     rcx
0x1800093f8  cmp     rax, 2
0x1800093fc  jb      loc_1800094DA
0x180009402  lea     rdx, [rcx+rcx]
0x180009406  cmp     rdx, 400h
0x18000940d  jbe     short loc_180009420
0x18000940f  lea     rcx, [rsp+498h+var_438]
0x180009414  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180009419  mov     rax, [rsp+498h+var_438]
0x18000941e  jmp     short loc_18000942A
0x180009420  lea     rax, [rsp+498h+var_430]
0x180009425  mov     [rsp+498h+var_438], rax
0x18000942a  jmp     short loc_180009441
0x18000942c  xor     ebx, ebx
0x18000942e  mov     rdi, [rsp+498h+var_460]
0x180009433  mov     r14, [rsp+498h+var_458]
0x180009438  mov     esi, [rsp+498h+var_468]
0x18000943c  mov     rax, [rsp+498h+var_438]
0x180009441  test    rax, rax
0x180009444  jnz     short loc_18000944D
0x180009446  mov     ebx, 8007000Eh
0x18000944b  jmp     short loc_180009493
0x18000944d  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x180009451  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180009456  mov     r9d, esi; cbMultiByte
0x180009459  mov     r8, r14; lpMultiByteStr
0x18000945c  xor     edx, edx; dwFlags
0x18000945e  lea     ecx, [rdx+3]; CodePage
0x180009461  call    cs:__imp_MultiByteToWideChar
0x180009467  test    eax, eax
0x180009469  jz      loc_18000938D
0x18000946f  mov     ecx, eax
0x180009471  mov     rax, [rsp+498h+var_438]
0x180009476  mov     [rax+rcx*2], bx
0x18000947a  mov     r8d, [rsp+498h+arg_20]; int
0x180009482  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180009487  lea     rcx, [rsp+498h+var_450]; this
0x18000948c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180009491  mov     ebx, eax
0x180009493  mov     rcx, rdi; hLibModule
0x180009496  call    cs:__imp_FreeLibrary
0x18000949c  nop
0x18000949d  lea     rax, [rsp+498h+var_430]
0x1800094a2  cmp     [rsp+498h+var_438], rax
0x1800094a7  jz      short loc_1800094B4
0x1800094a9  lea     rcx, [rsp+498h+var_438]
0x1800094ae  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800094b3  nop
0x1800094b4  mov     eax, ebx
0x1800094b6  mov     rcx, [rsp+498h+var_28]
0x1800094be  xor     rcx, rsp; StackCookie
0x1800094c1  call    __security_check_cookie
0x1800094c6  mov     rbx, [rsp+498h+arg_0]
0x1800094ce  add     rsp, 480h
0x1800094d5  pop     r14
0x1800094d7  pop     rdi
0x1800094d8  pop     rsi
0x1800094d9  retn
0x1800094da  mov     ecx, 80070057h; int
0x1800094df  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
