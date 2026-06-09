# _lambda_a0398f4cf8f11e0aa3a2732166078300_::operator()(ushort const *)

- ea: `0x18002366c`
- end: `0x180023764`
- name: `??R_lambda_a0398f4cf8f11e0aa3a2732166078300_@@QEBA@PEBG@Z`
- size: `248`
- prototype: `__int64 __fastcall(PCWSTR *, const WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800279d0`

## callees

- `0x1800152cc`
- `0x180015310`
- `0x1800153f8`
- `0x18002366c`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180023697`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800236dc`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180023697`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800236dc`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18002371a`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18002371a`

## string_xrefs

- `0x1800236a8`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\diagnosticoperations.cpp`
- `0x1800236ed`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\diagnosticoperations.cpp`
- `0x180023729`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\diagnosticoperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall _lambda_a0398f4cf8f11e0aa3a2732166078300_::operator()(PCWSTR *a1, const WCHAR *a2)
{
  HRESULT v4; // eax
  unsigned int LastError; // ebx
  const WCHAR *v6; // rcx
  HRESULT v7; // eax
  const char *v8; // r9
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PWSTR ppszPathOut; // [rsp+30h] [rbp+8h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+40h] [rbp+18h] BYREF

  lpExistingFileName = 0;
  v4 = PathAllocCombine(*a1, a2, 1u, (PWSTR *)&lpExistingFileName);
  LastError = v4;
  if ( v4 >= 0 )
  {
    v6 = a1[1];
    ppszPathOut = 0;
    v7 = PathAllocCombine(v6, a2, 1u, &ppszPathOut);
    LastError = v7;
    if ( v7 >= 0 )
    {
      if ( CopyFileW(lpExistingFileName, ppszPathOut, 0) )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
        LastError = 0;
        goto LABEL_9;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x48,
                    (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\diagnosticoperations.cpp",
                    v8);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\diagnosticoperations.cpp",
        (const char *)(unsigned int)v7,
        v10);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\diagnosticoperations.cpp",
      (const char *)(unsigned int)v4,
      v10);
  }
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpExistingFileName);
  return LastError;
}

```

## disassembly

```asm
0x18002366c  mov     rax, rsp
0x18002366f  mov     [rax+10h], rbx
0x180023673  mov     [rax+20h], rsi
0x180023677  push    rdi; int
0x180023678  sub     rsp, 20h
0x18002367c  mov     rsi, rcx
0x18002367f  mov     qword ptr [rax+18h], 0
0x180023687  mov     rcx, [rcx]; pszPathIn
0x18002368a  lea     r9, [rax+18h]; ppszPathOut
0x18002368e  mov     r8d, 1; dwFlags
0x180023694  mov     rdi, rdx
0x180023697  call    cs:__imp_PathAllocCombine
0x18002369d  mov     ebx, eax
0x18002369f  test    eax, eax
0x1800236a1  jns     short loc_1800236C1
0x1800236a3  mov     rcx, [rsp+28h]; this
0x1800236a8  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800236af  mov     r9d, eax; char *
0x1800236b2  mov     edx, 48h ; 'H'; void *
0x1800236b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800236bc  jmp     loc_180023748
0x1800236c1  mov     rcx, [rsi+8]; pszPathIn
0x1800236c5  lea     r9, [rsp+28h+ppszPathOut]; ppszPathOut
0x1800236ca  mov     r8d, 1; dwFlags
0x1800236d0  mov     [rsp+28h+ppszPathOut], 0
0x1800236d9  mov     rdx, rdi; pszMore
0x1800236dc  call    cs:__imp_PathAllocCombine
0x1800236e2  mov     ebx, eax
0x1800236e4  test    eax, eax
0x1800236e6  jns     short loc_18002370D
0x1800236e8  mov     rcx, [rsp+28h]; this
0x1800236ed  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800236f4  mov     r9d, eax; char *
0x1800236f7  mov     edx, 48h ; 'H'; void *
0x1800236fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023701  lea     rcx, [rsp+28h+ppszPathOut]
0x180023706  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002370b  jmp     short loc_180023748
0x18002370d  mov     rdx, [rsp+28h+ppszPathOut]; lpNewFileName
0x180023712  xor     r8d, r8d; bFailIfExists
0x180023715  mov     rcx, [rsp+28h+lpExistingFileName]; lpExistingFileName
0x18002371a  call    cs:__imp_CopyFileW
0x180023720  test    eax, eax
0x180023722  jnz     short loc_18002373C
0x180023724  mov     rcx, [rsp+28h]; this
0x180023729  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\cloudexperiencehost"...
0x180023730  lea     edx, [rax+48h]; void *
0x180023733  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023738  mov     ebx, eax
0x18002373a  jmp     short loc_180023701
0x18002373c  lea     rcx, [rsp+28h+ppszPathOut]
0x180023741  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180023746  xor     ebx, ebx
0x180023748  lea     rcx, [rsp+28h+lpExistingFileName]
0x18002374d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180023752  mov     rsi, [rsp+28h+arg_18]
0x180023757  mov     eax, ebx
0x180023759  mov     rbx, [rsp+28h+arg_8]
0x18002375e  add     rsp, 20h
0x180023762  pop     rdi
0x180023763  retn
```
