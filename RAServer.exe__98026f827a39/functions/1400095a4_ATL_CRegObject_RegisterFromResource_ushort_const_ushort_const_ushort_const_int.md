# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1400095a4`
- end: `0x14000974c`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `__int64 __fastcall(const wchar_t *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x14000b238`

## callees

- `0x140002640`
- `0x140003340`
- `0x1400035ec`
- `0x140004c34`
- `0x140004d7c`
- `0x140009430`
- `0x1400095a4`
- `0x140015aa0`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x1400096d5`
- `KERNEL32!MultiByteToWideChar` at `0x1400096d5`
- `KERNEL32!FindResourceExW` at `0x140009619`
- `KERNEL32!FindResourceExW` at `0x140009619`
- `KERNEL32!LoadResource` at `0x140009637`
- `KERNEL32!LoadResource` at `0x140009637`
- `KERNEL32!FreeLibrary` at `0x14000970a`
- `KERNEL32!FreeLibrary` at `0x14000970a`
- `KERNEL32!LoadLibraryExW` at `0x1400095ee`
- `KERNEL32!LoadLibraryExW` at `0x1400095ee`
- `KERNEL32!SizeofResource` at `0x140009650`
- `KERNEL32!SizeofResource` at `0x140009650`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        const wchar_t *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v8; // rsi
  unsigned int v9; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rdi
  unsigned int Error; // eax
  const CHAR *v13; // r14
  DWORD cchWideChar; // edi
  size_t v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  HMODULE v19; // [rsp+38h] [rbp-460h]
  _QWORD *v20; // [rsp+48h] [rbp-450h] BYREF
  const wchar_t *v21[2]; // [rsp+50h] [rbp-448h] BYREF
  LPWSTR v22; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v23[1032]; // [rsp+68h] [rbp-430h] BYREF

  v20 = 0;
  v21[1] = this;
  v21[0] = 0;
  v22 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  v19 = Library;
  if ( Library )
  {
    Resource = FindResourceExW(Library, a4, a3, 0);
    v11 = Resource;
    if ( !Resource )
      goto LABEL_4;
    v13 = (const CHAR *)LoadResource(v8, Resource);
    if ( !v13 )
      goto LABEL_4;
    cchWideChar = SizeofResource(v8, v11);
    if ( cchWideChar + 1 < cchWideChar )
    {
      v9 = -2147024882;
      goto LABEL_17;
    }
    try
    {
      v15 = ATL::AtlMultiplyThrow<unsigned __int64>();
      if ( v15 <= 0x400 )
      {
        lpWideCharStr = (WCHAR *)v23;
        v22 = (LPWSTR)v23;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v22, v15);
        lpWideCharStr = v22;
      }
    }
    catch ( ... )
    {
      v8 = v19;
      lpWideCharStr = v22;
    }
    if ( !lpWideCharStr )
    {
      v9 = -2147024882;
LABEL_16:
      FreeLibrary(v8);
      goto LABEL_17;
    }
    v17 = MultiByteToWideChar(3u, 0, v13, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v17 )
    {
      v22[v17] = 0;
      Error = ATL::CRegParser::RegisterBuffer(v21, v22, a5);
    }
    else
    {
LABEL_4:
      Error = ATL::AtlHresultFromLastError();
    }
    v9 = Error;
    goto LABEL_16;
  }
  v9 = ATL::AtlHresultFromLastError();
LABEL_17:
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v22);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
  return v9;
}

```

## disassembly

