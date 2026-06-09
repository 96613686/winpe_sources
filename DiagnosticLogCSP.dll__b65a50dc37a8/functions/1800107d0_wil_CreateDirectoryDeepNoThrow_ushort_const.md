# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x1800107d0`
- end: `0x1800109b4`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `484`
- prototype: `__int64 __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path`

## callers

- `0x1800107d0`
- `0x1800109bc`

## callees

- `0x180001bf8`
- `0x180002bdc`
- `0x180005c24`
- `0x1800107d0`
- `0x1800112e0`
- `0x180011308`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180010883`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180010883`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010961`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010961`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800107e7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010951`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800107e7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010951`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x180010820`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x180010820`

## string_xrefs

- `0x1800108d5`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18001092b`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
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
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rdx
  __int64 v19; // rdx
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
            operator delete(v11, v18);
            return v12;
          }
          DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)v11, v15);
          v12 = DirectoryDeepNoThrow;
          if ( DirectoryDeepNoThrow < 0 )
          {
            v16 = 132;
            goto LABEL_22;
          }
          operator delete(v11, v17);
        }
      }
      if ( !CreateDirectoryW((LPCWSTR)this, 0) )
      {
        LastError = GetLastError();
        if ( LastError != 183 )
        {
          if ( LastError )
          {
            v19 = 139;
            return wil::details::in1diag3::Return_Win32(retaddr, (void *)v19, v4, (const char *)LastError, cchValue);
          }
        }
      }
    }
    else if ( LastError != 183 && LastError )
    {
      v19 = 145;
      return wil::details::in1diag3::Return_Win32(retaddr, (void *)v19, v4, (const char *)LastError, cchValue);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800107d0  mov     [rsp+arg_0], rbx
0x1800107d5  mov     [rsp+arg_10], rbp
0x1800107da  push    rsi
0x1800107db  push    rdi
0x1800107dc  push    r14
0x1800107de  sub     rsp, 30h
0x1800107e2  xor     edx, edx; lpSecurityAttributes
0x1800107e4  mov     rdi, rcx
0x1800107e7  call    cs:__imp_CreateDirectoryW
0x1800107ee  nop     dword ptr [rax+rax+00h]
0x1800107f3  xor     r14d, r14d
0x1800107f6  test    eax, eax
0x1800107f8  jnz     loc_18001099E
0x1800107fe  call    cs:__imp_GetLastError
0x180010805  nop     dword ptr [rax+rax+00h]
0x18001080a  cmp     eax, 3
0x18001080d  jnz     loc_18001098C
0x180010813  lea     rdx, [rsp+48h+ppszRootEnd]; ppszRootEnd
0x180010818  mov     [rsp+48h+ppszRootEnd], r14
0x18001081d  mov     rcx, rdi; pszPath
0x180010820  call    cs:__imp_PathCchSkipRoot
0x180010827  nop     dword ptr [rax+rax+00h]
0x18001082c  test    eax, eax
0x18001082e  js      loc_18001094C
0x180010834  mov     rax, [rsp+48h+ppszRootEnd]
0x180010839  cmp     [rax], r14w
0x18001083d  jz      loc_18001094C
0x180010843  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180010847  mov     r8, rsi
0x18001084a  inc     r8
0x18001084d  cmp     [rdi+r8*2], r14w
0x180010852  jnz     short loc_18001084A
0x180010854  lea     rbx, [rdi+r8*2]
0x180010858  test    r8, r8
0x18001085b  jz      short loc_180010867
0x18001085d  cmp     word ptr [rbx-2], 5Ch ; '\'
0x180010862  jnz     short loc_180010867
0x180010864  dec     r8; cchSource
0x180010867  mov     eax, 1
0x18001086c  lea     r9, StringValue; "\\"
0x180010873  mov     [rsp+48h+bIgnoreCase], eax; bIgnoreCase
0x180010877  mov     rdx, rdi; lpStringSource
0x18001087a  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x18001087f  mov     [rsp+48h+cchValue], eax; unsigned int
0x180010883  call    cs:__imp_FindStringOrdinal
0x18001088a  nop     dword ptr [rax+rax+00h]
0x18001088f  cmp     eax, esi
0x180010891  jz      short loc_18001089D
0x180010893  movsxd  rbx, eax
0x180010896  inc     rbx
0x180010899  lea     rbx, [rdi+rbx*2]
0x18001089d  sub     rbx, rdi
0x1800108a0  sar     rbx, 1
0x1800108a3  jz      loc_18001094C
0x1800108a9  lea     rbp, [rbx+1]
0x1800108ad  mov     eax, 2
0x1800108b2  mul     rbp
0x1800108b5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800108bc  cmovb   rax, rsi
0x1800108c0  mov     rcx, rax; unsigned __int64
0x1800108c3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800108c8  mov     rsi, rax
0x1800108cb  test    rax, rax
0x1800108ce  jnz     short loc_1800108F5
0x1800108d0  mov     rcx, [rsp+48h]; this
0x1800108d5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800108dc  mov     ebx, 8007000Eh
0x1800108e1  mov     edx, 82h; void *
0x1800108e6  mov     r9d, ebx; char *
0x1800108e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800108ee  mov     eax, ebx
0x1800108f0  jmp     loc_1800109A0
0x1800108f5  mov     r9, rbx; unsigned __int64
0x1800108f8  mov     r8, rdi; unsigned __int16 *
0x1800108fb  mov     rdx, rbp; unsigned __int64
0x1800108fe  mov     rcx, rsi; unsigned __int16 *
0x180010901  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180010906  mov     ebx, eax
0x180010908  test    eax, eax
0x18001090a  jns     short loc_180010913
0x18001090c  mov     edx, 83h
0x180010911  jmp     short loc_180010926
0x180010913  mov     rcx, rsi; this
0x180010916  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x18001091b  mov     ebx, eax
0x18001091d  test    eax, eax
0x18001091f  jns     short loc_180010944
0x180010921  mov     edx, 84h; void *
0x180010926  mov     rcx, [rsp+48h]; this
0x18001092b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010932  mov     r9d, eax; char *
0x180010935  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001093a  mov     rcx, rsi; void *
0x18001093d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010942  jmp     short loc_1800108EE
0x180010944  mov     rcx, rsi; void *
0x180010947  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001094c  xor     edx, edx; lpSecurityAttributes
0x18001094e  mov     rcx, rdi; lpPathName
0x180010951  call    cs:__imp_CreateDirectoryW
0x180010958  nop     dword ptr [rax+rax+00h]
0x18001095d  test    eax, eax
0x18001095f  jnz     short loc_18001099E
0x180010961  call    cs:__imp_GetLastError
0x180010968  nop     dword ptr [rax+rax+00h]
0x18001096d  cmp     eax, 0B7h
0x180010972  jz      short loc_18001099E
0x180010974  test    eax, eax
0x180010976  jz      short loc_18001099E
0x180010978  mov     edx, 8Bh; void *
0x18001097d  mov     rcx, [rsp+48h]; this
0x180010982  mov     r9d, eax; char *
0x180010985  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001098a  jmp     short loc_1800109A0
0x18001098c  cmp     eax, 0B7h
0x180010991  jz      short loc_18001099E
0x180010993  test    eax, eax
0x180010995  jz      short loc_18001099E
0x180010997  mov     edx, 91h
0x18001099c  jmp     short loc_18001097D
0x18001099e  xor     eax, eax
0x1800109a0  mov     rbx, [rsp+48h+arg_0]
0x1800109a5  mov     rbp, [rsp+48h+arg_10]
0x1800109aa  add     rsp, 30h
0x1800109ae  pop     r14
0x1800109b0  pop     rdi
0x1800109b1  pop     rsi
0x1800109b2  retn
```
