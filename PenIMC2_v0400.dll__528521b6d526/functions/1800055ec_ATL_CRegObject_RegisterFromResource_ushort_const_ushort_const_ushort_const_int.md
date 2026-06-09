# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800055ec`
- end: `0x1800057bd`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `465`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800057c0`

## callees

- `0x1800037a4`
- `0x1800037c8`
- `0x1800037f4`
- `0x180004484`
- `0x180005454`
- `0x1800055ec`
- `0x18000cdb0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180005772`
- `KERNEL32!FreeLibrary` at `0x180005772`
- `KERNEL32!MultiByteToWideChar` at `0x180005738`
- `KERNEL32!MultiByteToWideChar` at `0x180005738`
- `KERNEL32!SizeofResource` at `0x1800056b0`
- `KERNEL32!SizeofResource` at `0x1800056b0`
- `KERNEL32!LoadResource` at `0x180005697`
- `KERNEL32!LoadResource` at `0x180005697`
- `KERNEL32!FindResourceW` at `0x180005679`
- `KERNEL32!FindResourceW` at `0x180005679`
- `KERNEL32!LoadLibraryExW` at `0x180005635`
- `KERNEL32!LoadLibraryExW` at `0x180005651`
- `KERNEL32!LoadLibraryExW` at `0x180005635`
- `KERNEL32!LoadLibraryExW` at `0x180005651`

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
  HMODULE Library; // rsi
  unsigned int Error; // ebx
  HRSRC ResourceW; // rax
  HRSRC v11; // rbx
  unsigned int v12; // eax
  const CHAR *Resource; // r14
  DWORD cchWideChar; // ebx
  DWORD v15; // eax
  int v16; // eax
  HMODULE v18; // [rsp+38h] [rbp-470h]
  _QWORD v19[3]; // [rsp+48h] [rbp-460h] BYREF
  LPWSTR lpWideCharStr; // [rsp+60h] [rbp-448h] BYREF
  _BYTE v21[1032]; // [rsp+68h] [rbp-440h] BYREF

  v19[2] = 0;
  v19[1] = this;
  v19[0] = 0;
  lpWideCharStr = 0;
  Library = LoadLibraryExW(a2, 0, 0x60u);
  v18 = Library;
  if ( !Library )
  {
    Library = LoadLibraryExW(a2, 0, 2u);
    v18 = Library;
    if ( !Library )
    {
      Error = ATL::AtlHresultFromLastError();
      goto LABEL_20;
    }
  }
  ResourceW = FindResourceW(Library, a3, a4);
  v11 = ResourceW;
  if ( !ResourceW )
    goto LABEL_5;
  Resource = (const CHAR *)LoadResource(Library, ResourceW);
  if ( !Resource )
    goto LABEL_5;
  cchWideChar = SizeofResource(Library, v11);
  v15 = cchWideChar + 1;
  if ( cchWideChar + 1 < cchWideChar )
    goto LABEL_8;
  try
  {
    if ( cchWideChar == -1 )
      goto LABEL_13;
    if ( 0xFFFFFFFFFFFFFFFFuLL / v15 < 2 )
      ATL::AtlThrowImpl(-2147024362);
    if ( 2 * (unsigned __int64)v15 <= 0x400 )
LABEL_13:
      lpWideCharStr = (LPWSTR)v21;
    else
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpWideCharStr, 2LL * v15);
  }
  catch ( ... )
  {
    Library = v18;
  }
  if ( !lpWideCharStr )
  {
LABEL_8:
    Error = -2147024882;
    goto LABEL_18;
  }
  v16 = MultiByteToWideChar(3u, 0, Resource, cchWideChar, lpWideCharStr, cchWideChar);
  if ( v16 )
  {
    lpWideCharStr[v16] = 0;
    v12 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v19, lpWideCharStr, a5);
  }
  else
  {
LABEL_5:
    v12 = ATL::AtlHresultFromLastError();
  }
  Error = v12;
LABEL_18:
  if ( Library )
    FreeLibrary(Library);
LABEL_20:
  if ( lpWideCharStr != (LPWSTR)v21 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpWideCharStr);
  return Error;
}

```

## disassembly

