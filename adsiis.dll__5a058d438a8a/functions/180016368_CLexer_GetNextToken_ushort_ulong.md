# CLexer::GetNextToken(ushort *,ulong *)

- ea: `0x180016368`
- end: `0x1800164f0`
- name: `?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z`
- size: `392`
- prototype: `int(CLexer *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800160d0`
- `0x1800164f8`
- `0x180016630`
- `0x1800166f0`
- `0x180016818`

## callees

- `0x180016368`
- `0x18001d66a`

## pseudocode

```c
__int64 __fastcall CLexer::GetNextToken(CLexer *this, unsigned __int16 *a2, unsigned int *a3)
{
  unsigned __int16 *v3; // r14
  int v6; // esi
  unsigned __int16 *v7; // rcx
  unsigned __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // eax

  v3 = a2;
  v6 = 0;
  memset_0(a2, 0, 0x209u);
  *((_DWORD *)this + 4) = 0;
  while ( 1 )
  {
    v7 = *(unsigned __int16 **)this;
    if ( *(_QWORD *)this && (v8 = *v7, (_WORD)v8) )
    {
      *(_QWORD *)this = ++v7;
    }
    else
    {
      *((_DWORD *)this + 6) = 1;
      v8 = 0;
    }
    if ( v6 )
    {
      if ( (unsigned __int16)v8 <= 0x3Du && (v9 = 0x2400900000000001LL, _bittest64(&v9, v8)) || (_WORD)v8 == 92 )
      {
        if ( !*((_DWORD *)this + 6) )
          *(_QWORD *)this = v7 - 1;
LABEL_32:
        *a3 = 1;
        *((_DWORD *)this + 5) = 1;
        return 0;
      }
      if ( ((_WORD)v8 == 64 || (_WORD)v8 == 33) && !*((_DWORD *)this + 7) )
      {
        if ( !*((_DWORD *)this + 6) )
          *(_QWORD *)this -= 2LL;
        goto LABEL_32;
      }
      v10 = *((_DWORD *)this + 4);
      *((_DWORD *)this + 4) = v10 + 1;
      if ( v10 >= 0x105 )
        return 2147942523LL;
      *v3 = v8;
      goto LABEL_29;
    }
    v11 = *((_DWORD *)this + 4);
    *((_DWORD *)this + 4) = v11 + 1;
    if ( v11 >= 0x105 )
      return 2147942523LL;
    *v3 = v8;
    switch ( (_WORD)v8 )
    {
      case 0x5C:
        v12 = 3;
        goto LABEL_40;
      case 0x2F:
        v12 = 14;
        goto LABEL_40;
      case 0x2C:
        *a3 = 2;
        *((_DWORD *)this + 5) = 2;
        return 0;
      case 0x3D:
        v12 = 25;
        goto LABEL_40;
      case 0x3A:
        v12 = 13;
        goto LABEL_40;
      case 0:
        v12 = 4;
        goto LABEL_40;
      case 0x40:
        if ( !*((_DWORD *)this + 7) )
        {
          v12 = 11;
LABEL_40:
          *a3 = v12;
          *((_DWORD *)this + 5) = v12;
          return 0;
        }
        break;
      default:
        if ( (_WORD)v8 == 33 && !*((_DWORD *)this + 7) )
        {
          v12 = 12;
          goto LABEL_40;
        }
        break;
    }
LABEL_29:
    v6 = 1;
    ++v3;
  }
}

```

## disassembly

