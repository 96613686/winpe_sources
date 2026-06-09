# CWinSATResultsInfo::InitVideoInfoFromRegistry(void)

- ea: `0x18000ba80`
- end: `0x18000bddb`
- name: `?InitVideoInfoFromRegistry@CWinSATResultsInfo@@AEAAJXZ`
- size: `859`
- prototype: `__int64 __fastcall(CWinSATResultsInfo *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002254`

## callees

- `0x180004360`
- `0x180008490`
- `0x18000ba80`
- `0x18000bde4`
- `0x18000be30`
- `0x18000c03c`
- `0x180010690`
- `0x180011e70`
- `0x180011ee0`
- `0x180012c06`
- `0x18002fb50`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000bc29`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bc38`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bd67`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bd76`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bd93`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bda2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bc29`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bc38`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bd67`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bd76`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bd93`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bda2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bbca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bc80`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bbca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bc80`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWinSATResultsInfo::InitVideoInfoFromRegistry(CWinSATResultsInfo *this)
{
  _QWORD *v1; // rax
  _QWORD *v2; // rbx
  void *v3; // rax
  __int64 v4; // rdx
  int v5; // r15d
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  void *v8; // rax
  __int64 v9; // rcx
  HMODULE ModuleHandleW; // rax
  _QWORD *v11; // rbx
  bool v12; // zf
  void *v13; // rsi
  void *v14; // rcx
  HMODULE v15; // rax
  unsigned int *v16; // rdx
  unsigned __int64 v17; // r9
  int v18; // eax
  _QWORD *v19; // rdi
  void *v20; // rcx
  void *v21; // rcx
  _QWORD *v23; // [rsp+30h] [rbp-2A8h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-2A0h] BYREF
  unsigned __int64 v25; // [rsp+40h] [rbp-298h] BYREF
  _QWORD *v26; // [rsp+48h] [rbp-290h] BYREF
  void **v27; // [rsp+50h] [rbp-288h] BYREF
  __int16 v28; // [rsp+58h] [rbp-280h]
  HMODULE v29; // [rsp+60h] [rbp-278h]
  __int64 v30; // [rsp+68h] [rbp-270h]
  __int64 v31; // [rsp+70h] [rbp-268h]
  CWinSATResultsInfo *v32; // [rsp+78h] [rbp-260h]
  __int64 v33; // [rsp+80h] [rbp-258h]
  _DWORD v34[4]; // [rsp+88h] [rbp-250h] BYREF
  _DWORD v35[6]; // [rsp+98h] [rbp-240h] BYREF
  unsigned __int16 v36[256]; // [rsp+B0h] [rbp-228h] BYREF

  v33 = -2;
  v32 = this;
  v1 = operator new(0x28u);
  v2 = v1;
  if ( !v1 )
    std::_Xbad_alloc();
  v26 = v1;
  v1[2] = 1;
  v1[3] = 0;
  *v1 = 0;
  v1[1] = 0;
  v3 = operator new(2u);
  if ( !v3 )
    std::_Xbad_alloc();
  v2[3] = v3;
  if ( *v2 )
    memcpy_0(v3, 0, 2LL * *v2);
  v4 = v2[3];
  if ( v4 )
    *(_WORD *)(v4 + 2LL * *v2) = 0;
  v26 = v2;
  LODWORD(v25) = 0;
  v5 = 0;
  v6 = operator new(0x28u);
  v7 = v6;
  if ( !v6 )
    std::_Xbad_alloc();
  v24 = v6;
  v6[2] = 1;
  v6[3] = 0;
  *v6 = 0;
  v6[1] = 0;
  v8 = operator new(2u);
  if ( !v8 )
    std::_Xbad_alloc();
  v7[3] = v8;
  if ( *v7 )
    memcpy_0(v8, 0, 2LL * *v7);
  v9 = v7[3];
  if ( v9 )
    *(_WORD *)(v9 + 2LL * *v7) = 0;
  v24 = v7;
  ModuleHandleW = g_DLLModuleHandle;
  v27 = &mlib::MUILoader::`vftable';
  v28 = 10016;
  if ( !g_DLLModuleHandle )
    ModuleHandleW = GetModuleHandleW(0);
  try
  {
    v29 = ModuleHandleW;
    v30 = 0;
    v31 = 0;
    v11 = *(_QWORD **)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                        &v23,
                        &v27);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v24);
    v24 = v11;
    ++v11[2];
    v12 = v23[2]-- == 1;
    if ( v12 )
    {
      v13 = v23;
      if ( v23 )
      {
        v14 = (void *)v23[3];
        if ( v14 )
          operator delete(v14);
        operator delete(v13);
      }
    }
  }
  catch ( mlib::MSError v34 )
  {
    LODWORD(v23) = v34[0];
    mlib::MSError::~MSError((mlib::MSError *)v34);
    v5 = (int)v23;
    v11 = v24;
    if ( (int)v23 < 0 )
    {
      v19 = v26;
      goto LABEL_35;
    }
  }
  v15 = g_DLLModuleHandle;
  v27 = &mlib::MUILoader::`vftable';
  v28 = 10001;
  if ( !g_DLLModuleHandle )
    v15 = GetModuleHandleW(0);
  try
  {
    v29 = v15;
    v30 = 0;
    v31 = 0;
    v19 = *(_QWORD **)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                        &v23,
                        &v27);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v26);
    v26 = v19;
    ++v19[2];
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v23);
  }
  catch ( mlib::MSError v35 )
  {
    LODWORD(v23) = v35[0];
    mlib::MSError::~MSError((mlib::MSError *)v35);
    v19 = v26;
    v5 = (int)v23;
    v11 = v24;
  }
  if ( v5 >= 0 )
  {
    D3DCommon::DXGetVideoInfoFromRegistry((D3DCommon *)&v25, v16);
    v17 = CWinSATResultsInfo::FixupReportedGraphicsMemory((unsigned int)v25);
    v18 = v17 ? StringCchPrintfW(v36, 0x100u, L"%u %ws", v17, v19[3]) : StringCchPrintfW(v36, 0x100u, L"%ws", v11[3]);
    v5 = v18;
    if ( v18 >= 0 )
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
        (char *)v32 + 504,
        v36);
  }
