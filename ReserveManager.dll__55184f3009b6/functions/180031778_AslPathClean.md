# AslPathClean

- ea: `0x180031778`
- end: `0x1800319b7`
- name: `AslPathClean`
- size: `575`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002f008`

## callees

- `0x180031778`
- `0x180031be0`
- `0x180031c04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800317b9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003180b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800317b9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003180b`

## pseudocode

```c
__int64 __fastcall AslPathClean(const wchar_t *Src, void *a2)
{
  unsigned __int64 v2; // rsi
  wchar_t *v6; // rbx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r8
  wchar_t v11; // ax
  unsigned __int64 v12; // rax
  wchar_t v13; // ax
  __int16 v14; // cx
  __int16 v15; // cx
  unsigned __int64 v16; // rax
  wchar_t v17; // ax

  v2 = -1;
  do
    ++v2;
  while ( Src[v2] );
  if ( v2 + 1 > 0x104 )
    return 3221225507LL;
  v6 = wcschr(Src, 0x3Au);
  if ( v6 )
    goto LABEL_10;
  v7 = 4;
  if ( !wcsncmp_0(Src, L"\\??\\", 4u) )
    goto LABEL_12;
  if ( !wcsncmp_0(Src, L"\\\\", 2u) )
  {
    v7 = 2;
    goto LABEL_12;
  }
  v6 = wcschr(Src, 0x5Cu);
  if ( v6 )
LABEL_10:
    v7 = ((unsigned __int64)((char *)v6 - (char *)Src) >> 1) + 1;
  else
    v7 = 1;
LABEL_12:
  memmove_0(a2, Src, 2 * v7);
  v8 = v7;
  v9 = v7;
  if ( v7 < v2 )
  {
    while ( 1 )
    {
      if ( Src[v9] == 92 || Src[v9] == 47 )
      {
        if ( !v8 || *((_WORD *)a2 + v8 - 1) != 92 )
          *((_WORD *)a2 + v8++) = 92;
        goto LABEL_54;
      }
      if ( Src[v9] != 46 )
        break;
      v10 = v9 + 1;
      if ( v9 + 1 == v2 )
        goto LABEL_55;
      v11 = Src[v9 + 1];
      if ( v11 == 92 || v11 == 47 )
      {
        ++v9;
        goto LABEL_54;
      }
      if ( v11 == 46 )
      {
        v12 = v9 + 2;
        if ( v9 + 2 == v2 || Src[v12] == 92 || Src[v12] == 47 )
        {
          while ( v8 >= v7 )
          {
            v14 = *((_WORD *)a2 + v8);
            *((_WORD *)a2 + v8) = 0;
            if ( v14 == 92 )
            {
              do
              {
                v15 = *((_WORD *)a2 + v8);
                *((_WORD *)a2 + v8) = 0;
                if ( v15 == 92 )
                  break;
                --v8;
              }
              while ( v8 >= v7 );
              break;
            }
            --v8;
          }
          v16 = v8 + 1;
          v9 = v10;
          if ( v8 >= v7 )
            v16 = v8;
          v8 = v16;
          goto LABEL_54;
        }
      }
      if ( Src[v9 + 2] != 92 && Src[v9 + 2] != 47 )
      {
        while ( v9 < v2 )
        {
          v17 = Src[v9];
          if ( v17 == 92 || v17 == 47 )
            goto LABEL_31;
          *((_WORD *)a2 + v8++) = v17;
          ++v9;
        }
LABEL_35:
        --v9;
      }
LABEL_54:
      if ( ++v9 >= v2 )
        goto LABEL_55;
    }
    while ( v9 < v2 )
    {
      v13 = Src[v9];
      if ( v13 == 92 || v13 == 47 )
      {
LABEL_31:
        if ( v8 >= 2 && *((_WORD *)a2 + v8 - 1) == 46 && *((_WORD *)a2 + v8 - 2) != 46 )
          --v8;
        goto LABEL_35;
      }
      *((_WORD *)a2 + v8++) = v13;
      ++v9;
    }
    goto LABEL_35;
  }
LABEL_55:
  *((_WORD *)a2 + v8) = 0;
  return 0;
}

