# IEFavResolver::GetParentFolderPath(ushort const *,ushort *,int)

- ea: `0x180017f60`
- end: `0x180017fec`
- name: `?GetParentFolderPath@IEFavResolver@@AEAAJPEBGPEAGH@Z`
- size: `140`
- prototype: `int(IEFavResolver *__hidden this, const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x180018d94`
- `0x180018f0c`
- `0x180019088`

## callees

- `0x180002ce0`
- `0x18000d17c`
- `0x180017f60`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x180017fa1`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x180017fa1`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180017fb2`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180017fb2`

## pseudocode

```c
HRESULT __fastcall IEFavResolver::GetParentFolderPath(
        IEFavResolver *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  HRESULT result; // eax
  WCHAR pszPath[264]; // [rsp+20h] [rbp-228h] BYREF

  result = StringCchCopyW(pszPath, 0x104u, a2);
  if ( result >= 0 )
  {
    result = PathCchRemoveBackslash(pszPath, 0x104u);
    if ( result >= 0 )
    {
      result = PathCchRemoveFileSpec(pszPath, 0x104u);
      if ( result >= 0 )
        return StringCchCopyW(a3, 0x104u, pszPath);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180017f60  mov     [rsp+arg_0], rbx
0x180017f65  push    rdi
0x180017f66  sub     rsp, 240h
0x180017f6d  mov     rax, cs:__security_cookie
0x180017f74  xor     rax, rsp
0x180017f77  mov     [rsp+248h+var_18], rax
0x180017f7f  mov     rbx, r8
0x180017f82  lea     rcx, [rsp+248h+pszPath]; unsigned __int16 *
0x180017f87  mov     r8, rdx; unsigned __int16 *
0x180017f8a  mov     edi, 104h
0x180017f8f  mov     edx, edi; unsigned __int64
0x180017f91  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017f96  test    eax, eax
0x180017f98  js      short loc_180017FCB
0x180017f9a  mov     edx, edi; cchPath
0x180017f9c  lea     rcx, [rsp+248h+pszPath]; pszPath
0x180017fa1  call    cs:__imp_PathCchRemoveBackslash
0x180017fa7  test    eax, eax
0x180017fa9  js      short loc_180017FCB
0x180017fab  mov     edx, edi; cchPath
0x180017fad  lea     rcx, [rsp+248h+pszPath]; pszPath
0x180017fb2  call    cs:__imp_PathCchRemoveFileSpec
0x180017fb8  test    eax, eax
0x180017fba  js      short loc_180017FCB
0x180017fbc  lea     r8, [rsp+248h+pszPath]; unsigned __int16 *
0x180017fc1  mov     edx, edi; unsigned __int64
0x180017fc3  mov     rcx, rbx; unsigned __int16 *
0x180017fc6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017fcb  mov     rcx, [rsp+248h+var_18]
0x180017fd3  xor     rcx, rsp; StackCookie
0x180017fd6  call    __security_check_cookie
0x180017fdb  mov     rbx, [rsp+248h+arg_0]
0x180017fe3  add     rsp, 240h
0x180017fea  pop     rdi
0x180017feb  retn
```
