# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180005538`
- end: `0x18000572b`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `499`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000572c`

## callees

- `0x180001f68`
- `0x180002238`
- `0x180003b90`
- `0x180003bb0`
- `0x180005394`
- `0x180005538`
- `0x180007700`
- `0x180024220`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800056d8`
- `KERNEL32!FreeLibrary` at `0x1800056d8`
- `KERNEL32!MultiByteToWideChar` at `0x18000569e`
- `KERNEL32!MultiByteToWideChar` at `0x18000569e`
- `KERNEL32!SizeofResource` at `0x18000560e`
- `KERNEL32!SizeofResource` at `0x18000560e`
- `KERNEL32!LoadResource` at `0x1800055f5`
- `KERNEL32!LoadResource` at `0x1800055f5`
- `KERNEL32!FindResourceW` at `0x1800055d7`
- `KERNEL32!FindResourceW` at `0x1800055d7`
- `KERNEL32!LoadLibraryExW` at `0x180005591`
- `KERNEL32!LoadLibraryExW` at `0x1800055ad`
- `KERNEL32!LoadLibraryExW` at `0x180005591`
- `KERNEL32!LoadLibraryExW` at `0x1800055ad`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        const WCHAR *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rsi
  unsigned int Error; // ebx
  HRSRC ResourceW; // rax
  HRSRC v10; // rbx
  unsigned int v11; // eax
  const CHAR *Resource; // r14
  DWORD cchWideChar; // ebx
  DWORD v14; // eax
  int v15; // eax
  HMODULE v17; // [rsp+38h] [rbp-460h]
  LPCWSTR v18[3]; // [rsp+48h] [rbp-450h] BYREF
  LPWSTR lpWideCharStr[130]; // [rsp+60h] [rbp-438h] BYREF

  v18[2] = 0;
  v18[1] = this;
  v18[0] = 0;
  memset(lpWideCharStr, 0, 0x408u);
  lpWideCharStr[0] = 0;
  Library = LoadLibraryExW(a2, 0, 0x60u);
  v17 = Library;
  if ( !Library )
  {
    Library = LoadLibraryExW(a2, 0, 2u);
    v17 = Library;
    if ( !Library )
    {
      Error = ATL::AtlHresultFromLastError();
      goto LABEL_20;
    }
  }
  ResourceW = FindResourceW(Library, (LPCWSTR)0x64, a4);
  v10 = ResourceW;
  if ( !ResourceW )
    goto LABEL_5;
  Resource = (const CHAR *)LoadResource(Library, ResourceW);
  if ( !Resource )
    goto LABEL_5;
  cchWideChar = SizeofResource(Library, v10);
  v14 = cchWideChar + 1;
  if ( cchWideChar + 1 < cchWideChar )
    goto LABEL_8;
  try
  {
    if ( cchWideChar == -1 )
      goto LABEL_13;
    if ( 0xFFFFFFFFFFFFFFFFuLL / v14 < 2 )
    {
      _mm_lfence();
      ATL::AtlThrowImpl(-2147024362);
    }
    if ( 2 * (unsigned __int64)v14 <= 0x400 )
    {
LABEL_13:
      lpWideCharStr[0] = (LPWSTR)&lpWideCharStr[1];
    }
    else
    {
      _mm_lfence();
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(lpWideCharStr, 2LL * v14);
    }
  }
  catch ( ... )
  {
    Library = v17;
  }
  if ( !lpWideCharStr[0] )
  {
LABEL_8:
    Error = -2147024882;
    goto LABEL_18;
  }
  _mm_lfence();
  v15 = MultiByteToWideChar(3u, 0, Resource, cchWideChar, lpWideCharStr[0], cchWideChar);
  if ( v15 )
  {
    lpWideCharStr[0][v15] = 0;
    v11 = ATL::CRegParser::RegisterBuffer(v18, lpWideCharStr[0], a5);
  }
  else
  {
LABEL_5:
    v11 = ATL::AtlHresultFromLastError();
  }
  Error = v11;
LABEL_18:
  if ( Library )
    FreeLibrary(Library);
LABEL_20:
  if ( (LPWSTR *)lpWideCharStr[0] != &lpWideCharStr[1] )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)lpWideCharStr);
  return Error;
}

