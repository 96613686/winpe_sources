# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x1800a2e18`
- end: `0x1800a2f9a`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `386`
- prototype: `__int64 __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x1800a2e18`
- `0x1800a2fa0`

## callees

- `0x18000cb80`
- `0x18000ed14`
- `0x180011ea4`
- `0x180021a0c`
- `0x180044c14`
- `0x1800a2e18`
- `0x1800a3c60`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x1800a2e2f`
- `KERNEL32!CreateDirectoryW` at `0x1800a2f3d`
- `KERNEL32!CreateDirectoryW` at `0x1800a2e2f`
- `KERNEL32!CreateDirectoryW` at `0x1800a2f3d`
- `KERNEL32!GetLastError` at `0x1800a2e40`
- `KERNEL32!GetLastError` at `0x1800a2f47`
- `KERNEL32!GetLastError` at `0x1800a2e40`
- `KERNEL32!GetLastError` at `0x1800a2f47`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800a2e5c`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800a2e5c`

## string_xrefs

- `0x1800a2ebf`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800a2f15`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800a2f62`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

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
0x1800a2e18  mov     [rsp+arg_0], rbx
0x1800a2e1d  mov     [rsp+arg_10], rbp
0x1800a2e22  push    rsi
0x1800a2e23  push    rdi
0x1800a2e24  push    r14; unsigned int
0x1800a2e26  sub     rsp, 20h
0x1800a2e2a  xor     edx, edx; lpSecurityAttributes
0x1800a2e2c  mov     rbx, rcx
0x1800a2e2f  call    cs:__imp_CreateDirectoryW
0x1800a2e35  xor     r14d, r14d
0x1800a2e38  test    eax, eax
0x1800a2e3a  jnz     loc_1800A2F85
0x1800a2e40  call    cs:__imp_GetLastError
0x1800a2e46  cmp     eax, 3
0x1800a2e49  jnz     loc_1800A2F73
0x1800a2e4f  lea     rdx, [rsp+38h+ppszRootEnd]; ppszRootEnd
0x1800a2e54  mov     [rsp+38h+ppszRootEnd], r14
0x1800a2e59  mov     rcx, rbx; pszPath
0x1800a2e5c  call    cs:__imp_PathCchSkipRoot
0x1800a2e62  test    eax, eax
0x1800a2e64  js      loc_1800A2F38
0x1800a2e6a  mov     rax, [rsp+38h+ppszRootEnd]
0x1800a2e6f  cmp     [rax], r14w
0x1800a2e73  jz      loc_1800A2F38
0x1800a2e79  mov     rcx, rbx; lpStringSource
0x1800a2e7c  call    ?find_last_path_segment@wil@@YAPEBGPEBG@Z; wil::find_last_path_segment(ushort const *)
0x1800a2e81  mov     rdi, rax
0x1800a2e84  sub     rdi, rbx
0x1800a2e87  sar     rdi, 1
0x1800a2e8a  jz      loc_1800A2F38
0x1800a2e90  lea     rcx, [r14-1]
0x1800a2e94  lea     rbp, [rdi+1]
0x1800a2e98  lea     eax, [r14+2]
0x1800a2e9c  mul     rbp
0x1800a2e9f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a2ea6  cmovb   rax, rcx
0x1800a2eaa  mov     rcx, rax; unsigned __int64
0x1800a2ead  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800a2eb2  mov     rsi, rax
0x1800a2eb5  test    rax, rax
0x1800a2eb8  jnz     short loc_1800A2EDF
0x1800a2eba  mov     rcx, [rsp+38h]; this
0x1800a2ebf  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a2ec6  mov     ebx, 8007000Eh
0x1800a2ecb  mov     edx, 82h; void *
0x1800a2ed0  mov     r9d, ebx; char *
0x1800a2ed3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2ed8  mov     eax, ebx
0x1800a2eda  jmp     loc_1800A2F87
0x1800a2edf  mov     r9, rdi; unsigned __int64
0x1800a2ee2  mov     r8, rbx; unsigned __int16 *
0x1800a2ee5  mov     rdx, rbp; unsigned __int64
0x1800a2ee8  mov     rcx, rsi; unsigned __int16 *
0x1800a2eeb  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800a2ef0  mov     edi, eax
0x1800a2ef2  test    eax, eax
0x1800a2ef4  jns     short loc_1800A2EFD
0x1800a2ef6  mov     edx, 83h
0x1800a2efb  jmp     short loc_1800A2F10
0x1800a2efd  mov     rcx, rsi; this
0x1800a2f00  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x1800a2f05  mov     edi, eax
0x1800a2f07  test    eax, eax
0x1800a2f09  jns     short loc_1800A2F30
0x1800a2f0b  mov     edx, 84h; void *
0x1800a2f10  mov     rcx, [rsp+38h]; this
0x1800a2f15  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a2f1c  mov     r9d, eax; char *
0x1800a2f1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2f24  mov     rcx, rsi; void *
0x1800a2f27  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a2f2c  mov     eax, edi
0x1800a2f2e  jmp     short loc_1800A2F87
0x1800a2f30  mov     rcx, rsi; void *
0x1800a2f33  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a2f38  xor     edx, edx; lpSecurityAttributes
0x1800a2f3a  mov     rcx, rbx; lpPathName
0x1800a2f3d  call    cs:__imp_CreateDirectoryW
0x1800a2f43  test    eax, eax
0x1800a2f45  jnz     short loc_1800A2F85
0x1800a2f47  call    cs:__imp_GetLastError
0x1800a2f4d  cmp     eax, 0B7h
0x1800a2f52  jz      short loc_1800A2F85
0x1800a2f54  test    eax, eax
0x1800a2f56  jz      short loc_1800A2F85
0x1800a2f58  mov     edx, 8Bh; void *
0x1800a2f5d  mov     rcx, [rsp+38h]; this
0x1800a2f62  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a2f69  mov     r9d, eax; char *
0x1800a2f6c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a2f71  jmp     short loc_1800A2F87
0x1800a2f73  cmp     eax, 0B7h
0x1800a2f78  jz      short loc_1800A2F85
0x1800a2f7a  test    eax, eax
0x1800a2f7c  jz      short loc_1800A2F85
0x1800a2f7e  mov     edx, 91h
0x1800a2f83  jmp     short loc_1800A2F5D
0x1800a2f85  xor     eax, eax
0x1800a2f87  mov     rbx, [rsp+38h+arg_0]
0x1800a2f8c  mov     rbp, [rsp+38h+arg_10]
0x1800a2f91  add     rsp, 20h
0x1800a2f95  pop     r14
0x1800a2f97  pop     rdi
0x1800a2f98  pop     rsi
0x1800a2f99  retn
```
