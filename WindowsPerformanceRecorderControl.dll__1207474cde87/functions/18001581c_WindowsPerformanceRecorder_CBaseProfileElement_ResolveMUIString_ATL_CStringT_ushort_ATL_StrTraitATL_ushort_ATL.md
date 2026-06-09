# WindowsPerformanceRecorder::CBaseProfileElement::ResolveMUIString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18001581c`
- end: `0x180015af6`
- name: `?ResolveMUIString@CBaseProfileElement@WindowsPerformanceRecorder@@KAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `730`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x180008368`
- `0x18000eef0`
- `0x18001568c`

## callees

- `0x180008330`
- `0x18000eeb0`
- `0x180011280`
- `0x18001581c`
- `0x180016480`
- `0x180016f5c`
- `0x18002f1b0`
- `0x180041ca4`
- `0x180044210`
- `0x18004b39c`
- `0x18004f940`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180015946`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180015946`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180015863`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180015863`
- `api-ms-win-core-libraryloader-l1-1-0!FindResourceExW` at `0x1800159f2`
- `api-ms-win-core-libraryloader-l1-1-0!FindResourceExW` at `0x1800159f2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180015a88`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180015abb`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180015a88`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180015abb`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180015992`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180015992`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall WindowsPerformanceRecorder::CBaseProfileElement::ResolveMUIString(const wchar_t **a1)
{
  const wchar_t *v2; // rcx
  int v3; // eax
  wchar_t *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rbx
  int v8; // eax
  __int64 result; // rax
  unsigned int v10; // r15d
  LPCWSTR v11; // rdi
  HMODULE Library; // rbx
  unsigned int v13; // ebx
  wchar_t *v14; // r14
  HRSRC Resource; // rax
  const struct ATL::ATLSTRINGRESOURCEIMAGE *StringResourceImage; // rax
  const struct ATL::ATLSTRINGRESOURCEIMAGE *v17; // r13
  rsize_t v18; // r15
  errno_t v19; // ecx
  unsigned int Error; // esi
  ATL::CAtlException *v21; // [rsp+28h] [rbp-40h] BYREF
  wchar_t *v22; // [rsp+70h] [rbp+8h] BYREF
  LPCWSTR lpLibFileName; // [rsp+78h] [rbp+10h] BYREF
  HMODULE v24; // [rsp+80h] [rbp+18h] BYREF

  v2 = *a1;
  v3 = *((_DWORD *)v2 - 4);
  if ( !v3 )
    return 1;
  if ( v3 < 0 )
    ATL::AtlThrowImpl(-2147024809);
  if ( *v2 != 64 )
    return 1;
  v4 = wcschr(v2, 0x2Cu);
  if ( !v4 || (int)(v4 - *a1) < 0 )
    return 1;
  v5 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  try
  {
    lpLibFileName = (LPCWSTR)(v5 + 24);
    v6 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(a1, &v22);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&lpLibFileName, v6);
    ATL::CStringData::Release((ATL::CStringData *)(v22 - 12));
    v22 = (wchar_t *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(a1, &v24);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v22, &v24);
    ATL::CStringData::Release((ATL::CStringData *)(v24 - 6));
    v7 = (__int64)v22;
    v8 = _o__wtoi(v22);
    if ( v8 )
    {
      v10 = -v8;
      if ( v8 > 0 )
        v10 = v8;
      ATL::CStringData::Release((ATL::CStringData *)(v7 - 24));
      v11 = lpLibFileName;
      Library = LoadLibraryExW(lpLibFileName, 0, 0x22u);
      v24 = Library;
      if ( Library )
      {
        v14 = (wchar_t *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
        v22 = v14;
        Resource = FindResourceExW(Library, (LPCWSTR)6, (LPCWSTR)(unsigned __int16)((v10 >> 4) + 1), 0);
        if ( Resource
          && (StringResourceImage = ATL::_AtlGetStringResourceImage(Library, Resource, v10),
              (v17 = StringResourceImage) != 0) )
        {
          v18 = *(unsigned __int16 *)StringResourceImage;
          if ( (((*((_DWORD *)v14 - 3) - v18) | (1 - *((_DWORD *)v14 - 2))) & 0x80000000) != 0LL )
          {
            ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((__int64 *)&v22, v18);
            v14 = v22;
          }
          v19 = o_wmemcpy_s_0(v14, v18, (const wchar_t *)v17 + 1, *(unsigned __int16 *)v17);
          ATL::AtlCrtErrorCheck(v19);
          if ( (int)v18 > *((_DWORD *)v14 - 3) )
            ATL::AtlThrowImpl(-2147024809);
          *((_DWORD *)v14 - 4) = v18;
          v14[v18] = 0;
          ATL::CSimpleStringT<unsigned short,0>::operator=(a1, &v22);
          ATL::CStringData::Release((ATL::CStringData *)(v14 - 12));
          FreeLibrary(Library);
          ATL::CStringData::Release((ATL::CStringData *)(v11 - 12));
          result = 0;
        }
        else
        {
          Error = ATL::AtlHresultFromLastError();
          ATL::CStringData::Release((ATL::CStringData *)(v14 - 12));
          FreeLibrary(Library);
          ATL::CStringData::Release((ATL::CStringData *)(v11 - 12));
          result = Error;
        }
      }
      else
      {
        v13 = ATL::AtlHresultFromLastError();
        ATL::CStringData::Release((ATL::CStringData *)(v11 - 12));
        result = v13;
      }
    }
    else
    {
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v22);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpLibFileName);
      result = 2147942487LL;
    }
  }
  catch ( ATL::CAtlException *v21 )
  {
    LODWORD(v22) = *(_DWORD *)v21;
    return (unsigned int)v22;
  }
  return result;
}

```

