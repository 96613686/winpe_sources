# DiagnosticsElevatedManagerImpl::RunActionForAllFiles(ushort const *,ushort const *,std::function<long (ushort const *)>)

- ea: `0x1800150d8`
- end: `0x1800152c5`
- name: `?RunActionForAllFiles@DiagnosticsElevatedManagerImpl@@AEAAJPEBG0V?$function@$$A6AJPEBG@Z@std@@@Z`
- size: `493`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *, __int64 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023af0`
- `0x180023bf0`

## callees

- `0x1800150d8`
- `0x1800152cc`
- `0x1800152ec`
- `0x180015310`
- `0x1800153f8`
- `0x18001a540`
- `0x18001b004`
- `0x1800227ac`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015215`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180015121`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180015121`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001520b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001520b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001519a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001519a`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180015269`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180015269`

## string_xrefs

- `0x180015137`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\diagnosticoperations.cpp`
- `0x1800151f2`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\diagnosticoperations.cpp`
- `0x180015227`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\diagnosticoperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DiagnosticsElevatedManagerImpl::RunActionForAllFiles(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        __int64 *a4)
{
  HRESULT v5; // eax
  unsigned int LastError; // ebx
  __int64 v7; // rdx
  __int64 *v8; // rcx
  void (__fastcall *v9)(__int64 *, __int64); // rax
  char *FirstFileW; // rbx
  __int64 v12; // rcx
  int v13; // eax
  const char *v14; // r9
  __int64 v15; // rdx
  __int64 *v16; // rcx
  PWSTR ppszPathOut; // [rsp+20h] [rbp-E0h] BYREF
  char *v18; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v19[2]; // [rsp+30h] [rbp-D0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v19[1] = a4;
  ppszPathOut = 0;
  v5 = PathAllocCombine(a2, a3, 1u, &ppszPathOut);
  LastError = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\diagnosticoperations.cpp",
      (const char *)(unsigned int)v5,
      (int)ppszPathOut);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    v8 = (__int64 *)a4[7];
    if ( v8 )
    {
      v9 = *(void (__fastcall **)(__int64 *, __int64))(*v8 + 32);
LABEL_4:
      LOBYTE(v7) = v8 != a4;
      v9(v8, v7);
      a4[7] = 0;
    }
    return LastError;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(ppszPathOut, &FindFileData);
  v18 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        v19[0] = FindFileData.cFileName;
        v12 = a4[7];
        if ( !v12 )
        {
          std::_Xbad_function_call();
          goto LABEL_16;
        }
        v13 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v12 + 16LL))(v12, v19);
        if ( v13 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x30,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\diagnosticoperations.cpp",
            (const char *)(unsigned int)v13,
            (int)ppszPathOut);
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    if ( GetLastError() == 18 )
      goto LABEL_16;
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x35,
                  (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\diagnosticoperations.cpp",
                  v14);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v18);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    v8 = (__int64 *)a4[7];
    if ( v8 )
    {
      v7 = *v8;
      v9 = *(void (__fastcall **)(__int64 *, __int64))(*v8 + 32);
      goto LABEL_4;
    }
    return LastError;
  }
LABEL_16:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v18);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
  v16 = (__int64 *)a4[7];
  if ( v16 )
  {
    LOBYTE(v15) = v16 != a4;
    (*(void (__fastcall **)(__int64 *, __int64))(*v16 + 32))(v16, v15);
    a4[7] = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800150d8  push    rbp
0x1800150da  push    rbx
0x1800150db  push    rdi
0x1800150dc  lea     rbp, [rsp-1A0h]
0x1800150e4  sub     rsp, 2A0h
0x1800150eb  mov     rax, cs:__security_cookie
0x1800150f2  xor     rax, rsp
0x1800150f5  mov     [rbp+1B0h+var_20], rax
0x1800150fc  mov     rdi, r9
0x1800150ff  mov     r10, r8
0x180015102  mov     rcx, rdx; pszPathIn
0x180015105  mov     [rsp+2B0h+var_278], r9
0x18001510a  mov     [rsp+2B0h+ppszPathOut], 0; int
0x180015113  lea     r9, [rsp+2B0h+ppszPathOut]; ppszPathOut
0x180015118  mov     r8d, 1; dwFlags
0x18001511e  mov     rdx, r10; pszMore
0x180015121  call    cs:__imp_PathAllocCombine
0x180015127  mov     ebx, eax
0x180015129  test    eax, eax
0x18001512b  jns     short loc_18001517E
0x18001512d  mov     rcx, [rbp+1B8h]; this
0x180015134  mov     r9d, eax; char *
0x180015137  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\cloudexperiencehost"...
0x18001513e  mov     edx, 1Ch; void *
0x180015143  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015148  nop
0x180015149  lea     rcx, [rsp+2B0h+ppszPathOut]
0x18001514e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015153  nop
0x180015154  mov     rcx, [rdi+38h]
0x180015158  test    rcx, rcx
0x18001515b  jz      short loc_180015177
0x18001515d  mov     rax, [rcx]
0x180015160  mov     rax, [rax+20h]
0x180015164  cmp     rcx, rdi
0x180015167  setnz   dl
0x18001516a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001516f  mov     qword ptr [rdi+38h], 0
0x180015177  mov     eax, ebx
0x180015179  jmp     loc_1800152AB
0x18001517e  xor     edx, edx; Val
0x180015180  mov     r8d, 250h; Size
0x180015186  lea     rcx, [rsp+2B0h+FindFileData]; void *
0x18001518b  call    memset_0
0x180015190  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x180015195  mov     rcx, [rsp+2B0h+ppszPathOut]; lpFileName
0x18001519a  call    cs:__imp_FindFirstFileW
0x1800151a0  mov     rbx, rax
0x1800151a3  mov     [rsp+2B0h+var_288], rax
0x1800151a8  dec     rax
0x1800151ab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800151af  ja      loc_180015270
0x1800151b5  test    byte ptr [rsp+2B0h+FindFileData.dwFileAttributes], 10h
0x1800151ba  jnz     short loc_180015203
0x1800151bc  lea     rax, [rsp+2B0h+FindFileData.cFileName]
0x1800151c1  mov     [rsp+2B0h+var_280], rax
0x1800151c6  mov     rcx, [rdi+38h]
0x1800151ca  test    rcx, rcx
0x1800151cd  jz      loc_180015269
0x1800151d3  mov     rax, [rcx]
0x1800151d6  lea     rdx, [rsp+2B0h+var_280]
0x1800151db  mov     rax, [rax+10h]
0x1800151df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151e4  mov     rcx, [rbp+1B8h]; this
0x1800151eb  test    eax, eax
0x1800151ed  jns     short loc_180015203
0x1800151ef  mov     r9d, eax; char *
0x1800151f2  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800151f9  mov     edx, 30h ; '0'; void *
0x1800151fe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015203  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x180015208  mov     rcx, rbx; hFindFile
0x18001520b  call    cs:__imp_FindNextFileW
0x180015211  test    eax, eax
0x180015213  jnz     short loc_1800151B5
0x180015215  call    cs:__imp_GetLastError
0x18001521b  cmp     eax, 12h
0x18001521e  jz      short loc_180015270
0x180015220  mov     rcx, [rbp+1B8h]; this
0x180015227  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\cloudexperiencehost"...
0x18001522e  mov     edx, 35h ; '5'; void *
0x180015233  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015238  mov     ebx, eax
0x18001523a  lea     rcx, [rsp+2B0h+var_288]
0x18001523f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180015244  nop
0x180015245  lea     rcx, [rsp+2B0h+ppszPathOut]
0x18001524a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001524f  nop
0x180015250  mov     rcx, [rdi+38h]
0x180015254  test    rcx, rcx
0x180015257  jz      loc_180015177
0x18001525d  mov     rdx, [rcx]
0x180015260  mov     rax, [rdx+20h]
0x180015264  jmp     loc_180015164
0x180015269  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001526f  nop
0x180015270  lea     rcx, [rsp+2B0h+var_288]
0x180015275  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18001527a  nop
0x18001527b  lea     rcx, [rsp+2B0h+ppszPathOut]
0x180015280  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015285  nop
0x180015286  mov     rcx, [rdi+38h]
0x18001528a  test    rcx, rcx
0x18001528d  jz      short loc_1800152A9
0x18001528f  cmp     rcx, rdi
0x180015292  mov     rax, [rcx]
0x180015295  setnz   dl
0x180015298  mov     rax, [rax+20h]
0x18001529c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152a1  mov     qword ptr [rdi+38h], 0
0x1800152a9  xor     eax, eax
0x1800152ab  mov     rcx, [rbp+1B0h+var_20]
0x1800152b2  xor     rcx, rsp; StackCookie
0x1800152b5  call    __security_check_cookie
0x1800152ba  add     rsp, 2A0h
0x1800152c1  pop     rdi
0x1800152c2  pop     rbx
0x1800152c3  pop     rbp
0x1800152c4  retn
```
