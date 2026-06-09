# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180004038`
- end: `0x1800041f3`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `443`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180004bac`

## callees

- `0x180002ba8`
- `0x180002cd8`
- `0x180003558`
- `0x180003808`
- `0x180003ea8`
- `0x180004038`
- `0x180005f60`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180004089`
- `KERNEL32!LoadLibraryExW` at `0x180004089`
- `KERNEL32!LoadResource` at `0x1800040cd`
- `KERNEL32!LoadResource` at `0x1800040cd`
- `KERNEL32!FindResourceExW` at `0x1800040af`
- `KERNEL32!FindResourceExW` at `0x1800040af`
- `KERNEL32!MultiByteToWideChar` at `0x180004172`
- `KERNEL32!MultiByteToWideChar` at `0x180004172`
- `KERNEL32!FreeLibrary` at `0x1800041a8`
- `KERNEL32!FreeLibrary` at `0x1800041a8`
- `KERNEL32!SizeofResource` at `0x1800040e1`
- `KERNEL32!SizeofResource` at `0x1800040e1`

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
0x180004038  mov     [rsp-8+arg_0], rbx
0x18000403d  push    rbp
0x18000403e  push    rsi
0x18000403f  push    rdi
0x180004040  lea     rbp, [rsp-360h]
0x180004048  sub     rsp, 460h
0x18000404f  mov     rax, cs:__security_cookie
0x180004056  xor     rax, rsp
0x180004059  mov     [rbp+370h+var_20], rax
0x180004060  mov     rax, rdx
0x180004063  mov     [rsp+470h+var_438], rcx
0x180004068  xor     edx, edx; hFile
0x18000406a  mov     [rsp+470h+var_440], 0
0x180004073  mov     rbx, r8
0x180004076  mov     [rsp+470h+var_430], 0
0x18000407f  mov     rcx, rax; lpLibFileName
0x180004082  mov     rsi, r9
0x180004085  lea     r8d, [rdx+2]; dwFlags
0x180004089  call    cs:__imp_LoadLibraryExW
0x18000408f  mov     rdi, rax
0x180004092  test    rax, rax
0x180004095  jnz     short loc_1800040A3
0x180004097  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000409c  mov     ebx, eax
0x18000409e  jmp     loc_1800041AE
0x1800040a3  xor     r9d, r9d; wLanguage
0x1800040a6  mov     r8, rbx; lpName
0x1800040a9  mov     rdx, rsi; lpType
0x1800040ac  mov     rcx, rdi; hModule
0x1800040af  call    cs:__imp_FindResourceExW
0x1800040b5  mov     rbx, rax
0x1800040b8  test    rax, rax
0x1800040bb  jnz     short loc_1800040C7
0x1800040bd  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800040c2  jmp     loc_1800041A3
0x1800040c7  mov     rdx, rbx; hResInfo
0x1800040ca  mov     rcx, rdi; hModule
0x1800040cd  call    cs:__imp_LoadResource
0x1800040d3  mov     rsi, rax
0x1800040d6  test    rax, rax
0x1800040d9  jz      short loc_1800040BD
0x1800040db  mov     rdx, rbx; hResInfo
0x1800040de  mov     rcx, rdi; hModule
0x1800040e1  call    cs:__imp_SizeofResource
0x1800040e7  mov     ebx, eax
0x1800040e9  lea     ecx, [rax+1]
0x1800040ec  cmp     ecx, eax
0x1800040ee  jnb     short loc_180004110
0x1800040f0  lea     rax, [rsp+470h+var_428]
0x1800040f5  cmp     [rsp+470h+var_430], rax
0x1800040fa  jz      short loc_180004106
0x1800040fc  lea     rcx, [rsp+470h+var_430]
0x180004101  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004106  mov     eax, 8007000Eh
0x18000410b  jmp     loc_1800041C6
0x180004110  test    ecx, ecx
0x180004112  jz      short loc_180004148
0x180004114  xor     edx, edx
0x180004116  mov     r8d, ecx
0x180004119  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000411d  div     r8
0x180004120  cmp     rax, 2
0x180004124  jb      loc_1800041E8
0x18000412a  lea     rdx, [rcx+rcx]
0x18000412e  cmp     rdx, 400h
0x180004135  jbe     short loc_180004148
0x180004137  lea     rcx, [rsp+470h+var_430]
0x18000413c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004141  mov     rax, [rsp+470h+var_430]
0x180004146  jmp     short loc_180004152
0x180004148  lea     rax, [rsp+470h+var_428]
0x18000414d  mov     [rsp+470h+var_430], rax
0x180004152  test    rax, rax
0x180004155  jnz     short loc_18000415E
0x180004157  mov     ebx, 8007000Eh
0x18000415c  jmp     short loc_1800041A5
0x18000415e  xor     edx, edx; dwFlags
0x180004160  mov     [rsp+470h+cchWideChar], ebx; cchWideChar
0x180004164  mov     r9d, ebx; cbMultiByte
0x180004167  mov     [rsp+470h+lpWideCharStr], rax; lpWideCharStr
0x18000416c  mov     r8, rsi; lpMultiByteStr
0x18000416f  lea     ecx, [rdx+3]; CodePage
0x180004172  call    cs:__imp_MultiByteToWideChar
0x180004178  test    eax, eax
0x18000417a  jz      loc_1800040BD
0x180004180  mov     r8d, [rbp+370h+arg_20]; int
0x180004187  xor     ecx, ecx
0x180004189  mov     edx, eax
0x18000418b  mov     rax, [rsp+470h+var_430]
0x180004190  mov     [rax+rdx*2], cx
0x180004194  lea     rcx, [rsp+470h+var_440]; this
0x180004199  mov     rdx, [rsp+470h+var_430]; unsigned __int16 *
0x18000419e  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800041a3  mov     ebx, eax
0x1800041a5  mov     rcx, rdi; hLibModule
0x1800041a8  call    cs:__imp_FreeLibrary
0x1800041ae  lea     rax, [rsp+470h+var_428]
0x1800041b3  cmp     [rsp+470h+var_430], rax
0x1800041b8  jz      short loc_1800041C4
0x1800041ba  lea     rcx, [rsp+470h+var_430]
0x1800041bf  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800041c4  mov     eax, ebx
0x1800041c6  mov     rcx, [rbp+370h+var_20]
0x1800041cd  xor     rcx, rsp; StackCookie
0x1800041d0  call    __security_check_cookie
0x1800041d5  mov     rbx, [rsp+470h+arg_0]
0x1800041dd  add     rsp, 460h
0x1800041e4  pop     rdi
0x1800041e5  pop     rsi
0x1800041e6  pop     rbp
0x1800041e7  retn
0x1800041e8  mov     ecx, 80070057h; int
0x1800041ed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
