# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x18001c304`
- end: `0x18001c52f`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `555`
- prototype: `__int64 __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, reparse_path`

## callers

- `0x18001c304`
- `0x18001d80c`
- `0x18004aee0`

## callees

- `0x180003f50`
- `0x180003f98`
- `0x1800089e4`
- `0x18001c304`
- `0x18001ee9c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18001c3a8`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18001c3a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c32c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c4b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c32c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c4b0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001c31b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001c4a6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001c31b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001c4a6`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18001c348`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18001c348`

## string_xrefs

- `0x18001c3f4`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18001c4f0`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
int __fastcall wil::CreateDirectoryDeepNoThrow(const WCHAR *this, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  unsigned int v4; // r8d
  __int64 v5; // r8
  const WCHAR *v6; // rdi
  int StringOrdinal; // eax
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rbp
  unsigned __int64 v10; // rax
  wil *v11; // rax
  wil *v12; // rbx
  unsigned int v14; // edi
  const WCHAR *v15; // rax
  unsigned __int16 *v16; // rdx
  unsigned __int16 *v17; // rcx
  int DirectoryDeepNoThrow; // eax
  unsigned __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rdx
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
    v5 = -1;
    do
      ++v5;
    while ( this[v5] );
    v6 = &this[v5];
    if ( v5 && *(v6 - 1) == 92 )
      LODWORD(v5) = v5 - 1;
    StringOrdinal = FindStringOrdinal(0x800000u, this, v5, L"\\", 1, 1);
    if ( StringOrdinal != -1 )
      v6 = &this[StringOrdinal + 1];
    v8 = v6 - this;
    if ( !v8 )
      goto LABEL_31;
    v9 = v8 + 1;
    v10 = 2 * (v8 + 1);
    if ( !is_mul_ok(v8 + 1, 2u) )
      v10 = -1;
    v11 = (wil *)operator new[](v10, (const struct std::nothrow_t *)std::nothrow);
    v12 = v11;
    if ( !v11 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)0x8007000ELL,
        cchValue);
      return -2147024882;
    }
    if ( v8 == -1 )
    {
      v14 = -2147024809;
    }
    else if ( v9 > 0x7FFFFFFF || v8 > 0x7FFFFFFE )
    {
      v14 = -2147024809;
      *(_WORD *)v11 = 0;
    }
    else
    {
      v15 = this;
      v16 = (unsigned __int16 *)v12;
      do
      {
        if ( !v8 )
          break;
        if ( !*v15 )
          break;
        *v16++ = *v15++;
        --v8;
        --v9;
      }
      while ( v9 );
      v17 = v16 - 1;
      v14 = v9 == 0 ? 0x8007007A : 0;
      if ( v9 )
        v17 = v16;
      *v17 = 0;
      if ( v9 )
      {
        DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow(v12, v16);
        v14 = DirectoryDeepNoThrow;
        if ( DirectoryDeepNoThrow < 0 )
        {
          v19 = (unsigned int)DirectoryDeepNoThrow;
          v20 = 132;
LABEL_38:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
            (const char *)v19,
            cchValue);
          operator delete(v12);
          return v14;
        }
        operator delete(v12);
LABEL_31:
        if ( !CreateDirectoryW(this, 0) )
        {
          LastError = GetLastError();
          if ( LastError != 183 )
          {
            if ( LastError )
            {
              v21 = 139;
              return wil::details::in1diag3::Return_Win32(retaddr, (void *)v21, v4, (const char *)LastError, cchValue);
            }
          }
        }
        return 0;
      }
    }
    v19 = v14;
    v20 = 131;
    goto LABEL_38;
  }
  if ( LastError != 183 && LastError )
  {
    v21 = 145;
    return wil::details::in1diag3::Return_Win32(retaddr, (void *)v21, v4, (const char *)LastError, cchValue);
  }
  return 0;
}