```asm
0x1400095a4  mov     [rsp+arg_0], rbx
0x1400095a9  push    rsi
0x1400095aa  push    rdi
0x1400095ab  push    r14
0x1400095ad  sub     rsp, 480h
0x1400095b4  mov     rax, cs:__security_cookie
0x1400095bb  xor     rax, rsp
0x1400095be  mov     [rsp+498h+var_28], rax
0x1400095c6  mov     r14, r9
0x1400095c9  mov     rdi, r8
0x1400095cc  mov     rax, rdx
0x1400095cf  xor     ebx, ebx
0x1400095d1  mov     [rsp+498h+var_450], rbx
0x1400095d6  mov     [rsp+498h+var_440], rcx
0x1400095db  mov     [rsp+498h+var_448], rbx
0x1400095e0  mov     [rsp+498h+var_438], rbx
0x1400095e5  xor     edx, edx; hFile
0x1400095e7  lea     r8d, [rbx+2]; dwFlags
0x1400095eb  mov     rcx, rax; lpLibFileName
0x1400095ee  call    cs:__imp_LoadLibraryExW
0x1400095f4  mov     rsi, rax
0x1400095f7  mov     [rsp+498h+var_460], rax
0x1400095fc  test    rax, rax
0x1400095ff  jnz     short loc_14000960D
0x140009601  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140009606  mov     ebx, eax
0x140009608  jmp     loc_140009711
0x14000960d  xor     r9d, r9d; wLanguage
0x140009610  mov     r8, rdi; lpName
0x140009613  mov     rdx, r14; lpType
0x140009616  mov     rcx, rsi; hModule
0x140009619  call    cs:__imp_FindResourceExW
0x14000961f  mov     rdi, rax
0x140009622  test    rax, rax
0x140009625  jnz     short loc_140009631
0x140009627  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14000962c  jmp     loc_140009705
0x140009631  mov     rdx, rdi; hResInfo
0x140009634  mov     rcx, rsi; hModule
0x140009637  call    cs:__imp_LoadResource
0x14000963d  mov     r14, rax
0x140009640  mov     [rsp+498h+var_458], rax
0x140009645  test    rax, rax
0x140009648  jz      short loc_140009627
0x14000964a  mov     rdx, rdi; hResInfo
0x14000964d  mov     rcx, rsi; hModule
0x140009650  call    cs:__imp_SizeofResource
0x140009656  mov     edi, eax
0x140009658  mov     [rsp+498h+var_468], eax
0x14000965c  inc     eax
0x14000965e  cmp     eax, edi
0x140009660  jnb     short loc_14000966C
0x140009662  mov     ebx, 8007000Eh
0x140009667  jmp     loc_140009711
0x14000966c  mov     ecx, eax
0x14000966e  mov     edx, 2
0x140009673  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x140009678  cmp     rax, 400h
0x14000967e  jbe     short loc_140009694
0x140009680  mov     rdx, rax
0x140009683  lea     rcx, [rsp+498h+var_438]
0x140009688  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14000968d  mov     rax, [rsp+498h+var_438]
0x140009692  jmp     short loc_14000969E
0x140009694  lea     rax, [rsp+498h+var_430]
0x140009699  mov     [rsp+498h+var_438], rax
0x14000969e  jmp     short loc_1400096B5
0x1400096a0  xor     ebx, ebx
0x1400096a2  mov     rsi, [rsp+498h+var_460]
0x1400096a7  mov     r14, [rsp+498h+var_458]
0x1400096ac  mov     edi, [rsp+498h+var_468]
0x1400096b0  mov     rax, [rsp+498h+var_438]
0x1400096b5  test    rax, rax
0x1400096b8  jnz     short loc_1400096C1
0x1400096ba  mov     ebx, 8007000Eh
0x1400096bf  jmp     short loc_140009707
0x1400096c1  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x1400096c5  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x1400096ca  mov     r9d, edi; cbMultiByte
0x1400096cd  mov     r8, r14; lpMultiByteStr
0x1400096d0  xor     edx, edx; dwFlags
0x1400096d2  lea     ecx, [rdx+3]; CodePage
0x1400096d5  call    cs:__imp_MultiByteToWideChar
0x1400096db  test    eax, eax
0x1400096dd  jz      loc_140009627
0x1400096e3  mov     ecx, eax
0x1400096e5  mov     rax, [rsp+498h+var_438]
0x1400096ea  mov     [rax+rcx*2], bx
0x1400096ee  mov     r8d, [rsp+498h+arg_20]; int
0x1400096f6  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x1400096fb  lea     rcx, [rsp+498h+var_448]; this
0x140009700  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x140009705  mov     ebx, eax
0x140009707  mov     rcx, rsi; hLibModule
0x14000970a  call    cs:__imp_FreeLibrary
0x140009710  nop
0x140009711  lea     rcx, [rsp+498h+var_438]
0x140009716  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x14000971b  nop
0x14000971c  lea     rcx, [rsp+498h+var_450]
0x140009721  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140009726  mov     eax, ebx
0x140009728  mov     rcx, [rsp+498h+var_28]
0x140009730  xor     rcx, rsp; StackCookie
0x140009733  call    __security_check_cookie
0x140009738  mov     rbx, [rsp+498h+arg_0]
0x140009740  add     rsp, 480h
0x140009747  pop     r14
0x140009749  pop     rdi
0x14000974a  pop     rsi
0x14000974b  retn
```
