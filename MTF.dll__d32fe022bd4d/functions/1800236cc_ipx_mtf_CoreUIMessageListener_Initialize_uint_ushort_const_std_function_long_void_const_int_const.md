# ipx::mtf::CoreUIMessageListener::Initialize(uint,ushort const *,std::function<long (void const *,int)> const &)

- ea: `0x1800236cc`
- end: `0x180023a59`
- name: `?Initialize@CoreUIMessageListener@mtf@ipx@@QEAAJIPEBGAEBV?$function@$$A6AJPEBXH@Z@std@@@Z`
- size: `909`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e914`
- `0x18001ed80`

## callees

- `0x180006074`
- `0x18001031c`
- `0x1800236cc`
- `0x18002b7dc`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023852`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023852`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023836`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023836`
- `CoreMessaging!CoreUICreate` at `0x18002379a`
- `CoreMessaging!CoreUICreate` at `0x18002379a`

## string_xrefs

- `0x180023848`: `CoreUIClientCreate`
- `0x18002382f`: `CoreUIComponents.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ipx::mtf::CoreUIMessageListener::Initialize(__int64 a1, int a2, _WORD *a3, __int64 a4)
{
  _QWORD *v7; // r15
  unsigned int v8; // ebx
  __int64 v10; // r8
  _QWORD *v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 (__fastcall ***v14)(_QWORD, __int64); // rcx
  __int64 v15; // rdx
  int v16; // eax
  unsigned int v17; // edi
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rdi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rcx
  int v33; // [rsp+20h] [rbp-20h]
  int v34; // [rsp+20h] [rbp-20h]
  int v35; // [rsp+20h] [rbp-20h]
  __int64 v36; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  __int64 v38; // [rsp+70h] [rbp+30h] BYREF

  v7 = (_QWORD *)(a1 + 64);
  if ( *(_QWORD *)(a1 + 64) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\coreuiadapter.cpp",
      (const char *)0x8000FFFFLL,
      v33);
    return v8;
  }
  *(_DWORD *)(a1 + 96) = a2;
  if ( *a3 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
  }
  v11 = (_QWORD *)(a1 + 32);
  std::wstring::assign((void *)(a1 + 32), a3);
  if ( a1 != a4 )
  {
    v13 = *(_QWORD *)(a1 + 24);
    if ( v13 )
    {
      LOBYTE(v12) = v13 != a1;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 32LL))(v13, v12);
      *(_QWORD *)(a1 + 24) = 0;
    }
    v14 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a4 + 24);
    if ( v14 )
    {
      if ( v14 == (__int64 (__fastcall ***)(_QWORD, __int64))a4 )
        v15 = a1;
      else
        v15 = 0;
      *(_QWORD *)(a1 + 24) = (**v14)(v14, v15);
    }
    else
    {
      *(_QWORD *)(a1 + 24) = 0;
    }
  }
  v16 = CoreUICreate(v7);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\coreuiadapter.cpp",
      (const char *)(unsigned int)v16,
      v33);
    return v17;
  }
  v38 = 0;
  v18 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v7 + 24LL))(*v7, &v38);
  v17 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\coreuiadapter.cpp",
      (const char *)(unsigned int)v18,
      v33);
    v19 = v38;
    v38 = 0;
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    return v17;
  }
  v20 = *v7;
  if ( ipx::mtf::g_fCoreUIComponentsChecked
    || (ipx::mtf::g_fCoreUIComponentsChecked = 1,
        Library = LoadLibraryExW(L"CoreUIComponents.dll", 0, 0),
        (ipx::mtf::g_hCoreUIComponents = Library) == 0) )
  {
    ProcAddress = (FARPROC)ipx::mtf::g_pfnCoreUIClientCreate;
  }
  else
  {
    ProcAddress = GetProcAddress(Library, "CoreUIClientCreate");
    ipx::mtf::g_pfnCoreUIClientCreate = ProcAddress;
  }
  if ( ProcAddress )
  {
    v28 = SharedMessagePortRefPtr::Initialize(a1 + 72);
    v17 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\coreuiadapter.cpp",
        (const char *)(unsigned int)v28,
        v33);
