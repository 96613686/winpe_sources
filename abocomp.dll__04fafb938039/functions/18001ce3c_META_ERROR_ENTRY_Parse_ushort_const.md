# META_ERROR_ENTRY::Parse(ushort const *)

- ea: `0x18001ce3c`
- end: `0x18001cfe2`
- name: `?Parse@META_ERROR_ENTRY@@QEAAJPEBG@Z`
- size: `422`
- prototype: `int(META_ERROR_ENTRY *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180021e80`

## callees

- `0x18001ce3c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001cf39`
- `msvcrt!_wcsicmp` at `0x18001cf52`
- `msvcrt!_wcsicmp` at `0x18001cf6b`
- `msvcrt!_wcsicmp` at `0x18001cf39`
- `msvcrt!_wcsicmp` at `0x18001cf52`
- `msvcrt!_wcsicmp` at `0x18001cf6b`
- `msvcrt!wcschr` at `0x18001ce8a`
- `msvcrt!wcschr` at `0x18001cedb`
- `msvcrt!wcschr` at `0x18001cf86`
- `msvcrt!wcschr` at `0x18001ce8a`
- `msvcrt!wcschr` at `0x18001cedb`
- `msvcrt!wcschr` at `0x18001cf86`
- `msvcrt!iswalpha` at `0x18001cf01`
- `msvcrt!iswalpha` at `0x18001cf1e`
- `msvcrt!iswalpha` at `0x18001cf01`
- `msvcrt!iswalpha` at `0x18001cf1e`
- `msvcrt!iswdigit` at `0x18001cebc`
- `msvcrt!iswdigit` at `0x18001cebc`
- `msvcrt!isspace` at `0x18001cea3`
- `msvcrt!isspace` at `0x18001cef4`
- `msvcrt!isspace` at `0x18001cf9b`
- `msvcrt!isspace` at `0x18001cea3`
- `msvcrt!isspace` at `0x18001cef4`
- `msvcrt!isspace` at `0x18001cf9b`
- `msvcrt!_wtoi` at `0x18001ce68`
- `msvcrt!_wtoi` at `0x18001cecd`
- `msvcrt!_wtoi` at `0x18001ce68`
- `msvcrt!_wtoi` at `0x18001cecd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001cfc1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001cfc1`

## pseudocode

```c
int __fastcall META_ERROR_ENTRY::Parse(META_ERROR_ENTRY *this, const unsigned __int16 *a2)
{
  unsigned __int16 v5; // r12
  wchar_t *v6; // rbx
  int v7; // r15d
  wchar_t *v8; // rbx
  wchar_t v9; // cx
  wchar_t *v10; // rdi
  wchar_t v11; // si
  int v12; // ebp
  wchar_t *v13; // rbx

  if ( !a2 )
    return -2147024809;
  v5 = _wtoi(a2);
  if ( v5 < 0x12Cu )
    return -2147024883;
  v6 = wcschr(a2, 0x2Cu);
  if ( !v6 )
    return -2147024883;
  do
    ++v6;
  while ( isspace(*(unsigned __int8 *)v6) );
  if ( *v6 == 42 )
  {
    v7 = -1;
  }
  else
  {
    if ( !iswdigit(*v6) )
      return -2147024883;
    v7 = _wtoi(v6);
  }
  v8 = wcschr(v6, 0x2Cu);
  if ( !v8 )
    return -2147024883;
  do
    ++v8;
  while ( isspace(*(unsigned __int8 *)v8) );
  if ( !iswalpha(*v8) )
    return -2147024883;
  v9 = *v8;
  v10 = v8;
  while ( iswalpha(v9) )
    v9 = *++v10;
  v11 = *v10;
  *v10 = 0;
  if ( _wcsicmp(v8, L"FILE") )
  {
    if ( _wcsicmp(v8, L"URL") )
    {
      if ( _wcsicmp(v8, L"REDIRECT") )
      {
        *v10 = v11;
        return -2147024883;
      }
      v12 = 2;
    }
    else
    {
      v12 = 1;
    }
  }
  else
  {
    v12 = 0;
  }
  *v10 = v11;
  v13 = wcschr(v10, 0x2Cu);
  if ( v13 )
  {
    do
      ++v13;
    while ( isspace(*(unsigned __int8 *)v13) );
    if ( *v13 )
    {
      *((_DWORD *)this + 15) = v5;
      *((_DWORD *)this + 14) = v7;
      *((_DWORD *)this + 16) = v12;
      return STRU::Copy(this, v13);
    }
  }
  return -2147024883;
}

```

## disassembly

