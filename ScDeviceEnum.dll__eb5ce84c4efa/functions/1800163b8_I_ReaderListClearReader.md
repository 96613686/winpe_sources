# I_ReaderListClearReader

- ea: `0x1800163b8`
- end: `0x1800164f8`
- name: `I_ReaderListClearReader`
- size: `320`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001b00c`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x1800163b8`
- `0x1800171c4`
- `0x18001cc6c`
- `0x18001dfe2`

## pseudocode

```c
__int64 __fastcall I_ReaderListClearReader(__int64 a1, unsigned __int16 *a2, __int64 a3)
{
  unsigned int v4; // r15d
  char *v6; // rcx
  __int64 *i; // r14
  unsigned __int16 *v8; // rax
  int v9; // edx
  int v10; // r8d
  __int64 **v11; // r12
  __int64 v13; // rbp
  int v14; // esi
  int v15; // ebx
  __int64 *v16; // rdi
  int v17; // [rsp+90h] [rbp+18h] BYREF
  int v18; // [rsp+94h] [rbp+1Ch]

  v18 = HIDWORD(a3);
  v4 = 0;
  v17 = 0;
  WppTraceIndent(a1, 0);
  v6 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  for ( i = *(__int64 **)(a1 + 112); ; i = *v11 )
  {
    if ( !i )
    {
      v4 = 1168;
      goto LABEL_13;
    }
    v8 = a2;
    v6 = (char *)(*i - (_QWORD)a2);
    do
    {
      v9 = *(unsigned __int16 *)&v6[(_QWORD)v8];
      v10 = *v8 - v9;
      if ( v10 )
        break;
      ++v8;
    }
    while ( v9 );
    v11 = (__int64 **)(i + 30);
    if ( !v10 )
      break;
  }
  I_ReaderListFreeItemCommon(i, &v17);
  v13 = *i;
  v14 = *((_DWORD *)i + 2);
  v15 = *((_DWORD *)i + 3);
  v16 = *v11;
  memset_0(i + 2, 0, 0xE0u);
  *i = v13;
  *((_DWORD *)i + 2) = v14;
  *((_DWORD *)i + 3) = v15;
  *v11 = v16;
LABEL_13:
  WppTraceIndent(v6, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      191,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v4);
  }
  return v4;
}

```

## disassembly

```asm
0x1800163b8  mov     rax, rsp
0x1800163bb  mov     [rax+18h], r8
0x1800163bf  push    rbx
0x1800163c0  push    rbp
0x1800163c1  push    rsi
0x1800163c2  push    rdi
0x1800163c3  push    r12
0x1800163c5  push    r13
0x1800163c7  push    r14
0x1800163c9  push    r15
0x1800163cb  sub     rsp, 38h
0x1800163cf  mov     rbx, rdx
0x1800163d2  xor     r15d, r15d
0x1800163d5  xor     edx, edx
0x1800163d7  mov     [rax+18h], r15d
0x1800163db  mov     r14, rcx
0x1800163de  call    WppTraceIndent
0x1800163e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163ea  lea     r13, WPP_GLOBAL_Control
0x1800163f1  cmp     rcx, r13
0x1800163f4  jz      short loc_18001641E
0x1800163f6  test    byte ptr [rcx+1Ch], 2
0x1800163fa  jz      short loc_18001641E
0x1800163fc  cmp     byte ptr [rcx+19h], 5
0x180016400  jb      short loc_18001641E
0x180016402  mov     r9, cs:WPP_pszIndent
0x180016409  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180016410  mov     rcx, [rcx+10h]
0x180016414  mov     edx, 0BEh
0x180016419  call    WPP_SF_s
0x18001641e  mov     r14, [r14+70h]
0x180016422  jmp     short loc_180016452
0x180016424  mov     rcx, [r14]
0x180016427  mov     rax, rbx
0x18001642a  sub     rcx, rbx
0x18001642d  movzx   r8d, word ptr [rax]
0x180016431  movzx   edx, word ptr [rax+rcx]
0x180016435  sub     r8d, edx
0x180016438  jnz     short loc_180016442
0x18001643a  add     rax, 2
0x18001643e  test    edx, edx
0x180016440  jnz     short loc_18001642D
0x180016442  lea     r12, [r14+0F0h]
0x180016449  test    r8d, r8d
0x18001644c  jz      short loc_1800164B4
0x18001644e  mov     r14, [r12]
0x180016452  test    r14, r14
0x180016455  jnz     short loc_180016424
0x180016457  mov     r15d, 490h
0x18001645d  mov     edx, 1
0x180016462  call    WppTraceIndent
0x180016467  mov     rcx, cs:WPP_GLOBAL_Control
0x18001646e  cmp     rcx, r13
0x180016471  jz      short loc_1800164A0
0x180016473  test    byte ptr [rcx+1Ch], 2
0x180016477  jz      short loc_1800164A0
0x180016479  cmp     byte ptr [rcx+19h], 5
0x18001647d  jb      short loc_1800164A0
0x18001647f  mov     r9, cs:WPP_pszIndent
0x180016486  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001648d  mov     rcx, [rcx+10h]
0x180016491  mov     edx, 0BFh
0x180016496  mov     [rsp+78h+var_58], r15d
0x18001649b  call    WPP_SF_sd
0x1800164a0  mov     eax, r15d
0x1800164a3  add     rsp, 38h
0x1800164a7  pop     r15
0x1800164a9  pop     r14
0x1800164ab  pop     r13
0x1800164ad  pop     r12
0x1800164af  pop     rdi
0x1800164b0  pop     rsi
0x1800164b1  pop     rbp
0x1800164b2  pop     rbx
0x1800164b3  retn
0x1800164b4  lea     rdx, [rsp+78h+arg_10]
0x1800164bc  mov     rcx, r14
0x1800164bf  call    I_ReaderListFreeItemCommon
0x1800164c4  mov     rbp, [r14]
0x1800164c7  lea     rcx, [r14+10h]; void *
0x1800164cb  mov     esi, [r14+8]
0x1800164cf  xor     edx, edx; Val
0x1800164d1  mov     ebx, [r14+0Ch]
0x1800164d5  mov     r8d, 0E0h; Size
0x1800164db  mov     rdi, [r12]
0x1800164df  call    memset_0
0x1800164e4  mov     [r14], rbp
0x1800164e7  mov     [r14+8], esi
0x1800164eb  mov     [r14+0Ch], ebx
0x1800164ef  mov     [r12], rdi
0x1800164f3  jmp     loc_18001645D
```
