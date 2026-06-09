# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x1400260f0`
- end: `0x1400262d0`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `480`
- prototype: `__int64 __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1400260bc`
- `0x1400260f0`

## callees

- `0x140004be0`
- `0x140004f20`
- `0x1400117bc`
- `0x1400260f0`
- `0x1400287cc`
- `0x14002d2c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002611e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002611e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026243`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140026107`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140026233`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140026107`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140026233`

## string_xrefs

- `0x140026181`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x140026264`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x140026290`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
int __fastcall wil::CreateDirectoryDeepNoThrow(const WCHAR *this, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  unsigned __int64 *v4; // r8
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rax
  wil *v8; // rax
  wil *v9; // rbx
  unsigned int v11; // edi
  const WCHAR *v12; // rax
  unsigned __int16 *v13; // rdx
  unsigned __int16 *v14; // rcx
  int DirectoryDeepNoThrow; // eax
  const struct std::nothrow_t *v16; // rdx
  unsigned __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rdx
  const struct std::nothrow_t *v20; // rdx
  unsigned int v21; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned __int64 v23; // [rsp+48h] [rbp+10h] BYREF

  if ( CreateDirectoryW(this, 0) )
    return 0;
  LastError = GetLastError();
  if ( LastError == 3 )
  {
    v23 = 0;
    if ( !wil::try_get_parent_path_range(this, (const unsigned __int16 *)&v23, v4) )
      goto LABEL_22;
    v5 = v23;
    v6 = v23 + 1;
    v7 = 2 * (v23 + 1);
    if ( !is_mul_ok(v23 + 1, 2u) )
      v7 = -1;
    v8 = (wil *)operator new[](v7, (const struct std::nothrow_t *)std::nothrow);
    v9 = v8;
    if ( !v8 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
        (const char *)0x8007000ELL,
        v21);
      return -2147024882;
    }
    if ( v6 )
    {
      if ( v6 > 0x7FFFFFFF || v5 > 0x7FFFFFFE )
      {
        v11 = -2147024809;
        *(_WORD *)v8 = 0;
      }
      else
      {
        v12 = this;
        v13 = (unsigned __int16 *)v9;
        do
        {
          if ( !v5 )
            break;
          if ( !*v12 )
            break;
          *v13++ = *v12++;
          --v5;
          --v6;
        }
        while ( v6 );
        v14 = v13 - 1;
        v11 = v6 == 0 ? 0x8007007A : 0;
        if ( v6 )
          v14 = v13;
        *v14 = 0;
        if ( v6 )
        {
          DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow(v9, v13);
          v11 = DirectoryDeepNoThrow;
          if ( DirectoryDeepNoThrow < 0 )
          {
            v17 = (unsigned int)DirectoryDeepNoThrow;
            v18 = 132;
LABEL_29:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v18,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
              (const char *)v17,
              v21);
            operator delete(v9, v20);
            return v11;
          }
          operator delete(v9, v16);
LABEL_22:
          if ( !CreateDirectoryW(this, 0) )
          {
            LastError = GetLastError();
            if ( LastError != 183 )
            {
              if ( LastError )
              {
                v19 = 139;
                return wil::details::in1diag3::Return_Win32(
                         retaddr,
                         (void *)v19,
                         (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                         (const char *)LastError,
                         v21);
              }
            }
          }
          return 0;
        }
      }
    }
    else
    {
      v11 = -2147024809;
    }
    v17 = v11;
    v18 = 131;
    goto LABEL_29;
  }
  if ( LastError != 183 && LastError )
  {
    v19 = 145;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v19,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
             (const char *)LastError,
             v21);
  }
  return 0;
}

