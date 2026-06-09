# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x18003c1d8`
- end: `0x18003c35a`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `386`
- prototype: `int __fastcall(const WCHAR *this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x18003c1d8`
- `0x18003c360`
- `0x18003dcf8`
- `0x18003de68`

## callees

- `0x18000abc4`
- `0x18000abfc`
- `0x18001208c`
- `0x18001fb04`
- `0x1800237b8`
- `0x18002ca4c`
- `0x18003c1d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c307`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003c1ef`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003c2fd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003c1ef`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003c2fd`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18003c21c`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18003c21c`

## string_xrefs

- `0x18003c27f`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18003c2d5`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18003c322`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rdx
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
0x18003c1d8  mov     [rsp+arg_0], rbx
0x18003c1dd  mov     [rsp+arg_10], rbp
0x18003c1e2  push    rsi
0x18003c1e3  push    rdi
0x18003c1e4  push    r14; unsigned int
0x18003c1e6  sub     rsp, 20h
0x18003c1ea  xor     edx, edx; lpSecurityAttributes
0x18003c1ec  mov     rbx, rcx
0x18003c1ef  call    cs:__imp_CreateDirectoryW
0x18003c1f5  xor     r14d, r14d
0x18003c1f8  test    eax, eax
0x18003c1fa  jnz     loc_18003C345
0x18003c200  call    cs:__imp_GetLastError
0x18003c206  cmp     eax, 3
0x18003c209  jnz     loc_18003C333
0x18003c20f  lea     rdx, [rsp+38h+ppszRootEnd]; ppszRootEnd
0x18003c214  mov     [rsp+38h+ppszRootEnd], r14
0x18003c219  mov     rcx, rbx; pszPath
0x18003c21c  call    cs:__imp_PathCchSkipRoot
0x18003c222  test    eax, eax
0x18003c224  js      loc_18003C2F8
0x18003c22a  mov     rax, [rsp+38h+ppszRootEnd]
0x18003c22f  cmp     [rax], r14w
0x18003c233  jz      loc_18003C2F8
0x18003c239  mov     rcx, rbx; lpStringSource
0x18003c23c  call    ?find_last_path_segment@wil@@YAPEBGPEBG@Z; wil::find_last_path_segment(ushort const *)
0x18003c241  mov     rdi, rax
0x18003c244  sub     rdi, rbx
0x18003c247  sar     rdi, 1
0x18003c24a  jz      loc_18003C2F8
0x18003c250  lea     rcx, [r14-1]
0x18003c254  lea     rbp, [rdi+1]
0x18003c258  lea     eax, [r14+2]
0x18003c25c  mul     rbp
0x18003c25f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003c266  cmovb   rax, rcx
0x18003c26a  mov     rcx, rax; unsigned __int64
0x18003c26d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003c272  mov     rsi, rax
0x18003c275  test    rax, rax
0x18003c278  jnz     short loc_18003C29F
0x18003c27a  mov     rcx, [rsp+38h]; this
0x18003c27f  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003c286  mov     ebx, 8007000Eh
0x18003c28b  mov     edx, 82h; void *
0x18003c290  mov     r9d, ebx; char *
0x18003c293  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c298  mov     eax, ebx
0x18003c29a  jmp     loc_18003C347
0x18003c29f  mov     r9, rdi; unsigned __int64
0x18003c2a2  mov     r8, rbx; unsigned __int16 *
0x18003c2a5  mov     rdx, rbp; unsigned __int64
0x18003c2a8  mov     rcx, rsi; unsigned __int16 *
0x18003c2ab  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18003c2b0  mov     edi, eax
0x18003c2b2  test    eax, eax
0x18003c2b4  jns     short loc_18003C2BD
0x18003c2b6  mov     edx, 83h
0x18003c2bb  jmp     short loc_18003C2D0
0x18003c2bd  mov     rcx, rsi; this
0x18003c2c0  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x18003c2c5  mov     edi, eax
0x18003c2c7  test    eax, eax
0x18003c2c9  jns     short loc_18003C2F0
0x18003c2cb  mov     edx, 84h; void *
0x18003c2d0  mov     rcx, [rsp+38h]; this
0x18003c2d5  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003c2dc  mov     r9d, eax; char *
0x18003c2df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c2e4  mov     rcx, rsi; void *
0x18003c2e7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003c2ec  mov     eax, edi
0x18003c2ee  jmp     short loc_18003C347
0x18003c2f0  mov     rcx, rsi; void *
0x18003c2f3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003c2f8  xor     edx, edx; lpSecurityAttributes
0x18003c2fa  mov     rcx, rbx; lpPathName
0x18003c2fd  call    cs:__imp_CreateDirectoryW
0x18003c303  test    eax, eax
0x18003c305  jnz     short loc_18003C345
0x18003c307  call    cs:__imp_GetLastError
0x18003c30d  cmp     eax, 0B7h
0x18003c312  jz      short loc_18003C345
0x18003c314  test    eax, eax
0x18003c316  jz      short loc_18003C345
0x18003c318  mov     edx, 8Bh; void *
0x18003c31d  mov     rcx, [rsp+38h]; this
0x18003c322  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003c329  mov     r9d, eax; char *
0x18003c32c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003c331  jmp     short loc_18003C347
0x18003c333  cmp     eax, 0B7h
0x18003c338  jz      short loc_18003C345
0x18003c33a  test    eax, eax
0x18003c33c  jz      short loc_18003C345
0x18003c33e  mov     edx, 91h
0x18003c343  jmp     short loc_18003C31D
0x18003c345  xor     eax, eax
0x18003c347  mov     rbx, [rsp+38h+arg_0]
0x18003c34c  mov     rbp, [rsp+38h+arg_10]
0x18003c351  add     rsp, 20h
0x18003c355  pop     r14
0x18003c357  pop     rdi
0x18003c358  pop     rsi
0x18003c359  retn
```
