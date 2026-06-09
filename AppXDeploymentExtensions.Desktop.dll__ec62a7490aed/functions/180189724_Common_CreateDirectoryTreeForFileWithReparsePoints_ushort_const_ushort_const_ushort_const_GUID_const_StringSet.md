# Common::CreateDirectoryTreeForFileWithReparsePoints(ushort const *,ushort const *,ushort const *,_GUID const &,StringSet &,StringSet *)

- ea: `0x180189724`
- end: `0x180189b41`
- name: `?CreateDirectoryTreeForFileWithReparsePoints@Common@@YAJPEBG00AEBU_GUID@@AEAVStringSet@@PEAV3@@Z`
- size: `1053`
- prototype: `__int64 __usercall@<rax>(Common *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, PCWSTR pszPathIn@<r8>, const unsigned __int16 *@<r9>, const struct _GUID *, struct StringSet *, struct StringSet *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x18008cf20`
- `0x18018a7b8`

## callees

- `0x18000a398`
- `0x18001adb4`
- `0x180023bd0`
- `0x180048cd4`
- `0x1800530c0`
- `0x180060724`
- `0x1800685b8`
- `0x1800af1bc`
- `0x1800af1fc`
- `0x1800af85a`
- `0x1800af918`
- `0x1800ba45d`
- `0x1801731cc`
- `0x180189724`
- `0x18018dd94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180189a2e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180189a42`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180189a2e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180189a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180189876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180189876`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801898bd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801898bd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180189866`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180189866`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180189773`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180189773`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1801897a1`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1801897a1`

## string_xrefs

- `0x1801897b8`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x180189a66`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x180189ab9`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x180189aea`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Common::CreateDirectoryTreeForFileWithReparsePoints(
        Common *this,
        const unsigned __int16 *a2,
        PCWSTR pszPathIn,
        const unsigned __int16 *a4,
        const struct _GUID *a5,
        struct StringSet *a6)
{
  const unsigned __int16 *v6; // rsi
  const unsigned __int16 *v8; // rdi
  const unsigned __int16 *v9; // r14
  HRESULT v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rdx
  PWSTR v14; // r15
  bool v15; // r13
  int v16; // eax
  const struct std::nothrow_t *v17; // rdx
  signed int LastError; // eax
  unsigned __int64 v19; // r9
  __int64 v20; // rdx
  DWORD FileAttributesW; // eax
  const unsigned __int16 *v22; // r8
  unsigned __int64 v23; // rdi
  unsigned __int16 v24; // r12
  char *v25; // rax
  char *v26; // rbx
  size_t v27; // rsi
  void *v28; // rcx
  PWSTR v29; // r14
  size_t v30; // rdi
  int v31; // edi
  __int64 v32; // rdx
  const struct std::nothrow_t *v33; // rdx
  const struct std::nothrow_t *v34; // rdx
  int v36; // [rsp+20h] [rbp-50h]
  PWSTR ppszPathOut; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int64 v38; // [rsp+38h] [rbp-38h] BYREF
  LPCWSTR lpPathName[2]; // [rsp+40h] [rbp-30h] BYREF
  int v40; // [rsp+50h] [rbp-20h]
  LPCWSTR pObjectName[2]; // [rsp+58h] [rbp-18h] BYREF
  int v42; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v6 = a4;
  v8 = a2;
  v9 = (const unsigned __int16 *)this;
  ppszPathOut = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  v10 = PathAllocCanonicalize(pszPathIn, 1u, &ppszPathOut);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = 834;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
      (const char *)(unsigned int)v10,
      v36);
    goto LABEL_71;
  }
  v13 = -1;
  do
    ++v13;
  while ( ppszPathOut[v13] );
  v10 = PathCchRemoveFileSpec(ppszPathOut, v13 + 1);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = 840;
    goto LABEL_7;
  }
  v14 = ppszPathOut;
  v15 = *ppszPathOut == 0;
  while ( 1 )
  {
    if ( v15 )
    {
      v11 = 0;
      goto LABEL_71;
    }
    if ( *v14 )
    {
      if ( *v14 != 92 )
        goto LABEL_46;
      *v14 = 0;
    }
    else
    {
      v15 = 1;
    }
    *(_OWORD *)pObjectName = 0;
    v42 = 0;
    *(_OWORD *)lpPathName = 0;
    v40 = 0;
    v16 = Common::PathHelpers::CombinePaths(v9, ppszPathOut, (struct Common::StringBuffer *)pObjectName);
    v11 = v16;
    if ( v16 < 0 )
    {
      v20 = 867;
      goto LABEL_64;
    }
    v16 = Common::PathHelpers::CombinePaths(v8, ppszPathOut, (struct Common::StringBuffer *)lpPathName);
    v11 = v16;
    if ( v16 < 0 )
    {
      v20 = 868;
      goto LABEL_64;
    }
    if ( !Common::GenericMap<unsigned short const *,unsigned short const *>::Find(a6, lpPathName[1]) )
      break;
LABEL_40:
    if ( !v15 )
      *v14 = 92;
    if ( lpPathName[1] )
      operator delete((void *)lpPathName[1], v17);
    if ( pObjectName[1] )
      operator delete((void *)pObjectName[1], v17);
LABEL_46:
    ++v14;
  }
  if ( !CreateDirectoryW(lpPathName[1], 0) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 == -2147024713 || v11 == -2147024891 )
    {
      FileAttributesW = GetFileAttributesW(lpPathName[1]);
      if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 )
        goto LABEL_27;
    }
    else
    {
      if ( v11 == -2147024893 )
      {
        v11 = -2147024713;
LABEL_24:
        v19 = v11;
        v20 = 898;
        goto LABEL_65;
      }
LABEL_27:
      if ( (v11 & 0x80000000) != 0 )
        goto LABEL_24;
    }
  }
  if ( !Common::GenericMap<unsigned short const *,unsigned short const *>::Find(a5, ppszPathOut) )
  {
    v16 = Common::Deployment::CopyPermissions(pObjectName[1], (LPWSTR)lpPathName[1], v22);
    v11 = v16;
    if ( v16 >= 0 )
    {
LABEL_39:
      StringSet::InsertIgnoreDuplicates(a6, lpPathName[1]);
      goto LABEL_40;
    }
    v20 = 919;
LABEL_64:
    v19 = (unsigned int)v16;
LABEL_65:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
      (const char *)v19,
      v36);
    goto LABEL_66;
  }
  v38 = 0;
  v16 = StringCchLengthW(ppszPathOut, 0x8000u, &v38);
  v11 = v16;
  if ( v16 < 0 )
  {
    v20 = 906;
    goto LABEL_64;
  }
  v23 = v38;
  v24 = 2 * (v38 + 11);
  v25 = (char *)operator new[](v24, (const struct std::nothrow_t *)&std::nothrow);
  v26 = v25;
  v38 = (unsigned __int64)v25;
  if ( !v25 )
  {
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38E,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
      (const char *)0x8007000ELL,
      v36);
