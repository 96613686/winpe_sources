# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x18000ffb8`
- end: `0x180010177`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `447`
- prototype: `int __fastcall(wil *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path`

## callers

- `0x18000ffb8`
- `0x180010180`

## callees

- `0x180001bc8`
- `0x180002bac`
- `0x180005b04`
- `0x18000ffb8`
- `0x180010a60`
- `0x180010a84`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180010059`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180010059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ffe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001012b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ffe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001012b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000ffcf`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010121`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000ffcf`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010121`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18000fffc`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18000fffc`

## string_xrefs

- `0x1800100a5`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800100fb`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=2
int __fastcall wil::CreateDirectoryDeepNoThrow(wil *this, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  unsigned int v4; // r8d
  __int64 v5; // r8
  char *v6; // rbx
  int StringOrdinal; // eax
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // rax
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rsi
  int v12; // ebx
  int DirectoryDeepNoThrow; // eax
  const unsigned __int16 *v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  int cchValue; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  PCWSTR ppszRootEnd; // [rsp+58h] [rbp+10h] BYREF

  if ( !CreateDirectoryW((LPCWSTR)this, 0) )
  {
    LastError = GetLastError();
    if ( LastError == 3 )
    {
      ppszRootEnd = 0;
      if ( PathCchSkipRoot((PCWSTR)this, &ppszRootEnd) >= 0 && *ppszRootEnd )
      {
        v5 = -1;
        do
          ++v5;
        while ( *((_WORD *)this + v5) );
        v6 = (char *)this + 2 * v5;
        if ( v5 && *((_WORD *)v6 - 1) == 92 )
          LODWORD(v5) = v5 - 1;
        StringOrdinal = FindStringOrdinal(0x800000u, (LPCWSTR)this, v5, L"\\", 1, 1);
        if ( StringOrdinal != -1 )
          v6 = (char *)this + 2 * StringOrdinal + 2;
        v8 = (v6 - (char *)this) >> 1;
        if ( v8 )
        {
          v9 = 2 * (v8 + 1);
          if ( !is_mul_ok(v8 + 1, 2u) )
            v9 = -1;
          v10 = (unsigned __int16 *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
          v11 = v10;
          if ( !v10 )
          {
            v12 = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x82,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
              (const char *)0x8007000ELL,
              cchValue);
            return v12;
          }
          DirectoryDeepNoThrow = StringCchCopyNW(v10, v8 + 1, (const unsigned __int16 *)this, v8);
          v12 = DirectoryDeepNoThrow;
          if ( DirectoryDeepNoThrow < 0 )
          {
            v16 = 131;
LABEL_22:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v16,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
              (const char *)(unsigned int)DirectoryDeepNoThrow,
              cchValue);
            operator delete(v11);
            return v12;
          }
          DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)v11, v15);
          v12 = DirectoryDeepNoThrow;
          if ( DirectoryDeepNoThrow < 0 )
          {
            v16 = 132;
            goto LABEL_22;
          }
          operator delete(v11);
        }
      }
      if ( !CreateDirectoryW((LPCWSTR)this, 0) )
      {
        LastError = GetLastError();
        if ( LastError != 183 )
        {
          if ( LastError )
          {
            v17 = 139;
            return wil::details::in1diag3::Return_Win32(retaddr, (void *)v17, v4, (const char *)LastError, cchValue);
          }
        }
      }
    }
    else if ( LastError != 183 && LastError )
    {
      v17 = 145;
      return wil::details::in1diag3::Return_Win32(retaddr, (void *)v17, v4, (const char *)LastError, cchValue);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000ffb8  mov     [rsp+arg_0], rbx
0x18000ffbd  mov     [rsp+arg_10], rbp
0x18000ffc2  push    rsi
0x18000ffc3  push    rdi
0x18000ffc4  push    r14
0x18000ffc6  sub     rsp, 30h
0x18000ffca  xor     edx, edx; lpSecurityAttributes
0x18000ffcc  mov     rdi, rcx
0x18000ffcf  call    cs:__imp_CreateDirectoryW
0x18000ffd5  xor     r14d, r14d
0x18000ffd8  test    eax, eax
0x18000ffda  jnz     loc_180010162
0x18000ffe0  call    cs:__imp_GetLastError
0x18000ffe6  cmp     eax, 3
0x18000ffe9  jnz     loc_180010150
0x18000ffef  lea     rdx, [rsp+48h+ppszRootEnd]; ppszRootEnd
0x18000fff4  mov     [rsp+48h+ppszRootEnd], r14
0x18000fff9  mov     rcx, rdi; pszPath
0x18000fffc  call    cs:__imp_PathCchSkipRoot
0x180010002  test    eax, eax
0x180010004  js      loc_18001011C
0x18001000a  mov     rax, [rsp+48h+ppszRootEnd]
0x18001000f  cmp     [rax], r14w
0x180010013  jz      loc_18001011C
0x180010019  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001001d  mov     r8, rsi
0x180010020  inc     r8
0x180010023  cmp     [rdi+r8*2], r14w
0x180010028  jnz     short loc_180010020
0x18001002a  lea     rbx, [rdi+r8*2]
0x18001002e  test    r8, r8
0x180010031  jz      short loc_18001003D
0x180010033  cmp     word ptr [rbx-2], 5Ch ; '\'
0x180010038  jnz     short loc_18001003D
0x18001003a  dec     r8; cchSource
0x18001003d  mov     eax, 1
0x180010042  lea     r9, StringValue; "\\"
0x180010049  mov     [rsp+48h+bIgnoreCase], eax; bIgnoreCase
0x18001004d  mov     rdx, rdi; lpStringSource
0x180010050  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x180010055  mov     [rsp+48h+cchValue], eax; unsigned int
0x180010059  call    cs:__imp_FindStringOrdinal
0x18001005f  cmp     eax, esi
0x180010061  jz      short loc_18001006D
0x180010063  movsxd  rbx, eax
0x180010066  inc     rbx
0x180010069  lea     rbx, [rdi+rbx*2]
0x18001006d  sub     rbx, rdi
0x180010070  sar     rbx, 1
0x180010073  jz      loc_18001011C
0x180010079  lea     rbp, [rbx+1]
0x18001007d  mov     eax, 2
0x180010082  mul     rbp
0x180010085  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001008c  cmovb   rax, rsi
0x180010090  mov     rcx, rax; unsigned __int64
0x180010093  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180010098  mov     rsi, rax
0x18001009b  test    rax, rax
0x18001009e  jnz     short loc_1800100C5
0x1800100a0  mov     rcx, [rsp+48h]; this
0x1800100a5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800100ac  mov     ebx, 8007000Eh
0x1800100b1  mov     edx, 82h; void *
0x1800100b6  mov     r9d, ebx; char *
0x1800100b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800100be  mov     eax, ebx
0x1800100c0  jmp     loc_180010164
0x1800100c5  mov     r9, rbx; unsigned __int64
0x1800100c8  mov     r8, rdi; unsigned __int16 *
0x1800100cb  mov     rdx, rbp; unsigned __int64
0x1800100ce  mov     rcx, rsi; unsigned __int16 *
0x1800100d1  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800100d6  mov     ebx, eax
0x1800100d8  test    eax, eax
0x1800100da  jns     short loc_1800100E3
0x1800100dc  mov     edx, 83h
0x1800100e1  jmp     short loc_1800100F6
0x1800100e3  mov     rcx, rsi; this
0x1800100e6  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x1800100eb  mov     ebx, eax
0x1800100ed  test    eax, eax
0x1800100ef  jns     short loc_180010114
0x1800100f1  mov     edx, 84h; void *
0x1800100f6  mov     rcx, [rsp+48h]; this
0x1800100fb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010102  mov     r9d, eax; char *
0x180010105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001010a  mov     rcx, rsi; void *
0x18001010d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010112  jmp     short loc_1800100BE
0x180010114  mov     rcx, rsi; void *
0x180010117  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001011c  xor     edx, edx; lpSecurityAttributes
0x18001011e  mov     rcx, rdi; lpPathName
0x180010121  call    cs:__imp_CreateDirectoryW
0x180010127  test    eax, eax
0x180010129  jnz     short loc_180010162
0x18001012b  call    cs:__imp_GetLastError
0x180010131  cmp     eax, 0B7h
0x180010136  jz      short loc_180010162
0x180010138  test    eax, eax
0x18001013a  jz      short loc_180010162
0x18001013c  mov     edx, 8Bh; void *
0x180010141  mov     rcx, [rsp+48h]; this
0x180010146  mov     r9d, eax; char *
0x180010149  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001014e  jmp     short loc_180010164
0x180010150  cmp     eax, 0B7h
0x180010155  jz      short loc_180010162
0x180010157  test    eax, eax
0x180010159  jz      short loc_180010162
0x18001015b  mov     edx, 91h
0x180010160  jmp     short loc_180010141
0x180010162  xor     eax, eax
0x180010164  mov     rbx, [rsp+48h+arg_0]
0x180010169  mov     rbp, [rsp+48h+arg_10]
0x18001016e  add     rsp, 30h
0x180010172  pop     r14
0x180010174  pop     rdi
0x180010175  pop     rsi
0x180010176  retn
```
