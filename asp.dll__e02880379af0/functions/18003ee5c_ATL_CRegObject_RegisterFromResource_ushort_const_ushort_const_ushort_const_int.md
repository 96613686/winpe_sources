# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18003ee5c`
- end: `0x18003f002`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `422`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18003ff50`
- `0x1800401d0`

## callees

- `0x180023dd0`
- `0x180030bd0`
- `0x18003ce3c`
- `0x18003ce74`
- `0x18003d5f8`
- `0x18003d7bc`
- `0x18003e3b4`
- `0x18003ecec`
- `0x18003ee5c`

## import_xrefs

- `KERNEL32!FindResourceExW` at `0x18003eedc`
- `KERNEL32!FindResourceExW` at `0x18003eedc`
- `KERNEL32!LoadResource` at `0x18003eefa`
- `KERNEL32!LoadResource` at `0x18003eefa`
- `KERNEL32!SizeofResource` at `0x18003ef0e`
- `KERNEL32!SizeofResource` at `0x18003ef0e`
- `KERNEL32!LoadLibraryExW` at `0x18003eeb6`
- `KERNEL32!LoadLibraryExW` at `0x18003eeb6`
- `KERNEL32!FreeLibrary` at `0x18003efb8`
- `KERNEL32!FreeLibrary` at `0x18003efb8`
- `KERNEL32!MultiByteToWideChar` at `0x18003ef82`
- `KERNEL32!MultiByteToWideChar` at `0x18003ef82`

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
  unsigned __int64 v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v20[3]; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[1032]; // [rsp+58h] [rbp-A8h] BYREF

  v20[1] = this;
  v19 = 0;
  v20[0] = 0;
  v21 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
    goto LABEL_17;
  }
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
    ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v21);
    Error = -2147024882;
    goto LABEL_19;
  }
  v15 = ATL::AtlMultiplyThrow<unsigned __int64>(cchWideChar + 1, 2);
  if ( v15 <= 0x400 )
  {
    lpWideCharStr = (WCHAR *)v22;
    v21 = (LPWSTR)v22;
  }
  else
  {
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v21, v15);
    lpWideCharStr = v21;
  }
  if ( lpWideCharStr )
  {
    v17 = MultiByteToWideChar(3u, 0, v13, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v17 )
    {
      v21[v17] = 0;
      v12 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v20, v21, a5);
      goto LABEL_15;
    }
LABEL_4:
    v12 = ATL::AtlHresultFromLastError();
LABEL_15:
    Error = v12;
    goto LABEL_16;
  }
  Error = -2147024882;
LABEL_16:
  FreeLibrary(v8);
LABEL_17:
  if ( v21 != (LPWSTR)v22 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v21);
LABEL_19:
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
  return Error;
}

```

## disassembly