```asm
0x180016368  push    rbx
0x18001636a  push    rbp
0x18001636b  push    rsi
0x18001636c  push    rdi
0x18001636d  push    r14
0x18001636f  sub     rsp, 20h
0x180016373  mov     r14, rdx
0x180016376  mov     rdi, r8
0x180016379  mov     rbx, rcx
0x18001637c  xor     ebp, ebp
0x18001637e  mov     rcx, r14; void *
0x180016381  xor     edx, edx; Val
0x180016383  mov     r8d, 209h; Size
0x180016389  mov     esi, ebp
0x18001638b  call    memset_0
0x180016390  lea     r9d, [rbp+1]
0x180016394  mov     [rbx+10h], ebp
0x180016397  mov     r10d, 105h
0x18001639d  mov     rcx, [rbx]
0x1800163a0  test    rcx, rcx
0x1800163a3  jz      short loc_1800163B6
0x1800163a5  movzx   edx, word ptr [rcx]
0x1800163a8  test    dx, dx
0x1800163ab  jz      short loc_1800163B6
0x1800163ad  add     rcx, 2
0x1800163b1  mov     [rbx], rcx
0x1800163b4  jmp     short loc_1800163BC
0x1800163b6  mov     [rbx+18h], r9d
0x1800163ba  mov     edx, ebp
0x1800163bc  test    esi, esi
0x1800163be  jz      short loc_180016421
0x1800163c0  cmp     esi, r9d
0x1800163c3  jnz     loc_1800164E0
0x1800163c9  cmp     dx, 3Dh ; '='
0x1800163cd  ja      short loc_1800163E3
0x1800163cf  mov     r8, 2400900000000001h
0x1800163d9  bt      r8, rdx
0x1800163dd  jb      loc_18001648B
0x1800163e3  cmp     dx, 5Ch ; '\'
0x1800163e7  jz      loc_18001648B
0x1800163ed  cmp     dx, 40h ; '@'
0x1800163f1  jz      short loc_180016411
0x1800163f3  cmp     dx, 21h ; '!'
0x1800163f7  jz      short loc_180016411
0x1800163f9  mov     ecx, [rbx+10h]
0x1800163fc  lea     eax, [rcx+1]
0x1800163ff  mov     [rbx+10h], eax
0x180016402  cmp     ecx, r10d
0x180016405  jnb     loc_1800164E0
0x18001640b  mov     [r14], dx
0x18001640f  jmp     short loc_18001647F
0x180016411  cmp     [rbx+1Ch], ebp
0x180016414  jnz     short loc_1800163F9
0x180016416  cmp     [rbx+18h], ebp
0x180016419  jnz     short loc_180016497
0x18001641b  add     qword ptr [rbx], 0FFFFFFFFFFFFFFFEh
0x18001641f  jmp     short loc_180016497
0x180016421  mov     ecx, [rbx+10h]
0x180016424  lea     eax, [rcx+1]
0x180016427  mov     [rbx+10h], eax
0x18001642a  cmp     ecx, r10d
0x18001642d  jnb     loc_1800164E0
0x180016433  mov     [r14], dx
0x180016437  cmp     dx, 5Ch ; '\'
0x18001643b  jz      loc_1800164D2
0x180016441  cmp     dx, 2Fh ; '/'
0x180016445  jz      loc_1800164CB
0x18001644b  cmp     dx, 2Ch ; ','
0x18001644f  jz      short loc_1800164BC
0x180016451  cmp     dx, 3Dh ; '='
0x180016455  jz      short loc_1800164B5
0x180016457  cmp     dx, 3Ah ; ':'
0x18001645b  jz      short loc_1800164AE
0x18001645d  test    dx, dx
0x180016460  jz      short loc_1800164A7
0x180016462  cmp     dx, 40h ; '@'
0x180016466  jnz     short loc_180016474
0x180016468  cmp     [rbx+1Ch], ebp
0x18001646b  jnz     short loc_18001647F
0x18001646d  mov     eax, 0Bh
0x180016472  jmp     short loc_1800164D7
0x180016474  cmp     dx, 21h ; '!'
0x180016478  jnz     short loc_18001647F
0x18001647a  cmp     [rbx+1Ch], ebp
0x18001647d  jz      short loc_1800164A0
0x18001647f  mov     esi, r9d
0x180016482  add     r14, 2
0x180016486  jmp     loc_18001639D
0x18001648b  cmp     [rbx+18h], ebp
0x18001648e  jnz     short loc_180016497
0x180016490  lea     rax, [rcx-2]
0x180016494  mov     [rbx], rax
0x180016497  mov     [rdi], r9d
0x18001649a  mov     [rbx+14h], r9d
0x18001649e  jmp     short loc_1800164DC
0x1800164a0  mov     eax, 0Ch
0x1800164a5  jmp     short loc_1800164D7
0x1800164a7  mov     eax, 4
0x1800164ac  jmp     short loc_1800164D7
0x1800164ae  mov     eax, 0Dh
0x1800164b3  jmp     short loc_1800164D7
0x1800164b5  mov     eax, 19h
0x1800164ba  jmp     short loc_1800164D7
0x1800164bc  mov     dword ptr [rdi], 2
0x1800164c2  mov     dword ptr [rbx+14h], 2
0x1800164c9  jmp     short loc_1800164DC
0x1800164cb  mov     eax, 0Eh
0x1800164d0  jmp     short loc_1800164D7
0x1800164d2  mov     eax, 3
0x1800164d7  mov     [rdi], eax
0x1800164d9  mov     [rbx+14h], eax
0x1800164dc  xor     eax, eax
0x1800164de  jmp     short loc_1800164E5
0x1800164e0  mov     eax, 8007007Bh
0x1800164e5  add     rsp, 20h
0x1800164e9  pop     r14
0x1800164eb  pop     rdi
0x1800164ec  pop     rsi
0x1800164ed  pop     rbp
0x1800164ee  pop     rbx
0x1800164ef  retn
```