LABEL_42:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\coreuiadapter.cpp",
        (const char *)v17,
        v34);
      v29 = v38;
      v38 = 0;
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      return v17;
    }
  }
  else
  {
    v36 = 0;
    v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v20 + 64LL))(v20, 0, &v36);
    v17 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\coreuiadapter.cpp",
        (const char *)(unsigned int)v23,
        v33);
      v24 = v36;
      v36 = 0;
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      goto LABEL_42;
    }
    v25 = v36;
    *(_QWORD *)(a1 + 80) = v36;
    if ( v25 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
      v25 = v36;
    }
    v36 = 0;
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v35 = a1 + 88;
  v26 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(void *, const void *, int), __int64, _QWORD))(*(_QWORD *)*v7 + 104LL))(
          *v7,
          ipx::mtf::CoreUIMessageListener::_EndpointCallback,
          a1,
          *(_QWORD *)(a1 + 80));
  v17 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\coreuiadapter.cpp",
      (const char *)(unsigned int)v26,
      v35);
    v27 = v38;
    v38 = 0;
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    return v17;
  }
  if ( v11[3] >= 8u )
    v11 = (_QWORD *)*v11;
  v30 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)v38 + 40LL))(
          v38,
          v11,
          *(_QWORD *)(a1 + 88),
          *(unsigned int *)(a1 + 96));
  v8 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\coreuiadapter.cpp",
      (const char *)(unsigned int)v30,
      v35);
    v31 = v38;
    v38 = 0;
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    return v8;
  }
  v32 = v38;
  v38 = 0;
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  return 0;
}