```asm
0x18003ee5c  mov     [rsp-8+arg_0], rbx
0x18003ee61  push    rbp
0x18003ee62  push    rsi
0x18003ee63  push    rdi
0x18003ee64  lea     rbp, [rsp-370h]
0x18003ee6c  sub     rsp, 470h
0x18003ee73  mov     rax, cs:__security_cookie
0x18003ee7a  xor     rax, rsp
0x18003ee7d  mov     [rbp+380h+var_20], rax
0x18003ee84  mov     rax, rdx
0x18003ee87  mov     [rsp+480h+var_440], rcx
0x18003ee8c  xor     edx, edx; hFile
0x18003ee8e  mov     [rsp+480h+var_450], 0
0x18003ee97  mov     rbx, r8
0x18003ee9a  mov     [rsp+480h+var_448], 0
0x18003eea3  mov     rcx, rax; lpLibFileName
0x18003eea6  mov     [rsp+480h+var_430], 0
0x18003eeaf  mov     rsi, r9
0x18003eeb2  lea     r8d, [rdx+2]; dwFlags
0x18003eeb6  call    cs:__imp_LoadLibraryExW
0x18003eebc  mov     rdi, rax
0x18003eebf  test    rax, rax
0x18003eec2  jnz     short loc_18003EED0
0x18003eec4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18003eec9  mov     ebx, eax
0x18003eecb  jmp     loc_18003EFBE
0x18003eed0  xor     r9d, r9d; wLanguage
0x18003eed3  mov     r8, rbx; lpName
0x18003eed6  mov     rdx, rsi; lpType
0x18003eed9  mov     rcx, rdi; hModule
0x18003eedc  call    cs:__imp_FindResourceExW
0x18003eee2  mov     rbx, rax
0x18003eee5  test    rax, rax
0x18003eee8  jnz     short loc_18003EEF4
0x18003eeea  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18003eeef  jmp     loc_18003EFB3
0x18003eef4  mov     rdx, rbx; hResInfo
0x18003eef7  mov     rcx, rdi; hModule
0x18003eefa  call    cs:__imp_LoadResource
0x18003ef00  mov     rsi, rax
0x18003ef03  test    rax, rax
0x18003ef06  jz      short loc_18003EEEA
0x18003ef08  mov     rdx, rbx; hResInfo
0x18003ef0b  mov     rcx, rdi; hModule
0x18003ef0e  call    cs:__imp_SizeofResource
0x18003ef14  mov     ebx, eax
0x18003ef16  inc     eax
0x18003ef18  cmp     eax, ebx
0x18003ef1a  jnb     short loc_18003EF30
0x18003ef1c  lea     rcx, [rsp+480h+var_430]
0x18003ef21  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18003ef26  mov     ebx, 8007000Eh
0x18003ef2b  jmp     loc_18003EFD4
0x18003ef30  mov     ecx, eax
0x18003ef32  mov     edx, 2
0x18003ef37  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18003ef3c  cmp     rax, 400h
0x18003ef42  jbe     short loc_18003EF58
0x18003ef44  mov     rdx, rax
0x18003ef47  lea     rcx, [rsp+480h+var_430]
0x18003ef4c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18003ef51  mov     rax, [rsp+480h+var_430]
0x18003ef56  jmp     short loc_18003EF62
0x18003ef58  lea     rax, [rsp+480h+var_428]
0x18003ef5d  mov     [rsp+480h+var_430], rax
0x18003ef62  test    rax, rax
0x18003ef65  jnz     short loc_18003EF6E
0x18003ef67  mov     ebx, 8007000Eh
0x18003ef6c  jmp     short loc_18003EFB5
0x18003ef6e  xor     edx, edx; dwFlags
0x18003ef70  mov     [rsp+480h+cchWideChar], ebx; cchWideChar
0x18003ef74  mov     r9d, ebx; cbMultiByte
0x18003ef77  mov     [rsp+480h+lpWideCharStr], rax; lpWideCharStr
0x18003ef7c  mov     r8, rsi; lpMultiByteStr
0x18003ef7f  lea     ecx, [rdx+3]; CodePage
0x18003ef82  call    cs:__imp_MultiByteToWideChar
0x18003ef88  test    eax, eax
0x18003ef8a  jz      loc_18003EEEA
0x18003ef90  mov     r8d, [rbp+380h+arg_20]; int
0x18003ef97  xor     ecx, ecx
0x18003ef99  mov     edx, eax
0x18003ef9b  mov     rax, [rsp+480h+var_430]
0x18003efa0  mov     [rax+rdx*2], cx
0x18003efa4  lea     rcx, [rsp+480h+var_448]; this
0x18003efa9  mov     rdx, [rsp+480h+var_430]; unsigned __int16 *
0x18003efae  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18003efb3  mov     ebx, eax
0x18003efb5  mov     rcx, rdi; hLibModule
0x18003efb8  call    cs:__imp_FreeLibrary
0x18003efbe  lea     rax, [rsp+480h+var_428]
0x18003efc3  cmp     [rsp+480h+var_430], rax
0x18003efc8  jz      short loc_18003EFD4
0x18003efca  lea     rcx, [rsp+480h+var_430]
0x18003efcf  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18003efd4  lea     rcx, [rsp+480h+var_450]
0x18003efd9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18003efde  mov     eax, ebx
0x18003efe0  mov     rcx, [rbp+380h+var_20]
0x18003efe7  xor     rcx, rsp; StackCookie
0x18003efea  call    __security_check_cookie
0x18003efef  mov     rbx, [rsp+480h+arg_0]
0x18003eff7  add     rsp, 470h
0x18003effe  pop     rdi
0x18003efff  pop     rsi
0x18003f000  pop     rbp
0x18003f001  retn
```
