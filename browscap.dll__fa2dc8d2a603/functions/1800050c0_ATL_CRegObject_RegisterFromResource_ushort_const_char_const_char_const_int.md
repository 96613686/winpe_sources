# ATL::CRegObject::RegisterFromResource(ushort const *,char const *,char const *,int)

- ea: `0x1800050c0`
- end: `0x180005402`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBGPEBD1H@Z`
- size: `834`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const char *, const char *, int)`
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180005d94`
- `0x180005eb0`
- `0x1800060d0`
- `0x1800061ec`

## callees

- `0x1800034f8`
- `0x180003714`
- `0x1800037f4`
- `0x180003ea4`
- `0x180004f3c`
- `0x1800050c0`
- `0x180007034`
- `0x18000b640`
- `0x18000b700`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005300`
- `msvcrt!memcpy_s` at `0x180005300`
- `msvcrt!free` at `0x180005287`
- `msvcrt!free` at `0x180005372`
- `msvcrt!free` at `0x18000539d`
- `msvcrt!free` at `0x180005287`
- `msvcrt!free` at `0x180005372`
- `msvcrt!free` at `0x18000539d`
- `msvcrt!malloc` at `0x180005194`
- `msvcrt!malloc` at `0x180005194`
- `KERNEL32!FreeLibrary` at `0x18000534f`
- `KERNEL32!FreeLibrary` at `0x18000534f`
- `KERNEL32!LoadLibraryExA` at `0x1800051f5`
- `KERNEL32!LoadLibraryExA` at `0x1800051f5`
- `KERNEL32!WideCharToMultiByte` at `0x1800051de`
- `KERNEL32!WideCharToMultiByte` at `0x1800051de`
- `KERNEL32!SizeofResource` at `0x180005255`
- `KERNEL32!SizeofResource` at `0x180005255`
- `KERNEL32!LoadResource` at `0x18000523d`
- `KERNEL32!LoadResource` at `0x18000523d`
- `KERNEL32!FindResourceExA` at `0x18000521f`
- `KERNEL32!FindResourceExA` at `0x18000521f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const char *a3,
        const char *a4,
        int a5)
{
  _QWORD *v8; // rbx
  __int64 v9; // rax
  __int64 cbMultiByte; // r14
  unsigned __int64 v11; // rax
  void *v12; // rsp
  CHAR *lpMultiByteStr; // rsi
  _QWORD *v14; // rax
  HMODULE Library; // rax
  HMODULE v16; // r14
  unsigned int v17; // esi
  HRSRC Resource; // rax
  HRSRC v19; // r15
  unsigned int Error; // eax
  HGLOBAL v21; // rsi
  DWORD v22; // eax
  rsize_t v23; // r15
  unsigned int v24; // eax
  void *v25; // rcx
  _BYTE *v26; // rcx
  errno_t v27; // eax
  void *v28; // rcx
  void *v30; // rcx
  CHAR MultiByteStr[4]; // [rsp+40h] [rbp+0h] BYREF
  _QWORD *v32; // [rsp+48h] [rbp+8h]
  HMODULE v33; // [rsp+50h] [rbp+10h]
  HGLOBAL v34; // [rsp+58h] [rbp+18h]
  _QWORD v35[2]; // [rsp+60h] [rbp+20h] BYREF
  void *Destination; // [rsp+70h] [rbp+30h] BYREF
  _BYTE v37[1032]; // [rsp+78h] [rbp+38h] BYREF

  v8 = 0;
  v32 = 0;
  v35[1] = this;
  v35[0] = 0;
  Destination = 0;
  if ( !a2 )
    goto LABEL_47;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  cbMultiByte = 2LL * ((int)v9 + 1);
  if ( (unsigned __int64)(cbMultiByte + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_47;
  if ( (int)cbMultiByte <= 1024
    && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(
         (ATL::_ATL_SAFE_ALLOCA_IMPL *)(int)cbMultiByte,
         (unsigned __int64)a2) )
  {
    v11 = (int)cbMultiByte + 15LL;
    if ( v11 < (int)cbMultiByte )
      v11 = 0xFFFFFFFFFFFFFF0LL;
    v12 = alloca(v11 & 0xFFFFFFFFFFFFFFF0uLL);
    lpMultiByteStr = MultiByteStr;
  }
  else
  {
    if ( (unsigned __int64)~(__int64)(int)cbMultiByte < 0x10 )
      goto LABEL_55;
    v14 = malloc((int)cbMultiByte + 16LL);
    if ( v14 )
    {
      *v14 = 0;
      v8 = v14;
      v32 = v14;
      lpMultiByteStr = (CHAR *)(v14 + 2);
    }
    else
    {
      lpMultiByteStr = 0;
    }
  }
  if ( !lpMultiByteStr || (*lpMultiByteStr = 0, !WideCharToMultiByte(3u, 0, a2, -1, lpMultiByteStr, cbMultiByte, 0, 0)) )
  {
LABEL_47:
    if ( Destination != v37 )
      ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(&Destination);
    while ( v8 )
    {
      v30 = v8;
      v8 = (_QWORD *)*v8;
      free(v30);
    }
    return 2147942414LL;
  }
  Library = LoadLibraryExA(lpMultiByteStr, 0, 2u);
  v16 = Library;
  v33 = Library;
  if ( Library )
  {
    Resource = FindResourceExA(Library, a4, a3, 0);
    v19 = Resource;
    if ( !Resource || (v21 = LoadResource(v16, Resource), (v34 = v21) == 0) )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_40:
      v17 = Error;
      goto LABEL_41;
    }
    v22 = SizeofResource(v16, v19);
    v23 = v22;
    *(_DWORD *)MultiByteStr = v23;
    v24 = v22 + 1;
    if ( v24 < (unsigned int)v23 )
    {
      if ( Destination != v37 )
        ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(&Destination);
      while ( v8 )
      {
        v25 = v8;
        v8 = (_QWORD *)*v8;
        free(v25);
      }
      return 2147942414LL;
    }
    try
    {
      if ( !v24 )
        goto LABEL_31;
      if ( !(0xFFFFFFFFFFFFFFFFuLL / v24) )
        ATL::AtlThrowImpl(-2147024809);
      if ( v24 > 0x400uLL )
      {
        ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::AllocateHeap(&Destination, v24);
        v26 = Destination;
      }
      else
      {
LABEL_31:
        v26 = v37;
        Destination = v37;
      }
    }
    catch ( ... )
    {
      v8 = v32;
      v16 = v33;
      v21 = v34;
      v23 = *(unsigned int *)MultiByteStr;
      v26 = Destination;
    }
    if ( !v26 )
    {
      v17 = -2147024882;
LABEL_41:
      FreeLibrary(v16);
      goto LABEL_42;
    }
    v27 = memcpy_s(v26, v23, v21, v23);
    if ( !v27 )
    {
LABEL_39:
      *((_BYTE *)Destination + v23) = 0;
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v35, (char *)Destination, a5);
      goto LABEL_40;
    }
    if ( v27 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v27 != 22 && v27 != 34 )
    {
      if ( v27 != 80 )
        ATL::AtlThrowImpl(-2147467259);
      goto LABEL_39;
    }
LABEL_55:
    ATL::AtlThrowImpl(-2147024809);
  }
  v17 = ATL::AtlHresultFromLastError();
LABEL_42:
  if ( Destination != v37 )
    ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(&Destination);
  while ( v8 )
  {
    v28 = v8;
    v8 = (_QWORD *)*v8;
    free(v28);
  }
  return v17;
}

```