```

## disassembly

```asm
0x1800236cc  mov     [rsp-28h+arg_8], rbx
0x1800236d1  mov     [rsp-28h+arg_10], rsi
0x1800236d6  push    rbp
0x1800236d7  push    rdi
0x1800236d8  push    r12
0x1800236da  push    r14
0x1800236dc  push    r15
0x1800236de  mov     rbp, rsp
0x1800236e1  sub     rsp, 40h
0x1800236e5  mov     rdi, r9
0x1800236e8  mov     rax, r8
0x1800236eb  mov     rbx, rcx
0x1800236ee  lea     r15, [rcx+40h]
0x1800236f2  xor     r12d, r12d
0x1800236f5  cmp     [r15], r12
0x1800236f8  jz      short loc_18002371E
0x1800236fa  mov     rcx, [rbp+28h]; this
0x1800236fe  mov     ebx, 8000FFFFh
0x180023703  mov     r9d, ebx; char *
0x180023706  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\internal"...
0x18002370d  lea     edx, [r12+63h]; void *
0x180023712  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023717  mov     eax, ebx
0x180023719  jmp     loc_180023A40
0x18002371e  mov     [rcx+60h], edx
0x180023721  cmp     [r8], r12w
0x180023725  jnz     short loc_18002372C
0x180023727  mov     r8, r12
0x18002372a  jmp     short loc_18002373A
0x18002372c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180023730  inc     r8
0x180023733  cmp     [rax+r8*2], r12w
0x180023738  jnz     short loc_180023730
0x18002373a  lea     rsi, [rcx+20h]
0x18002373e  mov     rdx, rax; Src
0x180023741  mov     rcx, rsi; void *
0x180023744  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180023749  cmp     rbx, rdi
0x18002374c  jz      short loc_180023797
0x18002374e  mov     rcx, [rbx+18h]
0x180023752  test    rcx, rcx
0x180023755  jz      short loc_18002376D
0x180023757  mov     rax, [rcx]
0x18002375a  cmp     rcx, rbx
0x18002375d  setnz   dl
0x180023760  mov     rax, [rax+20h]
0x180023764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023769  mov     [rbx+18h], r12
0x18002376d  mov     rcx, [rdi+18h]
0x180023771  test    rcx, rcx
0x180023774  jnz     short loc_18002377C
0x180023776  mov     [rbx+18h], r12
0x18002377a  jmp     short loc_180023797
0x18002377c  mov     rax, [rcx]
0x18002377f  mov     rax, [rax]
0x180023782  cmp     rcx, rdi
0x180023785  jnz     short loc_18002378C
0x180023787  mov     rdx, rbx
0x18002378a  jmp     short loc_18002378E
0x18002378c  xor     edx, edx
0x18002378e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023793  mov     [rbx+18h], rax
0x180023797  mov     rcx, r15
0x18002379a  call    cs:__imp_CoreUICreate
0x1800237a0  mov     edi, eax
0x1800237a2  test    eax, eax
0x1800237a4  jns     short loc_1800237C5
0x1800237a6  mov     rcx, [rbp+28h]; this
0x1800237aa  mov     r9d, eax; char *
0x1800237ad  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\internal"...
0x1800237b4  mov     edx, 6Ch ; 'l'; void *
0x1800237b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800237be  mov     eax, edi
0x1800237c0  jmp     loc_180023A40
0x1800237c5  mov     [rbp+arg_0], r12
0x1800237c9  mov     rcx, [r15]
0x1800237cc  mov     rax, [rcx]
0x1800237cf  lea     rdx, [rbp+arg_0]
0x1800237d3  mov     rax, [rax+18h]
0x1800237d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237dc  mov     edi, eax
0x1800237de  test    eax, eax
0x1800237e0  jns     short loc_180023817
0x1800237e2  mov     rcx, [rbp+28h]; this
0x1800237e6  mov     r9d, eax; char *
0x1800237e9  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\internal"...
0x1800237f0  mov     edx, 6Fh ; 'o'; void *
0x1800237f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800237fa  nop
0x1800237fb  mov     rcx, [rbp+arg_0]
0x1800237ff  mov     [rbp+arg_0], r12
0x180023803  test    rcx, rcx
0x180023806  jz      short loc_180023815
0x180023808  mov     rax, [rcx]
0x18002380b  mov     rax, [rax+10h]
0x18002380f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023814  nop
0x180023815  jmp     short loc_1800237BE
0x180023817  mov     rdi, [r15]
0x18002381a  cmp     cs:?g_fCoreUIComponentsChecked@mtf@ipx@@3_NA, r12b; bool ipx::mtf::g_fCoreUIComponentsChecked
0x180023821  jnz     short loc_180023861
0x180023823  mov     cs:?g_fCoreUIComponentsChecked@mtf@ipx@@3_NA, 1; bool ipx::mtf::g_fCoreUIComponentsChecked
0x18002382a  xor     r8d, r8d; dwFlags
0x18002382d  xor     edx, edx; hFile
0x18002382f  lea     rcx, LibFileName; "CoreUIComponents.dll"
0x180023836  call    cs:__imp_LoadLibraryExW
0x18002383c  mov     cs:?g_hCoreUIComponents@mtf@ipx@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ipx::mtf::g_hCoreUIComponents
0x180023843  test    rax, rax
0x180023846  jz      short loc_180023861
0x180023848  lea     rdx, aCoreuiclientcr; "CoreUIClientCreate"
0x18002384f  mov     rcx, rax; hModule
0x180023852  call    cs:__imp_GetProcAddress
0x180023858  mov     cs:?g_pfnCoreUIClientCreate@mtf@ipx@@3PEAXEA, rax; void * ipx::mtf::g_pfnCoreUIClientCreate
0x18002385f  jmp     short loc_180023868
0x180023861  mov     rax, cs:?g_pfnCoreUIClientCreate@mtf@ipx@@3PEAXEA; void * ipx::mtf::g_pfnCoreUIClientCreate
0x180023868  test    rax, rax
0x18002386b  jnz     loc_180023963
0x180023871  mov     [rbp+var_10], r12
0x180023875  mov     rax, [rdi]
0x180023878  lea     r8, [rbp+var_10]
0x18002387c  xor     edx, edx
0x18002387e  mov     rcx, rdi
0x180023881  mov     rax, [rax+40h]
0x180023885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002388a  mov     edi, eax
0x18002388c  test    eax, eax
0x18002388e  jns     short loc_1800238C8
0x180023890  mov     rcx, [rbp+28h]; this
0x180023894  mov     r9d, eax; char *
0x180023897  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\internal"...
0x18002389e  mov     edx, 31h ; '1'; void *
0x1800238a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800238a8  nop
0x1800238a9  mov     rcx, [rbp+var_10]
0x1800238ad  mov     [rbp+var_10], r12
0x1800238b1  test    rcx, rcx
0x1800238b4  jz      short loc_1800238C3
0x1800238b6  mov     rax, [rcx]
0x1800238b9  mov     rax, [rax+10h]
0x1800238bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238c2  nop
0x1800238c3  jmp     loc_18002398A
0x1800238c8  mov     rcx, [rbp+var_10]
0x1800238cc  mov     [rbx+50h], rcx
0x1800238d0  test    rcx, rcx
0x1800238d3  jz      short loc_1800238E5
0x1800238d5  mov     rax, [rcx]
0x1800238d8  mov     rax, [rax+8]
0x1800238dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238e1  mov     rcx, [rbp+var_10]
0x1800238e5  mov     [rbp+var_10], r12
0x1800238e9  test    rcx, rcx
0x1800238ec  jz      short loc_1800238FB
0x1800238ee  mov     rax, [rcx]
0x1800238f1  mov     rax, [rax+10h]
0x1800238f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238fa  nop
0x1800238fb  mov     rcx, [r15]
0x1800238fe  lea     r14, [rbx+58h]
0x180023902  mov     rax, [rcx]
0x180023905  mov     qword ptr [rsp+40h+var_20], r14; int
0x18002390a  mov     r9, [rbx+50h]
0x18002390e  mov     r8, rbx
0x180023911  lea     rdx, ?_EndpointCallback@CoreUIMessageListener@mtf@ipx@@KAJPEAXPEBXH@Z; ipx::mtf::CoreUIMessageListener::_EndpointCallback(void *,void const *,int)
0x180023918  mov     rax, [rax+68h]
0x18002391c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023921  mov     edi, eax
0x180023923  test    eax, eax
0x180023925  jns     loc_1800239C2
0x18002392b  mov     rcx, [rbp+28h]; this
0x18002392f  mov     r9d, eax; char *
0x180023932  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\internal"...
0x180023939  mov     edx, 77h ; 'w'; void *
0x18002393e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023943  nop
0x180023944  mov     rcx, [rbp+arg_0]
0x180023948  mov     [rbp+arg_0], r12
0x18002394c  test    rcx, rcx
0x18002394f  jz      short loc_18002395E
0x180023951  mov     rax, [rcx]
0x180023954  mov     rax, [rax+10h]
0x180023958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002395d  nop
0x18002395e  jmp     loc_1800237BE
0x180023963  lea     rcx, [rbx+48h]
0x180023967  call    ?Initialize@SharedMessagePortRefPtr@@QEAAJW4InputCapability@@@Z; SharedMessagePortRefPtr::Initialize(InputCapability)
0x18002396c  mov     edi, eax
0x18002396e  test    eax, eax
0x180023970  jns     short loc_1800238FB
0x180023972  mov     rcx, [rbp+28h]; this
0x180023976  mov     r9d, eax; char *
0x180023979  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\internal"...
0x180023980  mov     edx, 35h ; '5'; void *
0x180023985  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002398a  mov     rcx, [rbp+28h]; this
0x18002398e  mov     r9d, edi; char *
0x180023991  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\internal"...
0x180023998  mov     edx, 72h ; 'r'; void *
0x18002399d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800239a2  nop
0x1800239a3  mov     rcx, [rbp+arg_0]
0x1800239a7  mov     [rbp+arg_0], r12
0x1800239ab  test    rcx, rcx
0x1800239ae  jz      short loc_1800239BD
0x1800239b0  mov     rdx, [rcx]
0x1800239b3  mov     rax, [rdx+10h]
0x1800239b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239bc  nop
0x1800239bd  jmp     loc_1800237BE
0x1800239c2  mov     rcx, [rbp+arg_0]
0x1800239c6  mov     rax, [rcx]
0x1800239c9  cmp     qword ptr [rsi+18h], 8
0x1800239ce  jb      short loc_1800239D3
0x1800239d0  mov     rsi, [rsi]
0x1800239d3  mov     r9d, [rbx+60h]
0x1800239d7  mov     r8, [r14]
0x1800239da  mov     rdx, rsi
0x1800239dd  mov     rax, [rax+28h]
0x1800239e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239e6  mov     ebx, eax
0x1800239e8  test    eax, eax
0x1800239ea  jns     short loc_180023A24
0x1800239ec  mov     rcx, [rbp+28h]; this
0x1800239f0  mov     r9d, eax; char *
0x1800239f3  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\internal"...
0x1800239fa  mov     edx, 7Bh ; '{'; void *
0x1800239ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023a04  nop
0x180023a05  mov     rcx, [rbp+arg_0]
0x180023a09  mov     [rbp+arg_0], r12
0x180023a0d  test    rcx, rcx
0x180023a10  jz      short loc_180023A1F
0x180023a12  mov     rax, [rcx]
0x180023a15  mov     rax, [rax+10h]
0x180023a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a1e  nop
0x180023a1f  jmp     loc_180023717
0x180023a24  mov     rcx, [rbp+arg_0]
0x180023a28  mov     [rbp+arg_0], r12
0x180023a2c  test    rcx, rcx
0x180023a2f  jz      short loc_180023A3E
0x180023a31  mov     rax, [rcx]
0x180023a34  mov     rax, [rax+10h]
0x180023a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a3d  nop
0x180023a3e  xor     eax, eax
0x180023a40  lea     r11, [rsp+40h+var_s0]
0x180023a45  mov     rbx, [r11+38h]
0x180023a49  mov     rsi, [r11+40h]
0x180023a4d  mov     rsp, r11
0x180023a50  pop     r15
0x180023a52  pop     r14
0x180023a54  pop     r12
0x180023a56  pop     rdi
0x180023a57  pop     rbp
0x180023a58  retn
```