LABEL_35:
  v12 = v11[2]-- == 1;
  if ( v12 )
  {
    v20 = (void *)v11[3];
    if ( v20 )
      operator delete(v20);
    operator delete(v11);
  }
  v12 = v19[2]-- == 1;
  if ( v12 )
  {
    v21 = (void *)v19[3];
    if ( v21 )
      operator delete(v21);
    operator delete(v19);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000ba80  mov     rax, rsp
0x18000ba83  push    rdi
0x18000ba84  push    r14
0x18000ba86  push    r15
0x18000ba88  sub     rsp, 2C0h
0x18000ba8f  mov     qword ptr [rax-258h], 0FFFFFFFFFFFFFFFEh
0x18000ba9a  mov     [rax+10h], rbx
0x18000ba9e  mov     [rax+18h], rsi
0x18000baa2  mov     rax, cs:__security_cookie
0x18000baa9  xor     rax, rsp
0x18000baac  mov     [rsp+2D8h+var_28], rax
0x18000bab4  mov     [rsp+2D8h+var_260], rcx
0x18000bab9  mov     ecx, 28h ; '('; Size
0x18000babe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bac3  mov     rbx, rax
0x18000bac6  test    rax, rax
0x18000bac9  jnz     short loc_18000BAD1
0x18000bacb  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000bad1  mov     [rsp+2D8h+var_290], rbx
0x18000bad6  mov     qword ptr [rax+10h], 1
0x18000bade  xor     edi, edi
0x18000bae0  mov     [rax+18h], rdi
0x18000bae4  mov     [rax], rdi
0x18000bae7  mov     [rax+8], rdi
0x18000baeb  lea     ecx, [rdi+2]; Size
0x18000baee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000baf3  test    rax, rax
0x18000baf6  jnz     short loc_18000BAFE
0x18000baf8  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000bafe  mov     [rbx+18h], rax
0x18000bb02  mov     r8, [rbx]
0x18000bb05  test    r8, r8
0x18000bb08  jz      short loc_18000BB17
0x18000bb0a  add     r8, r8; Size
0x18000bb0d  xor     edx, edx; Src
0x18000bb0f  mov     rcx, rax; void *
0x18000bb12  call    memcpy_0
0x18000bb17  mov     rdx, [rbx+18h]
0x18000bb1b  test    rdx, rdx
0x18000bb1e  jz      short loc_18000BB27
0x18000bb20  mov     rax, [rbx]
0x18000bb23  mov     [rdx+rax*2], di
0x18000bb27  mov     [rsp+2D8h+var_290], rbx
0x18000bb2c  mov     dword ptr [rsp+2D8h+var_298], edi
0x18000bb30  mov     r15d, edi
0x18000bb33  mov     ecx, 28h ; '('; Size
0x18000bb38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bb3d  mov     rbx, rax
0x18000bb40  test    rax, rax
0x18000bb43  jnz     short loc_18000BB4B
0x18000bb45  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000bb4b  mov     [rsp+2D8h+var_2A0], rbx
0x18000bb50  mov     qword ptr [rax+10h], 1
0x18000bb58  mov     [rax+18h], rdi
0x18000bb5c  mov     [rax], rdi
0x18000bb5f  mov     [rax+8], rdi
0x18000bb63  mov     ecx, 2; Size
0x18000bb68  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bb6d  test    rax, rax
0x18000bb70  jnz     short loc_18000BB78
0x18000bb72  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000bb78  mov     [rbx+18h], rax
0x18000bb7c  mov     r8, [rbx]
0x18000bb7f  test    r8, r8
0x18000bb82  jz      short loc_18000BB91
0x18000bb84  add     r8, r8; Size
0x18000bb87  xor     edx, edx; Src
0x18000bb89  mov     rcx, rax; void *
0x18000bb8c  call    memcpy_0
0x18000bb91  mov     rcx, [rbx+18h]
0x18000bb95  test    rcx, rcx
0x18000bb98  jz      short loc_18000BBA1
0x18000bb9a  mov     rax, [rbx]
0x18000bb9d  mov     [rcx+rax*2], di
0x18000bba1  mov     [rsp+2D8h+var_2A0], rbx
0x18000bba6  mov     rax, cs:?g_DLLModuleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_DLLModuleHandle
0x18000bbad  lea     r14, ??_7MUILoader@mlib@@6B@; const mlib::MUILoader::`vftable'
0x18000bbb4  mov     [rsp+2D8h+var_288], r14
0x18000bbb9  mov     ecx, 2720h
0x18000bbbe  mov     [rsp+2D8h+var_280], cx
0x18000bbc3  test    rax, rax
0x18000bbc6  jnz     short loc_18000BBD6
0x18000bbc8  xor     ecx, ecx; lpModuleName
0x18000bbca  call    cs:__imp_GetModuleHandleW
0x18000bbd1  nop     dword ptr [rax+rax+00h]
0x18000bbd6  mov     [rsp+2D8h+var_278], rax
0x18000bbdb  mov     [rsp+2D8h+var_270], rdi
0x18000bbe0  mov     [rsp+2D8h+var_268], rdi
0x18000bbe5  lea     rdx, [rsp+2D8h+var_288]
0x18000bbea  lea     rcx, [rsp+2D8h+var_2A8]
0x18000bbef  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x18000bbf4  mov     rbx, [rax]
0x18000bbf7  lea     rcx, [rsp+2D8h+var_2A0]
0x18000bbfc  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000bc01  mov     [rsp+2D8h+var_2A0], rbx
0x18000bc06  inc     qword ptr [rbx+10h]
0x18000bc0a  mov     rax, [rsp+2D8h+var_2A8]
0x18000bc0f  sub     qword ptr [rax+10h], 1
0x18000bc14  jnz     short loc_18000BC45
0x18000bc16  mov     rsi, [rsp+2D8h+var_2A8]
0x18000bc1b  test    rsi, rsi
0x18000bc1e  jz      short loc_18000BC45
0x18000bc20  mov     rcx, [rsi+18h]
0x18000bc24  test    rcx, rcx
0x18000bc27  jz      short loc_18000BC35
0x18000bc29  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bc30  nop     dword ptr [rax+rax+00h]
0x18000bc35  mov     rcx, rsi
0x18000bc38  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bc3f  nop     dword ptr [rax+rax+00h]
0x18000bc44  nop
0x18000bc45  jmp     short loc_18000BC63
0x18000bc47  mov     r15d, dword ptr [rsp+2D8h+var_2A8]
0x18000bc4c  mov     rbx, [rsp+2D8h+var_2A0]
0x18000bc51  test    r15d, r15d
0x18000bc54  js      loc_18000BD52
0x18000bc5a  xor     edi, edi
0x18000bc5c  lea     r14, ??_7MUILoader@mlib@@6B@; const mlib::MUILoader::`vftable'
0x18000bc63  mov     rax, cs:?g_DLLModuleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_DLLModuleHandle
0x18000bc6a  mov     [rsp+2D8h+var_288], r14
0x18000bc6f  mov     ecx, 2711h
0x18000bc74  mov     [rsp+2D8h+var_280], cx
0x18000bc79  test    rax, rax
0x18000bc7c  jnz     short loc_18000BC8C
0x18000bc7e  xor     ecx, ecx; lpModuleName
0x18000bc80  call    cs:__imp_GetModuleHandleW
0x18000bc87  nop     dword ptr [rax+rax+00h]
0x18000bc8c  mov     [rsp+2D8h+var_278], rax
0x18000bc91  mov     [rsp+2D8h+var_270], rdi
0x18000bc96  mov     [rsp+2D8h+var_268], rdi
0x18000bc9b  lea     rdx, [rsp+2D8h+var_288]
0x18000bca0  lea     rcx, [rsp+2D8h+var_2A8]
0x18000bca5  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x18000bcaa  mov     rdi, [rax]
0x18000bcad  lea     rcx, [rsp+2D8h+var_290]
0x18000bcb2  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000bcb7  mov     [rsp+2D8h+var_290], rdi
0x18000bcbc  inc     qword ptr [rdi+10h]
0x18000bcc0  lea     rcx, [rsp+2D8h+var_2A8]
0x18000bcc5  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000bcca  nop
0x18000bccb  jmp     short loc_18000BCDC
0x18000bccd  mov     rdi, [rsp+2D8h+var_290]
0x18000bcd2  mov     r15d, dword ptr [rsp+2D8h+var_2A8]
0x18000bcd7  mov     rbx, [rsp+2D8h+var_2A0]
0x18000bcdc  test    r15d, r15d
0x18000bcdf  js      short loc_18000BD57
0x18000bce1  lea     rcx, [rsp+2D8h+var_298]; this
0x18000bce6  call    ?DXGetVideoInfoFromRegistry@D3DCommon@@YAJPEAK@Z; D3DCommon::DXGetVideoInfoFromRegistry(ulong *)
0x18000bceb  mov     ecx, dword ptr [rsp+2D8h+var_298]; unsigned __int64
0x18000bcef  call    ?FixupReportedGraphicsMemory@CWinSATResultsInfo@@CA_K_K@Z; CWinSATResultsInfo::FixupReportedGraphicsMemory(unsigned __int64)
0x18000bcf4  mov     r9, rax
0x18000bcf7  mov     edx, 100h; unsigned __int64
0x18000bcfc  lea     rcx, [rsp+2D8h+var_228]; unsigned __int16 *
0x18000bd04  test    rax, rax
0x18000bd07  jnz     short loc_18000BD1B
0x18000bd09  mov     r9, [rbx+18h]
0x18000bd0d  lea     r8, aWs; "%ws"
0x18000bd14  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000bd19  jmp     short loc_18000BD30
0x18000bd1b  mov     rax, [rdi+18h]
0x18000bd1f  mov     [rsp+2D8h+var_2B8], rax
0x18000bd24  lea     r8, aUWs; "%u %ws"
0x18000bd2b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000bd30  mov     r15d, eax
0x18000bd33  test    eax, eax
0x18000bd35  js      short loc_18000BD57
0x18000bd37  mov     rcx, [rsp+2D8h+var_260]
0x18000bd3c  add     rcx, 1F8h
0x18000bd43  lea     rdx, [rsp+2D8h+var_228]
0x18000bd4b  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x18000bd50  jmp     short loc_18000BD57
0x18000bd52  mov     rdi, [rsp+2D8h+var_290]
0x18000bd57  sub     qword ptr [rbx+10h], 1
0x18000bd5c  jnz     short loc_18000BD83
0x18000bd5e  mov     rcx, [rbx+18h]
0x18000bd62  test    rcx, rcx
0x18000bd65  jz      short loc_18000BD73
0x18000bd67  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bd6e  nop     dword ptr [rax+rax+00h]
0x18000bd73  mov     rcx, rbx
0x18000bd76  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bd7d  nop     dword ptr [rax+rax+00h]
0x18000bd82  nop
0x18000bd83  sub     qword ptr [rdi+10h], 1
0x18000bd88  jnz     short loc_18000BDAE
0x18000bd8a  mov     rcx, [rdi+18h]
0x18000bd8e  test    rcx, rcx
0x18000bd91  jz      short loc_18000BD9F
0x18000bd93  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bd9a  nop     dword ptr [rax+rax+00h]
0x18000bd9f  mov     rcx, rdi
0x18000bda2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bda9  nop     dword ptr [rax+rax+00h]
0x18000bdae  mov     eax, r15d
0x18000bdb1  mov     rcx, [rsp+2D8h+var_28]
0x18000bdb9  xor     rcx, rsp; StackCookie
0x18000bdbc  call    __security_check_cookie
0x18000bdc1  lea     r11, [rsp+2D8h+var_18]
0x18000bdc9  mov     rbx, [r11+28h]
0x18000bdcd  mov     rsi, [r11+30h]
0x18000bdd1  mov     rsp, r11
0x18000bdd4  pop     r15
0x18000bdd6  pop     r14
0x18000bdd8  pop     rdi
0x18000bdd9  retn
```