```

## disassembly

```asm
0x180005538  mov     [rsp+arg_0], rbx
0x18000553d  push    rsi
0x18000553e  push    rdi
0x18000553f  push    r14
0x180005541  sub     rsp, 480h
0x180005548  mov     rax, cs:__security_cookie
0x18000554f  xor     rax, rsp
0x180005552  mov     [rsp+498h+var_28], rax
0x18000555a  mov     r14, r9
0x18000555d  mov     rbx, rdx
0x180005560  xor     edi, edi
0x180005562  mov     [rsp+498h+var_440], rdi
0x180005567  mov     [rsp+498h+var_448], rcx
0x18000556c  mov     [rsp+498h+var_450], rdi
0x180005571  xor     edx, edx; Val
0x180005573  mov     r8d, 408h; Size
0x180005579  lea     rcx, [rsp+498h+var_438]; void *
0x18000557e  call    memset
0x180005583  mov     [rsp+498h+var_438], rdi
0x180005588  xor     edx, edx; hFile
0x18000558a  lea     r8d, [rdi+60h]; dwFlags
0x18000558e  mov     rcx, rbx; lpLibFileName
0x180005591  call    cs:__imp_LoadLibraryExW
0x180005597  mov     rsi, rax
0x18000559a  mov     [rsp+498h+var_460], rax
0x18000559f  test    rax, rax
0x1800055a2  jnz     short loc_1800055CC
0x1800055a4  xor     edx, edx; hFile
0x1800055a6  lea     r8d, [rdi+2]; dwFlags
0x1800055aa  mov     rcx, rbx; lpLibFileName
0x1800055ad  call    cs:__imp_LoadLibraryExW
0x1800055b3  mov     rsi, rax
0x1800055b6  mov     [rsp+498h+var_460], rax
0x1800055bb  test    rax, rax
0x1800055be  jnz     short loc_1800055CC
0x1800055c0  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800055c5  mov     ebx, eax
0x1800055c7  jmp     loc_1800056DF
0x1800055cc  mov     r8, r14; lpType
0x1800055cf  mov     edx, 64h ; 'd'; lpName
0x1800055d4  mov     rcx, rsi; hModule
0x1800055d7  call    cs:__imp_FindResourceW
0x1800055dd  mov     rbx, rax
0x1800055e0  test    rax, rax
0x1800055e3  jnz     short loc_1800055EF
0x1800055e5  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800055ea  jmp     loc_1800056CE
0x1800055ef  mov     rdx, rbx; hResInfo
0x1800055f2  mov     rcx, rsi; hModule
0x1800055f5  call    cs:__imp_LoadResource
0x1800055fb  mov     r14, rax
0x1800055fe  mov     [rsp+498h+var_458], rax
0x180005603  test    rax, rax
0x180005606  jz      short loc_1800055E5
0x180005608  mov     rdx, rbx; hResInfo
0x18000560b  mov     rcx, rsi; hModule
0x18000560e  call    cs:__imp_SizeofResource
0x180005614  mov     ebx, eax
0x180005616  mov     [rsp+498h+var_468], eax
0x18000561a  inc     eax
0x18000561c  cmp     eax, ebx
0x18000561e  jnb     short loc_18000562A
0x180005620  mov     ebx, 8007000Eh
0x180005625  jmp     loc_1800056D0
0x18000562a  mov     ecx, eax
0x18000562c  test    eax, eax
0x18000562e  jz      short loc_18000565F
0x180005630  xor     edx, edx
0x180005632  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005636  div     rcx
0x180005639  cmp     rax, 2
0x18000563d  jb      loc_18000571C
0x180005643  lea     rdx, [rcx+rcx]
0x180005647  cmp     rdx, 400h
0x18000564e  jbe     short loc_18000565F
0x180005650  lfence
0x180005653  lea     rcx, [rsp+498h+var_438]
0x180005658  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000565d  jmp     short loc_180005669
0x18000565f  lea     rax, [rsp+498h+var_430]
0x180005664  mov     [rsp+498h+var_438], rax
0x180005669  jmp     short loc_18000567B
0x18000566b  xor     edi, edi
0x18000566d  mov     rsi, [rsp+498h+var_460]
0x180005672  mov     r14, [rsp+498h+var_458]
0x180005677  mov     ebx, [rsp+498h+var_468]
0x18000567b  cmp     [rsp+498h+var_438], rdi
0x180005680  jz      short loc_180005620
0x180005682  lfence
0x180005685  mov     [rsp+498h+cchWideChar], ebx; cchWideChar
0x180005689  mov     rax, [rsp+498h+var_438]
0x18000568e  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180005693  mov     r9d, ebx; cbMultiByte
0x180005696  mov     r8, r14; lpMultiByteStr
0x180005699  xor     edx, edx; dwFlags
0x18000569b  lea     ecx, [rdx+3]; CodePage
0x18000569e  call    cs:__imp_MultiByteToWideChar
0x1800056a4  test    eax, eax
0x1800056a6  jz      loc_1800055E5
0x1800056ac  mov     ecx, eax
0x1800056ae  mov     rax, [rsp+498h+var_438]
0x1800056b3  mov     [rax+rcx*2], di
0x1800056b7  mov     r8d, [rsp+498h+arg_20]; int
0x1800056bf  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x1800056c4  lea     rcx, [rsp+498h+var_450]; this
0x1800056c9  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800056ce  mov     ebx, eax
0x1800056d0  test    rsi, rsi
0x1800056d3  jz      short loc_1800056DF
0x1800056d5  mov     rcx, rsi; hLibModule
0x1800056d8  call    cs:__imp_FreeLibrary
0x1800056de  nop
0x1800056df  lea     rax, [rsp+498h+var_430]
0x1800056e4  cmp     [rsp+498h+var_438], rax
0x1800056e9  jz      short loc_1800056F6
0x1800056eb  lea     rcx, [rsp+498h+var_438]
0x1800056f0  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800056f5  nop
0x1800056f6  mov     eax, ebx
0x1800056f8  mov     rcx, [rsp+498h+var_28]
0x180005700  xor     rcx, rsp; StackCookie
0x180005703  call    __security_check_cookie
0x180005708  mov     rbx, [rsp+498h+arg_0]
0x180005710  add     rsp, 480h
0x180005717  pop     r14
0x180005719  pop     rdi
0x18000571a  pop     rsi
0x18000571b  retn
0x18000571c  lfence
0x18000571f  mov     ecx, 80070216h; int
0x180005724  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