```asm
0x1800055ec  push    rbx
0x1800055ee  push    rsi
0x1800055ef  push    rdi
0x1800055f0  push    r14
0x1800055f2  push    r15
0x1800055f4  sub     rsp, 480h
0x1800055fb  mov     rax, cs:__security_cookie
0x180005602  xor     rax, rsp
0x180005605  mov     [rsp+4A8h+var_38], rax
0x18000560d  mov     r15, r9
0x180005610  mov     r14, r8
0x180005613  mov     rbx, rdx
0x180005616  xor     edi, edi
0x180005618  mov     [rsp+4A8h+var_450], rdi
0x18000561d  mov     [rsp+4A8h+var_458], rcx
0x180005622  mov     [rsp+4A8h+var_460], rdi
0x180005627  mov     [rsp+4A8h+var_448], rdi
0x18000562c  xor     edx, edx; hFile
0x18000562e  lea     r8d, [rdi+60h]; dwFlags
0x180005632  mov     rcx, rbx; lpLibFileName
0x180005635  call    cs:__imp_LoadLibraryExW
0x18000563b  mov     rsi, rax
0x18000563e  mov     [rsp+4A8h+var_470], rax
0x180005643  test    rax, rax
0x180005646  jnz     short loc_180005670
0x180005648  xor     edx, edx; hFile
0x18000564a  lea     r8d, [rdi+2]; dwFlags
0x18000564e  mov     rcx, rbx; lpLibFileName
0x180005651  call    cs:__imp_LoadLibraryExW
0x180005657  mov     rsi, rax
0x18000565a  mov     [rsp+4A8h+var_470], rax
0x18000565f  test    rax, rax
0x180005662  jnz     short loc_180005670
0x180005664  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005669  mov     ebx, eax
0x18000566b  jmp     loc_180005779
0x180005670  mov     r8, r15; lpType
0x180005673  mov     rdx, r14; lpName
0x180005676  mov     rcx, rsi; hModule
0x180005679  call    cs:__imp_FindResourceW
0x18000567f  mov     rbx, rax
0x180005682  test    rax, rax
0x180005685  jnz     short loc_180005691
0x180005687  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000568c  jmp     loc_180005768
0x180005691  mov     rdx, rbx; hResInfo
0x180005694  mov     rcx, rsi; hModule
0x180005697  call    cs:__imp_LoadResource
0x18000569d  mov     r14, rax
0x1800056a0  mov     [rsp+4A8h+var_468], rax
0x1800056a5  test    rax, rax
0x1800056a8  jz      short loc_180005687
0x1800056aa  mov     rdx, rbx; hResInfo
0x1800056ad  mov     rcx, rsi; hModule
0x1800056b0  call    cs:__imp_SizeofResource
0x1800056b6  mov     ebx, eax
0x1800056b8  mov     [rsp+4A8h+var_478], eax
0x1800056bc  inc     eax
0x1800056be  cmp     eax, ebx
0x1800056c0  jnb     short loc_1800056CC
0x1800056c2  mov     ebx, 8007000Eh
0x1800056c7  jmp     loc_18000576A
0x1800056cc  mov     ecx, eax
0x1800056ce  test    eax, eax
0x1800056d0  jz      short loc_1800056FE
0x1800056d2  xor     edx, edx
0x1800056d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800056d8  div     rcx
0x1800056db  cmp     rax, 2
0x1800056df  jb      loc_1800057B1
0x1800056e5  lea     rdx, [rcx+rcx]
0x1800056e9  cmp     rdx, 400h
0x1800056f0  jbe     short loc_1800056FE
0x1800056f2  lea     rcx, [rsp+4A8h+var_448]
0x1800056f7  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800056fc  jmp     short loc_180005708
0x1800056fe  lea     rax, [rsp+4A8h+var_440]
0x180005703  mov     [rsp+4A8h+var_448], rax
0x180005708  jmp     short loc_18000571A
0x18000570a  xor     edi, edi
0x18000570c  mov     rsi, [rsp+4A8h+var_470]
0x180005711  mov     r14, [rsp+4A8h+var_468]
0x180005716  mov     ebx, [rsp+4A8h+var_478]
0x18000571a  mov     rax, [rsp+4A8h+var_448]
0x18000571f  test    rax, rax
0x180005722  jz      short loc_1800056C2
0x180005724  mov     [rsp+4A8h+cchWideChar], ebx; cchWideChar
0x180005728  mov     [rsp+4A8h+lpWideCharStr], rax; lpWideCharStr
0x18000572d  mov     r9d, ebx; cbMultiByte
0x180005730  mov     r8, r14; lpMultiByteStr
0x180005733  xor     edx, edx; dwFlags
0x180005735  lea     ecx, [rdx+3]; CodePage
0x180005738  call    cs:__imp_MultiByteToWideChar
0x18000573e  test    eax, eax
0x180005740  jz      loc_180005687
0x180005746  mov     ecx, eax
0x180005748  mov     rax, [rsp+4A8h+var_448]
0x18000574d  mov     [rax+rcx*2], di
0x180005751  mov     r8d, [rsp+4A8h+arg_20]; int
0x180005759  mov     rdx, [rsp+4A8h+var_448]; unsigned __int16 *
0x18000575e  lea     rcx, [rsp+4A8h+var_460]; this
0x180005763  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180005768  mov     ebx, eax
0x18000576a  test    rsi, rsi
0x18000576d  jz      short loc_180005779
0x18000576f  mov     rcx, rsi; hLibModule
0x180005772  call    cs:__imp_FreeLibrary
0x180005778  nop
0x180005779  lea     rax, [rsp+4A8h+var_440]
0x18000577e  cmp     [rsp+4A8h+var_448], rax
0x180005783  jz      short loc_180005790
0x180005785  lea     rcx, [rsp+4A8h+var_448]
0x18000578a  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000578f  nop
0x180005790  mov     eax, ebx
0x180005792  mov     rcx, [rsp+4A8h+var_38]
0x18000579a  xor     rcx, rsp; StackCookie
0x18000579d  call    __security_check_cookie
0x1800057a2  add     rsp, 480h
0x1800057a9  pop     r15
0x1800057ab  pop     r14
0x1800057ad  pop     rdi
0x1800057ae  pop     rsi
0x1800057af  pop     rbx
0x1800057b0  retn
0x1800057b1  mov     ecx, 80070216h; int
0x1800057b6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
