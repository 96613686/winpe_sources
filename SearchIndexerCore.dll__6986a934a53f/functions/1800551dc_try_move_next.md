# try_move_next

- ea: `0x1800551dc`
- end: `0x180055427`
- name: `try_move_next`
- size: `587`
- prototype: `char __fastcall(_QWORD *, char **, __int64, const char **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180054aa0`
- `0x180055170`

## callees

- `0x180054fd0`
- `0x1800551dc`
- `0x180055430`
- `0x1800789c0`
- `0x1800ae990`
- `0x1800af620`

## import_xrefs

- `WS2_32!__imp_ntohl` at `0x180055339`
- `WS2_32!__imp_ntohl` at `0x180055339`
- `WS2_32!__imp_ntohs` at `0x180055379`
- `WS2_32!__imp_ntohs` at `0x180055379`

## string_xrefs

- `0x180055289`: `invalid multivalue blob (not enough bytes are left to read the entire varint)`

## pseudocode

```c
char __fastcall try_move_next(_QWORD *a1, char **a2, __int64 a3, const char **a4)
{
  _QWORD *v4; // rsi
  size_t v8; // rbp
  char result; // al
  const void *v11; // rdx
  unsigned __int8 Varint; // r12
  const char *v13; // rax
  unsigned __int64 v14; // r8
  unsigned __int64 v15; // rbp
  char *v16; // r9
  char *v17; // rcx
  __int64 v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int64 v21; // [rsp+28h] [rbp-50h] BYREF
  char v22; // [rsp+30h] [rbp-48h]

  *(_DWORD *)a3 = 5;
  v4 = a2 + 1;
  *(_QWORD *)(a3 + 8) = 0;
  *(_QWORD *)(a3 + 16) = 0;
  *a4 = 0;
  v8 = a1[1];
  if ( !v8 && *v4 )
  {
    *a4 = "invalid multivalue blob (has more body data than the header indicates should be present)";
    return 0;
  }
  v20 = 0;
  if ( v8 >= 9 )
  {
    Varint = sqlite3GetVarint(*a1, &v20);
  }
  else
  {
    v11 = (const void *)*a1;
    v21 = 0;
    v22 = 0;
    memcpy_0(&v21, v11, v8);
    Varint = sqlite3GetVarint(&v21, &v20);
    if ( Varint > v8 )
    {
      v13 = "invalid multivalue blob (not enough bytes are left to read the entire varint)";
LABEL_8:
      *a4 = v13;
      return 0;
    }
  }
  v21 = 0;
  if ( !get_sqlite3_serial_type_code_value_size(v20, &v21) )
  {
    v13 = "invalid multivalue blob (has a reserved serial type code)";
    goto LABEL_8;
  }
  v15 = v21;
  if ( *v4 < v21 )
  {
    v13 = "invalid multivalue blob (does not have enough body data for a header serial type code)";
    goto LABEL_8;
  }
  v16 = *a2;
  if ( v14 > 6 )
  {
    switch ( v14 )
    {
      case 7uLL:
        *(_DWORD *)a3 = 2;
        v19 = _byteswap_uint64(*(_QWORD *)v16);
        goto LABEL_39;
      case 8uLL:
        *(_DWORD *)a3 = 1;
        *(_QWORD *)(a3 + 8) = 0;
        goto LABEL_40;
      case 9uLL:
        *(_DWORD *)a3 = 1;
        *(_QWORD *)(a3 + 8) = 1;
        goto LABEL_40;
    }
    if ( v14 - 10 >= 2 )
    {
      *(_QWORD *)(a3 + 8) = v21;
      *(_QWORD *)(a3 + 16) = v16;
      *(_DWORD *)a3 = 4 - ((v14 & 1) != 0);
      goto LABEL_40;
    }
LABEL_35:
    *(_DWORD *)a3 = 5;
    goto LABEL_40;
  }
  switch ( v14 )
  {
    case 6uLL:
      *(_DWORD *)a3 = 1;
      v18 = _byteswap_uint64(*(_QWORD *)v16);
      goto LABEL_22;
    case 0uLL:
      goto LABEL_35;
    case 1uLL:
      *(_DWORD *)a3 = 1;
      v18 = *v16;
      goto LABEL_22;
    case 2uLL:
      *(_DWORD *)a3 = 1;
      v19 = (__int16)ntohs(*(_WORD *)v16);
      goto LABEL_39;
    case 3uLL:
      *(_DWORD *)a3 = 1;
      LODWORD(v18) = (unsigned __int8)v16[2]
                   | (((unsigned __int8)v16[1] | ((unsigned __int8)*v16 << 8)) << 8)
                   | 0xFF000000;
      if ( *v16 >= 0 )
        LODWORD(v18) = (unsigned __int8)v16[2] | (((unsigned __int8)v16[1] | ((unsigned __int8)*v16 << 8)) << 8);
      v18 = (int)v18;
      goto LABEL_22;
    case 4uLL:
      *(_DWORD *)a3 = 1;
      v19 = (int)ntohl(*(_DWORD *)v16);
LABEL_39:
      *(_QWORD *)(a3 + 8) = v19;
      goto LABEL_40;
  }
  v17 = *a2;
  *(_DWORD *)a3 = 1;
  v18 = sqlite3_from_int48(v17);
LABEL_22:
  *(_QWORD *)(a3 + 8) = v18;
LABEL_40:
  result = 1;
  *a1 += Varint;
  a1[1] -= Varint;
  *a2 += v15;
  *v4 -= v15;
  return result;
}

```

