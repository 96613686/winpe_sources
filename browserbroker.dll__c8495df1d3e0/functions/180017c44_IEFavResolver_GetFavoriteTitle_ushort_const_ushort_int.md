# IEFavResolver::GetFavoriteTitle(ushort const *,ushort *,int)

- ea: `0x180017c44`
- end: `0x180017cd4`
- name: `?GetFavoriteTitle@IEFavResolver@@AEAAJPEBGPEAGH@Z`
- size: `144`
- prototype: `int(IEFavResolver *__hidden this, const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `5`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x180018c10`
- `0x180018d94`
- `0x180018f0c`
- `0x180019088`
- `0x1800192f8`

## callees

- `0x180002ce0`
- `0x18000d17c`
- `0x180017c44`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180017c94`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180017c94`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveExtension` at `0x180017c85`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveExtension` at `0x180017c85`

## pseudocode

```c
HRESULT __fastcall IEFavResolver::GetFavoriteTitle(
        IEFavResolver *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  HRESULT result; // eax
  const unsigned __int16 *FileNameW; // rax
  WCHAR pszPath[264]; // [rsp+20h] [rbp-228h] BYREF

  result = StringCchCopyW(pszPath, 0x104u, a2);
  if ( result >= 0 )
  {
    result = PathCchRemoveExtension(pszPath, 0x104u);
    if ( result >= 0 )
    {
      FileNameW = PathFindFileNameW(pszPath);
      if ( FileNameW )
        return StringCchCopyW(a3, 0x104u, FileNameW);
      else
        return -2147467259;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180017c44  mov     [rsp+arg_0], rbx
0x180017c49  push    rdi
0x180017c4a  sub     rsp, 240h
0x180017c51  mov     rax, cs:__security_cookie
0x180017c58  xor     rax, rsp
0x180017c5b  mov     [rsp+248h+var_18], rax
0x180017c63  mov     rbx, r8
0x180017c66  lea     rcx, [rsp+248h+pszPath]; unsigned __int16 *
0x180017c6b  mov     r8, rdx; unsigned __int16 *
0x180017c6e  mov     edi, 104h
0x180017c73  mov     edx, edi; unsigned __int64
0x180017c75  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017c7a  test    eax, eax
0x180017c7c  js      short loc_180017CB3
0x180017c7e  mov     edx, edi; cchPath
0x180017c80  lea     rcx, [rsp+248h+pszPath]; pszPath
0x180017c85  call    cs:__imp_PathCchRemoveExtension
0x180017c8b  test    eax, eax
0x180017c8d  js      short loc_180017CB3
0x180017c8f  lea     rcx, [rsp+248h+pszPath]; pszPath
0x180017c94  call    cs:__imp_PathFindFileNameW
0x180017c9a  test    rax, rax
0x180017c9d  jz      short loc_180017CAE
0x180017c9f  mov     r8, rax; unsigned __int16 *
0x180017ca2  mov     edx, edi; unsigned __int64
0x180017ca4  mov     rcx, rbx; unsigned __int16 *
0x180017ca7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017cac  jmp     short loc_180017CB3
0x180017cae  mov     eax, 80004005h
0x180017cb3  mov     rcx, [rsp+248h+var_18]
0x180017cbb  xor     rcx, rsp; StackCookie
0x180017cbe  call    __security_check_cookie
0x180017cc3  mov     rbx, [rsp+248h+arg_0]
0x180017ccb  add     rsp, 240h
0x180017cd2  pop     rdi
0x180017cd3  retn
```