```

## disassembly

```asm
0x18001c304  mov     [rsp+arg_0], rbx
0x18001c309  mov     [rsp+arg_10], rbp
0x18001c30e  push    rsi
0x18001c30f  push    rdi
0x18001c310  push    r14
0x18001c312  sub     rsp, 30h
0x18001c316  xor     edx, edx; lpSecurityAttributes
0x18001c318  mov     rsi, rcx
0x18001c31b  call    cs:__imp_CreateDirectoryW
0x18001c321  xor     r14d, r14d
0x18001c324  test    eax, eax
0x18001c326  jnz     loc_18001C51A
0x18001c32c  call    cs:__imp_GetLastError
0x18001c332  cmp     eax, 3
0x18001c335  jnz     loc_18001C508
0x18001c33b  lea     rdx, [rsp+48h+ppszRootEnd]; ppszRootEnd
0x18001c340  mov     [rsp+48h+ppszRootEnd], r14
0x18001c345  mov     rcx, rsi; pszPath
0x18001c348  call    cs:__imp_PathCchSkipRoot
0x18001c34e  test    eax, eax
0x18001c350  js      loc_18001C4A1
0x18001c356  mov     rax, [rsp+48h+ppszRootEnd]
0x18001c35b  cmp     [rax], r14w
0x18001c35f  jz      loc_18001C4A1
0x18001c365  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001c369  mov     r8, rbx
0x18001c36c  inc     r8
0x18001c36f  cmp     [rsi+r8*2], r14w
0x18001c374  jnz     short loc_18001C36C
0x18001c376  lea     rdi, [rsi+r8*2]
0x18001c37a  test    r8, r8
0x18001c37d  jz      short loc_18001C389
0x18001c37f  cmp     word ptr [rdi-2], 5Ch ; '\'
0x18001c384  jnz     short loc_18001C389
0x18001c386  dec     r8; cchSource
0x18001c389  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x18001c391  lea     r9, StringValue; "\\"
0x18001c398  mov     rdx, rsi; lpStringSource
0x18001c39b  mov     [rsp+48h+cchValue], 1; int
0x18001c3a3  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x18001c3a8  call    cs:__imp_FindStringOrdinal
0x18001c3ae  cmp     eax, ebx
0x18001c3b0  jz      short loc_18001C3BC
0x18001c3b2  movsxd  rdi, eax
0x18001c3b5  inc     rdi
0x18001c3b8  lea     rdi, [rsi+rdi*2]
0x18001c3bc  sub     rdi, rsi
0x18001c3bf  sar     rdi, 1
0x18001c3c2  jz      loc_18001C4A1
0x18001c3c8  lea     rbp, [rdi+1]
0x18001c3cc  mov     eax, 2
0x18001c3d1  mul     rbp
0x18001c3d4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c3db  cmovb   rax, rbx
0x18001c3df  mov     rcx, rax; unsigned __int64
0x18001c3e2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001c3e7  mov     rbx, rax
0x18001c3ea  test    rax, rax
0x18001c3ed  jnz     short loc_18001C414
0x18001c3ef  mov     rcx, [rsp+48h]; this
0x18001c3f4  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001c3fb  mov     ebx, 8007000Eh
0x18001c400  mov     edx, 82h; void *
0x18001c405  mov     r9d, ebx; char *
0x18001c408  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c40d  mov     eax, ebx
0x18001c40f  jmp     loc_18001C51C
0x18001c414  test    rbp, rbp
0x18001c417  jz      loc_18001C4D5
0x18001c41d  cmp     rbp, 7FFFFFFFh
0x18001c424  jbe     short loc_18001C430
0x18001c426  mov     edi, 80070057h
0x18001c42b  jmp     loc_18001C4DF
0x18001c430  cmp     rdi, 7FFFFFFEh
0x18001c437  ja      short loc_18001C426
0x18001c439  mov     rax, rsi
0x18001c43c  mov     rdx, rbx
0x18001c43f  test    rdi, rdi
0x18001c442  jz      short loc_18001C460
0x18001c444  movzx   ecx, word ptr [rax]
0x18001c447  test    cx, cx
0x18001c44a  jz      short loc_18001C460
0x18001c44c  mov     [rdx], cx
0x18001c44f  add     rax, 2
0x18001c453  add     rdx, 2; unsigned __int16 *
0x18001c457  dec     rdi
0x18001c45a  sub     rbp, 1
0x18001c45e  jnz     short loc_18001C43F
0x18001c460  mov     rax, rbp
0x18001c463  lea     rcx, [rdx-2]
0x18001c467  neg     rax
0x18001c46a  sbb     edi, edi
0x18001c46c  not     edi
0x18001c46e  and     edi, 8007007Ah
0x18001c474  test    rbp, rbp
0x18001c477  cmovnz  rcx, rdx
0x18001c47b  mov     [rcx], r14w
0x18001c47f  jz      short loc_18001C4E3
0x18001c481  mov     rcx, rbx; this
0x18001c484  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x18001c489  mov     edi, eax
0x18001c48b  test    eax, eax
0x18001c48d  jns     short loc_18001C499
0x18001c48f  mov     r9d, eax
0x18001c492  mov     edx, 84h
0x18001c497  jmp     short loc_18001C4EB
0x18001c499  mov     rcx, rbx; Block
0x18001c49c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c4a1  xor     edx, edx; lpSecurityAttributes
0x18001c4a3  mov     rcx, rsi; lpPathName
0x18001c4a6  call    cs:__imp_CreateDirectoryW
0x18001c4ac  test    eax, eax
0x18001c4ae  jnz     short loc_18001C51A
0x18001c4b0  call    cs:__imp_GetLastError
0x18001c4b6  cmp     eax, 0B7h
0x18001c4bb  jz      short loc_18001C51A
0x18001c4bd  test    eax, eax
0x18001c4bf  jz      short loc_18001C51A
0x18001c4c1  mov     edx, 8Bh; void *
0x18001c4c6  mov     rcx, [rsp+48h]; this
0x18001c4cb  mov     r9d, eax; char *
0x18001c4ce  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001c4d3  jmp     short loc_18001C51C
0x18001c4d5  mov     edi, 80070057h
0x18001c4da  test    rbp, rbp
0x18001c4dd  jz      short loc_18001C4E3
0x18001c4df  mov     [rax], r14w
0x18001c4e3  mov     r9d, edi; char *
0x18001c4e6  mov     edx, 83h; void *
0x18001c4eb  mov     rcx, [rsp+48h]; this
0x18001c4f0  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001c4f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c4fc  mov     rcx, rbx; Block
0x18001c4ff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c504  mov     eax, edi
0x18001c506  jmp     short loc_18001C51C
0x18001c508  cmp     eax, 0B7h
0x18001c50d  jz      short loc_18001C51A
0x18001c50f  test    eax, eax
0x18001c511  jz      short loc_18001C51A
0x18001c513  mov     edx, 91h
0x18001c518  jmp     short loc_18001C4C6
0x18001c51a  xor     eax, eax
0x18001c51c  mov     rbx, [rsp+48h+arg_0]
0x18001c521  mov     rbp, [rsp+48h+arg_10]
0x18001c526  add     rsp, 30h
0x18001c52a  pop     r14
0x18001c52c  pop     rdi
0x18001c52d  pop     rsi
0x18001c52e  retn
```
