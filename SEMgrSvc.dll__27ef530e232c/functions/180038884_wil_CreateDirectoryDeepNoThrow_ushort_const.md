# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x180038884`
- end: `0x180038ab6`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `562`
- prototype: `__int64 __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path`

## callers

- `0x180038884`
- `0x18003b6a0`

## callees

- `0x1800049c4`
- `0x180004e4c`
- `0x18000c964`
- `0x180014898`
- `0x180038884`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180038928`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180038928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038a30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038a30`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003889b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180038a26`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003889b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180038a26`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800388c8`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800388c8`

## string_xrefs

- `0x180038974`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180038a4b`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180038a77`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
int __fastcall wil::CreateDirectoryDeepNoThrow(const WCHAR *this, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  __int64 v4; // r8
  const WCHAR *v5; // rdi
  int StringOrdinal; // eax
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // rax
  wil *v10; // rax
  wil *v11; // rbx
  unsigned int v13; // edi
  const WCHAR *v14; // rax
  unsigned __int16 *v15; // rdx
  unsigned __int16 *v16; // rcx
  int DirectoryDeepNoThrow; // eax
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rdx
  int cchValue; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  PCWSTR ppszRootEnd; // [rsp+58h] [rbp+10h] BYREF

  if ( CreateDirectoryW(this, 0) )
    return 0;
  LastError = GetLastError();
  if ( LastError == 3 )
  {
    ppszRootEnd = 0;
    if ( PathCchSkipRoot(this, &ppszRootEnd) < 0 || !*ppszRootEnd )
      goto LABEL_31;
    v4 = -1;
    do
      ++v4;
    while ( this[v4] );
    v5 = &this[v4];
    if ( v4 && *(v5 - 1) == 92 )
      LODWORD(v4) = v4 - 1;
    StringOrdinal = FindStringOrdinal(0x800000u, this, v4, L"\\", 1, 1);
    if ( StringOrdinal != -1 )
      v5 = &this[StringOrdinal + 1];
    v7 = v5 - this;
    if ( !v7 )
      goto LABEL_31;
    v8 = v7 + 1;
    v9 = 2 * (v7 + 1);
    if ( !is_mul_ok(v7 + 1, 2u) )
      v9 = -1;
    v10 = (wil *)operator new[](v9, (const struct std::nothrow_t *)std::nothrow);
    v11 = v10;
    if ( !v10 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)0x8007000ELL,
        cchValue);
      return -2147024882;
    }
    if ( v7 == -1 )
    {
      v13 = -2147024809;
    }
    else if ( v8 > 0x7FFFFFFF || v7 > 0x7FFFFFFE )
    {
      v13 = -2147024809;
      *(_WORD *)v10 = 0;
    }
    else
    {
      v14 = this;
      v15 = (unsigned __int16 *)v11;
      do
      {
        if ( !v7 )
          break;
        if ( !*v14 )
          break;
        *v15++ = *v14++;
        --v7;
        --v8;
      }
      while ( v8 );
      v16 = v15 - 1;
      v13 = v8 == 0 ? 0x8007007A : 0;
      if ( v8 )
        v16 = v15;
      *v16 = 0;
      if ( v8 )
      {
        DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow(v11, v15);
        v13 = DirectoryDeepNoThrow;
        if ( DirectoryDeepNoThrow < 0 )
        {
          v18 = (unsigned int)DirectoryDeepNoThrow;
          v19 = 132;
LABEL_38:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
            (const char *)v18,
            cchValue);
          operator delete(v11);
          return v13;
        }
        operator delete(v11);
LABEL_31:
        if ( !CreateDirectoryW(this, 0) )
        {
          LastError = GetLastError();
          if ( LastError != 183 )
          {
            if ( LastError )
            {
              v20 = 139;
              return wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)v20,
                       (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                       (const char *)LastError,
                       cchValue);
            }
          }
        }
        return 0;
      }
    }
    v18 = v13;
    v19 = 131;
    goto LABEL_38;
  }
  if ( LastError != 183 && LastError )
  {
    v20 = 145;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v20,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
             (const char *)LastError,
             cchValue);
  }
  return 0;
}

