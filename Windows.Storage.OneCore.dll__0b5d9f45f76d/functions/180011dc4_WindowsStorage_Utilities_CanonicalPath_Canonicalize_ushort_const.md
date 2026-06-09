# WindowsStorage::Utilities::CanonicalPath::_Canonicalize(ushort const *)

- ea: `0x180011dc4`
- end: `0x180011ef3`
- name: `?_Canonicalize@CanonicalPath@Utilities@WindowsStorage@@AEAAXPEBG@Z`
- size: `303`
- prototype: `void __fastcall(LPWSTR *ppszExt, LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callers

- `0x180011aa4`
- `0x180011b98`
- `0x180015a3c`

## callees

- `0x180010654`
- `0x180010670`
- `0x18001182c`
- `0x1800118f0`
- `0x180011dc4`
- `0x180011f20`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180011e05`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180011e49`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180011e05`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180011e49`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x180011e83`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x180011e83`

## string_xrefs

- `0x180011e62`: `onecore\base\windows.storage\src\CanonicalPath.h`
- `0x180011e94`: `onecore\base\windows.storage\src\CanonicalPath.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WindowsStorage::Utilities::CanonicalPath::_Canonicalize(LPWSTR *ppszExt, LPCWSTR lpFileName)
{
  unsigned __int64 FullPathNameW; // rcx
  const char *v5; // r9
  const WCHAR *v6; // rdx
  const WCHAR *v7; // r10
  HRESULT Extension; // eax
  WCHAR **v9; // rdx
  WCHAR *v10; // rcx
  WCHAR *v11; // rcx
  PCWSTR v12; // rcx
  LPWSTR lpBuffer[2]; // [rsp+20h] [rbp-28h] BYREF
  const WCHAR *v14; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  unsigned __int64 v16; // [rsp+70h] [rbp+28h] BYREF

  *(_OWORD *)lpBuffer = 0;
  v14 = 0;
  std::vector<unsigned short>::_Construct_n<>(lpBuffer);
  FullPathNameW = GetFullPathNameW(lpFileName, v14 - lpBuffer[0], lpBuffer[0], ppszExt + 1);
  v6 = v14;
  v7 = lpBuffer[0];
  if ( FullPathNameW > v14 - lpBuffer[0] )
  {
    v16 = FullPathNameW;
    std::vector<unsigned short>::_Reallocate<0>(lpBuffer, &v16);
    FullPathNameW = GetFullPathNameW(lpFileName, v14 - lpBuffer[0], lpBuffer[0], ppszExt + 1);
    v6 = v14;
    v7 = lpBuffer[0];
  }
  if ( !FullPathNameW )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecore\\base\\windows.storage\\src\\CanonicalPath.h",
      v5);
  Extension = PathCchFindExtension(v7, v6 - v7, (PCWSTR *)ppszExt);
  if ( Extension < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecore\\base\\windows.storage\\src\\CanonicalPath.h",
      (const char *)(unsigned int)Extension,
      (int)lpBuffer[0]);
  v9 = ppszExt + 2;
  if ( ppszExt + 2 != lpBuffer )
  {
    v10 = *v9;
    *v9 = lpBuffer[0];
    lpBuffer[0] = v10;
    v11 = ppszExt[3];
    ppszExt[3] = lpBuffer[1];
    lpBuffer[1] = v11;
    v12 = ppszExt[4];
    ppszExt[4] = (LPWSTR)v14;
    v14 = v12;
  }
  std::vector<unsigned short>::_Tidy(lpBuffer);
}

