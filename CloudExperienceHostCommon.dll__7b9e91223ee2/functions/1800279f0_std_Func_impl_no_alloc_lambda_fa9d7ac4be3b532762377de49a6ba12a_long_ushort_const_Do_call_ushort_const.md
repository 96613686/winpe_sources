# std::_Func_impl_no_alloc<_lambda_fa9d7ac4be3b532762377de49a6ba12a_,long,ushort const *>::_Do_call(ushort const * &&)

- ea: `0x1800279f0`
- end: `0x180027a73`
- name: `?_Do_call@?$_Func_impl_no_alloc@V_lambda_fa9d7ac4be3b532762377de49a6ba12a_@@JPEBG@std@@EEAAJ$$QEAPEBG@Z`
- size: `131`
- prototype: `__int64 __fastcall(__int64, const WCHAR **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800152cc`
- `0x180015310`
- `0x1800153f8`
- `0x1800279f0`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180027a11`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180027a11`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180027a3d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180027a3d`

## string_xrefs

- `0x180027a22`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\diagnosticoperations.cpp`
- `0x180027a4c`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\diagnosticoperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Func_impl_no_alloc<_lambda_fa9d7ac4be3b532762377de49a6ba12a_,long,unsigned short const *>::_Do_call(
        __int64 a1,
        const WCHAR **a2)
{
  const WCHAR *v2; // rdx
  const WCHAR *v3; // rcx
  HRESULT v4; // eax
  unsigned int LastError; // ebx
  const char *v6; // r9
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PWSTR ppszPathOut; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a2;
  v3 = *(const WCHAR **)(a1 + 8);
  ppszPathOut = 0;
  v4 = PathAllocCombine(v3, v2, 1u, &ppszPathOut);
  LastError = v4;
  if ( v4 >= 0 )
  {
    if ( DeleteFileW(ppszPathOut) )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x56,
                    (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\diagnosticoperations.cpp",
                    v6);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\diagnosticoperations.cpp",
      (const char *)(unsigned int)v4,
      v8);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
  return LastError;
}

```

## disassembly

```asm
0x1800279f0  push    rbx; int
0x1800279f2  sub     rsp, 20h
0x1800279f6  mov     rdx, [rdx]; pszMore
0x1800279f9  lea     r9, [rsp+28h+ppszPathOut]; ppszPathOut
0x1800279fe  mov     rcx, [rcx+8]; pszPathIn
0x180027a02  mov     r8d, 1; dwFlags
0x180027a08  mov     [rsp+28h+ppszPathOut], 0
0x180027a11  call    cs:__imp_PathAllocCombine
0x180027a17  mov     ebx, eax
0x180027a19  test    eax, eax
0x180027a1b  jns     short loc_180027A38
0x180027a1d  mov     rcx, [rsp+28h]; this
0x180027a22  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\cloudexperiencehost"...
0x180027a29  mov     r9d, eax; char *
0x180027a2c  mov     edx, 56h ; 'V'; void *
0x180027a31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a36  jmp     short loc_180027A61
0x180027a38  mov     rcx, [rsp+28h+ppszPathOut]; lpFileName
0x180027a3d  call    cs:__imp_DeleteFileW
0x180027a43  test    eax, eax
0x180027a45  jnz     short loc_180027A5F
0x180027a47  mov     rcx, [rsp+28h]; this
0x180027a4c  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\cloudexperiencehost"...
0x180027a53  lea     edx, [rax+56h]; void *
0x180027a56  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027a5b  mov     ebx, eax
0x180027a5d  jmp     short loc_180027A61
0x180027a5f  xor     ebx, ebx
0x180027a61  lea     rcx, [rsp+28h+ppszPathOut]
0x180027a66  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180027a6b  mov     eax, ebx
0x180027a6d  add     rsp, 20h
0x180027a71  pop     rbx
0x180027a72  retn
```
