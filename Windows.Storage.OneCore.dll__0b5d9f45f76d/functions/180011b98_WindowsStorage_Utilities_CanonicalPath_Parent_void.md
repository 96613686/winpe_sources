# WindowsStorage::Utilities::CanonicalPath::Parent(void)

- ea: `0x180011b98`
- end: `0x180011c3c`
- name: `?Parent@CanonicalPath@Utilities@WindowsStorage@@QEBA?AV123@XZ`
- size: `164`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path`

## callers

- `0x180011aa4`
- `0x180017c60`

## callees

- `0x180010670`
- `0x18001188c`
- `0x1800119a4`
- `0x180011b98`
- `0x180011dc4`
- `0x180011f20`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180011be2`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180011be2`

## string_xrefs

- `0x180011bf4`: `onecore\base\windows.storage\src\CanonicalPath.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsStorage::Utilities::CanonicalPath::Parent(__int64 a1, __int64 a2)
{
  HRESULT v3; // eax
  LPCWSTR *v4; // rcx
  int v6; // [rsp+20h] [rbp-28h]
  __int128 pszPath; // [rsp+28h] [rbp-20h] BYREF
  __int64 v8; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  pszPath = 0;
  v8 = 0;
  std::vector<unsigned short>::_Construct_n<unsigned short * const &,unsigned short * const &>(
    &pszPath,
    (__int64)(*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 16)) >> 1);
  v3 = PathCchRemoveFileSpec((PWSTR)pszPath, (v8 - (__int64)pszPath) >> 1);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xD7,
      (int)"onecore\\base\\windows.storage\\src\\CanonicalPath.h",
      (const char *)(unsigned int)v3,
      v6);
  *(_QWORD *)(a2 + 8) = 0;
  std::vector<unsigned short>::vector<unsigned short>(a2 + 16, &pszPath);
  WindowsStorage::Utilities::CanonicalPath::_Canonicalize((LPWSTR *)a2, *v4);
  std::vector<unsigned short>::_Tidy(&pszPath);
  return a2;
}

```

## disassembly

```asm
0x180011b98  mov     rax, rsp
0x180011b9b  mov     [rax+10h], rdx
0x180011b9f  push    rbx
0x180011ba0  sub     rsp, 40h
0x180011ba4  mov     rbx, rdx
0x180011ba7  xorps   xmm0, xmm0
0x180011baa  movdqu  xmmword ptr [rax-20h], xmm0
0x180011baf  mov     qword ptr [rax-10h], 0
0x180011bb7  lea     r8, [rcx+10h]
0x180011bbb  lea     r9, [r8+8]
0x180011bbf  mov     rdx, [r9]
0x180011bc2  sub     rdx, [r8]
0x180011bc5  sar     rdx, 1
0x180011bc8  lea     rcx, [rax-20h]
0x180011bcc  call    ??$_Construct_n@AEBQEAGAEBQEAG@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBQEAG1@Z; std::vector<ushort>::_Construct_n<ushort * const &,ushort * const &>(unsigned __int64,ushort * const &,ushort * const &)
0x180011bd1  nop
0x180011bd2  mov     rcx, qword ptr [rsp+48h+pszPath]; pszPath
0x180011bd7  mov     rdx, [rsp+48h+var_10]
0x180011bdc  sub     rdx, rcx
0x180011bdf  sar     rdx, 1; cchPath
0x180011be2  call    cs:__imp_PathCchRemoveFileSpec
0x180011be8  mov     rcx, [rsp+48h]; this
0x180011bed  test    eax, eax
0x180011bef  jns     short loc_180011C06
0x180011bf1  mov     r9d, eax; char *
0x180011bf4  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\windows.storage\\src\\Ca"...
0x180011bfb  mov     edx, 0D7h; void *
0x180011c00  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180011c06  mov     qword ptr [rbx+8], 0
0x180011c0e  lea     rcx, [rbx+10h]
0x180011c12  lea     rdx, [rsp+48h+pszPath]
0x180011c17  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<ushort>::vector<ushort>(std::vector<ushort> &&)
0x180011c1c  nop
0x180011c1d  mov     rdx, [rcx]; lpFileName
0x180011c20  mov     rcx, rbx; ppszExt
0x180011c23  call    ?_Canonicalize@CanonicalPath@Utilities@WindowsStorage@@AEAAXPEBG@Z; WindowsStorage::Utilities::CanonicalPath::_Canonicalize(ushort const *)
0x180011c28  nop
0x180011c29  lea     rcx, [rsp+48h+pszPath]
0x180011c2e  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180011c33  mov     rax, rbx
0x180011c36  add     rsp, 40h
0x180011c3a  pop     rbx
0x180011c3b  retn
```