```

## disassembly

```asm
0x1400260f0  mov     [rsp+arg_0], rbx
0x1400260f5  mov     [rsp+arg_10], rbp
0x1400260fa  push    rsi
0x1400260fb  push    rdi
0x1400260fc  push    r14; int
0x1400260fe  sub     rsp, 20h
0x140026102  xor     edx, edx; lpSecurityAttributes
0x140026104  mov     rbp, rcx
0x140026107  call    cs:__imp_CreateDirectoryW
0x14002610e  nop     dword ptr [rax+rax+00h]
0x140026113  xor     r14d, r14d
0x140026116  test    eax, eax
0x140026118  jnz     loc_1400262BA
0x14002611e  call    cs:__imp_GetLastError
0x140026125  nop     dword ptr [rax+rax+00h]
0x14002612a  cmp     eax, 3
0x14002612d  jnz     loc_1400262A8
0x140026133  lea     rdx, [rsp+38h+arg_8]; unsigned __int16 *
0x140026138  mov     [rsp+38h+arg_8], r14
0x14002613d  mov     rcx, rbp; lpStringSource
0x140026140  call    ?try_get_parent_path_range@wil@@YA_NPEBGPEA_K@Z; wil::try_get_parent_path_range(ushort const *,unsigned __int64 *)
0x140026145  test    al, al
0x140026147  jz      loc_14002622E
0x14002614d  mov     rdi, [rsp+38h+arg_8]
0x140026152  lea     rcx, [r14-1]
0x140026156  lea     eax, [r14+2]
0x14002615a  lea     rsi, [rdi+1]
0x14002615e  mul     rsi
0x140026161  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140026168  cmovb   rax, rcx
0x14002616c  mov     rcx, rax; unsigned __int64
0x14002616f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140026174  mov     rbx, rax
0x140026177  test    rax, rax
0x14002617a  jnz     short loc_1400261A1
0x14002617c  mov     rcx, [rsp+38h]; this
0x140026181  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140026188  mov     ebx, 8007000Eh
0x14002618d  mov     edx, 82h; void *
0x140026192  mov     r9d, ebx; char *
0x140026195  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002619a  mov     eax, ebx
0x14002619c  jmp     loc_1400262BC
0x1400261a1  test    rsi, rsi
0x1400261a4  jz      loc_140026275
0x1400261aa  cmp     rsi, 7FFFFFFFh
0x1400261b1  jbe     short loc_1400261BD
0x1400261b3  mov     edi, 80070057h
0x1400261b8  jmp     loc_14002627F
0x1400261bd  cmp     rdi, 7FFFFFFEh
0x1400261c4  ja      short loc_1400261B3
0x1400261c6  mov     rax, rbp
0x1400261c9  mov     rdx, rbx
0x1400261cc  test    rdi, rdi
0x1400261cf  jz      short loc_1400261ED
0x1400261d1  movzx   ecx, word ptr [rax]
0x1400261d4  test    cx, cx
0x1400261d7  jz      short loc_1400261ED
0x1400261d9  mov     [rdx], cx
0x1400261dc  add     rax, 2
0x1400261e0  add     rdx, 2; unsigned __int16 *
0x1400261e4  dec     rdi
0x1400261e7  sub     rsi, 1
0x1400261eb  jnz     short loc_1400261CC
0x1400261ed  mov     rax, rsi
0x1400261f0  lea     rcx, [rdx-2]
0x1400261f4  neg     rax
0x1400261f7  sbb     edi, edi
0x1400261f9  not     edi
0x1400261fb  and     edi, 8007007Ah
0x140026201  test    rsi, rsi
0x140026204  cmovnz  rcx, rdx
0x140026208  mov     [rcx], r14w
0x14002620c  jz      short loc_140026283
0x14002620e  mov     rcx, rbx; this
0x140026211  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x140026216  mov     edi, eax
0x140026218  test    eax, eax
0x14002621a  jns     short loc_140026226
0x14002621c  mov     r9d, eax
0x14002621f  mov     edx, 84h
0x140026224  jmp     short loc_14002628B
0x140026226  mov     rcx, rbx; void *
0x140026229  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002622e  xor     edx, edx; lpSecurityAttributes
0x140026230  mov     rcx, rbp; lpPathName
0x140026233  call    cs:__imp_CreateDirectoryW
0x14002623a  nop     dword ptr [rax+rax+00h]
0x14002623f  test    eax, eax
0x140026241  jnz     short loc_1400262BA
0x140026243  call    cs:__imp_GetLastError
0x14002624a  nop     dword ptr [rax+rax+00h]
0x14002624f  cmp     eax, 0B7h
0x140026254  jz      short loc_1400262BA
0x140026256  test    eax, eax
0x140026258  jz      short loc_1400262BA
0x14002625a  mov     edx, 8Bh; void *
0x14002625f  mov     rcx, [rsp+38h]; this
0x140026264  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14002626b  mov     r9d, eax; char *
0x14002626e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140026273  jmp     short loc_1400262BC
0x140026275  mov     edi, 80070057h
0x14002627a  test    rsi, rsi
0x14002627d  jz      short loc_140026283
0x14002627f  mov     [rax], r14w
0x140026283  mov     r9d, edi; char *
0x140026286  mov     edx, 83h; void *
0x14002628b  mov     rcx, [rsp+38h]; this
0x140026290  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140026297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002629c  mov     rcx, rbx; void *
0x14002629f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400262a4  mov     eax, edi
0x1400262a6  jmp     short loc_1400262BC
0x1400262a8  cmp     eax, 0B7h
0x1400262ad  jz      short loc_1400262BA
0x1400262af  test    eax, eax
0x1400262b1  jz      short loc_1400262BA
0x1400262b3  mov     edx, 91h
0x1400262b8  jmp     short loc_14002625F
0x1400262ba  xor     eax, eax
0x1400262bc  mov     rbx, [rsp+38h+arg_0]
0x1400262c1  mov     rbp, [rsp+38h+arg_10]
0x1400262c6  add     rsp, 20h
0x1400262ca  pop     r14
0x1400262cc  pop     rdi
0x1400262cd  pop     rsi
0x1400262ce  retn
```
