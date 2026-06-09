# FileFolder::CompareIDsInternal(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x180007b30`
- end: `0x180007c67`
- name: `?CompareIDsInternal@FileFolder@@MEAAIPEFBU_ITEMIDLIST_RELATIVE@@0@Z`
- size: `311`
- prototype: `__int64 __fastcall(FileFolder *this, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002030`
- `0x18000591c`
- `0x180007b30`
- `0x1800088e4`

## pseudocode

```c
__int64 __fastcall FileFolder::CompareIDsInternal(
        FileFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        const struct _ITEMIDLIST_RELATIVE *a3)
{
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  char *v9; // rdx
  char *v10; // rax
  signed __int64 v11; // rdx
  unsigned __int16 v12; // cx
  unsigned int v13; // ebx
  __int128 v15; // [rsp+20h] [rbp-50h] BYREF
  __m128i v16; // [rsp+30h] [rbp-40h]
  __int128 v17; // [rsp+40h] [rbp-30h] BYREF
  __m128i si128; // [rsp+50h] [rbp-20h]

  if ( !a2 || (v4 = 0, !*(_WORD *)a2) )
    v4 = 1;
  if ( !a3 || (v5 = 0, !*(_WORD *)a3) )
    v5 = 1;
  if ( v4 || v5 )
    return (unsigned int)(v5 - v4);
  v6 = 4;
  v7 = 4;
  if ( a2 && *(_WORD *)a2 )
    v7 = *(_DWORD *)((char *)a2 + 2);
  v5 = v7 == 2;
  if ( a3 && *(_WORD *)a3 )
    v6 = *(unsigned int *)((char *)a3 + 2);
  v4 = v6 == 2;
  if ( v5 != v4 )
  {
    return (unsigned int)(v5 - v4);
  }
  else
  {
    v17 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v17) = 0;
    v15 = 0;
    v16 = si128;
    LOWORD(v15) = 0;
    FileFolder::GetFileFolderName(v6, a2, &v17);
    FileFolder::GetFileFolderName(v8, a3, &v15);
    v9 = (char *)&v15;
    if ( v16.m128i_i64[1] > 7uLL )
      v9 = (char *)v15;
    v10 = (char *)&v17;
    if ( si128.m128i_i64[1] > 7uLL )
      v10 = (char *)v17;
    v11 = v9 - v10;
    while ( 1 )
    {
      v12 = *(_WORD *)v10;
      if ( *(_WORD *)v10 != *(_WORD *)&v10[v11] )
        break;
      v10 += 2;
      if ( !v12 )
      {
        v13 = 0;
        goto LABEL_25;
      }
    }
    v13 = v12 < *(_WORD *)&v10[v11] ? -1 : 1;
LABEL_25:
    std::wstring::~wstring((char **)&v15);
    std::wstring::~wstring((char **)&v17);
  }
  return v13;
}

```

## disassembly