## disassembly

```asm
0x18001581c  push    rbx
0x18001581e  push    rsi
0x18001581f  push    rdi
0x180015820  push    r12
0x180015822  push    r13
0x180015824  push    r14
0x180015826  push    r15
0x180015828  sub     rsp, 30h
0x18001582c  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x180015835  mov     r12, rcx
0x180015838  mov     rcx, [rcx]; Str
0x18001583b  mov     eax, [rcx-10h]
0x18001583e  test    eax, eax
0x180015840  jz      loc_180015AE0
0x180015846  js      loc_180015AD5
0x18001584c  cmp     word ptr [rcx], 40h ; '@'
0x180015850  jnz     loc_180015AE0
0x180015856  test    eax, eax
0x180015858  jle     loc_180015AE0
0x18001585e  mov     edx, 2Ch ; ','; Ch
0x180015863  call    cs:__imp_wcschr
0x180015869  mov     rbx, rax
0x18001586c  test    rax, rax
0x18001586f  jz      loc_180015AE0
0x180015875  sub     rbx, [r12]
0x180015879  sar     rbx, 1
0x18001587c  test    ebx, ebx
0x18001587e  js      loc_180015AE0
0x180015884  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001588b  lea     r14, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180015892  mov     rcx, r14
0x180015895  mov     rax, [rax+18h]
0x180015899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001589e  add     rax, 18h
0x1800158a2  mov     [rsp+68h+lpLibFileName], rax
0x1800158a7  lea     r9d, [rbx-1]
0x1800158ab  mov     esi, 1
0x1800158b0  mov     r8d, esi
0x1800158b3  lea     rdx, [rsp+68h+arg_0]; void *
0x1800158b8  mov     rcx, r12; void *
0x1800158bb  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x1800158c0  nop
0x1800158c1  mov     rdx, rax
0x1800158c4  lea     rcx, [rsp+68h+lpLibFileName]
0x1800158c9  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800158ce  nop
0x1800158cf  mov     rcx, [rsp+68h+arg_0]
0x1800158d4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800158d8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800158dd  nop
0x1800158de  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800158e5  mov     rcx, r14
0x1800158e8  mov     rax, [rax+18h]
0x1800158ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158f1  add     rax, 18h
0x1800158f5  mov     [rsp+68h+arg_0], rax
0x1800158fa  lea     r8d, [rbx+1]
0x1800158fe  mov     rax, [r12]
0x180015902  mov     r9d, [rax-10h]
0x180015906  sub     r9d, r8d
0x180015909  lea     rdx, [rsp+68h+arg_10]; void *
0x180015911  mov     rcx, r12; void *
0x180015914  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x180015919  nop
0x18001591a  lea     rdx, [rsp+68h+arg_10]
0x180015922  lea     rcx, [rsp+68h+arg_0]
0x180015927  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18001592c  nop
0x18001592d  mov     rcx, [rsp+68h+arg_10]
0x180015935  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180015939  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001593e  mov     rbx, [rsp+68h+arg_0]
0x180015943  mov     rcx, rbx
0x180015946  call    cs:__imp__o__wtoi
0x18001594c  nop
0x18001594d  test    eax, eax
0x18001594f  jnz     short loc_180015970
0x180015951  lea     rcx, [rsp+68h+arg_0]; this
0x180015956  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18001595b  nop
0x18001595c  lea     rcx, [rsp+68h+lpLibFileName]; this
0x180015961  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180015966  mov     eax, 80070057h
0x18001596b  jmp     loc_180015AE5
0x180015970  mov     r15d, eax
0x180015973  neg     r15d
0x180015976  cmovs   r15d, eax
0x18001597a  lea     rcx, [rbx-18h]; this
0x18001597e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015983  nop
0x180015984  xor     edx, edx; hFile
0x180015986  lea     r8d, [rdx+22h]; dwFlags
0x18001598a  mov     rdi, [rsp+68h+lpLibFileName]
0x18001598f  mov     rcx, rdi; lpLibFileName
0x180015992  call    cs:__imp_LoadLibraryExW
0x180015998  mov     rbx, rax
0x18001599b  mov     [rsp+68h+arg_10], rax
0x1800159a3  test    rax, rax
0x1800159a6  jnz     short loc_1800159BF
0x1800159a8  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800159ad  mov     ebx, eax
0x1800159af  lea     rcx, [rdi-18h]; this
0x1800159b3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800159b8  mov     eax, ebx
0x1800159ba  jmp     loc_180015AE5
0x1800159bf  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800159c6  mov     rcx, r14
0x1800159c9  mov     rax, [rax+18h]
0x1800159cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159d2  lea     r14, [rax+18h]
0x1800159d6  mov     [rsp+68h+arg_0], r14
0x1800159db  xor     r9d, r9d; wLanguage
0x1800159de  mov     eax, r15d
0x1800159e1  shr     eax, 4
0x1800159e4  add     ax, si
0x1800159e7  movzx   r8d, ax; lpName
0x1800159eb  lea     edx, [r9+6]; lpType
0x1800159ef  mov     rcx, rbx; hModule
0x1800159f2  call    cs:__imp_FindResourceExW
0x1800159f8  test    rax, rax
0x1800159fb  jz      loc_180015AA7
0x180015a01  mov     r8d, r15d; unsigned int
0x180015a04  mov     rdx, rax; hResInfo
0x180015a07  mov     rcx, rbx; hModule
0x180015a0a  call    ?_AtlGetStringResourceImage@ATL@@YAPEBUATLSTRINGRESOURCEIMAGE@1@PEAUHINSTANCE__@@PEAUHRSRC__@@I@Z; ATL::_AtlGetStringResourceImage(HINSTANCE__ *,HRSRC__ *,uint)
0x180015a0f  mov     r13, rax
0x180015a12  test    rax, rax
0x180015a15  jz      loc_180015AA7
0x180015a1b  movzx   r15d, word ptr [rax]
0x180015a1f  sub     esi, [r14-8]
0x180015a23  mov     ecx, [r14-0Ch]
0x180015a27  sub     ecx, r15d
0x180015a2a  or      esi, ecx
0x180015a2c  jge     short loc_180015A40
0x180015a2e  mov     edx, r15d
0x180015a31  lea     rcx, [rsp+68h+arg_0]
0x180015a36  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180015a3b  mov     r14, [rsp+68h+arg_0]
0x180015a40  lea     r8, [r13+2]; S2
0x180015a44  movzx   r9d, word ptr [r13+0]; N
0x180015a49  mov     rdx, r15; N1
0x180015a4c  mov     rcx, r14; S1
0x180015a4f  call    _o_wmemcpy_s_0
0x180015a54  mov     ecx, eax; int
0x180015a56  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180015a5b  nop
0x180015a5c  cmp     r15d, [r14-0Ch]
0x180015a60  jg      short loc_180015A9D
0x180015a62  mov     [r14-10h], r15d
0x180015a66  xor     eax, eax
0x180015a68  mov     [r14+r15*2], ax
0x180015a6d  lea     rdx, [rsp+68h+arg_0]
0x180015a72  mov     rcx, r12
0x180015a75  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180015a7a  nop
0x180015a7b  lea     rcx, [r14-18h]; this
0x180015a7f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015a84  nop
0x180015a85  mov     rcx, rbx; hLibModule
0x180015a88  call    cs:__imp_FreeLibrary
0x180015a8e  nop
0x180015a8f  lea     rcx, [rdi-18h]; this
0x180015a93  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015a98  nop
0x180015a99  xor     eax, eax
0x180015a9b  jmp     short loc_180015AE5
0x180015a9d  mov     ecx, 80070057h; int
0x180015aa2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180015aa7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180015aac  mov     esi, eax
0x180015aae  lea     rcx, [r14-18h]; this
0x180015ab2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015ab7  nop
0x180015ab8  mov     rcx, rbx; hLibModule
0x180015abb  call    cs:__imp_FreeLibrary
0x180015ac1  nop
0x180015ac2  lea     rcx, [rdi-18h]; this
0x180015ac6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015acb  mov     eax, esi
0x180015acd  jmp     short loc_180015AE5
0x180015acf  mov     eax, dword ptr [rsp+68h+arg_0]
0x180015ad3  jmp     short loc_180015AE5
0x180015ad5  mov     ecx, 80070057h; int
0x180015ada  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180015ae0  mov     eax, 1
0x180015ae5  add     rsp, 30h
0x180015ae9  pop     r15
0x180015aeb  pop     r14
0x180015aed  pop     r13
0x180015aef  pop     r12
0x180015af1  pop     rdi
0x180015af2  pop     rsi
0x180015af3  pop     rbx
0x180015af4  retn
```
