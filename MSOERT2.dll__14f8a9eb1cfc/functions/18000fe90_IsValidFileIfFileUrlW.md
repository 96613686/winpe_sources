# IsValidFileIfFileUrlW

- ea: `0x18000fe90`
- end: `0x18000ff1f`
- name: `IsValidFileIfFileUrlW`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000fe90`
- `0x180012fc0`

## import_xrefs

- `SHLWAPI!UrlCanonicalizeW` at `0x18000febe`
- `SHLWAPI!UrlCanonicalizeW` at `0x18000febe`
- `SHLWAPI!PathCreateFromUrlW` at `0x18000fee2`
- `SHLWAPI!PathCreateFromUrlW` at `0x18000fee2`
- `SHLWAPI!PathFileExistsW` at `0x18000fef1`
- `SHLWAPI!PathFileExistsW` at `0x18000fef1`

## pseudocode

```c
__int64 __fastcall IsValidFileIfFileUrlW(const WCHAR *a1)
{
  DWORD pcchCanonicalized[4]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR pszCanonicalized[264]; // [rsp+30h] [rbp-228h] BYREF

  pcchCanonicalized[0] = 260;
  if ( UrlCanonicalizeW(a1, pszCanonicalized, pcchCanonicalized, 0) )
    return 1;
  pcchCanonicalized[0] = 260;
  return PathCreateFromUrlW(pszCanonicalized, pszCanonicalized, pcchCanonicalized, 0)
      || PathFileExistsW(pszCanonicalized);
}

```

## disassembly

```asm
0x18000fe90  sub     rsp, 258h
0x18000fe97  mov     rax, cs:__security_cookie
0x18000fe9e  xor     rax, rsp
0x18000fea1  mov     [rsp+258h+var_18], rax
0x18000fea9  xor     r9d, r9d; dwFlags
0x18000feac  mov     [rsp+258h+pcchCanonicalized], 104h
0x18000feb4  lea     r8, [rsp+258h+pcchCanonicalized]; pcchCanonicalized
0x18000feb9  lea     rdx, [rsp+258h+pszCanonicalized]; pszCanonicalized
0x18000febe  call    cs:__imp_UrlCanonicalizeW
0x18000fec4  test    eax, eax
0x18000fec6  jnz     short loc_18000FF02
0x18000fec8  xor     r9d, r9d; dwFlags
0x18000fecb  mov     [rsp+258h+pcchCanonicalized], 104h
0x18000fed3  lea     r8, [rsp+258h+pcchCanonicalized]; pcchPath
0x18000fed8  lea     rdx, [rsp+258h+pszCanonicalized]; pszPath
0x18000fedd  lea     rcx, [rsp+258h+pszCanonicalized]; pszUrl
0x18000fee2  call    cs:__imp_PathCreateFromUrlW
0x18000fee8  test    eax, eax
0x18000feea  jnz     short loc_18000FF02
0x18000feec  lea     rcx, [rsp+258h+pszCanonicalized]; pszPath
0x18000fef1  call    cs:__imp_PathFileExistsW
0x18000fef7  xor     ecx, ecx
0x18000fef9  test    eax, eax
0x18000fefb  setnz   cl
0x18000fefe  mov     eax, ecx
0x18000ff00  jmp     short loc_18000FF07
0x18000ff02  mov     eax, 1
0x18000ff07  mov     rcx, [rsp+258h+var_18]
0x18000ff0f  xor     rcx, rsp; StackCookie
0x18000ff12  call    __security_check_cookie
0x18000ff17  add     rsp, 258h
0x18000ff1e  retn
```