```

## disassembly

```asm
0x180038884  mov     [rsp+arg_0], rbx
0x180038889  mov     [rsp+arg_10], rbp
0x18003888e  push    rsi
0x18003888f  push    rdi
0x180038890  push    r14
0x180038892  sub     rsp, 30h
0x180038896  xor     edx, edx; lpSecurityAttributes
0x180038898  mov     rsi, rcx
0x18003889b  call    cs:__imp_CreateDirectoryW
0x1800388a1  xor     r14d, r14d
0x1800388a4  test    eax, eax
0x1800388a6  jnz     loc_180038AA1
0x1800388ac  call    cs:__imp_GetLastError
0x1800388b2  cmp     eax, 3
0x1800388b5  jnz     loc_180038A8F
0x1800388bb  lea     rdx, [rsp+48h+ppszRootEnd]; ppszRootEnd
0x1800388c0  mov     [rsp+48h+ppszRootEnd], r14
0x1800388c5  mov     rcx, rsi; pszPath
0x1800388c8  call    cs:__imp_PathCchSkipRoot
0x1800388ce  test    eax, eax
0x1800388d0  js      loc_180038A21
0x1800388d6  mov     rax, [rsp+48h+ppszRootEnd]
0x1800388db  cmp     [rax], r14w
0x1800388df  jz      loc_180038A21
0x1800388e5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800388e9  mov     r8, rbx
0x1800388ec  inc     r8
0x1800388ef  cmp     [rsi+r8*2], r14w
0x1800388f4  jnz     short loc_1800388EC
0x1800388f6  lea     rdi, [rsi+r8*2]
0x1800388fa  test    r8, r8
0x1800388fd  jz      short loc_180038909
0x1800388ff  cmp     word ptr [rdi-2], 5Ch ; '\'
0x180038904  jnz     short loc_180038909
0x180038906  dec     r8; cchSource
0x180038909  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x180038911  lea     r9, StringValue; "\\"
0x180038918  mov     rdx, rsi; lpStringSource
0x18003891b  mov     [rsp+48h+cchValue], 1; int
0x180038923  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x180038928  call    cs:__imp_FindStringOrdinal
0x18003892e  cmp     eax, ebx
0x180038930  jz      short loc_18003893C
0x180038932  movsxd  rdi, eax
0x180038935  inc     rdi
0x180038938  lea     rdi, [rsi+rdi*2]
0x18003893c  sub     rdi, rsi
0x18003893f  sar     rdi, 1
0x180038942  jz      loc_180038A21
0x180038948  lea     rbp, [rdi+1]
0x18003894c  mov     eax, 2
0x180038951  mul     rbp
0x180038954  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003895b  cmovb   rax, rbx
0x18003895f  mov     rcx, rax; unsigned __int64
0x180038962  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180038967  mov     rbx, rax
0x18003896a  test    rax, rax
0x18003896d  jnz     short loc_180038994
0x18003896f  mov     rcx, [rsp+48h]; this
0x180038974  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003897b  mov     ebx, 8007000Eh
0x180038980  mov     edx, 82h; void *
0x180038985  mov     r9d, ebx; char *
0x180038988  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003898d  mov     eax, ebx
0x18003898f  jmp     loc_180038AA3
0x180038994  test    rbp, rbp
0x180038997  jz      loc_180038A5C
0x18003899d  cmp     rbp, 7FFFFFFFh
0x1800389a4  jbe     short loc_1800389B0
0x1800389a6  mov     edi, 80070057h
0x1800389ab  jmp     loc_180038A66
0x1800389b0  cmp     rdi, 7FFFFFFEh
0x1800389b7  ja      short loc_1800389A6
0x1800389b9  mov     rax, rsi
0x1800389bc  mov     rdx, rbx
0x1800389bf  test    rdi, rdi
0x1800389c2  jz      short loc_1800389E0
0x1800389c4  movzx   ecx, word ptr [rax]
0x1800389c7  test    cx, cx
0x1800389ca  jz      short loc_1800389E0
0x1800389cc  mov     [rdx], cx
0x1800389cf  add     rax, 2
0x1800389d3  add     rdx, 2; unsigned __int16 *
0x1800389d7  dec     rdi
0x1800389da  sub     rbp, 1
0x1800389de  jnz     short loc_1800389BF
0x1800389e0  mov     rax, rbp
0x1800389e3  lea     rcx, [rdx-2]
0x1800389e7  neg     rax
0x1800389ea  sbb     edi, edi
0x1800389ec  not     edi
0x1800389ee  and     edi, 8007007Ah
0x1800389f4  test    rbp, rbp
0x1800389f7  cmovnz  rcx, rdx
0x1800389fb  mov     [rcx], r14w
0x1800389ff  jz      short loc_180038A6A
0x180038a01  mov     rcx, rbx; this
0x180038a04  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x180038a09  mov     edi, eax
0x180038a0b  test    eax, eax
0x180038a0d  jns     short loc_180038A19
0x180038a0f  mov     r9d, eax
0x180038a12  mov     edx, 84h
0x180038a17  jmp     short loc_180038A72
0x180038a19  mov     rcx, rbx; Block
0x180038a1c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180038a21  xor     edx, edx; lpSecurityAttributes
0x180038a23  mov     rcx, rsi; lpPathName
0x180038a26  call    cs:__imp_CreateDirectoryW
0x180038a2c  test    eax, eax
0x180038a2e  jnz     short loc_180038AA1
0x180038a30  call    cs:__imp_GetLastError
0x180038a36  cmp     eax, 0B7h
0x180038a3b  jz      short loc_180038AA1
0x180038a3d  test    eax, eax
0x180038a3f  jz      short loc_180038AA1
0x180038a41  mov     edx, 8Bh; void *
0x180038a46  mov     rcx, [rsp+48h]; this
0x180038a4b  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180038a52  mov     r9d, eax; char *
0x180038a55  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180038a5a  jmp     short loc_180038AA3
0x180038a5c  mov     edi, 80070057h
0x180038a61  test    rbp, rbp
0x180038a64  jz      short loc_180038A6A
0x180038a66  mov     [rax], r14w
0x180038a6a  mov     r9d, edi; char *
0x180038a6d  mov     edx, 83h; void *
0x180038a72  mov     rcx, [rsp+48h]; this
0x180038a77  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180038a7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038a83  mov     rcx, rbx; Block
0x180038a86  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180038a8b  mov     eax, edi
0x180038a8d  jmp     short loc_180038AA3
0x180038a8f  cmp     eax, 0B7h
0x180038a94  jz      short loc_180038AA1
0x180038a96  test    eax, eax
0x180038a98  jz      short loc_180038AA1
0x180038a9a  mov     edx, 91h
0x180038a9f  jmp     short loc_180038A46
0x180038aa1  xor     eax, eax
0x180038aa3  mov     rbx, [rsp+48h+arg_0]
0x180038aa8  mov     rbp, [rsp+48h+arg_10]
0x180038aad  add     rsp, 30h
0x180038ab1  pop     r14
0x180038ab3  pop     rdi
0x180038ab4  pop     rsi
0x180038ab5  retn
```