```asm
0x18001ce3c  push    rbx
0x18001ce3e  push    rbp
0x18001ce3f  push    rsi
0x18001ce40  push    rdi
0x18001ce41  push    r12
0x18001ce43  push    r13
0x18001ce45  push    r14
0x18001ce47  push    r15
0x18001ce49  sub     rsp, 28h
0x18001ce4d  xor     r13d, r13d
0x18001ce50  mov     rbx, rdx
0x18001ce53  mov     r14, rcx
0x18001ce56  test    rdx, rdx
0x18001ce59  jnz     short loc_18001CE65
0x18001ce5b  mov     eax, 80070057h
0x18001ce60  jmp     loc_18001CFD1
0x18001ce65  mov     rcx, rbx; String
0x18001ce68  call    cs:__imp__wtoi
0x18001ce6e  mov     r12d, eax
0x18001ce71  mov     eax, 12Ch
0x18001ce76  cmp     r12w, ax
0x18001ce7a  jb      loc_18001CFCC
0x18001ce80  mov     edi, 2Ch ; ','
0x18001ce85  mov     rcx, rbx; Str
0x18001ce88  mov     edx, edi; Ch
0x18001ce8a  call    cs:__imp_wcschr
0x18001ce90  mov     rbx, rax
0x18001ce93  test    rax, rax
0x18001ce96  jz      loc_18001CFCC
0x18001ce9c  add     rbx, 2
0x18001cea0  movzx   ecx, byte ptr [rbx]; C
0x18001cea3  call    cs:__imp_isspace
0x18001cea9  test    eax, eax
0x18001ceab  jnz     short loc_18001CE9C
0x18001cead  cmp     word ptr [rbx], 2Ah ; '*'
0x18001ceb1  jnz     short loc_18001CEB9
0x18001ceb3  or      r15d, 0FFFFFFFFh
0x18001ceb7  jmp     short loc_18001CED6
0x18001ceb9  movzx   ecx, word ptr [rbx]; C
0x18001cebc  call    cs:__imp_iswdigit
0x18001cec2  test    eax, eax
0x18001cec4  jz      loc_18001CFCC
0x18001ceca  mov     rcx, rbx; String
0x18001cecd  call    cs:__imp__wtoi
0x18001ced3  mov     r15d, eax
0x18001ced6  mov     edx, edi; Ch
0x18001ced8  mov     rcx, rbx; Str
0x18001cedb  call    cs:__imp_wcschr
0x18001cee1  mov     rbx, rax
0x18001cee4  test    rax, rax
0x18001cee7  jz      loc_18001CFCC
0x18001ceed  add     rbx, 2
0x18001cef1  movzx   ecx, byte ptr [rbx]; C
0x18001cef4  call    cs:__imp_isspace
0x18001cefa  test    eax, eax
0x18001cefc  jnz     short loc_18001CEED
0x18001cefe  movzx   ecx, word ptr [rbx]; C
0x18001cf01  call    cs:__imp_iswalpha
0x18001cf07  test    eax, eax
0x18001cf09  jz      loc_18001CFCC
0x18001cf0f  movzx   ecx, word ptr [rbx]
0x18001cf12  mov     rdi, rbx
0x18001cf15  jmp     short loc_18001CF1E
0x18001cf17  add     rdi, 2
0x18001cf1b  movzx   ecx, word ptr [rdi]; C
0x18001cf1e  call    cs:__imp_iswalpha
0x18001cf24  test    eax, eax
0x18001cf26  jnz     short loc_18001CF17
0x18001cf28  movzx   esi, word ptr [rdi]
0x18001cf2b  lea     rdx, aFile; "FILE"
0x18001cf32  mov     rcx, rbx; String1
0x18001cf35  mov     [rdi], r13w
0x18001cf39  call    cs:__imp__wcsicmp
0x18001cf3f  test    eax, eax
0x18001cf41  jnz     short loc_18001CF48
0x18001cf43  mov     ebp, r13d
0x18001cf46  jmp     short loc_18001CF78
0x18001cf48  lea     rdx, aUrl_0; "URL"
0x18001cf4f  mov     rcx, rbx; String1
0x18001cf52  call    cs:__imp__wcsicmp
0x18001cf58  test    eax, eax
0x18001cf5a  jnz     short loc_18001CF61
0x18001cf5c  lea     ebp, [rax+1]
0x18001cf5f  jmp     short loc_18001CF78
0x18001cf61  lea     rdx, aRedirect_0; "REDIRECT"
0x18001cf68  mov     rcx, rbx; String1
0x18001cf6b  call    cs:__imp__wcsicmp
0x18001cf71  test    eax, eax
0x18001cf73  jnz     short loc_18001CFC9
0x18001cf75  lea     ebp, [rax+2]
0x18001cf78  mov     rax, rdi
0x18001cf7b  mov     edx, 2Ch ; ','; Ch
0x18001cf80  mov     rcx, rdi; Str
0x18001cf83  mov     [rax], si
0x18001cf86  call    cs:__imp_wcschr
0x18001cf8c  mov     rbx, rax
0x18001cf8f  test    rax, rax
0x18001cf92  jz      short loc_18001CFCC
0x18001cf94  add     rbx, 2
0x18001cf98  movzx   ecx, byte ptr [rbx]; C
0x18001cf9b  call    cs:__imp_isspace
0x18001cfa1  test    eax, eax
0x18001cfa3  jnz     short loc_18001CF94
0x18001cfa5  cmp     [rbx], r13w
0x18001cfa9  jz      short loc_18001CFCC
0x18001cfab  movzx   eax, r12w
0x18001cfaf  mov     rdx, rbx
0x18001cfb2  mov     rcx, r14
0x18001cfb5  mov     [r14+3Ch], eax
0x18001cfb9  mov     [r14+38h], r15d
0x18001cfbd  mov     [r14+40h], ebp
0x18001cfc1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001cfc7  jmp     short loc_18001CFD1
0x18001cfc9  mov     [rdi], si
0x18001cfcc  mov     eax, 8007000Dh
0x18001cfd1  add     rsp, 28h
0x18001cfd5  pop     r15
0x18001cfd7  pop     r14
0x18001cfd9  pop     r13
0x18001cfdb  pop     r12
0x18001cfdd  pop     rdi
0x18001cfde  pop     rsi
0x18001cfdf  pop     rbp
0x18001cfe0  pop     rbx
0x18001cfe1  retn
```
