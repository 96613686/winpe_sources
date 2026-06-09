# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x18003b488`
- end: `0x18003b5eb`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `355`
- prototype: `__int64 __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18003b488`
- `0x18003c1a0`
- `0x18003e904`
- `0x180052ce4`
- `0x1800c4f80`
- `0x1800c50d0`
- `0x1800c69f8`
- `0x1800fc0c0`

## callees

- `0x18003b488`
- `0x1800c8458`
- `0x1800ff298`
- `0x1801202a0`
- `0x180123774`
- `0x1801a7ee8`
- `0x1801a7fe0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b4a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b5a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b4a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b5a3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003b496`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003b595`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003b496`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003b595`

## string_xrefs

- `0x18003b517`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18003b56a`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18003b5cd`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
int __fastcall wil::CreateDirectoryDeepNoThrow(const WCHAR *this, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  unsigned __int64 *v4; // r8
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rbp
  unsigned __int64 v8; // rax
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx
  int DirectoryDeepNoThrow; // eax
  const unsigned __int16 *v12; // rdx
  int v13; // esi
  __int64 v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  const struct std::nothrow_t *v16; // rdx
  __int64 v17; // rdx
  unsigned int v18; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned __int64 v20; // [rsp+58h] [rbp+10h] BYREF

  if ( CreateDirectoryW(this, 0) )
    return 0;
  LastError = GetLastError();
  if ( LastError != 3 )
  {
    if ( LastError != 183 && LastError )
    {
      v17 = 145;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v17,
               (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
               (const char *)LastError,
               v18);
    }
    return 0;
  }
  v20 = 0;
  if ( wil::try_get_parent_path_range(this, (const unsigned __int16 *)&v20, v4) )
  {
    v6 = v20;
    v7 = v20 + 1;
    v8 = 2 * (v20 + 1);
    if ( !is_mul_ok(v20 + 1, 2u) )
      v8 = -1;
    v9 = (unsigned __int16 *)operator new[](v8, (const struct std::nothrow_t *)std::nothrow);
    v10 = v9;
    if ( !v9 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
        (const char *)0x8007000ELL,
        v18);
      return -2147024882;
    }
    DirectoryDeepNoThrow = StringCchCopyNW(v9, v7, this, v6);
    v13 = DirectoryDeepNoThrow;
    if ( DirectoryDeepNoThrow < 0 )
    {
      v14 = 131;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
        (const char *)(unsigned int)DirectoryDeepNoThrow,
        v18);
      operator delete(v10, v16);
      return v13;
    }
    DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)v10, v12);
    v13 = DirectoryDeepNoThrow;
    if ( DirectoryDeepNoThrow < 0 )
    {
      v14 = 132;
      goto LABEL_14;
    }
    operator delete(v10, v15);
  }
  if ( CreateDirectoryW(this, 0) )
    return 0;
  LastError = GetLastError();
  if ( LastError == 183 || !LastError )
    return 0;
  v17 = 139;
  return wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v17,
           (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
           (const char *)LastError,
           v18);
}

```

## disassembly

