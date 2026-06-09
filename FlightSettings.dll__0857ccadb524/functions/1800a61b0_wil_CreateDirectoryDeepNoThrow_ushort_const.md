# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x1800a61b0`
- end: `0x1800a6332`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `386`
- prototype: `__int64 __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x1800a61b0`
- `0x1800a66ac`
- `0x1800c1d64`
- `0x1800c1ed4`

## callees

- `0x180005020`
- `0x18000505c`
- `0x18000cc8c`
- `0x18001e6d4`
- `0x180041c44`
- `0x1800a61b0`
- `0x1800a746c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a61d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a62df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a61d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a62df`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a61c7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a62d5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a61c7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a62d5`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800a61f4`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800a61f4`

## string_xrefs

- `0x1800a6257`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800a62ad`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800a62fa`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
int __fastcall wil::CreateDirectoryDeepNoThrow(const WCHAR *this, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  const unsigned __int16 *v4; // rdx
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rax
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rsi
  int DirectoryDeepNoThrow; // eax
  const unsigned __int16 *v11; // rdx
  int v12; // edi
  __int64 v13; // rdx
  const struct std::nothrow_t *v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  __int64 v16; // rdx
  unsigned int v17; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PCWSTR ppszRootEnd; // [rsp+48h] [rbp+10h] BYREF

  if ( !CreateDirectoryW(this, 0) )
  {
    LastError = GetLastError();
    if ( LastError == 3 )
    {
      ppszRootEnd = 0;
      if ( PathCchSkipRoot(this, &ppszRootEnd) >= 0 )
      {
        if ( *ppszRootEnd )
        {
          v5 = wil::find_last_path_segment(this, v4) - this;
          if ( v5 )
          {
            v6 = 2 * (v5 + 1);
            if ( !is_mul_ok(v5 + 1, 2u) )
              v6 = -1;
            v7 = (unsigned __int16 *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
            v8 = v7;
            if ( !v7 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x82,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                (const char *)0x8007000ELL,
                v17);
              return -2147024882;
            }
            DirectoryDeepNoThrow = StringCchCopyNW(v7, v5 + 1, this, v5);
            v12 = DirectoryDeepNoThrow;
            if ( DirectoryDeepNoThrow < 0 )
            {
              v13 = 131;
LABEL_14:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v13,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                (const char *)(unsigned int)DirectoryDeepNoThrow,
                v17);
              operator delete(v8, v15);
              return v12;
            }
            DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)v8, v11);
            v12 = DirectoryDeepNoThrow;
            if ( DirectoryDeepNoThrow < 0 )
            {
              v13 = 132;
              goto LABEL_14;
            }
            operator delete(v8, v14);
          }
        }
      }
      if ( !CreateDirectoryW(this, 0) )
      {
        LastError = GetLastError();
        if ( LastError != 183 )
        {
          if ( LastError )
          {
            v16 = 139;
            return wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)v16,
                     (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                     (const char *)LastError,
                     v17);
          }
        }
      }
    }
    else if ( LastError != 183 && LastError )
    {
      v16 = 145;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v16,
               (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
               (const char *)LastError,
               v17);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800a61b0  mov     [rsp+arg_0], rbx
0x1800a61b5  mov     [rsp+arg_10], rbp
0x1800a61ba  push    rsi
0x1800a61bb  push    rdi
0x1800a61bc  push    r14; unsigned int
0x1800a61be  sub     rsp, 20h
0x1800a61c2  xor     edx, edx; lpSecurityAttributes
0x1800a61c4  mov     rbx, rcx
0x1800a61c7  call    cs:__imp_CreateDirectoryW
0x1800a61cd  xor     r14d, r14d
0x1800a61d0  test    eax, eax
0x1800a61d2  jnz     loc_1800A631D
0x1800a61d8  call    cs:__imp_GetLastError
0x1800a61de  cmp     eax, 3
0x1800a61e1  jnz     loc_1800A630B
0x1800a61e7  lea     rdx, [rsp+38h+ppszRootEnd]; ppszRootEnd
0x1800a61ec  mov     [rsp+38h+ppszRootEnd], r14
0x1800a61f1  mov     rcx, rbx; pszPath
0x1800a61f4  call    cs:__imp_PathCchSkipRoot
0x1800a61fa  test    eax, eax
0x1800a61fc  js      loc_1800A62D0
0x1800a6202  mov     rax, [rsp+38h+ppszRootEnd]
0x1800a6207  cmp     [rax], r14w
0x1800a620b  jz      loc_1800A62D0
0x1800a6211  mov     rcx, rbx; lpStringSource
0x1800a6214  call    ?find_last_path_segment@wil@@YAPEBGPEBG@Z; wil::find_last_path_segment(ushort const *)
0x1800a6219  mov     rdi, rax
0x1800a621c  sub     rdi, rbx
0x1800a621f  sar     rdi, 1
0x1800a6222  jz      loc_1800A62D0
0x1800a6228  lea     rcx, [r14-1]
0x1800a622c  lea     rbp, [rdi+1]
0x1800a6230  lea     eax, [r14+2]
0x1800a6234  mul     rbp
0x1800a6237  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a623e  cmovb   rax, rcx
0x1800a6242  mov     rcx, rax; unsigned __int64
0x1800a6245  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800a624a  mov     rsi, rax
0x1800a624d  test    rax, rax
0x1800a6250  jnz     short loc_1800A6277
0x1800a6252  mov     rcx, [rsp+38h]; this
0x1800a6257  lea     r8, aOnecoreInterna_10; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a625e  mov     ebx, 8007000Eh
0x1800a6263  mov     edx, 82h; void *
0x1800a6268  mov     r9d, ebx; char *
0x1800a626b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6270  mov     eax, ebx
0x1800a6272  jmp     loc_1800A631F
0x1800a6277  mov     r9, rdi; unsigned __int64
0x1800a627a  mov     r8, rbx; unsigned __int16 *
0x1800a627d  mov     rdx, rbp; unsigned __int64
0x1800a6280  mov     rcx, rsi; unsigned __int16 *
0x1800a6283  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800a6288  mov     edi, eax
0x1800a628a  test    eax, eax
0x1800a628c  jns     short loc_1800A6295
0x1800a628e  mov     edx, 83h
0x1800a6293  jmp     short loc_1800A62A8
0x1800a6295  mov     rcx, rsi; this
0x1800a6298  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x1800a629d  mov     edi, eax
0x1800a629f  test    eax, eax
0x1800a62a1  jns     short loc_1800A62C8
0x1800a62a3  mov     edx, 84h; void *
0x1800a62a8  mov     rcx, [rsp+38h]; this
0x1800a62ad  lea     r8, aOnecoreInterna_10; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a62b4  mov     r9d, eax; char *
0x1800a62b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a62bc  mov     rcx, rsi; void *
0x1800a62bf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a62c4  mov     eax, edi
0x1800a62c6  jmp     short loc_1800A631F
0x1800a62c8  mov     rcx, rsi; void *
0x1800a62cb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a62d0  xor     edx, edx; lpSecurityAttributes
0x1800a62d2  mov     rcx, rbx; lpPathName
0x1800a62d5  call    cs:__imp_CreateDirectoryW
0x1800a62db  test    eax, eax
0x1800a62dd  jnz     short loc_1800A631D
0x1800a62df  call    cs:__imp_GetLastError
0x1800a62e5  cmp     eax, 0B7h
0x1800a62ea  jz      short loc_1800A631D
0x1800a62ec  test    eax, eax
0x1800a62ee  jz      short loc_1800A631D
0x1800a62f0  mov     edx, 8Bh; void *
0x1800a62f5  mov     rcx, [rsp+38h]; this
0x1800a62fa  lea     r8, aOnecoreInterna_10; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a6301  mov     r9d, eax; char *
0x1800a6304  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a6309  jmp     short loc_1800A631F
0x1800a630b  cmp     eax, 0B7h
0x1800a6310  jz      short loc_1800A631D
0x1800a6312  test    eax, eax
0x1800a6314  jz      short loc_1800A631D
0x1800a6316  mov     edx, 91h
0x1800a631b  jmp     short loc_1800A62F5
0x1800a631d  xor     eax, eax
0x1800a631f  mov     rbx, [rsp+38h+arg_0]
0x1800a6324  mov     rbp, [rsp+38h+arg_10]
0x1800a6329  add     rsp, 20h
0x1800a632d  pop     r14
0x1800a632f  pop     rdi
0x1800a6330  pop     rsi
0x1800a6331  retn
```