LABEL_66:
    if ( lpPathName[1] )
      operator delete((void *)lpPathName[1], v34);
    if ( pObjectName[1] )
      operator delete((void *)pObjectName[1], v34);
    goto LABEL_71;
  }
  *(_DWORD *)v25 = 0;
  *(_OWORD *)(v25 + 4) = *(_OWORD *)v6;
  *((_WORD *)v25 + 10) = v23;
  v27 = 2 * v23;
  if ( !(2 * v23) )
  {
LABEL_36:
    v31 = WciSetReparsePointDataEx(lpPathName[1], v26, v24);
    if ( v31 < 0 )
    {
      v32 = 915;
      goto LABEL_53;
    }
    operator delete(v26, (const struct std::nothrow_t *)0x18);
    v8 = a2;
    v6 = a4;
    goto LABEL_39;
  }
  v28 = v25 + 22;
  if ( v25 == (char *)-22LL )
    goto LABEL_50;
  v29 = ppszPathOut;
  v30 = 2LL * (unsigned __int16)v23;
  if ( ppszPathOut && v30 >= v27 )
  {
    memcpy_0(v28, ppszPathOut, v27);
    v9 = (const unsigned __int16 *)this;
    goto LABEL_36;
  }
  memset_0(v28, 0, v30);
  if ( v29 )
  {
    if ( v30 < v27 )
    {
      *(_DWORD *)_o__errno() = 34;
      goto LABEL_51;
    }
  }
  else
  {
LABEL_50:
    *(_DWORD *)_o__errno() = 22;
LABEL_51:
    invalid_parameter_noinfo();
  }
  v31 = -2147483637;
  v32 = 914;