```asm
0x18003b488  push    rbx
0x18003b48a  push    rbp
0x18003b48b  push    rsi
0x18003b48c  push    rdi
0x18003b48d  sub     rsp, 28h
0x18003b491  xor     edx, edx; lpSecurityAttributes
0x18003b493  mov     rdi, rcx
0x18003b496  call    cs:__imp_CreateDirectoryW
0x18003b49c  test    eax, eax
0x18003b49e  jnz     short loc_18003B4B6
0x18003b4a0  call    cs:__imp_GetLastError
0x18003b4a6  cmp     eax, 3
0x18003b4a9  jz      short loc_18003B4C1
0x18003b4ab  cmp     eax, 0B7h
0x18003b4b0  jnz     loc_18003B5E1
0x18003b4b6  xor     eax, eax
0x18003b4b8  add     rsp, 28h
0x18003b4bc  pop     rdi
0x18003b4bd  pop     rsi
0x18003b4be  pop     rbp
0x18003b4bf  pop     rbx
0x18003b4c0  retn
0x18003b4c1  lea     rdx, [rsp+48h+arg_8]; unsigned __int16 *
0x18003b4c6  mov     [rsp+48h+arg_8], 0
0x18003b4cf  mov     rcx, rdi; lpStringSource
0x18003b4d2  call    ?try_get_parent_path_range@wil@@YA_NPEBGPEA_K@Z; wil::try_get_parent_path_range(ushort const *,unsigned __int64 *)
0x18003b4d7  test    al, al
0x18003b4d9  jz      loc_18003B590
0x18003b4df  mov     rsi, [rsp+48h+arg_8]
0x18003b4e4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003b4eb  mov     eax, 2
0x18003b4f0  lea     rbp, [rsi+1]
0x18003b4f4  mul     rbp
0x18003b4f7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003b4fe  cmovb   rax, rcx
0x18003b502  mov     rcx, rax; unsigned __int64
0x18003b505  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003b50a  mov     rbx, rax
0x18003b50d  test    rax, rax
0x18003b510  jnz     short loc_18003B534
0x18003b512  mov     rcx, [rsp+48h]; this
0x18003b517  lea     r8, aOnecoreInterna_9; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003b51e  mov     ebx, 8007000Eh
0x18003b523  mov     edx, 82h; void *
0x18003b528  mov     r9d, ebx; char *
0x18003b52b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b530  mov     eax, ebx
0x18003b532  jmp     short loc_18003B4B8
0x18003b534  mov     r9, rsi; unsigned __int64
0x18003b537  mov     r8, rdi; unsigned __int16 *
0x18003b53a  mov     rdx, rbp; unsigned __int64
0x18003b53d  mov     rcx, rbx; unsigned __int16 *
0x18003b540  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18003b545  mov     esi, eax
0x18003b547  test    eax, eax
0x18003b549  jns     short loc_18003B552
0x18003b54b  mov     edx, 83h
0x18003b550  jmp     short loc_18003B565
0x18003b552  mov     rcx, rbx; this
0x18003b555  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x18003b55a  mov     esi, eax
0x18003b55c  test    eax, eax
0x18003b55e  jns     short loc_18003B588
0x18003b560  mov     edx, 84h; void *
0x18003b565  mov     rcx, [rsp+48h]; this
0x18003b56a  lea     r8, aOnecoreInterna_9; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003b571  mov     r9d, eax; char *
0x18003b574  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b579  mov     rcx, rbx; void *
0x18003b57c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003b581  mov     eax, esi
0x18003b583  jmp     loc_18003B4B8
0x18003b588  mov     rcx, rbx; void *
0x18003b58b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003b590  xor     edx, edx; lpSecurityAttributes
0x18003b592  mov     rcx, rdi; lpPathName
0x18003b595  call    cs:__imp_CreateDirectoryW
0x18003b59b  test    eax, eax
0x18003b59d  jnz     loc_18003B4B6
0x18003b5a3  call    cs:__imp_GetLastError
0x18003b5a9  cmp     eax, 0B7h
0x18003b5ae  jz      loc_18003B4B6
0x18003b5b4  test    eax, eax
0x18003b5b6  jz      loc_18003B4B6
0x18003b5bc  mov     edx, 8Bh
0x18003b5c1  jmp     short loc_18003B5C8
0x18003b5c3  mov     edx, 91h; void *
0x18003b5c8  mov     rcx, [rsp+48h]; this
0x18003b5cd  lea     r8, aOnecoreInterna_9; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003b5d4  mov     r9d, eax; char *
0x18003b5d7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003b5dc  jmp     loc_18003B4B8
0x18003b5e1  test    eax, eax
0x18003b5e3  jz      loc_18003B4B6
0x18003b5e9  jmp     short loc_18003B5C3
```
