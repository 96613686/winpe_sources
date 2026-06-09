# IsSpellCheckFacilityPresent(void)

- ea: `0x18027791c`
- end: `0x1802779c4`
- name: `?IsSpellCheckFacilityPresent@@YA_NXZ`
- size: `168`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18027001c`

## callees

- `0x18013bad0`
- `0x18013c916`
- `0x180143a74`
- `0x18027791c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180277955`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180277955`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18027799e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18027799e`

## string_xrefs

- `0x18027797e`: `%s\msspellcheckingfacility.dll`

## pseudocode

```c
bool IsSpellCheckFacilityPresent(void)
{
  char v0; // bl
  WCHAR Buffer[264]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR pszPath[264]; // [rsp+230h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x208u);
  v0 = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    memset_0(pszPath, 0, 0x208u);
    if ( (int)StringCchPrintfW(pszPath, 0x104u, L"%s\\msspellcheckingfacility.dll", Buffer) >= 0 )
      return PathFileExistsW(pszPath);
  }
  return v0;
}

```

## disassembly

```asm
0x18027791c  push    rbx
0x18027791e  sub     rsp, 450h
0x180277925  mov     rax, cs:__security_cookie
0x18027792c  xor     rax, rsp
0x18027792f  mov     [rsp+458h+var_18], rax
0x180277937  xor     edx, edx; Val
0x180277939  lea     rcx, [rsp+458h+Buffer]; void *
0x18027793e  mov     r8d, 208h; Size
0x180277944  call    memset_0
0x180277949  mov     edx, 104h; uSize
0x18027794e  lea     rcx, [rsp+458h+Buffer]; lpBuffer
0x180277953  xor     bl, bl
0x180277955  call    cs:__imp_GetSystemDirectoryW
0x18027795b  test    eax, eax
0x18027795d  jz      short loc_1802779A9
0x18027795f  xor     edx, edx; Val
0x180277961  lea     rcx, [rsp+458h+pszPath]; void *
0x180277969  mov     r8d, 208h; Size
0x18027796f  call    memset_0
0x180277974  lea     r9, [rsp+458h+Buffer]
0x180277979  mov     edx, 104h; unsigned __int64
0x18027797e  lea     r8, aSMsspellchecki; "%s\\msspellcheckingfacility.dll"
0x180277985  lea     rcx, [rsp+458h+pszPath]; unsigned __int16 *
0x18027798d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180277992  test    eax, eax
0x180277994  js      short loc_1802779A9
0x180277996  lea     rcx, [rsp+458h+pszPath]; pszPath
0x18027799e  call    cs:__imp_PathFileExistsW
0x1802779a4  test    eax, eax
0x1802779a6  setnz   bl
0x1802779a9  mov     al, bl
0x1802779ab  mov     rcx, [rsp+458h+var_18]
0x1802779b3  xor     rcx, rsp; StackCookie
0x1802779b6  call    __security_check_cookie
0x1802779bb  add     rsp, 450h
0x1802779c2  pop     rbx
0x1802779c3  retn
```