```

## disassembly

```asm
0x180031778  push    rbx
0x18003177a  push    rbp
0x18003177b  push    rsi
0x18003177c  push    rdi
0x18003177d  push    r12
0x18003177f  push    r14
0x180031781  push    r15
0x180031783  sub     rsp, 20h
0x180031787  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003178b  mov     r14, rdx
0x18003178e  xor     r15d, r15d
0x180031791  mov     rdi, rcx
0x180031794  inc     rsi
0x180031797  cmp     [rcx+rsi*2], r15w
0x18003179c  jnz     short loc_180031794
0x18003179e  lea     rax, [rsi+1]
0x1800317a2  cmp     rax, 104h
0x1800317a8  jbe     short loc_1800317B4
0x1800317aa  mov     eax, 0C0000023h
0x1800317af  jmp     loc_1800319A8
0x1800317b4  mov     edx, 3Ah ; ':'; Ch
0x1800317b9  call    cs:__imp_wcschr
0x1800317bf  mov     ebp, 1
0x1800317c4  mov     rbx, rax
0x1800317c7  lea     r12d, [rbp+5Bh]
0x1800317cb  test    rax, rax
0x1800317ce  jnz     short loc_180031819
0x1800317d0  lea     ebx, [rax+4]
0x1800317d3  mov     rcx, rdi; String1
0x1800317d6  mov     r8d, ebx; MaxCount
0x1800317d9  lea     rdx, asc_18003F028; "\\??\\"
0x1800317e0  call    wcsncmp_0
0x1800317e5  test    eax, eax
0x1800317e7  jz      short loc_180031827
0x1800317e9  lea     r8d, [rbp+1]; MaxCount
0x1800317ed  mov     rcx, rdi; String1
0x1800317f0  lea     rdx, asc_18003EC6C; "\\\\"
0x1800317f7  call    wcsncmp_0
0x1800317fc  test    eax, eax
0x1800317fe  jnz     short loc_180031805
0x180031800  lea     ebx, [rbp+1]
0x180031803  jmp     short loc_180031827
0x180031805  mov     edx, r12d; Ch
0x180031808  mov     rcx, rdi; Str
0x18003180b  call    cs:__imp_wcschr
0x180031811  mov     rbx, rax
0x180031814  test    rax, rax
0x180031817  jz      short loc_180031824
0x180031819  sub     rbx, rdi
0x18003181c  shr     rbx, 1
0x18003181f  add     rbx, rbp
0x180031822  jmp     short loc_180031827
0x180031824  mov     rbx, rbp
0x180031827  lea     r8, [rbx+rbx]; Size
0x18003182b  mov     rdx, rdi; Src
0x18003182e  mov     rcx, r14; void *
0x180031831  call    memmove_0
0x180031836  mov     rdx, rbx
0x180031839  mov     rcx, rbx
0x18003183c  cmp     rbx, rsi
0x18003183f  jnb     loc_1800319A0
0x180031845  mov     r10w, 2Fh ; '/'
0x18003184a  mov     r9w, 2Eh ; '.'
0x18003184f  cmp     [rdi+rcx*2], r12w
0x180031854  jz      loc_18003197F
0x18003185a  cmp     [rdi+rcx*2], r10w
0x18003185f  jz      loc_18003197F
0x180031865  cmp     [rdi+rcx*2], r9w
0x18003186a  jnz     short loc_1800318EB
0x18003186c  lea     r8, [rcx+1]
0x180031870  cmp     r8, rsi
0x180031873  jz      loc_1800319A0
0x180031879  movzx   eax, word ptr [rdi+rcx*2+2]
0x18003187e  cmp     ax, r12w
0x180031882  jz      loc_18003197A
0x180031888  cmp     ax, r10w
0x18003188c  jz      loc_18003197A
0x180031892  cmp     ax, r9w
0x180031896  jnz     short loc_1800318B3
0x180031898  lea     rax, [rcx+2]
0x18003189c  cmp     rax, rsi
0x18003189f  jz      loc_180031926
0x1800318a5  cmp     [rdi+rax*2], r12w
0x1800318aa  jz      short loc_180031926
0x1800318ac  cmp     [rdi+rax*2], r10w
0x1800318b1  jz      short loc_180031926
0x1800318b3  cmp     [rdi+rcx*2+4], r12w
0x1800318b9  jz      loc_180031994
0x1800318bf  cmp     [rdi+rcx*2+4], r10w
0x1800318c5  jz      loc_180031994
0x1800318cb  jmp     loc_180031973
0x1800318d0  movzx   eax, word ptr [rdi+rcx*2]
0x1800318d4  cmp     ax, r12w
0x1800318d8  jz      short loc_1800318F2
0x1800318da  cmp     ax, r10w
0x1800318de  jz      short loc_1800318F2
0x1800318e0  mov     [r14+rdx*2], ax
0x1800318e5  add     rdx, rbp
0x1800318e8  add     rcx, rbp
0x1800318eb  cmp     rcx, rsi
0x1800318ee  jb      short loc_1800318D0
0x1800318f0  jmp     short loc_18003190B
0x1800318f2  cmp     rdx, 2
0x1800318f6  jb      short loc_18003190B
0x1800318f8  cmp     [r14+rdx*2-2], r9w
0x1800318fe  jnz     short loc_18003190B
0x180031900  cmp     [r14+rdx*2-4], r9w
0x180031906  jz      short loc_18003190B
0x180031908  sub     rdx, rbp
0x18003190b  sub     rcx, rbp
0x18003190e  jmp     loc_180031994
0x180031913  movzx   ecx, word ptr [r14+rdx*2]
0x180031918  mov     [r14+rdx*2], r15w
0x18003191d  cmp     cx, r12w
0x180031921  jz      short loc_18003192D
0x180031923  sub     rdx, rbp
0x180031926  cmp     rdx, rbx
0x180031929  jnb     short loc_180031913
0x18003192b  jmp     short loc_180031945
0x18003192d  movzx   ecx, word ptr [r14+rdx*2]
0x180031932  mov     [r14+rdx*2], r15w
0x180031937  cmp     cx, r12w
0x18003193b  jz      short loc_180031945
0x18003193d  sub     rdx, rbp
0x180031940  cmp     rdx, rbx
0x180031943  jnb     short loc_18003192D
0x180031945  cmp     rdx, rbx
0x180031948  lea     rax, [rdx+1]
0x18003194c  mov     rcx, r8
0x18003194f  cmovnb  rax, rdx
0x180031953  mov     rdx, rax
0x180031956  jmp     short loc_180031994
0x180031958  movzx   eax, word ptr [rdi+rcx*2]
0x18003195c  cmp     ax, r12w
0x180031960  jz      short loc_1800318F2
0x180031962  cmp     ax, r10w
0x180031966  jz      short loc_1800318F2
0x180031968  mov     [r14+rdx*2], ax
0x18003196d  add     rdx, rbp
0x180031970  add     rcx, rbp
0x180031973  cmp     rcx, rsi
0x180031976  jb      short loc_180031958
0x180031978  jmp     short loc_18003190B
0x18003197a  mov     rcx, r8
0x18003197d  jmp     short loc_180031994
0x18003197f  test    rdx, rdx
0x180031982  jz      short loc_18003198C
0x180031984  cmp     [r14+rdx*2-2], r12w
0x18003198a  jz      short loc_180031994
0x18003198c  mov     [r14+rdx*2], r12w
0x180031991  add     rdx, rbp
0x180031994  add     rcx, rbp
0x180031997  cmp     rcx, rsi
0x18003199a  jb      loc_18003184F
0x1800319a0  mov     [r14+rdx*2], r15w
0x1800319a5  mov     eax, r15d
0x1800319a8  add     rsp, 20h
0x1800319ac  pop     r15
0x1800319ae  pop     r14
0x1800319b0  pop     r12
0x1800319b2  pop     rdi
0x1800319b3  pop     rsi
0x1800319b4  pop     rbp
0x1800319b5  pop     rbx
0x1800319b6  retn
```