## disassembly

```asm
0x1800050c0  push    rbp
0x1800050c2  push    rsi
0x1800050c3  push    rdi
0x1800050c4  push    r12
0x1800050c6  push    r13
0x1800050c8  push    r14
0x1800050ca  push    r15
0x1800050cc  sub     rsp, 490h
0x1800050d3  lea     rbp, [rsp+40h]
0x1800050d8  mov     [rbp+480h+arg_0], rbx
0x1800050df  mov     rax, cs:__security_cookie
0x1800050e6  xor     rax, rbp
0x1800050e9  mov     [rbp+480h+var_40], rax
0x1800050f0  mov     r13, r9
0x1800050f3  mov     r12, r8
0x1800050f6  mov     r15, rdx
0x1800050f9  xor     edi, edi
0x1800050fb  mov     ebx, edi
0x1800050fd  mov     [rbp+480h+var_478], rbx
0x180005101  mov     [rbp+480h+var_458], rcx
0x180005105  mov     [rbp+480h+var_460], rdi
0x180005109  mov     [rbp+480h+Destination], rdi
0x18000510d  test    rdx, rdx
0x180005110  jz      loc_180005381
0x180005116  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000511a  inc     rax
0x18000511d  cmp     [rdx+rax*2], di
0x180005121  jnz     short loc_18000511A
0x180005123  inc     eax
0x180005125  movsxd  rcx, eax
0x180005128  lea     r14, [rcx+rcx]
0x18000512c  mov     eax, 80000000h
0x180005131  add     rax, r14
0x180005134  mov     ecx, 0FFFFFFFFh
0x180005139  cmp     rax, rcx
0x18000513c  ja      loc_180005381
0x180005142  movsxd  rsi, r14d
0x180005145  cmp     r14d, 400h
0x18000514c  jg      short loc_180005180
0x18000514e  mov     rcx, rsi; this
0x180005151  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180005156  test    al, al
0x180005158  jz      short loc_180005180
0x18000515a  lea     rax, [rsi+0Fh]
0x18000515e  cmp     rax, rsi
0x180005161  ja      short loc_18000516D
0x180005163  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000516d  and     rax, 0FFFFFFFFFFFFFFF0h
0x180005171  call    _alloca_probe
0x180005176  sub     rsp, rax
0x180005179  lea     rsi, [rsp+4C0h+MultiByteStr]
0x18000517e  jmp     short loc_1800051B2
0x180005180  mov     rax, rsi
0x180005183  not     rax
0x180005186  cmp     rax, 10h
0x18000518a  jb      loc_1800053F7
0x180005190  lea     rcx, [rsi+10h]; Size
0x180005194  call    cs:__imp_malloc
0x18000519a  test    rax, rax
0x18000519d  jnz     short loc_1800051A4
0x18000519f  mov     rsi, rdi
0x1800051a2  jmp     short loc_1800051B2
0x1800051a4  mov     [rax], rdi
0x1800051a7  mov     rbx, rax
0x1800051aa  mov     [rbp+480h+var_478], rax
0x1800051ae  lea     rsi, [rax+10h]
0x1800051b2  test    rsi, rsi
0x1800051b5  jz      loc_180005381
0x1800051bb  mov     [rsi], dil
0x1800051be  mov     [rsp+4C0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1800051c3  mov     [rsp+4C0h+lpDefaultChar], rdi; lpDefaultChar
0x1800051c8  mov     [rsp+4C0h+cbMultiByte], r14d; cbMultiByte
0x1800051cd  mov     [rsp+4C0h+lpMultiByteStr], rsi; lpMultiByteStr
0x1800051d2  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800051d6  mov     r8, r15; lpWideCharStr
0x1800051d9  xor     edx, edx; dwFlags
0x1800051db  lea     ecx, [rdx+3]; CodePage
0x1800051de  call    cs:__imp_WideCharToMultiByte
0x1800051e4  test    eax, eax
0x1800051e6  jz      loc_180005381
0x1800051ec  xor     edx, edx; hFile
0x1800051ee  lea     r8d, [rdx+2]; dwFlags
0x1800051f2  mov     rcx, rsi; lpLibFileName
0x1800051f5  call    cs:__imp_LoadLibraryExA
0x1800051fb  mov     r14, rax
0x1800051fe  mov     [rbp+480h+var_470], rax
0x180005202  test    rax, rax
0x180005205  jnz     short loc_180005213
0x180005207  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000520c  mov     esi, eax
0x18000520e  jmp     loc_180005356
0x180005213  xor     r9d, r9d; wLanguage
0x180005216  mov     r8, r12; lpName
0x180005219  mov     rdx, r13; lpType
0x18000521c  mov     rcx, r14; hModule
0x18000521f  call    cs:__imp_FindResourceExA
0x180005225  mov     r15, rax
0x180005228  test    rax, rax
0x18000522b  jnz     short loc_180005237
0x18000522d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005232  jmp     loc_18000534A
0x180005237  mov     rdx, r15; hResInfo
0x18000523a  mov     rcx, r14; hModule
0x18000523d  call    cs:__imp_LoadResource
0x180005243  mov     rsi, rax
0x180005246  mov     [rbp+480h+var_468], rax
0x18000524a  test    rax, rax
0x18000524d  jz      short loc_18000522D
0x18000524f  mov     rdx, r15; hResInfo
0x180005252  mov     rcx, r14; hModule
0x180005255  call    cs:__imp_SizeofResource
0x18000525b  mov     r15d, eax
0x18000525e  mov     dword ptr [rbp+480h+MultiByteStr], r15d
0x180005262  lea     eax, [r15+1]
0x180005266  cmp     eax, r15d
0x180005269  jnb     short loc_180005297
0x18000526b  lea     rax, [rbp+480h+var_448]
0x18000526f  cmp     [rbp+480h+Destination], rax
0x180005273  jz      short loc_18000527F
0x180005275  lea     rcx, [rbp+480h+Destination]
0x180005279  call    ?FreeHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000527e  nop
0x18000527f  jmp     short loc_18000528D
0x180005281  mov     rcx, rbx; Block
0x180005284  mov     rbx, [rbx]
0x180005287  call    cs:__imp_free
0x18000528d  test    rbx, rbx
0x180005290  jnz     short loc_180005281
0x180005292  jmp     loc_1800053A8
0x180005297  test    eax, eax
0x180005299  jz      short loc_1800052CB
0x18000529b  mov     ecx, eax
0x18000529d  xor     edx, edx
0x18000529f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800052a3  div     rcx
0x1800052a6  cmp     rax, 1
0x1800052aa  jb      loc_1800053D6
0x1800052b0  cmp     rcx, 400h
0x1800052b7  jbe     short loc_1800052CB
0x1800052b9  mov     rdx, rcx
0x1800052bc  lea     rcx, [rbp+480h+Destination]
0x1800052c0  call    ?AllocateHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800052c5  mov     rcx, [rbp+480h+Destination]
0x1800052c9  jmp     short loc_1800052D3
0x1800052cb  lea     rcx, [rbp+480h+var_448]
0x1800052cf  mov     [rbp+480h+Destination], rcx
0x1800052d3  jmp     short loc_1800052EB
0x1800052d5  xor     edi, edi
0x1800052d7  mov     rbx, [rbp+480h+var_478]
0x1800052db  mov     r14, [rbp+480h+var_470]
0x1800052df  mov     rsi, [rbp+480h+var_468]
0x1800052e3  mov     r15d, dword ptr [rbp+480h+MultiByteStr]
0x1800052e7  mov     rcx, [rbp+480h+Destination]; Destination
0x1800052eb  test    rcx, rcx
0x1800052ee  jnz     short loc_1800052F7
0x1800052f0  mov     esi, 8007000Eh
0x1800052f5  jmp     short loc_18000534C
0x1800052f7  mov     r9, r15; SourceSize
0x1800052fa  mov     r8, rsi; Source
0x1800052fd  mov     rdx, r15; DestinationSize
0x180005300  call    cs:__imp_memcpy_s
0x180005306  test    eax, eax
0x180005308  jz      short loc_18000532E
0x18000530a  cmp     eax, 0Ch
0x18000530d  jz      loc_1800053EC
0x180005313  cmp     eax, 16h
0x180005316  jz      loc_1800053F7
0x18000531c  cmp     eax, 22h ; '"'
0x18000531f  jz      loc_1800053F7
0x180005325  cmp     eax, 50h ; 'P'
0x180005328  jnz     loc_1800053E1
0x18000532e  mov     rax, [rbp+480h+Destination]
0x180005332  mov     [r15+rax], dil
0x180005336  mov     r8d, [rbp+480h+arg_20]; int
0x18000533d  mov     rdx, [rbp+480h+Destination]; char *
0x180005341  lea     rcx, [rbp+480h+var_460]; this
0x180005345  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEADH@Z; ATL::CRegParser::RegisterBuffer(char *,int)
0x18000534a  mov     esi, eax
0x18000534c  mov     rcx, r14; hLibModule
0x18000534f  call    cs:__imp_FreeLibrary
0x180005355  nop
0x180005356  lea     rax, [rbp+480h+var_448]
0x18000535a  cmp     [rbp+480h+Destination], rax
0x18000535e  jz      short loc_18000536A
0x180005360  lea     rcx, [rbp+480h+Destination]
0x180005364  call    ?FreeHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180005369  nop
0x18000536a  jmp     short loc_180005378
0x18000536c  mov     rcx, rbx; Block
0x18000536f  mov     rbx, [rbx]
0x180005372  call    cs:__imp_free
0x180005378  test    rbx, rbx
0x18000537b  jnz     short loc_18000536C
0x18000537d  mov     eax, esi
0x18000537f  jmp     short loc_1800053AD
0x180005381  lea     rax, [rbp+480h+var_448]
0x180005385  cmp     [rbp+480h+Destination], rax
0x180005389  jz      short loc_180005395
0x18000538b  lea     rcx, [rbp+480h+Destination]
0x18000538f  call    ?FreeHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180005394  nop
0x180005395  jmp     short loc_1800053A3
0x180005397  mov     rcx, rbx; Block
0x18000539a  mov     rbx, [rbx]
0x18000539d  call    cs:__imp_free
0x1800053a3  test    rbx, rbx
0x1800053a6  jnz     short loc_180005397
0x1800053a8  mov     eax, 8007000Eh
0x1800053ad  mov     rcx, [rbp+480h+var_40]
0x1800053b4  xor     rcx, rbp; StackCookie
0x1800053b7  call    __security_check_cookie
0x1800053bc  mov     rbx, [rbp+480h+arg_0]
0x1800053c3  lea     rsp, [rbp+450h]
0x1800053ca  pop     r15
0x1800053cc  pop     r14
0x1800053ce  pop     r13
0x1800053d0  pop     r12
0x1800053d2  pop     rdi
0x1800053d3  pop     rsi
0x1800053d4  pop     rbp
0x1800053d5  retn
0x1800053d6  mov     ecx, 80070057h; int
0x1800053db  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800053e1  mov     ecx, 80004005h; int
0x1800053e6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800053ec  mov     ecx, 8007000Eh; int
0x1800053f1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800053f7  mov     ecx, 80070057h; int
0x1800053fc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
