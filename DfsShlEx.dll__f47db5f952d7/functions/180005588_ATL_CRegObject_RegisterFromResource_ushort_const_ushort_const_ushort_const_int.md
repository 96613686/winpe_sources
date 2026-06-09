# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180005588`
- end: `0x18000575e`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `470`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000633c`
- `0x1800065d0`

## callees

- `0x18000385c`
- `0x180003a98`
- `0x180004328`
- `0x180004a50`
- `0x1800053f8`
- `0x180005588`
- `0x180006d3c`
- `0x18000a9d0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000570e`
- `KERNEL32!FreeLibrary` at `0x18000570e`
- `KERNEL32!SizeofResource` at `0x18000562e`
- `KERNEL32!SizeofResource` at `0x18000562e`
- `KERNEL32!MultiByteToWideChar` at `0x1800056d9`
- `KERNEL32!MultiByteToWideChar` at `0x1800056d9`
- `KERNEL32!FindResourceExW` at `0x1800055f7`
- `KERNEL32!FindResourceExW` at `0x1800055f7`
- `KERNEL32!LoadResource` at `0x180005615`
- `KERNEL32!LoadResource` at `0x180005615`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        const wchar_t *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v8; // rdi
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rsi
  unsigned int v12; // eax
  const CHAR *v13; // r14
  DWORD cchWideChar; // esi
  DWORD v15; // eax
  WCHAR *lpWideCharStr; // rax
  int v18; // eax
  HMODULE v19; // [rsp+38h] [rbp-460h]
  const wchar_t *v20[3]; // [rsp+48h] [rbp-450h] BYREF
  LPWSTR v21; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v22[1032]; // [rsp+68h] [rbp-430h] BYREF

  v20[2] = 0;
  v20[1] = this;
  v20[0] = 0;
  v21 = 0;
  Library = IsolationAwareLoadLibraryExW(a2, (__int64)a2, 2u);
  v8 = Library;
  v19 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_21:
    if ( v21 != (LPWSTR)v22 )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v21);
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
      v12 = ATL::CRegParser::RegisterBuffer(v20, v21, a5);
      goto LABEL_19;
    }
LABEL_4:
    v12 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v12;
    goto LABEL_20;
  }
  if ( v21 != (LPWSTR)v22 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v21);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180005588  mov     [rsp+arg_0], rbx
0x18000558d  push    rsi
0x18000558e  push    rdi
0x18000558f  push    r14
0x180005591  sub     rsp, 480h
0x180005598  mov     rax, cs:__security_cookie
0x18000559f  xor     rax, rsp
0x1800055a2  mov     [rsp+498h+var_28], rax
0x1800055aa  mov     r14, r9
0x1800055ad  mov     rsi, r8
0x1800055b0  xor     ebx, ebx
0x1800055b2  mov     [rsp+498h+var_440], rbx
0x1800055b7  mov     [rsp+498h+var_448], rcx
0x1800055bc  mov     [rsp+498h+var_450], rbx
0x1800055c1  mov     [rsp+498h+var_438], rbx
0x1800055c6  lea     r8d, [rbx+2]
0x1800055ca  mov     rcx, rdx; lpLibFileName
0x1800055cd  call    IsolationAwareLoadLibraryExW
0x1800055d2  mov     rdi, rax
0x1800055d5  mov     [rsp+498h+var_460], rax
0x1800055da  test    rax, rax
0x1800055dd  jnz     short loc_1800055EB
0x1800055df  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800055e4  mov     ebx, eax
0x1800055e6  jmp     loc_180005715
0x1800055eb  xor     r9d, r9d; wLanguage
0x1800055ee  mov     r8, rsi; lpName
0x1800055f1  mov     rdx, r14; lpType
0x1800055f4  mov     rcx, rdi; hModule
0x1800055f7  call    cs:__imp_FindResourceExW
0x1800055fd  mov     rsi, rax
0x180005600  test    rax, rax
0x180005603  jnz     short loc_18000560F
0x180005605  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000560a  jmp     loc_180005709
0x18000560f  mov     rdx, rsi; hResInfo
0x180005612  mov     rcx, rdi; hModule
0x180005615  call    cs:__imp_LoadResource
0x18000561b  mov     r14, rax
0x18000561e  mov     [rsp+498h+var_458], rax
0x180005623  test    rax, rax
0x180005626  jz      short loc_180005605
0x180005628  mov     rdx, rsi; hResInfo
0x18000562b  mov     rcx, rdi; hModule
0x18000562e  call    cs:__imp_SizeofResource
0x180005634  mov     esi, eax
0x180005636  mov     [rsp+498h+var_468], eax
0x18000563a  inc     eax
0x18000563c  cmp     eax, esi
0x18000563e  jnb     short loc_180005661
0x180005640  lea     rax, [rsp+498h+var_430]
0x180005645  cmp     [rsp+498h+var_438], rax
0x18000564a  jz      short loc_180005657
0x18000564c  lea     rcx, [rsp+498h+var_438]
0x180005651  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180005656  nop
0x180005657  mov     eax, 8007000Eh
0x18000565c  jmp     loc_18000572E
0x180005661  test    eax, eax
0x180005663  jz      short loc_180005698
0x180005665  mov     ecx, eax
0x180005667  xor     edx, edx
0x180005669  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000566d  div     rcx
0x180005670  cmp     rax, 2
0x180005674  jb      loc_180005752
0x18000567a  lea     rdx, [rcx+rcx]
0x18000567e  cmp     rdx, 400h
0x180005685  jbe     short loc_180005698
0x180005687  lea     rcx, [rsp+498h+var_438]
0x18000568c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180005691  mov     rax, [rsp+498h+var_438]
0x180005696  jmp     short loc_1800056A2
0x180005698  lea     rax, [rsp+498h+var_430]
0x18000569d  mov     [rsp+498h+var_438], rax
0x1800056a2  jmp     short loc_1800056B9
0x1800056a4  xor     ebx, ebx
0x1800056a6  mov     rdi, [rsp+498h+var_460]
0x1800056ab  mov     r14, [rsp+498h+var_458]
0x1800056b0  mov     esi, [rsp+498h+var_468]
0x1800056b4  mov     rax, [rsp+498h+var_438]
0x1800056b9  test    rax, rax
0x1800056bc  jnz     short loc_1800056C5
0x1800056be  mov     ebx, 8007000Eh
0x1800056c3  jmp     short loc_18000570B
0x1800056c5  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x1800056c9  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x1800056ce  mov     r9d, esi; cbMultiByte
0x1800056d1  mov     r8, r14; lpMultiByteStr
0x1800056d4  xor     edx, edx; dwFlags
0x1800056d6  lea     ecx, [rdx+3]; CodePage
0x1800056d9  call    cs:__imp_MultiByteToWideChar
0x1800056df  test    eax, eax
0x1800056e1  jz      loc_180005605
0x1800056e7  mov     ecx, eax
0x1800056e9  mov     rax, [rsp+498h+var_438]
0x1800056ee  mov     [rax+rcx*2], bx
0x1800056f2  mov     r8d, [rsp+498h+arg_20]; int
0x1800056fa  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x1800056ff  lea     rcx, [rsp+498h+var_450]; this
0x180005704  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180005709  mov     ebx, eax
0x18000570b  mov     rcx, rdi; hLibModule
0x18000570e  call    cs:__imp_FreeLibrary
0x180005714  nop
0x180005715  lea     rax, [rsp+498h+var_430]
0x18000571a  cmp     [rsp+498h+var_438], rax
0x18000571f  jz      short loc_18000572C
0x180005721  lea     rcx, [rsp+498h+var_438]
0x180005726  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000572b  nop
0x18000572c  mov     eax, ebx
0x18000572e  mov     rcx, [rsp+498h+var_28]
0x180005736  xor     rcx, rsp; StackCookie
0x180005739  call    __security_check_cookie
0x18000573e  mov     rbx, [rsp+498h+arg_0]
0x180005746  add     rsp, 480h
0x18000574d  pop     r14
0x18000574f  pop     rdi
0x180005750  pop     rsi
0x180005751  retn
0x180005752  mov     ecx, 80070057h; int
0x180005757  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