```

## disassembly

```asm
0x180011dc4  push    rbp
0x180011dc6  push    rbx
0x180011dc7  push    rsi
0x180011dc8  push    rdi
0x180011dc9  mov     rbp, rsp
0x180011dcc  sub     rsp, 48h
0x180011dd0  mov     rdi, rdx
0x180011dd3  mov     rbx, rcx
0x180011dd6  xorps   xmm0, xmm0
0x180011dd9  movdqu  xmmword ptr [rbp+lpBuffer], xmm0
0x180011dde  mov     [rbp+var_18], 0
0x180011de6  lea     rcx, [rbp+lpBuffer]
0x180011dea  call    ??$_Construct_n@$$V@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Construct_n<>(unsigned __int64)
0x180011def  nop
0x180011df0  mov     r8, [rbp+lpBuffer]; lpBuffer
0x180011df4  mov     rdx, [rbp+var_18]
0x180011df8  sub     rdx, r8
0x180011dfb  sar     rdx, 1; nBufferLength
0x180011dfe  lea     r9, [rbx+8]; lpFilePart
0x180011e02  mov     rcx, rdi; lpFileName
0x180011e05  call    cs:__imp_GetFullPathNameW
0x180011e0b  mov     ecx, eax
0x180011e0d  mov     rdx, [rbp+var_18]
0x180011e11  mov     rax, rdx
0x180011e14  mov     r10, [rbp+lpBuffer]
0x180011e18  sub     rax, r10
0x180011e1b  sar     rax, 1
0x180011e1e  cmp     rcx, rax
0x180011e21  jbe     short loc_180011E59
0x180011e23  mov     [rbp+arg_0], rcx
0x180011e27  lea     rdx, [rbp+arg_0]
0x180011e2b  lea     rcx, [rbp+lpBuffer]
0x180011e2f  call    ??$_Reallocate@$0A@@?$vector@GV?$allocator@G@std@@@std@@AEAAXAEA_K@Z; std::vector<ushort>::_Reallocate<0>(unsigned __int64 &)
0x180011e34  mov     r8, [rbp+lpBuffer]; lpBuffer
0x180011e38  mov     rdx, [rbp+var_18]
0x180011e3c  sub     rdx, r8
0x180011e3f  sar     rdx, 1; nBufferLength
0x180011e42  lea     r9, [rbx+8]; lpFilePart
0x180011e46  mov     rcx, rdi; lpFileName
0x180011e49  call    cs:__imp_GetFullPathNameW
0x180011e4f  mov     ecx, eax
0x180011e51  mov     rdx, [rbp+var_18]
0x180011e55  mov     r10, [rbp+lpBuffer]
0x180011e59  mov     rax, [rbp+20h]
0x180011e5d  test    rcx, rcx
0x180011e60  jnz     short loc_180011E77
0x180011e62  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\windows.storage\\src\\Ca"...
0x180011e69  mov     edx, 102h; void *
0x180011e6e  mov     rcx, rax; this
0x180011e71  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180011e77  sub     rdx, r10
0x180011e7a  sar     rdx, 1; cchPath
0x180011e7d  mov     r8, rbx; ppszExt
0x180011e80  mov     rcx, r10; pszPath
0x180011e83  call    cs:__imp_PathCchFindExtension
0x180011e89  mov     rcx, [rbp+20h]; this
0x180011e8d  test    eax, eax
0x180011e8f  jns     short loc_180011EA6
0x180011e91  mov     r9d, eax; char *
0x180011e94  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\windows.storage\\src\\Ca"...
0x180011e9b  mov     edx, 105h; void *
0x180011ea0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180011ea6  lea     rdx, [rbx+10h]
0x180011eaa  lea     rax, [rbp+lpBuffer]
0x180011eae  cmp     rdx, rax
0x180011eb1  jz      short loc_180011EE1
0x180011eb3  mov     rcx, [rdx]
0x180011eb6  mov     rax, [rbp+lpBuffer]
0x180011eba  mov     [rdx], rax
0x180011ebd  mov     [rbp+lpBuffer], rcx
0x180011ec1  mov     rcx, [rdx+8]
0x180011ec5  mov     rax, [rbp+lpBuffer+8]
0x180011ec9  mov     [rdx+8], rax
0x180011ecd  mov     [rbp+lpBuffer+8], rcx
0x180011ed1  mov     rcx, [rdx+10h]
0x180011ed5  mov     rax, [rbp+var_18]
0x180011ed9  mov     [rdx+10h], rax
0x180011edd  mov     [rbp+var_18], rcx
0x180011ee1  lea     rcx, [rbp+lpBuffer]
0x180011ee5  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180011eea  add     rsp, 48h
0x180011eee  pop     rdi
0x180011eef  pop     rsi
0x180011ef0  pop     rbx
0x180011ef1  pop     rbp
0x180011ef2  retn
```