## disassembly

```asm
0x1800551dc  push    rbx
0x1800551de  push    rbp
0x1800551df  push    rsi
0x1800551e0  push    rdi
0x1800551e1  push    r12
0x1800551e3  push    r14
0x1800551e5  push    r15
0x1800551e7  sub     rsp, 40h
0x1800551eb  mov     rax, cs:__security_cookie
0x1800551f2  xor     rax, rsp
0x1800551f5  mov     [rsp+78h+var_40], rax
0x1800551fa  mov     dword ptr [r8], 5
0x180055201  lea     rsi, [rdx+8]
0x180055205  mov     qword ptr [r8+8], 0
0x18005520d  mov     rdi, r9
0x180055210  mov     qword ptr [r8+10h], 0
0x180055218  mov     rbx, r8
0x18005521b  mov     qword ptr [r9], 0
0x180055222  mov     r15, rdx
0x180055225  mov     rbp, [rcx+8]
0x180055229  mov     r14, rcx
0x18005522c  test    rbp, rbp
0x18005522f  jnz     short loc_180055247
0x180055231  cmp     [rsi], rbp
0x180055234  jbe     short loc_180055247
0x180055236  lea     rax, aInvalidMultiva_2; "invalid multivalue blob (has more body "...
0x18005523d  mov     [r9], rax
0x180055240  xor     al, al
0x180055242  jmp     loc_18005540B
0x180055247  mov     [rsp+78h+var_58], 0
0x180055250  cmp     rbp, 9
0x180055254  jnb     short loc_180055295
0x180055256  mov     rdx, [rcx]; Src
0x180055259  xor     eax, eax
0x18005525b  lea     rcx, [rsp+78h+var_50]; void *
0x180055260  mov     [rsp+78h+var_50], rax
0x180055265  mov     r8, rbp; Size
0x180055268  mov     [rsp+78h+var_48], al
0x18005526c  call    memcpy_0
0x180055271  lea     rdx, [rsp+78h+var_58]
0x180055276  lea     rcx, [rsp+78h+var_50]
0x18005527b  call    sqlite3GetVarint
0x180055280  movzx   r12d, al
0x180055284  cmp     r12, rbp
0x180055287  jbe     short loc_1800552A5
0x180055289  lea     rax, aInvalidMultiva; "invalid multivalue blob (not enough byt"...
0x180055290  mov     [rdi], rax
0x180055293  jmp     short loc_180055240
0x180055295  mov     rcx, [rcx]
0x180055298  lea     rdx, [rsp+78h+var_58]
0x18005529d  call    sqlite3GetVarint
0x1800552a2  mov     r12b, al
0x1800552a5  mov     r8, [rsp+78h+var_58]
0x1800552aa  lea     rdx, [rsp+78h+var_50]
0x1800552af  mov     rcx, r8
0x1800552b2  mov     [rsp+78h+var_50], 0
0x1800552bb  call    get_sqlite3_serial_type_code_value_size
0x1800552c0  test    al, al
0x1800552c2  jnz     short loc_1800552CD
0x1800552c4  lea     rax, aInvalidMultiva_3; "invalid multivalue blob (has a reserved"...
0x1800552cb  jmp     short loc_180055290
0x1800552cd  mov     rbp, [rsp+78h+var_50]
0x1800552d2  cmp     [rsi], rbp
0x1800552d5  jnb     short loc_1800552E0
0x1800552d7  lea     rax, aInvalidMultiva_1; "invalid multivalue blob (does not have "...
0x1800552de  jmp     short loc_180055290
0x1800552e0  mov     r9, [r15]
0x1800552e3  mov     edi, 1
0x1800552e8  cmp     r8, 6
0x1800552ec  ja      loc_180055397
0x1800552f2  jz      loc_18005538D
0x1800552f8  mov     rax, r8
0x1800552fb  test    r8, r8
0x1800552fe  jz      loc_1800553CB
0x180055304  sub     rax, rdi
0x180055307  jz      short loc_180055385
0x180055309  sub     rax, rdi
0x18005530c  jz      short loc_180055373
0x18005530e  sub     rax, rdi
0x180055311  jz      short loc_180055347
0x180055313  sub     rax, rdi
0x180055316  jz      short loc_180055334
0x180055318  cmp     rax, rdi
0x18005531b  jnz     loc_1800553B4
0x180055321  mov     rcx, r9
0x180055324  mov     [rbx], edi
0x180055326  call    sqlite3_from_int48
0x18005532b  mov     [rbx+8], rax
0x18005532f  jmp     loc_1800553F7
0x180055334  mov     [rbx], edi
0x180055336  mov     ecx, [r9]; netlong
0x180055339  call    cs:__imp_ntohl
0x18005533f  movsxd  rcx, eax
0x180055342  jmp     loc_1800553F3
0x180055347  mov     [rbx], edi
0x180055349  movzx   eax, byte ptr [r9+1]
0x18005534e  movzx   ecx, byte ptr [r9]
0x180055352  mov     edx, ecx
0x180055354  shl     edx, 8
0x180055357  or      edx, eax
0x180055359  movzx   eax, byte ptr [r9+2]
0x18005535e  shl     edx, 8
0x180055361  or      edx, eax
0x180055363  mov     eax, edx
0x180055365  or      eax, 0FF000000h
0x18005536a  test    cl, cl
0x18005536c  cmovns  eax, edx
0x18005536f  cdqe
0x180055371  jmp     short loc_18005532B
0x180055373  mov     [rbx], edi
0x180055375  movzx   ecx, word ptr [r9]; netshort
0x180055379  call    cs:__imp_ntohs
0x18005537f  movsx   rcx, ax
0x180055383  jmp     short loc_1800553F3
0x180055385  mov     [rbx], edi
0x180055387  movsx   rax, byte ptr [r9]
0x18005538b  jmp     short loc_18005532B
0x18005538d  mov     [rbx], edi
0x18005538f  mov     rax, [r9]
0x180055392  bswap   rax
0x180055395  jmp     short loc_18005532B
0x180055397  mov     rax, r8
0x18005539a  sub     rax, 7
0x18005539e  jz      short loc_1800553E7
0x1800553a0  sub     rax, rdi
0x1800553a3  jz      short loc_1800553DB
0x1800553a5  sub     rax, rdi
0x1800553a8  jz      short loc_1800553D3
0x1800553aa  sub     rax, rdi
0x1800553ad  jz      short loc_1800553CB
0x1800553af  cmp     rax, rdi
0x1800553b2  jz      short loc_1800553CB
0x1800553b4  and     r8b, dil
0x1800553b7  mov     [rbx+8], rbp
0x1800553bb  neg     r8b
0x1800553be  mov     [rbx+10h], r9
0x1800553c2  sbb     eax, eax
0x1800553c4  add     eax, 4
0x1800553c7  mov     [rbx], eax
0x1800553c9  jmp     short loc_1800553F7
0x1800553cb  mov     dword ptr [rbx], 5
0x1800553d1  jmp     short loc_1800553F7
0x1800553d3  mov     [rbx], edi
0x1800553d5  mov     [rbx+8], rdi
0x1800553d9  jmp     short loc_1800553F7
0x1800553db  mov     [rbx], edi
0x1800553dd  mov     qword ptr [rbx+8], 0
0x1800553e5  jmp     short loc_1800553F7
0x1800553e7  mov     dword ptr [rbx], 2
0x1800553ed  mov     rcx, [r9]
0x1800553f0  bswap   rcx
0x1800553f3  mov     [rbx+8], rcx
0x1800553f7  movzx   ecx, r12b
0x1800553fb  mov     al, dil
0x1800553fe  add     [r14], rcx
0x180055401  sub     [r14+8], rcx
0x180055405  add     [r15], rbp
0x180055408  sub     [rsi], rbp
0x18005540b  mov     rcx, [rsp+78h+var_40]
0x180055410  xor     rcx, rsp; StackCookie
0x180055413  call    __security_check_cookie
0x180055418  add     rsp, 40h
0x18005541c  pop     r15
0x18005541e  pop     r14
0x180055420  pop     r12
0x180055422  pop     rdi
0x180055423  pop     rsi
0x180055424  pop     rbp
0x180055425  pop     rbx
0x180055426  retn
```
