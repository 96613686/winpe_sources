# Microsoft::Resources::CStringResolverInternal::_BuildPri(void)

- ea: `0x1800aac98`
- end: `0x1800aaf60`
- name: `?_BuildPri@CStringResolverInternal@Resources@Microsoft@@AEAAJXZ`
- size: `712`
- prototype: `__int64 __fastcall(Microsoft::Resources::CStringResolverInternal *__hidden this)`
- caller_count: `3`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800aa89c`
- `0x1800aaa40`
- `0x1800aab54`

## callees

- `0x18000c880`
- `0x18002c8d0`
- `0x180032148`
- `0x1800364a8`
- `0x1800371a8`
- `0x1800576b4`
- `0x18007ae10`
- `0x180083aa8`
- `0x1800862f0`
- `0x1800867dc`
- `0x18009cc08`
- `0x1800aac98`
- `0x1800ab08c`
- `0x1800ab2c8`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aad87`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aad87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aad0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aad76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aae1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aaec5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aad0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aad76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aae1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aaec5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aad19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aae2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aaed3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aad19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aae2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aaed3`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800aadf0`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800aadf0`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800aadd4`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800aadd4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Resources::CStringResolverInternal::_BuildPri(
        Microsoft::Resources::CStringResolverInternal *this)
{
  int FileContents; // ebx
  __int64 v3; // rdx
  void *v4; // rsi
  HANDLE ProcessHeap; // rax
  __int64 v7; // rcx
  SIZE_T v8; // rbx
  HANDLE v9; // rax
  void *v10; // rax
  __int64 v11; // rdx
  const char *v12; // r9
  unsigned int LastError; // esi
  void *v14; // rbx
  HANDLE v15; // rax
  unsigned int v16; // edx
  Microsoft::Resources::Runtime::CResourceManagerInternal *v17; // rcx
  Microsoft::Resources::Runtime::CResourceManagerInternal *v18; // rax
  Microsoft::Resources::Runtime::CResourceManagerInternal *v19; // rax
  void *v20; // rbx
  HANDLE v21; // rax
  unsigned int v22[2]; // [rsp+20h] [rbp-268h] BYREF
  Microsoft::Resources::Runtime::CResourceManagerInternal *v23; // [rsp+28h] [rbp-260h]
  Microsoft::Resources::CStringResolverInternal *v24; // [rsp+30h] [rbp-258h]
  char v25; // [rsp+38h] [rbp-250h]
  WCHAR PathName[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  *(_QWORD *)v22 = 0;
  Microsoft::Resources::CStringResolverInternal::_ResetPackageResources(this);
  v24 = this;
  v25 = 1;
  FileContents = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1));
  if ( FileContents < 0 )
  {
    v3 = 388;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\stringresolver\\src\\cstringresolverinternal.cpp",
      (const char *)(unsigned int)FileContents,
      v22[0]);
    v4 = (void *)*((_QWORD *)this + 4);
    if ( v4 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
      *((_QWORD *)this + 4) = 0;
    }
    return (unsigned int)FileContents;
  }
  FileContents = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 1) + 8LL))(
                   *((_QWORD *)this + 1),
                   v22);
  if ( FileContents < 0 )
  {
    v3 = 390;
    goto LABEL_3;
  }
  if ( !*(_QWORD *)v22 )
    return 0;
  if ( DefArray_Size(1, *(_QWORD *)v22) )
  {
    v8 = DefArray_Size(v7, *(_QWORD *)v22);
    v9 = GetProcessHeap();
    v10 = HeapAlloc(v9, 8u, v8);
  }
  else
  {
    v10 = 0;
  }
  *((_QWORD *)this + 4) = v10;
  if ( !v10 )
  {
    v11 = 395;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\stringresolver\\src\\cstringresolverinternal.cpp",
      (const char *)0x8007000ELL,
      v22[0]);
    v20 = (void *)*((_QWORD *)this + 4);
    if ( v20 )
    {
      v21 = GetProcessHeap();
      HeapFree(v21, 0, v20);
      *((_QWORD *)this + 4) = 0;
    }
    return 2147942414LL;
  }
  FileContents = Microsoft::Resources::Build::FileBuilder::GenerateFileContents(
                   *((Microsoft::Resources::Build::FileBuilder **)this + 1),
                   v10,
                   v22[0],
                   (unsigned int *)this + 10);
  if ( FileContents < 0 )
  {
    v3 = 400;
    goto LABEL_3;
  }
  GetTempPath2W(260);
  if ( GetTempFileNameW(PathName, L"StringResolver", 0, (LPWSTR)this + 56) )
  {
    FileContents = Microsoft::Resources::Build::FileBuilder::WriteToFile(
                     *((Microsoft::Resources::Build::FileBuilder **)this + 1),
                     (const unsigned __int16 *)this + 56);
    if ( FileContents < 0 )
    {
      v3 = 410;
      goto LABEL_3;
    }
    v17 = (Microsoft::Resources::Runtime::CResourceManagerInternal *)*((_QWORD *)this + 7);
    if ( v17 )
    {
      Microsoft::Resources::Runtime::CResourceManagerInternal::`scalar deleting destructor'(v17, v16);
      *((_QWORD *)this + 7) = 0;
    }
    v18 = (Microsoft::Resources::Runtime::CResourceManagerInternal *)operator new(
                                                                       0xC8u,
                                                                       (const struct std::nothrow_t *)&std::nothrow);
    v23 = v18;
    if ( v18 )
      v19 = (Microsoft::Resources::Runtime::CResourceManagerInternal *)Microsoft::Resources::Runtime::CResourceManagerInternal::CResourceManagerInternal(v18);
    else
      v19 = 0;
    *((_QWORD *)this + 7) = v19;
    if ( !v19 )
    {
      v11 = 420;
      goto LABEL_29;
    }
    FileContents = Microsoft::Resources::Runtime::CResourceManagerInternal::InitializeForFile(
                     v19,
                     (const unsigned __int16 *)this + 56);
    if ( FileContents < 0 )
    {
      v3 = 422;
      goto LABEL_3;
    }
    FileContents = Microsoft::Resources::Runtime::CResourceManagerInternal::GetResourceIndex(
                     *((Microsoft::Resources::Runtime::CResourceManagerInternal **)this + 7),
                     L"SR_Package",
                     (struct Microsoft::Resources::Runtime::CResourceIndexInternal **)this + 8);
    if ( FileContents < 0 )
    {
      v3 = 423;
      goto LABEL_3;
    }
    FileContents = Microsoft::Resources::CStringResolverInternal::_SetContext(this);
    if ( FileContents < 0 )
    {
      v3 = 424;
      goto LABEL_3;
    }
    *((_DWORD *)this + 18) = 1;
    return 0;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x198,
                (unsigned int)"onecoreuap\\base\\mrt\\runtime\\stringresolver\\src\\cstringresolverinternal.cpp",
                v12);
  v14 = (void *)*((_QWORD *)this + 4);
  if ( v14 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v14);
    *((_QWORD *)this + 4) = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x1800aac98  push    rbx
0x1800aac9a  push    rbp
0x1800aac9b  push    rsi
0x1800aac9c  push    rdi
0x1800aac9d  sub     rsp, 268h
0x1800aaca4  mov     rax, cs:__security_cookie
0x1800aacab  xor     rax, rsp
0x1800aacae  mov     [rsp+288h+var_38], rax
0x1800aacb6  mov     rdi, rcx
0x1800aacb9  xor     ebp, ebp
0x1800aacbb  mov     qword ptr [rsp+288h+var_268], rbp; int
0x1800aacc0  call    ?_ResetPackageResources@CStringResolverInternal@Resources@Microsoft@@AEAAXXZ; Microsoft::Resources::CStringResolverInternal::_ResetPackageResources(void)
0x1800aacc5  mov     [rsp+288h+var_258], rdi
0x1800aacca  mov     [rsp+288h+var_250], 1
0x1800aaccf  mov     rcx, [rdi+8]
0x1800aacd3  mov     rax, [rcx]
0x1800aacd6  mov     rax, [rax+10h]
0x1800aacda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aacdf  mov     ebx, eax
0x1800aace1  test    eax, eax
0x1800aace3  jns     short loc_1800AAD2A
0x1800aace5  mov     edx, 184h; void *
0x1800aacea  mov     rcx, [rsp+288h]; this
0x1800aacf2  mov     r9d, ebx; char *
0x1800aacf5  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\mrt\\runtime\\stringr"...
0x1800aacfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aad01  nop
0x1800aad02  mov     rsi, [rdi+20h]
0x1800aad06  test    rsi, rsi
0x1800aad09  jz      short loc_1800AAD23
0x1800aad0b  call    cs:__imp_GetProcessHeap
0x1800aad11  mov     r8, rsi; lpMem
0x1800aad14  xor     edx, edx; dwFlags
0x1800aad16  mov     rcx, rax; hHeap
0x1800aad19  call    cs:__imp_HeapFree
0x1800aad1f  mov     [rdi+20h], rbp
0x1800aad23  mov     eax, ebx
0x1800aad25  jmp     loc_1800AAF44
0x1800aad2a  mov     rcx, [rdi+8]
0x1800aad2e  mov     rax, [rcx]
0x1800aad31  lea     rdx, [rsp+288h+var_268]
0x1800aad36  mov     rax, [rax+8]
0x1800aad3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aad3f  mov     ebx, eax
0x1800aad41  test    eax, eax
0x1800aad43  jns     short loc_1800AAD4C
0x1800aad45  mov     edx, 186h
0x1800aad4a  jmp     short loc_1800AACEA
0x1800aad4c  mov     rdx, qword ptr [rsp+288h+var_268]
0x1800aad51  test    rdx, rdx
0x1800aad54  jz      loc_1800AAF42
0x1800aad5a  mov     ecx, 1
0x1800aad5f  call    _DefArray_Size
0x1800aad64  test    rax, rax
0x1800aad67  jz      short loc_1800AAD8F
0x1800aad69  mov     rdx, qword ptr [rsp+288h+var_268]
0x1800aad6e  call    _DefArray_Size
0x1800aad73  mov     rbx, rax
0x1800aad76  call    cs:__imp_GetProcessHeap
0x1800aad7c  mov     r8, rbx; dwBytes
0x1800aad7f  mov     edx, 8; dwFlags
0x1800aad84  mov     rcx, rax; hHeap
0x1800aad87  call    cs:__imp_HeapAlloc
0x1800aad8d  jmp     short loc_1800AAD92
0x1800aad8f  mov     rax, rbp
0x1800aad92  mov     [rdi+20h], rax
0x1800aad96  test    rax, rax
0x1800aad99  jnz     short loc_1800AADA5
0x1800aad9b  mov     edx, 18Bh
0x1800aada0  jmp     loc_1800AAEA1
0x1800aada5  lea     r9, [rdi+28h]; unsigned int *
0x1800aada9  mov     r8d, [rsp+288h+var_268]; unsigned int
0x1800aadae  mov     rdx, rax; void *
0x1800aadb1  mov     rcx, [rdi+8]; this
0x1800aadb5  call    ?GenerateFileContents@FileBuilder@Build@Resources@Microsoft@@QEAAJPEAXIPEAI@Z; Microsoft::Resources::Build::FileBuilder::GenerateFileContents(void *,uint,uint *)
0x1800aadba  mov     ebx, eax
0x1800aadbc  test    eax, eax
0x1800aadbe  jns     short loc_1800AADCA
0x1800aadc0  mov     edx, 190h
0x1800aadc5  jmp     loc_1800AACEA
0x1800aadca  lea     rdx, [rsp+288h+PathName]
0x1800aadcf  mov     ecx, 104h
0x1800aadd4  call    cs:__imp_GetTempPath2W
0x1800aadda  lea     rsi, [rdi+70h]
0x1800aadde  mov     r9, rsi; lpTempFileName
0x1800aade1  xor     r8d, r8d; uUnique
0x1800aade4  lea     rdx, PrefixString; "StringResolver"
0x1800aadeb  lea     rcx, [rsp+288h+PathName]; lpPathName
0x1800aadf0  call    cs:__imp_GetTempFileNameW
0x1800aadf6  test    eax, eax
0x1800aadf8  jnz     short loc_1800AAE3D
0x1800aadfa  mov     rcx, [rsp+288h]; this
0x1800aae02  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\mrt\\runtime\\stringr"...
0x1800aae09  mov     edx, 198h; void *
0x1800aae0e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800aae13  mov     esi, eax
0x1800aae15  mov     rbx, [rdi+20h]
0x1800aae19  test    rbx, rbx
0x1800aae1c  jz      short loc_1800AAE36
0x1800aae1e  call    cs:__imp_GetProcessHeap
0x1800aae24  mov     r8, rbx; lpMem
0x1800aae27  xor     edx, edx; dwFlags
0x1800aae29  mov     rcx, rax; hHeap
0x1800aae2c  call    cs:__imp_HeapFree
0x1800aae32  mov     [rdi+20h], rbp
0x1800aae36  mov     eax, esi
0x1800aae38  jmp     loc_1800AAF44
0x1800aae3d  mov     rdx, rsi; unsigned __int16 *
0x1800aae40  mov     rcx, [rdi+8]; this
0x1800aae44  call    ?WriteToFile@FileBuilder@Build@Resources@Microsoft@@QEAAJPEBG@Z; Microsoft::Resources::Build::FileBuilder::WriteToFile(ushort const *)
0x1800aae49  mov     ebx, eax
0x1800aae4b  test    eax, eax
0x1800aae4d  jns     short loc_1800AAE59
0x1800aae4f  mov     edx, 19Ah
0x1800aae54  jmp     loc_1800AACEA
0x1800aae59  mov     rcx, [rdi+38h]; this
0x1800aae5d  test    rcx, rcx
0x1800aae60  jz      short loc_1800AAE6B
0x1800aae62  call    ??_GCResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::`scalar deleting destructor'(uint)
0x1800aae67  mov     [rdi+38h], rbp
0x1800aae6b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800aae72  mov     ecx, 0C8h; unsigned __int64
0x1800aae77  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800aae7c  mov     [rsp+288h+var_260], rax
0x1800aae81  test    rax, rax
0x1800aae84  jz      short loc_1800AAE90
0x1800aae86  mov     rcx, rax; this
0x1800aae89  call    ??0CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::Runtime::CResourceManagerInternal::CResourceManagerInternal(void)
0x1800aae8e  jmp     short loc_1800AAE93
0x1800aae90  mov     rax, rbp
0x1800aae93  mov     [rdi+38h], rax
0x1800aae97  test    rax, rax
0x1800aae9a  jnz     short loc_1800AAEE4
0x1800aae9c  mov     edx, 1A4h; void *
0x1800aaea1  mov     r9d, 8007000Eh; char *
0x1800aaea7  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\mrt\\runtime\\stringr"...
0x1800aaeae  mov     rcx, [rsp+288h]; this
0x1800aaeb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aaebb  nop
0x1800aaebc  mov     rbx, [rdi+20h]
0x1800aaec0  test    rbx, rbx
0x1800aaec3  jz      short loc_1800AAEDD
0x1800aaec5  call    cs:__imp_GetProcessHeap
0x1800aaecb  mov     r8, rbx; lpMem
0x1800aaece  xor     edx, edx; dwFlags
0x1800aaed0  mov     rcx, rax; hHeap
0x1800aaed3  call    cs:__imp_HeapFree
0x1800aaed9  mov     [rdi+20h], rbp
0x1800aaedd  mov     eax, 8007000Eh
0x1800aaee2  jmp     short loc_1800AAF44
0x1800aaee4  mov     rdx, rsi; unsigned __int16 *
0x1800aaee7  mov     rcx, rax; this
0x1800aaeea  call    ?InitializeForFile@CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAJPEBG@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::InitializeForFile(ushort const *)
0x1800aaeef  mov     ebx, eax
0x1800aaef1  test    eax, eax
0x1800aaef3  jns     short loc_1800AAEFF
0x1800aaef5  mov     edx, 1A6h
0x1800aaefa  jmp     loc_1800AACEA
0x1800aaeff  lea     r8, [rdi+40h]; struct Microsoft::Resources::Runtime::CResourceIndexInternal **
0x1800aaf03  lea     rdx, aSrPackage; "SR_Package"
0x1800aaf0a  mov     rcx, [rdi+38h]; this
0x1800aaf0e  call    ?GetResourceIndex@CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAJPEBGPEAPEAVCResourceIndexInternal@234@@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::GetResourceIndex(ushort const *,Microsoft::Resources::Runtime::CResourceIndexInternal * *)
0x1800aaf13  mov     ebx, eax
0x1800aaf15  test    eax, eax
0x1800aaf17  jns     short loc_1800AAF23
0x1800aaf19  mov     edx, 1A7h
0x1800aaf1e  jmp     loc_1800AACEA
0x1800aaf23  mov     rcx, rdi; this
0x1800aaf26  call    ?_SetContext@CStringResolverInternal@Resources@Microsoft@@AEAAJXZ; Microsoft::Resources::CStringResolverInternal::_SetContext(void)
0x1800aaf2b  mov     ebx, eax
0x1800aaf2d  test    eax, eax
0x1800aaf2f  jns     short loc_1800AAF3B
0x1800aaf31  mov     edx, 1A8h
0x1800aaf36  jmp     loc_1800AACEA
0x1800aaf3b  mov     dword ptr [rdi+48h], 1
0x1800aaf42  xor     eax, eax
0x1800aaf44  mov     rcx, [rsp+288h+var_38]
0x1800aaf4c  xor     rcx, rsp; StackCookie
0x1800aaf4f  call    __security_check_cookie
0x1800aaf54  add     rsp, 268h
0x1800aaf5b  pop     rdi
0x1800aaf5c  pop     rsi
0x1800aaf5d  pop     rbp
0x1800aaf5e  pop     rbx
0x1800aaf5f  retn
```