```asm
0x180007b30  mov     [rsp-18h+arg_0], rbx
0x180007b35  push    rbp
0x180007b36  push    rsi
0x180007b37  push    rdi
0x180007b38  mov     rbp, rsp
0x180007b3b  sub     rsp, 70h
0x180007b3f  mov     rax, cs:__security_cookie
0x180007b46  xor     rax, rsp
0x180007b49  mov     [rbp+var_10], rax
0x180007b4d  mov     rdi, r8
0x180007b50  xor     esi, esi
0x180007b52  test    rdx, rdx
0x180007b55  jz      short loc_180007B5E
0x180007b57  cmp     [rdx], si
0x180007b5a  mov     eax, esi
0x180007b5c  jnz     short loc_180007B63
0x180007b5e  mov     eax, 1
0x180007b63  test    rdi, rdi
0x180007b66  jz      short loc_180007B70
0x180007b68  cmp     [r8], si
0x180007b6c  mov     ebx, esi
0x180007b6e  jnz     short loc_180007B75
0x180007b70  mov     ebx, 1
0x180007b75  test    eax, eax
0x180007b77  jnz     loc_180007C47
0x180007b7d  test    ebx, ebx
0x180007b7f  jnz     loc_180007C47
0x180007b85  lea     ecx, [rax+4]
0x180007b88  mov     eax, ecx
0x180007b8a  test    rdx, rdx
0x180007b8d  jz      short loc_180007B97
0x180007b8f  cmp     [rdx], si
0x180007b92  jz      short loc_180007B97
0x180007b94  mov     eax, [rdx+2]
0x180007b97  mov     ebx, esi
0x180007b99  cmp     eax, 2
0x180007b9c  setz    bl
0x180007b9f  test    rdi, rdi
0x180007ba2  jz      short loc_180007BAE
0x180007ba4  cmp     [r8], si
0x180007ba8  jz      short loc_180007BAE
0x180007baa  mov     ecx, [r8+2]
0x180007bae  mov     eax, esi
0x180007bb0  cmp     ecx, 2
0x180007bb3  setz    al
0x180007bb6  cmp     ebx, eax
0x180007bb8  jnz     loc_180007C47
0x180007bbe  xorps   xmm0, xmm0
0x180007bc1  movups  [rbp+var_30], xmm0
0x180007bc5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180007bcd  movdqu  [rbp+var_20], xmm1
0x180007bd2  mov     word ptr [rbp+var_30], si
0x180007bd6  movups  [rbp+var_50], xmm0
0x180007bda  movdqu  [rbp+var_40], xmm1
0x180007bdf  mov     word ptr [rbp+var_50], si
0x180007be3  lea     r8, [rbp+var_30]
0x180007be7  call    ?GetFileFolderName@FileFolder@@IEAAXPEFBU_ITEMIDLIST@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FileFolder::GetFileFolderName(_ITEMIDLIST const *,std::wstring &)
0x180007bec  lea     r8, [rbp+var_50]
0x180007bf0  mov     rdx, rdi
0x180007bf3  call    ?GetFileFolderName@FileFolder@@IEAAXPEFBU_ITEMIDLIST@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FileFolder::GetFileFolderName(_ITEMIDLIST const *,std::wstring &)
0x180007bf8  lea     rdx, [rbp+var_50]
0x180007bfc  cmp     qword ptr [rbp+var_40+8], 7
0x180007c01  cmova   rdx, qword ptr [rbp+var_50]
0x180007c06  lea     rax, [rbp+var_30]
0x180007c0a  cmp     qword ptr [rbp+var_20+8], 7
0x180007c0f  cmova   rax, qword ptr [rbp+var_30]
0x180007c14  sub     rdx, rax
0x180007c17  movzx   ecx, word ptr [rax]
0x180007c1a  cmp     cx, [rax+rdx]
0x180007c1e  jnz     short loc_180007C2D
0x180007c20  add     rax, 2
0x180007c24  test    cx, cx
0x180007c27  jnz     short loc_180007C17
0x180007c29  mov     ebx, esi
0x180007c2b  jmp     short loc_180007C32
0x180007c2d  sbb     ebx, ebx
0x180007c2f  or      ebx, 1
0x180007c32  lea     rcx, [rbp+var_50]
0x180007c36  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007c3b  nop
0x180007c3c  lea     rcx, [rbp+var_30]
0x180007c40  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007c45  jmp     short loc_180007C49
0x180007c47  sub     ebx, eax
0x180007c49  mov     eax, ebx
0x180007c4b  mov     rcx, [rbp+var_10]
0x180007c4f  xor     rcx, rsp; StackCookie
0x180007c52  call    __security_check_cookie
0x180007c57  mov     rbx, [rsp+70h+arg_0]
0x180007c5f  add     rsp, 70h
0x180007c63  pop     rdi
0x180007c64  pop     rsi
0x180007c65  pop     rbp
0x180007c66  retn
```
