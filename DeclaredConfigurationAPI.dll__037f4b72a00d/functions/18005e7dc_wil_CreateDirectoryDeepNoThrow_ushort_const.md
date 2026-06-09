# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x18005e7dc`
- end: `0x18005e92e`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `338`
- prototype: `__int64 __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18005e7dc`
- `0x180067160`
- `0x1800865e8`
- `0x1800869b0`
- `0x18009a348`

## callees

- `0x18000be80`
- `0x18000bf4c`
- `0x1800117dc`
- `0x18005e7dc`
- `0x18009a324`
- `0x18009ac5c`
- `0x1800a1fdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e7f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e8e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e7f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e8e5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005e7ea`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005e8db`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005e7ea`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005e8db`

## string_xrefs

- `0x18005e85d`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18005e8b3`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18005e900`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
int __fastcall wil::CreateDirectoryDeepNoThrow(wil *this, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  unsigned __int64 *v4; // r8
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // rbp
  unsigned __int64 v7; // rax
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rbx
  int DirectoryDeepNoThrow; // eax
  const unsigned __int16 *v12; // rdx
  int v13; // esi
  __int64 v14; // rdx
  __int64 v15; // rdx
  unsigned int v16; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned __int64 v18; // [rsp+58h] [rbp+10h] BYREF

  if ( !CreateDirectoryW((LPCWSTR)this, 0) )
  {
    LastError = GetLastError();
    if ( LastError == 3 )
    {
      v18 = 0;
      if ( wil::try_get_parent_path_range((LPCWSTR)this, (const unsigned __int16 *)&v18, v4) )
      {
        v5 = v18;
        v6 = v18 + 1;
        v7 = 2 * (v18 + 1);
        if ( !is_mul_ok(v18 + 1, 2u) )
          v7 = -1;
        v8 = (unsigned __int16 *)operator new[](v7, (const struct std::nothrow_t *)std::nothrow);
        v9 = v8;
        if ( !v8 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x82,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
            (const char *)0x8007000ELL,
            v16);
          return -2147024882;
        }
        DirectoryDeepNoThrow = StringCchCopyNW(v8, v6, (const unsigned __int16 *)this, v5);
        v13 = DirectoryDeepNoThrow;
        if ( DirectoryDeepNoThrow < 0 )
        {
          v14 = 131;
LABEL_12:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v14,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
            (const char *)(unsigned int)DirectoryDeepNoThrow,
            v16);
          operator delete(v9);
          return v13;
        }
        DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)v9, v12);
        v13 = DirectoryDeepNoThrow;
        if ( DirectoryDeepNoThrow < 0 )
        {
          v14 = 132;
          goto LABEL_12;
        }
        operator delete(v9);
      }
      if ( !CreateDirectoryW((LPCWSTR)this, 0) )
      {
        LastError = GetLastError();
        if ( LastError != 183 )
        {
          if ( LastError )
          {
            v15 = 139;
            return wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)v15,
                     (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                     (const char *)LastError,
                     v16);
          }
        }
      }
    }
    else if ( LastError != 183 && LastError )
    {
      v15 = 145;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v15,
               (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
               (const char *)LastError,
               v16);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18005e7dc  push    rbx
0x18005e7de  push    rbp
0x18005e7df  push    rsi
0x18005e7e0  push    rdi
0x18005e7e1  sub     rsp, 28h
0x18005e7e5  xor     edx, edx; lpSecurityAttributes
0x18005e7e7  mov     rdi, rcx
0x18005e7ea  call    cs:__imp_CreateDirectoryW
0x18005e7f0  test    eax, eax
0x18005e7f2  jnz     loc_18005E923
0x18005e7f8  call    cs:__imp_GetLastError
0x18005e7fe  cmp     eax, 3
0x18005e801  jnz     loc_18005E911
0x18005e807  lea     rdx, [rsp+48h+arg_8]; unsigned __int16 *
0x18005e80c  mov     [rsp+48h+arg_8], 0
0x18005e815  mov     rcx, rdi; lpStringSource
0x18005e818  call    ?try_get_parent_path_range@wil@@YA_NPEBGPEA_K@Z; wil::try_get_parent_path_range(ushort const *,unsigned __int64 *)
0x18005e81d  test    al, al
0x18005e81f  jz      loc_18005E8D6
0x18005e825  mov     rsi, [rsp+48h+arg_8]
0x18005e82a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005e831  mov     eax, 2
0x18005e836  lea     rbp, [rsi+1]
0x18005e83a  mul     rbp
0x18005e83d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005e844  cmovb   rax, rcx
0x18005e848  mov     rcx, rax; unsigned __int64
0x18005e84b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005e850  mov     rbx, rax
0x18005e853  test    rax, rax
0x18005e856  jnz     short loc_18005E87D
0x18005e858  mov     rcx, [rsp+48h]; this
0x18005e85d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005e864  mov     ebx, 8007000Eh
0x18005e869  mov     edx, 82h; void *
0x18005e86e  mov     r9d, ebx; char *
0x18005e871  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e876  mov     eax, ebx
0x18005e878  jmp     loc_18005E925
0x18005e87d  mov     r9, rsi; unsigned __int64
0x18005e880  mov     r8, rdi; unsigned __int16 *
0x18005e883  mov     rdx, rbp; unsigned __int64
0x18005e886  mov     rcx, rbx; unsigned __int16 *
0x18005e889  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18005e88e  mov     esi, eax
0x18005e890  test    eax, eax
0x18005e892  jns     short loc_18005E89B
0x18005e894  mov     edx, 83h
0x18005e899  jmp     short loc_18005E8AE
0x18005e89b  mov     rcx, rbx; this
0x18005e89e  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x18005e8a3  mov     esi, eax
0x18005e8a5  test    eax, eax
0x18005e8a7  jns     short loc_18005E8CE
0x18005e8a9  mov     edx, 84h; void *
0x18005e8ae  mov     rcx, [rsp+48h]; this
0x18005e8b3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005e8ba  mov     r9d, eax; char *
0x18005e8bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e8c2  mov     rcx, rbx; Block
0x18005e8c5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005e8ca  mov     eax, esi
0x18005e8cc  jmp     short loc_18005E925
0x18005e8ce  mov     rcx, rbx; Block
0x18005e8d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005e8d6  xor     edx, edx; lpSecurityAttributes
0x18005e8d8  mov     rcx, rdi; lpPathName
0x18005e8db  call    cs:__imp_CreateDirectoryW
0x18005e8e1  test    eax, eax
0x18005e8e3  jnz     short loc_18005E923
0x18005e8e5  call    cs:__imp_GetLastError
0x18005e8eb  cmp     eax, 0B7h
0x18005e8f0  jz      short loc_18005E923
0x18005e8f2  test    eax, eax
0x18005e8f4  jz      short loc_18005E923
0x18005e8f6  mov     edx, 8Bh; void *
0x18005e8fb  mov     rcx, [rsp+48h]; this
0x18005e900  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005e907  mov     r9d, eax; char *
0x18005e90a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005e90f  jmp     short loc_18005E925
0x18005e911  cmp     eax, 0B7h
0x18005e916  jz      short loc_18005E923
0x18005e918  test    eax, eax
0x18005e91a  jz      short loc_18005E923
0x18005e91c  mov     edx, 91h
0x18005e921  jmp     short loc_18005E8FB
0x18005e923  xor     eax, eax
0x18005e925  add     rsp, 28h
0x18005e929  pop     rdi
0x18005e92a  pop     rsi
0x18005e92b  pop     rbp
0x18005e92c  pop     rbx
0x18005e92d  retn
```
