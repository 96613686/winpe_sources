# _CreateUri(ushort const *,IUri * *)

- ea: `0x18005494c`
- end: `0x1800549e7`
- name: `?_CreateUri@@YAJPEBGPEAPEAUIUri@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUri **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180054b38`

## callees

- `0x1800028d0`
- `0x18005494c`
- `0x180055ca0`

## import_xrefs

- `urlmon!CoInternetCombineUrl` at `0x1800549ae`
- `urlmon!CoInternetCombineUrl` at `0x1800549ae`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1800549c8`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1800549c8`

## pseudocode

```c
int __fastcall _CreateUri(const unsigned __int16 *a1, struct IUri **a2)
{
  int result; // eax
  DWORD pcchResult[4]; // [rsp+40h] [rbp-1028h] BYREF
  WCHAR pszResult[2048]; // [rsp+50h] [rbp-1018h] BYREF

  *a2 = 0;
  pcchResult[0] = 0;
  result = CoInternetCombineUrl(L"ms-appx:///", a1, 0x8000000u, pszResult, 0x800u, pcchResult, 0);
  if ( result >= 0 )
    return CreateUri(pszResult, 0x4000u, 0, a2);
  return result;
}

```

## disassembly

```asm
0x18005494c  push    rbx
0x18005494e  mov     eax, 1060h
0x180054953  call    _alloca_probe
0x180054958  sub     rsp, rax
0x18005495b  mov     rax, cs:__security_cookie
0x180054962  xor     rax, rsp
0x180054965  mov     [rsp+1068h+var_18], rax
0x18005496d  mov     rbx, rdx
0x180054970  mov     qword ptr [rdx], 0
0x180054977  lea     rax, [rsp+1068h+var_1028]
0x18005497c  mov     [rsp+1068h+dwReserved], 0; dwReserved
0x180054984  mov     rdx, rcx; pwzRelativeUrl
0x180054987  mov     [rsp+1068h+pcchResult], rax; pcchResult
0x18005498c  lea     rcx, pwzBaseUrl; "ms-appx:///"
0x180054993  mov     [rsp+1068h+cchResult], 800h; cchResult
0x18005499b  lea     r9, [rsp+1068h+pszResult]; pszResult
0x1800549a0  mov     [rsp+1068h+var_1028], 0
0x1800549a8  mov     r8d, 8000000h; dwCombineFlags
0x1800549ae  call    cs:__imp_CoInternetCombineUrl
0x1800549b4  test    eax, eax
0x1800549b6  js      short loc_1800549CE
0x1800549b8  mov     r9, rbx; ppURI
0x1800549bb  lea     rcx, [rsp+1068h+pszResult]; pwzURI
0x1800549c0  xor     r8d, r8d; dwReserved
0x1800549c3  mov     edx, 4000h; dwFlags
0x1800549c8  call    cs:__imp_CreateUri
0x1800549ce  mov     rcx, [rsp+1068h+var_18]
0x1800549d6  xor     rcx, rsp; StackCookie
0x1800549d9  call    __security_check_cookie
0x1800549de  add     rsp, 1060h
0x1800549e5  pop     rbx
0x1800549e6  retn
```