LABEL_53:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v32,
    (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
    (const char *)(unsigned int)v31,
    v36);
  operator delete(v26, (const struct std::nothrow_t *)0x18);
  if ( lpPathName[1] )
    operator delete((void *)lpPathName[1], v33);
  if ( pObjectName[1] )
    operator delete((void *)pObjectName[1], v33);
  v11 = v31;
LABEL_71:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppszPathOut);
  return v11;
}

```

## disassembly

```asm
0x180189724  mov     rax, rsp
0x180189727  mov     [rax+18h], rbx
0x18018972b  mov     [rax+20h], r9
0x18018972f  mov     [rax+10h], rdx
0x180189733  mov     [rax+8], rcx
0x180189737  push    rbp
0x180189738  push    rsi
0x180189739  push    rdi
0x18018973a  push    r12
0x18018973c  push    r13
0x18018973e  push    r14
0x180189740  push    r15
0x180189742  mov     rbp, rsp
0x180189745  sub     rsp, 70h
0x180189749  mov     rsi, r9
0x18018974c  mov     rbx, r8
0x18018974f  mov     rdi, rdx
0x180189752  mov     r14, rcx
0x180189755  xor     r12d, r12d
0x180189758  mov     [rbp+ppszPathOut], r12
0x18018975c  xor     edx, edx
0x18018975e  lea     rcx, [rbp+ppszPathOut]
0x180189762  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180189767  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x18018976b  lea     edx, [r12+1]; dwFlags
0x180189770  mov     rcx, rbx; pszPathIn
0x180189773  call    cs:__imp_PathAllocCanonicalize
0x18018977a  nop     dword ptr [rax+rax+00h]
0x18018977f  mov     ebx, eax
0x180189781  test    eax, eax
0x180189783  jns     short loc_18018978C
0x180189785  mov     edx, 342h
0x18018978a  jmp     short loc_1801897B8
0x18018978c  mov     rcx, [rbp+ppszPathOut]; pszPath
0x180189790  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180189794  inc     rdx
0x180189797  cmp     [rcx+rdx*2], r12w
0x18018979c  jnz     short loc_180189794
0x18018979e  inc     rdx; cchPath
0x1801897a1  call    cs:__imp_PathCchRemoveFileSpec
0x1801897a8  nop     dword ptr [rax+rax+00h]
0x1801897ad  mov     ebx, eax
0x1801897af  test    eax, eax
0x1801897b1  jns     short loc_1801897D0
0x1801897b3  mov     edx, 348h; void *
0x1801897b8  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x1801897bf  mov     r9d, eax; char *
0x1801897c2  mov     rcx, [rbp+38h]; this
0x1801897c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801897cb  jmp     loc_180189B1D
0x1801897d0  mov     r15, [rbp+ppszPathOut]
0x1801897d4  cmp     r12w, [r15]
0x1801897d8  setz    r13b
0x1801897dc  mov     ecx, 5Ch ; '\'
0x1801897e1  test    r13b, r13b
0x1801897e4  jnz     loc_180189B1A
0x1801897ea  cmp     r12w, [r15]
0x1801897ee  jnz     short loc_1801897F5
0x1801897f0  mov     r13b, 1
0x1801897f3  jmp     short loc_180189803
0x1801897f5  cmp     cx, [r15]
0x1801897f9  jnz     loc_180189A11
0x1801897ff  mov     [r15], r12w
0x180189803  xorps   xmm0, xmm0
0x180189806  movups  xmmword ptr [rbp+pObjectName], xmm0
0x18018980a  mov     [rbp+var_8], r12d
0x18018980e  movups  xmmword ptr [rbp+lpPathName], xmm0
0x180189812  mov     [rbp+var_20], r12d
0x180189816  lea     r8, [rbp+pObjectName]; this
0x18018981a  mov     rdx, [rbp+ppszPathOut]; Src
0x18018981e  mov     rcx, r14; unsigned __int16 *
0x180189821  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x180189826  mov     ebx, eax
0x180189828  test    eax, eax
0x18018982a  js      loc_180189AE2
0x180189830  lea     r8, [rbp+lpPathName]; this
0x180189834  mov     rdx, [rbp+ppszPathOut]; Src
0x180189838  mov     rcx, rdi; unsigned __int16 *
0x18018983b  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x180189840  mov     ebx, eax
0x180189842  test    eax, eax
0x180189844  js      loc_180189ADB
0x18018984a  mov     rdx, [rbp+lpPathName+8]
0x18018984e  mov     rcx, [rbp+arg_28]
0x180189852  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x180189857  test    rax, rax
0x18018985a  jnz     loc_1801899E4
0x180189860  xor     edx, edx; lpSecurityAttributes
0x180189862  mov     rcx, [rbp+lpPathName+8]; lpPathName
0x180189866  call    cs:__imp_CreateDirectoryW
0x18018986d  nop     dword ptr [rax+rax+00h]
0x180189872  test    eax, eax
0x180189874  jnz     short loc_1801898D6
0x180189876  call    cs:__imp_GetLastError
0x18018987d  nop     dword ptr [rax+rax+00h]
0x180189882  mov     ebx, eax
0x180189884  test    eax, eax
0x180189886  jle     short loc_180189891
0x180189888  movzx   ebx, ax
0x18018988b  or      ebx, 80070000h
0x180189891  mov     eax, 800700B7h
0x180189896  cmp     ebx, eax
0x180189898  jz      short loc_1801898B9
0x18018989a  cmp     ebx, 80070005h
0x1801898a0  jz      short loc_1801898B9
0x1801898a2  cmp     ebx, 80070003h
0x1801898a8  jnz     short loc_1801898D2
0x1801898aa  mov     ebx, eax
0x1801898ac  mov     r9d, ebx
0x1801898af  mov     edx, 382h
0x1801898b4  jmp     loc_180189AEA
0x1801898b9  mov     rcx, [rbp+lpPathName+8]; lpFileName
0x1801898bd  call    cs:__imp_GetFileAttributesW
0x1801898c4  nop     dword ptr [rax+rax+00h]
0x1801898c9  cmp     eax, 0FFFFFFFFh
0x1801898cc  jz      short loc_1801898D6
0x1801898ce  test    al, 10h
0x1801898d0  jnz     short loc_1801898D6
0x1801898d2  test    ebx, ebx
0x1801898d4  js      short loc_1801898AC
0x1801898d6  mov     rdx, [rbp+ppszPathOut]
0x1801898da  mov     rcx, [rbp+arg_20]
0x1801898de  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x1801898e3  test    rax, rax
0x1801898e6  jz      loc_1801899C0
0x1801898ec  mov     [rbp+var_38], r12
0x1801898f0  lea     r8, [rbp+var_38]; unsigned __int64 *
0x1801898f4  mov     edx, 8000h; unsigned __int64
0x1801898f9  mov     rcx, [rbp+ppszPathOut]; unsigned __int16 *
0x1801898fd  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180189902  mov     ebx, eax
0x180189904  test    eax, eax
0x180189906  js      loc_180189ACD
0x18018990c  mov     rdi, [rbp+var_38]
0x180189910  lea     eax, [rdi+0Bh]
0x180189913  add     ax, ax
0x180189916  movzx   r12d, ax
0x18018991a  mov     ecx, r12d; unsigned __int64
0x18018991d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180189924  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180189929  mov     rbx, rax
0x18018992c  mov     [rbp+var_38], rax
0x180189930  test    rax, rax
0x180189933  jz      loc_180189AAD
0x180189939  mov     dword ptr [rax], 0
0x18018993f  movups  xmm0, xmmword ptr [rsi]
0x180189942  movdqu  xmmword ptr [rax+4], xmm0
0x180189947  mov     [rax+14h], di
0x18018994b  lea     rsi, [rdi+rdi]
0x18018994f  test    rsi, rsi
0x180189952  jz      short loc_18018998C
0x180189954  lea     rcx, [rax+16h]; void *
0x180189958  test    rcx, rcx
0x18018995b  jz      loc_180189A42
0x180189961  mov     r14, [rbp+ppszPathOut]
0x180189965  movzx   edi, di
0x180189968  add     rdi, rdi
0x18018996b  test    r14, r14
0x18018996e  jz      loc_180189A1A
0x180189974  cmp     rdi, rsi
0x180189977  jb      loc_180189A1A
0x18018997d  mov     r8, rsi; Size
0x180189980  mov     rdx, r14; Src
0x180189983  call    memcpy_0
0x180189988  mov     r14, [rbp+arg_0]
0x18018998c  movzx   r8d, r12w
0x180189990  mov     rdx, rbx
0x180189993  mov     rcx, [rbp+lpPathName+8]
0x180189997  call    WciSetReparsePointDataEx
0x18018999c  mov     edi, eax
0x18018999e  xor     r12d, r12d
0x1801899a1  test    eax, eax
0x1801899a3  js      loc_180189AA6
0x1801899a9  lea     edx, [r12+18h]; struct std::nothrow_t *
0x1801899ae  mov     rcx, rbx; void *
0x1801899b1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801899b6  mov     rdi, [rbp+arg_8]
0x1801899ba  mov     rsi, [rbp+arg_18]
0x1801899be  jmp     short loc_1801899D7
0x1801899c0  mov     rdx, [rbp+lpPathName+8]; LPWSTR
0x1801899c4  mov     rcx, [rbp+pObjectName+8]; pObjectName
0x1801899c8  call    ?CopyPermissions@Deployment@Common@@YAJPEBG0@Z; Common::Deployment::CopyPermissions(ushort const *,ushort const *)
0x1801899cd  mov     ebx, eax
0x1801899cf  test    eax, eax
0x1801899d1  js      loc_180189AD4
0x1801899d7  mov     rdx, [rbp+lpPathName+8]; unsigned __int16 *
0x1801899db  mov     rcx, [rbp+arg_28]; this
0x1801899df  call    ?InsertIgnoreDuplicates@StringSet@@QEAAJPEBG@Z; StringSet::InsertIgnoreDuplicates(ushort const *)
0x1801899e4  test    r13b, r13b
0x1801899e7  jnz     short loc_1801899EF
0x1801899e9  mov     word ptr [r15], 5Ch ; '\'
0x1801899ef  mov     rcx, [rbp+lpPathName+8]; void *
0x1801899f3  test    rcx, rcx
0x1801899f6  jz      short loc_1801899FE
0x1801899f8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801899fd  nop
0x1801899fe  mov     rcx, [rbp+pObjectName+8]; void *
0x180189a02  test    rcx, rcx
0x180189a05  jz      short loc_180189A0C
0x180189a07  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180189a0c  mov     ecx, 5Ch ; '\'
0x180189a11  add     r15, 2
0x180189a15  jmp     loc_1801897E1
0x180189a1a  mov     r8, rdi; Size
0x180189a1d  xor     edx, edx; Val
0x180189a1f  call    memset_0
0x180189a24  test    r14, r14
0x180189a27  jz      short loc_180189A42
0x180189a29  cmp     rdi, rsi
0x180189a2c  jnb     short loc_180189A59
0x180189a2e  call    cs:__imp__o__errno
0x180189a35  nop     dword ptr [rax+rax+00h]
0x180189a3a  mov     dword ptr [rax], 22h ; '"'
0x180189a40  jmp     short loc_180189A54
0x180189a42  call    cs:__imp__o__errno
0x180189a49  nop     dword ptr [rax+rax+00h]
0x180189a4e  mov     dword ptr [rax], 16h
0x180189a54  call    _invalid_parameter_noinfo
0x180189a59  mov     edi, 8000000Bh
0x180189a5e  mov     edx, 392h; void *
0x180189a63  mov     r9d, edi; char *
0x180189a66  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x180189a6d  mov     rcx, [rbp+38h]; this
0x180189a71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180189a76  nop
0x180189a77  mov     edx, 18h; struct std::nothrow_t *
0x180189a7c  mov     rcx, rbx; void *
0x180189a7f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180189a84  nop
0x180189a85  mov     rcx, [rbp+lpPathName+8]; void *
0x180189a89  test    rcx, rcx
0x180189a8c  jz      short loc_180189A94
0x180189a8e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180189a93  nop
0x180189a94  mov     rcx, [rbp+pObjectName+8]; void *
0x180189a98  test    rcx, rcx
0x180189a9b  jz      short loc_180189AA2
0x180189a9d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180189aa2  mov     ebx, edi
0x180189aa4  jmp     short loc_180189B1D
0x180189aa6  mov     edx, 393h
0x180189aab  jmp     short loc_180189A63
0x180189aad  mov     rcx, [rbp+38h]; this
0x180189ab1  mov     ebx, 8007000Eh
0x180189ab6  mov     r9d, ebx; char *
0x180189ab9  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x180189ac0  mov     edx, 38Eh; void *
0x180189ac5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180189aca  nop
0x180189acb  jmp     short loc_180189AFB
0x180189acd  mov     edx, 38Ah
0x180189ad2  jmp     short loc_180189AE7
0x180189ad4  mov     edx, 397h
0x180189ad9  jmp     short loc_180189AE7
0x180189adb  mov     edx, 364h
0x180189ae0  jmp     short loc_180189AE7
0x180189ae2  mov     edx, 363h; void *
0x180189ae7  mov     r9d, eax; char *
0x180189aea  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x180189af1  mov     rcx, [rbp+38h]; this
0x180189af5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180189afa  nop
0x180189afb  mov     rcx, [rbp+lpPathName+8]; void *
0x180189aff  test    rcx, rcx
0x180189b02  jz      short loc_180189B0A
0x180189b04  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180189b09  nop
0x180189b0a  mov     rcx, [rbp+pObjectName+8]; void *
0x180189b0e  test    rcx, rcx
0x180189b11  jz      short loc_180189B1D
0x180189b13  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180189b18  jmp     short loc_180189B1D
0x180189b1a  mov     ebx, r12d
0x180189b1d  lea     rcx, [rbp+ppszPathOut]
0x180189b21  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180189b26  mov     eax, ebx
0x180189b28  mov     rbx, [rsp+70h+arg_10]
0x180189b30  add     rsp, 70h
0x180189b34  pop     r15
0x180189b36  pop     r14
0x180189b38  pop     r13
0x180189b3a  pop     r12
0x180189b3c  pop     rdi
0x180189b3d  pop     rsi
0x180189b3e  pop     rbp
0x180189b3f  retn
```
