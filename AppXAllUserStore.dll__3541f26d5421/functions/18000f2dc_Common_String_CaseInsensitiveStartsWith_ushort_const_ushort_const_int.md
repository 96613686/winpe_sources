# Common::String::CaseInsensitiveStartsWith(ushort const *,ushort const *,int *)

- ea: `0x18000f2dc`
- end: `0x18000f3de`
- name: `?CaseInsensitiveStartsWith@String@Common@@SAJPEBG0PEAH@Z`
- size: `258`
- prototype: `__int64 __fastcall(LPCWCH lpString1, const unsigned __int16 *, int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180028c10`
- `0x180029470`
- `0x180029a74`

## callees

- `0x18000f2dc`
- `0x180017f50`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f3a0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f3a0`

## string_xrefs

- `0x18000f3c2`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall Common::String::CaseInsensitiveStartsWith(LPCWCH lpString1, const unsigned __int16 *a2, int *a3)
{
  int v5; // edi
  __int64 v6; // rdx
  LPCWCH v7; // rax
  unsigned int v8; // ebx
  __int64 v9; // r11
  __int64 v10; // rcx
  const WCHAR *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  const WCHAR *v14; // rcx
  const WCHAR *v15; // r8
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !lpString1 )
  {
    v8 = -2147024809;
LABEL_18:
    v13 = 47;
    goto LABEL_19;
  }
  v5 = 1;
  v6 = 0x3FFFFFFF;
  v7 = lpString1;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  v8 = v6 == 0 ? 0x80070057 : 0;
  v9 = (0x3FFFFFFF - v6) & -(__int64)(v6 != 0);
  if ( !v6 )
    goto LABEL_18;
  v10 = 0x3FFFFFFF;
  v11 = L"S-";
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  v8 = v10 == 0 ? 0x80070057 : 0;
  v12 = (0x3FFFFFFF - v10) & ((unsigned __int128)-(__int128)(unsigned __int64)v10 >> 64);
  if ( !v10 )
  {
    v13 = 48;
LABEL_19:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v13,
      (int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)v8);
    return v8;
  }
  if ( (unsigned int)v9 < (unsigned int)v12 )
    goto LABEL_15;
  v14 = &dword_1800505A4;
  v15 = &dword_1800505A4;
  if ( (_DWORD)v12 )
  {
    v14 = lpString1;
    v15 = L"S-";
  }
  if ( CompareStringOrdinal(v14, v12, v15, v12, 1) != 2 )
LABEL_15:
    v5 = 0;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000f2dc  push    rbx
0x18000f2de  push    rbp
0x18000f2df  push    rsi
0x18000f2e0  push    rdi
0x18000f2e1  push    r14
0x18000f2e3  sub     rsp, 30h
0x18000f2e7  xor     ebp, ebp
0x18000f2e9  mov     rsi, r8
0x18000f2ec  mov     r10, rcx
0x18000f2ef  test    rcx, rcx
0x18000f2f2  jz      loc_18000F3B3
0x18000f2f8  mov     r9d, 3FFFFFFFh
0x18000f2fe  lea     edi, [rbp+1]
0x18000f301  mov     edx, r9d
0x18000f304  mov     rax, rcx
0x18000f307  cmp     [rax], bp
0x18000f30a  jz      short loc_18000F315
0x18000f30c  add     rax, 2
0x18000f310  sub     rdx, rdi
0x18000f313  jnz     short loc_18000F307
0x18000f315  mov     rax, rdx
0x18000f318  mov     r8d, 80070057h
0x18000f31e  neg     rax
0x18000f321  mov     rcx, r9
0x18000f324  mov     rax, rdx
0x18000f327  sbb     ebx, ebx
0x18000f329  sub     rcx, rdx
0x18000f32c  not     ebx
0x18000f32e  and     ebx, r8d
0x18000f331  neg     rax
0x18000f334  sbb     r11, r11
0x18000f337  and     r11, rcx
0x18000f33a  test    rdx, rdx
0x18000f33d  jz      short loc_18000F3B8
0x18000f33f  lea     r14, aS; "S-"
0x18000f346  mov     rcx, r9
0x18000f349  mov     rax, r14
0x18000f34c  cmp     [rax], bp
0x18000f34f  jz      short loc_18000F35A
0x18000f351  add     rax, 2
0x18000f355  sub     rcx, rdi
0x18000f358  jnz     short loc_18000F34C
0x18000f35a  mov     rax, rcx
0x18000f35d  neg     rax
0x18000f360  mov     rax, rcx
0x18000f363  sbb     ebx, ebx
0x18000f365  sub     r9, rcx
0x18000f368  not     ebx
0x18000f36a  and     ebx, r8d
0x18000f36d  neg     rax
0x18000f370  sbb     rdx, rdx
0x18000f373  and     rdx, r9; cchCount1
0x18000f376  test    rcx, rcx
0x18000f379  jnz     short loc_18000F380
0x18000f37b  lea     edx, [rcx+30h]
0x18000f37e  jmp     short loc_18000F3BD
0x18000f380  cmp     r11d, edx
0x18000f383  jb      short loc_18000F3AB
0x18000f385  test    edx, edx
0x18000f387  mov     [rsp+58h+bIgnoreCase], edi; bIgnoreCase
0x18000f38b  lea     rcx, dword_1800505A4
0x18000f392  mov     r9d, edx; cchCount2
0x18000f395  mov     r8, rcx
0x18000f398  cmovnz  rcx, r10; lpString1
0x18000f39c  cmovnz  r8, r14; lpString2
0x18000f3a0  call    cs:__imp_CompareStringOrdinal
0x18000f3a6  cmp     eax, 2
0x18000f3a9  jz      short loc_18000F3AD
0x18000f3ab  mov     edi, ebp
0x18000f3ad  mov     [rsi], edi
0x18000f3af  xor     eax, eax
0x18000f3b1  jmp     short loc_18000F3D3
0x18000f3b3  mov     ebx, 80070057h
0x18000f3b8  mov     edx, 2Fh ; '/'; void *
0x18000f3bd  mov     rcx, [rsp+58h]; this
0x18000f3c2  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\widest"...
0x18000f3c9  mov     r9d, ebx; char *
0x18000f3cc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f3d1  mov     eax, ebx
0x18000f3d3  add     rsp, 30h
0x18000f3d7  pop     r14
0x18000f3d9  pop     rdi
0x18000f3da  pop     rsi
0x18000f3db  pop     rbp
0x18000f3dc  pop     rbx
0x18000f3dd  retn
```
